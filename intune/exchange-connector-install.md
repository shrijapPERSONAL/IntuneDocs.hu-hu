---
title: "A helyszíni EAS Exchange Connector beállítása az Intune-ban"
titleSuffix: Azure portal
description: "Az Intune és a helyszíni Exchange Server közötti kommunikáció engedélyezése a Connector eszközzel"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39fb4b4b91eb6769eb1d5d95736cbbde141c6812
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Az Intune helyszíni Exchange Connector telepítése az Azure-beli Microsoft Intune-ban

A helyszíni Exchange Server-környezetekben az Intune helyszíni Exchange Connectorral felügyelhető az eszközök helyszíni Exchange-postaládákhoz való hozzáférése az alapján, hogy az eszköz regisztrálva van-e az Intune-ban, és hogy kompatibilis-e az Intune eszközmegfelelőségi szabályzataival. A helyszíni Exchange Connector felelős a helyszíni Exchange Serverekhez kapcsolódó mobileszközök észleléséért is a meglévő Exchange Active Sync (EAS) rekord és az Intune szinkronizálásával.

> [!IMPORTANT]
> Típustól függetlenül az Intune előfizetésenként csak egy helyszíni Exchange Connector kapcsolatot támogat.

Ha engedélyezni szeretne egy kapcsolatot, amely lehetővé teszi, hogy a Microsoft Intune kommunikáljon a helyszíni Exchange Serverrel, akkor kövesse az alábbi lépéseket:

1.  Töltse le az Intune helyszíni Exchange Connector eszközét az Azure Portalról.
2.  Telepítése és konfigurálja a helyszíni Intune Exchange Connectort.
3.  Az Exchange-kapcsolat ellenőrzése.

## <a name="on-premises-exchange-connector-requirements"></a>A helyszíni Exchange Connector rendszerkövetelményei
A következő táblázat a helyszíni Exchange Connector számítógépre vonatkozó követelményeit tartalmazza.

|Követelmény|További információ|
|---------------|--------------------|
|Operációs rendszerek|Az Intune a helyszíni Exchange Connectort olyan számítógépen támogatja, amelyen a Windows Server 2008 SP2 64 bites, a Windows Server 2008 R2, a Windows Server 2012 vagy a Windows Server 2012 R2 rendszer valamelyik kiadása fut.<br /><br />Az összekötő Server Core rendszereken nem támogatott.|
|Microsoft Exchange|A helyszíni összekötőhöz a Microsoft Exchange 2010 SP1 vagy újabb verziójára, vagy régi dedikált Exchange Online-ra van szükség. Lépjen kapcsolatba a fiókkezelővel annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **régi** konfigurációval rendelkezik-e.|
|Mobileszköz-kezelő szolgáltató| [Mobileszköz-kezelő szolgáltatóként a Microsoft Intune-t állítsa be](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Hardver|Azon számítógépnek, amelyre az összekötőt telepíteni kívánja, 1,6 GHz-es processzorral, 2 GB memóriával és legalább 10 GB szabad lemezterülettel kell rendelkeznie.|users-add.md
|Active Directory-szinkronizálás|Mielőtt az Intune-t a Connector segítségével csatlakoztatná az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](users-add.md), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure Active Directory meglévő példányával.|
|További szoftverek|Az összekötőt futtató számítógépnek a Microsoft .NET-keretrendszer 4.5-ös és a Windows PowerShell 2.0-s verziójának teljes telepítésével kell rendelkeznie.|
|Hálózat|Az összekötő telepítéséhez használt számítógépnek olyan tartományhoz kell tartoznia, amely megbízhatósági kapcsolatban áll az Exchange Server-t üzemeltető tartománnyal.<br /><br />A számítógépet úgy kell beállítani, hogy a 80-as és a 443-as porton, a tűzfalakon és a proxykiszolgálókon keresztül hozzáférjen az Intune szolgáltatáshoz. Az Intune által használt tartományok a következők: manage.microsoft.com, &#42;manage.microsoft.com és &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Active Directory-felhasználói fiókot, amelyet az Intune Exchange Connector fog használni. A fióknak engedéllyel kell rendelkeznie az alábbi szükséges Windows PowerShell Exchange-parancsmagok futtatásához:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Töltse le a helyszíni Exchange Connector szoftver telepítőcsomagját

1. Egy, a helyszíni Exchange Conectort támogató Windows Server rendszerben nyissa meg az [Azure Portalt](http://portal.azure.com), és jelentkezzen be egy olyan felhasználói fiókkal, amely rendszergazda a helyszíni Exchange Serveren, és van licence az Exchange Server használatához.

2. Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Az **Intune** kiválasztásával megnyílik az Intune irányítópult. Itt válassza a **Helyszíni hozzáférés** lehetőséget.

4. A **Helyszíni hozzáférés – Exchange ActiveSync-összekötő** panel **Beállítás** szakaszában válassza az **A helyszíni összekötő letöltése** elemet.

5.  A helyszíni Exchange Connectort egy tömörített (.zip) mappa tartalmazza, amelyet megnyithat vagy a számítógépre is menthet. A **Fájl letöltése** párbeszédpanelen kattintson a **Mentés** parancsra a tömörített mappa biztonságos helyre való mentéséhez.

    > [!IMPORTANT]
    > Ne nevezze és ne helyezze át a helyszíni Exchange Connector mappájában levő fájlokat. A mappa tartalmának áthelyezése vagy átnevezése az Exchange Connector sikertelen telepítését eredményezi.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>A helyszíni Intune Exchange Connector telepítése és konfigurálása
A helyszíni Intune Exchange Connector telepítéséhez hajtsa végre az alábbi lépéseket. A helyszíni Exchange Connector Intune-előfizetésenként csak egyszer és csak egy számítógépre telepíthető. Ha a helyszíni Exchange Connector szoftverből további példányt próbál meg konfigurálni, akkor az új kapcsolat felváltja az eredeti kapcsolatot.

1.  A helyszíni Exchange Connector által támogatott operációs rendszerben bontsa ki az **Exchange_Connector_Setup.zip** fájl tartalmát egy biztonságos helyre.

2.  A fájlok kibontása után nyissa meg a kibontott mappát, majd kattintson duplán az **Exchange_Connector_Setup.exe** fájlra a helyszíni Exchange Connector telepítéséhez.

    > [!IMPORTANT]
    > Ha a célmappa nem biztonságos hely, akkor a helyszíni Connector telepítése után törölje a **WindowsIntune.accountcert** tanúsítványfájlt.

3.  A **Microsoft Intune Exchange Connector** párbeszédpanelen válassza ki a **Helyszíni Microsoft Exchange Server** vagy **Üzemeltetett Microsoft Exchange Server** lehetőségek egyikét.

  ![Válassza ki a meglévő Exchange Server típusát](./media/intune-sa-exchange-connector-config.png)

  Helyszíni Exchange-kiszolgáló esetén adja meg az **Ügyfélelérési kiszolgáló** szerepkört futtató Exchange-kiszolgáló nevét vagy teljes tartománynevét.

  Üzemeltetett Exchange-kiszolgáló esetén adja meg az Exchange-kiszolgáló címét. Az üzemeltetett Exchange-kiszolgáló URL-címének megkeresése:

    1. Nyissa meg az Office 365 Outlook Web Appjét.

    2. Kattintson a **?** ikonra baloldalt felül, majd válassza a **Névjegy** lehetőséget.

    3. Keresse meg a **POP külső kiszolgáló** értéket.

    4. Kattintson a **Proxykiszolgáló** elemre az üzemeltetett Exchange proxykiszolgáló-beállításainak megadásához.
        1. Válassza a **Proxykiszolgáló használata mobileszköz-információk szinkronizálásakor**lehetőséget.

        2. Adja meg a **proxykiszolgáló nevét** és **portszámát** a kiszolgálóhoz való hozzáféréshez.

        3. Ha a proxykiszolgálóhoz való csatlakozáshoz hitelesítő adatok megadása szükséges, válassza a **Hitelesítő adatok használata a proxykiszolgálóhoz való csatlakozáshoz** lehetőséget. Ezután adja meg a **tartomány\felhasználó** és a **jelszó** értékét.

        4. Válassza az **OK** gombot.

    5. A **Felhasználó (Tartomány\felhasználó)** és **Jelszó** mezőknél adja meg az Exchange-kiszolgálóhoz való csatlakozáshoz szükséges hitelesítő adatokat.

    6.  Adja meg azokat a rendszergazdai hitelesítő adatokat, amelyek szükségesek ahhoz, hogy az értesítéseket egy felhasználó Exchange Server-postaládájába küldhesse a rendszer. Ezeket az értesítéseket a feltételes hozzáférési szabályzatokon keresztül konfigurálhatja az Intune-ban.

        Győződjön meg arról, hogy az Automatikus észlelés szolgáltatás és az Exchange-webszolgáltatások konfigurálva vannak az Exchange ügyfélelérési kiszolgálón. Az ezzel kapcsolatos további információkért lásd: [Ügyfélelérési kiszolgáló](https://technet.microsoft.com/library/dd298114.aspx).

    7.  A **Jelszó** mezőben adja meg a fiók jelszavát, hogy az Intune hozzáférhessen az Exchange-kiszolgálóhoz.

    8. Válassza a **Csatlakozás** elemet.

    > [!NOTE]
    > A kapcsolat konfigurálása néhány percig is eltarthat.

A konfiguráció alatt az Exchange Connector tárolja a proxybeállításait, hogy lehetővé tegye a kapcsolódást az internethez. Ha a proxybeállításai megváltoznak, az Exchange Connector ismételt konfigurálásával frissítenie kell az Exchange Connector proxybeállításait.

Miután az Exchange Connector létrehozta a kapcsolatot, azokat a mobileszközöket, amelyek az Exchange Connectorban felügyelt felhasználókhoz vannak társítva, a rendszer automatikusan szinkronizálja és hozzáadja az Exchange Connectorhoz. Ez a szinkronizálás eltarthat egy ideig.

> [!NOTE]
> Ha telepítette a helyszíni Exchange Connectort, de később törli az Exchange-kapcsolatot, akkor el kell távolítania a helyszíni Exchange Connectort is arról a számítógépről, amelyre telepítette.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása 
Miután az Exchange-összekötő létrehozott egy Exchange-kapcsolatot a megadott CAS (ügyfél-hozzáférési kiszolgáló) használatával, képes felfedezni más CAS kiszolgálókat is. Ha az elsődleges CAS elérhetetlenné válik, az összekötő átvált egy másik CAS-ra (ha elérhető), amíg az elsődleges CAS elérhetősége helyre nem áll. Ez a funkció alapértelmezés szerint be van kapcsolva. Ha szeretné kikapcsolni a funkciót, kövesse az alábbi eljárást:
1. Az Exchange-összekötőt futtató kiszolgálón nyissa meg a %*ProgramData*%\Microsoft\Windows Intune Exchange Connector mappát. 
2. Nyissa meg egy szövegszerkesztőben az **OnPremisesExchangeConnectorServiceConfiguration.xml** fájlt.
3. Módosítsa az &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; értéket az &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; értékre a funkció letiltásához.    


## <a name="monitor-the-exchange-connector-activity"></a>Az Exchange Connector tevékenységének figyelése

Az Exchange Connector sikeres konfigurálása után megtekintheti a kapcsolat és a legutóbbi sikeres szinkronizálási kísérlet állapotát. Az Exchange Connector kapcsolatának ellenőrzése:

1. Az Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget.
2. A kapcsolat állapotának ellenőrzéséhez a **Kezelés** alatt válassza a **Helyszíni Exchange-hozzáférés** lehetőséget.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

### <a name="system-center-operations-manager-scom-management-pack"></a>System Center Operations Manager (SCOM) felügyeleti csomag

Az Intune 1710-es kadásától kezdve használható [az Exchange Connectorhoz és az Intune-hoz készült SCOM felügyeleti csomag](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Ez számos megoldást nyújt az Exchange Connector figyelésére, amikor hibaelhárítás szükséges.

## <a name="next-steps"></a>További lépések
[Feltételes hozzáférési szabályzat létrehozása helyszíni Exchange-hez](conditional-access-exchange-create.md)

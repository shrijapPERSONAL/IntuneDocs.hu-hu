---
title: "A helyszíni EAS Exchange-összekötője | Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Exchange ActiveSync MDM – Az Intune felügyeleti konzol és a helyszíni Exchange Server közötti kommunikáció engedélyezése a Connector eszközzel"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2871136fc15f945fe5b757a6e4364d3980832e37
ms.openlocfilehash: 92e4a15630c70ac80dd07684baafbbd15cd2f38c


---

# <a name="install-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure-preview"></a>Az Intune helyszíni Exchange-összekötőjének telepítése az Azure-beli Microsoft Intune előzetesében

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Olyan kapcsolat beállításához, amely lehetővé teszi, hogy a Microsoft Intune kommunikáljon a mobileszközök postaládáit működtető Exchange-kiszolgálóval, le kell töltenie a helyszíni Exchange Connector összekötő eszközt, majd az Intune felügyeleti konzolról konfigurálnia kell azt. Típustól függetlenül az Intune előfizetésenként csak egy Exchange-Connector kapcsolatot támogat.

## <a name="on-premises-exchange-connector-requirements"></a>A helyszíni Exchange Connector rendszerkövetelményei
A következő táblázat a helyszíni Exchange Connector számítógépre vonatkozó követelményeit tartalmazza.

|Követelmény|További információ|
|---------------|--------------------|
|Operációs rendszerek|Az Intune a helyszíni Exchange Connectort olyan számítógépen támogatja, amelyen a Windows Server 2008 SP2 64 bites, a Windows Server 2008 R2, a Windows Server 2012 vagy a Windows Server 2012 R2 rendszer valamelyik kiadása fut.<br /><br />Az összekötő Server Core rendszereken nem támogatott.|
|Microsoft Exchange|A helyszíni összekötőhöz a Microsoft Exchange 2010 SP1 vagy újabb verziójára, vagy régi dedikált Exchange Online-ra van szükség. Lépjen kapcsolatba a fiókkezelővel annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **régi** konfigurációval rendelkezik-e.|
|Mobileszköz-kezelő szolgáltató| [Mobileszköz-kezelő szolgáltatóként a Microsoft Intune-t állítsa be](https://docs.microsoft.com/en-us/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).|
|Hardver|Azon számítógépnek, amelyre az összekötőt telepíteni kívánja, 1,6 GHz-es processzorral, 2 GB memóriával és legalább 10 GB szabad lemezterülettel kell rendelkeznie.|
|Active Directory-szinkronizálás|Mielőtt az Intune-t a Connector segítségével csatlakoztatná az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure Active Directory meglévő példányával.|
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

1. Egy, a helyszíni Exchange Connectort támogató Windows Server rendszerben nyissa meg az [Azure Portalt](http://portal.azure.com) olyan felhasználói fiókkal, amely rendszergazda az Exchange-bérlőben és van licence az Exchange Server használatához.

2.  Válassza a **Feltételes hozzáférés** számítási feladatot.
3.  Nyissa meg a **Helyszíni** panelt az Azure Portal **Feltételes hozzáférés** elemére kattintva.

4. A **Beállítás** szakaszban válassza az **Exchange ActiveSync helyszíni összekötő**, majd az **On-Premises Connector letöltése** elemet.

4.  A helyszíni Exchange Connectort egy tömörített (.zip) mappa tartalmazza, amelyet megnyithat vagy a számítógépre is menthet. A **Fájl letöltése** párbeszédpanelen kattintson a **Mentés** parancsra a tömörített mappa biztonságos helyre való mentéséhez.

> [!IMPORTANT]
> Ne nevezze és ne helyezze át a helyszíni Exchange Connector mappájában levő fájlokat. A mappa tartalmának áthelyezése vagy átnevezése sikertelen telepítést eredményez.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>A helyszíni Intune Exchange Connector telepítése és konfigurálása
A helyszíni Intune Exchange Connector telepítéséhez hajtsa végre az alábbi lépéseket. A helyszíni Exchange Connector Intune-előfizetésenként csak egyszer és csak egy számítógépre telepíthető. Ha a helyszíni Exchange Connector szoftverből további példányt próbál meg konfigurálni, akkor az új kapcsolat felváltja az eredeti kapcsolatot.

1.  A helyszíni Exchange Connector által támogatott operációs rendszerben bontsa ki az **Exchange_Connector_Setup.zip** fájl tartalmát egy biztonságos helyre.

2.  A fájlok kibontása után nyissa meg a kibontott mappát, majd kattintson duplán az **Exchange_Connector_Setup.exe** fájlra a helyszíni Exchange Connector telepítéséhez.

    > [!IMPORTANT]
    > Ha a célmappa nem biztonságos hely, akkor a helyszíni Connector telepítése után törölje a **WindowsIntune.accountcert** tanúsítványfájlt.

3.  A **Microsoft Intune Exchange Connector** párbeszédpanelen válassza ki a **Helyszíni Microsoft Exchange Server** vagy **Üzemeltetett Microsoft Exchange Server** lehetőségek egyikét.

  ![Válassza ki a meglévő Exchange Server típusát](../media/intune-sa-exchange-connector-config.png)

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

A kapcsolat konfigurálása néhány percig is eltarthat.

A konfiguráció alatt az Exchange Connector tárolja a proxybeállításait, hogy lehetővé tegye a kapcsolódást az internethez. Ha a proxybeállításai megváltoznak, az Exchange Connector ismételt konfigurálásával frissítenie kell az Exchange Connector proxybeállításait.

Miután az Exchange Connector létrehozta a kapcsolatot, azokat a mobileszközöket, amelyek az Exchange Connectorban felügyelt felhasználókhoz vannak társítva, a rendszer automatikusan szinkronizálja és hozzáadja az Exchange Connectorhoz. Ez a szinkronizálás eltarthat egy ideig.

> [!NOTE]
> Ha telepítette a helyszíni Exchange Connectort, de később törli az Exchange-kapcsolatot, akkor el kell távolítania a helyszíni Exchange Connectort is arról a számítógépről, amelyre telepítette.

## <a name="validate-the-exchange-connection"></a>Az Exchange-kapcsolat ellenőrzése

Az Exchange Connector sikeres konfigurálása után megtekintheti a kapcsolat és a legutóbbi sikeres szinkronizálási kísérlet állapotát. Az [Azure Portalon](http://portal.azure.com) válassza az **Intune** > **Feltételes hozzáférés** számítási feladatot. A **Beállítás** szakaszban válassza az **Exchange helyszíni összekötő** elemet, majd ellenőrizze, hogy a kapcsolat aktívként jelenik-e meg.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

## <a name="next-steps"></a>További lépések
[Feltételes hozzáférési szabályzat létrehozása helyszíni Exchange-hez](create-conditional-access-policy-for-exchange-on-premises.md)



<!--HONumber=Feb17_HO1-->



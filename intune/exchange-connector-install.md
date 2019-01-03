---
title: Állítsa be a Microsoft Intune helyszíni Exchange-összekötő |} A Microsoft Intune-ban
description: A helyszíni Exchange-összekötővel kezelheti az eszközök az Exchange-postaládákhoz való hozzáférését az Intune-regisztráció és az Exchange Active Sync (EAS) alapján.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 28886382da00f5c07129f4e69e0bbadf97634420
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817262"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Az Intune helyszíni Exchange-összekötőjének telepítése az Azure-beli Microsoft Intune-ban

Helyszíni Exchange Server-környezetben az Intune feltételes hozzáférési funkciójával engedélyezheti vagy letilthatja a helyszíni Exchange-postaládák elérését. Exchange Active Sync helyszíni összekötőkkel csatlakoztathatja az Intune-t az Exchange-szervezetéhez, és beállíthatja az Intune feltételes hozzáférési funkcióját eszközmegfelelőségi szabályzatokkal együtt. Ezután, amikor egy eszköz megpróbál csatlakozni az Exchange-hez, az Intune megállapítja, hogy az eszköz regisztrálva van-e az Intune-ban, és hogy megfelelő állapotú-e. Az Intune-ban való regisztráció megállapításához a helyszíni Exchange-összekötő leképezi az Exchange Serverben lévő Exchange Active Sync (EAS) -rekordokat Intune-rekordokká. További információért lásd: [Mik a feltételes hozzáférés használatának szokásos módjai az Intune-ban?](conditional-access-intune-common-ways-use.md)

> [!IMPORTANT]
> Az Intune mostantól egy előfizetésben több helyszíni Exchange-összekötőt is támogat. Ha a cége egynél több helyszíni Exchange-összekötővel rendelkezik, minden Exchange-szervezet részére külön összekötőt építhet ki.

Ha engedélyezni szeretne egy kapcsolatot, amely lehetővé teszi, hogy a Microsoft Intune kommunikáljon a helyszíni Exchange Serverrel, ennek általános lépései a következők:

1.  Töltse le az Intune helyszíni Exchange-összekötőjét az Azure Portalról.
2.  Telepítse és konfigurálja az Exchange-összekötőt a helyszíni Exchange-szervezet egyik számítógépén.
3.  Az Exchange-kapcsolat ellenőrzése.
4. Ismételje meg ezeket a lépéseket az összes olyan Exchange-szervezetnél, amelyet csatlakoztatni szeretne az Intune-hoz.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Az Intune helyszíni Exchange-összekötő követelményei
A következő táblázat a helyszíni Exchange-összekötő számítógépre vonatkozó követelményeit tartalmazza.


|            Követelmény             |                                                                                                                                                                                                        További információ                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Operációs rendszerek          |                                                               Az Intune a helyszíni Exchange-összekötőt olyan számítógépen támogatja, amelyen a Windows Server 2008 SP2 64 bites, a Windows Server 2008 R2, a Windows Server 2012, a Windows Server 2012 R2 vagy a Windows Server 2016 rendszer valamelyik kiadása fut.<br /><br />Az összekötő nem támogatott a Server Core telepítéseken.                                                                |
|         Microsoft Exchange         |                                                                           A helyszíni összekötőhöz a Microsoft Exchange 2010 SP3 vagy újabb verziójára, vagy régi dedikált Exchange Online-ra van szükség. Lépjen kapcsolatba a fiókkezelővel annak megállapításához, hogy a dedikált Exchange Online-környezet <strong>új</strong> vagy <strong>régi</strong> konfigurációval rendelkezik-e.                                                                           |
| Mobileszköz-kezelő szolgáltató |                                                                                                                              [Mobileszköz-kezelő szolgáltatóként a Microsoft Intune-t állítsa be](mdm-authority-set.md).                                                                                                                               |
|              Hardver              |                                                                                                                                                     Azon számítógépnek, amelyre az összekötőt telepíteni kívánja, 1,6 GHz-es processzorral, 2 GB memóriával és legalább 10 GB szabad lemezterülettel kell rendelkeznie.                                                                                                                                                      |
|  Active Directory-szinkronizálás  |                                                                                      Mielőtt az Intune-t az összekötő segítségével csatlakoztathatná az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](users-add.md), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure Active Directory meglévő példányával.                                                                                      |
|        További szoftverek         |                                                                                                                                           Az összekötőt futtató számítógépnek a Microsoft .NET-keretrendszer 4.5-ös és a Windows PowerShell 2.0-s verziójának teljes telepítésével kell rendelkeznie.                                                                                                                                           |
|              Network (Hálózat)               | Az összekötő telepítéséhez használt számítógépnek olyan tartományhoz kell tartoznia, amely megbízhatósági kapcsolatban áll az Exchange Server-t üzemeltető tartománnyal.<br /><br />A számítógépet úgy kell beállítani, hogy a 80-as és a 443-as porton, a tűzfalakon és a proxykiszolgálókon keresztül hozzáférjen az Intune szolgáltatáshoz. Az Intune által használt tartományok a következők: manage.microsoft.com, &#42;manage.microsoft.com és &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Active Directory-felhasználói fiókot, amelyet a helyszíni Exchange-összekötő fog használni. A fióknak engedéllyel kell rendelkeznie az alábbi szükséges Windows PowerShell Exchange-parancsmagok futtatásához:


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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>A helyszíni Exchange-összekötő szoftver telepítőcsomagjának letöltése

1. Egy, a helyszíni Exchange-összekötőt támogató Windows Server rendszerben nyissa meg az [Azure Portalt](https://portal.azure.com), és jelentkezzen be egy olyan felhasználói fiókkal, amely rendszergazda a helyszíni Exchange Serveren, és rendelkezik licenccel az Exchange Server használatához.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Válassza az **Intune** lehetőséget az Intune irányítópult megnyitásához. Itt válassza a **Helyszíni hozzáférés** lehetőséget.

4. A **Beállítás** területen válassza az **Exchange ActiveSync összekötő** lehetőséget, majd **A helyszíni összekötő letöltése** elemet.

5.  A helyszíni Exchange-összekötőt egy tömörített (.zip) mappa tartalmazza, amelyet megnyithat vagy a számítógépre menthet. A **Fájl letöltése** párbeszédpanelen kattintson a **Mentés** parancsra a tömörített mappa biztonságos helyre való mentéséhez.

    > [!IMPORTANT]
    > Ne nevezze és ne helyezze át a helyszíni Exchange-összekötő mappájában levő fájlokat. A mappa tartalmának áthelyezése vagy átnevezése az Exchange-összekötő sikertelen telepítését eredményezi.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>A helyszíni Intune Exchange-összekötő telepítése és konfigurálása
A helyszíni Intune Exchange-összekötő telepítéséhez hajtsa végre az alábbi lépéseket. Ha több Exchange-szervezettel rendelkezik, ismételje meg ezeket a lépéseket az összes további beállítandó Exchange-összekötő esetében.

1. Egy, a helyszíni Exchange-összekötő által támogatott operációs rendszerben bontsa ki az **Exchange_Connector_Setup.zip** fájl tartalmát egy biztonságos helyre.

2. A fájlok kibontása után nyissa meg a kibontott mappát, majd kattintson duplán az **Exchange_Connector_Setup.exe** fájlra a helyszíni Exchange-összekötő telepítéséhez.

   > [!IMPORTANT]
   > Ha a célmappa nem biztonságos hely, akkor a helyszíni összekötők telepítése után törölje a **MicrosoftIntune.accountcert** tanúsítványfájlt.

3. A **Microsoft Intune Exchange Connector** párbeszédpanelen válassza ki a **Helyszíni Microsoft Exchange Server** vagy **Üzemeltetett Microsoft Exchange Server** lehetőségek egyikét.

   ![Kép az Exchange-kiszolgáló típusának kiválasztási helyéről](./media/intune-sa-exchange-connector-config.png)

   Helyszíni Exchange-kiszolgáló esetén adja meg az **Ügyfélelérési kiszolgáló** szerepkört futtató Exchange-kiszolgáló nevét vagy teljes tartománynevét.

   Üzemeltetett Exchange-kiszolgáló esetén adja meg az Exchange-kiszolgáló címét. Az üzemeltetett Exchange-kiszolgáló URL-címének megkeresése:

   1. Nyissa meg az Office 365-ös Webes Outlookot.

   2. Kattintson a **?** ikonra baloldalt felül, majd válassza a **Névjegy** lehetőséget.

   3. Keresse meg a **POP külső kiszolgáló** értéket.

   4. Kattintson a **Proxykiszolgáló** elemre az üzemeltetett Exchange proxykiszolgáló-beállításainak megadásához.
       1. Válassza a **Proxykiszolgáló használata mobileszköz-információk szinkronizálásakor**lehetőséget.

       2. Adja meg a **proxykiszolgáló nevét** és **portszámát** a kiszolgálóhoz való hozzáféréshez.

       3. Ha a proxykiszolgálóhoz való csatlakozáshoz hitelesítő adatok megadása szükséges, válassza a **Hitelesítő adatok használata a proxykiszolgálóhoz való csatlakozáshoz** lehetőséget. Ezután adja meg a **tartomány\felhasználó** és a **jelszó** értékét.

       4. Válassza az **OK** gombot.

   5. A **Felhasználó (Tartomány\felhasználó)** és **Jelszó** mezőknél adja meg az Exchange-kiszolgálóhoz való csatlakozáshoz szükséges hitelesítő adatokat.

   6.  Adja meg azokat a hitelesítő adatokat, amelyek szükségesek ahhoz, hogy az értesítéseket egy felhasználó Exchange Server-postaládájába küldhesse a rendszer. Ezt a felhasználót dedikálhatja kizárólag az értékesítésekre. Az értesítésekkel foglalkozó felhasználónak egy Exchange-postaládára van szüksége az értesítések e-mailes küldéséhez. Ezeket az értesítéseket a feltételes hozzáférési szabályzatokon keresztül konfigurálhatja az Intune-ban.  

       Győződjön meg arról, hogy az Automatikus észlelés szolgáltatás és az Exchange-webszolgáltatások konfigurálva vannak az Exchange ügyfélelérési kiszolgálón. Az ezzel kapcsolatos további információkért lásd: [Ügyfélelérési kiszolgáló](https://technet.microsoft.com/library/dd298114.aspx).

   7.  A **Jelszó** mezőben adja meg a fiók jelszavát, hogy az Intune hozzáférhessen az Exchange-kiszolgálóhoz.

   8. Válassza a **Csatlakozás** elemet.

   > [!NOTE]
   > A kapcsolat konfigurálása néhány percig is eltarthat.

A konfiguráció során az Exchange-összekötő tárolja a proxybeállításait, hogy lehetővé tegye a kapcsolódást az internethez. Ha a proxybeállításai megváltoznak, az Exchange-összekötő ismételt konfigurálásával frissítenie kell az Exchange-összekötő proxybeállításait.

Miután az Exchange-összekötő létrehozta a kapcsolatot, azokat a mobileszközöket, amelyek az Exchange-ben felügyelt felhasználókhoz vannak társítva, a rendszer automatikusan szinkronizálja és hozzáadja az Exchange-összekötőhöz. Ez a szinkronizálás eltarthat egy ideig.

> [!NOTE]
> Ha telepítette a helyszíni Exchange-összekötőt, de később törli az Exchange-kapcsolatot, akkor el kell távolítania a helyszíni Exchange-összekötőt is arról a számítógépről, amelyre telepítette.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Összekötők telepítése több Exchange-szervezethez
Az Intune egy előfizetésben több helyszíni Exchange-összekötőt is támogat. Ha a bérlője több Exchange-szervezettel rendelkezik, minden Exchange-szervezet részére külön összekötőt állíthat be. Töltse le egyszer a .zip mappát, majd az előző szakasz lépéseit követve bontsa ki és futtassa a telepítőprogramot az egyes Exchange-szervezetek egyik kiszolgálóján.

Az alábbi szakaszokban ismertetett magas rendelkezésre állási, figyelési és manuális szinkronizálási szolgáltatásokat a rendszer az Intune-hoz csatlakoztatott összes Exchange-szervezetnél támogatja.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása 
Miután az Exchange-összekötő létrehozott egy Exchange-kapcsolatot a megadott CAS (ügyfél-hozzáférési kiszolgáló) használatával, képes felfedezni más CAS kiszolgálókat is. Ha az elsődleges CAS elérhetetlenné válik, az összekötő átvált egy másik CAS-ra (ha elérhető), amíg az elsődleges CAS elérhetősége helyre nem áll. Ez a funkció alapértelmezés szerint be van kapcsolva. Ha szeretné kikapcsolni a funkciót, kövesse az alábbi eljárást:
1. Az Exchange-összekötőt futtató kiszolgálón nyissa meg a %*ProgramData*%\Microsoft\Windows Intune Exchange Connector mappát. 
2. Nyissa meg egy szövegszerkesztőben az **OnPremisesExchangeConnectorServiceConfiguration.xml** fájlt.
3. Módosítsa az &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; értéket az &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; értékre a funkció letiltásához.    


## <a name="monitor-the-exchange-connector-activity"></a>Az Exchange Connector tevékenységének figyelése

Az Exchange-összekötő sikeres konfigurálása után megtekintheti a kapcsolat és a legutóbbi sikeres szinkronizálási kísérlet állapotát. Az Exchange-összekötő kapcsolatainak ellenőrzése:

1. Az Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget.
2. A **Beállítás** területen válassza az **Exchange ActiveSync összekötők** lehetőséget az egyes Exchange-összekötők csatlakozási állapotának ellenőrzéséhez.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

### <a name="system-center-operations-manager-scom-management-pack"></a>System Center Operations Manager (SCOM) felügyeleti csomag

Az Intune 1710-es kadásától kezdve használható [az Exchange Connectorhoz és az Intune-hoz készült SCOM felügyeleti csomag](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Ez számos megoldást nyújt az Exchange Connector figyelésére, amikor hibaelhárítás szükséges.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Gyors szinkronizálás vagy teljes szinkronizálás manuális kényszerítése
A helyszíni Exchange-összekötők automatikusan szinkronizálják az EAS- és az Intune-eszközrekordokat rendszeres időközönként. Ha egy eszköz megfelelőségi állapota megváltozik, az automatikus szinkronizálási folyamat rendszeresen frissíti a rekordokat az eszközelérés letiltásához vagy engedélyezéséhez.

   - **Gyors szinkronizálás** rendszeresen történik, naponta többször. A gyors szinkronizálás beolvassa azoknak az Intune-licenccel rendelkező és helyszíni feltételes Exchange-hozzáféréshez beállított felhasználóknak az eszközadatait, amelyek megváltoztak az utolsó szinkronizálás óta.

   - **Teljes szinkronizálás** naponta egyszer történik alapértelmezés szerint. A teljes szinkronizálás beolvassa az összes, Intune-licenccel rendelkező és helyszíni feltételes Exchange-hozzáféréshez beállított felhasználó eszközadatait. A teljes szinkronizálás emellett beolvassa az Exchange kiszolgálói adatait is, és biztosítja, hogy az Intune által az Azure Portalon megadott konfiguráció frissüljön az Exchange-kiszolgálón. 

Kényszerítheti a szinkronizálás futtatását egy összekötőn, ha a **Gyors szinkronizálás** vagy a **Teljes szinkronizálás** lehetőséget választja az Intune-irányítópulton. Ehhez kövesse az alábbi lépéseket:

   1. Az Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget.
   2. A **Beállítás** területen válassza az **Exchange Active Sync összekötő** lehetőséget.
   3. Válassza a szinkronizálni kívánt összekötőt, majd válassza a **Gyors szinkronizálás** vagy a **Teljes szinkronizálás** lehetőséget.

## <a name="next-steps"></a>További lépések
[Feltételes hozzáférési szabályzat létrehozása helyszíni Exchange-hez](conditional-access-exchange-create.md)

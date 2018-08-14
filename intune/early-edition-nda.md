---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f9849b2c327397c0b8945ee42d9fca7f9f46250
ms.sourcegitcommit: 58cddb08b64bd60f041eff46ff215e83e13db4e6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40001910"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>A Microsoft Intune előzetes kiadása – 2018. augusztus

> [!Note]
> Titoktartási szerződés hatálya alá tartozó tájékoztatás: A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az itt, nagyon szűk körben megosztott információkra titoktartási szerződés vonatkozik. Az információk egy részletét se tegye közzé közösségi médiában vagy nyilvános webhelyeken, például Twitteren, UserVoice-on, Redditen vagy hasonlón. 

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza, titoktartási szerződés hatálya alatt. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Az információkat ne tweetelje, ne tegye közzé a UserVoice-on, és más módon se ossza meg a vállalatán kívül. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>A Windows Hello a jövőben felhasználókat és eszközöket céloz meg <!-- 1106609 -->
A [Windows Hello for Business](windows-hello.md) szabályzatának létrehozásakor a szabályzat az összes cégen belüli felhasználóra vonatkozik (a bérlő egészén). Ezzel a frissítéssel a szabályzat alkalmazható lesz egy adott eszközkonfigurációs szabályzatot használó konkrét felhasználókra és eszközökre is (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Identitásvédelem** > **Windows Hello for Business**).

Az Azure Portalon az Intune-ban a Windows Hello konfigurációja és beállításai az **Eszközregisztráció** és az **Eszközkonfiguráció** területen is jelen lesznek. Az **Eszközregisztráció** a teljes céget célozza (a bérlő egészén), és támogatja a Windows AutoPilot (Kezdőélmény) programot. Az **Eszközkonfiguráció** azokat az eszközöket és felhasználókat célozza, amelyek a bejelentkezéskor alkalmazott szabályzatot használják.

Érintett kiadások:  
- Windows 10 és újabb
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>S mód szabályzása Windows 10 és újabb rendszerű eszközökön – nyilvános előzetes verzió <!-- 1958649 -->
Olyan eszközkonfigurációs profilt hozhat létre, amely a Windows 10 rendszerű eszközön kikapcsolja az S módot, vagy megakadályozza, hogy a felhasználók kikapcsolják az S módot. Ez a funkció a következő helyen található meg: Intune > **Eszközkonfiguráció** > **Profilok** >  **Windows 10 és újabb** > **Kiadásfrissítés és módkapcsoló**.
Az S módról az [S módú Windows 10 bemutatása](https://www.microsoft.com/windows/s-mode) című részben talál több információt.
Érintett kiadások: Windows 10 és újabb (1809 és újabb)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Modern VPN-támogatási frissítések iOS-hez <!-- 2459928, 1819876, and 2650856 -->
Egy későbbi frissítés támogatni fogja a következő iOS VPN-ügyfeleket: 
- F5 Access (3.0.1 és újabb verziók)
- Citrix SSO
- Palo Alto Networks GlobalProtect (5.0 és újabb verziók) Egy későbbi frissítésben szintén:
- A meglévő **F5 Access** kapcsolattípusok új neve **F5 Access Legacy** lesz (az egyes F5 védjegyezési frissítéseken belül).
- A meglévő **Palo Alto Networks GlobalProtect** kapcsolattípusok új neve **Legacy Palo Alto Networks GlobalProtect** lesz (az egyes Palo Alto védjegyezési frissítéseken belül). 

Az ilyen kapcsolatok meglévő profiljai tovább működnek az örökölt VPN-ügyféllel. Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN, vagy Legacy Palo Alto Networks GlobalProtect iOS-es használata esetén át kell térnie az új alkalmazásokra. Tegye meg ezt minél előbb annak érdekében, hogy a VPN hozzáférhető legyen az iOS-eszközökön, amikor iOS 12-re frissülnek.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>A Céges portál zárolása egyalkalmazásos módban a felhasználó bejelentkezéséig <!--1067692 --> 
A Céges portált egyalkalmazásos módban is futtathatja, ha a DEP-regisztráció során a felhasználót a beállítási asszisztens helyett a Céges portálon keresztül hitelesíti. Ez a beállítás a beállítási asszisztens futtatása után azonnal zárolja az eszközt, így a felhasználónak a hozzáféréshez be kell jelentkeznie. A folyamat biztosítja, hogy az eszköz az előkészítés teljes folyamatán végigmenjen, és ne maradjon hozzárendelt felhasználó nélkül.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Hatókörcímkék a szabályzatokhoz <!--1081974 eeready-->

Hatókörcímkék létrehozásával korlátozhatja a hozzáférést az Intune erőforrásaihoz. Adjon hozzá hatókörcímkét egy szerepkör-hozzárendeléshez, majd adja hozzá a hatókörcímkét egy konfigurációs profilhoz. A szerepkör csak a megfelelő hatókörcímkével rendelkező (vagy hatókörcímke nélküli) erőforrásokhoz férhet hozzá.
Hatókörcímke hozzáadásához válassza az **Intune-szerepkörök** > **Hatókör (Címkék)** > **Létrehozás** lehetőséget.
Hatókörcímke szerepkör-hozzárendeléshez való hozzáadásához válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** > **Hatókör (Címkék)** lehetőséget.
Hatókörcímke konfigurációs profilhoz való hozzáadásához válassza az **Eszközkonfiguráció** > **Profilok** > válasszon egy profilt > **Tulajdonságok** > **Hatókör (Címkék)** lehetőséget.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Felhasználóbarát rövid név hozzáadása Autopilot-eszközökhöz <!--1346521 -->
Egy jövőbeli nyilvános előzetes verzió lehetővé teszi a rendszergazdáknak, hogy felhasználót rendeljenek hozzá egyetlen AutoPilot-eszközhöz.  A rendszergazdák rövid nevet is létrehozhatnak a felhasználó üdvözléséhez az eszköz AutoPilottal történő beállításakor.

A következőkre vonatkozik: Windows Insider 1809 vagy újabb build (előzetes verzió használata során).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Csomagalagút-kezelés támogatása az iOS-es alkalmazásonkénti VPN-profilok egyedi és Pulse Secure kapcsolattípusaihoz <!-- 1520957 -->
Az iOS-es alkalmazásonkénti VPN-profilok használatakor egyaránt lehetősége lesz az alkalmazásiréteg-beli (alkalmazásproxy) és csomagszintű (csomagalagút) alagútkezelésre. Ezek a beállítások a következő kapcsolattípusokkal lesznek elérhetők:
- Egyéni VPN
- Pulse Secure Ha nem biztos a megfelelő értékben, tekintse meg a VPN-szolgáltató dokumentációját.
A következőre vonatkozik: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Elérhető Zscaler-kapcsolat az iOS-es VPN-profilok számára <!-- 1769858 eeready -->
Az iOS-es VPN-eszközregisztrációs profil létrehozásakor (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **iOS** platform > **VPN** profiltípus), több kapcsolattípus áll rendelkezésre, többek között a Cisco és a Citrix. Egy jövőbeli frissítés a Zscalert is hozzáadja a kapcsolattípusokhoz. 
[Az iOS rendszerű eszközökre vonatkozó VPN-beállítások](vpn-settings-ios.md) című cikk felsorolja az elérhető kapcsolattípusokat.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows személyes eszközregisztráció letiltása <!-- 1849498 -->
Letilthatja a Windows rendszerű személyes eszközök regisztrációját az Intune [mobileszköz-kezelésében](windows-enroll.md). Ez a funkció nem alkalmas az [Intune PC-ügynök](manage-windows-pcs-with-microsoft-intune.md) használatával regisztrált eszközök letiltásához.
A funkció megtekintéséhez kattintson az **Eszközregisztráció** > **Eszközkorlátozások** elemre.
A korlátozás bekapcsolása nincs hatással a már regisztrált eszközökre.
A korlátozás bekapcsolását követően az Intune minden új Windows-regisztrációs kérelem esetében ellenőrzi, hogy céges regisztrációként engedélyezték-e. Céges regisztrációnak minősülnek az alábbi módszerek:
- A felhasználó [készülékregisztráció-kezelői fiókot]( device-enrollment-manager-enroll.md) használ a regisztráláshoz.
- Az eszközregisztráció a [Windows Autopilot](enrollment-autopilot.md) használatával történik.
- Az eszköz IMEI-száma szerepel az **Eszközregisztráció** > **[Céges eszközazonosítók]( corporate-identifiers-add.md)** listán.
- Az eszközregisztráció [tömeges kiépítési csomagban](windows-bulk-enroll.md) történik.
- Az eszközregisztráció az [SCMM megosztott kezeléshez való automatikus regisztrációja](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management) révén történik.

A jogosulatlan regisztrációk le lesznek tiltva. Az alábbi regisztrációkat cégesként jelzi az Intune, de le lesznek tiltva, mert nem kínálják fel az Intune-rendszergazdának az eszközönkénti szabályozást:
- [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [Azure Active Directory-kapcsolat a Windows beállítása során](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [Azure Active Directory-kapcsolat a Windows beállításból](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).

Az alábbi személyes regisztrációs módszerek is le lesznek tiltva:
- [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [Munkahelyi fiók hozzáadása a Windows-beállításokból](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).
- [Csak MDM-regisztráció]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) lehetősége a Windows-beállításokból.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Gépnév-minták megadása egy Autopilot-profilban <!--1849855-->
Gépnév-sablont adhat meg a [gép nevének](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) Autopilot-regisztráció során történő létrehozásához és beállításához. Ezt az Autopilot profilban kell megadnia a következő helyen: **Eszközregisztráció** > **Windows-regisztráció** > **Windows Autopilot Deployment-szolgáltatás** > **Profilok**. Csak alfanumerikus karakterek és kötőjel használható.
A következőkre vonatkozik: Windows Insider 1809 vagy újabb build (előzetes verzió használata során).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS-es verziószám és buildszám megjelenítése <!-- 1892471 -->
Az iOS operációs rendszer verziószáma az **Eszközmegfelelőség** > **Eszközmegfelelőség** területen látható. Egy jövőbeli frissítéssel a buildszám is megjelenik.
A biztonsági frissítések megjelenésekor az Apple általában megtartja a verziószámot, de a buildszám változik. A megjelenített buildszám segítségével könnyen ellenőrizheti, hogy telepítve van-e a biztonsági frissítés.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>A Windows Autopilot-profiloknál a céges bejelentkezési oldalon és a tartományi hibalapon elrejthető lesz a fiókváltoztatás lehetősége <!--1901669 -->
Egy nyilvános előzetes verzió új profilbeállításokat tartalmaz majd a Windows Autopilot profil rendszergazdái részére, amellyel elrejthetik a fiókváltoztatás lehetőségét a céges bejelentkezési oldalon és a tartományi hibalapon. A beállítás elrejtése akkor lehetséges, ha az Azure Active Directoryban konfigurálva van a Vállalati védjegyezés. A következőkre vonatkozik: Windows Insider 1809 vagy újabb build (előzetes verzió használata során).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>iOS-es szoftverfrissítések megjelenítésének késleltetése az eszközön <!-- 1949583 -->
Az Intune > **Szoftverfrissítések** > **iOS-es szabályzatok frissítése** területen konfigurálhatja, hogy mely napon, mely időpontban ne telepítsenek frissítéseket az eszközök. Egy jövőbeli frissítéssel 1-90 napig késleltetheti a szoftverfrissítések láthatóvá válását az eszközön. 
A [Microsoft Intune iOS frissítési szabályzatok konfigurálása](software-updates-ios.md) területen látható a jelenlegi beállítások listája.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Elavult eszközök az eszközmegfelelőségi irányítópulton <!-- 1981119 -->
Egy jövőbeli frissítés eltávolítja az elavult eszközöket az eszközmegfelelőségi irányítópultról. Ez módosítani fogja a megfelelőségi számokat.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Új frissítés a felhasználói felülethez a Céges portál webhelyen <!--2000968 -->
A Céges portál webhelyen új funkciók jelennek meg a felhasználók visszajelzései alapján. Jelentős javulást fog tapasztalni az Android, az iOS, és a Windows rendszerű eszközök már meglévő funkciói és használhatósága terén. Új, modern és rugalmas külsőt kapnak a webhely különböző területei, köztük az eszközadatok, a visszajelzés, a támogatás és az eszközök áttekintése. Amit még tapasztalni fog:
- Zökkenőmentes munkafolyamatok minden eszközplatformon
- Hatékonyabb eszközazonosítási és beléptetési folyamatok
- Praktikusabb hibaüzenetek
- Barátságosabb nyelvezet, kevesebb műszaki zsargon
- Alkalmazások közvetlen hivatkozásainak megoszthatósága
- Nagy méretű alkalmazáskatalógusok javított teljesítménye
- Nagyobb hozzáférhetőség minden felhasználó számára

### <a name="office-365-proplus-version----2213968-eeready---"></a>Office 365 ProPlus verzió <!-- 2213968 eeready -->
Amikor Intune-t használó Windows 10 rendszerű eszközökhöz rendeli hozzá az Office 365 ProPlus-alkalmazásokat, kiválaszthatja az Office-verziót. Az Azure Portalon válassza a **Microsoft Intune** > **Alkalmazások** > **Alkalmazás hozzáadása** lehetőséget. Ezután válassza az **Office 365 ProPlus csomag (Windows 10)** lehetőséget a **Típus** legördülő menüből. Kattintson az **Alkalmazáscsomag beállításai** elemre a kapcsolódó panel megjelenítéséhez. Állítsa be a **Frissítési csatornát** például a **Havonta** értékre. Azt is megteheti, hogy az **Igen** elemre kattintva törli az Office (msi) másik verzióját a végfelhasználói eszközökről. Kattintson az **Adott** elemre az Office adott verziójának telepítéséhez a végfelhasználói eszközök kiválasztott csatornáján. Ekkor kiválaszthatja az Office **adott verzióját** a használathoz. Az elérhető verziók idővel változni fognak. Ezért egy új központi telepítés létrehozásakor újabb verziók válhatnak elérhetővé, és előfordulhat, hogy egyes régebbi verziók már nem érhetők el. A jelenleg üzemelő példányok továbbra is a régebbi verziót telepítik, de a verziólista csatornánként folyamatosan frissül. További információkért lásd: [Az Office 365 ProPlus frissítési csatornáinak áttekintése](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profil konfigurálása egyes képernyők kihagyásához a beállítási asszisztens működése során <!-- 2276470 -->
macOS-es regisztrációs profil létrehozásakor konfigurálhatja a profilt a következő képernyők bármelyikének kihagyására, amikor egy felhasználó a beállítási asszisztenst használja:
- Android-áttelepítés
- Hang megjelenítése
- Személyes adatok védelme
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Változás a helyszíni összekötők frissítési folyamatában <!-- 2277554 -->
Felhasználói visszajelzések alapján megváltozik a helyszíni összekötők frissítésének folyamata. Miután elvégezte a helyszíni összekötő kezdeti telepítését, a frissítések automatikusan lezajlanak. Ez a változás először a Microsoft Intune-hoz készült új PFX-tanúsítvány-összekötőnél jelenik meg, majd a soron következő további helyszíni összekötőknél is. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Támogatás a Windows 10 VPN DNS-beállításának regisztrálásához <!-- 2282852 -->
A Windows 10 VPN-profilokat a jövőben úgy is konfigurálhatja, hogy egyéni profilok használata nélkül is dinamikusan regisztrálják a belső DNS-ben a VPN-interfészhez rendelt IP-címeket.
A [Windows 10 VPN-beállítások](vpn-settings-windows-10.md) listája felsorolja a jelenleg elérhető VPN-profilbeállításokat. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Alkalmazások korlátozása és a céges erőforrásokhoz való hozzáférés letiltása iOS és Android for Work rendszerű eszközökön <!-- 2451462 -->
Az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Android for Work** > **Rendszerbiztonság** területen, új, **Korlátozott alkalmazások** beállítás jelenik meg. Az új beállítás egy megfelelőségi szabályzattal tiltja le a céges erőforrásokhoz való hozzáférést, ha bizonyos alkalmazások telepítve vannak az eszközön. Az eszköz addig nem megfelelőnek minősül, amíg a korlátozott alkalmazásokat el nem távolítják róla.
Érintett kiadások: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>A klasszikus Azure-portál megfelelőségi szabályzatainak exportálása .csv-fájlba <!-- 2469637 -->
A klasszikus Azure-portálon létrehozott megfelelőségi szabályzatok hamarosan elavulnak.  Amikor ez bekövetkezik, áttekintheti és törölheti a meglévő szabályzatokat, de már nem frissítheti őket. A szabályzatokat vesszővel tagolt (.csv-) fájlként exportálhatja. Ezt követően a fájlban lévő adatok felhasználásával újra létrehozhatja a szabályzatokat az Intune Azure Portalon.
> [!IMPORTANT]
> Miután a klasszikus Azure-portál elavult, már nem férhet hozzá a szabályzatokhoz, és nem is tekintheti meg azokat. Ezért ne feledje exportálni és újra létrehozni őket a klasszikus Azure-portálon még a klasszikus Azure-portál elavulása előtt.

### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>A terminológia módosítása „kivonás” és „törlés” kifejezésekre <!-- 2175759 -->
A Graph API-val való konzisztencia érdekében az Intune felhasználói felületén és a dokumentációban az alábbi terminológiai változásokat vezetjük be:
- A **Céges adatok eltávolítása** kifejezést a **Kivonás** kifejezés váltja fel
- A **Gyári beállítások visszaállítása** kifejezést a **törlés** váltja fel



<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>További szinkronizálási lehetőségek a windowsos céges portál alkalmazásban <!-- 2683177 -->
A windowsos Céges portál alkalmazás hozzáad egy eszközszinkronizálási műveletet a Windows tálcájához és a Start menü gyorslistáihoz. Az eszközök gyors szinkronizáláshoz és a vállalati erőforrások eléréséhez kattintson ezek közöl valamelyik helyre.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Eszközök PIN-kódjának alaphelyzetbe állítása a Windows 10-es Céges portál alkalmazásból <!-- 2101282 --> 
Alkalmazottaik rövidesen közvetlenül a Windows 10-es Céges portál alkalmazásból tudják alaphelyzetbe állítani eszközeik PIN-kódját vagy jelszavát. Ez a funkció a PIN-kód alaphelyzetbe állítását támogató, Intune által felügyelt távoli és helyszíni eszközökön is elérhető lesz. A távoli eszközre vonatkozó kérelmek az eszköz típusától függően vagy eltávolítják az eszköz PIN-kódját, vagy létrehoznak egy ideiglenes PIN-kódot. A helyszíni eszközre alaphelyzetbe állítást kérő felhasználók az eszköz Beállítások alkalmazásához lesznek irányítva.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Új böngészési élmény a windowsos céges portál alkalmazásban <!-- 2317227 -->  
Ha a windowsos céges portál alkalmazásban alkalmazásokat böngész vagy keres, lehetőség lesz váltani a meglévő **Csempék** nézet és az újonnan hozzáadott **Részletek** nézet között. Az új nézet megjeleníti az alkalmazások adatait, például a nevet, a kiadót, a kiadás dátumát és a telepítés állapotát.  

Az **Alkalmazások** lapon használható lesz egy **Telepítve** nézet is, amely a befejezett és a folyamatban lévő telepítések adatait jeleníti meg. Visszajelzést vagy javaslatot szeretne küldeni a változásokkal kapcsolatban? Küldje el visszajelzését a céges portál alkalmazásban.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>A céges portál alkalmazás javított használati élménye az eszközregisztráció-kezelők számára <!-- 675800 -->
Ha egy eszközregisztráció-kezelő (DEM) bejelentkezik a windowsos céges portál alkalmazásba, az alkalmazás csak az eszközregisztráció-kezelő jelenlegi, futó eszközét jeleníti meg. Ennek a fejlesztésnek köszönhetően kevesebb olyan időtúllépés fog történni, amely korábban akkor jelentkezett, ha az alkalmazás megpróbálta betölteni a kezelő által regisztrált összes eszközt.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP eszközlicencek használata a Céges portál előzetes kiépítésére a DEP-regisztráció során <!-- 1608345 -->
Volume Purchase Program (VPP) eszközlicencekkel előre kiépítheti a Céges portált az Készülékregisztrációs program (DEP) keretében végzett regisztrációk során. Ehhez a regisztrációs profil létrehozása vagy szerkesztése során kell megadni a Céges portál telepítéséhez használni kívánt VPP-jogkivonatot. Fontos, hogy a jogkivonat ne járjon le, és hogy elég licenccel rendelkezzen a Céges portál alkalmazáshoz. Amennyiben a jogkivonat lejár vagy a licencei elfogynak, az Intune az App Store-beli Céges portált fogja leküldeni (ilyenkor a rendszer kéri az Apple-azonosítót).

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows rendszerű üzletági (LOB) alkalmazások fájlnévkiterjesztései <!-- 1884873 -->
A Windowsos üzletági alkalmazások fájlnévkiterjesztései közé tartozik már az *.msi*, *.appx*, *.appxbundle*, *.msix* és *.msixbundle* is. A **Mobilalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséggel hozzáadhat egy alkalmazást a Microsoft Intune-hoz. Megjelenik az **Alkalmazás hozzáadása** panel, ahol kiválaszthatja az **Alkalmazás típusát**. Windowsos üzletági alkalmazásokhoz válassza az **Üzletági alkalmazás** lehetőséget az alkalmazás típusa területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy megfelelő kiterjesztésű telepítőfájlt.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP konfigurációs csomag automatikus hozzáadása a konfigurációs profilhoz <!-- 2144658 -->
Ha a [Komplex veszélyforrások elleni védelem használata mellett készít elő](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) eszközöket az Intune-ban, ehhez jelenleg le kell töltenie egy konfigurációs csomagot, melyet aztán hozzáad a konfigurációs profilhoz. Egy későbbi frissítéstől kezdve az Intune automatikusan megkapja a csomagot a Windows Defender biztonsági központtól, és hozzáadja azt az Ön profiljához.

A Windows 10 és újabb verziókra vonatkozik.

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM-megfelelőség ellenőrzése <!-- 2192052 -->
Egy későbbi frissítésnek része lesz a System Center Configuration Manager (SCCM) egy új megfelelőségi beállítása (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Windows 10**). Az SCCM az Intune-nak küld megfelelőségi jeleket. Az Intune beállításával megkövetelhető, hogy minden SCCM-jelre „megfelelő” legyen a válasz.

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. Az SCCM-ben ehhez a követelményhez a „Telepítve” állapot tartozik. Ha az eszközön bármelyik program ismeretlen állapotban van, akkor az eszköz nem megfelelőnek fog minősülni az Intune-ban.

A Windows 10 és újabb verziókra vonatkozik

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>VPP-jogkivonatok lejáratára vagy a Céges portál licenceinek alacsony számára vonatkozó riasztások <!-- 2237572 -->
Ha a Volume Purchase Program (VPP) igénybe vételével építi ki a Céges portált a DEP-regisztráció során, az Intune riasztást fog küldeni a VPP-jogkivonat közeli lejáratáról, és ha a Céges portál licencei hamarosan elfogynak.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Megerősítés szükséges a Céges portál kiépítéséhez éppen használt VPP-jogkivonat törléséhez <!-- 2237634 -->
A jövőben meg kell erősíteni az olyan Volume Purchase Program (VPP) jogkivonat törlését, amelyet éppen a Céges portál kiépítéséhez használnak a DEP-regisztráció során.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>A Windows Installer további biztonsági beállításai <!-- 2282430 -->
Engedélyezheti a felhasználóknak az alkalmazástelepítések szabályozását. Ha engedélyezve van, azok a telepítések, amelyek a biztonság megsértése miatt le lettek volna állítva engedélyt kapnak a folytatásra. Megadhatja, hogy a Windows Installer emelt szintű engedélyeket használjon, amikor programokat telepít a rendszerben. Emellett engedélyezheti a Windows Information Protection (WIP) elemeinek indexelését és az ezekre vonatkozó metaadatok titkosítatlan helyen való tárolását. A szabályzat tiltásakor a WIP által védett elemek nem lesznek indexelve, és nem jelennek meg a Cortana vagy a fájlkezelő eredményei között. Ezeknek a beállításoknak a funkciói alapértelmezés szerint le lesznek tiltva. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Az iOS-es eszközökön az alkalmazásvédelmi beállítások használatával letilthatja a harmadik féltől származó billentyűzeteket <!-- 1248481 -->
Az Intune-rendszergazdák az iOS-es eszközökön letilthatják a harmadik féltől származó billentyűzeteket, ha azok a szabályzat által védett alkalmazásokon hozzáférnek a céges adatokhoz. Ha az alkalmazásvédelmi szabályzat (APP) a harmadik félhez tartozó billentyűzetek letiltására van beállítva, az eszköz használója üzenetet kap, amikor először fér hozzá ilyen billentyűzettel a céges adatokhoz. A natív billentyűzeten kívül minden más lehetőség le lesz tiltva, és a felhasználók nem láthatják ezeket. A felhasználók csak egyszer látják az üzenetet. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Nem-biometrikus PIN-kód kérése alkalmazások indítása vagy időtúllépés esetén <!-- 1506985 -->

Amikor az alkalmazások indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Az Office 365 Pro Plus nyelvi csomagjai <!-- 1833450 -->
Az Intune rendszergazdájaként további nyelveket helyezhet üzembe az Intune által felügyelt Office 365 Pro Plus alkalmazások számára. Az elérhető nyelvek listája tartalmazza a nyelvi csomag **Típusát** (alap, részleges vagy nyelvi ellenőrzési) is. Az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen, az **Alkalmazástípusok** listáján, válassza az **Office 365 csomag** alatti **Windows 10** lehetőséget. Az **Alkalmazáscsomag beállításai** panelen válassza a **Nyelvek** lehetőséget.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>A Céges portál webhely felhasználói felületéhez kiadott új frissítés előnézete <!--2000968 -->
A felhasználók visszajelzései alapján új funkciókkal egészül ki a Céges portál webhely/iOS alkalmazáskatalógus. Jelentős javulást fog tapasztalni az Android, az iOS, és a Windows rendszerű eszközök már meglévő funkciói és használhatósága terén. Új, modern és rugalmas külsőt kapnak a webhely különböző területei, köztük az eszközadatok, a visszajelzés, a támogatás és az eszközök áttekintése. Amit még tapasztalni fog:

- Zökkenőmentes munkafolyamatok minden eszközplatformon
- Hatékonyabb eszközazonosítási és beléptetési folyamatok
- Praktikusabb hibaüzenetek
- Barátságosabb nyelvezet, kevesebb műszaki zsargon
- Alkalmazások közvetlen hivatkozásainak megoszthatósága
- Nagy méretű alkalmazáskatalógusok javított teljesítménye
- Nagyobb hozzáférhetőség minden felhasználó számára

A frissítés jelenleg előzetes verzióban érhető el. Az előzetes verzió kipróbálásához regisztráljon a következő címen: http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Nem-biometrikus PIN-kód kérése alkalmazások első indítása vagy időtúllépés esetén <!-- 1506985 --> 

Amikor az alkalmazások első indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Kötelező üzletági (LOB) alkalmazások üzembe helyezésének lehetősége az összes felhasználó számára Windows 10 rendszerű asztali eszközökön <!-- 1627835 RS4 -->
Az ügyfelek eszközkörnyezetben helyezhetik üzembe a kötelező üzletági Windows 10 rendszerű alkalmazásokat. Így az alkalmazások az eszköz összes felhasználója számára elérhetővé válnak. Ez csak Windows 10 rendszerű asztali eszközökre vonatkozik.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciójának frissítése <!--1631531 -->

Az androidos alkalmazások ajánlott eljárásaihoz igazodva hamarosan frissülni fog az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciója. Az elkövetkező néhány hónapban az Androidhoz készült Céges portál alkalmazás frissülni fog a **Súgó és visszajelzés** menüpont két különálló, **Súgó** és **Visszajelzés küldése** menüpontra osztásával. A **Súgó** oldalon egy **Gyakran ismételt kérdések** szakasz és egy **E-mail küldése az ügyfélszolgálatnak** gomb jelenik meg, amellyel a végfelhasználó naplókat tölthet fel a Microsoft részére, és e-mailben írhatja meg a problémát az ügyfélszolgálatnak. A **Visszajelzés küldése** oldal a Microsoft szabványos visszajelzési folyamatán vezeti végig a felhasználót, melynek során a rendszer a „Tetszik”, a „Nem tetszik”, és a „Javaslatom van” választ kínálja fel.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Alkalmazásvédelmi szabályzatok  <!-- 679615 -->
Az Intune alkalmazásvédelmi szabályzatai lehetőséget nyújtanak globális szintű alapértelmezett szabályzatok létrehozására, amelyekkel gyorsan beállítható a megfelelő védelem a teljes bérlő összes felhasználója számára.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).




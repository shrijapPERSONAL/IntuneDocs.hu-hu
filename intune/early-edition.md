---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b003fde011fd3a727c7c7a163fedb1dae6779425
ms.sourcegitcommit: 407191a92ef356a3d196b6f9959b9b033190ca2c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>A Microsoft Intune előzetes kiadása – 2018. április

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Ne ossza meg ezeket az információkat cégen kívüli személyekkel. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
>A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) oldalát.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1804 start -->

### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Hívóazonosító megjelenítése a személyes profilban – Android for Work <!--1098984 -->
Előfordulhat, hogy az eszközön személyes profilt használó végfelhasználók nem látják egy munkahelyi kapcsolat hívásazonosítójának részleteit. 

Ez a frissítés egy új beállítást jelenít meg az **Android for Work** > **Eszközkorlátozások** > **Munkahelyi profil beállításai** területen:
- Munkahelyi kapcsolat hívásazonosítójának megjelenítése a személyes profilban

Engedélyezése (konfigurálás nélkül) esetén a munkahelyi hívó részletei megjelennek a személyes profilban. Tiltása esetén a munkahelyi hívó részletei nem jelennek meg a személyes profilban. 

A következőkre vonatkozik: Android munkahelyi profilos eszközök Android v6.0 és újabb operációs rendszerekkel

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Új Windows Defender Credential Guard-beállítások az Endpoint Protection-beállításokban <!--1102252 --><!--from 1802-->

Új [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard)-beállításokkal bővült az **Eszközkonfiguráció** > **Profilok** > **Endpoint protection** terület. A következő beállítások lesznek hozzáadva:

- Platformbiztonsági szint: megadhatja, hogy engedélyezve legyen-e a platformbiztonsági szint a következő újraindításkor. A virtualizálás-alapú biztonsághoz biztonságos rendszerindítás szükséges. A virtualizálás-alapú biztonságot igény szerint a közvetlen memória-hozzáférés (DMA) védelmi funkcióinak használatakor is engedélyezheti. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.
- Virtualizálás-alapú biztonság: megadhatja, hogy engedélyezve legyen-e a virtualizálás-alapú biztonság a következő újraindításkor.
- Windows Defender Credential Guard: a Credential Guard a virtualizálás-alapú biztonsággal történő együttes bekapcsolásával megvédheti a hitelesítő adatokat a következő újraindításnál, ha a platformszintű biztonság engedélyezve van a biztonságos újraindítás és a virtualizálás-alapú biztonság funkciókkal. Elérhető beállítások: **Letiltva**, **Engedélyezve UEFI-zárolással**, **Engedélyezve zárolás nélkül**, és **Nincs konfigurálva**.
  - A „Letiltva” beállítás távolról kikapcsolja a Credential Guardot, ha azt korábban bekapcsolta az „Engedélyezve zárolás nélkül” funkcióval.

  - Az „Engedélyezve UEFI-zárolással” beállítással biztosíthatja, hogy a Credential Guard ne legyen letiltható egy beállításkulccsal vagy egy csoportházirenddel. A beállítás használata után a Credential Guard letiltásához a csoportházirendet „Letiltva” állapotra kell állítania, és el kell távolítania a biztonsági funkciókat a jelen lévő felhasználókkal rendelkező számítógépekről a UEFI-ben megőrzött konfigurációk törléséhez. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

  - Az „Engedélyezve zárolás nélkül” beállítással távolról letilthatja a Credential Guardot egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, legalább a Windows 10 1511-es verziójának kell futnia.

  - A „Nincs konfigurálva” beállítás nem definiálja a szabályzatbeállítást. A csoportházirend nem írja a szabályzatbeállítást a beállításjegyzékbe, így ez nincs hatással a számítógépekre vagy a felhasználókra. Ha már meg van adva egy beállítás a beállításjegyzékben, az nem módosul.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>PIN-jelszó támogatása MAM PIN-ként Androidon<!-- 1438086 -->

Az Intune-rendszergazdák alkalmazásindítási követelményként állíthatnak be PIN-jelszót a numerikus MAM PIN-kód helyett. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune a PIN-jelszót a hagyományos, numerikus PIN-kódhoz hasonlóan támogatja: állíthat be minimális jelszóhosszt, és engedélyezheti a karakterek és sorozatok ismétlődését a felügyeleti konzolon. Ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség Android rendszerben. Ez a funkció már elérhető az iOS rendszerben.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Kamera és képernyőkép rögzítésének blokkolása Android for Work rendszerben <!-- 1098977 eeready-->
Két új tulajdonság lesz elérhető letiltásra, amikor az Android-eszközökhöz eszközkorlátozásokat állít be: 
- Kamera: Letiltja a hozzáférést az eszközön lévő összes kamerához
- Képernyőfelvétel: Letiltja a képernyőfelvételt, és megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön

Android for Work rendszerre érvényes.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1473977 -->
A Microsoft Intune támogatni fogja a macOS-hoz készült LOB-alkalmazások telepítését az Azure Portalról. Ezzel a funkcióval hozzáadhat egy macOS-hoz készült LOB-alkalmazást az Intune-hoz, miután azt előkészítette egy, a GitHubon elérhető eszközzel. Válassza az Azure Portalon az **Intune** panel **Mobilalkalmazások** elemét. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** > **Hozzáadás** elemet. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget. 

### <a name="support-for-user-less-devices----1637553---"></a>Felhasználó nélküli eszközök támogatása <!-- 1637553 -->
Az Intune támogatni fogja a megfelelőség kiértékelését a felhasználó nélküli eszközökön is, ideértve például a Microsoft Surface Hub eszközt. A megfelelőségi szabályzat alkalmazható közvetlenül eszközökre. Ezért a megfelelőség (vagy meg nem felelőség) megállapítható a társított felhasználó nélküli eszközök esetében is.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>További helyi eszközbiztonsági beállítások <!-- 1403702 -->
További helyi eszközbiztonsági beállításokat adhat meg a Windows 10 rendszerű eszközökhöz. Ezek a további beállítások a következő területeken lesznek elérhetők: Microsoft hálózati ügyfél, Microsoft hálózati kiszolgáló, hálózati hozzáférés és biztonság, valamint interaktív bejelentkezés. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítésének megkövetelése <!-- 1553555 -->
A rendszergazdák blokkolhatják a végfelhasználók számára a Windows 10 RS4 rendszer asztalának elérését, amíg az Intune el nem végzi a szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítését az AutoPilot-eszközök beállításakor.

### <a name="rules-for-removing-devices----1609459---"></a>Szabályok eszközeltávolításhoz <!-- 1609459 -->
Új szabályok lesznek elérhetők, melyekkel automatikusan eltávolíthatja azokat az eszközöket, amelyek nem jelentkeztek be az Ön által megadott számú napon keresztül. Az új szabály megtekintéséhez nyissa meg az **Intune** panelt, és válassza az **Eszközök**, majd az **Eszközeltávolítási szabályok** lehetőséget.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Fogyasztói alkalmazások és funkciók használatának meggátolása a Windows 10 Enterprise RS4 rendszerű Autopilot-eszközökön<!-- 1621980 -->
Le fogja tudni tiltani a fogyasztói alkalmazások és funkciók telepítését a Windows 10 Enterprise RS4 rendszerű AutoPilot-eszközökön. Ennek a funkciónak a megtekintéséhez válassza az **Intune** > **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Windows AutoPilot-profilok** > **Új létrehozása** > **Beléptetési beállítások** lehetőséget. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>A Komplex veszélyforrások elleni védelem integrálása az Intune-ban <!-- 1629303 -->
A [Komplex veszélyforrások elleni védelem](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) megállapítja a Windows 10 rendszerű eszközök kockázati szintjét. Amikor az Intune kiértékeli a Windows 10-eszközök megfelelőségét, ez a kiértékelés a Komplex veszélyforrások elleni védelem kockázati pontszámát is tartalmazza. A Komplex veszélyforrások elleni védelem szolgáltatást használhatja feltételes hozzáféréssel kombinálva a hálózata még hatékonyabb védelme érdekében.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Új regisztrációs lépések a macOS High Sierra 10.13.2 és újabb rendszert futtató eszközök felhasználóinak <!--1734567 -->
A macOS High Sierra 10.13.2 rendszer bevezette a „felhasználó által jóváhagyott” mobileszköz-kezelési regisztrációt. A jövőben a jóváhagyott regisztrációk lehetővé fogják tenni az Intune-nak bizonyos biztonsági szempontból kényes beállítások kezelését. További információt az Apple támogatási dokumentumában találhat itt: https://support.apple.com/HT208019.

A macOS rendszerhez készült Céges portál alkalmazással regisztrált eszközök „felhasználó által nem jóváhagyott” állapotúként lesznek minősítve, hacsak a felhasználó manuálisan jóváhagyást nem ad a Rendszerbeállítások menü megnyitásával. Emiatt a macOS rendszerhez készült Céges portál alkalmazás mostantól a regisztrációs folyamat végén átirányítja a macOS 10.13.2 és újabb rendszerek felhasználóit a regisztrációjuk manuális jóváhagyásához. Az Intune felügyeleti konzolja jelenti, ha egy regisztrált eszközt jóváhagyott a felhasználó.

### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-eszközök törlése <!-- 1713650 -->
Az Intune-rendszergazdák képesek lesznek törölni az Autopilot-eszközöket.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Beépített Minden felhasználó és Minden eszköz csoport Android for Work- (AFW) alkalmazástársításokhoz <!-- 1813073 -->
Kihasználhatja majd a beépített **Minden felhasználó** és **Minden eszköz** csoportot az AFW-alapú alkalmazástársításokhoz. További információért lásd: [Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Továbbfejlesztett eszköztörlési funkció <!--1832333 -->
Mostantól nem kell eltávolítania a céges adatokat vagy visszaállítania a gyári beállításokat, mielőtt törölhetne egy eszközt az Intune-ból.

Az új törlési funkció eléréséhez jelentkezzen be az Intune-ba, és válassza az **Eszközök** > **Minden eszköz** > eszköz neve > **Törlés** lehetőséget.

 Ha továbbra is szeretné alaphelyzetbe állítani vagy kivonni az eszközöket, használhatja a megszokott **Céges adatok eltávolítása** és **Gyári beállítások visszaállítása** lehetőséget, mielőtt a **Törlés** lehetőséget választaná. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Az Autopilot-profilok csoportokat fognak megcélozni <!-- 1877935 -->
Az AutoPilot Deployment-profilok jelenleg egyes eszközökhöz rendelhetők hozzá. Április végétől a következőképpen fogja tudni hozzárendelni ezeket a profilokat:
- Hozzon létre egy Azure AD-csoportot, mely tartalmazza az AutoPilot-eszközöket.
- Rendelje hozzá a kívánt profilokat az Azure AD-csoporthoz. Az AutoPilot-profil ezután hozzá lesz rendelve az adott csoportban található AutoPilot-eszközökhöz.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Hang lejátszása iOS rendszeren Elveszett üzemmódban <!-- 1629303 -->
Amikor egy felügyelt iOS-eszköz a mobileszköz-kezelés (MDM) [Elveszett üzemmódjában](device-lost-mode.md) van, lejátszhat egy hangot (**Eszközök** > **Minden eszköz** > válasszon iOS-eszközt > **Áttekintés** > **Egyebek**). A hang lejátszása egészen addig folytatódik, amíg az eszköz ki nem lép az Elveszett üzemmódból, vagy a felhasználó le nem tiltja a hangot az eszközön. iOS 9.3-as és újabb rendszerű eszközökre érvényes.

### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Az Intune újratelepíti a felhasználók által eltávolított kötelező alkalmazásokat <!-- 1947010 -->
Ha egy végfelhasználó eltávolít egy kötelező alkalmazást, az Intune a 7 napos újraértékelési ciklus kivárása helyett 24 órán belül automatikusan újratelepíti az alkalmazást.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Egyéni tulajdonosnév használata SCEP-tanúsítványokban <!-- 2064190 -->
Használhatja az **OnPremisesSamAccountName** köznapi nevet egyéni tulajdonosként az SCEP-tanúsítványprofilokban. Így használhatja például a következőt: `CN={OnPremisesSamAccountName})`.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnosztikai jelentések küldése a macOS rendszerhez készült Céges portál alkalmazásban <!-- 2216677 -->
Frissülni fog a macOS-eszközökhöz készült Céges portál alkalmazás, hogy jobb lehetőségeket nyújtson a felhasználóknak az Intune-nal kapcsolatos hibák jelentésére. A dolgozói a Céges portál alkalmazásból a következőket tehetik majd meg:
- Diagnosztikai jelentések feltöltése közvetlenül a Microsoft fejlesztői csapatának.
- Incidensazonosító elküldése e-mailben a vállalata informatikai támogatási csoportjának.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>Mindig bekapcsolva VPN Windows 10-hez <!--1333666 -->

Jelenleg a [Minden bekapcsolva](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) trigger a Windows 10-eszközökön csak OMA-URI-val létrehozott egyéni VPN-profil segítségével használható.

A frissítés révén a rendszergazdák engedélyezhetik a Mindig bekapcsolva beállítást a Windows 10 VPN-profilokban közvetlenül az Azure Portalon elérhető Intune konzolról. A Mindig bekapcsolva beállítású VPN-profilok automatikusan csatlakoznak az alábbi esetekben:

- Felhasználói bejelentkezés az eszközre
- Hálózatváltozás az eszközön
- Az eszköz képernyője ismét bekapcsol, miután ki volt kapcsolva

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Javított hibaüzenet az Apple MDM Push-tanúsítvány feltöltési hibájához <!-- 2172331 -->

A hibaüzenet elmagyarázza, hogy ugyanazt az Apple ID-t kell használni egy meglévő MDM-tanúsítvány megújításakor.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Csoport minden eszközének megjelenítése az eszközprofil-diagramon és -állapotlistán <!-- 1449153 eeready -->
Eszközprofil konfigurálásakor (**Eszközök konfigurálása** > **Profilok**) kiválasztja az eszközprofilt, például iOS. Ezután hozzárendeli ezt a profilt egy csoporthoz, mely tartalmaz iOS- és nem iOS-eszközöket is. A grafikus diagramon lévő számlálón az látható, hogy a profil alkalmazva lett az iOS- *és* a nem iOS-eszközökre is (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**). Amikor a grafikus diagramot választva megjeleníti az **Áttekintés** lapot, az **Eszközállapot** terület felsorolja a csoport összes eszközét, nemcsak az iOS-eszközöket. 

A jelen frissítés megjelenése után a grafikus diagram (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**) csak az adott eszközprofil számlálóját fogja megjeleníteni. Ha például az eszközprofil iOS-eszközökre van alkalmazva, akkor a diagram csak az iOS-eszközök számát jeleníti meg. A grafikus diagram választása és az **Eszközállapot** lista megnyitása esetén is csak az iOS-eszközök lesznek felsorolva.

A jelen frissítés elkészültéig a grafikus felhasználói diagramot ideiglenesen eltávolítottuk. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Több Exchange Connector támogatása <!-- 2070451 -->

Mostantól nem csak egy Microsoft Intune Exchange Connectort használhat bérlőnként. Az Intune hamarosan több Exchange Connector használatát is támogatni fogja, hogy több helyszíni Exchange-szervezetnél állíthassa be az Intune feltételes hozzáférést.

A helyszíni Intune Exchange Connector segítségével annak alapján kezelheti az eszközök helyszíni Exchange-postafiókokhoz történő hozzáférését, hogy az adott eszköz regisztrálva van-e az Intune-ban, és megfelel-e az Intune eszközmegfelelőségi szabályzatainak. Az összekötő beállításához töltse le a helyszíni Intune Exchange Connectort az Azure Portalról, és telepítse egy Exchange-szervezeten belüli kiszolgálón. A Microsoft Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget, majd a **Telepítés** területen kattintson az **Exchange ActiveSync Connector** lehetőségre. Töltse le a helyszíni Exchange Connectort, és telepítse egy Exchange-szervezeten belüli kiszolgálón. Most, hogy már nem csupán egy Exchange Connectort használhat bérlőnként, ugyanezekkel a lépésekkel letöltheti és telepítheti az összekötőt minden további Exchange-szervezethez, ha vannak ilyenek.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Új támogatás az iOS-hez készült Cisco AnyConnect-ügyfélhez<!-- 1333708 -->

Az iOS-hez készült Cisco AnyConnect új VPN-profiljai a Cisco AnyConnect 4.0.7x vagy újabb verzióival működnek. A meglévő iOS Cisco AnyConnect VPN-profiljai a **Cisco Legacy AnyConnect** (Cisco örökölt AnyConnect) nevet kapják, és továbbra is úgy működnek a Cisco AnyConnect 4.0.5x verziójával, mint eddig.

> [!NOTE]
> Ez a változás csak az iOS rendszerre érvényes, az Android, az Android for Work és a macOS rendszerekhez továbbra is csak egy Cisco AnyConnect-lehetőség érhető el.

#### <a name="more-information"></a>További információ

Az új alkalmazás támogatásához új iOS Cisco AnyConnect VPN-profilt kell létrehoznia, mert az új Cisco AnyConnect és a Cisco Legacy AnyConnect két különböző alkalmazás. Ha saját környezetben kezeli az AnyConnect-ügyfelet, az új Cisco AnyConnect-alkalmazást is üzembe kell helyeznie. Frissítés végrehajtásához törölnie kell a Cisco Legacy AnyConnect VPN-profilt is, továbbá el kell távolítania a Cisco Legacy AnyConnect-alkalmazást.

A hálózati hozzáférés-vezérlő (NAC) integrációja az eredeti kiadásban nem működik az új AnyConnect-ügyféllel. Jelenleg is dolgozunk a Cisco közreműködésével a NAC-integráció elérhetővé tételén egy későbbi kiadásban.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Kötelező üzletági (LOB) alkalmazások üzembe helyezésének lehetősége az összes felhasználó számára Windows 10 rendszerű asztali eszközökön <!-- 1627835 RS4 -->
Az ügyfelek eszközkörnyezetben helyezhetik üzembe a kötelező üzletági Windows 10 rendszerű alkalmazásokat. Így az alkalmazások az eszköz összes felhasználója számára elérhetővé válnak. Ez csak Windows 10 rendszerű asztali eszközökre vonatkozik.

### <a name="company-portal-enrollment-improved----1874230--"></a>A Céges portálra történő regisztráció továbbfejlesztése <!-- 1874230-->
A Céges portálon az 1703-as vagy annál újabb verziójú Windows 10 rendszerrel eszközt regisztráló ügyfelek az alkalmazás elhagyása nélkül hajthatják végre a regisztráció első lépését.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciójának frissítése <!--1631531 -->

Az androidos alkalmazások ajánlott eljárásaihoz igazodva hamarosan frissülni fog az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciója. Az elkövetkező néhány hónapban az Androidhoz készült Céges portál alkalmazás frissülni fog a **Súgó és Visszajelzés** menüpont két különálló, **Súgó** és **Visszajelzés küldése** menüpontra osztásával. A **Súgó** oldalon egy **Gyakran ismételt kérdések** szakasz és egy **E-mail küldése az ügyfélszolgálatnak** gomb jelenik meg, amellyel a végfelhasználó naplókat tölthet fel a Microsoft részére, és e-mailben írhatja meg a problémát az ügyfélszolgálatnak. A **Visszajelzés küldése** oldal a Microsoft szabványos visszajelzési folyamatán vezeti végig a felhasználót, melynek során a rendszer a „Tetszik”, a „Nem tetszik”, és a „Javaslatom van” választ kínálja fel.

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Új nyomtatóbeállítások az oktatási profilokban <!-- 1308900 -->

Az oktatási profilok új beállításai a **Nyomtatók** kategória **Nyomtatók**, **Alapértelmezett nyomtató**, **Új nyomtatók hozzáadása** területén érhetők el.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Alkalmazásvédelmi szabályzatok  <!-- 679615 -->
Az Intune alkalmazásvédelmi szabályzatai lehetőséget nyújtanak globális szintű alapértelmezett szabályzatok létrehozására, amelyekkel gyorsan beállítható a megfelelő védelem a teljes bérlő összes felhasználója számára.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->   
Az Azure Active Directory (Azure AD) használatával korlátozhatja majd a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el.




## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.


### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



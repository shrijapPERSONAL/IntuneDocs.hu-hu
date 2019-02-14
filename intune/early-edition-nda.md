---
title: Előzetes kiadása – Microsoft Intune
titlesuffix: ''
description: A Microsoft Intune előzetes kiadása
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 605868af91e734a6bd1457a97e9089d69ba81718
ms.sourcegitcommit: bc863efcf760ba35421d8566581e8768056485f1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227896"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>Az előzetes kiadása, a Microsoft Intune – 2019. február

> [!Note]
> NDA-értesítés: A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az itt, nagyon szűk körben megosztott információkra titoktartási szerződés vonatkozik. Az információk egy részletét se tegye közzé közösségi médiában vagy nyilvános webhelyeken, például Twitteren, UserVoice-on, Redditen vagy hasonlón. 

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza, titoktartási szerződés hatálya alatt. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Az információkat ne tweetelje, ne tegye közzé a UserVoice-on, és más módon se ossza meg a vállalatán kívül. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>PowerShell-parancsprogramok a 64 bites gazdagépen 64 bites eszközökön futtathatja <!-- 1862675  -->
Eszközkonfigurációs profil hozzá egy PowerShell-parancsfájlt, ha a parancsfájl mindig futtatják a 32 bites, akár a 64 bites operációs rendszereken. Ezzel a frissítéssel a rendszergazda tudja futtatni a parancsprogramot a 64 bites PowerShell-gazdagépet a 64 bites eszközökön (**eszközkonfiguráció** > **PowerShell-parancsfájlok**  >   **Adjon hozzá** > **konfigurálása** > **64 bites PowerShell-gazdagépet a szkriptet futtathatja**).
A PowerShell használatával további részletekért lásd: [az Intune-ban a PowerShell-parancsfájlok](intune-management-extension.md).
A következőkre vonatkozik: Windows 10 és újabb

### <a name="rename-an-enrolled-windows-device----1911112----"></a>Egy regisztrált Windows-eszköz átnevezése <!-- 1911112  -->
Nevezze át a regisztrált Windows 10-es eszköz lesz (RS4 vagy újabb). Szeretné elvégezni, válassza ki a **Intune** > **eszközök** > **minden eszköz** > Válasszon egy eszközt > **átnevezése eszköz**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>SCEP-tanúsítványok felhasználó nélküli macOS-eszközök hozzárendelése    <!-- 2340521   -->
Láthatja, hogy egyszerű tanúsítványigénylési protokoll (SCEP) tanúsítványok hozzárendelése egy felhasználó nélküli macOS-eszközt, és rendelje hozzá a tanúsítvány Wi-Fi vagy VPN-profilok. Ez kibővíti a meglévő támogatást, már eleve [tanúsítványok hozzárendelése Windows, iOS és Android rendszerű, felhasználó nélküli eszközök](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="find-out-which-devices-support-esim----2432018---"></a>Ismerje meg, hogy mely eszközök támogatják az esim-kártya <!-- 2432018 -->
Lesz egy új **esim-kártya készlet** mezőt a hardver lap eszközökhöz. Az iktatott megtekintéséhez válassza ki **Intune** > **eszközök** > Válasszon egy eszközt > **hardver**.

### <a name="intune-conditional-access-ui-update------2432313----"></a>Az Intune feltételes hozzáférés felhasználói felület frissítése   <!-- 2432313  -->
Fejlesztéseket végzünk az Intune-konzolon a feltételes hozzáférés felhasználói felületén. Ezek a következők:
- Cserélje le az Intune *feltételes hozzáférési* panelről a panel az Azure Active Directoryból. Ez biztosítja a hozzáférést a beállítások és konfigurációk teljes körét a feltételes hozzáférés, amely egy Azure AD-technológia marad.
- Helyezze át a *Exchange szolgáltatási összekötője* jelenleg a telepítőt a *helyszíni hozzáférés* panelen. Azt is vannak átnevezés, az adott panelhez *Exchange-hozzáférés*. Ez a változás egyesíteni fogja, ahol konfigurálhatja és figyelheti az Exchange online és helyszíni kapcsolatos részleteket.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>Intune az Android-eszközökön a Google Play védelme API-kat használja <!-- 2577355  -->
Egyes rendszergazdáknak kihívással szembesülnek, a BYOD fekvő tájolás, a végfelhasználók előfordulhat, hogy végül a telepítés vagy jailbreaking a mobiltelefonon. Ez a viselkedés, amíg nem néha helytelenül – intentioned, annak érdekében, hogy a végfelhasználói eszközökön a szervezet adatainak megvédése beállított számos Intune-házirendek a Mellőzés eredményez. Így az Intune kínál mind a regisztrált és nem regisztrált eszközök rootolásának és függetlenítésének észlelését. Ebben a kiadásban az Intune most már használja a Google Play védelme API-k hozzáadása a nem regisztrált eszközök a meglévő legfelső szintű észlelési ellenőrzése. Google nem osztja meg a legfelső szintű észlelési ellenőrzéseket végez a teljes, miközben várhatóan ezen API-k, felhasználók, akik rendelkezik rootolva eszközeiket a testre szabható az eszközök bármilyen okból újabb operációsrendszer-frissítés részletes a régebbi eszközöket képes észlelni. Ezek a felhasználók majd egytől a vállalati adatokhoz hozzáférő, vagy a házirend-kompatibilis alkalmazások a vállalati fiókokra törlődhetnek. További értékek a rendszergazda már az Intune App Protection panelen található jelentéskészítési frissítéseket – a "Megjelölt felhasználók" a jelentés megmutatja, hogy mely felhasználók észlelése keresztül a Google Play Protect a SafetyNet API vizsgálatot, a "potenciálisan káros alkalmazások" jelentést fog megjelenítése, mely alkalmazások észlelése API-n keresztül a Google ellenőrzése alkalmazások vizsgálatát. Ez a funkció Android rendszeren érhető el. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>A Win32-alkalmazás adatai hibaelhárítás panelen érhető el <!-- 2617342    -->
Egy Win32-alkalmazás telepítése sikertelen naplófájlok gyűjteni az Intune-alkalmazás lesz **hibaelhárítás** panelen. Alkalmazás telepítési hibaelhárítással kapcsolatos további információkért lásd: [alkalmazás telepítési problémák elhárítása](troubleshoot-app-install.md).

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>A teljes képernyős böngésző és a Microsoft Edge böngésző alkalmazások teljes képernyős módban a Windows 10-eszközökön futtathatja <!-- 2935135  -->
Egy alkalmazás vagy több alkalmazás használhatja a teljes képernyős módban a Windows 10-es eszközökön. Ez a frissítés segítségével a böngészőben megjelenő alkalmazásokba teljes képernyős módban számos módosításait tartalmazza többek között:

- Adja meg a Microsoft Edge böngészőt vagy futtatható alkalmazásokat a teljes képernyős eszközön teljes képernyős böngésző (**eszközkonfiguráció** > **profilok** > **új profil**  >  **Windows 10 és újabb** tartozó platform > **teljes képernyős** profiltípus).
- Korlátozása a Microsoft Edge, így azt nem lehet (vagy is) a kioszkmódban futtatni (**eszközkonfiguráció** > **profilok** > **új profil**  >  **Windows 10 és újabb** tartozó platform > **eszközkorlátozások** profiltípus > **a Microsoft Edge böngésző**). Teljes képernyős módban fut, amikor a Microsoft Edge-beállítások a végfelhasználók által módosítható.

A jelenlegi beállítások listájáért lásd:

- [Windows 10-es és újabb beállításai a teljes képernyős fiókként való futtatásra](kiosk-settings-windows.md)
- [A Microsoft Edge böngésző eszközkorlátozások](device-restrictions-windows-10.md#microsoft-edge-browser)

A következőkre vonatkozik: Windows 10 és újabb

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Hatókörcímkék automatikus hozzárendelése a hatókörrel rendelkező rendszergazda által létrehozott erőforrások <!-- 3173823  -->
Amikor a rendszergazda létrehoz egy erőforrást, bármely, a rendszergazda rendelt hatókörcímkék automatikusan rendeli hozzá ezeket az új erőforrásokat.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>Új eszközkorlátozásokra vonatkozó beállítások az iOS és macOS-eszközök <!-- 3448774 -->
Bizonyos beállítások és funkciók iOS és macOS rendszerű eszközökön korlátozhatja (**eszközkonfiguráció** > **profilok** > **új profil**  >  **iOS** vagy **macOS** tartozó platform > **eszközkorlátozások** profiltípus). Ez a frissítés további funkciókat és vezérelheti, például beállítás képernyő idő módosítása esim-kártya beállításait és a mobil tervek késlelteti a szoftverfrissítéseket, blokkolja a tartalom gyorsítótárazása, a felhasználó látható-e, és egyéb beállítások hozzáadása.
Az aktuálisan elérhető funkcióit és korlátozhatja a beállítások megtekintéséhez lásd:
- [iOS-eszközök korlátozásaira vonatkozó beállítások](device-restrictions-ios.md)
- [macOS-eszközök korlátozásaira vonatkozó beállítások](device-restrictions-macos.md)

A következőkre vonatkozik:
- iOS
- macOS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>Sikertelen regisztráció jelentés áthelyezi az Eszközregisztráció panel <!-- 3560202 -->
A **sikertelen regisztrációk** jelentés helyezi át a **figyelő** szakaszában a **eszközregisztráció** panelen. Két új oszlopot (regisztrációs módszer és operációsrendszer-verzió) is bekerülnek.

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>Módosítsa a "Teljes képernyős" "Dedikált eszközök" <!-- 3598402  -->
Android-terminológia, igazodva **teljes képernyős** változik **dedikált eszközök** alatt eszközkonfigurációs profilokkal **Android enterprise**  >   **Eszköz tulajdonosa** > **Eszközkorlátozások**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>Safari és Delaying felhasználói szoftverfrissítési beállítások helyez át az Intune felhasználói felületén látható-e iOS frissítése <!-- 3640850, , 3803313  -->
IOS-eszközök esetén a Safari beállításait, és konfigurálhatja a szoftverfrissítéseket. Ebben a frissítésben ezek a beállítások az Intune felhasználói felület különböző részeinek helyez át:

- A Safari beállításait helyez át a **Safari** (**eszközkonfiguráció** > **profilok** > **új profil**  >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus) való **beépített alkalmazások**. 
- A **késlelteti az felhasználói szoftvereket látható-e frissítés az iOS-eszközök felügyelt** beállítás (**szoftverfrissítések** > **Update-szabályzatok iOS rendszerhez**) kerülát **Eszközkorlátozások** > **általános**.

A jelenlegi beállítások listájáért lásd: [eszközkorlátozások iOS](device-restrictions-ios.md) és [iOS szoftverfrissítések](software-updates-ios.md).

A következőkre vonatkozik: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>Korlátozások engedélyezése az eszköz között új képernyő idő az iOS-eszközökön <!-- 3699164  -->
Konfigurálhatja a **korlátozások engedélyezése az eszköz között** a felügyelt iOS-eszközök (**eszközkonfiguráció** > **profilok**  >  **Új profil** > **iOS** tartozó platform > **eszközkorlátozások** profiltípus > **általános**). Ebben a frissítésben ezzel a beállítással új **(csak felügyelt) képernyő idő**. A viselkedés megegyezik. Pontosabban: 

- iOS-es 11.4.1 és korábbi: **Blokk** megakadályozza, hogy a végfelhasználók számára az Eszközbeállítások között a saját korlátozásokkal. 
- iOS-es 12.0 és újabb verziók: **Blokk** megakadályozza, hogy a végfelhasználók saját beállítás **képernyő idő** az Eszközbeállítások között, beleértve a tartalom & adatvédelmi korlátozások. Frissített iOS 12.0-s eszközök többé nem jelenik meg a korlátozásokat fülre az Eszközbeállítások között. Ezek a beállítások szerepelnek **képernyő idő**. 

A jelenlegi beállítások listájáért lásd: [eszközkorlátozások iOS](device-restrictions-ios.md).

A következőkre vonatkozik: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>Az iOS-alkalmazások App-állapot részletei <!-- 3761235  -->
Új alkalmazás telepítési kapcsolatos hibaüzeneteket a következő lesz:
- VPP-alkalmazások a megosztott iPad telepítésekor hiba
- Hiba, amikor az app Store-ban le van tiltva.
- Hiba található a VPP-licenc az alkalmazás
- Nem sikerült telepíteni a rendszer alkalmazások az MDM-szolgáltató
- Nem sikerült telepíteni a alkalmazások eszköz esetén az elveszett eszköz mód vagy a teljes képernyős módban
- Nem sikerült telepíteni az alkalmazást, amikor a felhasználó nem jelentkezett be, az App Store

Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > "App name" > **eszköz telepítési állapota**. Új hibaüzenetek lesz elérhető a **állapot részletei** oszlop.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Online licenccel rendelkező Microsoft Store az üzleti alkalmazások telepítése <!-- 1672660  -->
Rendelje hozzá a szükséges online licenccel rendelkező Microsoft Store for Business-alkalmazások az eszköz a környezetben lehet. Központi telepítése a Microsoft Store for Business app így lehetővé teszi az alkalmazásnak, hogy az eszköz összes felhasználójához telepíthetők. Ez a tulajdonság csak a Windows 10 RS4 + asztali eszközökön alkalmazható. Az ügyfélalkalmazások hozzárendelés lapon találhat MSFB Online licencelt alkalmazások telepítésére, az eszköz a környezetben érhető el.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise-alkalmazás – hogy az alkalmazás üzembe helyezése <!-- 1171203 -->
Android-eszközökhöz a egy nem regisztrált alkalmazás alkalmazásvédelmi szabályzat regisztráció nélkül (alkalmazás-TUDJUK) a telepítési forgatókönyvben is elérheti, használja a felügyelt Google Play áruházbeli alkalmazások telepítése és ÜZLETÁGI alkalmazások a felhasználók számára. Pontosabban, az informatikai részleg már nem igényel a végfelhasználók számára, hogy lazábbá tehető az eszközeik biztonsági irányelvei, tiltják azáltal, hogy telepítések az ismeretlen forrásból származó alkalmazás katalógus és telepítési élményt nyújt a végfelhasználók számára. Emellett ebben a telepítési forgatókönyvben egy jobb végfelhasználói élményt biztosít.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-házirendek frissítése a hitelesítési módszert, és a vállalati portál alkalmazás telepítése  <!-- 1927359 -->
A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök, az Intune már nem támogatja a vállalati portál manuális telepítés a végfelhasználók az app store áruházból. Ez a változás csak akkor jelentősége, amikor Ön az Apple beállítási asszisztens regisztráció során hitelesítsék magukat. Ez a változás csak is hatással van a regisztrált iOS-eszközöket:  
* Az Apple configuratorral
* Apple üzleti vezető
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Ha a felhasználók a vállalati portál alkalmazást az App store áruházból telepítik, és próbálja meg, ezek eszközöket regisztrálni, akkor egy hibaüzenetet fog kapni. Ezek az eszközök csak céges portál használatához, amikor, a leküldött, automatikusan, az Intune-regisztráció során vár. Regisztrációs profilok az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Ha azt szeretné, hogy a DEP-eszközök felhasználói szeretné, hogy a vállalati portálon, szüksége lesz a beállítások megadása egy regisztrációs profilt. Emellett a **az eszköz azonosítására** a céges portál alkalmazás képernyőjén hamarosan elavulttá válnak.  
Is telepíthetik a vállalati portált a DEP-eszközökön már regisztrált, nyissa meg az Intune-nak frissítenie > ügyfélalkalmazások, és küldje le az alkalmazás-konfigurációs házirendek segítségével felügyelt alkalmazásként. A jövőbeli docs részletei elvégezheti ezeket a lépéseket ismerteti.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és átkerülnek a saját konfigurációs profil <!-- 3322847 -->
Az Intune-ban a felügyeleti sablonok (**eszközkonfiguráció** > **felügyeleti sablonok**) jelenleg privát előzetes verzióban érhető el. Ez a frissítés: Felügyeleti sablonok az Intune-ban kezelheti körülbelül 300 beállításokat tartalmaz. Korábban ezek a beállítások csak megtalálható a Helyicsoportházirend-szerkesztő.
Felügyeleti sablonok érhetők el a nyilvános előzetes verzióban felügyeleti sablonok helyez át a **eszközkonfiguráció** > **felügyeleti sablonok** való **eszköz konfigurációs** > **profilok** >**profil létrehozása** > a **Platform**, válassza a  **Windows 10 és újabb**, a **profiltípus**, válassza a **felügyeleti sablonok**.
Jelentéskészítés engedélyezve van a következőkre vonatkozik: Windows 10 és újabb

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune-ban macOS céges portálra sötét üzemmód <!-- 3300524 -->
Az Intune-ban macOS céges portálra sötét mód mostantól támogatja a macOS-hez. Ha engedélyezi a sötét üzemmód 10.14 + macOS-eszközön, a vállalati portál lehetőség a megjelenését, amely mutatja, hogy a üzemmód színeket.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Az Alkalmazásvédelmi szabályzat (APP) beállításai webes adatokhoz <!-- 2662995 -->
A webes tartalmakra vonatkozó APP szabályzatok beállításait az Android- és iOS-eszközökön is frissítjük, hogy hatékonyabban kezelhetők legyenek a webes http- és https-hivatkozások, valamint az univerzális iOS-hivatkozásokon és Android-alkalmazáshivatkozásokon keresztüli adatátvitel.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Elavult eszközök az eszközmegfelelőségi irányítópulton <!-- 1981119 -->
Egy jövőbeli frissítés eltávolítja az elavult eszközöket az eszközmegfelelőségi irányítópultról. Ez módosítani fogja a megfelelőségi számokat.

## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).

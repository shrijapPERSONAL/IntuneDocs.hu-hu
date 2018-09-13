---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6cc33bc6e03d2e0370c9e2c2dd9d3462296710e6
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329684"
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



### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS-es verziószám és buildszám megjelenítése <!-- 1892471 -->
Az iOS operációs rendszer verziószáma az **Eszközmegfelelőség** > **Eszközmegfelelőség** területen látható. Egy jövőbeli frissítéssel a buildszám is megjelenik.
A biztonsági frissítések megjelenésekor az Apple általában megtartja a verziószámot, de a buildszám változik. A megjelenített buildszám segítségével könnyen ellenőrizheti, hogy telepítve van-e a biztonsági frissítés.

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

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profil konfigurálása egyes képernyők kihagyásához a beállítási asszisztens működése során <!-- 2276470 -->
macOS-es regisztrációs profil létrehozásakor konfigurálhatja a profilt a következő képernyők bármelyikének kihagyására, amikor egy felhasználó a beállítási asszisztenst használja:
- Android-áttelepítés
- Hang megjelenítése
- Személyes adatok védelme
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Változás a helyszíni összekötők frissítési folyamatában <!-- 2277554 -->
Felhasználói visszajelzések alapján megváltozik a helyszíni összekötők frissítésének folyamata. Miután elvégezte a helyszíni összekötő kezdeti telepítését, a frissítések automatikusan lezajlanak. Ez a változás először a Microsoft Intune-hoz készült új PFX-tanúsítvány-összekötőnél jelenik meg, majd a soron következő további helyszíni összekötőknél is. 



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

Amikor az alkalmazások indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza az **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Az Office 365 Pro Plus nyelvi csomagjai <!-- 1833450 -->
Az Intune rendszergazdájaként további nyelveket helyezhet üzembe az Intune által felügyelt Office 365 Pro Plus alkalmazások számára. Az elérhető nyelvek listája tartalmazza a nyelvi csomag **Típusát** (alap, részleges vagy nyelvi ellenőrzési) is. Az Azure Portalon válassza a **Microsoft Intune** > **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen, az **Alkalmazástípusok** listáján, válassza az **Office 365 csomag** alatti **Windows 10** lehetőséget. Az **Alkalmazáscsomag beállításai** panelen válassza a **Nyelvek** lehetőséget.

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

Amikor az alkalmazások első indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza az **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

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




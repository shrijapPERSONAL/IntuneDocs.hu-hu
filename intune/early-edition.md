---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95ad588b084319cd8a0f5f5c5d92da0e892eed50
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745043"
---
# <a name="the-early-edition-for-microsoft-intune---june-2018"></a>A Microsoft Intune előzetes kiadása – 2018. június

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

<!-- 1806 start -->

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Egyetlen célra használható céges (COSU) funkció támogatása Android-eszközökhöz <!-- 1630973 -->

Az Intune támogatni fogja a gondosan felügyelt, zárolt, kioszk-stílusú Android-eszközöket. Ez lehetővé teszi a rendszergazdák számára, hogy egyetlen alkalmazásra vagy kis alkalmazáskészletre szűkítsék az eszközhasználatot, és megakadályozzák, hogy a felhasználók más alkalmazásokat engedélyezzenek vagy más műveleteket hajtsanak végre az eszközön.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS-támogatás az Apple Készülékregisztrációs programjában <!-- 747651 -->

Az Intune támogatni fogja a macOS rendszerű eszközök Apple Készülékregisztrációs programjába (DEP) történő regisztrálását. Ehhez tegye a következőket:

1. Az apple.com üzembe helyezésekor rendeljen hozzá macOS sorozatszámokat egy MDM-kiszolgálóhoz.
2. Importálja a sorozatszámokat az Intune-ba.
3. Hozzon létre egy regisztrációs profilt kifejezetten a macOS-eszközökhöz.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>A Google névváltoztatásai az Android for Work és a Play for Work kifejezéseknél <!--842873 -->
Az Intune a Google egyes márkaneveit érintő változtatásaihoz igazodva frissíteni fogja az „Android for Work” terminológiáját.  Az „Android for Work” és a „Play for Work” kifejezések használata megszűnik. A környezettől függően a következő kifejezések kerülnek használatba:

- Az „Android Enterprise” az általános, korszerű androidos felügyeleti környezetre vonatkozik.
- A „Munkahelyi profil” vagy a „Profil tulajdonosa” kifejezés a munkahelyi profilokkal felügyelt hozott eszközökre (BYOD) vonatkozik.
- A „Felügyelt Google Play” kifejezés a Google Áruházra vonatkozik.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Az iOS-alkalmazáskonfigurációk figyelése minden egyes eszközön <!-- 880037 eeready eestaged -->

A Microsoft Intune rendszergazdájaként minden egyes felügyelt eszközön nyomon követheti az iOS-alkalmazáskonfiguráció állapotát. Az Azure Portal **Microsoft Intune** oldalán kattintson az **Eszközök** > **Minden eszköz** lehetőségre. A felügyelt eszközök listáján az egyik eszközre kattintva nyissa meg a hozzá tartozó panelt. Az eszköz paneljén kattintson az **Alkalmazáskonfiguráció** elemre.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Az iOS-es eszközökön az alkalmazásvédelmi beállítások használatával letilthatja a harmadik féltől származó billentyűzeteket <!-- 1248481 -->
Az Intune-rendszergazdák az iOS-es eszközökön letilthatják a harmadik féltől származó billentyűzeteket, ha azok a szabályzat által védett alkalmazásokon hozzáférnek a céges adatokhoz. Ha az alkalmazásvédelmi szabályzat (APP) a harmadik félhez tartozó billentyűzetek letiltására van beállítva, az eszköz használója üzenetet kap, amikor először fér hozzá ilyen billentyűzettel a céges adatokhoz. A natív billentyűzeten kívül minden más lehetőség le lesz tiltva, és a felhasználók nem láthatják ezeket. A felhasználók csak egyszer látják az üzenetet. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Eszközmegfelelési szabályzat létrehozása macOS-eszközökön a tűzfalbeállítások használatával <!-- 1497640 -->
Amikor új macOS-es megfelelőségi szabályzatot hoz létre (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: macOS** > **Rendszerbiztonság**), a **Tűzfal** új beállításai válnak elérhetővé: 
- **Tűzfal**: Konfigurálhatja a bejövő kapcsolatok kezelését a környezetében.
- **Bejövő kapcsolatok**: **Letilthatja** az összes bejövő kapcsolatot az olyan alapvető internetes szolgáltatások kivételével, mint a DHCP, a Bonjour vagy az IPSec. Ez a beállítás letiltja az összes megosztási szolgáltatást is.
- **Rejtett üzemmód**: a rejtett üzemmód **engedélyezésével** megakadályozhatja, hogy a számítógép válaszoljon a bejövő kérelmekre. Az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre.

A macOS 10.12 és újabb verziókra vonatkozik

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>sAMAccountName használata fiókhoz tartozó felhasználónévként az e-mail profilokhoz <!-- 1500307 -->

Fiókhoz tartozó felhasználónévként használhatja a helyszíni **sAMAccountName** nevet az Android-, iOS- és Windows 10 rendszerű e-mail profilokhoz. Az Azure Active Directory (Azure AD) `domain` vagy `ntdomain` attribútumából a tartományt is lekérheti. Vagy adjon meg egy egyéni statikus tartományt.

A funkció használatához szinkronizálnia kell a(z) `sAMAccountName` attribútumot a helyszíni Active Directory-környezetből az Azure AD-ra.

Android, iOS, Windows 10 és későbbi verziókra vonatkozik.

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Nem-biometrikus PIN-kód kérése alkalmazások indítása vagy időtúllépés esetén <!-- 1506985 -->

Amikor az alkalmazások indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Céges alkalmazásadatok szelektív törlése <!-- 1507030 -->
A rendszergazdák új műveletként konfigurálhatják a céges adatok szelektív törlését, ha az alkalmazásvédelmi szabályzatok (APP) hozzáférési beállításai nem teljesülnek.  Ez a funkció lehetővé teszi a rendszergazdák számára, hogy a céges adatokat automatikusan védjék vagy távolítsák el az előre konfigurált feltételeken alapuló alkalmazásokról.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Mennyiségi vásárlási program keretében beszerzett iOS-alkalmazás visszavonása <!-- 1777384 -->
A Microsoft Intune rendszergazdájaként visszavonhatja bármely, mennyiségi vásárlási program (Volume Purchase Program, VPP) keretében vásárolt iOS-es alkalmazás licencét. A felhasználókat értesítheti, amikor megszűnik az alkalmazás hozzájuk rendelése. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. A visszavont licencek száma látható lesz az Intune **Alkalmazások** tevékenységcsoportján belüli **Licencelt alkalmazások** csomóponton. Az iOS-es VPP-alkalmazásokkal kapcsolatos további információkat a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakörben tekintheti meg.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Az Office 365 Pro Plus nyelvi csomagjai <!-- 1833450 -->
Az Intune rendszergazdájaként további nyelveket helyezhet üzembe az Intune által felügyelt Office 365 Pro Plus alkalmazások számára. Az elérhető nyelvek listája tartalmazza a nyelvi csomag **Típusát** (alap, részleges vagy nyelvi ellenőrzési) is. Az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen, az **Alkalmazástípusok** listáján, válassza az **Office 365 csomag** alatti **Windows 10** lehetőséget. Az **Alkalmazáscsomag beállításai** panelen válassza a **Nyelvek** lehetőséget.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP-alkalmazáslicenc visszavonása <!-- 1863797 -->
Rendszergazdaként visszavonhatja egy eszköz vagy egy felhasználó hozzárendelt iOS VPP-alkalmazáslicencét. Az iOS VPP-alkalmazás eltávolítása az alkalmazás licencének visszavonását is lehetővé teszi. Ezt követően az alkalmazáslicencet hozzárendelheti egy másik felhasználóhoz vagy eszközhöz. Az iOS VPP-alkalmazáslicencekre vonatkozó további információkat az [iOS mennyiségi programban vásárolt alkalmazások kezelése a Microsoft Intune-ban](vpp-apps-ios.md) című témakörben tekintheti meg.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Új frissítés a felhasználói felülethez a Céges portál webhelyen <!--2000968 -->
A felhasználók visszajelzései alapján új funkciókkal egészül ki a Céges portál webhely. Jelentős javulást fog tapasztalni az Android, az iOS, és a Windows rendszerű eszközök már meglévő funkciói és használhatósága terén. Új, modern és rugalmas külsőt kapnak a webhely különböző területei, köztük az eszközadatok, a visszajelzés, a támogatás és az eszközök áttekintése. Amit még tapasztalni fog:

- Zökkenőmentes munkafolyamatok minden eszközplatformon
- Hatékonyabb eszközazonosítási és beléptetési folyamatok
- Praktikusabb hibaüzenetek
- Barátságosabb nyelvezet, kevesebb műszaki zsargon
- Alkalmazások közvetlen hivatkozásainak megoszthatósága
- Nagy méretű alkalmazáskatalógusok javított teljesítménye
- Nagyobb hozzáférhetőség minden felhasználó számára

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Az Office 365 Pro Plus alkalmazás üzemelő példányának szerkesztése <!-- 2150145 -->
A Microsoft Intune rendszergazdájaként több lehetősége lesz az saját Office 365 Pro Plus üzemelő példány szerkesztésére. Az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazások** lehetőséget. Az alkalmazások listáján jelölje ki a saját Office 365 Pro Plus csomagot.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Feltöltött ismétlődő céges eszközazonosítók soronkénti áttekintése <!-- 2203794 -->
A céges azonosítók feltöltésekor az Intune az ismétlődések listázásával ad lehetőséget a döntésre, hogy cseréli vagy megtartja a meglévő információt. Az ismétlődések esetén készülő jelentés akkor jelenik meg, ha az **Eszközregisztráció** > **Céges eszközazonosítók** > **Azonosítók hozzáadása** lehetőséget választja. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Céges eszközazonosítók manuális hozzáadása <!-- 2203803 -->
Manuálisan adhat hozzá céges eszközazonosítókat. Válassza az **Eszközregisztráció** > **Céges eszközazonosítók** > **Hozzáadás** lehetőséget.

### <a name="new-status-for-devices-in-device-configuration----2308882---"></a>Új eszközállapotok az eszközregisztrációban <!-- 2308882 -->
Az **Eszközregisztráció** > **Áttekintés** területen a következő új állapotok jelennek meg:
- Sikerült
- Hiba
- Ütközés
- Függőben
- Nem alkalmazható Egy olyan kép is megjelenik, amely mutatja a más platformon lévő eszközszámot. Például egy iOS-profil megtekintése esetén a profilhoz rendelt, nem iOS rendszerű eszközök száma is látható lesz az új csempén. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Az eszközmegfelelőség támogatja a harmadik féltől származó vírusvédelmi megoldásokat <!-- 2325484 -->
Eszközmegfelelőségi szabályzat létrehozásakor (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: Windows 10 és későbbi verziók** > **Beállítások** > **Rendszerbiztonság**), új **Eszközbiztonsági** lehetőségek jelennek meg: 
- **Vírusvédelem**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centeren regisztrált vírusvédelmi megoldások (például Symantec) használatával ellenőrizheti a megfelelőséget. 
- **Kémprogram-elhárító**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centeren regisztrált kémprogram-elhárító megoldások (például Symantec) használatával ellenőrizheti a megfelelőséget. 

A Windows 10 és újabb verziókra vonatkozik 

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Palo Alto Networks GlobalProtect VPN-profilok támogatása <!-- 1333680 eeready ! -->

Ez a frissítés lehetővé teszi a Palo Alto Networks GlobalProtect szolgáltatás választását a VPN-kapcsolat típusaként az Intune-beli VPN-profilokban (**Eszközök konfigurálása** > **Profilok** > **Profil létrehozása** > **Profil típusa** > **VPN**). Ebben a kiadásban az alábbi platformok támogatottak: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Megfelelőség beállítása az eszköz helye alapján <!-- 851881 ! -->
Bizonyos esetekben érdemes a vállalati erőforrásokhoz való hozzáférést egy adott helyre korlátozni, amelyet hálózati kapcsolattal ad meg. Megfelelőségi szabályzatot (**Eszközmegfelelőség** > **Helyek**) az eszköz IP-címe alapján hozhat létre. Ha az eszköz az IP-címtartományon kívülre kerül, akkor nem férhet hozzá a vállalati erőforrásokhoz.

A következőkre vonatkozik: Android 6.0-s és újabb eszközök frissített Céges portál alkalmazással

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Továbbfejlesztett hibaelhárítás az alkalmazástelepítéshez <!-- 928990 -->
A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. Bevezetjük az alkalmazás-hibaelhárítási funkcióink nyilvános előzetes verzióját. Ennek keretében megjelenik egy új, **Kezelt alkalmazások** nevű csomópont minden egyedülálló eszköz alatt. Ez a Intune MDM-en keresztül szolgáltatott alkalmazások listáját tartalmazza. A csomóponton belül az alkalmazástelepítési állapotokat tekintheti meg. Ha kijelöl egy önálló alkalmazást, megnyithatja annak hibaelhárítási nézetét. A hibaelhárítási nézetben megtekintheti az alkalmazás végpontok közötti életciklusát, például a létrehozási, a módosítási, a célzási dátumot, valamint az alkalmazás egy eszközre való továbbításának dátumát. Továbbá ha az alkalmazás telepítése sikertelen volt, megjelenik egy hibakód, és egy hasznos üzenet a hiba okáról.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Nem-biometrikus PIN-kód kérése alkalmazások első indítása vagy időtúllépés esetén <!-- 1506985 --> 

Amikor az alkalmazások első indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Alkalmazás-hozzáférés letiltása a nem jóváhagyott eszközgyártókon és -modelleken <!-- 1425689 ! -->
Az Intune rendszergazdái egy adott Android-gyártókat és/vagy iOS-gyártókat tartalmazó listát kényszeríthetnek az Intune App Protection-szabályzatokkal. A rendszergazda egy pontosvesszőkkel elválasztott listában adhat meg gyártókat az Android-szabályzatokhoz, valamint eszközmodelleket az iOS-szabályzatokhoz. Az Intune App Protection-szabályzatok csak Android- és iOS-eszközökre vonatkoznak. A megadott listán két különálló művelet hajtható létre:
- Az alkalmazás-hozzáférés letiltása a nem megadott eszközökön,
- vagy a vállalati adatok szelektív törlése a nem megadott eszközökön. 

A felhasználó nem férhet hozzá a célalkalmazáshoz, ha az nem felel meg a szabályzat feltételeinek. A rendszer a beállítások alapján letilthatja a felhasználót, vagy szelektíven törölheti annak vállalati adatait az alkalmazáson belül. iOS-eszközökön a funkció működéséhez az is szükséges, hogy az alkalmazások (vagyis a WXP, az Outlook, a Managed Browser és a Yammer) integrálják az Intune App SDK-t, hogy a megcélzott alkalmazásoknál kötelezővé lehessen tenni a minimális verzióbeállításokat. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Android-eszközökön ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség. 

A végfelhasználói eszközökön az Intune-ügyfél az Application Protection-szabályzatok Intune-panelén megadott egyszerű karakterlánc-egyezések alapján végezne műveleteket. Ez teljes mértékben az eszköz által jelentett értéktől függ. Ennek fényében a rendszergazának kell ügyelnie arra, hogy a kívánt viselkedés az elvártnak megfelelően működjön. Ezt úgy lehet elérni, ha teszteli a beállítást különböző eszközgyártókkal és -modellekkel egy kisebb felhasználói csoportban. A Microsoft Intune-ban válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget az alkalmazásvédelmi szabályzatok megtekintéséhez és hozzáadásához. További információ az alkalmazásvédelmi szabályzatok létrehozásáról: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioszkmód engedélyezése Windows 10-eszközökön <!-- 1560072 ! -->
Windows 10-eszközökön létrehozhat egy konfigurációs profilt, és engedélyezheti a kioszkmódot (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10** > **Eszközkorlátozások** > **Kioszkmód**). Ebben a frissítésben a **Kioszk (előnézet)** beállítást **Kioszk (elavult)** névre neveztük át. A **Kioszk (elavult)** beállítás használata már nem javasolt, de a júliusi frissítésig még működik. A **Kioszk (elavult)** beállítást az új **Kioszkmód** profiltípus helyettesíti (**Profil létrehozása** > **Windows 10** > **Kioszk (előnézet)**), amely a kioszkok Windows 10 RS4-es és újabb verziós konfigurációjához tartalmaz beállításokat.

A Windows 10 és újabb verziókra vonatkozik.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Az alkalmazás alkalmazásfelhasználói modellben használt azonosítójának (AUMID) lekérése a Microsoft Store Vállalatoknak alkalmazásaihoz kioszkmódban <!-- 1560077 ! -->
Az Intune lekérheti az alkalmazás alkalmazásfelhasználói modellben használt azonosítóját (AUMID) a Microsoft Store Vállalatoknak alkalmazásaihoz, így hatékonyabb kioszkprofil-konfigurációt nyújt.

További információ a Microsoft Store Vállalatoknak alkalmazásairól: [A Microsoft Store Vállalatoknak áruházban vásárolt alkalmazások felügyelete](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Az alkalmazásvédelmi szabályzatok műveleteinek elérése <!-- 1483510 EEready -->
Hamarosan úgy konfigurálhatja az alkalmazásvédelmi szabályzatokat, hogy azokkal törölje, letiltsa vagy figyelmeztesse a nem megfelelő eszközöket. A legújabb művelet a *törlés*, amely eltávolítja a vállalati adatokat az eszközről. Törlés esetén az eszköz felhasználója értesítést kap a törlés okáról és a lehetséges szervizelési lépésekről. Egyes beállítások – például az operációs rendszer minimális verziója – esetén több műveletet is alkalmazhat, például letiltás és törlés. Ezek a műveletek az alkalmazás indításakor aktiválódnak.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Új leltáradatok Windows-eszközökhöz <!-- 1333569 eeready -->

Windows-eszközök esetében a következő leltáradatokat érheti el az eszköz **Hardver** lapján (**Csoportok** > **Minden mobileszköz** > **Eszközök** > Válassza ki a felhasználó eszközét > **Tulajdonságok megtekintése** > **Hardver**):
- TPM
- Vírusvédelem
- Kémprogram-elhárító
- Tűzfal
- UAC
- Akkumulátor
- Tartománynév

Az adatok CSP általi lekéréséről a [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) című cikk DeviceStatus témájú szakaszaiban talál további információkat.

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune és a Microsoft Edge böngésző <!-- 1818969 -->
A Microsoft Edge mobilböngésző (iOS és Android) mostantól támogatja az Intune alkalmazásvédelmi szabályzatait. Az Edge böngészőalkalmazásba a céges Azure AD-fiókjukkal bejelentkező felhasználókat az Intune védi. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Új nyelv/terület beállítás automata OOBE konfigurálásakor <!-- 1821766 -->
A kezdőélmény automata profiljaiban egy új konfigurációs beállítás lesz elérhető, amellyel megadható a profilok nyelve és régiója.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Új beállítás az eszköz billentyűzetének konfigurálásához <!-- 1821768 -->
A kezdőélmény automata profiljaiban egy új beállítás lesz elérhető, amellyel konfigurálható a billentyűzet.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS- és macOS-eszközök képernyőjének megosztása a TeamViewerrel <!-- 1985547 -->
Jelenleg a TeamViewerrel távolról felügyelheti [az Intune által kezelt Android- és Windows-eszközöket](device-profile-android-teamviewer.md).

A rendszergazdák ezentúl a TeamViewerhez csatlakozva képernyőmegosztást kezdeményezhetnek iOS- és macOS-eszközökkel. Az iPhone-, iPad- és macOS-felhasználók valós időben megoszthatják a képernyőjüket bármilyen más asztali vagy mobileszközzel. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Visszatért az eszközprofil grafikus felhasználói diagramja <!-- 2160133 -->
Az eszközprofil grafikus felhasználói diagramján megjelenített számok javításakor (**Eszközkonfiguráció** > **Profilok** > Válasszon ki egy meglévő profilt > **Áttekintés**) ideiglenesen eltávolítottuk a grafikus felhasználói diagramot.

Ezzel a frissítéssel visszatér a grafikus felhasználói diagram, amely az Azure Portalon jelenik meg.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Minden felhasználó és eszköz hozzárendelése hatókörcsoportokként <!-- 2196803 -->
Minden felhasználót, eszközt és a hatókörcsoportok felhasználóit és eszközeit hozzárendelheti. Ehhez válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelés** > **Hozzárendelések** > hozzárendelés kiválasztása > **Hatókör (csoportok)** lehetőséget.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Az Autopilot-profilok csoportokat fognak megcélozni <!-- 1877935 -->
Az AutoPilot Deployment-profilok jelenleg egyes eszközökhöz rendelhetők hozzá. A funkció kiadása után így rendelheti hozzá a profilokat:
- Hozzon létre egy Azure AD-csoportot, mely tartalmazza az AutoPilot-eszközöket.
- Rendelje hozzá a kívánt profilokat az Azure AD-csoporthoz. Az AutoPilot-profil ezután hozzá lesz rendelve az adott csoportban található AutoPilot-eszközökhöz.

### <a name="management-name-field-will-be-editable----1875989---"></a>A Felügyeleti név mező szerkeszthető lesz <!-- 1875989 -->
Szerkesztheti a Felügyeleti név mezőt az eszköz **Tulajdonságok** panelén. A mező szerkesztéséhez válassza az **Eszközök** > **Minden eszköz** > Válassza ki az eszközt > **Tulajdonságok** lehetőségét. A Felügyeleti név mezővel egyéni módon azonosíthat egy eszközt.

<!-- 1804 start -->

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>További helyi eszközbiztonsági beállítások <!-- 1403702 -->
További helyi eszközbiztonsági beállításokat adhat meg a Windows 10 rendszerű eszközökhöz. Ezek a további beállítások a következő területeken lesznek elérhetők: Microsoft hálózati ügyfél, Microsoft hálózati kiszolgáló, hálózati hozzáférés és biztonság, valamint interaktív bejelentkezés. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

### <a name="rules-for-removing-devices----1609459---"></a>Szabályok eszközeltávolításhoz <!-- 1609459 -->
Új szabályok lesznek elérhetők, melyekkel automatikusan eltávolíthatja azokat az eszközöket, amelyek nem jelentkeztek be az Ön által megadott számú napon keresztül. Az új szabály megtekintéséhez nyissa meg az **Intune** panelt, és válassza az **Eszközök**, majd az **Eszközeltávolítási szabályok** lehetőséget.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Fogyasztói alkalmazások és funkciók használatának meggátolása a Windows 10 Enterprise RS4 rendszerű Autopilot-eszközökön<!-- 1621980 -->
Le fogja tudni tiltani a fogyasztói alkalmazások és funkciók telepítését a Windows 10 Enterprise RS4 rendszerű AutoPilot-eszközökön. Ennek a funkciónak a megtekintéséhez válassza az **Intune** > **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Windows AutoPilot-profilok** > **Új létrehozása** > **Beléptetési beállítások** lehetőséget. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Több Exchange Connector támogatása <!-- 2070451 -->

Mostantól nem csak egy Microsoft Intune Exchange Connectort használhat bérlőnként. Az Intune hamarosan több Exchange Connector használatát is támogatni fogja, hogy több helyszíni Exchange-szervezetnél állíthassa be az Intune feltételes hozzáférést.

A helyszíni Intune Exchange Connector segítségével annak alapján kezelheti az eszközök helyszíni Exchange-postafiókokhoz történő hozzáférését, hogy az adott eszköz regisztrálva van-e az Intune-ban, és megfelel-e az Intune eszközmegfelelőségi szabályzatainak. Az összekötő beállításához töltse le a helyszíni Intune Exchange Connectort az Azure Portalról, és telepítse egy Exchange-szervezeten belüli kiszolgálón. A Microsoft Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget, majd a **Telepítés** területen kattintson az **Exchange ActiveSync Connector** lehetőségre. Töltse le a helyszíni Exchange Connectort, és telepítse egy Exchange-szervezeten belüli kiszolgálón. Most, hogy már nem csupán egy Exchange Connectort használhat bérlőnként, ugyanezekkel a lépésekkel letöltheti és telepítheti az összekötőt minden további Exchange-szervezethez, ha vannak ilyenek.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Kötelező üzletági (LOB) alkalmazások üzembe helyezésének lehetősége az összes felhasználó számára Windows 10 rendszerű asztali eszközökön <!-- 1627835 RS4 -->
Az ügyfelek eszközkörnyezetben helyezhetik üzembe a kötelező üzletági Windows 10 rendszerű alkalmazásokat. Így az alkalmazások az eszköz összes felhasználója számára elérhetővé válnak. Ez csak Windows 10 rendszerű asztali eszközökre vonatkozik.

### <a name="company-portal-enrollment-improved----1874230--"></a>A Céges portálra történő regisztráció továbbfejlesztése <!-- 1874230-->
A Céges portálon az 1703-as vagy annál újabb verziójú Windows 10 rendszerrel eszközt regisztráló ügyfelek az alkalmazás elhagyása nélkül hajthatják végre a regisztráció első lépését.

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




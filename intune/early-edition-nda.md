---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0500194f5afaba11f37b84bbdf606e6167632a71
ms.sourcegitcommit: afa2e84d5cadf5542ecabc26e61dc71919992a22
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340182"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>A Microsoft Intune előzetes kiadása – 2018. július

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

<!-- 1807 start -->

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Eszközök PIN-kódjának alaphelyzetbe állítása a Windows 10-es Céges portál alkalmazásból <!-- 2101282 --> 
Alkalmazottaik rövidesen közvetlenül a Windows 10-es Céges portál alkalmazásból tudják alaphelyzetbe állítani eszközeik PIN-kódját vagy jelszavát. Ez a funkció a PIN-kód alaphelyzetbe állítását támogató, Intune által felügyelt távoli és helyszíni eszközökön is elérhető lesz. A távoli eszközre vonatkozó kérelmek az eszköz típusától függően vagy eltávolítják az eszköz PIN-kódját, vagy létrehoznak egy ideiglenes PIN-kódot. A helyszíni eszközre alaphelyzetbe állítást kérő felhasználók az eszköz Beállítások alkalmazásához lesznek irányítva.

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>S/MIME használata titkosításhoz és aláíráshoz egy felhasználó több eszközén <!-- 1333642 -->
Egy későbbi frissítés része lesz egy új importált tanúsítványprofilt használó S/MIME e-mail-titkosítás (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > platform kiválasztása > **Importált PKCS-tanúsítvány** profiltípus). Az Intune-ban a tanúsítványok PFX formátumban importálhatók. Az Intune képes ugyanazokat a tanúsítványokat az egy felhasználó által regisztrált több eszközre is telepíteni. Ez a következőket is magában foglalja:

- A natív iOS-es e-mail-profil támogatja az S/MIME titkosítás PFX formátumú importált tanúsítványok használatával történő engedélyezését.
- A Windows Phone 10 rendszerű eszközök natív levelezőalkalmazása automatikusan az S/MIME tanúsítványt használja.
- A privát tanúsítványok több platformon is telepíthetők. A S/MIME-ot azonban nem minden e-mail-alkalmazás támogatja.
- Más platformokon az S/MIME engedélyezéséhez szükség lehet a levelező alkalmazás manuális konfigurálására.  
- Az S/MIME titkosítást támogató e-mail-alkalmazások esetleg az MDM által nem támogatható módon kezelik az S/MIME e-mail-titkosításhoz szükséges tanúsítványok fogadását, például a közzétevőjük tanúsítványtárából olvassák ki azokat.

Támogatott a következőkön: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP eszközlicencek használata a Céges portál előzetes kiépítésére a DEP-regisztráció során <!-- 1608345 -->
Volume Purchase Program (VPP) eszközlicencekkel előre kiépítheti a Céges portált az Készülékregisztrációs program (DEP) keretében végzett regisztrációk során. Ehhez a regisztrációs profil létrehozása vagy szerkesztése során kell megadni a Céges portál telepítéséhez használni kívánt VPP-jogkivonatot. Fontos, hogy a jogkivonat ne járjon le, és hogy elég licenccel rendelkezzen a Céges portál alkalmazáshoz. Amennyiben a jogkivonat lejár vagy a licencei elfogynak, az Intune az App Store-beli Céges portált fogja leküldeni (ilyenkor a rendszer kéri az Apple-azonosítót).

### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Eszközök tömeges törlése az Eszközök panelen <!-- 1793693 -->
Lehetséges lesz egyszerre több eszközt törölni az Eszközök panelen. Válassza az **Eszközök** > **Minden eszköz** lehetőséget >jelölje ki a törölni kívánt eszközöket > válassza a **Törlés** lehetőséget. A nem törölhető eszközök esetében riasztás fog megjelenni.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Új Wi-Fi eszközkonfigurációs profil Windows 10 vagy újabb rendszerhez <!-- 1879077 -->
Wi-Fi profilok jelenleg XML-fájlok használatával importálhatók és exportálhatók. A Wi-Fi eszközkonfigurációs profilok közvetlenül az Intune-ban is létrehozhatók lesznek, ahogyan néhány más platformon is.

A profil létrehozásához nyissa meg az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Wi-Fi** elemet. 

A Windows 10 és újabb verziókra vonatkozik.

###  <a name="windows-line-of-business-lob-apps-file-extension-rename----1884873---"></a>Módosul a Windows rendszerű üzletági (LOB) alkalmazások fájlnévkiterjesztése <!-- 1884873 -->
A Windowsos üzletági alkalmazások fájlnévkiterjesztése *.appx* és *.appxbundle* helyett *.msix* és *.msixbundle* lesz. A **Mobilalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséggel hozzáadhat egy alkalmazást a Microsoft Intune-hoz. Megjelenik az **Alkalmazás hozzáadása** panel, ahol kiválaszthatja az **Alkalmazás típusát**. Windowsos üzletági alkalmazásokhoz válassza az **Üzletági alkalmazás** lehetőséget az alkalmazás típusa területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy megfelelő kiterjesztésű telepítőfájlt.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP konfigurációs csomag automatikus hozzáadása a konfigurációs profilhoz <!-- 2144658 -->
Ha a [Komplex veszélyforrások elleni védelem használata mellett készít elő](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) eszközöket az Intune-ban, ehhez jelenleg le kell töltenie egy konfigurációs csomagot, melyet aztán hozzáad a konfigurációs profilhoz. Egy későbbi frissítéstől kezdve az Intune automatikusan megkapja a csomagot a Windows Defender biztonsági központtól, és hozzáadja azt az Ön profiljához.

A Windows 10 és újabb verziókra vonatkozik.

### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>A Kioszkmód – elavult lehetőség nem használható és nem módosítható <!-- 2149998 -->
A [Kioszkmód funkció](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Eszközkorlátozások**) elavul. Helyét a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) veszi át. A **Kioszkmód - Elavult** funkció nem lesz használható, és a felhasználói felület nem lesz módosítható és nem lesz frissíthető. 

A kioszkmód a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával engedélyezhető.

Windows 10 vagy újabb, és a Windows Holographic for Business rendszerekre vonatkozik

### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Az API-k külső hitelesítésszolgáltatókat használnak <!-- 2184013 -->
Lesz egy Java API, amely külső hitelesítésszolgáltatókat engedélyez az Intune és az SCEP integrálásához. A felhasználók így hozzáadhatják egy profilhoz az SCEP-tanúsítványt, és alkalmazhatják az MDM-et használó eszközökre.

Az Intune jelenleg az [Active Directory tanúsítványszolgáltatást használó SCEP-kérelmeket](certificates-scep-configure.md) támogatja.

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM-megfelelőség ellenőrzése <!-- 2192052 -->
Egy későbbi frissítésnek része lesz a System Center Configuration Manager (SCCM) egy új megfelelőségi beállítása (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Windows 10**). Az SCCM az Intune-nak küld megfelelőségi jeleket. Az Intune beállításával megkövetelhető, hogy minden SCCM-jelre „megfelelő” legyen a válasz.

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. Az SCCM-ben ehhez a követelményhez a „Telepítve” állapot tartozik. Ha az eszközön bármelyik program ismeretlen állapotban van, akkor az eszköz nem megfelelőnek fog minősülni az Intune-ban.

A Windows 10 és újabb verziókra vonatkozik

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>VPP-jogkivonatok lejáratára vagy a Céges portál licenceinek alacsony számára vonatkozó riasztások <!-- 2237572 -->
Ha a Volume Purchase Program (VPP) igénybe vételével építi ki a Céges portált a DEP-regisztráció során, az Intune riasztást fog küldeni a VPP-jogkivonat közeli lejáratáról, és ha a Céges portál licencei hamarosan elfogynak.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Megerősítés szükséges a Céges portál kiépítéséhez éppen használt VPP-jogkivonat törléséhez <!-- 2237634 -->
A jövőben meg kell erősíteni az olyan Volume Purchase Program (VPP) jogkivonat törlését, amelyet éppen a Céges portál kiépítéséhez használnak a DEP-regisztráció során.

### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Androidos eszközök automatikus megjelölése regisztráltként a Samsung Knox Mobile Enrollment „cégesként” használva <!-- 2404851 -->
A Samsung Knox Mobile Enrollment használatával regisztrált Androidos eszközök alapértelmezés szerint **céges** megjelölést kapnak az **Eszköz tulajdonjoga** alatt. Nem lesz szükség a céges eszközök IMEI- vagy sorozatszám alapján történő manuális azonosítására a Knox Mobile Enrollment használatával végzett regisztráció előtt.

### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>A Munkamenet befejezése gomb megjelenítése ki- és bekapcsolható a kioszkmódú böngészőkben <!-- 2455253 -->
Konfigurálható lesz, hogy a kioszkmódú böngészőkben megjelenjen-e a Munkamenet vége gomb. A vezérlő az **Eszközkonfiguráció** > **Kioszkmód (előzetes verzió)** >  **kioszkmódú webböngésző** alatt található. Bekapcsolása esetén, ha a felhasználó a gombra kattint, az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot töröl, és visszatér az alapértelmezett URL-címre.

### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM mobilkonfigurációs profil létrehozása <!-- 2564077 -->
Az **Eszközkonfiguráció** alatt létre lehet majd hozni egy eSIM mobilprofilt. Importálható lesz egy fájl, amely a mobilszolgáltató által megadott mobiltelefon-aktiválási kódokat tartalmazza. Ezek a profilok aztán alkalmazhatók lesznek az eSIM LTE-t engedélyező Windows 10 rendszerű eszközökön, amilyen a Surface Pro LTE és más eSIM-képes eszközök.

Ellenőrizze, hogy [eszközei támogatják-e az eSIM-profilokat](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

A Windows 10 és újabb verziókra vonatkozik. 




<!-- 1806 start -->

### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ütköző eszközkonfigurációs profilok kiemelése <!-- 1556983 -->
Az **Eszközkonfiguráció** alatt megjelenik a meglévő profilok listája. Ez a frissítés ezt egy újabb oszloppal bővíti, amely az ütköző profilokról közöl részleteket. Egy ütközést jelző sor kiválasztásával megjeleníthető az ütközést okozó beállítás és profil. 

További tudnivalók az [Eszközkonfigurációs profilokról](device-profiles.md).

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

### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>A Céges portál alkalmazás meg nem felelésről szóló üzeneteinek frissítései <!-- 1832222 -->
Felülvizsgáljuk az üzeneteket, amelyeket az eszközök felhasználói akkor kapnak, ha az eszköz nem megfelelő. Az üzenetek eredeti jelentése megmarad, de barátságosabb hangnemben, kevesebb szakzsargonnal fogalmazzuk át őket. Frissítjük a dokumentációra és a megoldási lépésekre mutató hivatkozásokat is, hogy naprakészek legyenek.  

Az alábbi szöveg eredeti és átdolgozott változata a megjelenő üzenetek javítását példázza:  

Eredeti: *Az eszköz nem lépett kapcsolatba az Intune szolgáltatással a rendszergazda által megkövetelt meghatározott időszakban. A probléma megoldásához nyissa meg a Céges portál alkalmazást az eszközön, és kattintson a Megfelelőség ellenőrzése gombra.*  

Átdolgozott: *Az Ön eszköze már jó ideje nem jelentkezett be a vállalatánál. A kapcsolat újbóli felvételéhez nyissa meg a Céges portál alkalmazást az eszközön, és koppintson a Beállítások ellenőrzése lehetőségre.*  

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Az Office 365 Pro Plus alkalmazás üzemelő példányának szerkesztése <!-- 2150145 -->
A Microsoft Intune rendszergazdájaként több lehetősége lesz az saját Office 365 Pro Plus üzemelő példány szerkesztésére. Az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazások** lehetőséget. Az alkalmazások listáján jelölje ki a saját Office 365 Pro Plus csomagot.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Feltöltött ismétlődő céges eszközazonosítók soronkénti áttekintése <!-- 2203794 -->
A céges azonosítók feltöltésekor az Intune az ismétlődések listázásával ad lehetőséget a döntésre, hogy cseréli vagy megtartja a meglévő információt. Az ismétlődések esetén készülő jelentés akkor jelenik meg, ha az **Eszközregisztráció** > **Céges eszközazonosítók** > **Azonosítók hozzáadása** lehetőséget választja. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Céges eszközazonosítók manuális hozzáadása <!-- 2203803 -->
Manuálisan adhat hozzá céges eszközazonosítókat. Válassza az **Eszközregisztráció** > **Céges eszközazonosítók** > **Hozzáadás** lehetőséget.

### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Új eszközmegfelelőségi eszközállapotok <!-- 2308882 -->
A következő új állapotok lesznek hozzáadva az **Eszközmegfelelőség** > **Szabályzatok** > egy szabályzat kijelölése > **Áttekintés** alatt:
- Sikerült
- Hiba
- Ütközés
- Függőben
- Nem alkalmazható

Egy olyan kép is megjelenik, amely mutatja a más platformon lévő eszközszámot. Például egy iOS-profil megtekintése esetén a profilhoz rendelt, nem iOS rendszerű eszközök száma is látható lesz az új csempén. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Az eszközmegfelelőség támogatja a harmadik féltől származó vírusvédelmi megoldásokat <!-- 2325484 -->
Eszközmegfelelőségi szabályzat létrehozásakor (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: Windows 10 és későbbi verziók** > **Beállítások** > **Rendszerbiztonság**), új **Eszközbiztonsági** lehetőségek jelennek meg: 
- **Vírusvédelem**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centeren regisztrált vírusvédelmi megoldások (például Symantec) használatával ellenőrizheti a megfelelőséget. 
- **Kémprogram-elhárító**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centeren regisztrált kémprogram-elhárító megoldások (például Symantec) használatával ellenőrizheti a megfelelőséget. 

A Windows 10 és újabb verziókra vonatkozik 

<!-- 1805 start -->

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Továbbfejlesztett hibaelhárítás az alkalmazástelepítéshez <!-- 928990 -->
A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. Bevezetjük az alkalmazás-hibaelhárítási funkcióink nyilvános előzetes verzióját. Ennek keretében megjelenik egy új, **Kezelt alkalmazások** nevű csomópont minden egyedülálló eszköz alatt. Ez a Intune MDM-en keresztül szolgáltatott alkalmazások listáját tartalmazza. A csomóponton belül az alkalmazástelepítési állapotokat tekintheti meg. Ha kijelöl egy önálló alkalmazást, megnyithatja annak hibaelhárítási nézetét. A hibaelhárítási nézetben megtekintheti az alkalmazás végpontok közötti életciklusát, például a létrehozási, a módosítási, a célzási dátumot, valamint az alkalmazás egy eszközre való továbbításának dátumát. Továbbá ha az alkalmazás telepítése sikertelen volt, megjelenik egy hibakód, és egy hasznos üzenet a hiba okáról.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Nem-biometrikus PIN-kód kérése alkalmazások első indítása vagy időtúllépés esetén <!-- 1506985 --> 

Amikor az alkalmazások első indításakor vagy rendszergazda által megállapított időtúllépés esetén az Intune nem-biometrikus PIN-kódot kér, ezzel korlátozza a biometrikus azonosítás használatát a céges adatokhoz való hozzáféréshez, és növeli a mobilalkalmazás-felügyeletet (MAM) engedélyező alkalmazások biztonságát. A beállítások azokat a felhasználókat érintik, akik a Touch ID (iOS), a Face ID (iOS), az Android Biometric, vagy más jövőbeli biometrikus hitelesítési módszerekkel férnek hozzá az APP/MAM-engedélyezésű alkalmazásokhoz. A beállítások segítségével az Intune rendszergazdái a felhasználói hozzáférés kiterjedtebb ellenőrzése révén kizárhatják annak lehetőségét, hogy a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert alkalmazó eszközök céges adatokat adjanak ki jogosulatlan személyek számára. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Alkalmazás-hozzáférés letiltása a nem jóváhagyott eszközgyártókon és -modelleken <!-- 1425689 ! -->
Az Intune rendszergazdái egy adott Android-gyártókat és/vagy iOS-gyártókat tartalmazó listát kényszeríthetnek az Intune App Protection-szabályzatokkal. A rendszergazda egy pontosvesszőkkel elválasztott listában adhat meg gyártókat az Android-szabályzatokhoz, valamint eszközmodelleket az iOS-szabályzatokhoz. Az Intune App Protection-szabályzatok csak Android- és iOS-eszközökre vonatkoznak. A megadott listán két különálló művelet hajtható létre:
- Az alkalmazás-hozzáférés letiltása a nem megadott eszközökön,
- vagy a vállalati adatok szelektív törlése a nem megadott eszközökön. 

A felhasználó nem férhet hozzá a célalkalmazáshoz, ha az nem felel meg a szabályzat feltételeinek. A rendszer a beállítások alapján letilthatja a felhasználót, vagy szelektíven törölheti annak vállalati adatait az alkalmazáson belül. iOS-eszközökön a funkció működéséhez az is szükséges, hogy az alkalmazások (vagyis a WXP, az Outlook, a Managed Browser és a Yammer) integrálják az Intune App SDK-t, hogy a megcélzott alkalmazásoknál kötelezővé lehessen tenni a minimális verzióbeállításokat. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Android-eszközökön ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség. 

A végfelhasználói eszközökön az Intune-ügyfél az Application Protection-szabályzatok Intune-panelén megadott egyszerű sztringegyezések alapján végezne műveleteket. Ez teljes mértékben az eszköz által jelentett értéktől függ. Ennek fényében a rendszergazának kell ügyelnie arra, hogy a kívánt viselkedés az elvártnak megfelelően működjön. Ezt úgy lehet elérni, ha teszteli a beállítást különböző eszközgyártókkal és -modellekkel egy kisebb felhasználói csoportban. A Microsoft Intune-ban válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget az alkalmazásvédelmi szabályzatok megtekintéséhez és hozzáadásához. További információ az alkalmazásvédelmi szabályzatok létrehozásáról: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Az alkalmazásvédelmi szabályzatok műveleteinek elérése <!-- 1483510 EEready -->
Hamarosan úgy konfigurálhatja az alkalmazásvédelmi szabályzatokat, hogy azokkal törölje, letiltsa vagy figyelmeztesse a nem megfelelő eszközöket. A legújabb művelet a *törlés*, amely eltávolítja a vállalati adatokat az eszközről. Törlés esetén az eszköz felhasználója értesítést kap a törlés okáról és a lehetséges szervizelési lépésekről. Egyes beállítások – például az operációs rendszer minimális verziója – esetén több műveletet is alkalmazhat, például letiltás és törlés. Ezek a műveletek az alkalmazás indításakor aktiválódnak.

<!-- 1804 start -->

### <a name="rules-for-removing-devices----1609459---"></a>Szabályok eszközeltávolításhoz <!-- 1609459 -->
Új szabályok lesznek elérhetők, melyekkel automatikusan eltávolíthatja azokat az eszközöket, amelyek nem jelentkeztek be az Ön által megadott számú napon keresztül. Az új szabály megtekintéséhez nyissa meg az **Intune** panelt, és válassza az **Eszközök**, majd az **Eszközeltávolítási szabályok** lehetőséget.

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
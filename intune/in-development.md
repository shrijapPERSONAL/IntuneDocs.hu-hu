---
title: A fejlesztés – Microsoft Intune
titlesuffix: ''
description: Fejlesztés a Microsoft Intune-funkciók
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e068e2c9834290b705e8e7bc2f895636415f9ba
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675442"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>A Microsoft Intune - április 2019 fejlesztés alatt

Segítség a készültségi és tervezési, ezen a lapon listák Intune felhasználói felület frissíti, és a szolgáltatásokat, fejlesztés alatt állnak, de még nem elérhető. Továbbá:

- Ha várhatóan tovább fogjuk, hogy intézkedjen módosítása előtt kell, tesszük közzé egy ingyenes Office-Üzenetközpontban post.
- Ha egy szolgáltatás vagy előzetes elindul, éles környezetben, vagy általánosan elérhető, a szolgáltatás leírása áthelyezi ezt oldal ki, majd onnan az [Újdonságok oldalát](whats-new.md).
- Ezen a lapon, és a [Újdonságok oldalát](whats-new.md) rendszeresen frissül. További hírekért látogasson vissza.
- Tekintse meg a [M365 ütemterv](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratégiai le és ütemterveket.

> [!Note]
> Ezek az elemek tükrözik a Microsoft jelenlegi verziójával kapcsolatos elvárások hamarosan egy későbbi kiadásban az Intune funkcióival kapcsolatos. Dátumok és az egyes szolgáltatások változhatnak. Nem minden eleme fejlesztési rendelkeznie a szolgáltatás ezen az oldalon.

**RSS-hírcsatorna**: Értesítés küldése, amikor ezen a lapon frissül, másolása és beillesztése a következő URL-címet a hírcsatorna olvasóba szerint: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Bejelentkezési beállítások megadásához és újraindítási beállítások macOS-eszközökön <!-- 1210083 -->
MacOS-eszközökön, létrehozhat egy eszközkonfigurációs profilt (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > Válasszon **macOS** tartozó platform > **eszközfunkciók** profiltípus). Új bejelentkezési ablak beállításokat fogja például egyéni fejléc bemutató cikkeket tartalmazzák, válassza ki, hogyan felhasználók jelentkezzen be, megjelenítése vagy elrejtése az energiaellátási beállításokat és egyéb.

A jelenlegi beállítások megtekintéséhez lépjen a [eszközfunkció-beállítások macOS](macos-device-features-settings.md).

A következőkre vonatkozik: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Speciális beállítások a Windows Defender-tűzfal <!-- 1311949 -->
Hamarosan fogja tudni az ügyfeleken a Windows Defender az egyéni tűzfalszabályok kezelése az Intune-nal. Bejövő és kimenő viselkedés, alkalmazások hálózati címek és portok a szabályok határozzák meg. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Alkalmazások védelme feltételes hozzáférés megkövetelése  <!--1634317 -->
Fogja tudni használni *megkövetelése alkalmazásvédelmi szabályzatának*, ami megerősíti, hogy a házirend bejelentkezési meg, hogy a felhasználók hozzáférését az adatok védelme a feltételes hozzáférés befejezése előtt a felhasználó alkalmazása vonatkozik. Miközben házirend garancia lelassíthatják az első használata élményt, azt úgy segít védekezni hálózati problémák, a felügyeleti konfigurációs hibák vagy a szándékos erőfeszítéseket támadók alkalmazásvédelmi szabályzatokat. 

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660---"></a>Online licenccel rendelkező Microsoft Store az üzleti alkalmazások telepítése <!-- 16726660 -->
Láthatja, hogy hozzárendeléséhez szükséges online licenccel rendelkező Microsoft Store for Business-alkalmazások az eszköz a környezetben. Központi telepítése a Microsoft Store for Business app így lehetővé teszi az alkalmazásnak, hogy az eszköz összes felhasználójához telepíthetők. Ez a tulajdonság csak a Windows 10 RS4 + asztali eszközökön alkalmazható. Az ügyfélalkalmazások hozzárendelés lapon találhat MSFB Online licencelt alkalmazások telepítésére, az eszköz a környezetben érhető el.

### <a name="include-and-exclude-mixture-of-user-groups-and-device-groups-when-assigning-policies-and-profiles----1807547---"></a>Belefoglalása vagy kizárása a felhasználói csoportokat és eszközcsoportokat tömbökből való hozzárendelésekor a házirendek és profilok <!-- 1807547 -->
Való hozzárendelésekor a megfelelőségi szabályzatok, vagy a konfigurációs profilokat, hozzárendelheti azokat a biztonsági csoportok a felhasználók vagy eszközök. Jelenleg közé tartozik, és csak a felhasználói csoportok kizárása *vagy* csak az eszköz csoportok belefoglalása vagy kizárása. Nem belefoglalása és kizárása vegyesen, mint például a felhasználói csoportok belefoglalása *és* eszközök csoport kizárása.

Fogja tudni belefoglalása vagy kizárása a felhasználói csoportokat és eszközcsoportokat. Megadhatja a felhasználók egy csoportjánál, és zárja ki az eszközök egy csoportját. Például hozzárendelése vagy eszközkonfigurációs profil üzembe helyezése a felhasználók egy csoportjára, de kizárja a személyes eszközök.

[Eszközkonfigurációs profilok hozzárendelése](device-profile-assign.md) tartalmaz további tájékoztatást a profilok hozzárendelése a felhasználói csoportokat és eszközcsoportokat.

A következőkre vonatkozik: Összes platform

### <a name="retire-noncompliant-devices----1827291---"></a>Nem megfelelő eszközök kivonása <!-- 1827291 -->
Adjon hozzá egy új megfelelőségi műveletet egy nem megfelelő eszköz kivonja fogunk. Egy nem megfelelő eszközt, az összes vállalati adat eltávolítása, és is eltávolítja az eszközt az Intune felügyelete alól. Ez a művelet fut, ha eléri a beállított értéke napokban megadva. A minimális érték 30 nap. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Kernel-bővítmények beállítások konfigurálása a macOS-eszközökön <!-- 2043024 -->
MacOS-eszközökön, létrehozhat egy eszközkonfigurációs profilt (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > Válasszon **macOS** tartozó platform). Új beállítások csoportja, konfigurálhatja és az eszközök kernel-bővítmények használata lehetővé teszi.

A következőkre vonatkozik: macOS 10.13.2 és újabb verziók

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Egyes képernyők kihagyásához során a beállítási asszisztens profil konfigurálása <!-- 2276470 -->
macOS-es regisztrációs profil létrehozásakor konfigurálhatja a profilt a következő képernyők bármelyikének kihagyására, amikor egy felhasználó a beállítási asszisztenst használja:
- Android-áttelepítés
- Hang megjelenítése
- Személyes adatok védelme
- Ha hozzon létre egy új profilt, vagy egy profil szerkesztése iCloudStorage, a kiválasztott hagyja ki képernyők kell szinkronizálni az Apple MDM-kiszolgáló. Így nem lesz késleltetés vesz fel a profil módosítása a felhasználók kiadhatnak az eszköz manuális szinkronizálása.
További információkért lásd: [a Készülékregisztrációs Program vagy az Apple School Manager macOS-eszközök automatikus regisztrálása](device-enrollment-program-enroll-macos.md).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Eszköz felhasználók megtekinthetik a már telepített vagy telepíteni próbált minden felügyelt alkalmazás <!-- 2352913 -->
A Windows céges portál felsorolja az összes felügyelt alkalmazások&ndash; egyszerre kötelező és elérhető&ndash; telepített a felhasználó eszközén. Felhasználók tudják próbált nézet és a függőben lévő alkalmazások telepítésére, és azok aktuális állapotát. Ha a szervezet nem, hogy az alkalmazások, kötelező vagy elérhető legyen, a felhasználók látják egy üzenet tájékoztatja, hogy nem vállalati alkalmazások telepítve vannak-e. Felhasználók is elérhetik a rendezését vagy szűrését alkalmazások telepítési állapot szerint.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Az Apple VPP-tokenek hatókörcímkék <!--2371886 -->
Az Apple VPP-tokenek hatókörcímkék adhat hozzá lesz. Csak az azonos címkéjű hatókörhöz hozzárendelt felhasználók hozzáférhet az adott címkével rendelkező Apple VPP-tokent. VPP-alkalmazások és e-könyv adott tokennel vásárolt öröklik a hatókörcímkék. Hatókörcímkék kapcsolatos további információkért lásd: [RBAC használata és a hatókör-címkéket](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Ha használja a "alkalmazhatósági szabályok" konfigurációs profilok létrehozása a Windows 10 rendszerű eszköz <!-- 2549910 -->
Windows 10-es eszközkonfigurációs profilok létrehozása (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10-es** tartozó platform). Is elérheti, hozzon létre egy **alkalmazhatósági szabály** , a profil csak egy adott kiadását vagy egy adott verzió érvényes. Például hozzon létre egy profilt, amely lehetővé teszi egy BitLocker-beállítások. Miután hozzáadta a profil, használjon egy alkalmazhatósági szabályt, hogy a profil csak Windows 10 Enterprise rendszert futtató eszközökre vonatkozik.

A következőkre vonatkozik: 
- Windows 10 és újabb

### <a name="enable-win32-app-dependencies----2617348---"></a>A Win32-alkalmazás függőségei engedélyezése <!-- 2617348 -->
Nyilvános előzetes verzió - rendszergazdaként, láthatja, hogy más alkalmazások telepíti a függőségeket a Win32-alkalmazás telepítése előtt kötelező. Pontosabban, az eszközön telepíteni kell a függő alkalmazás(ok) a Win32-alkalmazás telepítése előtt. Ez a funkció akkor lesz elérhető, csak azt követően az Intune felügyeleti ügynök frissítve lett 1904 verziót (1.18.120.0 nagyobb), amely 1 vagy 2 további hét után 1904, hogy frissítse a szolgáltatást is igénybe vehet. Válassza ki az Intune-ban **ügyfélalkalmazások** > **alkalmazások** > **Hozzáadás** megjelenítéséhez a **alkalmazás hozzáadása** panelen. Válassza ki **Windows-alkalmazás (Win32)** , a **alkalmazástípus**. További információkért lásd: [önálló Intune - Win32-Alkalmazáskezelés](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Új eszköz korlátozási beállítását Android Enterprise, az eszköz tulajdonosa: lehetővé teszik a felhasználók többalkalmazásos kioszk mód futtató dedikált Android Enterprise-eszközök Wi-Fi hálózatokhoz való kapcsolódásának <!--3041940 -->
A rendszergazdák tudják egy új beállítás, amely lehetővé teszi a felhasználóknak Bluetooth konfigurálása saját dedikált Android Enterprise eszközeiken futó többalkalmazásos kioszk mód bekapcsolására. Az Intune-konzolon ez a beállítás megtekintéséhez válassza ki **Intune** > **eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa, eszközkorlátozások** profiltípus > **beállításai**   >  **Dedikált eszközök** > Válasszon **többalkalmazásos** származó a **teljes képernyős mód** beállítás legördülő lista. Lehetőség nevű **Wi-Fi konfiguráció** lehetővé teszik a lesz. 

A következőkre vonatkozik: Android Enterprise dedikált futtató többalkalmazásos kioszk mód eszközökön. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Új eszköz korlátozási beállítását Android Enterprise, az eszköz tulajdonosa: megadása esetén a felhasználók a Bluetooth és a párosítást a dedikált vállalati Android-eszköz konfigurálása <!--3041941 -->
A rendszergazdák tudják egy új beállítás, amely lehetővé teszi a felhasználóknak Bluetooth konfigurálása saját dedikált Android Enterprise eszközeiken futó többalkalmazásos kioszk mód bekapcsolására. Az Intune-konzolon ez a beállítás megtekintéséhez válassza ki **Intune** > **eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa, eszközkorlátozások** profiltípus > **beállításai**   >  **Dedikált eszközök** > Válasszon **többalkalmazásos** származó a **teljes képernyős mód** beállítás legördülő lista. Lehetőség nevű **Bluetooth konfigurációs** lehetővé teszik a lesz. 

A következőkre vonatkozik: Android Enterprise dedikált futtató többalkalmazásos kioszk mód eszközökön. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>(Nyilvános előzetes verzió) alapvető biztonsági állapot figyelése <!-- 3082047 --> 
Ha nyomon, hogy a *Eszközállapot* számára a biztonsági előírások a nézet szervezi állapotát a referenciakonfiguráció kategóriák szerint, például *fent zárolási*, *BitLocker*, és  *Böngésző*. Az összes rendelkezésre álló alapvető kategória jelenik meg. Minden egyes kategóriánál láthatja, hány eszközt nem egyeznek meg az adott alapkonfiguráció kategóriát, helytelenül vannak konfigurálva, vagy nem vonatkoznak.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune-ban biztonsági műveletek a Defender ATP-ben (a nyilvános előzetes verzió) <!-- 3208597 -->
Hamarosan elérhető nyilvános előzetes verzió, az Intune hamarosan új biztonsági tevékenységek a újonnan bejelentett Microsoft Defender fenyegetések és biztonsági rések kezelése.  Ez az integráció biztonsági műveleteket a rendszergazdák a Windows Defender ATP (WDATP) hatékonyabban kommunikálhatnak a javasolt szervizelés újonnan felbukkanó fenyegetésekkel szemben, hogy az Intune-rendszergazdák számára. Biztonsági feladatokat is hozzáadja a kockázatalapú megközelítés felderíteni, rangsorolására és végponti biztonsági rések és konfigurációs hibáinak javítása.

Az Intune-ban biztonsági feladatokkal kapcsolatos további információkért tekintse meg a következő blogbejegyzésben: kapcsolatos [Microsoft Defender ATP fenyegetések és biztonsági rések kezelése Intune-ban biztonsági műveletek segítségével](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Létrehozhat és használhat OEMConfig eszközkonfigurációs profilok az Intune-ban <!-- 3305883 -->
Az Intune támogatni fogja a OEMConfig konfigurálása vállalati Android-eszköz. Pontosabban a hozhat létre eszközkonfigurációs profil, és beállítások alkalmazása az OEMConfig használatával vállalati Android-eszköz (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android enterprise** tartozó platform).

OEM-ek támogatása jelenleg-OEM alapon. Ha azt szeretné, OEMConfig alkalmazás nem érhető el OEMConfig alkalmazások listájában, lépjen kapcsolatba `IntuneOEMConfig@microsoft.com`.

A következőkre vonatkozik: 
- Android enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Új eszközkorlátozásokra vonatkozó beállítások az Android Enterprise, az eszköz tulajdonosa <!-- 3574254 -->
A vállalati Android-eszköz engedélyezi vagy korlátozza a funkciókat, jelszószabályok beállítása és egyéb egy eszközkorlátozási profilt hozhat létre (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa > eszközkorlátozások** profiltípus). 

Új beállításokat, beleértve a jelszó-beállításokat, így teljes hozzáférést a Google Play Store apps teljes körűen felügyelt eszközök esetében, és további elérhető lesz. 

Beállítások aktuális listájának megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md). 

A következőkre vonatkozik: Android Enterprise teljes körűen felügyelt eszközök

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>A Windows 10-es eszközök megfelelőségi szabályzatot a TPM lapkakészlet-ellenőrzés <!-- 3617671 -->
Számos Windows 10-es és újabb rendszerű eszközök kell a platformmegbízhatósági modul (TPM) chipkészletekkel. Egy új megfelelőségi beállítás ellenőrzi egy TPM-e az eszközön.

[Windows 10-es és újabb megfelelőségi szabályzat beállításai](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) aktuális beállításokat sorolja fel.

A következőkre vonatkozik: 
- Windows 10 és újabb

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Az Intune-ban regisztrált telepítendő Win32-alkalmazások konfigurálása az Azure AD-hez csatlakoztatott eszközök <!-- 3695227 -->
Is elérheti, hogy rendelje hozzá a Win32-alkalmazások Intune telepíthető legyen regisztrálva az Azure AD-hez csatlakoztatott eszközök. Win32-alkalmazások az Intune-ban kapcsolatos további információkért lásd: [Win32-Alkalmazáskezelés](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>A Windows Defender komplex veszélyforrások elleni védelem alapkonfiguráció <!-- 3754134 -->
Fogunk hozzáadni az új alaptervet úgy, hogy a Windows Defender komplex veszélyforrások elleni védelem beállításainak konfigurálásához nyújtanak segítséget.

### <a name="device-overview-shows-primary-user---794259---"></a>Eszköz áttekintése látható elsődleges felhasználó <!--794259 -->
Az eszköz áttekintése lapon jelennek meg az elsődleges felhasználója, a felhasználói eszköz affinitási felhasználói (UDA) is nevezik. Az eszköz elsődleges felhasználója megtekintéséhez válassza ki **Intune** > **eszközök** > **minden eszköz** > Válasszon egy eszközt. Az elsődleges felhasználó tetején fog megjelenni a **áttekintése** lapot.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Teljes körűen felügyelt Android Enterprise-eszközök bővített támogatása <!-- 3903241, 3903244, 3903246 -->
Bontsa ki a teljes körűen felügyelt Android Enterprise-eszközök támogatását fogunk ([bejelentése a január, 2019](whats-new.md#week-of-january-14-2019) , többek között az alábbiak:
- Megfelelőség
- Feltételes hozzáférés
- Új felhasználói alkalmazás

Beállítása az Android teljes körűen felügyelt eszközök, ugorjon a **eszközregisztráció** > **Android-eszközök regisztrálási** > **vállalat által birtokolt, teljes körűen felügyelt felhasználói eszközök**. Teljes körűen felügyelt Android-eszközök továbbra is előzetes verzióban érhető el támogatás, és bizonyos Intune-funkciók nem teljesen működőképes. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Jelentéskészítés a vállalati Android munkahelyi profilos eszközök további felügyelt Google Play alkalmazás <!-- 4105925 -->
A felügyelt Google Play alkalmazások telepített vállalati Android munkahelyi profilos eszközök esetén lesz megtekinthetők az alkalmazás az eszközön telepített adott verziószáma. Ez csak a szükséges alkalmazások vonatkozik. A rendelkezésre álló alkalmazások ugyanazokat a funkciókat az egy későbbi kiadásban engedélyezve lesz.

### <a name="ios-third-party-keyboards----4111843---"></a>iOS harmadik féltől származó billentyűzetek <!-- 4111843 -->
Az Intune alkalmazásvédelmi szabályzat (alkalmazás) támogatása a **harmadik féltől származó billentyűzetek** beállítás miatt az iOS platform megváltoztatására megszűnik. Nem tudnak konfigurálja ezt a beállítást az Intune felügyeleti konzolon, és nem kényszeríti az Intune App SDK az ügyfélen.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>A felhasználók a Windows-frissítések keresése <!-- 3316758 -->
Adunk hozzá egy új Windows frissítési kör beállítás, amely segítségével megakadályozhatja a felhasználók Windows-frissítések keresése. Ez a beállítás nem lesz elérhető a portálon, de konfigurálható az Intune Graph API használatával.

### <a name="windows-update-notifications----3316782---"></a>Windows-frissítési értesítések <!-- 3316782 -->
Azt adja hozzá támogatást a Windows Update kör konfigurációk úgy is elérheti a felhasználók a Windows Update-értesítések beállítása. Ez a beállítás nem lesz elérhető a portálon, de konfigurálható az Intune Graph API használatával.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Céges portál iOS 12-eszközök felhasználói regisztrációjának módosításai <!--3448635 --> 
IOS-hez készült céges portál fog frissülni, az alkalmazás regisztrációs képernyők és a lépéseket, amelyek a mobileszköz-kezelési regisztrációs módosításokat jelent meg az Apple iOS 12.2 összhangban vannak. A frissített munkafolyamatot most fogja kérni a felhasználók számára:

- Nyissa meg a céges portál webhelyet (keresztül a Safari esetében), és a felügyeleti profil letöltéséhez a vállalati portál alkalmazásba való visszatérés előtt Safari engedélyezése.
- Nyissa meg a beállítási alkalmazást a felügyeleti profil telepítésére az eszközükön.
- Térjen vissza a céges portál alkalmazás regisztráció elvégzését.

Hogyan készítheti elő a módosítások kapcsolatos további információkért lásd: a [a Microsoft technikai Közösség post](https://aka.ms/CP_changes_iOS12). Addig is támogatásához új iOS-regisztrációk vállalati portálon, hogy frissítettük lépéseit [iOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/en-us/intune/ios-enroll). Doc módosítások után az Apple iOS-verziót 12.2 kiadások lesz élő. 

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Könnyebb elérhetőség érdekében a diagnosztikai beállítások <!-- 3804627 -->
Adunk hozzá egy új lehetőség a **Auditnaplók** minden napló számítási az Intune-konzolon, amellyel közvetlenül nyissa meg a panelen a *diagnosztikai beállítások* lap.

## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



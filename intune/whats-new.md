---
title: Újdonságok a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Az Azure-beli Intune-portál újdonságai
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc6b8f90a261325afe7d7ee97bab99dbbd09c095
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374072"
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Ugyanitt találhat [jövőbeni változtatásokról](in-development.md), [fontos bejelentésekről](#notices), és információkat [korábbi verziókról](whats-new-archive.md). 

> [!Note]
> Egyes funkciók bevezetése több hetet igénybe vehet, így előfordulhat, hogy nem elérhetők a felhasználók számára az első héten.

**RSS-hírcsatorna**: Értesítés küldése, amikor ezen a lapon frissül, másolása és beillesztése a következő URL-címet a hírcsatorna olvasóba szerint: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-may-20-2019"></a>2019. május 20 hete 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="windows-company-portal-app----3316993---"></a>Windowsos Munkahelyi portál alkalmazás <!-- 3316993 -->
A Windows céges portál alkalmazás már egy új lap feliratú **eszközök**. A **eszközök** lapon megjelenik a végfelhasználók számára az összes regisztrált eszközökön. Felhasználók jelenik meg ez a változás a vállalati portálon 10.3.4291.0 verzióját használják, és később. A vállalati portál konfigurálásával kapcsolatos további információkért lásd: [a Microsoft Intune vállalati portál alkalmazás konfigurálása](company-portal-app.md).

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Az autopilot eszköz OrderID attribútum neve módosult csoporthoz címke <!-- 4659453 -->

Intuitívabb, ellenőrizze, hogy a **OrderID** értékre változott az Autopilot-eszközök attribútumnév **csoporthoz címke**. Autopilot-eszközadatok a feltöltendő CSV-k használatakor, az oszlop fejlécére, nem OrderID csoporthoz címke kell használnia.  

## <a name="week-of-may-13-2019"></a>2019. május 13 hete 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359-idready-wnready--"></a>Intune-házirendek frissítése a hitelesítési módszert, és a vállalati portál alkalmazás telepítése  <!-- 1927359 idready wnready-->
A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök, az Intune már nem támogatja a vállalati portál manuális telepítés a végfelhasználók az app store áruházból. Ez a változás csak akkor jelentősége, amikor Ön az Apple beállítási asszisztens regisztráció során hitelesítsék magukat. Ez a változás csak is hatással van a regisztrált iOS-eszközöket:  
* Az Apple configuratorral

* Apple üzleti vezető

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Ha a felhasználók a vállalati portál alkalmazást az App store áruházból telepítik, és próbálja meg, ezek eszközöket regisztrálni, akkor egy hibaüzenetet fog kapni. Ezek az eszközök csak akkor használja a vállalati portálon, ha azt a leküldött, automatikusan, az Intune-regisztráció során is várhatók. Regisztrációs profilok az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Ha azt szeretné, hogy a DEP-eszközök felhasználói szeretné, hogy a vállalati portálon, szüksége lesz a beállítások megadása egy regisztrációs profilt. 

Emellett a **az eszköz azonosítására** képernyőn, az IOS-es céges portál eltávolítása folyamatban van. Ezért rendszergazdák, akik számára szeretne feltételes hozzáférésének engedélyezésére vagy a vállalati alkalmazások telepítése a DEP-regisztrációs profilt kell frissíteni. Ez a követelmény csak akkor érvényes, ha a DEP-regisztráció a beállítási Asszisztenssel van hitelesítve. Ebben az esetben kell küldenie az eszközön a céges portálon. Ehhez válassza ki a **Intune** > **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs program jogkivonatok** > Válasszon egy tokent > **profilok** > Válasszon egy profilt > **tulajdonságok** > beállítása **céges portál telepítése** való **Igen**.

A már regisztrált DEP-eszközökön a vállalati portál telepítéséhez kell Intune-ban lépjen > ügyfélalkalmazások, és küldje le az alkalmazás-konfigurációs házirendek segítségével felügyelt alkalmazásként. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>A sor üzleti (LOB) alkalmazásokat egy alkalmazásvédelmi szabályzatot használó frissítsenek hogyan konfigurálása <!-- 3568384 -->
Most már beállíthatja a végfelhasználói honnan be egy üzletági (LOB) alkalmazás frissített verzióját. Végfelhasználók akkor látják ezt a szolgáltatást a **minimális Alkalmazásverzió** feltételes indítási párbeszédpanel, amely kérni fogja a végfelhasználók számára, hogy a LOB-alkalmazás minimális verziójára frissíteni. Meg kell adnia a részletes frissítési az ÜZLETÁGI alkalmazásvédelmi szabályzat (alkalmazás) részeként. Ez a funkció iOS és Android rendszeren érhető el. IOS-eszközökön, a szolgáltatás használatához az alkalmazásnak, hogy a rendszer integrált (vagy burkolása az alkalmazásburkoló eszköz használatával), az Intune SDK for iOS v. 10.0.7 vagy újabb. Ez a szolgáltatás megköveteli az Android, a legújabb vállalati portál. Konfigurálása, hogy a felhasználó frissíti a LOB-alkalmazás, az alkalmazásnak szüksége van egy felügyelt alkalmazás konfigurációs szabályzatát a kulcsot a neki küldött `com.microsoft.intune.myappstore`. Az elküldött értékkel fogja meghatározni, melyik tár a végfelhasználó tölti le az alkalmazásból. Ha a vállalati portálról telepítik az alkalmazást, az értéknek kell lennie `CompanyPortal`. Más tárolására meg kell adni egy teljes URL-CÍMÉT.

#### <a name="intune-management-extension-powershell-scripts-----3734186-idready---"></a>Az Intune felügyeleti bővítmény PowerShell-parancsprogramok  <!-- 3734186 idready -->
Konfigurálhatja a PowerShell-parancsfájlok futtatásához a felhasználó rendszergazdai jogosultságokat az eszközön. További információkért lásd: [használja a Powershellt parancsfájlokat az Intune-ban Windows 10 rendszerű eszközökön](intune-management-extension.md) és [Win32-Alkalmazáskezelés](apps-win32-app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Androidos vállalati Alkalmazáskezelés <!-- 4459905 -->
Hogy egyszerűbb legyen a rendszergazdák beállítása és használata az Android Enterprise management, az Intune automatikusan új négy gyakori Android Enterprise kapcsolódó alkalmazásokat az Intune felügyeleti konzolon. A négy Android Enterprise-alkalmazások a következők:

- **[A Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – teljes körűen felügyelt Android Enterprise-forgatókönyvek esetén használatos.
- **[A Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  -segít, jelentkezzen be a fiókok kétfaktoros ellenőrzési használatakor.
- **[Az Intune céges portál](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  – alkalmazás alkalmazásvédelmi szabályzatokat (alkalmazás) és az Android Enterprise munkahelyi profil helyzetekben használatos.
- [Kezdőlap képernyő felügyelt](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – Android Enterprise dedikált/kioszk esetekben használatos.

Korábban a rendszergazdáknak kell manuálisan található, és hagyja jóvá a ezeket az alkalmazásokat a [felügyelt Google Play áruház](https://play.google.com/store/apps) beállítása. Ez a változás eltávolítja azokat korábban manuális lépései könnyebben és gyorsabban az ügyfelek számára az Android Enterprise management használatához.

Rendszergazdák akkor láthatnak, ezeket az automatikusan hozzáadódik az Intune-alkalmazások listájában, hogy először csatlakoznak az Intune-bérlő a felügyelt Google Play időben négy alkalmazásokat. További információkért lásd: [Intune-fiókjához csatlakozhat a felügyelt Google Play fiókjához](connect-intune-android-enterprise.md). A bérlők számára, amely már csatlakoztatva van a bérlő vagy akik már használják Android Enterprise nincs teendője rendszergazdák tennie. Ezeket az alkalmazásokat négy automatikusan megjelenik a 2019. május szolgáltatás bevezetés befejezése után 7 napon belül.

### <a name="device-configuration"></a>Eszközök konfigurálása

####  <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Intune-ban biztonsági műveletek a Defender ATP-ben (a nyilvános előzetes verzió)     <!-- 3208597 -->
Nyilvános előzetes verzióban elérhető az Intune segítségével biztonsági feladatok kezelése a Microsoft Defender komplex veszélyforrások elleni védelem (ATP). Ez az integráció az ATP, és hozzáadja a kockázatalapú megközelítés felderíteni, rangsorolására és végponti biztonsági réseket és a konfigurációs hibák, javíthatja a felderítést, hogy a megoldás közötti idő csökkentése mellett.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>A Windows 10-es eszközök megfelelőségi szabályzatot a TPM lapkakészlet-ellenőrzés <!-- 3617671   idstaged-->
Számos Windows 10-es és újabb rendszerű eszközök kell a platformmegbízhatósági modul (TPM) chipkészletekkel. A frissítés egy új megfelelőségi beállítás, amely ellenőrzi a TPM lapka az eszközön lévő verziója tartalmazza. 

[Windows 10-es és újabb megfelelőségi szabályzat beállításai](compliance-policy-create-windows.md#device-security) ismerteti ezt a beállítást.

Érintett kiadások: Windows 10 és újabb

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Megakadályozza, hogy a végfelhasználók számára a személyes elérési pont módosítása és Siri kiszolgáló bejelentkezés IOS-es eszközök letiltása <!-- 4097904   --> 
Létrehozhat egy eszközkorlátozási profilt az iOS-eszközön (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus). A frissítés konfigurálható új beállításokat tartalmazza:

- **Beépített alkalmazások**: Siri parancsok kiszolgálóoldali naplózása
- **Vezeték nélküli**: Személyes elérési pont (csak felügyelt) felhasználói módosítása

Ezek a beállítások megtekintéséhez, keresse fel a [beépített alkalmazás beállításai IOS-re](device-restrictions-ios.md#built-in-apps) és [vezeték nélküli beállításai iOS-es](device-restrictions-ios.md#wireless).

A következőkre vonatkozik: iOS 12.2 és újabb

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Új tanterem alkalmazás eszközkorlátozásokra vonatkozó beállításai macOS-eszközök <!-- 4097905   --> 
Akkor is eszközkonfigurációs profilok létrehozása macOS-eszközök esetén (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **macOS** tartozó platform > **eszközkorlátozások** profiltípus). A frissítés tartalmazza az új osztályterem alkalmazás beállításai, a képernyőfelvételek letiltására, és a lehetőség az iCloud-Fotókönyvtár letiltása.

A jelenlegi beállítások megtekintéséhez lépjen a [engedélyezett vagy korlátozott funkciók az Intune-nal macOS beállításai](device-restrictions-macos.md).

A következőkre vonatkozik: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>A rendszer átnevezi az iOS app store beállítás elérésére szolgáló jelszó<!-- 4557891  -->
A **alkalmazásáruház elérésére szolgáló jelszó** beállítás új neve **jelszó iTunes Store megkövetelése minden vásárláshoz** (**eszközkonfiguráció**  >  **Profilok** > **profil létrehozása** > **iOS** tartozó platform > **eszközkorlátozások** számára Profil típusa > **App store, dokumentumok megtekintése, és a játékok**).

Az elérhető beállítások megtekintéséhez lépjen a [App Store, dokumentumok megtekintése, játékok IOS-eszközök beállításai](device-restrictions-ios.md#app-store-doc-viewing-gaming).

A következőre vonatkozik: iOS

####  <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>A Microsoft Defender komplex veszélyforrások elleni védelem baseline (előzetes verzió)  <!--  3754134 -->
Hozzáadtunk egy biztonsági alaptervet előzetes a [Microsoft Defender komplex veszélyforrások elleni védelem](security-baseline-settings-defender-atp.md) beállításait. Ez a alapvető érhető el, ha a környezet megfelel-e használatára vonatkozó Előfeltételek [Microsoft Defender komplex veszélyforrások elleni védelem](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Windows regisztrációs állapot oldal (ESP) már általánosan elérhető <!-- 3605348 -->
A regisztrálási állapot oldal már verziója. További információkért lásd: [beállítása egy regisztrálási állapot oldal](windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Az Intune felhasználói felület frissítés - Autopilot beléptetési profil létrehozása  <!-- 4593669 -->
A felhasználói felület az Autopilot-beléptetési profil létrehozása az Azure felhasználói felület stílusok igazodva frissítve lett. További információ: [Autopilot beléptetési profil létrehozása](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile). Halad előre, további Intune forgatókönyvek frissülni fognak az új felhasználói felület stílusát.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Engedélyezze az Autopilot alaphelyzetbe állítása az összes Windows-eszköz <!-- 4225665 -->
Az autopilot alaphelyzetbe állítása most már működik minden Windows-eszközökhöz, azokat is, a regisztrálási állapot oldal használatára konfigurálva. Ha az eszköz egy regisztrálási állapot oldal eszközök kezdeti regisztrációja során nem lett konfigurálva, az eszköz fog egyenesen eljuthat a desktopban bejelentkezést követően. Igénybe vehet nyolc órát szinkronizálása és jelennek meg a megfelelő Intune-ban. További információkért lásd: [eszközök alaphelyzetbe állítása a távoli Windows Autopilot visszaállítással](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Nem kötelező, ha a Keresés az összes eszköz IMEI formátummal <!--30407680 -->
Nem kell IMEI-számokat tartalmaz szóközöket keresés **minden eszköz**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Törölhetne egy eszközt az Apple portálján megjelennek az Intune-portálon <!--2489996 -->
Ha egy eszközt az Apple Device Enrollment Program vagy az Apple üzleti Manager portálok törölnek, az eszköz automatikusan törölve lesz, az Intune-ból a következő szinkronizáláskor.


### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>A titkosítási jelentés kívül esik a nyilvános előzetes verzió   <!-- 4587546      -->
A [jelentés a BitLocker és az eszköz titkosítása](encryption-monitor.md) már általánosan elérhető, és a nyilvános előzetes verziója már nem része. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Outlook-aláírás és a biometriai beállítások az iOS és Android-eszközök <!-- 4050557 -->
Mostantól megadhatja, hogy engedélyezve van-e az alapértelmezett aláírást az Outlook iOS és Android rendszerű eszközökön. Emellett kiválaszthatja, hogy a felhasználók az IOS Outlook biometrikus beállításának módosításához.

## <a name="week-of-may-6-2019"></a>2019. május 6 hete 

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Hálózati hozzáférés-vezérlés (NAC) támogatása iOS-eszközökhöz készült F5 hozzáférés <!-- 4500808 -->

F5 BIG-IP 13, amely lehetővé teszi a NAC-funkciók F5 hozzáférés az Intune-ban iOS-en frissítést adott ki. Ez a funkció használatához:

- BIG-IP Update 13.1.1.5 való frissítéséhez. BIG-IP-14 nem támogatott.
- BIG-IP integrálása az Intune-nal a NAC. Lépések [áttekintése: APM konfigurálása az eszköz állapotát ellenőrzi a végpont felügyeleti rendszerekkel](https://support.f5.com/kb/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
- Ellenőrizze a **engedélyezése hálózati hozzáférést vezérlő (NAC)** beállítása az Intune-ban a VPN-profil.

A rendelkezésre álló beállítás megtekintéséhez, keresse fel a [konfigurálása VPN-beállítások iOS-eszközökön](vpn-settings-ios.md).

A következőre vonatkozik: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Frissített PFX-Tanúsítványösszekötő a Microsoft Intune-ban <!-- doc-vso 1521237  -->  
Kibocsátottunk egy frissítést a [PFX-Tanúsítványösszekötő a Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors) , csökken a lekérdezési időköz 5 perccel 30 másodperc.

## <a name="week-of-april-22-2019"></a>2019 április 22 hete

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Értékelések a Microsoft Intune-hoz létre megfelelőségi Manager használatával<!-- 4404750 -->

[Megfelelőségi Manager](https://servicetrust.microsoft.com/ComplianceManager) (megnyílik egy másik Microsoft-webhely) van egy munkafolyamat-alapú kockázati frissítésfelmérő eszközt a Microsoft Szolgáltatásmegbízhatósági portált. Ezáltal nyomon követésére, hozzárendelése és ellenőrzése a kapcsolódó Microsoft-szolgáltatások a szervezet a jogszabályoknak való megfelelőség tevékenységek. Az Office 365, Azure, Dynamics, szolgáltatások és az Intune hozhat létre a saját megfelelőségi vizsgálata. Az Intune két értékelésekkel rendelkezik érhető el – FFIEC és az általános adatvédelmi rendelet.

Összpontosítsa figyelmét részletes vezérlők - vezérlőkkel Microsoft által felügyelt és a szervezet által felügyelt Compliance Manager segítségével. Végezze el az értékeléseket, és ezután exportálhatja, és nyomtassa ki az értékelések.

[Szövetségi pénzügyi intézmények vizsgálat Tanács (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (megnyílik egy másik Microsoft-webhely) megfelelőségi egy olyan online banki FFIEC által kiadott szabványainak. Érdemes a leginkább kért értékelését pénzügyi intézmények, amely az Intune-nal. Hogyan segíti az Intune FFIEC kiberbiztonsági irányelvek kapcsolódó nyilvános felhőalapú számítási feladatokhoz megfelelő értelmezi azt. Az Intune FFIEC értékelése a második FFIEC Compliance Manager assessment.

A következő példában láthatja a bontás FFIEC vezérlők. A Microsoft 64 vezérlők ismerteti. Ön felelős a fennmaradó 12 szabályozza.

![Tekintse meg a minta az Intune-értékelés FFIEC, beleértve a felhasználói műveletek és a Microsoft-műveletek](./media/intune-ffiec-assessment-status.png)

[Általános adatvédelmi rendelet (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (megnyílik egy másik Microsoft-webhely) egy Európai Unión (EU) törvény, amely segít megvédeni a jogosultságokat az egyének és adataikat. Általános adatvédelmi rendelet a leginkább kért assessment érdekében, hogy megfeleljenek adatvédelmi szabályzat. 

A következő példában láthatja az általános adatvédelmi rendelet vezérlők bontásához. A Microsoft 49 vezérlők ismerteti. Ön felelős a fennmaradó 66 szabályozza.

![Tekintse meg a minta az Intune-értékelés GDPR, beleértve a felhasználói műveletek és a Microsoft-műveletek](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>2019. április 15 i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>OpenSSL titkosítási Androidos alkalmazásvédelmi szabályzatok <!-- 3747362 -->
Az Intune alkalmazásvédelmi szabályzatai (alkalmazás) Android-eszközökön az OpenSSL titkosítási tárba, amely érvényes a FIPS 140-2 szabványnak megfelelő használja. További információkért lásd: a [titkosítási](app-protection-policy-settings-android.md#encryption) szakaszában [Androidos alkalmazásvédelmi szabályzat beállításai a Microsoft Intune-ban](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>A Win32-alkalmazás függőségei engedélyezése <!-- 2617348  -->
Mint a rendszergazda megkövetelheti, hogy más alkalmazások telepíti a függőségeket a Win32-alkalmazás telepítése előtt. Pontosabban, az eszközön telepíteni kell a függő alkalmazás(ok) a Win32-alkalmazás telepítése előtt. Válassza ki az Intune-ban **ügyfélalkalmazások** > **alkalmazások** > **Hozzáadás** megjelenítéséhez a **alkalmazás hozzáadása** panelen. Válassza ki **Windows-alkalmazás (Win32)** , a **alkalmazástípus**. Miután hozzáadta az alkalmazást, kijelölheti **függőségek** és a függő alkalmazásokat, a Win32-alkalmazás telepítése előtt telepíteni kell. További információkért lásd: [önálló Intune - Win32-Alkalmazáskezelés](apps-win32-app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Alkalmazás verziója telepítéséhez szükséges információkat a Microsoft Store üzleti alkalmazások <!-- 3537391   -->
Alkalmazás telepítési jelentések az üzleti alkalmazások Microsoft Store-alkalmazás verziója adatai tartalmazzák. Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások**. Válassza ki a **Microsoft Store for Business app** , majd **eszköz telepítési állapota** alatt a **figyelő** szakaszban.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>A Win32-alkalmazások követelményszabályok bővítése <!-- 3676883   -->
Követelmény szabályai alapján a PowerShell parancsfájlok, a beállításjegyzék-értékek és a fájl rendszer-információkat is létrehozhat. Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > **Hozzáadás**. Válassza ki **Windows-alkalmazás (Win32)** , a **alkalmazástípus** a a **alkalmazás hozzáadása** panelen.  Válassza ki **követelmények** > **Hozzáadás** konfigurálása további követelmény-szabályokkal. Ezt követően válassza **Fájltípus**, **beállításjegyzék**, vagy **parancsfájl** , a **követelmény típusa**. További információkért lásd: [Win32-Alkalmazáskezelés](apps-win32-app-management.md).

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Az Intune-ban regisztrált telepítendő Win32-alkalmazások konfigurálása az Azure AD-hez csatlakoztatott eszközök <!-- 3695227  -->
A Win32-alkalmazások Intune-ban regisztrált telepítendő rendelhet az Azure AD-hez csatlakoztatott eszközök. Win32-alkalmazások az Intune-ban kapcsolatos további információkért lásd: [Win32-Alkalmazáskezelés](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---794259----"></a>Eszköz áttekintése látható elsődleges felhasználó <!--794259  -->
Az eszköz áttekintése lapon jelennek meg az elsődleges felhasználója, a felhasználói eszköz affinitási felhasználói (UDA) is nevezik. Az eszköz elsődleges felhasználója megtekintéséhez válassza ki **Intune** > **eszközök** > **minden eszköz** > Válasszon egy eszközt. Az elsődleges felhasználó tetején fog megjelenni a **áttekintése** lapot.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Jelentéskészítés a vállalati Android munkahelyi profilos eszközök további felügyelt Google Play alkalmazás <!-- 4105925  -->
A telepített vállalati Android munkahelyi profilos eszközök felügyelt Google Play alkalmazások megtekintheti az alkalmazást az eszközön telepített adott verziószáma. Ez csak a szükséges alkalmazások vonatkozik. A rendelkezésre álló alkalmazások ugyanazokat a funkciókat az egy későbbi kiadásban engedélyezve lesz. 

#### <a name="ios-third-party-keyboards----4111843-----"></a>iOS harmadik féltől származó billentyűzetek <!-- 4111843   -->
Az Intune app protection szabályzat (alkalmazás) támogatása a **harmadik féltől származó billentyűzetek** beállítása iOS-iOS platform módosítása miatt már nem támogatott. Nem tudnak konfigurálja ezt a beállítást az Intune felügyeleti konzolon, és nem kényszeríti az Intune App SDK az ügyfélen.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Bejelentkezési beállítások megadásához és újraindítási beállítások macOS-eszközökön <!-- 1210083  -->
MacOS-eszközökön, létrehozhat egy eszközkonfigurációs profilt (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > Válasszon **macOS** tartozó platform > **eszközfunkciók** profiltípus). Ez a frissítés magában foglalja az új bejelentkezési ablak beállításait, például egy egyéni szalagcím látható, válassza ki, hogyan felhasználók jelentkezzen be, megjelenítése vagy elrejtése az energiaellátási beállításokat és egyéb.

Ezek a beállítások megtekintéséhez, keresse fel a [eszközfunkció-beállítások macOS](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Többalkalmazásos kioszk módban futó eszköz tulajdonosa dedikált eszközök konfigurálása Wi-Fi Android Enterprise <!--3041940  -->
Beállítások az Android Enterprise, az eszköz tulajdonosa többalkalmazásos kioszk módban dedikált eszközként futtatásakor engedélyezheti. Ebben a frissítésben engedélyezheti a felhasználóknak való beállítása és csatlakozása a Wi-Fi-hálózatokhoz (**Intune** > **eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa, eszközkorlátozások** profiltípus >  **Dedikált eszközök** > **teljes képernyős mód**: **Multi-App** > **Wi-Fi konfigurációs**). 

Az összes, a konfigurálható beállítások megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md).

Érintett kiadások: A többalkalmazásos kioszk mód androidos dedikált vállalati eszközökön


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>A Bluetooth és az Android Enterprise, az eszköz tulajdonosa párosítás többalkalmazásos kioszk módban futó dedikált eszközök konfigurálása <!-- 3041941  -->
Beállítások az Android Enterprise, az eszköz tulajdonosa többalkalmazásos kioszk módban dedikált eszközként futtatásakor engedélyezheti. Ez a frissítés lehetővé teszi a végfelhasználók számára, hogy a Bluetooth engedélyezése, és párosítsa az eszközöket a Bluetooth-on keresztül (**Intune** > **eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa, eszközkorlátozások** profil típus > **dedikált eszközök** > **teljes képernyős mód**: **Multi-App** > **Bluetooth konfigurációs**). 

Az összes, a konfigurálható beállítások megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md).

Érintett kiadások: A többalkalmazásos kioszk mód androidos dedikált vállalati eszközökön

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Létrehozhat és használhat OEMConfig eszközkonfigurációs profilok az Intune-ban <!-- 3305883  -->
Ebben a frissítésben az Intune támogatja az OEMConfig konfigurálása vállalati Android-eszköz. Pontosabban a hozhat létre eszközkonfigurációs profil, és beállítások alkalmazása az OEMConfig használatával vállalati Android-eszköz (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android enterprise** tartozó platform).

OEM-ek támogatása jelenleg-OEM alapon. Ha azt szeretné, OEMConfig alkalmazás nem érhető el OEMConfig alkalmazások listájában, lépjen kapcsolatba `IntuneOEMConfig@microsoft.com`.

Ez a funkció kapcsolatos további információkért lépjen a [használata és kezelése az Android Enterprise-eszközök Microsoft Intune-ban OEMConfig](android-oem-configuration-overview.md).

Érintett kiadások: Android enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Windows-frissítési értesítések  <!-- 3316758, 3316782  -->
Két hozzáadtunk *a felhasználói élmény beállításainak* a Windows Update csörögni konfigurációk, amelyek az Intune-konzolról kezelheti. Mostantól:
- Letiltása vagy engedélyezése a felhasználóknak [-Windows-frissítéseket keresni](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Kezelheti a [Windows-frissítési értesítés szintjét](windows-update-settings.md#windows-update-notification-level) , hogy a felhasználók láthatják.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Új eszközkorlátozásokra vonatkozó beállítások az Android Enterprise, az eszköz tulajdonosa <!-- 3574254  -->
A vállalati Android-eszköz engedélyezi vagy korlátozza a funkciókat, jelszószabályok beállítása és egyéb egy eszközkorlátozási profilt hozhat létre (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **Android Enterprise** tartozó platform > **csak az eszköz tulajdonosa > eszközkorlátozások** profiltípus). 

Ez a frissítés magában foglalja az új jelszó-beállításokat, lehetővé teszi, hogy a teljes körűen felügyelt eszközök és más alkalmazásokat a Google Play Store teljes hozzáférést. Beállítások aktuális listájának megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md). 

Érintett kiadások: Android Enterprise teljes körűen felügyelt eszközök

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>A Windows 10-es eszközök megfelelőségi szabályzatot a TPM lapkakészlet-ellenőrzés <!-- 3617671 -->

Ez a funkció késik, és szerepelnie kell egy későbbi kiadásban.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>A Windows 10 és újabb rendszerű eszközökön a Microsoft Edge böngésző frissített felhasználói Felületet módosítása <!-- 3775833   -->
Eszközkonfigurációs profil létrehozásakor engedélyezése vagy korlátozása a Microsoft Edge-funkciók a Windows 10-es és újabb rendszerű eszközök (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Windows 10 és újabb** platformon > **eszközkorlátozások** profiltípus >  **A Microsoft Edge böngésző**). Ez a frissítés a Microsoft Edge-beállítások: a kifejezőbb és megérteni. 

Ezek a szolgáltatások megtekintéséhez, keresse fel a [eszközkorlátozásokra vonatkozó beállításai a Microsoft Edge böngésző](device-restrictions-windows-10.md#microsoft-edge-browser).

Érintett kiadások: Windows 10 és újabb

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Kibővített támogatás Android Enterprise teljes körűen felügyelt eszközök (előzetes verzió)  <!--   3903241, 3903244, 3903246   -->
A nyilvános előzetes verzióként kiterjesztettük a támogatást a teljes körűen felügyelt Android Enterprise-eszközök ([bejelentése a január, 2019](whats-new.md#week-of-january-14-2019) , többek között az alábbiak: 

- Teljes körűen felügyelt, dedikált eszközök hozhat létre [megfelelőségi szabályzatok](compliance-policy-create-android-for-work.md) jelszavakra vonatkozó szabályokat és operációs rendszerre vonatkozó követelmények (**eszközmegfelelőség**  >   **Házirendek** > **szabályzat létrehozása** > **Android Enterprise** tartozó platform > **eszköz tulajdonosa** számára Profil típusa). 

  A dedikált eszközök, az eszköz állapotúként előfordulhat, hogy **nem megfelelő**. Feltételes hozzáférés nem érhető el, a dedikált eszközök. Győződjön meg arról, bármely feladatok vagy dedikált eszközök felelnek meg a hozzárendelt szabályzatok lekérése műveletek végrehajtásához.

- [Feltételes hozzáférés](conditional-access.md) – a felügyelt eszközök feltételes hozzáférési házirendeket, amelyek a alkalmazni az Android az Android Enterprise is teljes mértékben érvényesek. Felhasználók most már regisztrálhatja teljes körűen felügyelt eszköz az Azure Active Directory-a **a Microsoft Intune app**. Ezután tekintse meg és oldja meg a céges erőforrások elérésére megfelelőségi problémákat.

- Új felhasználó alkalmazást (Microsoft Intune-alkalmazás) – van egy új végfelhasználói alkalmazás Android teljes körűen felügyelt eszközök nevű **a Microsoft Intune**. Az új alkalmazás passzív és a modern, és biztosít hasonló funkcionálisan a vállalati portál alkalmazás, de teljes körűen felügyelt eszközök esetében. További információkért lásd: [a Google Play áruházból a Microsoft Intune app](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Beállítása az Android teljes körűen felügyelt eszközök, ugorjon a **eszközregisztráció** > **Android-eszközök regisztrálási** > **vállalat által birtokolt, teljes körűen felügyelt felhasználói eszközök**. Teljes körűen felügyelt Android-eszközök továbbra is előzetes verzióban érhető el támogatás, és bizonyos Intune-funkciók nem teljesen működőképes.  

Ebben az előzetes verzióban kapcsolatos további információkért lásd: blog, [Microsoft Intune – előzetes verzió 2 Android Enterprise teljes körűen felügyelt eszközökön](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Egyes képernyők kihagyásához során a beállítási asszisztens profil konfigurálása <!-- 2276470  wnstaged-->
Ha egy macOS beléptetési profil létrehozása, konfigurálhatja úgy, hogy hagyja ki az összes alábbi képernyőt, amikor egy felhasználó halad végig a beállítási asszisztens:
- Megjelenés
- Hang megjelenítése
- Ha hozzon létre egy új profilt, vagy egy profil szerkesztése iCloudStorage, a kiválasztott hagyja ki képernyők kell szinkronizálni az Apple MDM-kiszolgáló.  Így nem lesz késleltetés vesz fel a profil módosítása a felhasználók kiadhatnak az eszköz manuális szinkronizálása.
További információkért lásd: [a Készülékregisztrációs Program vagy az Apple School Manager macOS-eszközök automatikus regisztrálása](device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Tömeges eszköz elnevezési vállalati iOS-eszközök regisztrálásakor<!--3566569  -->
Apple vállalati regisztrációs módszerek (DEP/ABM/ASM) használatával, amikor egy eszköz nevének formátuma neve bejövő IOS-es eszközök automatikus is beállíthatja. Megadhat olyan formátum, amely tartalmazza az eszköz típusától és a sorozatszám a sablonban. Ehhez válassza ki a **Intune** > **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs program jogkivonatok** > **válasszon egy tokent** >**profil létrehozása** > **eszköz névadási**. Szerkesztheti a meglévő profilok, de csak az újonnan szinkronizált eszközökön fog rendelkezni a alkalmazni nevét.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Frissített alapértelmezett időtúllépési üzenet a regisztrálási állapot oldal <!-- 3959331 -->
Frissítettük az alapértelmezett időtúllépési üzenet a regisztrációs állapot oldal (ESP) meghaladja az időtúllépés értékét az ESP-profilban megadott felhasználó számára látható. Az új alapértelmezett üzenet a felhasználók mit talál és mit fejlesztettünk a következő műveleteket az ESP üzembe helyezéssel.  

### <a name="device-management"></a>Eszközkezelés

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Nem megfelelő eszközök kivonása  <!-- 1827291   -->
Ez a funkció késleltetését, és a egy későbbi kiadásban fog érkezni.


### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Az Intune Data Warehouse 1.0-s verziójú módosításokat vissza a bétaverzió tükröző <!-- 4403765 -->
Ha az 1.0-s verziójú 1808 rendszerben bevezetett, az API alkalmazást jelentős módokon eltérő számú. A 1903 ezeket a módosításokat megjelennek a bétaverzió API be újra. Ha fontos a bétaverzió API-t használó jelentéseket, erősen ajánlott ezeket a jelentéseket átváltása 1.0-s verziójú parancsban történt használhatatlanná tévő elkerülése érdekében. További információkért lásd: [esetében az Intune-adattárház API módosítási napló](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>(Nyilvános előzetes verzió) alapvető biztonsági állapot figyelése <!-- 3082047 --> 
Hozzáadtunk egy [kategória nézet](security-baselines-monitor.md#per-category-view) biztonsági előírások nyomon követésével. (Biztonsági előírások továbbra is előzetes verzióban érhető el). A kategória nézet jeleníti meg minden kategória az alaptervből együtt százalékos arányát az adott kategória minden egyes állapot csoportjához minősülő eszközökre. Most láthatja, hogy hány eszköz nem egyezik meg az egyes kategóriákat, helytelenül vannak konfigurálva, vagy nem vonatkoznak.

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Az Apple VPP-tokenek hatókörcímkék <!--2371886  -->
Hatókörcímkék adhat hozzá az Apple VPP-tokent. Csak az azonos címkéjű hatókörhöz hozzárendelt felhasználók hozzáférhet az adott címkével rendelkező Apple VPP-tokent. VPP-alkalmazások és e-könyv adott tokennel vásárolt öröklik a hatókörcímkék. Hatókörcímkék kapcsolatos további információkért lásd: [RBAC használata és a hatókör-címkéket](scope-tags.md).







## <a name="week-of-april-1-2019"></a>2019. április 1 hét

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Frissített tanúsítvány-összekötőt  <!-- ICM 113304612 -->
Mindkét kiadás frissítéseket a [Intune tanúsítvány-összekötő és a PFX-Tanúsítványösszekötő a Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). Az új kiadásokkal számos ismert problémák megoldása.  

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Felhasználóiélmény-frissítést a vállalati portál alkalmazás iOS-hez <!-- 2536024 -->
IOS-eszközökön a vállalati portál alkalmazás kezdőlapja megváltozott. Ezzel a kezdőlapján fog jobban kövesse iOS felhasználói felületi minták, és jobb észlelhetőség is biztosít az alkalmazásokhoz és e-könyvek.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Céges portál iOS 12-eszközök felhasználói regisztrációjának módosításai <!--3448635 -->  
A vállalati portál iOS beléptetési képernyők és a lépéseket, amelyek a mobileszköz-kezelési regisztrációs módosításokat jelent meg az Apple iOS 12.2 összhangban vannak frissítve lett-e. A frissített munkafolyamatot kéri a felhasználótól:  

* Nyissa meg a céges portál webhelyen, és a felügyeleti profil letöltéséhez a vállalati portál alkalmazásba való visszatérés előtt Safari engedélyezése.  
* Nyissa meg a beállítási alkalmazást a felügyeleti profil telepítésére az eszközükön.
* Térjen vissza a céges portál alkalmazás regisztráció elvégzését.  

Frissített regisztrációs lépéseket és képernyők: [iOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>2019. március 25 hete

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>A Power BI megfelelésével alkalmazást a Microsoft Intune-ban az adattárház panelen támogatása <!-- 4260871 -->
Korábban a **töltse le a Power BI-fájl** hivatkozásra a **Intune Data Warehouse** panel letöltött egy Intune-adattárház-jelentés (.pbix-fájl). Ez a jelentés a Power BI megfelelésével alkalmazás lett cserélve. A Power BI megfelelésével app speciális betöltésekor vagy a telepítő nem szükséges. Ez közvetlenül a Power BI online portálon nyissa meg, és kifejezetten az Intune-bérlőhöz, a hitelesítő adatok alapján az adatok megjelenítéséhez. Az Intune-ban válassza ki a **beállítása az Intune-adattárház** hivatkozást az Intune panel jobb oldalán. Kattintson a **Power BI alkalmazás első**. További információkért lásd: [kapcsolódás az Adattárházhoz a Power bi-ban a](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>2019. március 18 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>A Microsoft Visio és a Microsoft-projekt üzembe helyezése <!-- 3725386  -->
Most már telepítheti a Microsoft Visio Pro for Office 365 és a Microsoft Project Online asztali ügyfél független alkalmazásokat a Microsoft Intune, a Windows 10-eszközökön, ha licencekkel rendelkezik ezekhez az alkalmazásokhoz. Az Intune-ból, válassza ki a **ügyfélalkalmazások** > **alkalmazások** > **Hozzáadás** megjelenítéséhez a **alkalmazás hozzáadása** panelen. Az a **alkalmazás hozzáadása** panelen válassza ki **Windows 10-es** , a **alkalmazástípus**. Ezután válassza ki **alkalmazáscsomag konfigurálása** válassza ki a telepíteni kívánt alkalmazások. Office 365-alkalmazások Windows 10 rendszerű eszközökhöz kapcsolatos további információkért lásd: [hozzárendelése az Office 365-alkalmazások Windows 10-es eszközökhöz a Microsoft Intune-nal](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>A Microsoft Visio Pro for Office 365-höz a Terméknév módosítása <!-- 3593653  -->
**A Microsoft Visio Pro for Office 365** néven már ismert **Microsoft Visio Online 2. csomagjának**.  A Microsoft Visio kapcsolatos további információkért lásd: [a Visio Online 2. csomagjának](https://products.office.com/visio/visio-online-plan-2). Office 365-alkalmazások Windows 10 rendszerű eszközökhöz kapcsolatos további információkért lásd: [hozzárendelése az Office 365-alkalmazások Windows 10-es eszközökhöz a Microsoft Intune-nal](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Az Intune app protection szabályzat (alkalmazás) karakteres korlátot beállítása <!-- 3291302  -->
Intune-rendszergazdák adhatja meg az Intune alkalmazás kivételt **Kivágás, másolás és beillesztés korlátozása más alkalmazásokkal** házirend-beállítást.  Rendszergazdaként adja meg, amely kivágott vagy másolt a kezelt alkalmazások karakterek száma. Ez a beállítás lehetővé teszi a megosztását a megadott számú karaktert bármely alkalmazásba, függetlenül az "Kivágás, másolás és beillesztés korlátozása más alkalmazásokkal" beállítást. Vegye figyelembe, hogy az Androidhoz készült Intune vállalati portál verziója igényel 5.0.4364.0 verzió vagy újabb. További információkért lásd: [iOS adatvédelem](app-protection-policy-settings-ios.md#data-protection), [Android adatvédelem](app-protection-policy-settings-android.md#data-protection), és [ügyfelekre vonatkozó alkalmazásvédelmi naplók áttekintése](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Az Office központi telepítési eszköz (ODT) XML for Office ProPlus üzembe helyezéséhez <!-- 3192477   -->
Ha egy Office Pro Plus-példány létrehozása az Intune felügyeleti konzolon, adja meg az Office központi telepítési eszköz (ODT) XML lehet. Ez lehetővé teszi a testreszabhatóság nagyobb, ha a meglévő Intune felhasználói felület beállításai nem felelnek meg az igényeinek. További információkért lásd: [hozzárendelése az Office 365-alkalmazások Windows 10-es eszközökhöz a Microsoft Intune-nal](https://docs.microsoft.com/intune/apps-add-office365) és [beállítási lehetőségei az Office-telepítő eszköz](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Alkalmazásikonok mostantól automatikusan generált háttérrel jelennek <!-- 1429026  -->
A Windows céges portál alkalmazást, az ikonok most már megjelenik (amennyiben az érzékelhető) az ikon meghatározó színe alapján automatikusan generált háttérrel. Alkalmazható, ha a háttér felváltja a szürke kontúrt, amely korábban látható alkalmazáscsempén. Felhasználók látni fogják a céges portál 10.3.3451.0 újabb verzióiban ez a változás.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>A céges portál alkalmazás használata a Windows tömeges beléptetése után rendelkezésre álló alkalmazások telepítése <!-- 2751523   -->
Az Intune-ban regisztrált Windows-eszközök [Windows csoportos regisztrálás](windows-bulk-enroll.md) (kiépítési csomagok) tudják a vállalati portál alkalmazás segítségével telepítik az elérhető alkalmazásokat. A vállalati portál alkalmazással kapcsolatos további információkért lásd: [adja hozzá manuálisan a Windows 10-es céges portál](store-apps-company-portal-app.md) és [a Microsoft Intune vállalati portál alkalmazás konfigurálása](company-portal-app.md).

> [!Note]
> Ez a funkció a központilag még nem teljes mértékben telepített minden ügyfél számára. Ha nem tudja használni a vállalati portálon a tömegesen beléptetett eszközökön, akkor előfordulhat, hogy Várjon, amíg ez a változás vezet be a fiókjába.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>A Microsoft Teams alkalmazáshoz is kijelölhető az Office-app suite részeként <!-- 3828932  -->
A Microsoft Teams-alkalmazást tartalmazza, vagy az Office Pro Plus app suite telepítésének részeként kizárt is. Ez a funkció Office Pro Plus build száma 16.0.11328.20116+ működik. A felhasználónak kell jelentkezzen ki, majd jelentkezzen be az eszközön a telepítés befejezéséhez. Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > **Hozzáadás**. Válassza ki az egyik a **Office 365 csomag** alkalmazástípust, majd válassza ki **alkalmazáscsomag konfigurálása**.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Automatikusan elindít egy alkalmazást, amikor több alkalmazás fut a teljes képernyős módban a Windows 10-es és újabb rendszerű eszközök <!-- 2351390 -->

Windows 10-es és újabb rendszerű eszközök, az eszköz kioszk módban futtatni, és sok más alkalmazás futtatása. Ez a frissítés van egy **AutoLaunch** beállítás (**eszközkonfiguráció** > **profilok** > **profillétrehozása**  >  **Windows 10 és újabb** tartozó platform > **teljes képernyős** profiltípus > **többalkalmazásos kioszk**). Ez a beállítás használatával automatikusan elindít egy alkalmazást, ha a felhasználó bejelentkezik az eszközre.

Listáját és leírását, a kioszkmód megtekintéséhez lásd: [Windows 10-es és újabb beállításai az Intune-ban a teljes képernyős fiókként való futtatásra](kiosk-settings-windows.md).

Érintett kiadások: Windows 10 és újabb

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Műveleti naplók is megjelenítése a részletek a nem megfelelő eszközök <!-- 4063755  -->
Útválasztási Intune az Azure monitor-funkciók jelentkezik, ha a műveleti naplókban is irányíthatja. Ebben a frissítésben a műveleti naplókban is tájékoztatást nyújt a nem megfelelő eszközök. 

Ez a szolgáltatás további információkért lásd: [küldési naplóadatokat, storage, az event hubs vagy az Intune-ban a log analytics](review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>További Intune számítási feladatok útvonal-naplók az Azure monitornak <!-- 3804627 -->
Az Intune-ban, naplózási és műveleti naplók átirányítása a storage-események hubok és log analytics az Azure monitorban (**Intune** > **figyelés** > **diagnosztika beállítások**). Ebben a frissítésben ezeket a naplókat a további Intune számítási, beleértve a megfelelőség, a konfigurációk, az ügyfélalkalmazások és további irányíthatja. 

Az Azure monitornak útválasztási naplók kapcsolatos további információkért lásd: [Teljesítménynapló-adatok küldése a tárolóhoz, az event hubs, vagy a log analytics](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Létrehozhat és használhat a mobilitási bővítmények Android Zebra-eszközökön az Intune-ban <!-- 3305880   -->
Ebben a frissítésben az Intune konfigurálása Android Zebra eszközöket támogatja. Pontosabban, hozhat létre eszközkonfigurációs profil, és beállítások StageNow által generált mobilitási bővítmények MX-profilok használatával Android Zebra-eszközökre vonatkoznak (**eszközkonfiguráció**  >   **Profilok** > **profil létrehozása** > **Android** tartozó platform > **MX-profil (csak Zebra)** profil Írja be).

Ez a szolgáltatás további információkért lásd: [használatát és mobilitási bővítmények az Intune-ban Zebra-eszközök felügyeletéhez](android-zebra-mx-overview.md).

Érintett kiadások: Android

### <a name="device-management"></a>Eszközkezelés

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Titkosítási jelentés a Windows 10 rendszerű eszközökhöz (nyilvános előzetes verzió)<!-- 2351538 -->  
Az új [titkosítási jelentésben (előzetes verzió)](encryption-monitor.md) a Windows 10 rendszerű eszközök titkosítási állapotát részleteinek megtekintéséhez. Rendelkezésre álló adatot közé tartozik az eszközök TPM-verzió, titkosítási készültségi állapot, hibajelentés és még.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>A BitLocker helyreállítási kulcsok elérését az Intune-portálon (a nyilvános előzetes verzió) <!-- 2351547   -->  
Most már használhatja az Intune [részleteinek megtekintéséhez](encryption-monitor.md) BitLocker-kulcs azonosítója és a BitLocker helyreállítási kulcsok az Azure Active Directoryból.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>A Microsoft Edge támogatása az iOS- és Android-eszközök Intune-forgatókönyvek <!-- 3411007 -->
A Microsoft Edge támogatni fogják az azonos felügyeleti forgatókönyvek, az Intune Managed Browser továbbfejlesztett végfelhasználói élmény igény szerinti hozzáadásával. A Microsoft Edge vállalati Intune szabályzatai által engedélyezett funkciók kettős-Identity, app protection házirend-integráció, az Azure application proxy-integráció, és felügyelt Kedvencek és a kezdőlap parancsikonok. További információkért lásd: [Microsoft Edge támogatási](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Az Exchange Online vagy Intune-összekötő csak az EAS-eszközök támogatását kivezetjük <!--3105122  -->
Az Intune-konzolon többé nem támogatja a megtekintése, és csak az EAS-eszközök kezelésének csatlakozik Exchange online-hoz az Intune-összekötővel. Ehelyett a következő lehetősége van:
- A mobileszköz-felügyeleti (MDM) eszközök regisztrálása
- Az Intune alkalmazásvédelmi szabályzatok használata az eszközök kezeléséhez
- Az Exchange vezérlőkkel leírt módon [ügyfelek és a mobileszköz Exchange Online-ban](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Az összes eszköz lapon-pontos eszköz keresését, [name] <!--4254930 -->
Most már kereshet egy pontos eszköz nevét. Lépjen a **Intune** > **eszközök** > **minden eszköz** > a keresőmezőbe, az eszköz nevét körülvevő {} keresése egy pontos egyezés. Ha például **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>A bérlő állapotának oldalon további összekötők támogatása <!-- 3617202  -->
A [bérlői állapotlapon](tenant-status.md) ettől kezdve további összekötők, többek között az állapotadatait *Windows Defender komplex veszélyforrások elleni védelem* (ATP) és egyéb Mobile Threat Defense-összekötők.

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Csak bizonyos Azure Active Directory-szerepkör való hozzáférés biztosítása az Intune-ban olvasása <!-- 3637917  -->
Az Intune olvassa el, csak kapott hozzáférést a következő Azure AD-szerepkörökhöz. Az Azure AD-szerepkörökhöz rendelt engedélyeket váltja fel az Intune szerepköralapú hozzáférés-vezérlés (RBAC) az adott engedélyek.

Olvassa el az Intune-naplózási adatokat csak a hozzáférést:

- Szabályozási ügyintéző
- Megfelelőségi adatok rendszergazda

Csak olvasásra jogosító hozzáférés Intune-ban tárolt összes:

- Biztonsági rendszergazda
- Biztonsági operátor
- Biztonsági olvasó

További információkért lásd: [szerepköralapú hozzáférés-vezérlés](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Hatókörcímkék az iOS-alkalmazáskiépítési profilok <!--2934430   -->
Így csak is az adott hatókörcímke hozzárendelt szerepkörrel rendelkező személyek hozzáférhetnek az IOS-es alkalmazáskiépítési profil hatókörcímke adhat hozzá egy IOS-es alkalmazáskiépítési profil. További információkért lásd: [RBAC használata és a hatókör-címkéket](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Hatókörcímkék az alkalmazáskonfigurációs szabályzatok <!--2371891   -->
Így csak is az adott hatókörcímke hozzárendelt szerepkörrel rendelkező személyek hozzáférhetnek az alkalmazáskonfigurációs szabályzat hatókörcímke adhat hozzá alkalmazás-konfigurációs házirend. Az alkalmazáskonfigurációs szabályzat csak a megcélzott vagy az azonos hatókörcímke hozzárendelt alkalmazásokhoz vannak rendelve. További információkért lásd: [RBAC használata és a hatókör-címkéket](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>A Microsoft Edge támogatása az iOS- és Android-eszközök Intune-forgatókönyvek <!-- 3411007 -->
A Microsoft Edge támogatni fogják az azonos felügyeleti forgatókönyvek, az Intune Managed Browser hozzáadásával kapcsolatos fejlesztések a végfelhasználói élményt. A Microsoft Edge vállalati Intune szabályzatai által engedélyezett funkciók kettős-Identity, app protection házirend-integráció, az Azure application proxy-integráció, és felügyelt Kedvencek és a kezdőlap parancsikonok. További információkért lásd: [Microsoft Edge támogatási](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>2019. február 25 hete

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="intune-powershell-module----951068----"></a>Intune-ban a PowerShell-modul <!-- 951068  -->
Már elérhető az Intune-os PowerShell modult, amely lehetővé teszi a Microsoft Graphon keresztül az Intune API támogatását, a [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Részletes tájékoztatást a modul használata](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Ez a modul használatával eltávolítási módjaira](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Kézbesítésoptimalizálás továbbfejlesztett támogatása  <!--3183757  -->
Kiterjesztettük a támogatást az Intune-ban a kézbesítésoptimalizálás konfigurálása. Most már konfigurálhat egy kibontott listája [kézbesítésoptimalizálás beállítások](delivery-optimization-settings.md) és a cél az eszközök közvetlenül az Intune-konzolon.


## <a name="week-of-february-18-2019"></a>2019. február 18 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune az Android-eszközökön a Google Play védelme API-kat használja <!-- 2577355   -->
Egyes rendszergazdáknak kihívással szembesülnek, a BYOD fekvő tájolás, a végfelhasználók előfordulhat, hogy végül a telepítés vagy jailbreaking a mobiltelefonon. Ez a viselkedés, amíg nem néha helytelenül – intentioned, annak érdekében, hogy a végfelhasználói eszközökön a szervezet adatainak megvédése beállított számos Intune-házirendek a Mellőzés eredményez. Így az Intune kínál mind a regisztrált és nem regisztrált eszközök rootolásának és függetlenítésének észlelését. Ebben a kiadásban az Intune most már használja a Google Play védelme API-k hozzáadása a nem regisztrált eszközök a meglévő legfelső szintű észlelési ellenőrzése. Google nem osztja meg a legfelső szintű észlelési ellenőrzéseket végez a teljes, miközben várhatóan ezen API-k, felhasználók, akik rendelkezik rootolva eszközeiket a testre szabható az eszközök bármilyen okból újabb operációsrendszer-frissítés részletes a régebbi eszközöket képes észlelni. Ezek a felhasználók majd egytől a vállalati adatokhoz hozzáférő, vagy a házirend-kompatibilis alkalmazások a vállalati fiókokra törlődhetnek. További értékek a rendszergazda már az Intune App Protection panelen található jelentéskészítési frissítéseket – a "Megjelölt felhasználók" a jelentés megmutatja, hogy mely felhasználók észlelése keresztül a Google Play Protect a SafetyNet API vizsgálatot, a "potenciálisan káros alkalmazások" jelentést fog megjelenítése, mely alkalmazások észlelése API-n keresztül a Google ellenőrzése alkalmazások vizsgálatát. Ez a funkció Android rendszeren érhető el.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>A Win32-alkalmazás adatai hibaelhárítás panelen érhető el <!-- 2617342   -->
Most már gyűjthet hiba naplófájlokat egy Win32-alkalmazás telepítése az Intune App **hibaelhárítás** panelen. Alkalmazás telepítési hibaelhárítással kapcsolatos további információkért lásd: [alkalmazás telepítési problémák elhárítása](troubleshoot-app-install.md) és [hibaelhárítása Win32 alkalmazás problémák](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Az iOS-alkalmazások App-állapot részletei <!-- 3761235   -->
Új alkalmazás telepítési hiba történt a következőhöz kapcsolódó üzenetek vannak:
- VPP-alkalmazások a megosztott iPad telepítésekor hiba
- Hiba, amikor az app Store-ban le van tiltva.
- Hiba található a VPP-licenc az alkalmazás
- Nem sikerült telepíteni a rendszer alkalmazások az MDM-szolgáltató
- Nem sikerült telepíteni a alkalmazások eszköz esetén az elveszett eszköz mód vagy a teljes képernyős módban
- Nem sikerült telepíteni az alkalmazást, amikor a felhasználó nem jelentkezett be, az App Store

Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > "App name" > **eszköz telepítési állapota**. Új hibaüzenetek lesz elérhető a **állapot részletei** oszlop.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Új alkalmazás kategóriák képernyő Windows 10-es céges portál alkalmazásban<!-- 3834780  -->
Egy új képernyőt nevű **Alkalmazáskategóriák** a Windows 10 céges portál alkalmazás tallózása és kiválasztása élményének növelése érdekében jelentősen bővült. A felhasználók mostantól látnak alkalmazásaikat, például a kategóriák szerint rendezve **kiemelt**, **oktatási**, és **termelékenység**. Ez a módosítás megjelenik a céges portál verziókban 10.3.3451.0 és újabb verziók. Az új képernyő megtekintése: [az alkalmazásfelhasználói felület újdonságai](https://docs.microsoft.com/intune/whats-new-app-ui). A vállalati portál alkalmazások kapcsolatos további információkért lásd: [telepítése és megosztása az eszközön található alkalmazások](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>A Power BI megfelelőségi alkalmazás <!-- 1455231 doc-work-item -->
A Power BI online-hoz az Intune-adattárház elérése a [(adatraktár) az Intune megfelelőségi](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) alkalmazást. A Power BI alkalmazással most már elérheti és megoszthatja az előre létrehozott jelentések beállítások nélkül, és a böngésző elhagyása nélkül. További információkért lásd: [módosítási napló - megfelelőségi a Power BI alkalmazás](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>PowerShell-parancsprogramok a 64 bites gazdagépen 64 bites eszközökön futtathatja <!-- 1862675   -->
Eszközkonfigurációs profil hozzá egy PowerShell-parancsfájlt, ha a parancsfájl mindig futtatják a 32 bites, akár a 64 bites operációs rendszereken. Ezzel a frissítéssel a rendszergazda tudja futtatni a parancsprogramot a 64 bites PowerShell-gazdagépet a 64 bites eszközökön (**eszközkonfiguráció** > **PowerShell-parancsfájlok**  >   **Adjon hozzá** > **konfigurálása** > **64 bites PowerShell-gazdagépet a szkriptet futtathatja**).

A PowerShell használatával további részletekért lásd: [az Intune-ban a PowerShell-parancsfájlok](intune-management-extension.md).

Érintett kiadások: Windows 10 és újabb

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS-felhasználók a rendszer kéri a jelszó frissítése <!-- 1873216 -->
Az Intune kényszerít a **ChangeAtNextAuth** beállítása macOS-eszközökön. Ez a beállítás hatással van a végfelhasználók és a jelszó házirendek vagy a jelszó eszközkorlátozási profilok rendelkező eszközök. A végfelhasználók a jelszófrissítési egyszer megerősítését. Ez a kérdés történik, amikor egy felhasználó először futtat egy feladatot, amely megköveteli a hitelesítést, például az eszköz bejelentkezik. Felhasználók is frissíteni a jelszavát, ha rendszergazdai jogosultsággal, például az kulcslánc-hozzáférési csinál semmit, amely szükséges lehet kéri. 

Minden olyan új vagy meglévő szabályzat jelszómódosítások a rendszergazda által a végfelhasználók számára, hogy újra frissíteni a jelszavát kéri.

Érintett kiadások:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>SCEP-tanúsítványok felhasználó nélküli macOS-eszközök hozzárendelése  <!-- 2340521  -->
Rendelje hozzá az egyszerű tanúsítványigénylési protokoll (SCEP) tanúsítványok eszközattribútumok MacOS rendszerű eszközökhöz, beleértve a, a felhasználói affinitás nélküli eszközök használatával, és rendelje hozzá a tanúsítványprofil Wi-Fi vagy VPN-profilok. Ez kibővíti a támogatást, már eleve [SCEP-tanúsítványok és a felhasználói affinitás nélküli eszközökhöz hozzárendelni](certificates-scep-configure.md#create-a-scep-certificate-profile) Windows, iOS és Android rendszerű.  Ezt a frissítést hozzáadja a kívánt tanúsítvány típusú *eszköz* a macOS-hez készült SCEP-tanúsítványprofil konfigurálásakor.

Érintett kiadások: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Az Intune feltételes hozzáférés felhasználói felület frissítése   <!-- 2432313   -->
A feltételes hozzáférés az Intune-konzolon a felhasználói felület fejlesztéseket végeztünk. Ezek a következők:
-  Lecseréli az Intune *feltételes hozzáférési* panelről a panel az Azure Active Directoryból. Ez biztosítja a hozzáférést, a beállítások és konfigurációk teljes körét [feltételes hozzáférési](conditional-access.md) (ami továbbra is egy Azure AD-technológia), az Intune-konzolról. 
- Azt már átnevezték a *helyszíni hozzáférés* panel *Exchange-hozzáférés*, és más helyre a *Exchange szolgáltatási összekötője* átnevezve: ezen a panelen a telepítőt.  Ez a változás összesíti a helyét, [konfigurálhatja és figyelheti az Exchange online-hoz és a helyszíni kapcsolatos részleteket](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>A teljes képernyős böngésző és a Microsoft Edge böngésző alkalmazások teljes képernyős módban a Windows 10-eszközökön futtathatja <!-- 2935135   -->
Egy alkalmazás vagy sok alkalmazás használhatja a teljes képernyős módban a Windows 10-eszközök. Ez a frissítés segítségével a böngészőben megjelenő alkalmazásokba teljes képernyős módban számos módosításait tartalmazza többek között:

- Adja meg a Microsoft Edge böngészőt vagy futtatható alkalmazásokat a teljes képernyős eszközön teljes képernyős böngésző (**eszközkonfiguráció** > **profilok** > **új profil**  >  **Windows 10 és újabb** tartozó platform > **teljes képernyős** profiltípus).
- Új funkciók és beállítások érhetők el engedélyezése vagy korlátozása (**eszközkonfiguráció** > **profilok** > **új profil**  >  **Windows 10 és újabb** tartozó platform > **eszközkorlátozások** profiltípus), többek között:

  - Microsoft Edge Browser:
  - A Microsoft Edge-teljes képernyős mód használata
  - Üresjárati idő után frissítse a böngészőt

 - Kedvencek és keresés:
  - -Motor keresés engedélyezése

Ezek a beállítások listáját lásd:

- [Windows 10-es és újabb beállításai a teljes képernyős fiókként való futtatásra](kiosk-settings-windows.md)
- [A Microsoft Edge böngésző eszközkorlátozások](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Kedvencek és keresési eszközkorlátozások](device-restrictions-windows-10.md##favorites-and-search)

Érintett kiadások: Windows 10 és újabb

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Új eszközkorlátozásokra vonatkozó beállítások az iOS és macOS-eszközök <!-- 3448774   -->
Bizonyos beállítások és funkciók iOS és macOS rendszerű eszközökön korlátozhatja (**eszközkonfiguráció** > **profilok** > **új profil**  >  **iOS** vagy **macOS** tartozó platform > **eszközkorlátozások** profiltípus). Ezt a frissítést hozzáadja a további funkciók és szabályozhatja, beleértve a beállítás képernyő idő, módosítás, esim-kártya beállításait és mobil terveket, és további információ az iOS-eszközök beállításai. Ezenkívül késlelteti a szoftverfrissítéseket, és blokkolja a tartalom gyorsítótárazása macOS-eszközökön a felhasználó látható-e. 

A funkciók és korlátozhatja a beállítások megtekintéséhez lásd:

- [iOS-eszközök korlátozásaira vonatkozó beállítások](device-restrictions-ios.md)
- [macOS-eszközök korlátozásaira vonatkozó beállítások](device-restrictions-macos.md)

Érintett kiadások:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>"Kioszkeszközök" most nevezik "Dedikált eszközök" Vállalati Android-eszközökön <!-- 3598402   -->
Android-terminológia, igazodva **teljes képernyős** módosul, amelyikben **dedikált eszközök** a vállalati Android-eszköz (**eszközkonfiguráció**  >  **Profilok** > **profil létrehozása** > ** tartozó platform Android enterprise > **eszköz tulajdonosa csak** > **eszköz Korlátozások** > **dedikált eszközök**).

Az elérhető beállítások megtekintéséhez lépjen a [eszközbeállítások engedélyezett vagy korlátozott funkciók](device-restrictions-android-for-work.md#dedicated-device-settings).

Érintett kiadások:  
Vállalati Android

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Safari és Delaying felhasználói szoftverfrissítési beállítások helyez át az Intune felhasználói felületén látható-e iOS frissítése <!-- 3640850, 3803313   -->
IOS-eszközök esetén a Safari beállításait, és konfigurálhatja a szoftverfrissítéseket. Ebben a frissítésben ezek a beállítások az Intune felhasználói felület különböző részeinek helyez át:

- A Safari beállításait az áthelyezett **Safari** (**eszközkonfiguráció** > **profilok** > **új profil**  >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus) való  **[beépített alkalmazások](device-restrictions-ios.md#built-in-apps)** .
- A **késlelteti az felhasználói szoftvereket látható-e frissítés az iOS-eszközök felügyelt** beállítás (**szoftverfrissítések** > **Update-szabályzatok iOS rendszerhez**) kerülát **Eszközkorlátozások** >  **[általános](device-restrictions-ios.md#general)** .  További információ a hatás szerint is megjelenítheti a meglévő szabályzatokat: [iOS szoftverfrissítések](software-updates-ios.md#configure-the-policy). 

A beállítások listájáért lásd:

- [eszközkorlátozások iOS](device-restrictions-ios.md) 
- [iOS-szoftverfrissítések](software-updates-ios.md)

Ez a funkció az alábbiakra vonatkozik: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Korlátozások engedélyezése az eszköz között új képernyő idő az iOS-eszközökön <!-- 3699164   -->
Konfigurálhatja a **korlátozások engedélyezése az eszköz között** a felügyelt iOS-eszközök (**eszközkonfiguráció** > **profilok**  >  **Új profil** > **iOS** tartozó platform > **eszközkorlátozások** profiltípus > **általános**). Ebben a frissítésben ezzel a beállítással új **(csak felügyelt) képernyő idő**. 

A viselkedés megegyezik. Pontosabban: 

- iOS-es 11.4.1 és korábbi: **Blokk** megakadályozza, hogy a végfelhasználók számára az Eszközbeállítások között a saját korlátozásokkal. 
- iOS-es 12.0 és újabb verziók: **Blokk** megakadályozza, hogy a végfelhasználók saját beállítás **képernyő idő** az Eszközbeállítások között, beleértve a tartalom & adatvédelmi korlátozások. Frissített iOS 12.0-s eszközök többé nem jelenik meg a korlátozásokat fülre az Eszközbeállítások között. Ezek a beállítások szerepelnek **képernyő idő**. 

A beállítások listájáért lásd: [eszközkorlátozások iOS](device-restrictions-ios.md#general).

Érintett kiadások: 
- iOS


### <a name="device-management"></a>Eszközkezelés

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Egy regisztrált Windows-eszköz átnevezése <!-- 1911112  -->
Most átnevezheti a regisztrált Windows 10-es eszköz (RS4 vagy újabb). Szeretné elvégezni, válassza ki a **Intune** > **eszközök** > **minden eszköz** > Válasszon egy eszközt > **átnevezése eszköz**. Ez a funkció jelenleg nem támogatja a átnevezési hibrid Azure AD-Windows-eszközök.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Hatókörcímkék automatikus hozzárendelése a hatókörrel rendelkező rendszergazda által létrehozott erőforrások <!-- 3173823  -->
Amikor a rendszergazda létrehoz egy erőforrást, bármely, a rendszergazda rendelt hatókörcímkék automatikusan rendeli hozzá ezeket az új erőforrásokat.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Sikertelen regisztráció jelentés áthelyezi az Eszközregisztráció panel <!-- 3560202  -->
A **sikertelen regisztrációk** jelentés át lett helyezve a **figyelő** szakaszában a **eszközregisztráció** panelen. Két új oszlopot (regisztrációs módszer és operációsrendszer-verzió) hozzá lett adva.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Vállalati portálon való lemondás jelentés hiányos felhasználói regisztrációk neve: <!--3815076 eemiss -->
A **céges portálon való lemondás** jelentés át lett nevezve a **hiányos felhasználói regisztrációk**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>2019. február 4 hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Intune-ban macOS céges portálra sötét üzemmód <!-- 3300524  -->
Az Intune-ban macOS céges portálra sötét mód mostantól támogatja a macOS-hez. Ha engedélyezi a sötét üzemmód 10.14 + macOS-eszközön, a vállalati portál lehetőség a megjelenését, amely mutatja, hogy a üzemmód színeket.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>2019. január 21 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Bejelentési értesítések Win32-alkalmazások <!-- 3136566   -->
Bemutató végfelhasználói bejelentési értesítések egy alkalmazás-hozzárendelés tilthatja le. Az Intune-ból, válassza ki a **ügyfélalkalmazás** > **alkalmazások** > Válassza ki az alkalmazást > **hozzárendelések** > **csoportokhozközétartozik**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Az Intune app protection házirendek felhasználói felület frissítése <!-- 3251427  -->
Módosítottuk a címkék beállításainak és az Intune app Protection, hogy könnyebben érthetőek gombok. A változások a következők:  
- Vezérlők meg nem változtatják **Igen** / **nincs** elsősorban szabályozza **blokk** / **engedélyezése** és **letiltása** / **engedélyezése** szabályozza. A címkék is frissülnek.  
- Beállítások újraformázása, így a beállítás, és a felirat egymás mellett a vezérlőelemet, adja meg a jobb navigációs.   

Az alapértelmezett beállításokat és a beállítások száma nem változik, de ez a változás lehetővé teszi, hogy a felhasználó megértése, keresse meg, és a alkalmazni a beállításokat több egyszerűen kiválasztott alkalmazásvédelmi szabályzatok. További információ: [iOS-beállítások](app-protection-policy-settings-ios.md) és [Android-beállításokat](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Az Outlook további beállítások <!-- 3301182  -->
Mostantól konfigurálhatja az IOS rendszerhez készült Outlook és az Android, az Intune-nal a következő további beállításokat:

- Csak a munkahelyi vagy iskolai fiókkal az Outlookban az iOS és Android rendszerhez használható engedélyezése
- Modern hitelesítéssel az Office 365 és a hibrid, modern hitelesítést a helyszíni fiókok telepítése
- Használat `SAMAccountName` az e-mail profilban, az egyszerű hitelesítés kijelölésekor a felhasználónév mező
- Lehetővé teszi az ügyfelek menteni
- Konfigurálja a külső címzetteknek e-mail tippek
- Konfigurálása **szűrt levelek**
- Biometrikai IOS rendszerhez készült Outlook eléréséhez szükséges
- Külső képek letiltása

> [!NOTE]
> Ha az Intune alkalmazásvédelmi szabályzatokat használ a vállalati identitások kezelésére, érdemes lehet nem engedélyezi az **biometrika megkövetelése**. További információkért lásd: **vállalati hitelesítő adatok megkövetelése a hozzáféréshez** a [hozzáférési beállítások iOS](app-protection-policy-settings-ios.md#access-requirements) és [Android-beállításokat](app-protection-policy-settings-android.md#access-requirements).

További információkért lásd: [konfigurációs beállításai a Microsoft Outlook](app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Androidos vállalati alkalmazások törlése <!-- 1352553 -->
Törölheti a felügyelt Google Play-alkalmazások Microsoft Intune-ból. Felügyelt Google Play alkalmazás törléséhez nyissa meg a Microsoft Intune az Azure Portalon, és válassza a **ügyfélalkalmazás** > **alkalmazások**. Az alkalmazás listában jelölje ki a három pontra (...) jobb oldalán a felügyelt Google Play-alkalmazást, majd válassza ki **törlése** a megjelenő listából. Ha egy felügyelt Google Play-alkalmazást töröl alkalmazásokat az alkalmazáslistából, a felügyelt Google Play alkalmazás automatikusan jóvá nem hagyott.

#### <a name="managed-google-play-app-type----1352580---"></a>Felügyelt Google Play alkalmazás típusa <!-- 1352580 -->
A **felügyelt Google Play** alkalmazástípus lehetővé teszi, hogy kifejezetten [felügyelt Google Play-alkalmazások](https://play.google.com/work/search?q=microsoft&c=apps) az Intune-hoz. Az Intune-rendszergazdaként mostantól Tallózás, keresés, hagyja jóvá, szinkronizálása és jóváhagyott a felügyelt Google Play-alkalmazások Intune-ban hozzárendelése.  Már nem kell külön tallózással keresse meg a felügyelt Google Play konzolon, és többé nem kell újból hitelesítésre.  Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > **Hozzáadás**. Az a **alkalmazástípus** listáról válassza ki **felügyelt Google Play** az alkalmazás típusaként.

### <a name="default-android-pin-keyboard----3802457---"></a>Alapértelmezett Androidos PIN-kód billentyűzet <!-- 3802457 -->
A végfelhasználók számára, akik saját Android-eszközökön 'Numerikus' a PIN-kód típusú állított be az Intune App Protection szabályzat (alkalmazás) PIN-kód láthatják az alapértelmezett Android billentyűzet helyett a rögzített Android billentyűzet felhasználói felület, amely a korábban készült. A módosítás alapértelmezett billentyűzetek használata az Android és iOS-, mind a mindkét "Numerikus" és/vagy "PIN-jelszó PIN-kód típusú összhangban kell. Végfelhasználói hozzáférési beállítások az Android, például az alkalmazás PIN-kód, bővebben lásd: [Android hozzáférési követelmények](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Microsoft által ajánlott beállítások használata a biztonsági előírások (nyilvános előzetes verzió) <!-- 2055484   -->

Az Intune integrálható más, biztonsági célú szolgáltatásokkal, például a Windows Defender ATP-vel és az Office 365 ATP-vel. Az ügyfelek a Microsoft 365-szolgáltatásokon átívelő közös stratégiát és összefüggő, teljes körű biztonsági munkafolyamatokat kérnek. Célunk a stratégiák összehangolása és ezáltal olyan megoldások létrehozása, amelyek hidat képeznek a biztonsági műveletek és a gyakori felügyeleti feladatok között. Az Intune-ban ezen cél elérésére a Microsoft által ajánlott „biztonsági előírások” közzétételével törekszünk (**Intune** > **Biztonsági előírások**).  A rendszergazda ezen alaptervek közvetlenül a biztonsági házirendek létrehozása, és telepítheti őket a felhasználóknak. Testre szabhatja a ajánlásokat és tanácsokat a szervezet igényeinek kielégítése érdekében. Az Intune biztosítja, hogy az eszközök megfeleljenek ezeknek az előírásoknak, és értesíti a rendszergazdákat, ha egy felhasználó vagy eszköz nem felel meg.

Ez a funkció jelenleg nyilvános előzetes verzióban, így minden létrehozott profilok mostantól nem helyezi át biztonsági előírások sablonokat, amelyek általánosan elérhető (GA). Nem szeretné használni ezeket a sablonokat előzetes az éles környezetben.

Biztonsági alapterveket kapcsolatos további információkért lásd: [az Intune-ban Windows 10 biztonsági alapterv létrehozása](security-baselines-monitor.md).

Ez a funkció az alábbiakra vonatkozik: Windows 10 és újabb

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>A nem rendszergazdák engedélyezhetik a BitLocker az Azure AD-csatlakoztatott Windows 10 rendszerű eszközökön<!-- 2147379   -->
Ha engedélyezi a BitLocker-beállítások Windows 10 rendszerű eszközökön (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10 és újabb** tartozó platform > **az Endpoint protection** profiltípus > **Windows titkosítási**), akkor adja hozzá a BitLocker-beállítások. 

A frissítés tartalmaz egy új BitLocker beállítását, hogy általános jogú felhasználók (nem rendszergazda), engedélyezheti a titkosítást. 

A beállítások megtekintéséhez lépjen a [Endpoint protection-beállítások Windows 10-es](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>A Configuration Manager-megfelelőség ellenőrzése <!-- 2192052  eepublished  -->
Ez a frissítés magában foglalja a System Center Configuration Manager az új megfelelőségi beállítás (**eszközmegfelelőség** > **házirendek** > **hozzon létre házirendet**  >  **Windows 10 és újabb** > **Configuration Manager megfelelőségi**). A Configuration Manager megfelelőségi jeleket küldi az Intune-nak. Ezzel a beállítással megkövetelheti az összes Configuration Manager-jel való visszatéréshez "megfelelő".

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ha az eszközön lévő összes programot ismeretlen állapotban van, az eszköz akkor nem kompatibilis az Intune-ban.

[A Configuration Manager megfelelőségi](compliance-policy-create-windows.md#configuration-manager-compliance) ismerteti ezt a beállítást.

Érintett kiadások: Windows 10 és újabb

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Eszközkonfigurációs profil használatával felügyelt iOS-eszközök tapétáját testreszabása <!-- 2809324   -->
Amikor egy iOS-eszközök konfigurációs profilt hoz létre, testre szabhatja az egyes funkciók (**eszközkonfiguráció** > **profilok** > **létrehozása profil** > **iOS** tartozó platform > **eszközfunkciók** profiltípus). A frissítés tartalmaz új **háttérkép** beállítások, amelyek lehetővé teszik a rendszergazdáknak .png, .jpg és .jpeg-rendszerkép használata a kezdőképernyő vagy a zárolási képernyőn. Ezek a háttér-beállítások csak a felügyelt eszközökre vonatkoznak. 

Ezek a beállítások listáját lásd: [IOS-es eszközfunkció-beállítások](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10-es teljes képernyős szolgáltatás általánosan elérhető <!-- 3594661  -->
Ez a frissítés a Windows 10-es és újabb rendszerű eszközök teljes képernyős funkció általánosan elérhető (GA). Felveheti és konfigurálhatja az összes beállítások megtekintéséhez lásd: [teljes képernyős beállítások Windows 10-es (és újabb)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Bluetooth-névjegyek megosztása eltávolítják az Eszközkorlátozások > Android Enterprise eszköz tulajdonosa <!-- 3598396   -->
Az Android Enterprise-eszközöket egy eszközkorlátozási profilt hoz létre, ha van egy **forduljon megosztása Bluetooth használatával** beállítás. Ebben a frissítésben a **forduljon megosztása Bluetooth használatával** beállítás törlődik (**eszközkonfiguráció** > **profilok**  >   **Profil létrehozása** > **Android Enterprise** tartozó platform > **Eszközkorlátozások > eszköz tulajdonosa** profiltípus > **általános** ). 

A **forduljon megosztása Bluetooth használatával** beállítás nem támogatott az Android vállalati eszköz tulajdonosa management. Ezzel a beállítással a rendszer eltávolítja, ha ez nem érinti az bármely eszköz vagy a bérlők, akkor is, ha ez a beállítás engedélyezve van, és konfigurálva a környezetben.

Beállítások aktuális listájának megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md).

Érintett kiadások: Androidos vállalati eszköz tulajdonosa

### <a name="device-management"></a>Eszközkezelés

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>WIP regisztrációval nem rendelkező eszközök szelektív törlés támogatása <!-- 1434452 -->
Windows Information Protection regisztráció nélkül (WIP-TUDJUK) lehetővé teszi a felhasználóknak teljes körű MDM-regisztráció nélkül a Windows 10 rendszerű eszközökön a vállalati adatok védelme érdekében. Miután dokumentumok védettek a WIP-TUDJUK házirend, a védett adatok szelektív törlése az Intune-rendszergazda által. A felhasználó és eszköz kiválasztásával, és a törlési kérelmet, a WIP segítségével védett összes adatot küldő – hogy házirend használhatatlan lesz. Ehhez az Azure Portal Intune részén válassza a **Mobilalkalmazás** > **Alkalmazás szelektív törlése** lehetőséget.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Új műveleti naplók, és képes titkosítottan küldeni a naplókat az Azure Monitor szolgáltatás <!-- 3762211  -->
Az Intune beépített naplózásra, amely nyomon követi az eseményeket, a módosítások rendelkezik. A frissítés új naplózási szolgáltatásokat, beleértve a tartalmazza: 
- Műveleti naplók (előzetes verzió), amely a felhasználók és eszközök regisztrálása, beleértve a sikeres és sikertelen kísérlet részletek megjelenítése.
- A vizsgálati naplók és a műveleti naplókban az Azure Monitor, beleértve a storage-fiókok, az event hubs, elküldött, és a log analytics. Ezek a szolgáltatások lehetővé teszik tárolni, például Splunk és QRadar elemzések és a naplózási adatok vizualizációkat.

[Napló adatokat küldeni a tárolási, az event hubs, vagy a log analytics az Intune-ban](review-logs-using-azure-monitor.md) Ez a szolgáltatás további információkkal szolgál.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Hagyja ki a további beállítási asszisztens képernyők az iOS DEP-eszközökön <!-- 2687509  -->
Jelenleg kihagyhatja a képernyők, mellett állíthatja be iOS DEP-eszközök a beállítási asszisztens képernyőinek kihagyásához amikor egy felhasználó regisztrálja az eszközt: Képviselő hangvételét, adatvédelmi, Android áttelepítési, kezdőlap gombot, iMessage & FaceTime, bevezetési, tekintse meg a Migrálási, megjelenését, képernyő idő, szoftverfrissítés, SIM telepítő megjelenítéséhez.
Válassza ki, amely a képernyők kihagyásához, lépjen a **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > Válasszon egy tokent > **Profilok** > Válasszon egy profilt > **tulajdonságok** > **beállítási asszisztens testreszabása** > Válasszon **elrejtése**  bármely képernyők kihagyásához a > **OK**.
Hozzon létre egy új profilt, vagy szerkessze a profil, ha a kiválasztott kihagyása képernyők kell szinkronizálni az Apple MDM-kiszolgáló. Így nem lesz késleltetés vesz fel a profil módosítása a felhasználók kiadhatnak az eszköz manuális szinkronizálása.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise-alkalmazás – hogy az alkalmazás üzembe helyezése <!-- 1171203 -->
Android-eszközökhöz a egy nem regisztrált alkalmazás alkalmazásvédelmi szabályzat regisztráció nélkül (alkalmazás-TUDJUK) a telepítési forgatókönyvben, így a felügyelt Google Play áruházbeli alkalmazások telepítése és az ÜZLETÁGI alkalmazások a felhasználók számára való használata. Pontosabban a végfelhasználók számára biztosíthat már nem igényel a végfelhasználók számára, hogy lazábbá tehető az eszközeik biztonsági irányelvei, tiltják azáltal, hogy telepítések az ismeretlen forrásból származó alkalmazás katalógus és telepítési élményt. Emellett ebben a telepítési forgatókönyvben egy jobb végfelhasználói élményt biztosít.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>2019. január 14 hete

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>A vállalat által birtokolt, teljes körűen felügyelt Android-eszközök támogatása előzetes verzió <!-- 1574342  -->
Az Intune mostantól támogatja a teljes körűen felügyelt Android-eszközök a vállalat által birtokolt "eszköz tulajdonosa" forgatókönyv, ahol eszközök szorosan által felügyelt IT és a rendszer az egyes felhasználókkal kapcsolódó. Ez lehetővé teszi a rendszergazdák számára a teljes eszköz kezelése, egy kiterjesztett tartomány nem érhető el a munkahelyi profilok házirend-vezérlők kényszerítésére, és korlátozza a felhasználók, alkalmazások telepítése csak a felügyelt Google Play áruházból. További információkért lásd: [beállítása az Intune-ban Android-regisztrációs teljes körűen felügyelt eszközök](android-fully-managed-enroll.md) és [a dedikált eszközök és a teljes körűen felügyelt eszközök regisztrálásához](android-dedicated-devices-fully-managed-enroll.md).  Ne feledje, hogy ez a funkció előzetes verzióban érhető el. Az Intune bizonyos funkciók, például a tanúsítványok, megfelelőségi és feltételes hozzáférés, nem érhetők el jelenleg az Android a teljes körűen felügyelt felhasználói eszközök.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>2019. január 7 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-app-pin----2298397---"></a>Intune az alkalmazás <!-- 2298397 -->
A rendszergazdáknak konfigurálhat egy végfelhasználó úgy megvárhatja, amíg meg kell változtatni a PIN-kód alkalmazás Intune-beli napok száma. Az új beállítás *PIN-kód visszaállítása után a napok számát* kiválasztásával az Azure Portalon érhető el, és **Intune** > **ügyfélalkalmazás**  >   **Az alkalmazásvédelmi szabályzatok** > **házirend létrehozása** > **beállítások** > **a hozzáférési követelmények**. Elérhető [iOS](app-protection-policy-settings-ios.md) és [Android](app-protection-policy-settings-android.md) eszközök esetében ez a funkció támogatja a pozitív egész értéket.


#### <a name="intune-device-reporting-fields----2748738---"></a>Az Intune eszköz reporting mezők <!-- 2748738 -->
Az Intune további eszköz területén, beleértve az alkalmazás regisztrációs azonosító, Android gyártója, modell, és biztonsági javítást, valamint IOS-es modell reporting biztosít. Az Intune-ban, ezek a mezők érhetők el kiválasztásával **ügyfélalkalmazás** > **alkalmazásvédelmi állapot** választva **alkalmazásvédelmi jelentés: iOS, Android**. Emellett ezek a paraméterek segítségével konfigurálja a **engedélyezése** lista az eszköz gyártója (Android), a **engedélyezése** lista az eszköz modellje (Android és iOS) és a minimális Android biztonsági javítási szintnek verzió beállítását. 


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és átkerülnek a saját konfigurációs profil <!-- 3322847 -->

Az Intune-ban a felügyeleti sablonok (**eszközkonfiguráció** > **felügyeleti sablonok**) jelenleg nyilvános előzetes verzióban érhető el. Ez a frissítés:

- Felügyeleti sablonok tartalmaznak körülbelül 300 beállítások, amelyek felügyelhetők az Intune-ban. Korábban ezek a beállítások csak megtalálható a Helyicsoportházirend-szerkesztő.
- Felügyeleti sablonok nyilvános előzetes verzióban érhetők el.
- Felügyeleti sablonok helyez át a **eszközkonfiguráció** > **felügyeleti sablonok** való **eszközkonfiguráció**  >   **Profilok** > **profil létrehozása** > a **Platform**, válassza a **Windows 10 és újabb** > a **profil típus**, válassza a **felügyeleti sablonok**.
- Jelentéskészítés engedélyezve van

További információk a funkcióról, nyissa meg [a csoportházirend-beállítások konfigurálása a Windows 10-es sablonok](administrative-templates-windows.md).

Érintett kiadások: Windows 10 és újabb

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Titkosítása és aláírás egy felhasználó több eszközt, az S/MIME használata  <!-- 1333642 -->
A frissítés része az új importált tanúsítványprofilt használó S/MIME e-mail-titkosítás (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > platform kiválasztása > **Importált PKCS-tanúsítvány** profiltípus). Az Intune-ban a tanúsítványok PFX formátumban importálhatók. Az Intune képes ugyanazokat a tanúsítványokat az egy felhasználó által regisztrált több eszközre is telepíteni. Ez a következőket is magában foglalja:
- A natív iOS-es e-mail-profil támogatja az S/MIME titkosítás PFX formátumú importált tanúsítványok használatával történő engedélyezését.
- A Windows Phone 10 rendszerű eszközök natív levelezőalkalmazása automatikusan az S/MIME tanúsítványt használja.
- A privát tanúsítványok több platformon is telepíthetők. A S/MIME-ot azonban nem minden e-mail-alkalmazás támogatja.
- Más platformokon az S/MIME engedélyezéséhez szükség lehet a levelező alkalmazás manuális konfigurálására.  
- Az S/MIME titkosítást támogató e-mail-alkalmazások esetleg az MDM által nem támogatható módon kezelik az S/MIME e-mail-titkosításhoz szükséges tanúsítványok fogadását, például a közzétevőjük tanúsítványtárából olvassák ki azokat.
Ez a szolgáltatás további információkért lásd: [való bejelentkezéshez, és e-mailek titkosítása S/MIME áttekintése](certificates-s-mime-encryption-sign.md).
Támogatott a következő rendszereken: Windows, Windows Phone 10-es, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Automatikus csatlakozás és szabályok továbbra is fennáll, DNS-beállítások használata a Windows 10-es és újabb rendszerű eszközök esetén új beállítások <!-- 1333665, 2999078 -->
A Windows 10-es és újabb rendszerű eszközök oldja meg a tartományok, mint a contoso.com DNS-kiszolgálók listáját tartalmazó VPN konfigurációs profilt is létrehozhat. Ez a frissítés a névfeloldáshoz új beállítást tartalmaz (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > kiválasztása **Windows 10-es és újabb verziók** tartozó platform > Válasszon **VPN** profiltípus > **DNS-beállítások** >**Hozzáadás**): 
- **Automatikus csatlakozás**: Amikor **engedélyezve**, az eszköz automatikusan csatlakozik a VPN-t, amikor egy eszköz kapcsolatba lép az ad meg, például a contoso.com tartományhoz.
- **Állandó**: Alapértelmezés szerint minden névfeloldási házirend táblája (NRPT) szabályok aktívak, amíg az eszköz csatlakoztatva van, a VPN-profil használatával. Ha a beállítás értéke **engedélyezve** az NRPT-szabály, a szabály aktív marad az eszközön, akkor is, ha a VPN bontja a kapcsolatot. A szabály marad, amíg a VPN-profil eltávolítása, vagy manuálisan eltávolítását a szabályt, amely végezhető PowerShell használatával.
[A Windows 10-es VPN-beállítások](vpn-settings-windows-10.md) beállításokat ismerteti. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Használja a megbízható hálózatok észlelése a Windows 10-es eszközök VPN-profilokhoz <!-- 1500165 -->
Megbízható hálózatok észlelése használatakor megakadályozhatja a VPN-profilok automatikusan hozzon létre egy VPN-kapcsolatot, amikor a felhasználó már szerepel a megbízható hálózat. Ez a frissítés engedélyezéséhez a megbízható hálózatok észlelése a Windows 10 és újabb verzióit futtató eszközökön DNS-utótagok adhat hozzá (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Windows 10 és újabb** tartozó platform > **VPN** profiltípus).
[A Windows 10-es VPN-beállítások](vpn-settings-windows-10.md) sorolja fel az aktuális VPN-beállításokat.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Több felhasználó által használt eszközök felügyelete a Windows Holographic for Business <!-- 1907917, 1063203 -->
Jelenleg konfigurálhatja megosztott PC-beállítások Windows 10 és Windows Holographic for Business-eszközök egyéni OMA-URI-beállítás használatával. Ez a frissítés egy új profil hozzá lesz adva közös használatú eszköz beállításainak konfigurálása (**eszközkonfiguráció** > **profilok** > **profillétrehozása**  >  **Windows 10 és újabb** > **megosztott több felhasználó-eszköz**).
Ez a funkció kapcsolatos további információkért lépjen [kezelheti a megosztott eszközök Intune-beállításokhoz](shared-user-device-settings.md).
Érintett kiadások: A Windows 10 és újabb verziók, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Új Windows 10 frissítési beállítások <!--2626030  2512994  -->
Az a [Windows 10-es frissítési körök](windows-update-for-business-configure.md), konfigurálhatja:
- **Automatikus frissítés viselkedése** – egy új beállítás, *visszaállítás alapértelmezettre* visszaállítani az eredeti automatikus frissítési beállítások gépeken futó Windows 10-es gépen a *2018. október frissítése*
- **A felhasználó felfüggesztése Windows-frissítések** – egy új szoftverhasználat-frissítési beállítást, amely lehetővé teszi, hogy Ön blokkolhatja vagy engedélyezheti a felhasználók számára történő telepítésének felfüggesztése konfigurálása a *beállítások* gépek. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS e-mail-profilok segítségével az S/MIME aláíráshoz és titkosításhoz <!-- 2662949 -->
Létrehozhat egy e-mail-profilt, amely különböző beállításokat tartalmazza. Ez a frissítés aláírása és titkosítása az iOS-eszközök e-mail-üzeneteket is használható az S/MIME beállításokat tartalmaz (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **iOS** tartozó platform > **E-mail** profiltípus).
[iOS e-mail-konfigurációs beállítások](email-settings-ios.md) beállításokat sorolja fel.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Néhány BitLocker-beállítások támogatja a Windows 10 Pro kiadás<!-- 2727036 -->
Hozhat létre, amely beállítja az endpoint protection-beállítások Windows 10 rendszerű eszközökön, beleértve a BitLocker konfigurációs profil. Ezt a frissítést az egyes BitLocker-beállítások Windows 10 Professional kiadást támogat. Ezen védelmi beállítások megtekintéséhez, keresse fel a [Endpoint protection-beállítások Windows 10-es](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Megosztott eszköz konfigurációja új üzenet a zárolási képernyőn iOS-eszközökhöz az Azure Portalon<!-- 2809362 -->
Ha iOS-eszközökhöz készült konfigurációs profilt hoz létre, adhat hozzá **megosztott eszköz konfigurációja** beállításokat adott szöveg megjelenítése a zárolási képernyőn. A frissítés tartalmazza a következő módosításokat: 
- A **megosztott eszköz konfigurációja** beállítások az Azure Portalon a rendszer átnevezi "Üzenet a zárolási képernyőn (csak felügyelt)" (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **iOS** tartozó platform > Válasszon **eszközfunkciók** profiltípus > **zárolása Üzenet képernyőn**).
- Zárolási képernyőjén üzenetek hozzáadásakor beszúrhat sorozatszám, eszköz nevét, vagy egy másik eszköz-specifikus érték a változóként **eszközcímke-információ** és **lábjegyzet a zárolási képernyőn**. Beírhatja például `Device name: {{devicename}}` vagy `Serial number is {{serialnumber}}` kapcsos zárójelek használatával. [iOS-jogkivonatok](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) felsorolja a rendelkezésre álló jogkivonatokat használhat.
[Beállításai üzenetek megjelenítéséhez a zárolási képernyőn](shared-device-settings-ios.md) beállításokat sorolja fel.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Új App Store, dokumentumok megtekintése, játékok eszközkorlátozásokra vonatkozó beállításai az iOS-eszközök hozzáadása <!-- 2827760-->
A **eszközkonfiguráció** > **profilok** > **profil létrehozása** > **iOS** számára Platform > **eszközkorlátozások** profiltípus > **App Store, dokumentumok megtekintése, játékok**, a következő beállítások lettek hozzáadva: Lehetővé teszi az ügyfelek írni a nem felügyelt ügyfelek fiókok nem felügyelt alkalmazásai olvasni a felügyelt ügyfelek fiókok ezek a beállítások megtekintéséhez nyissa meg a felügyelt alkalmazások [eszközkorlátozások iOS](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Vállalati Android-eszköz tulajdonosa eszköz új értesítés, útmutatók és keyguard beállítások <!-- 3201839 3201843 -->
A frissítés számos új funkciót, a vállalati Android-eszköz tartalmaz az eszköz tulajdonosa futtatásakor. Ezeket a funkciókat használ, lépjen a **eszközkonfiguráció** > **profilok** > **profil létrehozása** > a **Platform**, válassza a **Android Enterprise** > a **profiltípus**, válassza a **csak az eszköz tulajdonosa** > **eszköz Korlátozások**.

Új funkciók: 

- Tiltsa le a megjelenítése, beleértve a bejövő hívások, a rendszer riasztásai, rendszerhibák és több rendszer értesítései.
- Oktatóanyagok és útmutatók az első alkalommal megnyitott alkalmazások indítása kihagyása javasol.
- Tiltsa le a beállítások, például a kamera, értesítések, ujjlenyomattal történő Zárolásfeloldás speciális keyguard és egyebek.


A beállítások megtekintéséhez lépjen a [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Vállalati Android-eszköz tulajdonosa eszköz használhat a mindig bekapcsolva beállítású VPN-kapcsolatok <!-- 3202194 -->
Ebben a frissítésben mindig bekapcsolt VPN-kapcsolatok Android enterprise eszköz tulajdonosa eszközökön is használhatja. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
Engedélyezheti a mindig bekapcsolt VPN **eszközkonfiguráció** > **profilok** > **profil létrehozása**  >   **Android enterprise** tartozó platform > **eszközkorlátozások** az eszköz tulajdonosa csak > **kapcsolat** beállításait. A beállítások megtekintéséhez lépjen a [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Új beállítás az end folyamatok a Feladatkezelő Windows 10 rendszerű eszközökön <!-- 3285177 --> 
A frissítés tartalmaz egy új beállítás a Feladatkezelő használatát a Windows 10 rendszerű eszközökön folyamatait. Eszközkonfigurációs profil használatával (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > a **Platform** , válassza a **Windows 10-es** > a **profiltípus**, válassza a **eszközkorlátozások** > **általános** beállítások), engedélyezése vagy tiltása, ezt a beállítást választja.
Ezek a beállítások megtekintéséhez, keresse fel a [Windows 10-es eszközkorlátozási beállítások](device-restrictions-windows-10.md).
Érintett kiadások: Windows 10 és újabb


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Részletesebb regisztrációs korlátozási hiba üzenetkezelés <!-- 3111564 -->
Részletes hibaüzenetek a regisztrációs korlátozások nem teljesülnek esetén érhetők el. Tekintse meg ezeket az üzeneteket, lépjen a **Intune** > **hibaelhárítás** >, és ellenőrizze a regisztrációs hibák tábla. További információkért lásd: a [regisztrációs hibák listája](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="tenant-status-dashboard-----1124854---"></a>Bérlői állapot-irányítópultra  <!-- 1124854 -->
Az új [bérlői állapotlapon](tenant-status.md) egyetlen helyen tekintheti állapota és a kapcsolódó tudnivalókat a bérlő számára.  Az irányítópult négy területet oszlik:
- **Bérlő részletei** –, amely tartalmazza a bérlő nevét és helyét, információkat jelenít meg az MDM-szolgáltató az összes regisztrált eszközökre a bérlőben, és a licencek számát. Ez a szakasz felsorolja a szolgáltatás jelenlegi kiadása a bérlő számára is.
- **Összekötő állapota** -konfigurálta, és azokat, amelyek még nem engedélyez is listázhatja az elérhető összekötők információit jeleníti meg.  
   Minden összekötő az aktuális állapotától függően, hogy vannak megjelölve kifogástalan, figyelmeztetés vagy nem megfelelő. Válasszon egy összekötőt, és a áthatoló részletezést és a részletek megtekintéséhez vagy konfigurálásához, további információt.
-  **Az Intune szolgáltatás állapota** -jeleníti meg az aktív incidensek által érintett vagy valamilyen okból kimaradás lép adatait a bérlő számára. Ebben a szakaszban található információk az Office Üzenetközpontjában közvetlenül a rendszer lekéri.
-  **Az Intune hírek** – aktív üzeneteket jelenít meg a bérlő számára. Üzenetekben többek között az értesítéseket, amikor a bérlő kap a legújabb Intune-funkciók.  Ebben a szakaszban található információk az Office Üzenetközpontjában közvetlenül a rendszer lekéri.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Új Súgó és támogatás a Windows 10 céges portál élmény <!-- 1488939-->
Az új céges portál Súgó és támogatás oldalt segít a felhasználóknak, és segítséget kaphat az alkalmazás és a hozzáférési problémák hibáinak elhárítása. Az új lapon, e-mail-hiba- és diagnosztikai adatainak, és keresse meg a cég segélyszolgálat adatait. Ezek a gyakori kérdésekkel foglalkozó szakaszban az Intune-ban dokumentációkra mutató hivatkozásokat is találhat. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Új Súgó és támogatás élmény az Intune-hoz   <!-- #3307080 -->
Vezetünk az új Súgó és támogatás funkció az összes bérlőn néhány napon keresztül. Az új felület érhető el az Intune-hoz, és az Intune-ban paneleken lévő használatakor érhetők el a [az Azure portal](https://portal.azure.com/).
Az új felületen saját szavaival fejtheti ki problémáját, valamint hibaelhárítási ötleteket kaphat, és webalapú szervizelési tartalmakat találhat. Ezek a megoldások érhetők el keresztül egy szabályalapú machine learning algoritmus, felhasználó által készített lekérdezésekben. Probléma-specifikus útmutatás kiegészítéseként használhatja az új megkülönbözteti a kis létrehozási munkafolyamat e-mailben vagy telefonos támogatási eset nyitása. Az új felületet előre kijelölt beállítások biztosan megfeleljen az Súgó és támogatás megnyitásakor a konzol területéhez alapuló rögzített előző Súgó és támogatás élménye váltja fel. További információkért lásd: [hogyan kérhet támogatást a Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-for-apps----1081941---"></a>Hatókörcímkék alkalmazásokhoz <!-- 1081941 -->
Hatókörcímkék korlátozni a szerepköröket és alkalmazásokat hozhat létre. Hatókörcímke adhat hozzá egy alkalmazáshoz, így csak is az adott hatókörcímke hozzárendelt szerepkörrel rendelkező személyek hozzáférhetnek az alkalmazáshoz. Jelenleg a felügyelt Google Play vagy az Apple Volume Purchase Program (VPP) használatával megvásárolt alkalmazások Intune-hoz hozzáadott alkalmazások nem lehet hozzárendelni a hatókörcímkék (de támogatása a jövőben fognak érkezni). További információkért lásd: [használja a szűrő házirendek hatókörcímkék](scope-tags.md).

<!-- ########################## -->
## <a name="week-of-december-10-2018"></a>2018. December 10. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="updates-for-application-transport-security----748318---"></a>A Application Transport Security frissítések <!-- 748318 -->

A Microsoft Intune támogatja a Transport Layer Security (TLS) 1.2-es + kategóriaelső a titkosítás, annak biztosítása érdekében, az Intune alapértelmezés szerint a biztonságosabb és igazodva más Microsoft-szolgáltatások, például a Microsoft Office 365 biztosít. Ez a követelmény teljesítéséhez az iOS és MacOS rendszerű céges portálok kényszeríti az Apple frissített Application Transport Security (ATS) követelményeket, amelyek megkövetelik a TLS 1.2-es +. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás érint az iOS és MacOS-es céges portál alkalmazások használata. További információkért lásd: a [Intune támogatási blogján](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Az Intune App SDK támogatni fogja a 256 bites titkosítási kulcsok <!-- 1832174 -->
Az Androidhoz készült Intune App SDK mostantól 256 bites titkosítást kulcsokat használ, ha az alkalmazásvédelmi szabályzatok engedélyezve van a titkosítási. Az SDK továbbra is támogatja a 128 bites kulcsok tartalmat és a régebbi SDK-t használó alkalmazások kompatibilitását.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>MacOS-eszközökhöz szükséges a Microsoft automatikus frissítési verzió 4.5.0 <!-- 3503442 -->
A folytatáshoz frissítéseknek a fogadása a vállalati portál és más Office-alkalmazások az Intune által felügyelt macOS-eszközökhöz a Microsoft automatikus frissítési 4.5.0 kell frissítenie. Előfordulhat, hogy a felhasználóknak már van ez a verzió az Office-alkalmazásokban.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Az Intune macOS 10.12 vagy újabb verziója szükséges <!-- 2827778 -->
Az Intune most már a macOS 10.12 vagy újabb verziója szükséges. MacOS előzetes verziókat használó eszközök regisztrálása az Intune-ban a vállalati portál nem használható. Szeretne kapni a Távsegítség és az új funkciók, a felhasználók kell frissítheti az eszközt a macOS 10.12 vagy újabb verzió és a vállalati portál frissítése a legújabb verzióra.

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>2018. November 26 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>A vállalat által birtokolt felügyelt iOS-eszközökön lévő alkalmazások eltávolítása <!-- 1281677 -->

Bármilyen alkalmazást a vállalat által birtokolt felügyelt iOS-eszközök távolíthatja el. Ha az **Eltávolítás** hozzárendelési típussal megcélozza a felhasználó- vagy eszközcsoportokat, akkor bármilyen alkalmazást el tud távolítani. Személyes és nem felügyelt iOS-eszközök esetében a továbbiakban csak az Intune használatával telepített alkalmazásokat tudja majd eltávolítani.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Az Intune Win32 alkalmazás tartalmának letöltése <!-- 2617320 -->
A Windows 10 RS3 és fent az ügyfelek letöltik Intune Win32 alkalmazás tartalmának kézbesítésoptimalizálás összetevőt a Windows 10-es ügyfél használ. Kézbesítésoptimalizálás társ-társ funkciókat biztosít, amelyek alapértelmezés szerint van kapcsolva. Kézbesítésoptimalizálás konfigurálható a csoportházirend és a jövőben az Intune MDM-n keresztül További információkért lásd: [kézbesítés optimalizálása Windows 10-es](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Felhasználói eszközök és alkalmazások tartalom menü <!-- 2771453 -->
A végfelhasználók most már használhatja helyi menü eszközön, és az alkalmazások indításához a gyakori műveletekhez, például egy eszköz átnevezése vagy a megfelelőség ellenőrzése.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Egyéni háttér beállítása kezdőlap képernyő felügyelt alkalmazásban  <!-- 3041945 -->
Egy beállítás, amely lehetővé teszi, hogy Ön szabja testre a kezdőlap képernyő felügyelt alkalmazást az Android Enterprise, a több alkalmazás, a teljes képernyős mód eszközökön háttér adunk hozzá.  **Egyéni URL-háttér** konfigurálásához nyissa meg az Azure portalon az Intune > Eszközkonfiguráció elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat kioszkbeállításainak szerkesztéséhez.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Alkalmazás alkalmazásvédelmi szabályzat-hozzárendelés mentése és alkalmazása <!-- 3104570 -->
Keresztül most már hatékonyabban szabályozhatja a [alkalmazásvédelmi szabályzat-hozzárendelések](app-protection-policies.md#deploy-a-policy-to-users). Amikor kiválaszt *hozzárendelések* állítsa be, vagy szerkessze a szabályzat hozzárendeléseinek, meg kell **mentése** a konfigurációt a módosítás alkalmazása előtt. Használat **elveti** törölje az összes módosítást, anélkül, hogy bármely módosításainak mentése a belefoglalási vagy kizárási sorolja fel.  Mentés igénylő vagy elvetésének csak a kívánt felhasználók alkalmazásvédelmi szabályzat vannak rendelve.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Új Microsoft Edge böngésző beállításai Windows 10-es és újabb verziók <!-- 3174639 -->
A frissítés segítségével szabályozhatja, és kezelheti az eszközökön a Microsoft Edge böngésző új beállításokat tartalmazza. Ezek a beállítások listáját lásd: [eszközkorlátozási Windows 10-es (és újabb)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Új alkalmazások támogatják az alkalmazásvédelmi szabályzatokkal <!-- 3330037 -->
A következő alkalmazások kezelheti [az Intune alkalmazásvédelmi szabályzatai](app-protection-policies.md):
- Stream (iOS)
- Teendők (Android, iOS)
- A PowerApps (Android, iOS)
- A folyamat (Android, iOS)

Használja alkalmazásvédelmi szabályzatok vállalati adat- és adatátviteli ezeket az alkalmazásokat, például a többi Intune-szabályzat által felügyelt alkalmazások védelmére. Megjegyezés: Ha a Flow még nem láthatók a konzolon, hozzáadhat folyamatot, ha hoz létre vagy szerkeszt, és az alkalmazásvédelmi szabályzatok. Ehhez használja a **+ további alkalmazások** lehetőséget, majd adja meg a *Alkalmazásazonosító* a Flow a beviteli mezőben. Android használatra *com.microsoft.flow*, és az iOS használja *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>iOS és macOS-verziószámok és buildelési számokat jelennek meg <!-- 1892471 -->
Az **Eszközmegfelelőség** > **Eszközmegfelelőség** megjeleníti az iOS és macOS operációs rendszerek verzióit, amelyek elérhetők a megfelelőségi szabályzatokkal. A frissítés magában foglalja a buildszám, a mindkét platform konfigurálható.
A biztonsági frissítések megjelenésekor az Apple általában megtartja a verziószámot, de a buildszám változik. A megfelelőségi szabályzat buildszámának segítségével könnyen ellenőrizheti, hogy telepítve van-e a biztonsági frissítés.
Ez a funkció használatához lásd: [iOS](compliance-policy-create-ios.md#device-health) és [macOS](compliance-policy-create-mac-os.md#device-properties) megfelelőségi szabályzatokat.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Frissítési körök váltotta fel kézbesítésoptimalizálás beállítások Windows 10-es és újabb <!-- 2753807 -->
Kézbesítésoptimalizálás egy új profilt a Windows 10-es és újabb verziók. Ez a funkció a szoftverfrissítések továbbítására a szervezetnél található eszközökön hatékonyabbá élményt nyújt. Ez a frissítés is segítséget nyújthat a beállításokat a konfigurációs profil használatával az új és meglévő frissítési körök.
Kézbesítési optimalizálás konfigurációs profil beállítása: [Windows 10 (és újabb) kézbesítésoptimalizálási beállításait](delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Új eszköz eszközkorlátozásokra vonatkozó beállítások az iOS és macOS-eszközök <!-- 2827760 -->
A frissítés az iOS és macOS-eszközökhöz IOS 12 megjelent új beállításokat tartalmazza:

**iOS-beállítások**: 
- Általános: Alkalmazás eltávolításának zárolása (csak felügyelt)
- Általános: Blokk USB korlátozott módban (csak felügyelt)
- Általános: A kényszerített automatikus dátum és idő (csak felügyelt)
- Jelszó: Letilthatja a jelszó automatikus kitöltés (csak felügyelt)
- Jelszó: Letiltja a jelszó közelségi kérelmeket (csak felügyelt)
- Jelszó: Letilthatja a jelszó megosztása (csak felügyelt)

**macOS-beállításokat**: 
- Jelszó: Jelszó automatikus kitöltés letiltása
- Jelszó: Jelszó közelségi-kérések blokkolása
- Jelszó: Letilthatja a jelszó megosztása

Ezekkel a beállításokkal kapcsolatos további tudnivalókért lásd: [iOS](device-restrictions-ios.md) és [macOS](device-restrictions-macos.md) eszközkorlátozásokra vonatkozó beállításai.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Válassza ki, a regisztrálási állapot oldal nyomon alkalmazások<!-- 2531007 -->
Kiválaszthatja, melyik alkalmazások nyomon a regisztrálási állapot oldal. Ezek az alkalmazások telepítve vannak, amíg a felhasználó az eszköz nem használható. További információkért lásd: [beállítása egy regisztrálási állapot oldal](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Keresse meg az Autopilot-eszközök sorozatszám alapján <!--2595788 -->
Most már kereshet az Autopilot-eszközök sorozatszám alapján. Ehhez válassza ki a **eszközregisztráció** > **Windows regisztrációs** > **eszközök** > írja be a sorozatszám a **keresés alapján sorozatszám** box > nyomja le az Enter billentyűt.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Nyomon követheti az Office ProPlus telepítése <!--2620217 -->
Felhasználók nyomon követheti a telepítés előrehaladását [Office ProPlus](apps-add-office365.md) használatával a [regisztrálási állapot oldal](windows-enrollment-status.md). További információkért lásd: [beállítása egy regisztrálási állapot oldal](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Riasztások lejáró VPP-token vagy a céges portál futó alacsony licenc <!-- 2237572 -->
Ha előre ellátja a DEP-regisztráció során a céges portál Volume Purchase Program (VPP) használ, Intune riasztást küld, amikor a VPP-token érvényessége hamarosan lejár, és a licencek a céges portál kevés.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>az Apple School Manager-fiókok támogatása macOS Készülékregisztrációs Program <!--3006133 -->
Az Intune már támogatja a macOS-eszközök az Apple School Manager-fiókok a Készülékregisztrációs programmal.  További információkért lásd: [automatikusan regisztrálni a macOS-eszközök az Apple School Manager vagy a Készülékregisztrációs Program](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Új Intune eszköz-előfizetés Termékváltozat <!--3312071-->
A vállalatok számára az eszközkezelés költségeinek csökkentéséhez már elérhető egy új, eszközalapú előfizetési termékváltozat. Ennek az Intune-beli eszköz-termékváltozatnak a licencelése eszközönként történik, havi elszámolással. Az ár a licencprogramtól függően változik. Közvetlenül a Microsoft 365 felügyeleti központban, és keresztül elérhető a [nagyvállalati szerződés](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and szolgáltatási szerződését](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [a Microsoft Open Szerződések](https://partner.microsoft.com/licensing/licensing-agreements), és [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Eszközkezelés

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Ideiglenesen letilthatja az Android-eszközökön módosításokat a teljes képernyős mód <!-- 3041935 -->
Ha többalkalmazásos kioszkmódban használ Android-eszközöket, előfordulhat, hogy a rendszergazdáknak módosításokat kell végrehajtaniuk az eszközön. Ez a frissítés új lehetővé teszi, hogy a rendszergazda ideiglenesen felfüggesztése teljes képernyős mód használata a PIN-kódot, és hozzáférhet a teljes eszköz a többalkalmazásos kioszk beállításokat tartalmaz.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Az Android Enterprise teljes képernyős eszközökön virtuális Kezdőlap gomb engedélyezése  <!-- 3042021 -->
Az új beállítás segítségével a felhasználók az eszközön lévő többfunkciós gombra való koppintással válthatnak a többalkalmazásos kioszkeszközökön található Managed Home Screen alkalmazás és az egyéb hozzárendelt alkalmazások között. Ez a beállítás igen hasznosnak bizonyul olyan esetekben, amikor a felhasználó kioszkalkalmazása nem reagál megfelelően a „vissza” gomb megnyomására. Ezt a beállítást Ön konfigurálni tudja majd az egyetlen célra használható céges Android-eszközökön. A **Virtuális kezdőképernyő gomb** be- és kikapcsolásához válassza az Azure portalon az Intune > Eszközök konfigurálása elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat kioszkbeállításainak szerkesztéséhez.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>2018. November 12 hete

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Hálózati hozzáférés-vezérlés (NAC) iOS-es Citrix egyszeri bejelentkezés támogatása <!-- 3259404 -->

A Citrix Citrix-átjáróra, hogy a hálózati hozzáférés-vezérlés (NAC) a Citrix egyszeri bejelentkezés az Intune-ban iOS-es frissítést adott ki. Részvétel a VPN-profilon belül egy Eszközazonosítót tartalmazzák az Intune-ban, és juttathatja el ezt a profilt az iOS-eszközökön. Szüksége lesz a legújabb frissítés telepítése a Citrix-átjáróra a funkció használatához.

[VPN-beállítások konfigurálása az iOS-eszközökön](vpn-settings-ios.md#base-vpn-settings) további információt nyújt az NAC, beleértve néhány további követelményeket is. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>2018. november 5-i hét

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Támogatja az iOS 12 OAuth iOS e-mail-profilok <!--2155106 -->

Az Intune iOS e-mail-profiljai támogatják az iOS 12-es nyílt engedélyezést (OAuth). Ennek a funkciónak a megtekintéséhez hozzon létre egy új profilt (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **iOS** a platformhoz > **E-mail** a profiltípushoz), vagy frissítsen egy létező iOS-es e-mail-profilt. Ha engedélyezi az OAuth-hitelesítést egy olyan profilban, amely már üzembe van helyezve a felhasználóknál, akkor a felhasználóknak újra el kell végezniük a hitelesítést, és le kell ismét tölteniük az e-mailjeiket.

Az [iOS-es e-mail-profilok](email-settings-ios.md) szakaszban további információt talál az OAuth e-mail-profilban való használatáról.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Az autopilot hibrid Azure Active Directory támogatja a csatlakoztatott eszközök (előzetes verzió) <!-- 1048100-->
Az Autopilot segítségével mostantól hibrid, Azure Active Directory-hoz csatlakoztatott eszközöket állíthat be. A hibrid Autopilot funkció használatához az eszközöket csatlakoztatni kell a szervezet hálózatához. További információt a [Deploy hybrid Azure AD joined devices using Intune and Windows Autopilot](windows-autopilot-hybrid.md) (Hibrid, Azure AD-hez csatlakoztatott eszközök üzembe helyezése az Intune és a Windows Autopilot használatával) című cikkben talál.
Ez a funkció néhány napon belül kerül bevezetésre a felhasználók között. Előfordulhat tehát, hogy Ön nem tudja követni ezeket a lépéseket addig, amíg a fiókjában is meg nem jelenik ez az újítás.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>2018. október 29-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Nem biometrikus PIN-kód kérése után egy megadott időkorlát <!-- 1506985 -->
Mivel az Intune nem biometrikus PIN-kód megadását írja elő a rendszergazda által meghatározott időtúllépés után, ezzel magasabb szintű védelmet biztosít a mobilalkalmazás-kezelést (MAM) engedélyező alkalmazások számára azáltal, hogy korlátozza a biometrikus azonosításnak a céges adatokhoz való hozzáférés érdekében történő használatát. A beállítások APP/MAM szolgáltatást engedélyező alkalmazásokhoz való hozzáférésre használt Touch ID (iOS), Face ID (iOS), Android Biometric és egyéb jövőbeli biometrikus hitelesítési módszereket alkalmazó felhasználókra vonatkoznak. E beállítások segítségével az Intune-rendszergazdák részletesen szabályozhatják a felhasználók hozzáférését, így megelőzhetik azokat az eseteket, amikor a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert használó eszközről céges adatok juthatnak illetéktelen felhasználók birtokába. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza az **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget. A hozzáférésre vonatkozó beállításokról az [iOS-beállítások](app-protection-policy-settings-ios.md#access-requirements) és az [Android-beállítások](app-protection-policy-settings-android.md#access-requirements) oldalon tájékozódhat.

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>A regisztrált eszközökre az Intune APP a beállítások átvitele adatok a mobileszköz-kezelési iOS rendszeren <!-- 2244713 -->
Elkülönítheti az Intune APP adatátviteli beállítások iOS rendszerű, MDM-et engedélyező eszközökön való szabályozását a regisztrált felhasználók személyazonosságának megadásától, amely Egyszerű felhasználónévként (UPN) is ismert. Az IntuneMAMUPN-t nem használó rendszergazdák nem tapasztalnak majd működésbeli változást. Ha ez a funkció elérhetővé válik, a regisztrált eszközök adatátviteli viselkedésének vezérléséhez IntuneMAMUPN-t használó rendszergazdáknak át kell tekinteniük az új beállításokat, és szükség szerint frissíteniük kell APP-beállításaikat.

#### <a name="windows-10-win32-apps----2617325---"></a>A Windows 10-es Win32-alkalmazások <!-- 2617325 -->
Konfigurálhatja a Win32-alkalmazások telepítését az egyes felhasználók felhasználói környezetében, de választhatja azt is, hogy az eszköz összes felhasználója esetében telepíti az alkalmazást.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Windows-Win32-alkalmazások és a PowerShell-parancsprogramok <!-- 2617330 -->
A végfelhasználóknak nem kell többé bejelentkezniük az eszközön a Win32-alkalmazások telepítéséhez és a PowerShell-parancsfájlok végrehajtásához. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Ügyféloldali alkalmazás telepítésének hibaelhárítása <!-- 1363711 -->
Az ügyfélalkalmazások telepítésével kapcsolatban felmerülő hibák elhárításához a **Hibaelhárítás** panelen található **Alkalmazástelepítés** címkével ellátott oszlopban talál segítséget. A **Hibaelhárítás** panel megtekintéséhez válassza az Intune-portálon a **Súgó és támogatás** részben található **Hibaelhárítás** elemet.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Hálózati hozzáférés-vezérlő támogatása az IOS-es VPN-ügyfelek <!-- 1333693 -->
Az ebben a frissítésben biztosított új beállítás lehetővé teszi a Hálózati hozzáférés-vezérlést (NAC), amikor VPN-konfigurációprofilt hoz létre a Cisco AnyConnect, az F5 Access és a Citrix SSO for iOS esetében. E beállítással az eszköz NAC-azonosítója feltüntethető a VPN-profilban. Jelenleg nincsenek olyan VPN-ügyfelek vagy NAC-partnermegoldások, amelyek támogatnák ezt az új NAC-azonosítót, de [támogatási blogbejegyzésünkből](ttps://aka.ms/iOS12_and_vpn) értesülhet az esetleges változásokról.

A NAC használatához a következőt kell tennie:
1. Jelentkezzen be, és állítsa be, hogy az Intune feltüntesse az eszközazonosítókat a VPN-profilokban.
2. Frissítse a NAC-szolgáltató szoftverét/belső vezérlőprogramját a tőle közvetlenül kapott útmutatást követve.

Erről az iOS-VPN-profilon belüli beállításról a [VPN-beállítások hozzáadása iOS rendszerű eszközökön a Microsoft Intune-ban](vpn-settings-ios.md) című cikkben tájékozódhat. A hálózati hozzáférés-vezérlésről a [Hálózati hozzáférés-vezérlés (NAC) integrálása az Intune-nal](network-access-control-integrate.md) című cikkben tájékozódhat. 

A következőre vonatkozik: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Egy eszközről törölni egy e-mail profilt, még akkor is, ha csak egy e-mail-profil <!-- 1818139 -->
Korábban nem tudott e-mail-profilt eltávolítani az adott eszközről, *ha* az volt az egyetlen e-mail-profil rajta. E frissítésnek köszönhetően ez most megváltozik. Mostantól akkor is eltávolíthat e-mail-profilt, ha az az egyetlen, amely az eszközön található. További információt [Az e-mail-beállítások konfigurálása a Microsoft Intune-ban](email-settings-configure.md) című GitHub dokumentumban talál.

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell-parancsprogramok és aad-ben <!-- 2309469 -->
Az Intune-beli PowerShell-parancsfájlok beállíthatók úgy, hogy AAD-eszközbiztonsági csoportokat célozzanak meg.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Új "kötelező jelszó típusa" alapértelmezett beállítása az Android, Android enterprise<!-- 2649963 -->
Új megfelelőségi szabályzat létrehozásakor (Platform > Rendszerbiztonság > **Intune** > **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Android** vagy **Android Enterprise**) a következőképpen módosul a **Jelszó kötelező típusa** beállítás alapértelmezett értéke:

Forrás: Az eszköz alapértelmezett: Legalább számok

Érintett kiadások: Android, Android Enterprise

Ezekről a beállításokról az [Android](compliance-policy-create-android.md) és az [Android Enterprise](compliance-policy-create-android-for-work.md) oldalakon tájékozódhat.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Használja a Windows 10-es Wi-Fi profil előmegosztott kulccsal <!-- 2662938 -->
E frissítés révén előre megosztott kulcsot (PSK) használhat a WPA/WPA2 személyes biztonsági protokollal a Windows 10-es Wi-Fi-konfigurációprofil hitelesítéséhez. Meghatározhatja a mért hálózatokra vonatkozó költségkonfigurációt is a 2018. október 10-i frissítésű Windows 10 rendszert használó eszközök esetében.

Jelenleg importálni kell a Wi-Fi-profilokat vagy egyéni profilt kell létrehozni az előre megosztott kulcsok használatához. A jelenlegi beállításokat a [Windows 10 Wi-Fi beállításait](wi-fi-settings-windows.md) ismertető cikk írja le. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Az eszközökről származó PKCS- és SCEP-tanúsítványok eltávolítása <!-- 3218390 -->
Bizonyos forgatókönyvek esetében a PKCS- és SCEP-tanúsítványok akkor is megmaradnak az eszközökön, ha szabályzatot távolít el egy csoportból, konfigurációt vagy telepített megfelelőséget töröl, illetve ha valamelyik rendszergazda meglévő SCEP- vagy PKCS-profilt frissít. E frissítéssel változik ez a működési logika. Egyes forgatókönyvek esetében eltávolítjuk az eszközökről a PKCS- és a SCEP-tanúsítványokat, míg mások esetében a tanúsítványok megmaradnak az eszközön. E tanúsítványokról a [SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban](remove-certificates.md) című cikkben tájékozódhat.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>MacOS-eszközökre vonatkozó megfelelőségi forgalomirányító használata <!-- 2504381 -->
E frissítés tartalmazza a macOS rendszerre készült Gatekeeper technológiát, amely az eszközök megfelelőségének kiértékelésére szolgál. A Gatekeeper funkció beállításáról a [macOS-es eszközök megfelelőségi szabályzatainak hozzáadása az Intune-nal](compliance-policy-create-mac-os.md) című cikkben tájékozódhat.


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="enrollment-abandonment-report----1382924---"></a>Regisztráció való lemondás jelentés <!-- 1382924 -->
A regisztrációmegszakítással kapcsolatos további részleteket tartalmazó új jelentés a **Eszközregisztráció** > **Figyelés** szakaszban áll rendelkezésre. További információt a [Céges portállal történő regisztráció megszakítása – jelentés](enrollment-report-company-portal-abandon.md) című cikkben talál.

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Új Azure Active Directory – használati feltételek funkció <!-- 2870393 -->
Az Intune-ra vonatkozó Általános Szerződési Feltételek helyett mostantól használhatja az Azure Active Directory-ra vonatkozó Általános Szerződési Feltételek funkciót. Az Azure AD Használati feltételek funkciója nagyobb rugalmasságot biztosít abban, hogy mely feltételek jelenjenek meg és mikor, továbbá jobb honosítástámogatást, jobb feltételmegjelenítés-vezérlést és jobb jelentéskészítési funkciókat nyújt. Az Azure AD Használati feltételek funkciójához Prémium P1 szintű Azure Active Directory szükséges, amely az Enterprise Mobility + Security E3 csomagnak is része. További információt [A céges felhasználói hozzáférési használati feltételek kezelése](terms-and-conditions-create.md) című cikkben talál.

#### <a name="android-device-owner-mode-support---3188762--"></a>Androidos eszköz tulajdonosa mód támogatása <!--3188762-->
A Samsung Knox Mobile Enrollment esetében az Intune mostantól támogatja az eszközöknek az Android Device Owner kezelési módra való regisztrációját. A Wi-Fi- és mobilhálózatok felhasználói az eszköz első bekapcsolása után csupán néhány érintéssel regisztrálhatnak. További információ: [Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Eszközkezelés
#### <a name="new-settings-for-software-updates------1907869---"></a>A szoftverfrissítések új beállításai   <!-- 1907869 -->  
- Mostantól konfigurálhatja az egyes riasztási végfelhasználók számára a legújabb szoftverfrissítések telepítésének befejezéséhez szükséges újraindítást kapcsolatos értesítéseket.   
- Konfigurálhat egy újraindítás kapcsolatos figyelmeztető üzenet újraindul, a munkaidőn kívül történik, amely támogatja a BYOD-forgatókönyvekhez.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Csoportban a Windows Autopilot-ban regisztrált eszközök korrelátor azonosító alapján <!-- 2075110 -->
Az Intune mostantól támogatja a Windows rendszerű eszközök korrelátorazonosító alapján történő csoportosítását, ha regisztrációjuk az [Autopilot for existing devices](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) (Autopilot meglévő eszközökön) című cikkben leírtak szerint, a Configuration Manager használatával történt. A korrelátorazonosító az AutoPilot konfigurációs fájljának egyik paramétere. Az Intune az [Azure AD-eszközök enrollmentProfileName attribútumát](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) automatikusan az ezzel megegyező „OfflineAutopilotprofile-<correlator ID>” attribútumra állítja be. Így tetszőleges dinamikus Azure AD-csoportok hozhatók létre korrelátorazonosító alapján az offline Autopilot-regisztrációk enrollmentprofileName attribútuma használatával. További információt a [Windows Autopilot for existing devices](enrollment-autopilot.md#windows-autopilot-for-existing-devices) (Windows Autopilot meglévő eszközökön) című cikkben talál.

#### <a name="intune-app-protection-policies----2984657---"></a>Az Intune alkalmazásvédelmi szabályzatai <!-- 2984657 -->
Az Intune alkalmazásvédelemre vonatkozó szabályzatának segítségével többféle adatvédelmi beállítást konfigurálhat az Intune védelemben részesített alkalmazásaira, például a Microsoft Outlookra és a Microsoft Wordre vonatkozóan. E beállítások megjelenését és működését az [iOS](app-protection-policy-settings-ios.md) és az [Android](app-protection-policy-settings-android.md) esetében is módosítottuk, így könnyebben találhatja meg az egyes beállításokat. A szabályzatra vonatkozó beállítások három kategóriába tartoznak:
- **Adatáthelyezés** – Ebbe a csoportba tartoznak az adatszivárgás elleni védelem (DLP) vezérlői, például a kivágás, a másolás, a beillesztés és a mentés másként művelet korlátozásai. Ezek a beállítások szabják meg, hogy hogyan kezelhetik a felhasználók az adatokat az alkalmazásokban.
- **Hozzáférési követelmények** – Ez a csoport tartalmazza a PIN-kód alkalmazásonkénti beállítási lehetőségeit, amelyek meghatározzák, hogyan férnek hozzá a végfelhasználók az alkalmazásokhoz egy munkahelyi környezetben.  
- **Feltételes bevezetés** – Ebbe a csoportba olyan beállítások tartoznak, mint az operációs rendszerre vonatkozó minimális beállítások, a függetlenítésészlelés és a rootolt eszközök felderítése, valamint az offline türelmi időszakok.  
  
A beállítások funkciói nem módosulnak, de könnyebben találhatók majd meg, ha Ön a szabályzatlétrehozási folyamatban dolgozik.

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Az Intune támogatni fogja 8 GB maximális csomag mérete, a LOB-alkalmazások <!-- 1727158 -->
Az Intune 8 GB-ra növelte a Line-of-business- (LOB) alkalmazások maximális csomagméretét. További információt az [Alkalmazások hozzáadása a Microsoft Intune-hoz](apps-add.md) című cikkben talál.

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>A vállalati portál alkalmazás márka egyéni rendszerkép hozzáadása <!-- 1916266 -->
A Microsoft Intune rendszergazdájaként Ön olyan egyéni márkaemblémát tölthet fel, amely háttérképként jelenik majd meg a felhasználónak az iOS Céges portál alkalmazásban található profiloldalán. További információkat a Céges portál alkalmazás konfigurálásáról [a Microsoft Intune Céges portál alkalmazás konfigurálását](company-portal-app.md) ismertető cikkből tudhat meg.

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Az Intune megőrzi a honosított Office nyelvi, amikor a felhasználók gépein Office frissítése <!-- 2971030 -->
Amikor az Intune telepíti az Office-t a végfelhasználó számítógépén, a végfelhasználók automatikusan ugyanazt a nyelvcsomagokat kapják meg, amelyekkel már eddig is rendelkeztek a korábbi .MSI Office-telepítések esetében. További információt az [Office 365-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal](apps-add-office365.md) című cikkben talál.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Új Intune támogatási szolgáltatásokat a Microsoft 365-kezelési portálon <!-- 3076965 -->
Hamarosan új Súgó és támogatás felületet vezetünk be az Intune esetében a [Microsoft 365 Eszközkezelési portálon]( http://devicemanagement.microsoft.com). Az új felületen saját szavaival fejtheti ki problémáját, valamint hibaelhárítási ötleteket kaphat, és webalapú szervizelési tartalmakat találhat. Ezeket a megoldásokat szabályokon alapuló gépi tanulási algoritmus biztosítja a felhasználók kérései alapján.  

A problémákra összpontosító útmutatáson túl használhatja az új esetkészítő munkafolyamatot is, amellyel e-mailen vagy telefonon keresztül nyithat támogatási eseteket.  

A bevezetésben részt vevő ügyfelek esetében ez az új felület lép a jelenlegi Súgó és támogatás felület helyébe, rajta az előre kijelölt lehetőségek olyan állandó készletével, amely a konzol azon területén alapul, ahová Ön a Súgó és támogatás megnyitásakor kerül.  

*Ez az új Súgó és támogatás felület csak a bérlők bizonyos részére (de nem mindegyikükre) vonatkozóan kerül bevezetésre, és az Eszközkezelési portálon érhető el. Az új felület használóit véletlenszerűen választjuk ki az Intune rendelkezésre álló bérlői közül. A bevezetés bővítésekor új bérlőket adunk hozzá.*  

További információkért lásd: [Súgó és támogatás élmény](get-support.md#help-and-support-experience) a hogyan kérhet támogatást a Microsoft Intune-hoz.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Intune – előzetes verzió érhető el a PowerShell-modul <!-- 951068 -->
A [GitHub]( https://aka.ms/intunepowershell) felületén mostantól új PowerShell-modul áll rendelkezésre, amely a Microsoft Graph-on keresztül nyújt támogatást az Intune API-hez. A modul használatáról az ugyanezen a helyen található README részen tájékozódhat. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>2018. október 15-i hét

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>PIN-kód kérése az ujjlenyomatok módosításakor vagy face ID iOS-eszközön  <!-- 2637704  -->
A felhasználókat mostantól PIN-kód megadására kéri a rendszer azt követően, hogy biometrikus módosításokat hajtanak végre iOS-eszközükön. Ebbe beletartoznak a regisztrált ujjlenyomat- és face ID-azonosítást érintő módosítások is. A kérés időzítése attól függ, hogy a *hozzáférés újraellenőrzésére vonatkozó követelmények* konfigurációja hány perc után lépi túl az időt.  Ha nincs beállítva PIN-kód, a rendszer új beállítására kéri a felhasználót. 
 
Ez a funkció csak az iOS-ben érhető el, és a működéséhez szükséges az alkalmazások integrálása az Intune APP SDK for iOS 9.0.1-es vagy újabb verziójával. Az SDK-integráció szükséges a viselkedés kényszeríthetőségéhez a megcélzott alkalmazásoknál. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Néhány alkalmazás, amely ezek között szerepelhet: WXP, Outlook, Managed Browser és Yammer.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>2018. október 1-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Hozzáférési kulcs profil tulajdonságainak a vállalati portál alkalmazás használatával <!-- 772203 -->
A végfelhasználók mostantól a Céges portál alkalmazással hozzáférhetnek a legfontosabb fióktulajdonságokhoz és -műveletekhez, például a jelszó-visszaállításhoz. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>3. fél billentyűzetek blokkolhatja iOS APP beállításai <!-- 1248481 -->
Az Intune-rendszergazdák az iOS-es eszközökön letilthatják a harmadik féltől származó billentyűzeteket, ha azok a szabályzat által védett alkalmazásokon hozzáférnek a céges adatokhoz. Ha az alkalmazásvédelmi szabályzat (APP) a harmadik félhez tartozó billentyűzetek letiltására van beállítva, az eszköz használója üzenetet kap, amikor először fér hozzá ilyen billentyűzettel a céges adatokhoz. A natív billentyűzeten kívül minden más lehetőség le van tiltva, és a felhasználók nem láthatják ezeket. A felhasználók csak egyszer látják az üzenetet. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Felhasználóifiók-hozzáférés felügyelt Android és IOS rendszerű eszközökön az Intune-alkalmazások <!-- 1248496 -->
A Microsoft Intune rendszergazdájaként szabályozhatja, hogy melyik felhasználói fiókok legyenek hozzáadva a Microsoft Office-alkalmazásokhoz a felügyelt eszközökön. A hozzáférést korlátozhatja csak a szervezeti felhasználói fiókokra, és blokkolhatja a személyes fiókok használatát a regisztrált eszközökön. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Az Outlook iOS és Android-alkalmazás-konfigurációs szabályzat <!--1828527 -->
Mostantól létrehozhat egy Outlook iOS és Android alkalmazáskonfigurációs szabályzatot iOS és Android rendszerekhez az olyan helyszíni felhasználók számára, akik az alapszintű hitelesítést és az ActiveSync protokollt használják. További konfigurálási beállítások lesznek hozzáadva az engedélyezésüket követően az iOS és Android rendszerre készült Outlookhoz.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Az Office 365 Pro Plus nyelvi csomagok <!-- 1833450 -->
Az Intune rendszergazdájaként további nyelveket helyezhet üzembe az Intune által felügyelt Office 365 Pro Plus alkalmazások számára. Az elérhető nyelvek listája tartalmazza a nyelvi csomag **Típusát** (alap, részleges vagy nyelvi ellenőrzési) is. Az Azure Portalon válassza a **Microsoft Intune** > **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen, az **Alkalmazástípusok** listáján, válassza az **Office 365 csomag** alatti **Windows 10** lehetőséget. Az **Alkalmazáscsomag beállításai** panelen válassza a **Nyelvek** lehetőséget.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows – üzletági (LOB) alkalmazások fájlkiterjesztések <!-- 1884873 -->
Most már tartalmazza a kiterjesztések Windows LOB-alkalmazások *.msi*, *.appx*, *.appxbundle*, *.msix*, és *. msixbundle*. Az alkalmazásokat az **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséggel adhatja hozzá a Microsoft Intune-hoz. Megjelenik az **Alkalmazás hozzáadása** panel, ahol kiválaszthatja az **Alkalmazás típusát**. Windowsos üzletági alkalmazásokhoz válassza az **Üzletági alkalmazás** lehetőséget az alkalmazás típusa területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy megfelelő kiterjesztésű telepítőfájlt.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Windows 10-es alkalmazás üzembe helyezése az Intune-nal <!-- 2309001 -->
Az üzleti alkalmazások és a Vállalati Microsoft Áruházbeli alkalmazások meglévő támogatására építve a rendszergazdák a szervezetük legtöbb meglévő alkalmazását az Intune segítségével telepíthetik a végfelhasználók Windows 10 rendszerű eszközeire. A rendszergazdák a Windows 10-es felhasználók számára több különböző formátumban adhatják hozzá, telepíthetik vagy eltávolíthatják az alkalmazásokat, például MSI-k, setup.exe fájlok vagy az MSP használatával. Az Intune a letöltést és a telepítést megelőzően kiértékeli a követelményszabályokat és a Windows 10 Műveletközpontján keresztül értesíti a végfelhasználókat a telepítés állapotáról vagy az újraindítási követelményekről. Ez a funkció gyakorlatilag lehetővé teszi, hogy az ez iránt érdeklődő szervezetek az Intune-ba és a felhőbe helyezzék át e műveleteiket. Ez a funkció jelenleg nyilvános előzetes verzióban érhető el, és várhatóan a következő néhány hónap során jelentős új képességekkel fog bővülni. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>A webes adatok Alkalmazásbeállítások alkalmazásvédelmi szabályzat (alkalmazás) <!-- 2662995 -->
A webes tartalmakra vonatkozó APP szabályzatok beállításait az Android- és iOS-eszközökön is frissítjük, hogy hatékonyabban kezelhetők legyenek a webes http- és https-hivatkozások, valamint az univerzális iOS-hivatkozásokon és Android-alkalmazáshivatkozásokon keresztüli adatátvitel. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Felhasználói eszközök és alkalmazások tartalom menü <!-- 2771453 -->
A végfelhasználók mostantól az eszközök és alkalmazások helyi menüjéből is elvégezhetnek olyan gyakori műveleteket, mint például egy eszköz átnevezése vagy a megfelelőség ellenőrzése. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>A Windows Céges portálon használható billentyűparancsok <!-- 2771518 -->
A végfelhasználók mostantól az eszközökre és alkalmazásokra vonatkozó műveleteket a Windows rendszerű céges portál billentyűparancsaival is aktiválhatják.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Hozzon létre DNS-utótagokat a VPN profilok a Windows 10 rendszerű eszközökön<!-- 1333668 -->
Egy VPN-eszközregisztrációs profil létrehozásakor (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 és újabb** platform > **VPN** profiltípus) meg kell adni néhány DNS-beállítást. Ezzel a frissítéssel egyszerre több **DNS-utótag** is megadható az Intune-ban. A DNS-utótagok használatakor a rendszer a hálózati erőforrások rövid nevére keres rá a teljes tartománynév (FQDN) helyett. Ezzel a frissítéssel a DNS-utótagok sorrendje is módosítható az Intune-ban.
A jelenlegi DNS-beállításokat [a Windows 10 VPN-beállításaival](vpn-settings-windows-10.md#dns-settings) foglalkozó cikk ismerteti.
Érintett kiadások: Windows 10-es eszközök

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Mindig bekapcsolt VPN az Android enterprise munkahelyi profil támogatása <!-- 1333705 -->
Ez a frissítés lehetővé teszi a mindig bekapcsolt VPN-kapcsolatok használatát a felügyelt munkahelyi profillal rendelkező Android Enterprise rendszerű eszközökön. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
A Mindig bekapcsolt VPN a következő helyen engedélyezhető: **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Android Enterprise** platform > **Eszközkorlátozások** > **Kapcsolatok** lehetőséget.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>SCEP-tanúsítványok kiállításához felhasználó nélküli eszközök <!-- 1744554 -->
A tanúsítványok jelenleg felhasználók részére vannak kiállítva. Ezzel a frissítéssel az SCEP-tanúsítványok már eszközök, köztük felhasználó nélküli eszközök, például kioszkok részére is kiállíthatók (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** platform > **SCEP-tanúsítvány** elemet). Egyéb frissítések:
- Az SCEP-profil **Tulajdonos** tulajdonsága mostantól egy egyéni szövegmező, amely új változókat is tartalmazhat. 
- Az SCEP-profilokban a **Tulajdonos alternatív neve (SAN)** tulajdonság mostantól tábla formátumú, és új változókat is tartalmazhat. A táblában a rendszergazdák megadhatnak attribútumokat, és a hozzájuk tartozó értéket egy egyéni szövegmezőben tölthetik ki. Az SAN a következő attribútumokat támogatja: 
  - DNS
  - E-mail-cím
  - EGYSZERŰ FELHASZNÁLÓNÉV

  Ezek az új változók statikus szöveggel adhatók meg egy egyéni szövegmezőben. Például a DNS-attribútumok a következő formátumban adhatók meg: `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > A kapcsos zárójel, pontosvessző és függőleges vonal szimbólumok „ { } ; | ” nem használhatók az SAN statikus szövegében. A kapcsos zárójeleknek mindig az új eszköztanúsítvány valamely változóját kell közrefogniuk ahhoz, hogy az elfogadható legyen mint `Subject` vagy `Subject alternative name`. 

Új változók az eszköztanúsítványokban:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - A `{{FullyQualifiedDomainName}}` csak a Windows rendszerű és tartományhoz csatlakoztatott eszközök esetén működik. 
>  -  Ha a tárgyban megad olyan eszköztulajdonságokat, mint az IMEI, a sorozatszám vagy a teljesen minősített tartománynév, vagy az eszköztanúsítványban megadja a SAN-azonosítót, vegye figyelembe, hogy ezeket a tulajdonságokat az eszközhöz hozzáféréssel rendelkező személyek meghamisíthatják. 

Az SCEP-tanúsítványprofilok létrehozásakor jelenleg használható változókat az [SCEP-tanúsítványprofil létrehozása](certificates-scep-configure.md#create-a-scep-certificate-profile) cikk ismerteti. 

Érintett kiadások: Windows 10 és újabb verziók és az iOS-, Wi-Fi támogatott

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Uncompliant eszközök távoli zárolása <!-- 2064495 -->
A megfelelőségi szabályzatokhoz létrehozható egy olyan művelet, amely távolról zárolja a nem megfelelő eszközöket. Ehhez az Intune **Eszközmegfelelőség** menüjében hozzon létre egy új szabályzatot, vagy válasszon ki egy meglévőt, majd kattintson a **Tulajdonságok** elemre. Válassza a **Meg nem felelés esetén végrehajtandó műveletek** > **Hozzáadás** lehetőséget, majd az eszköz távoli zárolását.
Támogatott a következő rendszereken: 
- Android
- iOS
- macOS
- Windows 10 mobil verzió 
- Windows Phone 8.1 és újabb verziók 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Windows 10-es és újabb teljes képernyős profil fejlesztések az Azure Portalon <!-- 2748224 -->
Ez a frissítés a következő fejlesztéseket vezeti be a Windows 10 rendszerű kioszk eszközkonfigurációs profilokban (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 és újabb** platform > **Kioszk (előzetes verzió)** profiltípus): 
- Jelenleg több kioszkprofil is létrehozható ugyanazon az eszközön. Ezzel a frissítéssel az Intune eszközönként már csak egy kioszkprofilt támogat. Ha továbbra is több kioszkprofilt kíván használni ugyanazon eszközön, használhat egy egyéni URI-t.
- A **többalkalmazásos kioszk** profilokban kiválaszthatja az alkalmazás csempéinek méretét és sorrendjét a **Start menü elrendezéséhez** az alkalmazásrácson. Ha ennél több testreszabási lehetőségre van szüksége, továbbra is feltölthet egy XML-fájlt.
- A kioszk böngészőbeállításai át lettek helyezve a **Kioszk** beállításaiba. Jelenleg a **Kioszk böngészőbeállításai** saját kategóriával rendelkeznek az Azure Portalon.
Érintett kiadások: Windows 10 és újabb




### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Az Autopilot-profil még nincs regisztrálva a Autopilot Win 10-es eszközök regisztrálását a alkalmazni <!-- 1558983 -->
AutoPilot-profilokat alkalmazhat a beléptetett Windows 10-es eszközökön, amelyek még nem lettek regisztrálva az AutoPilotba. Az AutoPilot profilban válassza a **Minden megcélzott eszköz átalakítása az AutoPilotra** lehetőséget, amely automatikusan regisztrálja a nem AutoPilot-eszközöket az AutoPilot üzembehelyezési szolgáltatással. A regisztráció feldolgozása 48 órát is igénybe vehet. A regisztrációjuk törlése és a visszaállításuk után az AutoPilot üzembe helyezi az eszközöket.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Hozzon létre, és több regisztrálási állapot oldal profilok hozzárendelése az Azure AD-csoportok <!-- 2526564 -->
Mostantól több regisztrálási állapot oldalprofilt is [létrehozhat és hozzárendelhet](windows-enrollment-status.md) az Azure ADD-csoportokhoz.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>A Készülékregisztrációs Program Manager rendszerbe történő áttelepítés Apple üzleti az Intune-ban <!--2748613-->
Az Intune-ban működik az Apple üzleti Manager (ABM), és a fiókok frissíthetők a Készülékregisztrációs programból (DEP) az ABM-be. A folyamat az Intune-ban ugyanaz. Az Apple-fiók DEP-ről ABM-re való frissítéséhez lépjen a következő helyre: [ https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Riasztás és a regisztrációs állapot lapját az eszköz regisztrációs Áttekintés lap <!--2748656-->
A riasztások és a beléptetési hibák mostantól külön lapfüleken jelennek meg az Eszközök beléptetése áttekintő oldalon.

### <a name="device-management"></a>Eszközkezelés

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Alkalmazások és a hozzáférés letiltása korlátozza az Android-eszközökön a vállalati erőforrások <!-- 2451462  -->  
Az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Android** > **Rendszerbiztonság** területen, az *Eszközbiztonság* szakaszban megjelent egy új, **Korlátozott alkalmazások** nevű beállítás. A **Korlátozott alkalmazások** beállítás egy megfelelőségi szabályzattal tiltja le a céges erőforrásokhoz való hozzáférést, ha bizonyos alkalmazások telepítve vannak az eszközön. Az eszköz addig nem megfelelőnek minősül, amíg a korlátozott alkalmazásokat el nem távolítják róla.
Érintett kiadások: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

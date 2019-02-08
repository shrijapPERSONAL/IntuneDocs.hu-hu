---
title: Újdonságok a Microsoft Intune-ban – Azure | Microsoft Docs
titlesuffix: ''
description: Az Azure-beli Intune-portál újdonságai
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ee33525c382b09952a28fad09ee7844e73f2257
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850394"
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a jövőbeni változtatásokról, a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi kiadásokról](whats-new-archive.md) is. 

> [!Note]
> Egyes funkciók bevezetése több hetet igénybe vehet, így előfordulhat, hogy nem elérhetők a felhasználók számára az első héten.
>
> A mobileszköz-kezelés (MDM) új hibrid funkciójával kapcsolatos további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

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
## <a name="week-of-february-4-2019"></a>2019. február 4 hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-macos-company-portal-dark-mode----3300524-eeready---"></a>Intune-ban macOS céges portálra sötét üzemmód <!-- 3300524 eeready -->
Az Intune-ban macOS céges portálra sötét mód mostantól támogatja a macOS-hez. Ha engedélyezi a sötét üzemmód 10.14 + macOS-eszközön, a vállalati portál lehetőség a megjelenését, amely mutatja, hogy a üzemmód színeket.

## <a name="week-of-january-21-2019"></a>2019. január 21 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Bejelentési értesítések Win32-alkalmazások <!-- 3136566   -->
Bemutató végfelhasználói bejelentési értesítések egy alkalmazás-hozzárendelés tilthatja le. Az Intune-ból, válassza ki a **ügyfélalkalmazás** > **alkalmazások** > Válassza ki az alkalmazást > **hozzárendelések** > **csoportokhozközétartozik**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Az Intune alkalmazásvédelmi szabályzataihoz tartozó kezelőfelületre vonatkozó frissítés <!-- 3251427  -->
Módosítottuk a címkék beállításainak és az Intune app Protection, hogy könnyebben érthetőek gombok. A változások a következők:  
- Vezérlők meg nem változtatják **Igen** / **nincs** elsősorban szabályozza **blokk** / **engedélyezése** és **letiltása** / **engedélyezése** szabályozza. A címkék is frissülnek.  
- Beállítások újraformázása, így a beállítás, és a felirat egymás mellett a vezérlőelemet, adja meg a jobb navigációs.   

Az alapértelmezett beállításokat és a beállítások száma nem változik, de ez a változás lehetővé teszi, hogy a felhasználó megértése, keresse meg, és a alkalmazni a beállításokat több egyszerűen kiválasztott alkalmazásvédelmi szabályzatok. További információ: [iOS-beállítások](app-protection-policy-settings-ios.md) és [Android-beállításokat](app-protection-policy-settings-android.md).

#### <a name="additional-settings-for-outlook----3301182----"></a>Az Outlook további beállítások <!-- 3301182  -->
Mostantól konfigurálhatja az IOS rendszerhez készült Outlook és az Intune-nal Android followiong további beállításait:
- Csak a munkahelyi vagy iskolai fiókkal az Outlookban az iOS és Android rendszerhez használható engedélyezése
- Modern hitelesítéssel az Office 365 és a hibrid, modern hitelesítést a helyszíni fiókok telepítése
- Használat `SAMAccountName` az e-mail profilban, az egyszerű hitelesítés kijelölésekor a felhasználónév mező

A következő beállításokat is továbbra is fokozatosan vezetjük be, és hamarosan közzétesszük a konzolon:
- Lehetővé teszi az ügyfelek menteni
- Konfigurálja a külső címzetteknek e-mail tippek
- Konfigurálása **szűrt levelek**
- Biometrikai IOS rendszerhez készült Outlook eléréséhez szükséges

Az alábbi beállítást az Intune-konzolon megjelenik, de ha konfigurálva, nem a várt módon fog működni. A probléma hamarosan lesz kijavítva:
- Külső képek letiltása

> [!NOTE]
> Ha az Intune alkalmazásvédelmi szabályzatokat használ a vállalati identitások kezelésére, érdemes lehet nem engedélyezi az **biometrika megkövetelése**. További információkért lásd: **vállalati hitelesítő adatok megkövetelése a hozzáféréshez** a [hozzáférési beállítások iOS](app-protection-policy-settings-ios.md#access-requirements) és [Android-beállításokat](app-protection-policy-settings-android.md#access-requirements).

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

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>A Configuration Manager megfelelőségének ellenőrzése <!-- 2192052  eepublished  -->
Ez a frissítés magában foglalja a System Center Configuration Manager az új megfelelőségi beállítás (**eszközmegfelelőség** > **házirendek** > **hozzon létre házirendet**  >  **Windows 10 és újabb** > **Configuration Manager megfelelőségi**). A Configuration Manager megfelelőségi jeleket küldi az Intune-nak. Ezzel a beállítással megkövetelheti az összes Configuration Manager-jel való visszatéréshez "megfelelő".

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ha az eszközön lévő összes programot ismeretlen állapotban van, az eszköz akkor nem kompatibilis az Intune-ban.

[A Configuration Manager megfelelőségi](compliance-policy-create-windows.md#configuration-manager-compliance) ismerteti ezt a beállítást.

A következőkre vonatkozik: Windows 10 és újabb

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Eszközkonfigurációs profil használatával felügyelt iOS-eszközök tapétáját testreszabása <!-- 2809324   -->
Amikor egy iOS-eszközök konfigurációs profilt hoz létre, testre szabhatja az egyes funkciók (**eszközkonfiguráció** > **profilok** > **létrehozása profil** > **iOS** tartozó platform > **eszközfunkciók** profiltípus). A frissítés tartalmaz új **háttérkép** beállítások, amelyek lehetővé teszik a rendszergazdáknak .png, .jpg és .jpeg-rendszerkép használata a kezdőképernyő vagy a zárolási képernyőn. Ezek a háttér-beállítások csak a felügyelt eszközökre vonatkoznak. 

Ezek a beállítások listáját lásd: [IOS-es eszközfunkció-beállítások](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10-es teljes képernyős szolgáltatás általánosan elérhető <!-- 3594661  -->
Ez a frissítés a Windows 10-es és újabb rendszerű eszközök teljes képernyős funkció általánosan elérhető (GA). Felveheti és konfigurálhatja az összes beállítások megtekintéséhez lásd: [teljes képernyős beállítások Windows 10-es (és újabb)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Bluetooth-névjegyek megosztása eltávolítják az Eszközkorlátozások > Android Enterprise eszköz tulajdonosa <!-- 3598396   -->
Az Android Enterprise-eszközöket egy eszközkorlátozási profilt hoz létre, ha van egy **forduljon megosztása Bluetooth használatával** beállítás. Ebben a frissítésben a **forduljon megosztása Bluetooth használatával** beállítás törlődik (**eszközkonfiguráció** > **profilok**  >   **Profil létrehozása** > **Android Enterprise** tartozó platform > **Eszközkorlátozások > eszköz tulajdonosa** profiltípus > **általános** ). 

A **forduljon megosztása Bluetooth használatával** beállítás nem támogatott az Android vállalati eszköz tulajdonosa management. Ezzel a beállítással a rendszer eltávolítja, ha ez nem érinti az bármely eszköz vagy a bérlők, akkor is, ha ez a beállítás engedélyezve van, és konfigurálva a környezetben.

Beállítások aktuális listájának megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md).

A következőkre vonatkozik: Androidos vállalati eszköz tulajdonosa

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

## <a name="week-of-january-14-2019"></a>2019. január 14 hete

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>A vállalat által birtokolt, teljes körűen felügyelt Android-eszközök támogatása előzetes verzió <!-- 1574342  -->
Az Intune mostantól támogatja a teljes körűen felügyelt Android-eszközök a vállalat által birtokolt "eszköz tulajdonosa" forgatókönyv, ahol eszközök szorosan által felügyelt IT és a rendszer az egyes felhasználókkal kapcsolódó. Ez lehetővé teszi a rendszergazdák számára a teljes eszköz kezelése, egy kiterjesztett tartomány nem érhető el a munkahelyi profilok házirend-vezérlők kényszerítésére, és korlátozza a felhasználók, alkalmazások telepítése csak a felügyelt Google Play áruházból. További információkért lásd: [beállítása az Intune-ban Android-regisztrációs teljes körűen felügyelt eszközök](android-fully-managed-enroll.md) és [a dedikált eszközök és a teljes körűen felügyelt eszközök regisztrálásához](android-dedicated-devices-fully-managed-enroll.md).  Ne feledje, hogy ez a funkció előzetes verzióban érhető el. Az Intune bizonyos funkciók, például a tanúsítványok, megfelelőségi és feltételes hozzáférés, nem érhetők el jelenleg az Android a teljes körűen felügyelt felhasználói eszközök.

## <a name="week-of-january-7-2019"></a>2019. január 7 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-app-pin----2298397---"></a>Intune az alkalmazás <!-- 2298397 -->
A rendszergazdáknak konfigurálhat egy végfelhasználó úgy megvárhatja, amíg meg kell változtatni a PIN-kód alkalmazás Intune-beli napok száma. Az új beállítás *PIN-kód visszaállítása után a napok számát* kiválasztásával az Azure Portalon érhető el, és **Intune** > **ügyfélalkalmazás**  >   **Az alkalmazásvédelmi szabályzatok** > **házirend létrehozása** > **beállítások** > **a hozzáférési követelmények**. Elérhető [iOS](app-protection-policy-settings-ios.md) és [Android](app-protection-policy-settings-android.md) eszközök esetében ez a funkció támogatja a pozitív egész értéket.


#### <a name="intune-device-reporting-fields----2748738---"></a>Az Intune eszköz reporting mezők <!-- 2748738 -->
Az Intune további eszköz területén, beleértve az alkalmazás regisztrációs azonosító, Android gyártója, modell, és biztonsági javítást, valamint IOS-es modell reporting biztosít. Az Intune-ban, ezek a mezők érhetők el kiválasztásával **ügyfélalkalmazás** > **alkalmazásvédelmi állapot** választva **alkalmazásvédelmi jelentés: iOS, Android**. Emellett ezek a paraméterek segítségével konfigurálja a **engedélyezése** lista az eszköz gyártója (Android), a **engedélyezése** lista az eszköz modellje (Android és iOS) és a minimális Android biztonsági javítási szintnek verzió beállítását. 


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és átkerülnek a saját konfigurációs profil <!-- 3322847 -->

Az Intune-ban a felügyeleti sablonok (**eszközkonfiguráció** > **felügyeleti sablonok**) jelenleg privát előzetes verzióban érhető el. Ez a frissítés:

- Felügyeleti sablonok tartalmaznak körülbelül 300 beállítások, amelyek felügyelhetők az Intune-ban. Korábban ezek a beállítások csak megtalálható a Helyicsoportházirend-szerkesztő.
- Felügyeleti sablonok nyilvános előzetes verzióban érhetők el.
- Felügyeleti sablonok helyez át a **eszközkonfiguráció** > **felügyeleti sablonok** való **eszközkonfiguráció**  >   **Profilok** > **profil létrehozása** > a **Platform**, válassza a **Windows 10 és újabb** > a **profil típus**, válassza a **felügyeleti sablonok**.
- Jelentéskészítés engedélyezve van

További információk a funkcióról, nyissa meg [a csoportházirend-beállítások konfigurálása a Windows 10-es sablonok](administrative-templates-windows.md).

A következőkre vonatkozik: Windows 10 és újabb

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
A következőkre vonatkozik: A Windows 10 és újabb verziók, Windows Holographic for Business

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
- Tiltsa le a megjelenítése, beleértve a bejövő hívások, a rendszer riasztásai, rendszerhibák és több rendszer értesítései
- Oktatóanyagok és útmutatók az első alkalommal megnyitott alkalmazások indítása kihagyása javasol.
- Speciális keyguard beállításainak letiltása, például a kamera, értesítések, ujjlenyomattal történő Zárolásfeloldás és több, a beállítások megtekintéséhez nyissa meg [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Vállalati Android-eszköz tulajdonosa eszköz használhat a mindig bekapcsolva beállítású VPN-kapcsolatok <!-- 3202194 -->
Ebben a frissítésben mindig bekapcsolt VPN-kapcsolatok Android enterprise eszköz tulajdonosa eszközökön is használhatja. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
Engedélyezheti a mindig bekapcsolt VPN **eszközkonfiguráció** > **profilok** > **profil létrehozása**  >   **Android enterprise** tartozó platform > **eszközkorlátozások** az eszköz tulajdonosa csak > **kapcsolat** beállításait. A beállítások megtekintéséhez lépjen a [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Új beállítás az end folyamatok a Feladatkezelő Windows 10 rendszerű eszközökön <!-- 3285177 --> 
A frissítés tartalmaz egy új beállítás a Feladatkezelő használatát a Windows 10 rendszerű eszközökön folyamatait. Eszközkonfigurációs profil használatával (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > a **Platform** , válassza a **Windows 10-es** > a **profiltípus**, válassza a **eszközkorlátozások** > **általános** beállítások), engedélyezése vagy tiltása, ezt a beállítást választja.
Ezek a beállítások megtekintéséhez, keresse fel a [Windows 10-es eszközkorlátozási beállítások](device-restrictions-windows-10.md).
A következőkre vonatkozik: Windows 10 és újabb


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Részletesebb regisztrációs korlátozási hiba üzenetkezelés <!-- 3111564 -->
Részletes hibaüzenetek a regisztrációs korlátozások nem teljesülnek esetén érhetők el. Tekintse meg ezeket az üzeneteket, lépjen a **Intune** > **hibaelhárítás** >, és ellenőrizze a regisztrációs hibák tábla. További információkért lásd: a [regisztrációs hibák listája](help-desk-operators.md#configuration-policies-reference).



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
Hatókörcímkék korlátozni a szerepköröket és alkalmazásokat hozhat létre. Hatókörcímke adhat hozzá egy alkalmazáshoz, így csak is az adott hatókörcímke hozzárendelt szerepkörrel rendelkező személyek hozzáférhetnek az alkalmazáshoz. Apple Volume Purchase Program (VPP) használatával vásárolt alkalmazások hatókörcímkék nem lehet hozzárendelni.  További információkért lásd: [használja a szűrő házirendek hatókörcímkék](scope-tags.md).



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

## <a name="week-of-november-26-2018"></a>2018. November 26 hete

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Alkalmazások eltávolítása a céges, felügyelt iOS-eszközökről <!-- 1281677 -->

Bármilyen alkalmazást a vállalat által birtokolt felügyelt iOS-eszközök távolíthatja el. Ha az **Eltávolítás** hozzárendelési típussal megcélozza a felhasználó- vagy eszközcsoportokat, akkor bármilyen alkalmazást el tud távolítani. Személyes és nem felügyelt iOS-eszközök esetében a továbbiakban csak az Intune használatával telepített alkalmazásokat tudja majd eltávolítani.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Az Intune Win32 alkalmazás tartalmának letöltése <!-- 2617320 -->
A Windows 10 RS3 és fent az ügyfelek letöltik Intune Win32 alkalmazás tartalmának kézbesítésoptimalizálás összetevőt a Windows 10-es ügyfél használ. Kézbesítésoptimalizálás társ-társ funkciókat biztosít, amelyek alapértelmezés szerint van kapcsolva. Kézbesítésoptimalizálás konfigurálható a csoportházirend és a jövőben az Intune MDM-n keresztül További információkért lásd: [kézbesítés optimalizálása Windows 10-es](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Eszközök és alkalmazások végfelhasználói helyi menüje <!-- 2771453 -->
A végfelhasználók most már használhatja helyi menü eszközön, és az alkalmazások indításához a gyakori műveletekhez, például egy eszköz átnevezése vagy a megfelelőség ellenőrzése.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Egyéni háttér beállítása a Managed Home Screen alkalmazásban  <!-- 3041945 -->
Egy beállítás, amely lehetővé teszi, hogy Ön szabja testre a kezdőlap képernyő felügyelt alkalmazást az Android Enterprise, a több alkalmazás, a teljes képernyős mód eszközökön háttér adunk hozzá.  **Egyéni URL-háttér** konfigurálásához nyissa meg az Azure portalon az Intune > Eszközkonfiguráció elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat kioszkbeállításainak szerkesztéséhez.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Alkalmazásvédelmi szabályzat-hozzárendelés mentése és alkalmazása <!-- 3104570 -->
Keresztül most már hatékonyabban szabályozhatja a [alkalmazásvédelmi szabályzat-hozzárendelések](app-protection-policies.md#deploy-a-policy-to-users). Amikor kiválaszt *hozzárendelések* állítsa be, vagy szerkessze a szabályzat hozzárendeléseinek, meg kell **mentése** a konfigurációt a módosítás alkalmazása előtt. Használat **elveti** törölje az összes módosítást, anélkül, hogy bármely módosításainak mentése a belefoglalási vagy kizárási sorolja fel.  Mentés igénylő vagy elvetésének csak a kívánt felhasználók alkalmazásvédelmi szabályzat vannak rendelve.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>A Microsoft Edge böngészőhöz tartozó új beállítások Windows 10 és újabb rendszerek esetében <!-- 3174639 -->
A frissítés segítségével szabályozhatja, és kezelheti az eszközökön a Microsoft Edge böngésző új beállításokat tartalmazza. Ezek a beállítások listáját lásd: [eszközkorlátozási Windows 10-es (és újabb)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Új alkalmazások támogatják az alkalmazásvédelmi szabályzatokkal <!-- 3330037 -->
A következő alkalmazások kezelheti [az Intune alkalmazásvédelmi szabályzatai](app-protection-policies.md):
- Stream (iOS)
- Teendők (Android, iOS)
- A PowerApps (Android, iOS)
- A folyamat (Android, iOS)

Használja alkalmazásvédelmi szabályzatok vállalati adat- és adatátviteli ezeket az alkalmazásokat, például a többi Intune-szabályzat által felügyelt alkalmazások védelmére. Megjegyezés: Ha a Flow még nem láthatók a konzolon, hozzáadhat folyamatot, ha hoz létre vagy szerkeszt, és az alkalmazásvédelmi szabályzatok. Ehhez használja a **+ további alkalmazások** lehetőséget, majd adja meg a *Alkalmazásazonosító* a Flow a beviteli mezőben. Android használatra *com.microsoft.flow*, és az iOS használja *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>Megjelenítjük az iOS- és macOS-verziószámokat és -buildszámokat <!-- 1892471 -->
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

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>A Regisztrációs állapotlapon nyomon követett alkalmazások kiválasztása<!-- 2531007 -->
Kiválaszthatja, melyik alkalmazások nyomon a regisztrálási állapot oldal. Ezek az alkalmazások telepítve vannak, amíg a felhasználó az eszköz nem használható. További információkért lásd: [beállítása egy regisztrálási állapot oldal](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Keresse meg az Autopilot-eszközök sorozatszám alapján <!--2595788 -->
Most már kereshet az Autopilot-eszközök sorozatszám alapján. Ehhez válassza ki a **eszközregisztráció** > **Windows regisztrációs** > **eszközök** > írja be a sorozatszám a **keresés alapján sorozatszám** box > nyomja le az Enter billentyűt.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Az Office ProPlus telepítésének nyomon követése <!--2620217 -->
Felhasználók nyomon követheti a telepítés előrehaladását [Office ProPlus](apps-add-office365.md) használatával a [regisztrálási állapot oldal](windows-enrollment-status.md). További információkért lásd: [beállítása egy regisztrálási állapot oldal](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>VPP-jogkivonatok lejáratára vagy a Céges portál licenceinek alacsony számára vonatkozó riasztások <!-- 2237572 -->
Ha előre ellátja a DEP-regisztráció során a céges portál Volume Purchase Program (VPP) használ, Intune riasztást küld, amikor a VPP-token érvényessége hamarosan lejár, és a licencek a céges portál kevés.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>A macOS-készülékregisztrációs program által biztosított támogatás az Apple School Manager-fiókokhoz <!--3006133 -->
Az Intune már támogatja a macOS-eszközök az Apple School Manager-fiókok a Készülékregisztrációs programmal.  További információkért lásd: [automatikusan regisztrálni a macOS-eszközök az Apple School Manager vagy a Készülékregisztrációs Program](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Új Intune eszköz-előfizetés Termékváltozat <!--3312071-->
A vállalatok számára az eszközkezelés költségeinek csökkentéséhez már elérhető egy új, eszközalapú előfizetési termékváltozat. Ennek az Intune-beli eszköz-termékváltozatnak a licencelése eszközönként történik, havi elszámolással. Az ár a licencprogramtól függően változik. Az Office felügyeleti portálján keresztül közvetlenül, és keresztül elérhető a [nagyvállalati szerződés](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and szolgáltatási szerződését](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [nyissa meg a Microsoft-szerződések ](https://partner.microsoft.com/licensing/licensing-agreements), és [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Eszközkezelés

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Kioszkmód ideiglenesen szüneteltetése Android-eszközökön a módosítások végrehajtásához <!-- 3041935 -->
Ha többalkalmazásos kioszkmódban használ Android-eszközöket, előfordulhat, hogy a rendszergazdáknak módosításokat kell végrehajtaniuk az eszközön. Ez a frissítés új lehetővé teszi, hogy a rendszergazda ideiglenesen felfüggesztése teljes képernyős mód használata a PIN-kódot, és hozzáférhet a teljes eszköz a többalkalmazásos kioszk beállításokat tartalmaz.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Virtuális kezdőképernyő gomb bekapcsolása az Android Enterprise rendszerű kioszkeszközökön  <!-- 3042021 -->
Az új beállítás segítségével a felhasználók az eszközön lévő többfunkciós gombra való koppintással válthatnak a többalkalmazásos kioszkeszközökön található Managed Home Screen alkalmazás és az egyéb hozzárendelt alkalmazások között. Ez a beállítás igen hasznosnak bizonyul olyan esetekben, amikor a felhasználó kioszkalkalmazása nem reagál megfelelően a „vissza” gomb megnyomására. Ezt a beállítást Ön konfigurálni tudja majd az egyetlen célra használható céges Android-eszközökön. A **Virtuális kezdőképernyő gomb** be- és kikapcsolásához válassza az Azure portalon az Intune > Eszközök konfigurálása elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat kioszkbeállításainak szerkesztéséhez.
A teljes képernyős beállítások megtekintéséhez lásd: [eszközkorlátozások Android Enterprise](device-restrictions-android-for-work.md).

## <a name="week-of-november-12-2018"></a>2018. November 12 hete

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Hálózati hozzáférés-vezérlés (NAC) iOS-es Citrix egyszeri bejelentkezés támogatása <!-- 3259404 -->

A Citrix Citrix-átjáróra, hogy a hálózati hozzáférés-vezérlés (NAC) a Citrix egyszeri bejelentkezés az Intune-ban iOS-es frissítést adott ki. Részvétel a VPN-profilon belül egy Eszközazonosítót tartalmazzák az Intune-ban, és juttathatja el ezt a profilt az iOS-eszközökön. Szüksége lesz a legújabb frissítés telepítése a Citrix-átjáróra a funkció használatához.

[VPN-beállítások konfigurálása az iOS-eszközökön](vpn-settings-ios.md#base-vpn-settings) további információt nyújt az NAC, beleértve néhány további követelményeket is. 

## <a name="week-of-november-5-2018"></a>2018. november 5-i hét

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Az iOS 12 OAuth támogatása az iOS-es e-mail-profilokban <!--2155106 -->

Az Intune iOS e-mail-profiljai támogatják az iOS 12-es nyílt engedélyezést (OAuth). Ennek a funkciónak a megtekintéséhez hozzon létre egy új profilt (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **iOS** a platformhoz > **E-mail** a profiltípushoz), vagy frissítsen egy létező iOS-es e-mail-profilt. Ha engedélyezi az OAuth-hitelesítést egy olyan profilban, amely már üzembe van helyezve a felhasználóknál, akkor a felhasználóknak újra el kell végezniük a hitelesítést, és le kell ismét tölteniük az e-mailjeiket.

Az [iOS-es e-mail-profilok](email-settings-ios.md) szakaszban további információt talál az OAuth e-mail-profilban való használatáról.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Autopilot-támogatás a hibrid, Azure Active Directory-hoz csatlakoztatott eszközökhöz (előzetes verzió) <!-- 1048100-->
Az Autopilot segítségével mostantól hibrid, Azure Active Directory-hoz csatlakoztatott eszközöket állíthat be. A hibrid Autopilot funkció használatához az eszközöket csatlakoztatni kell a szervezet hálózatához. További információt a [Deploy hybrid Azure AD joined devices using Intune and Windows Autopilot](windows-autopilot-hybrid.md) (Hibrid, Azure AD-hez csatlakoztatott eszközök üzembe helyezése az Intune és a Windows Autopilot használatával) című cikkben talál.
Ez a funkció néhány napon belül kerül bevezetésre a felhasználók között. Előfordulhat tehát, hogy Ön nem tudja követni ezeket a lépéseket addig, amíg a fiókjában is meg nem jelenik ez az újítás.

## <a name="week-of-october-29-2018"></a>2018. október 29-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Nem biometrikus PIN-kód kérése a megadott időtúllépés után <!-- 1506985 -->
Mivel az Intune nem biometrikus PIN-kód megadását írja elő a rendszergazda által meghatározott időtúllépés után, ezzel magasabb szintű védelmet biztosít a mobilalkalmazás-kezelést (MAM) engedélyező alkalmazások számára azáltal, hogy korlátozza a biometrikus azonosításnak a céges adatokhoz való hozzáférés érdekében történő használatát. A beállítások APP/MAM szolgáltatást engedélyező alkalmazásokhoz való hozzáférésre használt Touch ID (iOS), Face ID (iOS), Android Biometric és egyéb jövőbeli biometrikus hitelesítési módszereket alkalmazó felhasználókra vonatkoznak. E beállítások segítségével az Intune-rendszergazdák részletesen szabályozhatják a felhasználók hozzáférését, így megelőzhetik azokat az eseteket, amikor a több ujjlenyomatos vagy egyéb biometrikus hozzáférési módszert használó eszközről céges adatok juthatnak illetéktelen felhasználók birtokába. Az Azure Portalon nyissa meg a **Microsoft Intune** oldalt. Válassza az **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** > **Szabályzat hozzáadása** > **Beállítások** lehetőséget. Az adott beállításokhoz keresse meg a **Hozzáférés** lehetőséget. A hozzáférésre vonatkozó beállításokról az [iOS-beállítások](app-protection-policy-settings-ios.md#access-requirements) és az [Android-beállítások](app-protection-policy-settings-android.md#access-requirements) oldalon tájékozódhat.

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Az Intune APP adatátviteli beállításai a mobileszköz-felügyelettel (MDM) regisztrált iOS-eszközökön <!-- 2244713 -->
Elkülönítheti az Intune APP adatátviteli beállítások iOS rendszerű, MDM-et engedélyező eszközökön való szabályozását a regisztrált felhasználók személyazonosságának megadásától, amely Egyszerű felhasználónévként (UPN) is ismert. Az IntuneMAMUPN-t nem használó rendszergazdák nem tapasztalnak majd működésbeli változást. Ha ez a funkció elérhetővé válik, a regisztrált eszközök adatátviteli viselkedésének vezérléséhez IntuneMAMUPN-t használó rendszergazdáknak át kell tekinteniük az új beállításokat, és szükség szerint frissíteniük kell APP-beállításaikat.

#### <a name="windows-10-win32-apps----2617325---"></a>Windows 10 rendszerű Win32-alkalmazások <!-- 2617325 -->
Konfigurálhatja a Win32-alkalmazások telepítését az egyes felhasználók felhasználói környezetében, de választhatja azt is, hogy az eszköz összes felhasználója esetében telepíti az alkalmazást.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Windows Win32-alkalmazások és PowerShell-parancsfájlok <!-- 2617330 -->
A végfelhasználóknak nem kell többé bejelentkezniük az eszközön a Win32-alkalmazások telepítéséhez és a PowerShell-parancsfájlok végrehajtásához. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Az ügyfélalkalmazások telepítésével kapcsolatos hibák elhárítása <!-- 1363711 -->
Az ügyfélalkalmazások telepítésével kapcsolatban felmerülő hibák elhárításához a **Hibaelhárítás** panelen található **Alkalmazástelepítés** címkével ellátott oszlopban talál segítséget. A **Hibaelhárítás** panel megtekintéséhez válassza az Intune-portálon a **Súgó és támogatás** részben található **Hibaelhárítás** elemet.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Hálózati hozzáférés-vezérléssel kapcsolatos támogatás iOS rendszert használó VPN-ügyfeleken <!-- 1333693 -->
Az ebben a frissítésben biztosított új beállítás lehetővé teszi a Hálózati hozzáférés-vezérlést (NAC), amikor VPN-konfigurációprofilt hoz létre a Cisco AnyConnect, az F5 Access és a Citrix SSO for iOS esetében. E beállítással az eszköz NAC-azonosítója feltüntethető a VPN-profilban. Jelenleg nincsenek olyan VPN-ügyfelek vagy NAC-partnermegoldások, amelyek támogatnák ezt az új NAC-azonosítót, de [támogatási blogbejegyzésünkből](ttps://aka.ms/iOS12_and_vpn) értesülhet az esetleges változásokról.

A NAC használatához a következőt kell tennie:
1. Jelentkezzen be, és állítsa be, hogy az Intune feltüntesse az eszközazonosítókat a VPN-profilokban.
2. Frissítse a NAC-szolgáltató szoftverét/belső vezérlőprogramját a tőle közvetlenül kapott útmutatást követve.

Erről az iOS-VPN-profilon belüli beállításról a [VPN-beállítások hozzáadása iOS rendszerű eszközökön a Microsoft Intune-ban](vpn-settings-ios.md) című cikkben tájékozódhat. A hálózati hozzáférés-vezérlésről a [Hálózati hozzáférés-vezérlés (NAC) integrálása az Intune-nal](network-access-control-integrate.md) című cikkben tájékozódhat. 

A következőre vonatkozik: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>E-mail-profil eltávolítása az adott eszközről akkor is, ha ez az egyetlen e-mail-profil az eszközön <!-- 1818139 -->
Korábban nem tudott e-mail-profilt eltávolítani az adott eszközről, *ha* az volt az egyetlen e-mail-profil rajta. E frissítésnek köszönhetően ez most megváltozik. Mostantól akkor is eltávolíthat e-mail-profilt, ha az az egyetlen, amely az eszközön található. További információt [Az e-mail-beállítások konfigurálása a Microsoft Intune-ban](email-settings-configure.md) című GitHub dokumentumban talál.

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell-parancsfájlok és az AAD <!-- 2309469 -->
Az Intune-beli PowerShell-parancsfájlok beállíthatók úgy, hogy AAD-eszközbiztonsági csoportokat célozzanak meg.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Új alapértelmezett „ Jelszó kötelező típusa” beállítás Android és Android Enterprise esetén<!-- 2649963 -->
Új megfelelőségi szabályzat létrehozásakor (Platform > Rendszerbiztonság > **Intune** > **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Android** vagy **Android Enterprise**) a következőképpen módosul a **Jelszó kötelező típusa** beállítás alapértelmezett értéke:

Forrás: Az eszköz alapértelmezett: Legalább számok

A következőkre vonatkozik: Android, Android Enterprise

Ezekről a beállításokról az [Android](compliance-policy-create-android.md) és az [Android Enterprise](compliance-policy-create-android-for-work.md) oldalakon tájékozódhat.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Előre megosztott kulcsok használata a Windows 10-es Wi-Fi-profilokban <!-- 2662938 -->
E frissítés révén előre megosztott kulcsot (PSK) használhat a WPA/WPA2 személyes biztonsági protokollal a Windows 10-es Wi-Fi-konfigurációprofil hitelesítéséhez. Meghatározhatja a mért hálózatokra vonatkozó költségkonfigurációt is a 2018. október 10-i frissítésű Windows 10 rendszert használó eszközök esetében.

Jelenleg importálni kell a Wi-Fi-profilokat vagy egyéni profilt kell létrehozni az előre megosztott kulcsok használatához. A jelenlegi beállításokat a [Windows 10 Wi-Fi beállításait](wi-fi-settings-windows.md) ismertető cikk írja le. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>PKCS- és SCEP-tanúsítványok eltávolítása az eszközökről <!-- 3218390 -->
Bizonyos forgatókönyvek esetében a PKCS- és SCEP-tanúsítványok akkor is megmaradnak az eszközökön, ha szabályzatot távolít el egy csoportból, konfigurációt vagy telepített megfelelőséget töröl, illetve ha valamelyik rendszergazda meglévő SCEP- vagy PKCS-profilt frissít. E frissítéssel változik ez a működési logika. Egyes forgatókönyvek esetében eltávolítjuk az eszközökről a PKCS- és a SCEP-tanúsítványokat, míg mások esetében a tanúsítványok megmaradnak az eszközön. E tanúsítványokról a [SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban](remove-certificates.md) című cikkben tájékozódhat.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Gatekeeper használata macOS rendszerű eszközökön a megfelelőség ellenőrzésére <!-- 2504381 -->
E frissítés tartalmazza a macOS rendszerre készült Gatekeeper technológiát, amely az eszközök megfelelőségének kiértékelésére szolgál. A Gatekeeper funkció beállításáról a [macOS-es eszközök megfelelőségi szabályzatainak hozzáadása az Intune-nal](compliance-policy-create-mac-os.md) című cikkben tájékozódhat.


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="enrollment-abandonment-report----1382924---"></a>Regisztrációmegszakítási jelentés <!-- 1382924 -->
A regisztrációmegszakítással kapcsolatos további részleteket tartalmazó új jelentés a **Eszközregisztráció** > **Figyelés** szakaszban áll rendelkezésre. További információt a [Céges portállal történő regisztráció megszakítása – jelentés](enrollment-report-company-portal-abandon.md) című cikkben talál.

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Az Azure Active Directory új Használati feltételek funkciója <!-- 2870393 -->
Az Intune-ra vonatkozó Általános Szerződési Feltételek helyett mostantól használhatja az Azure Active Directory-ra vonatkozó Általános Szerződési Feltételek funkciót. Az Azure AD Használati feltételek funkciója nagyobb rugalmasságot biztosít abban, hogy mely feltételek jelenjenek meg és mikor, továbbá jobb honosítástámogatást, jobb feltételmegjelenítés-vezérlést és jobb jelentéskészítési funkciókat nyújt. Az Azure AD Használati feltételek funkciójához Prémium P1 szintű Azure Active Directory szükséges, amely az Enterprise Mobility + Security E3 csomagnak is része. További információt [A céges felhasználói hozzáférési használati feltételek kezelése](terms-and-conditions-create.md) című cikkben talál.

#### <a name="android-device-owner-mode-support---3188762--"></a>Támogatás az Android Device Owner módhoz <!--3188762-->
A Samsung Knox Mobile Enrollment esetében az Intune mostantól támogatja az eszközöknek az Android Device Owner kezelési módra való regisztrációját. A Wi-Fi- és mobilhálózatok felhasználói az eszköz első bekapcsolása után csupán néhány érintéssel regisztrálhatnak. További információ: [Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Eszközkezelés
#### <a name="new-settings-for-software-updates------1907869---"></a>A szoftverfrissítések új beállításai   <!-- 1907869 -->  
- Mostantól konfigurálhatja az egyes riasztási végfelhasználók számára a legújabb szoftverfrissítések telepítésének befejezéséhez szükséges újraindítást kapcsolatos értesítéseket.   
- Konfigurálhat egy újraindítás kapcsolatos figyelmeztető üzenet újraindul, a munkaidőn kívül történik, amely támogatja a BYOD-forgatókönyvekhez.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>A Windows Autopilotban regisztrált eszközök csoportosítása korrelátorazonosító alapján <!-- 2075110 -->
Az Intune mostantól támogatja a Windows rendszerű eszközök korrelátorazonosító alapján történő csoportosítását, ha regisztrációjuk az [Autopilot for existing devices](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) (Autopilot meglévő eszközökön) című cikkben leírtak szerint, a Configuration Manager használatával történt. A korrelátorazonosító az AutoPilot konfigurációs fájljának egyik paramétere. Az Intune az [Azure AD-eszközök enrollmentProfileName attribútumát](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) automatikusan az ezzel megegyező „OfflineAutopilotprofile-<correlator ID>” attribútumra állítja be. Így tetszőleges dinamikus Azure AD-csoportok hozhatók létre korrelátorazonosító alapján az offline Autopilot-regisztrációk enrollmentprofileName attribútuma használatával. További információt a [Windows Autopilot for existing devices](enrollment-autopilot.md#windows-autopilot-for-existing-devices) (Windows Autopilot meglévő eszközökön) című cikkben talál.

#### <a name="intune-app-protection-policies----2984657---"></a>Az Intune alkalmazásvédelemre vonatkozó szabályzata <!-- 2984657 -->
Az Intune alkalmazásvédelemre vonatkozó szabályzatának segítségével többféle adatvédelmi beállítást konfigurálhat az Intune védelemben részesített alkalmazásaira, például a Microsoft Outlookra és a Microsoft Wordre vonatkozóan. E beállítások megjelenését és működését az [iOS](app-protection-policy-settings-ios.md) és az [Android](app-protection-policy-settings-android.md) esetében is módosítottuk, így könnyebben találhatja meg az egyes beállításokat. A szabályzatra vonatkozó beállítások három kategóriába tartoznak:
- **Adatáthelyezés** – Ebbe a csoportba tartoznak az adatszivárgás elleni védelem (DLP) vezérlői, például a kivágás, a másolás, a beillesztés és a mentés másként művelet korlátozásai. Ezek a beállítások szabják meg, hogy hogyan kezelhetik a felhasználók az adatokat az alkalmazásokban.
- **Hozzáférési követelmények** – Ez a csoport tartalmazza a PIN-kód alkalmazásonkénti beállítási lehetőségeit, amelyek meghatározzák, hogyan férnek hozzá a végfelhasználók az alkalmazásokhoz egy munkahelyi környezetben.  
- **Feltételes bevezetés** – Ebbe a csoportba olyan beállítások tartoznak, mint az operációs rendszerre vonatkozó minimális beállítások, a függetlenítésészlelés és a rootolt eszközök felderítése, valamint az offline türelmi időszakok.  
  
A beállítások funkciói nem módosulnak, de könnyebben találhatók majd meg, ha Ön a szabályzatlétrehozási folyamatban dolgozik.

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Az Intune a legfeljebb 8 GB csomagméretű LOB-alkalmazásokat támogatja majd. <!-- 1727158 -->
Az Intune 8 GB-ra növelte a Line-of-business- (LOB) alkalmazások maximális csomagméretét. További információt az [Alkalmazások hozzáadása a Microsoft Intune-hoz](apps-add.md) című cikkben talál.

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Egyéni márkaembléma hozzáadása a Céges portál alkalmazáshoz <!-- 1916266 -->
A Microsoft Intune-rendszergazdák feltölthetnek egy egyéni márkaemblémát, amely háttérképként jelenik meg a felhasználó profiloldalán az iOS-en, a Céges portál alkalmazásban. További információkat a Céges portál alkalmazás konfigurálásáról [a Microsoft Intune Céges portál alkalmazás konfigurálását](company-portal-app.md) ismertető cikkből tudhat meg.

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Az Intune megőrzi a honosított Office nyelvét a végfelhasználói gépekre telepített Office frissítésekor <!-- 2971030 -->
Amikor az Intune telepíti az Office-t a végfelhasználó számítógépén, a végfelhasználók automatikusan ugyanazt a nyelvcsomagokat kapják meg, amelyekkel már eddig is rendelkeztek a korábbi .MSI Office-telepítések esetében. További információt az [Office 365-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal](apps-add-office365.md) című cikkben talál.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Új Intune támogatási felület a Microsoft 365 Eszközkezelési portálon <!-- 3076965 -->
Hamarosan új Súgó és támogatás felületet vezetünk be az Intune esetében a [Microsoft 365 Eszközkezelési portálon]( http://devicemanagement.microsoft.com). Az új felületen saját szavaival fejtheti ki problémáját, valamint hibaelhárítási ötleteket kaphat, és webalapú szervizelési tartalmakat találhat. Ezeket a megoldásokat szabályokon alapuló gépi tanulási algoritmus biztosítja a felhasználók kérései alapján.  

A problémákra összpontosító útmutatáson túl használhatja az új esetkészítő munkafolyamatot is, amellyel e-mailen vagy telefonon keresztül nyithat támogatási eseteket.  

A bevezetésben részt vevő ügyfelek esetében ez az új felület lép a jelenlegi Súgó és támogatás felület helyébe, rajta az előre kijelölt lehetőségek olyan állandó készletével, amely a konzol azon területén alapul, ahová Ön a Súgó és támogatás megnyitásakor kerül.  

*Ez az új Súgó és támogatás felület csak a bérlők bizonyos részére (de nem mindegyikükre) vonatkozóan kerül bevezetésre, és az Eszközkezelési portálon érhető el. Az új felület használóit véletlenszerűen választjuk ki az Intune rendelkezésre álló bérlői közül. A bevezetés bővítésekor új bérlőket adunk hozzá.*  

További információkért lásd: [Súgó és támogatás élmény](get-support.md#help-and-support-experience) a hogyan kérhet támogatást a Microsoft Intune-hoz.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>PowerShell-modul az Intune-hoz – Előzetes verzió érhető el <!-- 951068 -->
A [GitHub]( https://aka.ms/intunepowershell) felületén mostantól új PowerShell-modul áll rendelkezésre, amely a Microsoft Graph-on keresztül nyújt támogatást az Intune API-hez. A modul használatáról az ugyanezen a helyen található README részen tájékozódhat. 


## <a name="week-of-october-15-2018"></a>2018. október 15-i hét

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>PIN-kód megadására kérő üzenet, amikor Ön módosítja az ujjlenyomat- vagy Face ID-azonosítást iOS eszközén  <!-- 2637704  -->
A felhasználókat mostantól PIN-kód megadására kéri a rendszer azt követően, hogy biometrikus módosításokat hajtanak végre iOS-eszközükön. Ebbe beletartoznak a regisztrált ujjlenyomat- és face ID-azonosítást érintő módosítások is. A kérés időzítése attól függ, hogy a *hozzáférés újraellenőrzésére vonatkozó követelmények* konfigurációja hány perc után lépi túl az időt.  Ha nincs beállítva PIN-kód, a rendszer új beállítására kéri a felhasználót. 
 
Ez a funkció csak az iOS-ben érhető el, és a működéséhez szükséges az alkalmazások integrálása az Intune APP SDK for iOS 9.0.1-es vagy újabb verziójával. Az SDK-integráció szükséges a viselkedés kényszeríthetőségéhez a megcélzott alkalmazásoknál. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Néhány alkalmazás, amely ezek között szerepelhet: WXP, Outlook, Managed Browser és Yammer.


## <a name="week-of-october-1-2018"></a>2018. október 1-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Hozzáférés a legfontosabb profiltulajdonságokhoz a Céges portál alkalmazással <!-- 772203 -->
A végfelhasználók mostantól a Céges portál alkalmazással hozzáférhetnek a legfontosabb fióktulajdonságokhoz és -műveletekhez, például a jelszó-visszaállításhoz. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Az iOS-es eszközökön az alkalmazásvédelmi beállítások használatával letilthatja a harmadik féltől származó billentyűzeteket <!-- 1248481 -->
Az Intune-rendszergazdák az iOS-es eszközökön letilthatják a harmadik féltől származó billentyűzeteket, ha azok a szabályzat által védett alkalmazásokon hozzáférnek a céges adatokhoz. Ha az alkalmazásvédelmi szabályzat (APP) a harmadik félhez tartozó billentyűzetek letiltására van beállítva, az eszköz használója üzenetet kap, amikor először fér hozzá ilyen billentyűzettel a céges adatokhoz. A natív billentyűzeten kívül minden más lehetőség le van tiltva, és a felhasználók nem láthatják ezeket. A felhasználók csak egyszer látják az üzenetet. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Intune-alkalmazások felhasználói fiókjainak hozzáférése a felügyelt Android és iOS rendszerű eszközökön <!-- 1248496 -->
A Microsoft Intune rendszergazdájaként szabályozhatja, hogy melyik felhasználói fiókok legyenek hozzáadva a Microsoft Office-alkalmazásokhoz a felügyelt eszközökön. A hozzáférést korlátozhatja csak a szervezeti felhasználói fiókokra, és blokkolhatja a személyes fiókok használatát a regisztrált eszközökön. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Outlook iOS és Android alkalmazáskonfigurációs szabályzat <!--1828527 -->
Mostantól létrehozhat egy Outlook iOS és Android alkalmazáskonfigurációs szabályzatot iOS és Android rendszerekhez az olyan helyszíni felhasználók számára, akik az alapszintű hitelesítést és az ActiveSync protokollt használják. További konfigurálási beállítások lesznek hozzáadva az engedélyezésüket követően az iOS és Android rendszerre készült Outlookhoz.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Az Office 365 Pro Plus nyelvi csomagjai <!-- 1833450 -->
Az Intune rendszergazdájaként további nyelveket helyezhet üzembe az Intune által felügyelt Office 365 Pro Plus alkalmazások számára. Az elérhető nyelvek listája tartalmazza a nyelvi csomag **Típusát** (alap, részleges vagy nyelvi ellenőrzési) is. Az Azure Portalon válassza a **Microsoft Intune** > **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen, az **Alkalmazástípusok** listáján, válassza az **Office 365 csomag** alatti **Windows 10** lehetőséget. Az **Alkalmazáscsomag beállításai** panelen válassza a **Nyelvek** lehetőséget.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows rendszerű üzletági (LOB) alkalmazások fájlnévkiterjesztései <!-- 1884873 -->
A Windowsos üzletági alkalmazások fájlnévkiterjesztései közé tartozik már az *.msi*, *.appx*, *.appxbundle*, *.msix* és *.msixbundle* is. Az alkalmazásokat az **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséggel adhatja hozzá a Microsoft Intune-hoz. Megjelenik az **Alkalmazás hozzáadása** panel, ahol kiválaszthatja az **Alkalmazás típusát**. Windowsos üzletági alkalmazásokhoz válassza az **Üzletági alkalmazás** lehetőséget az alkalmazás típusa területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy megfelelő kiterjesztésű telepítőfájlt.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Windows 10-es alkalmazások telepítése az Intune-nal <!-- 2309001 -->
Az üzleti alkalmazások és a Vállalati Microsoft Áruházbeli alkalmazások meglévő támogatására építve a rendszergazdák a szervezetük legtöbb meglévő alkalmazását az Intune segítségével telepíthetik a végfelhasználók Windows 10 rendszerű eszközeire. A rendszergazdák a Windows 10-es felhasználók számára több különböző formátumban adhatják hozzá, telepíthetik vagy eltávolíthatják az alkalmazásokat, például MSI-k, setup.exe fájlok vagy az MSP használatával. Az Intune a letöltést és a telepítést megelőzően kiértékeli a követelményszabályokat és a Windows 10 Műveletközpontján keresztül értesíti a végfelhasználókat a telepítés állapotáról vagy az újraindítási követelményekről. Ez a funkció gyakorlatilag lehetővé teszi, hogy az ez iránt érdeklődő szervezetek az Intune-ba és a felhőbe helyezzék át e műveleteiket. Ez a funkció jelenleg nyilvános előzetes verzióban érhető el, és várhatóan a következő néhány hónap során jelentős új képességekkel fog bővülni. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Eszközök és alkalmazások végfelhasználói helyi menüje <!-- 2771453 -->
A végfelhasználók mostantól az eszközök és alkalmazások helyi menüjéből is elvégezhetnek olyan gyakori műveleteket, mint például egy eszköz átnevezése vagy a megfelelőség ellenőrzése. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>A Windows rendszerű Céges portál billentyűparancsai <!-- 2771518 -->
A végfelhasználók mostantól az eszközökre és alkalmazásokra vonatkozó műveleteket a Windows rendszerű céges portál billentyűparancsaival is aktiválhatják.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>DNS-utótagok létrehozása a Windows 10 rendszerű eszközökön futó VPN-konfigurációs profilokban<!-- 1333668 -->
Egy VPN-eszközregisztrációs profil létrehozásakor (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 és újabb** platform > **VPN** profiltípus) meg kell adni néhány DNS-beállítást. Ezzel a frissítéssel egyszerre több **DNS-utótag** is megadható az Intune-ban. A DNS-utótagok használatakor a rendszer a hálózati erőforrások rövid nevére keres rá a teljes tartománynév (FQDN) helyett. Ezzel a frissítéssel a DNS-utótagok sorrendje is módosítható az Intune-ban.
A jelenlegi DNS-beállításokat [a Windows 10 VPN-beállításaival](vpn-settings-windows-10.md#dns-settings) foglalkozó cikk ismerteti.
A következőkre vonatkozik: Windows 10-es eszközök

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Mindig bekapcsolt VPN támogatása az Android Enterprise munkahelyi profiljaihoz <!-- 1333705 -->
Ez a frissítés lehetővé teszi a mindig bekapcsolt VPN-kapcsolatok használatát a felügyelt munkahelyi profillal rendelkező Android Enterprise rendszerű eszközökön. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
A Mindig bekapcsolt VPN a következő helyen engedélyezhető: **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Android Enterprise** platform > **Eszközkorlátozások** > **Kapcsolatok** lehetőséget.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>SCEP-tanúsítványok kiállítása felhasználó nélküli eszközökre <!-- 1744554 -->
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

A következőkre vonatkozik: Windows 10 és újabb verziók és az iOS-, Wi-Fi támogatott

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Nem megfelelő eszközök távoli zárolása <!-- 2064495 -->
A megfelelőségi szabályzatokhoz létrehozható egy olyan művelet, amely távolról zárolja a nem megfelelő eszközöket. Ehhez az Intune **Eszközmegfelelőség** menüjében hozzon létre egy új szabályzatot, vagy válasszon ki egy meglévőt, majd kattintson a **Tulajdonságok** elemre. Válassza a **Meg nem felelés esetén végrehajtandó műveletek** > **Hozzáadás** lehetőséget, majd az eszköz távoli zárolását.
Támogatott a következő rendszereken: 
- Android
- iOS
- macOS
- Windows 10 mobil verzió 
- Windows Phone 8.1 és újabb verziók 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>A Windows 10 és újabb rendszerű kioszkprofilok fejlesztései az Azure portálon <!-- 2748224 -->
Ez a frissítés a következő fejlesztéseket vezeti be a Windows 10 rendszerű kioszk eszközkonfigurációs profilokban (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 és újabb** platform > **Kioszk (előzetes verzió)** profiltípus): 
- Jelenleg több kioszkprofil is létrehozható ugyanazon az eszközön. Ezzel a frissítéssel az Intune eszközönként már csak egy kioszkprofilt támogat. Ha továbbra is több kioszkprofilt kíván használni ugyanazon eszközön, használhat egy egyéni URI-t.
- A **többalkalmazásos kioszk** profilokban kiválaszthatja az alkalmazás csempéinek méretét és sorrendjét a **Start menü elrendezéséhez** az alkalmazásrácson. Ha ennél több testreszabási lehetőségre van szüksége, továbbra is feltölthet egy XML-fájlt.
- A kioszk böngészőbeállításai át lettek helyezve a **Kioszk** beállításaiba. Jelenleg a **Kioszk böngészőbeállításai** saját kategóriával rendelkeznek az Azure Portalon.
A következőkre vonatkozik: Windows 10 és újabb




### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>AutoPilot-profilok alkalmazása a beléptetett, de az AutoPilotba még nem regisztrált Windows 10-es eszközökön <!-- 1558983 -->
AutoPilot-profilokat alkalmazhat a beléptetett Windows 10-es eszközökön, amelyek még nem lettek regisztrálva az AutoPilotba. Az AutoPilot profilban válassza a **Minden megcélzott eszköz átalakítása az AutoPilotra** lehetőséget, amely automatikusan regisztrálja a nem AutoPilot-eszközöket az AutoPilot üzembehelyezési szolgáltatással. A regisztráció feldolgozása 48 órát is igénybe vehet. A regisztrációjuk törlése és a visszaállításuk után az AutoPilot üzembe helyezi az eszközöket.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Több regisztrálási állapot oldalprofil létrehozása és hozzárendelése Azure AD-csoportokhoz <!-- 2526564 -->
Mostantól több regisztrálási állapot oldalprofilt is [létrehozhat és hozzárendelhet](windows-enrollment-status.md) az Azure ADD-csoportokhoz.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migrálás a Készülékregisztrációs programból az Apple Business Managerbe az Intune-ban <!--2748613-->
Az Intune-ban működik az Apple üzleti Manager (ABM), és a fiókok frissíthetők a Készülékregisztrációs programból (DEP) az ABM-be. A folyamat az Intune-ban ugyanaz. Az Apple-fiók DEP-ről ABM-re való frissítéséhez lépjen a következő helyre: [ https://support.apple.com/en-us/HT208817]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Riasztás és Beléptetési állapot fülek az Eszközök beléptetése áttekintő képernyőn <!--2748656-->
A riasztások és a beléptetési hibák mostantól külön lapfüleken jelennek meg az Eszközök beléptetése áttekintő oldalon.

### <a name="device-management"></a>Eszközkezelés

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Alkalmazások korlátozása és a céges erőforrásokhoz való hozzáférés letiltása androidos eszközökön <!-- 2451462  -->  
Az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Android** > **Rendszerbiztonság** területen, az *Eszközbiztonság* szakaszban megjelent egy új, **Korlátozott alkalmazások** nevű beállítás. A **Korlátozott alkalmazások** beállítás egy megfelelőségi szabályzattal tiltja le a céges erőforrásokhoz való hozzáférést, ha bizonyos alkalmazások telepítve vannak az eszközön. Az eszköz addig nem megfelelőnek minősül, amíg a korlátozott alkalmazásokat el nem távolítják róla.
A következőkre vonatkozik: 
- Android




## <a name="week-of-september-24-2018"></a>2018. szeptember 24-i hét

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Office 365: Eszközkezelési adminisztrációs központ <!-- 3078424 -->
A Microsoft 365 többek között egyszerűsített felügyelet ígér, ezért az évek alatt integráltuk a Microsoft 365 háttérszolgáltatásait, amelyekkel olyan, teljes körű forgatókönyveket biztosítunk, mint az Intune vagy az Azure AD feltételes hozzáférése. Az új [Microsoft 365 felügyeleti központ](http://devicemanagement.microsoft.com) az a hely, amely összevonja, egyszerűsíti és integrálja a rendszergazdák felhasználói élményét. Az Eszközfelügyelet szakértői munkaterület könnyű hozzáférést biztosít az összes eszköz- és alkalmazásfelügyeleti információhoz és feladathoz, amelyre a szervezetnek szüksége lehet. Ez várhatóan a vállalati végfelhasználói számítástechnikai csapatok elsődleges felhőbeli munkaterületévé fog válni.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>További külső tanúsítványszolgáltatók (CA) támogatása <!-- 3093107 -->
Az Egyszerű tanúsítványigénylési protokoll (SCEP) segítségével mostantól kiadhat új tanúsítványokat, és meg is újíthat tanúsítványokat a Windows, iOS, Android és macOS rendszerű mobileszközökön.

### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Az Intune áttér az iOS 10 és újabb verziók támogatására <!-- 2454656 -->  
Az Intune-regisztráció, a céges portál és felügyelt böngésző mostantól csak az iOS 10 vagy újabb rendszert futtató iOS-eszközöket támogatják. A szervezet érintett eszközeinek és felhasználóinak megtekintéséhez az Azure Portalon lépjen az Intune > **Eszközök** > **Minden eszköz** elemre. Szűrje a találatokat operációs rendszer alapján, és az **Oszlopok** elemre kattintva megjelenítheti az operációs rendszerekre vonatkozó adatokat. Kérje meg az érintett felhasználókat, hogy frissítsék az eszközeiket egy támogatott operációsrendszer-verzióra.  

Ha az alábbi eszközök közül valamelyikkel rendelkezik, vagy szeretné ezek közül valamelyiket regisztrálni, ne feledje, hogy azok csak az iOS 9-es vagy régebbi verziókat támogatják.  Az Intune Céges portál további eléréséhez ezeket az eszközöket olyanokra kell cserélnie, amelyek támogatják az iOS 10-es és újabb verzióit:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. generáció) 
* iPad Mini (1. generáció)  

## <a name="week-of-september-17-2018"></a>2018. szeptember 17-i hét

### <a name="app-management"></a>Alkalmazáskezelés

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Alkalmazásvédelem állapotával kapcsolatos ismétlődő csempék eltávolítása <!-- 3083391 -->
A **Felhasználó állapota – iOS** és a **Felhasználó állapota – Android** csempék egyaránt jelen voltak az **Ügyfélalkalmazások – Áttekintés** oldalon, valamint az **Ügyfélalkalmazások – Alkalmazásvédelem állapota** oldalon. Az ismétlődés megszüntetése érdekében az állapotcsempék el lettek távolítva az **Ügyfélalkalmazások – Áttekintés** oldalról. 

## <a name="week-of-august-27-2018"></a>2018. augusztus 27-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Csomagalagút-kezelés támogatása az iOS-es alkalmazásonkénti VPN-profilok egyedi és Pulse Secure kapcsolattípusaihoz <!-- 1520957 -->
Az iOS-es alkalmazásonkénti VPN-profilok használatakor választhat az alkalmazásiréteg-beli (alkalmazásproxy) és csomagszintű (csomagalagút) alagútkezelés között. Ezek a beállítások a következő kapcsolattípusokkal érhetők el:
- Egyéni VPN
- Pulse Secure Ha nem biztos a megfelelő értékben, tekintse meg a VPN-szolgáltató dokumentációját.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>iOS-es szoftverfrissítések megjelenítésének késleltetése az eszközön <!-- 1949583 -->
Az Intune > **Szoftverfrissítések** > **iOS-es szabályzatok frissítése** területen konfigurálhatja, hogy mely napon, mely időpontban ne telepítsenek frissítéseket az eszközök. Egy jövőbeli frissítéssel 1-90 napig késleltetheti a szoftverfrissítések láthatóvá válását az eszközön. 
A [Microsoft Intune iOS frissítési szabályzatok konfigurálása](software-updates-ios.md) területen látható a jelenlegi beállítások listája.

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus verzió <!-- 2213968 -->
Amikor Intune-t használó Windows 10 rendszerű eszközökhöz rendeli hozzá az Office 365 ProPlus-alkalmazásokat, kiválaszthatja az Office-verziót. Az Azure Portalon válassza a **Microsoft Intune** > **Alkalmazások** > **Alkalmazás hozzáadása** lehetőséget. Ezután válassza az **Office 365 ProPlus csomag (Windows 10)** lehetőséget a **Típus** legördülő menüből. Kattintson az **Alkalmazáscsomag beállításai** elemre a kapcsolódó panel megjelenítéséhez. Állítsa be a **Frissítési csatornát** például a **Havonta** értékre. Azt is megteheti, hogy az **Igen** elemre kattintva törli az Office (msi) másik verzióját a végfelhasználói eszközökről. Kattintson az **Adott** elemre az Office adott verziójának telepítéséhez a végfelhasználói eszközök kiválasztott csatornáján. Ekkor kiválaszthatja az Office **adott verzióját** a használathoz. Az elérhető verziók idővel változni fognak. Ezért egy új központi telepítés létrehozásakor újabb verziók válhatnak elérhetővé, és előfordulhat, hogy egyes régebbi verziók már nem érhetők el. A jelenleg üzemelő példányok továbbra is a régebbi verziót telepítik, de a verziólista csatornánként folyamatosan frissül. További információkért lásd: [Az Office 365 ProPlus frissítési csatornáinak áttekintése](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Támogatás a Windows 10 VPN DNS-beállításának regisztrálásához <!-- 2282852 -->
A Windows 10 VPN-profilokat ettől a frissítéstől kezdve úgy is konfigurálhatja, hogy egyéni profilok használata nélkül is dinamikusan regisztrálják a belső DNS-ben a VPN-interfészhez rendelt IP-címeket.
A [Windows 10 VPN-beállítások](vpn-settings-windows-10.md) című témakörben további információkat talál a jelenleg elérhető VPN-profilbeállításokról. 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>A macOS-es Céges portál telepítő mostantól a verziószámot is tartalmazza a telepítőfájl nevében <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>iOS – automatikus alkalmazásfrissítések <!-- 2729759 -->
Az automatikus alkalmazásfrissítések eszköz- és felhasználói licencelésű alkalmazások esetén is működnek az iOS 11.0 és újabb verzióin.




### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>A Windows Hello a jövőben felhasználókat és eszközöket céloz meg <!-- 1106609 -->
A [Windows Hello for Business](windows-hello.md) szabályzatának létrehozásakor a szabályzat az összes cégen belüli felhasználóra vonatkozik (a bérlő egészén). Ezzel a frissítéssel a szabályzat alkalmazható lesz egy adott eszközkonfigurációs szabályzatot használó konkrét felhasználókra és eszközökre is (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Identitásvédelem** > **Windows Hello for Business**).
Az Azure Portalon az Intune-ban a Windows Hello konfigurációja és beállításai az **Eszközregisztráció** és az **Eszközkonfiguráció** területen is jelen vannak. Az **Eszközregisztráció** a teljes céget célozza (a bérlő egészén), és támogatja a Windows AutoPilot (Kezdőélmény) programot. Az **Eszközkonfiguráció** azokat az eszközöket és felhasználókat célozza, amelyek a bejelentkezéskor alkalmazott szabályzatot használják.
Ez a funkció az alábbiakra vonatkozik:  
- Windows 10 és újabb
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Elérhető Zscaler-kapcsolat az iOS-es VPN-profilok számára <!-- 1769858 -->
Az iOS-es VPN-eszközregisztrációs profil létrehozásakor (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **iOS** platform > **VPN** profiltípus), több kapcsolattípus áll rendelkezésre, többek között a Cisco és a Citrix. Ez a frissítés a Zscalert is hozzáadja a kapcsolattípusokhoz. 
[Az iOS rendszerű eszközökre vonatkozó VPN-beállítások](vpn-settings-ios.md) című cikk felsorolja az elérhető kapcsolattípusokat.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>FIPS mód Windows 10-es nagyvállalati Wi-Fi-profilokhoz <!-- 1879077 -->
Mostantól engedélyezhető a Federal Information Processing Standards (FIPS) Windows 10-es nagyvállalati Wi-Fi-profilokhoz az Azure-beli Intune-portálon. Ügyeljen arra, hogy a FIPS mód a Wi-Fi-infrastruktúrán is engedélyezve legyen, ha a Wi-Fi-profilokon engedélyezi.
A Wi-Fi-profilok létrehozását a [Wi-Fi-beállítások Windows 10 és újabb rendszerű eszközökhöz az Intune-ban](wi-fi-settings-windows.md) című témakör ismerteti.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>S mód szabályzása Windows 10 és újabb rendszerű eszközökön – nyilvános előzetes verzió <!-- 1958649 -->
Ettől a funkciófrissítéstől kezdve olyan eszközkonfigurációs profilt hozhat létre, amely a Windows 10 rendszerű eszközön kikapcsolja az S módot, vagy megakadályozza, hogy a felhasználók kikapcsolják az S módot. Ez a funkció a következő helyen található meg: Intune > **Eszközkonfiguráció** > **Profilok** >  **Windows 10 és újabb** > **Kiadásfrissítés és módkapcsoló**.
Az S módról az [S módú Windows 10 bemutatása](https://www.microsoft.com/windows/s-mode) című részben talál több információt.
Érvényes: a [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) legfrissebb buildjére (amíg az előzetes verzióban van).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP konfigurációs csomag automatikus hozzáadása a konfigurációs profilhoz <!-- 2144658 -->
Ha a [Komplex veszélyforrások elleni védelem használata mellett készít elő](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) eszközöket az Intune-ban, ehhez korábban le kellett töltenie egy konfigurációs csomagot, melyet aztán hozzáadott a konfigurációs profilhoz. Ettől a frissítéstől kezdve az Intune automatikusan megkapja a csomagot a Windows Defender biztonsági központtól, és hozzáadja azt az Ön profiljához.
A Windows 10 és újabb verziókra vonatkozik.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Felhasználók csatlakozásának megkövetelése az eszköz telepítése során <!--2311457-->
Az eszközprofilok beállíthatók úgy, hogy megköveteljék az eszköz hálózathoz csatlakozását, mielőtt továbblépnének a Hálózat oldalon a Windows 10 telepítése során. Amíg ez a funkció előzetes verziójú, a beállítás használatához a Windows Insider 1809-es buildje, vagy annál újabb verzió szükséges.
Érvényes: a [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) legfrissebb buildjére (amíg az előzetes verzióban van).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Alkalmazások korlátozása és a céges erőforrásokhoz való hozzáférés letiltása iOS és Android Enterprise rendszerű eszközökön <!-- 2451462 -->
Az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **iOS** > **Rendszerbiztonság** területen új, **Korlátozott alkalmazások** beállítás jelent meg. Az új beállítás egy megfelelőségi szabályzattal tiltja le a céges erőforrásokhoz való hozzáférést, ha bizonyos alkalmazások telepítve vannak az eszközön. Az eszköz addig nem megfelelőnek minősül, amíg a korlátozott alkalmazásokat el nem távolítják róla.
A következőre vonatkozik: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Modern VPN-támogatási frissítések iOS-hez <!-- 2459928, 1819876, and 2650856 -->
Ez a frissítés a következő iOS VPN-ügyfelekhez nyújt támogatást: 
- F5 Access (3.0.1 és újabb verziók)
- Citrix SSO
- Palo Alto Networks GlobalProtect (5.0 és újabb verziók) Szintén ebben a frissítésben:
- A jelenlegi **F5 Access** kapcsolattípus új neve iOS rendszeren **F5 Access Legacy**.
- A jelenlegi **Palo Alto Networks GlobalProtect** kapcsolattípus új neve iOS rendszeren **Palo Alto Networks GlobalProtect (legacy)**.
Az ezekkel a kapcsolattípusokkal létező profilok továbbra is működnek a megfelelő örökölt VPN-ügyfelekkel. Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN, vagy Palo Alto Networks GlobalProtect 4.1 vagy korábbi verzió iOS-es használata esetén át kell térnie az új alkalmazásokra. Tegye meg ezt minél előbb annak érdekében, hogy a VPN hozzáférhető legyen az iOS-eszközökön, amikor iOS 12-re frissülnek.
Az iOS 12-ről és a VPN-profilokról a [Microsoft Intune ügyfélszolgálat blogjában](https://go.microsoft.com/fwlink/?linkid=2013806) talál további információt.

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Megfelelőségi szabályzatok exportálása a klasszikus Azure-portálról, és azok újbóli létrehozása az Azure-beli Intune-portálon <!-- 2469637 -->
A klasszikus Azure-portálon létrehozott megfelelőségi szabályzatok hamarosan elavulnak. Áttekintheti és törölheti a meglévő megfelelőségi szabályzatokat, de már nem frissítheti őket. Ha megfelelőségi szabályzatokat kell az Azure-beli Intune-portálra migrálnia, akkor veszővel tagolt (*.csv*) fájlként exportálhatja azokat. Ezt követően a fájlban lévő adatok felhasználásával újra létrehozhatja a szabályzatokat az Azure-beli Intune-portálon.

> [!IMPORTANT]
> A klasszikus Azure-portál kivonása után többé nem fér majd hozzá megfelelőségi szabályzataihoz, és meg sem tekintheti azokat. Ezért ne feledje exportálni és az Azure Portalon újra létrehozni szabályzatait még a klasszikus Azure-portál elavulása előtt.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile – Új mobileszköz-védelmi partner <!-- 22662717 -->
A vállalati erőforrások mobil elérése kockázatfelmérésen alapuló feltételes hozzáféréssel korlátozható. A kockázatfelmérést a Better Mobile végzi, amely egy, a Microsoft Intune-nal integrálható, veszélyforrások elleni mobileszköz-védelmi megoldás.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>A Céges portál zárolása egyalkalmazásos módban a felhasználó bejelentkezéséig <!--1067692 --> 
A Céges portált egyalkalmazásos módban is futtathatja, ha a DEP-regisztráció során a felhasználót a beállítási asszisztens helyett a Céges portálon keresztül hitelesíti. Ez a beállítás a beállítási asszisztens futtatása után azonnal zárolja az eszközt, így a felhasználónak a hozzáféréshez be kell jelentkeznie. A folyamat biztosítja, hogy az eszköz az előkészítés teljes folyamatán végigmenjen, és ne maradjon hozzárendelt felhasználó nélkül.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Felhasználóbarát rövid név hozzáadása Autopilot-eszközökhöz <!--1346521 -->
Mostantól [egyetlen Autopilot-eszközhöz is rendelhető felhasználó](enrollment-autopilot.md). A rendszergazdák rövid nevet is létrehozhatnak a felhasználó üdvözléséhez az eszköz AutoPilottal történő beállításakor.
Érvényes: a [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) legfrissebb buildjére (amíg az előzetes verzióban van).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP eszközlicencek használata a Céges portál előzetes kiépítésére a DEP-regisztráció során <!-- 1608345 -->
Mostantól mennyiségi vásárlási program (Volume Purchase Program, VPP-) eszközlicencekkel előre is kiépítheti a Céges portált, amikor regisztrál a készülékregisztrációs programban (DEP-ben). Ehhez a [regisztrációs profil létrehozása vagy szerkesztése](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) során kell megadni a Céges portál telepítéséhez használni kívánt VPP-jogkivonatot. Fontos, hogy a jogkivonat ne járjon le, és hogy elég licenccel rendelkezzen a Céges portál alkalmazáshoz. Amennyiben a jogkivonat lejár vagy a licencei elfogynak, az Intune az App Store-beli Céges portált fogja leküldeni (ilyenkor a rendszer kéri az Apple-azonosítót).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Megerősítés szükséges a Céges portál kiépítéséhez éppen használt VPP-jogkivonat törléséhez <!-- 2237634 -->
Mostantól meg kell erősíteni az olyan Volume Purchase Program- (VPP-) jogkivonatok törlését, amelyek éppen a Céges portál előre kiépítéséhez vannak használatban a DEP-regisztráció során.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows személyes eszközregisztráció letiltása <!-- 1849498 -->
[Letilthatja a Windows rendszerű személyes eszközök](enrollment-restrictions-set.md#set-device-type-restrictions) regisztrációját az Intune [mobileszköz-kezelésében](windows-enroll.md). Ez a funkció nem alkalmas az [Intune PC-ügynök](manage-windows-pcs-with-microsoft-intune.md) használatával regisztrált eszközök letiltásához. Ez a funkció a következő néhány hét során lesz bevezetve, így előfordulhat, hogy nem látja azonnal a felhasználói felületen.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Gépnév-minták megadása egy Autopilot-profilban <!--1849855-->
[Gépnév-sablont adhat meg](enrollment-autopilot.md#create-an-autopilot-deployment-profile) a [gép nevének](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) Autopilot-regisztráció során történő létrehozásához és beállításához. Érvényes: a [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) legfrissebb buildjére (amíg az előzetes verzióban van).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>A Windows Autopilot-profiloknál a céges bejelentkezési oldalon és a tartományi hibalapon elrejthető lesz a fiókváltoztatás lehetősége <!--1901669 -->
[Új Windows Autopilot-profilbeállítások](enrollment-autopilot.md#create-an-autopilot-deployment-profile) állnak rendelkezésre a rendszergazdák részére, amelyekkel elrejthetik a fiókváltoztatás lehetőségét a céges bejelentkezési oldalon és a tartományi hibalapon. A beállítás elrejtése akkor lehetséges, ha az Azure Active Directoryban konfigurálva van a Vállalati védjegyezés. Érvényes: a [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) legfrissebb buildjére (amíg az előzetes verzióban van).



### <a name="device-management"></a>Eszközkezelés

#### <a name="delete-jamf-devices----2653306--"></a>JAMF-eszközök törlése <!-- 2653306-->
A JAMF által felügyelt eszközök az **Eszközök** > JAMF-eszköz kiválasztása > **Törlés** lehetőséggel törölhetők.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>A terminológia módosítása „kivonás” és „törlés” kifejezésekre <!-- 2175759 -->
A Graph API-val való konzisztencia érdekében az Intune felhasználói felületén és a dokumentációban az alábbi terminológiai változásokat vezettük be:
- A **Céges adatok eltávolítása** kifejezést a „Kivonás” kifejezés váltja fel
- A **Gyári beállítások visszaállítása** kifejezést a **törlés** váltja fel

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Megerősítő párbeszédpanel jelenik meg, ha egy rendszergazda MDM leküldéses tanúsítványt próbál törölni <!-- 297909500-->
Ha valaki egy Apple MDM Push-tanúsítvány törlését kezdeményezi, egy megerősítő párbeszédpanelen megjelenik a kapcsolódó iOS- és macOS-eszközök száma. A tanúsítvány törlése esetén ezeket az eszközöket újra kell regisztrálni.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>A Windows Installer további biztonsági beállításai <!-- 2282430 -->
Engedélyezheti a felhasználóknak az alkalmazástelepítések szabályozását. Ha engedélyezve van, azok a telepítések, amelyek a biztonság megsértése miatt le lettek volna állítva engedélyt kapnak a folytatásra. Megadhatja, hogy a Windows Installer emelt szintű engedélyeket használjon, amikor programokat telepít a rendszerben. Emellett engedélyezheti a Windows Information Protection (WIP) elemek indexelését és az ezekre vonatkozó metaadatok titkosítatlan helyen való tárolását. A szabályzat tiltásakor a WIP által védett elemek nem lesznek indexelve és nem jelennek meg a Cortana vagy a fájlkezelő eredményei között. Ezeknek a beállításoknak a funkciói alapértelmezés szerint le vannak tiltva. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Új frissítés a felhasználói felülethez a Céges portál webhelyen <!--2000968 -->
A felhasználók visszajelzései alapján új funkciókkal egészült ki a Céges portál webhely. Jelentős javulást fog tapasztalni eszközei már meglévő funkciói és használhatósága terén. Új, modern és rugalmas külsőt kaptak a webhely különböző területei, &ndash;köztük az eszközadatok, a visszajelzés, a támogatás és az eszközök áttekintése&ndash;. Amit még tapasztalni fog:

- Zökkenőmentes munkafolyamatok minden eszközplatformon
- Hatékonyabb eszközazonosítási és beléptetési folyamatok
- Praktikusabb hibaüzenetek
- Barátságosabb nyelvezet, kevesebb műszaki zsargon
- Alkalmazások közvetlen hivatkozásainak megoszthatósága
- Nagy méretű alkalmazáskatalógusok javított teljesítménye
- Nagyobb hozzáférhetőség minden felhasználó számára  

Az [Intune Céges portál webhelyének dokumentációja](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) frissítve lett, hogy tükrözze a változásokat. Az alkalmazás fejlesztéseire a [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-app-ui.md) oldalon láthat egy példát.  

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Továbbfejlesztett függetlenítésészlelés a megfelelőségi jelentéskészítés során <!-- 2198738 -->
A továbbfejlesztett függetlenítésészlelés beállítás állapota mostantól minden megfelelőségi jelentésben megjelenik a felügyeleti konzolon.

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-for-policies---1081974---"></a>Hatókörcímkék a szabályzatokhoz <!--1081974 -->
[Hatókörcímkék létrehozásával](scope-tags.md) korlátozható a hozzáférés az Intune erőforrásaihoz. Adjon hozzá hatókörcímkét egy szerepkör-hozzárendeléshez, majd adja hozzá a hatókörcímkét egy konfigurációs profilhoz. A szerepkör csak a megfelelő hatókörcímkével rendelkező (vagy hatókörcímke nélküli) erőforrásokhoz férhet hozzá.

## <a name="week-of-august-14-2018"></a>2018. augusztus 14-i hét

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS-támogatás az Apple Készülékregisztrációs programjában <!-- 747651 -->
Az Intune mostantól támogatja a macOS rendszerű eszközök regisztrálását az Apple készülékregisztrációs programjába (DEP). További információkért lásd: [macOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>2018. július 23-ai hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1895847 -->
A Microsoft Intune lehetővé teszi macOS üzletági alkalmazások **Kötelező** vagy **Regisztrációval elérhető** beállítással való üzembe helyezését. A végfelhasználók elvégezhetik az alkalmazások **Rendelkezésre álló** állapotban való üzembe helyezését a macOS-es céges portálon vagy a [Céges portál webhelyén](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>A Kioszk mód támogatása beépített iOS-alkalmazások számára <!-- 2051098 -->
iOS-eszközökön a Store-alkalmazások és a Felügyelt alkalmazások mellet mostantól a beépített alkalmazásoknál is (mint például a Safari) kiválasztható a Kioszk mód.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Az Office 365 Pro Plus alkalmazás üzemelő példányának szerkesztése <!-- 2150145 -->
Microsoft Intune-rendszergazdaként több lehetősége van saját Office 365 Pro Plus üzemelő példányainak szerkesztésére. Továbbá, ezentúl már nem szükséges törölni az üzemelő példányokat az alkalmazáscsomag tulajdonságainak megváltoztatásához. Az Azure Portalon válassza a **Microsoft Intune** > **Ügyfélalkalmazások** > **Alkalmazások** lehetőséget. Az alkalmazások listáján jelölje ki a saját Office 365 Pro Plus csomagot.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Már elérhető az Androidhoz használható frissített Intune App SDK <!-- 2744271-->

Elérhető az Androidhoz használható Intune App SDK frissített verziója, mely támogatja az Android P kiadását. Ha Ön alkalmazásfejlesztő, és az Intune App SDK-t használja Androidhoz, telepítenie kell az Intune App SDK frissített verzióját, hogy biztosíthassa az Intune megfelelő működését az alkalmazásainál Android P-eszközökön. Az Intune App SDK jelen frissített verziója tartalmaz egy beépülő modult, amely gondoskodik az SDK frissítéseiről. A már meglévő integrált kódokat nem szükséges újraírnia. További információt az [Intune App SDK Androidhoz](https://github.com/msintuneappsdk/ms-intune-app-sdk-android) című témakörben talál. Ha az Intune-hoz a régi megjelölő stílust használja, javasoljuk, hogy használja az aktatáska ikont. A márkajelzési részletekről [ebben a GitHub-adattárban](https://github.com/msintuneappsdk/intune-app-partner-badge) tájékozódhat.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Eszközmegfelelési szabályzat létrehozása macOS-eszközökön a tűzfalbeállítások használatával <!-- 1497640 -->
Amikor új macOS-es megfelelőségi szabályzatot hoz létre (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: macOS** > **Rendszerbiztonság**), a **Tűzfal** új beállításai válnak elérhetővé: 

- **Tűzfal**: Hogyan bejövő kapcsolatok konfigurálása a környezet kezeli.
- **A bejövő kapcsolatok**: **Blokk** minden bejövő kapcsolat, kivéve az alapvető internetes szolgáltatások, például a DHCP, Bonjour és az IPSec szükséges. Ez a beállítás letiltja az összes megosztási szolgáltatást is.
- **Rejtett üzemmód**: **Engedélyezése** rejtett üzemmód megakadályozza, hogy az eszköz kérelmekre. Az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre.

A macOS 10.12 és újabb verziókra vonatkozik

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Új Wi-Fi eszközkonfigurációs profil Windows 10 vagy újabb rendszerhez <!-- 1879077 -->
Wi-Fi profilok jelenleg XML-fájlok használatával importálhatók és exportálhatók. A frissítésnek köszönhetően a Wi-Fi eszközkonfigurációs profilok már közvetlenül az Intune-ban is létrehozhatóak, ahogyan néhány más platform esetében is.

A profil létrehozásához nyissa meg az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Wi-Fi** elemet. 

A Windows 10 és újabb verziókra vonatkozik.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>A Kioszkmód – elavult lehetőség nem használható és nem módosítható <!-- 2149998 -->
A [Kioszkmód funkció](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Eszközkorlátozások**) elavult. Helyét a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) veszi át. A frissítés után a **Kioszkmód – Elavult** funkció már nem lesz kiválasztható, és a felhasználói felület nem módosítható és nem frissíthető. 

A kioszkmód a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával engedélyezhető.

Windows 10 vagy újabb, és a Windows Holographic for Business rendszerekre vonatkozik

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Az API-k külső hitelesítésszolgáltatókat használnak <!-- 2184013 -->
A frissítés tartalmaz egy Java API-t, amely engedélyezi a külső hitelesítésszolgáltatók számára az Intune- és az SCEP-integrációt. A felhasználók így hozzáadhatják egy profilhoz az SCEP-tanúsítványt, és alkalmazhatják az MDM-et használó eszközökre.

Az Intune jelenleg az [Active Directory tanúsítványszolgáltatást használó SCEP-kérelmeket](certificates-scep-configure.md) támogatja.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>A Munkamenet befejezése gomb megjelenítése ki- és bekapcsolható a kioszkmódú böngészőkben <!-- 2455253 -->
Mostantól konfigurálható, hogy a kioszkmódú böngészőkben megjelenjen-e a Munkamenet vége gomb. A vezérlő az **Eszközkonfiguráció** > **Kioszkmód (előzetes verzió)** >  **kioszkmódú webböngésző** alatt található. Bekapcsolása esetén, ha a felhasználó a gombra kattint, az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot töröl, és visszatér az alapértelmezett URL-címre.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM mobilkonfigurációs profil létrehozása <!-- 2564077 -->
Az **Eszközkonfiguráció** alatt létre lehet hozni egy eSIM mobilprofilt. Importálható lesz egy fájl, amely a mobilszolgáltató által megadott mobiltelefon-aktiválási kódokat tartalmazza. Ezek a profilok aztán alkalmazhatók lesznek az eSIM LTE-t engedélyező Windows 10 rendszerű eszközökön, amilyen a Surface Pro LTE és más eSIM-képes eszközök.

Ellenőrizze, hogy [eszközei támogatják-e az eSIM-profilokat](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

A Windows 10 és újabb verziókra vonatkozik. 




### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>A Samsung Knox Mobile Enrollment használatával regisztrált Androidos eszközök automatikus megjelölése „cégesként”. <!-- 2404851 -->
A Samsung Knox Mobile Enrollment használatával regisztrált Androidos eszközök alapértelmezés szerint **céges** megjelölést kapnak az **Eszköz tulajdonosa** alatt. Ezentúl nincs szükség a céges eszközök IMEI- vagy sorozatszám alapján történő manuális azonosítására a Knox Mobile Enrollment használatával végzett regisztráció előtt.

### <a name="device-management"></a>Eszközkezelés

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Eszközök tömeges törlése az Eszközök panelen <!-- 1793693 -->

Az Eszközök panelen mostantól egyszerre több eszközt is törölhet. Válassza az **Eszközök** > **Minden eszköz** lehetőséget >jelölje ki a törölni kívánt eszközöket > válassza a **Törlés** lehetőséget. A nem törölhető eszközök esetében riasztás fog megjelenni.

## <a name="week-of-july-16-2018"></a>2018. július 16-ai hét  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>További szinkronizálási lehetőségek a windowsos Céges portál alkalmazásban  
A Windowsos Céges portál alkalmazás mostantól lehetővé teszi, hogy a szinkronizálási folyamatot közvetlenül a Windows tálcájáról vagy a Start menüből is elindíthassa. Ez a funkció abban az esetben igazán hasznos, ha csak szinkronizálni szeretné eszközeit, hogy utána hozzáférhessen a vállalati erőforrásokhoz. Az új funkció eléréséhez jobb gombbal kattintson a Céges portál alkalmazás ikonjára a tálcán vagy a Start menüben. A megjelenő menüpontok közül (azaz a gyorslistában) válassza **Az eszköz szinkronizálása** lehetőséget. Megnyílik a Céges portál alkalmazás **Beállítások** lapja és megkezdődik a szinkronizálás. Az új funkciók megtekintéséhez lásd: [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md)   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Új böngészési élmény a windowsos céges portál alkalmazásban  

Ha a windowsos Céges portál alkalmazásban alkalmazásokat böngész vagy keres, mostantól válthat a meglévő **Csempék** nézet és az újonnan hozzáadott **Részletek** nézet között. Az új nézet az alkalmazások adatait jeleníti meg, például a nevet, a kiadót, a kiadás dátumát és a telepítés állapotát.  

Az **Alkalmazások** lapon található egy **Telepítve** nézet is, amely a befejezett és a folyamatban lévő telepítések adatait jeleníti meg. Az új nézet megtekintéséhez lásd: [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md)  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>A céges portál alkalmazás továbbfejlesztett felhasználói élménye készülékregisztráció-kezelők használatakor  
Ha egy készülékregisztráció-kezelő (DEM) bejelentkezik a windowsos céges portál alkalmazásba, az alkalmazás csak a készülékregisztráció-kezelő jelenlegi, éppen futó eszközét jeleníti meg. Ennek a fejlesztésnek köszönhetően kevesebb olyan időtúllépés fog történni, amely korábban akkor jelentkezett, ha az alkalmazás megpróbálta megjeleníteni a kezelő által regisztrált összes eszközt.  


## <a name="week-of-july-9-2018"></a>2018. július 9-ei hét

### <a name="app-management"></a>Alkalmazáskezelés

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Alkalmazás-hozzáférés letiltása a nem jóváhagyott eszközgyártókon és -modelleken <!-- 1425689 ! -->
Az Intune rendszergazdái egy adott Android-gyártókat és/vagy iOS-modelleket tartalmazó listát kényszeríthetnek az Intune App Protection-szabályzatokkal. A rendszergazda egy pontosvesszőkkel elválasztott listában adhat meg gyártókat az Android-szabályzatokhoz, valamint eszközmodelleket az iOS-szabályzatokhoz. Az Intune App Protection-szabályzatok csak Android- és iOS-eszközökre vonatkoznak. A megadott listán két különálló művelet hajtható végre:
- Az alkalmazás-hozzáférés letiltása a nem megadott eszközökön,
- vagy a vállalati adatok szelektív törlése a nem megadott eszközökön. 

A felhasználó nem férhet hozzá a célalkalmazáshoz, ha az nem felel meg a szabályzat feltételeinek. A rendszer a beállítások alapján letilthatja a felhasználót, vagy szelektíven törölheti annak vállalati adatait az alkalmazáson belül. IOS-eszközökön a funkcióhoz az alkalmazásoknak (például WXP, Outlook, Managed Browser, Yammer) integrálniuk kell az Intune App SDK-t, hogy a megcélzott alkalmazásokon kötelezővé lehessen tennie ezt a funkciót. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Android-eszközökön ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség. 

A végfelhasználói eszközökön az Intune-ügyfél az Application Protection-szabályzatok Intune-panelén megadott egyszerű sztringegyezések alapján végez műveleteket. Ez teljes mértékben az eszköz által jelentett értéktől függ. Ennek fényében a rendszergazának kell ügyelnie arra, hogy a kívánt viselkedés az elvártnak megfelelően működjön. Ezt úgy lehet elérni, ha teszteli a beállítást különböző eszközgyártókkal és -modellekkel egy kisebb felhasználói csoportban. A Microsoft Intune-ban válassza az **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget az alkalmazásvédelmi szabályzatok megtekintéséhez és hozzáadásához. Az alkalmazásvédelmi szabályzatokkal kapcsolatos további információért lásd: [Mik azok az alkalmazásvédelmi szabályzatok](app-protection-policy.md) és [Szelektív adattörlés alkalmazásvédelmi szabályzatok hozzáférési műveleteivel az Intune-ban](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Hozzáférés a macOS Céges portáljának kiadás előtti buildjéhez <!-- 1734766 -->
A Microsoft AutoUpdate-tel regisztrálhat, hogy korábban megkapja a buildeket, ha csatlakozik az Insider programhoz. A regisztráció lehetővé teszi a frissített Céges portál használatát, még mielőtt az elérhetővé válna a végfelhasználók számára. További információért lásd a [Microsoft Intune blogját](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>2018. július 2-ai hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Az iOS-alkalmazáskonfigurációk figyelése minden egyes eszközön <!-- 880037 -->
A Microsoft Intune rendszergazdájaként minden egyes felügyelt eszközön nyomon követheti az iOS-alkalmazáskonfiguráció állapotát. Az Azure Portal **Microsoft Intune** oldalán kattintson az **Eszközök** > **Minden eszköz** lehetőségre. A felügyelt eszközök listáján az egyik eszközre kattintva nyissa meg a hozzá tartozó panelt. Az eszköz paneljén kattintson az **Alkalmazáskonfiguráció** elemre.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Az alkalmazásvédelmi szabályzatok műveleteinek elérése <!-- 1483510 -->
Konfigurálhatja az alkalmazásvédelmi szabályzatokat, hogy azokkal törölje, letiltsa vagy figyelmeztesse a nem megfelelő eszközöket. A *törlés* művelettel eltávolítja a vállalati adatokat az eszközről. Törlés esetén az eszköz felhasználója értesítést kap a törlés okáról és a lehetséges szervizelési lépésekről. Egyes beállítások – például az operációs rendszer minimális verziója – esetén több műveletet is alkalmazhat, például letiltás és törlés. Ne feledje, hogy ezek a műveletek az alkalmazás indításakor aktiválódnak.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Céges alkalmazásadatok szelektív törlése <!-- 1507030 -->
A rendszergazdák új műveletként konfigurálhatják a céges adatok szelektív törlését, ha az alkalmazásvédelmi szabályzatok (APP) hozzáférési beállításai nem teljesülnek.  Ez a funkció lehetővé teszi a rendszergazdák számára, hogy a céges adatokat automatikusan védjék vagy távolítsák el az előre konfigurált feltételeken alapuló alkalmazásokról.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Mennyiségi vásárlási program keretében beszerzett iOS-alkalmazás visszavonása <!-- 1777384 -->
A Microsoft Intune rendszergazdájaként visszavonhatja a mennyiségi vásárlási program (Volume Purchase Program, VPP) keretében vásárolt kiválasztott iOS-es alkalmazás összes licencét. Értesítheti a felhasználókat, amikor megszűnik egy felhasználói licenccel rendelkező alkalmazás hozzájuk rendelése. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. A visszavont licencek száma látható lesz az Intune **Alkalmazások** tevékenységcsoportján belüli **Licencelt alkalmazások** csomóponton. Az iOS-es VPP-alkalmazásokkal kapcsolatos további információkat a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakörben tekintheti meg.

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>A Céges portál alkalmazás meg nem felelésről szóló üzeneteinek frissítései <!-- 1832222 -->
Felülvizsgáltuk az üzeneteket, amelyeket az eszközök felhasználói akkor kapnak, ha az eszköz nem megfelelő. Az üzenetek eredeti jelentése megmaradt, de barátságosabb hangnemben, kevesebb szakzsargonnal fogalmaztuk át őket. Frissítettük a dokumentációra és a megoldási lépésekre mutató hivatkozásokat is, hogy naprakészek legyenek.
Az alábbi szöveg eredeti és átdolgozott változata a megjelenő üzenetek javítását példázza:
- **Mielőtt**: *Ez az eszköz nem lépett kapcsolatba az Intune szolgáltatás a szükséges a rendszergazda által megadott időszakban A probléma megoldásához nyissa meg a Céges portál alkalmazást az eszközön, és kattintson a Megfelelőség ellenőrzése gombra.*
- **Miután**: *Az eszköz még nem jelentkezett be az a szervezet egy ideje. A kapcsolat újbóli felvételéhez nyissa meg a Céges portál alkalmazást az eszközön, és koppintson a Beállítások ellenőrzése lehetőségre.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP-alkalmazáslicenc visszavonása <!-- 1863797 -->
Rendszergazdaként visszavonhatja egy eszköz vagy egy felhasználó hozzárendelt iOS VPP-alkalmazáslicencét. Az iOS VPP-alkalmazás eltávolítása az alkalmazás licencének visszavonását is lehetővé teszi. Az alkalmazás eltávolítása előtt a felhasználót vagy az eszközt ki kell vonni az alkalmazás céljaként megadott csoportból. A felhasználó vagy az eszköz csoportból való eltávolításával elkerülhető az alkalmazás újratelepítése. Ezeknek a lépéseknek a követése után az alkalmazáslicencet hozzárendelheti egy másik felhasználóhoz vagy eszközhöz. Az iOS VPP-alkalmazáslicencekre vonatkozó további információkat az [iOS mennyiségi programban vásárolt alkalmazások kezelése a Microsoft Intune-ban](vpp-apps-ios.md) című témakörben tekintheti meg.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Eszközkategóriák kiválasztása a „Hozzáférés munkahelyi vagy iskolai rendszerhez” beállításokkal <!-- 1058963 eenotready --> 
Ha engedélyezte az [eszközcsoport-leképezést](https://docs.microsoft.com/intune/device-group-mapping), a Windows 10-felhasználókat felkéri a rendszer egy eszközkategória választására, miután regisztráltak a **Gépház** > **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** területen elérhető **Csatlakozás** gombbal. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>sAMAccountName használata fiókhoz tartozó felhasználónévként az e-mail profilokhoz <!-- 1500307 -->
Fiókhoz tartozó felhasználónévként használhatja a helyszíni **sAMAccountName** nevet az Android-, iOS- és Windows 10 rendszerű e-mail-profilokhoz. Használhatja az Azure Active Directory (Azure AD) `domain` vagy `ntdomain` attribútumából is a tartományt. Vagy adjon meg egy egyéni statikus tartományt.

A funkció használatához szinkronizálnia kell a(z) `sAMAccountName` attribútumot a helyszíni Active Directory-környezetből az Azure AD-ra.

[Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 és későbbi verziókra](email-settings-windows-10.md) vonatkozik.

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ütköző eszközkonfigurációs profilok kiemelése <!-- 1556983 -->
Az **Eszközkonfiguráció** alatt megjelenik a meglévő profilok listája. Ez a frissítés ezt egy újabb oszloppal bővíti, amely az ütköző profilokról közöl részleteket. Egy ütközést jelző sor kiválasztásával megjeleníthető az ütközést okozó beállítás és profil. 

További tudnivalók a [konfigurációs profilok kezeléséről](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Új eszközmegfelelőségi eszközállapotok <!-- 2308882 -->
A következő új állapotok lettek hozzáadva az **Eszközmegfelelőség** > **Szabályzatok** > egy szabályzat kijelölése > **Áttekintés** alatt:
- Sikerült
- Hiba
- Ütközés
- Függőben lévő
- Nem alkalmazható Egy olyan kép is megjelenik, amely mutatja a más platformon lévő eszközszámot. Például egy iOS-profil megtekintése esetén a profilhoz rendelt, nem iOS rendszerű eszközök száma is látható lesz az új csempén. Lásd: [Eszközmegfelelési szabályzatok](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Az eszközmegfelelőség támogatja a harmadik féltől származó vírusvédelmi megoldásokat <!-- 2325484 -->
Eszközmegfelelőségi szabályzat létrehozásakor (**eszközmegfelelőség** > **házirendek** > **szabályzat létrehozása**  >  **Platform: Windows 10-es és újabb verziók** > **beállítások** > **rendszerbiztonság**), új **[Eszközbiztonsági](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** beállítások: 
- **A víruskereső**: Ha a beállítása **megkövetelése**, ellenőrizheti a megfelelőségi regisztrált Windows-Security Center, például a Symantec és a Windows Defender víruskereső megoldásokkal. 
- **Kémprogram-elhárító**: Ha beállítása **megkövetelése**, ellenőrizheti a megfelelőségi Windows a Security Center, például a Symantec és a Windows Defender regisztrált kémprogram-elhárító megoldásokkal. 

A következőkre vonatkozik: Windows 10 és újabb 

### <a name="device-enrollment"></a>Eszközök beléptetése

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Profil nélküli eszközök oszlop a regisztrációs programtokenek listájában <!-- 1853904 -->
A regisztrációs program tokenlistájában van egy olyan új oszlop, amelyben a hozzárendelt profil nélküli eszközök száma látható. Ez lehetővé teszi, hogy a rendszergazdák profilokat rendeljenek hozzá ezekhez az eszközökhöz, mielőtt a felhasználóknak kiosztanák őket. Az új oszlop megtekintéséhez válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget.

### <a name="device-management"></a>Eszközkezelés

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>A Google névváltoztatásai az Android for Work és a Play for Work kifejezéseknél <!--842873 -->
Az Intune a Google egyes márkaneveit érintő változtatásaihoz igazodva frissítette az „Android for Work” terminológiáját. Az „Android for Work” és a „Play for Work” kifejezések használata megszűnt. A szövegkörnyezettől függően eltérő terminológiát használunk:
- Az „Android Enterprise” az általános, korszerű androidos felügyeleti környezetre vonatkozik.
- A „Munkahelyi profil” vagy a „Profil tulajdonosa” kifejezés a munkahelyi profilokkal felügyelt hozott eszközökre (BYOD) vonatkozik.
- A „Felügyelt Google Play” kifejezés a Google Áruházra vonatkozik.

#### <a name="rules-for-removing-devices----1609459---"></a>Szabályok eszközeltávolításhoz <!-- 1609459 -->
Új szabályok érhetők el, melyekkel automatikusan eltávolíthatja azokat az eszközöket, amelyek nem jelentkeztek be az Ön által megadott számú napon keresztül. Az új szabály megtekintéséhez nyissa meg az **Intune** panelt, és válassza az **Eszközök**, majd az **Eszközök adattörlési szabályai** lehetőséget.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Egyetlen célra használható céges funkció támogatása Android-eszközökhöz <!-- 1630973 -->

Az Intune támogatja a gondosan felügyelt, zárolt, kioszkstílusú Android-eszközöket. Ez lehetővé teszi a rendszergazdák számára, hogy egyetlen alkalmazásra vagy kis alkalmazáskészletre szűkítsék az eszközhasználatot, és megakadályozzák, hogy a felhasználók más alkalmazásokat engedélyezzenek vagy más műveleteket hajtsanak végre az eszközön. Az Android-kioszk beállításához lépjen az Intune > **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** területre. További információért lásd: [Vállalati androidos kioszkeszközök regisztrálásának beállítása](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Feltöltött ismétlődő céges eszközazonosítók soronkénti áttekintése <!-- 2203794-->
A céges azonosítók feltöltésekor az Intune az ismétlődések listázásával most lehetőséget ad a döntésre, hogy cseréli vagy megtartja a meglévő információt. Az ismétlődések esetén készülő jelentés akkor jelenik meg, ha az **Eszközregisztráció** > **Céges eszközazonosítók** > **Azonosítók hozzáadása** lehetőséget választja. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Céges eszközazonosítók manuális hozzáadása <!-- 2203803 -->
Már hozzáadhatja manuálisan a céges eszközök azonosítóit. Válassza az **Eszközregisztráció** > **Céges eszközazonosítók** > **Hozzáadás** lehetőséget. 

## <a name="week-of-june-25-2018"></a>2018. június 25-i hét

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – Új mobileszköz-védelmi partner <!-- 1169249 -->

A Microsoft Intune-nal integrálható, Pradeo nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

## <a name="week-of-june-18-2018"></a>2018. június 18-i hét

### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Microsoft Edge-mobiltámogatás az Intune alkalmazásvédelmi szabályzataihoz <!-- 1817882 -->

A Microsoft Edge mobilböngésző mostantól támogatja az Intune-ban meghatározott alkalmazásvédelmi szabályzatokat.

## <a name="week-of-june-11-2018"></a>2018. június 11-i hét

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>A FIPS-mód használata az NDES tanúsítvány-összekötővel <!-- 1333688 -->
Ha az NDES tanúsítvány-összekötőt olyan számítógépre telepítették, amelyen a Federal Information Processing Standard (FIPS) üzemmód engedélyezve volt, a tanúsítványok kiadása és visszavonása nem az elvárható módon működött. Ettől a frissítéstől kezdve az NDES tanúsítvány-összekötőhöz FIPS-támogatás is tartozik. 

A frissítés a következőket is tartalmazza:

- Az NDES tanúsítvány-összekötő megköveteli a .NET-keretrendszer 4.5-ös verzióját, amely automatikusan része a Windows Server 2016 és Windows Server 2012 R2 rendszereknek. Korábban a .NET 3.5 keretrendszer volt a minimálisan elvárt verzió.
- Az NDES tanúsítvány-összekötő tartalmazza a TLS 1.2 támogatását. Ha tehát a kiszolgáló, amelyen az NDES tanúsítvány-összekötő telepítve van, támogatja a TLS 1.2-t, akkor a TLS 1.2 lesz használva. Amennyiben a kiszolgáló nem támogatja a TLS 1.2 verziót, a TLS 1.1 lesz használva. Az eszközök és a kiszolgáló közötti hitelesítéshez jelenleg a TLS 1.1 van használatban.

További információ: [SCEP-tanúsítványok konfigurálása és használata](certificates-scep-configure.md) és [PKCS-tanúsítványok konfigurálása és használata](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>2018. június 4-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Az alkalmazás alkalmazásfelhasználói modellben használt azonosítójának (AUMID) lekérése a Microsoft Store Vállalatoknak alkalmazásaihoz kioszkmódban <!-- 1560077 ! -->
Az Intune mostantól lekérheti az alkalmazás alkalmazásfelhasználói modellben használt azonosítóját (AUMID) a Microsoft Store Vállalatoknak alkalmazásaihoz, így hatékonyabb kioszkprofil-konfigurációt nyújt.

További információ a Microsoft Store Vállalatoknak alkalmazásairól: [A Microsoft Store Vállalatoknak áruházban vásárolt alkalmazások felügyelete](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Új védjegyzési lap a Céges portálon <!-- 1916370 -->
A Céges portál védjegyzési lapja új elrendezést, szövegtartalmat és elemleírásokat kapott.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Palo Alto Networks GlobalProtect VPN-profilok támogatása <!-- 1333680 ! -->
Ez a frissítés lehetővé teszi a Palo Alto Networks GlobalProtect szolgáltatás választását a VPN-kapcsolat típusaként az Intune-beli VPN-profilokban (**Eszközök konfigurálása** > **Profilok** > **Profil létrehozása** > **Profil típusa** > **VPN**). Ebben a kiadásban az alábbi platformok támogatottak: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>További helyi eszközbiztonsági beállítások <!-- 1403702 -->
További helyi eszközbiztonsági beállításokat adhat meg a Windows 10 rendszerű eszközökhöz. Ezek a további beállítások a következő területeken érhetők el: Microsoft hálózati ügyfél, Microsoft hálózati kiszolgáló, hálózati hozzáférés és biztonság, valamint interaktív bejelentkezés. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioszkmód engedélyezése Windows 10-eszközökön <!-- 1560072 ! -->
Windows 10-eszközökön létrehozhat egy konfigurációs profilt, és engedélyezheti a kioszkmódot (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10** > **Eszközkorlátozások** > **Kioszkmód**). Ebben a frissítésben a **Kioszk (előnézet)** beállítást **Kioszk (elavult)** névre neveztük át. A **Kioszk (elavult)** beállítás használata már nem javasolt, de a júliusi frissítésig még működik. A **Kioszk (elavult)** beállítást az új **Kioszkmód** profiltípus helyettesíti (**Profil létrehozása** > **Windows 10** > **Kioszk (előnézet)**), amely a kioszkok Windows 10 RS4-es és újabb verziós konfigurációjához tartalmaz beállításokat.

A Windows 10 és újabb verziókra vonatkozik.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Visszatért az eszközprofil grafikus felhasználói diagramja <!-- 2160133 -->
Az eszközprofil grafikus felhasználói diagramján megjelenített számok javításakor (**Eszközkonfiguráció** > **Profilok** > Válasszon ki egy meglévő profilt > **Áttekintés**) ideiglenesen eltávolítottuk a grafikus felhasználói diagramot.

Ezzel a frissítéssel visszatér a grafikus felhasználói diagram, amely az Azure Portalon jelenik meg.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Windows Autopilot-alapú beléptetés támogatása felhasználóhitelesítés nélkül <!-- 1165118 -->
Az Intune mostantól támogatja a Windows Autopilot-alapú beléptetést felhasználóhitelesítés nélkül. Ez egy új funkcionalitás, melyet a Windows Autopilot beléptetési profilban érhet el úgy, hogy az „Autopilot Deployment mode” (Autopilot telepítési módja) beállítást „Self-Deploying” (Öntelepítés) értékre állítja.  Az ilyen típusú regisztráció sikeres elvégzéséhez az eszközön a Windows 10 Insider Preview Build 17672 vagy újabb verziónak kell futnia, és rendelkeznie kell egy TPM 2.0 lapkával. Mivel nem igényel felhasználóhitelesítést, ennek a lehetőségnek a használata csak olyan eszközökhöz javasolt, amelyekhez fizikailag is hozzáfér.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Új nyelv/terület beállítás automata OOBE konfigurálásakor <!-- 1821766 -->
A kezdőélmény automata profiljaiban egy új konfigurációs beállítás érhető el, amellyel megadható a profilok nyelve és régiója. Az új beállítás eléréséhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** > **Telepítési mód** = **Öntelepítés** > **Konfigurált alapértelmezések** lehetőséget.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Új beállítás az eszköz billentyűzetének konfigurálásához <!-- 1821768 -->
A kezdőélmény automata profiljaiban egy új beállítás lesz elérhető, amellyel konfigurálható a billentyűzet. Az új beállítás eléréséhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** > **Telepítési mód** = **Öntelepítés** > **Konfigurált alapértelmezések** lehetőséget.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Az Autopilot-profilok csoportokat fognak megcélozni <!-- 1877935 -->
Az AutoPilot Deployment-profilok AutoPilot-eszközöket tartalmazó Azure AD-csoportokhoz rendelhetők hozzá.

### <a name="device-management"></a>Eszközkezelés

#### <a name="set-compliance-by-device-location----851881----"></a>Megfelelőség beállítása az eszköz helye alapján <!-- 851881 ! -->
Bizonyos esetekben érdemes a vállalati erőforrásokhoz való hozzáférést egy adott helyre korlátozni, amelyet hálózati kapcsolattal ad meg. Hozhat létre mostantól megfelelőségi szabályzatot (**Eszközmegfelelőség** > **Helyek**) az eszköz IP-címe alapján. Ha az eszköz az IP-címtartományon kívülre kerül, akkor nem férhet hozzá a vállalati erőforrásokhoz.

A következőkre vonatkozik: Android 6.0-s és újabb eszközök frissített Céges portál alkalmazással

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Fogyasztói alkalmazások és funkciók használatának meggátolása a Windows 10 Enterprise RS4 rendszerű Autopilot-eszközökön<!-- 1621980 -->
Le fogja tudni tiltani a fogyasztói alkalmazások és funkciók telepítését a Windows 10 Enterprise RS4 rendszerű AutoPilot-eszközökön. A szolgáltatás eléréséhez válassza az **Intune** > **Eszközök konfigurálása** > **Profilok** > **Profil létrehozása** > **Platform** = **Windows 10 vagy újabb** > **Profiltípus** = **Eszközkorlátozások** > **Konfigurálás** > **Windows Reflektorfény** > **Fogyasztói funkciók** lehetőséget. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>A Windows 10 legújabb szoftverfrissítéseinek eltávolítása <!-- 1732948 -->
Ha kritikus problémát tapasztal a Windows 10 rendszerű gépein, akkor választhatja az utolsó funkciófrissítés vagy az utolsó minőségi frissítés eltávolítását (vagyis a korábbi verzió visszaállítását). A funkciófrissítések és minőségi frissítések eltávolításának lehetősége csak ahhoz a karbantartási csatornához érhető el, amelyhez az eszköz tartozik. Az eltávolítás aktivál egy szabályzatot, mely visszaállítja az előző frissítést a Windows 10 rendszerű gépein. A funkciófrissítések esetében korlátozhatja 2–60 napra a legújabb verzió eltávolításának lehetőségét. A szoftverfrissítés-eltávolítási beállítások megadásához válassza a **Szoftverfrissítések** lehetőséget az Azure Portal **Microsoft Intune** paneljén. Ezután a **Szoftverfrissítések** panelen válassza a **Windows 10-es frissítési körök** lehetőséget. Itt végül választhatja az **Áttekintés** szakaszban lévő **Eltávolítás** lehetőséget.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>IMEI- és sorozatszám keresése minden eszközön <!-- 1793685 -->
Mostantól kereshet IMEI- és sorozatszámokra a Minden eszköz panelen (az e-mail-cím, UPN, eszköznév és felügyeleti név lehetősége továbbra is elérhető). Válassza az Intune-ban az **Eszközök** > **Minden eszköz** lehetőséget, és írja be a kívánt keresési feltételt a keresőmezőbe.

#### <a name="management-name-field-will-be-editable----1875989---"></a>A Felügyeleti név mező szerkeszthető lesz <!-- 1875989 -->
Szerkesztheti a Felügyeleti név mezőt az eszköz **Tulajdonságok** panelén. A mező szerkesztéséhez válassza az **Eszközök** > **Minden eszköz** > Válassza ki az eszközt > **Tulajdonságok** lehetőségét. A Felügyeleti név mezővel egyéni módon azonosíthat egy eszközt.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Új összes eszközök szűrő: Eszközkategória <!-- 1878520 -->
Mostantól szűrheti a **Minden eszköz** listát eszközkategória szerint. Ehhez válassza az **Eszközök** > **Minden eszköz** > **Szűrő** > **Eszközkategória** lehetőséget.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS- és macOS-eszközök képernyőjének megosztása a TeamViewerrel <!-- 1985547 -->
A rendszergazdák ezentúl a [TeamViewerhez](device-profile-android-teamviewer.md) csatlakozva képernyőmegosztást kezdeményezhetnek iOS- és macOS-eszközökkel. Az iPhone-, iPad- és macOS-felhasználók valós időben megoszthatják a képernyőjüket bármilyen más asztali vagy mobileszközzel. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Több Exchange Connector támogatása <!-- 2070451 -->
Mostantól nemcsak egy Microsoft Intune Exchange Connectort használhat bérlőnként. Az Intune most már több Exchange Connector használatát is támogatja, hogy több helyszíni Exchange-szervezetnél állíthassa be az Intune feltételes hozzáférést.

A helyszíni Intune Exchange Connector segítségével annak alapján kezelheti az eszközök helyszíni Exchange-postafiókokhoz történő hozzáférését, hogy az adott eszköz regisztrálva van-e az Intune-ban, és megfelel-e az Intune eszközmegfelelőségi szabályzatainak. Az összekötő beállításához töltse le a helyszíni Intune Exchange Connectort az Azure Portalról, és telepítse egy Exchange-szervezeten belüli kiszolgálón. A Microsoft Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget, majd a **Telepítés** területen kattintson az **Exchange ActiveSync Connector** lehetőségre. Töltse le a helyszíni Exchange Connectort, és telepítse egy Exchange-szervezeten belüli kiszolgálón. Most, hogy már nem csupán egy Exchange Connectort használhat bérlőnként, ugyanezekkel a lépésekkel letöltheti és telepítheti az összekötőt minden további Exchange-szervezethez, ha vannak ilyenek.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Új eszköz hardveres részletei: CCID <!-- 2156657 -->
A Chip Card Interface Device (CCID) azonosító mostantól elérhető minden eszközhöz. A megtekintéséhez válassza az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Hardver** lehetőséget, és ellenőrizze a **Hálózati adatok** szakaszt.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Minden felhasználó és eszköz hozzárendelése hatókörcsoportokként <!-- 2196803 -->
Minden felhasználót, eszközt és a hatókörcsoportok felhasználóit és eszközeit hozzárendelheti. Ehhez válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** > kívánt hozzárendelés > **Hatókör (csoportok)** lehetőséget.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Mostantól elérhető az UDID azonosító iOS- és macOS-eszközökhöz <!-- 2219806 -->
Az iOS- és macOS-eszközök UDID (Unique Device Identifier) azonosítójának megtekintéséhez válassza az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Hardver** lehetőséget. Az UDID csak vállalati eszközökhöz érhető el (ezt az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Tulajdonságok** > **Eszköz tulajdonjoga** lehetőséget választva állíthatja be).

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Továbbfejlesztett hibaelhárítás az alkalmazástelepítéshez <!-- 928990 -->
A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. Bevezetjük az alkalmazás-hibaelhárítási funkcióink nyilvános előzetes verzióját. Ennek keretében megjelenik egy új, **Kezelt alkalmazások** nevű csomópont minden egyedülálló eszköz alatt. Ez a Intune MDM-en keresztül szolgáltatott alkalmazások listáját tartalmazza. A csomóponton belül az alkalmazástelepítési állapotokat tekintheti meg. Ha kijelöl egy önálló alkalmazást, megnyithatja annak hibaelhárítási nézetét. A hibaelhárítási nézetben megtekintheti az alkalmazás végpontok közötti életciklusát, például a létrehozási, a módosítási, a célzási dátumot, valamint az alkalmazás egy eszközre való továbbításának dátumát. Továbbá ha az alkalmazás telepítése sikertelen volt, megjelenik egy hibakód, és egy hasznos üzenet a hiba okáról. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Intune-beli alkalmazásvédelmi szabályzatok és Microsoft Edge <!-- 1818968 -->
A Microsoft Edge mobilböngésző (iOS és Android) mostantól támogatja a Microsoft Intune alkalmazásvédelmi szabályzatait. Az Intune azokat a felhasználókat is védeni fogja, akik iOS- és Android-eszközön jelentkeznek be Azure AD-fiókjukkal az Edge alkalmazásba. iOS-eszközökön a **Require managed browser for web content** (Felügyelt böngésző megkövetelése a webes tartalmakhoz) szabályzat engedélyezi a felhasználóknak a hivatkozások felügyelt Microsoft Edge-ben való megnyitását.

## <a name="week-of-may-14-2018"></a>2018. május 14-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítésének megkövetelése <!-- 1553555 -->

A rendszergazdák blokkolhatják a végfelhasználók számára a Windows 10 RS4 rendszer asztalának elérését, amíg az Intune el nem végzi a szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítését az AutoPilot-eszközök beállításakor. További információért lásd: [Regisztrációs állapotlap beállítása](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Alkalmazásvédelmi szabályzatok konfigurálása <!-- 2144597 Part 2 -->

Az Azure Portalon, ahelyett hogy az Intune App Protection szolgáltatáspanelre lépne, mostantól elegendő egyszerűen az Intune-t megnyitnia. Most már az Intune egyetlen helyén érhetők csak el az alkalmazásvédelmi szabályzatok. Az összes alkalmazásvédelmi szabályzatát megtalálhatja az Intune **Mobilalkalmazás** paneljén, az **Alkalmazásvédelmi szabályzatok** területen. Ez az integráció leegyszerűsíti a felhőbeli szolgáltatások adminisztrációját. Ne feledje, hogy minden alkalmazásvédelmi szabályzat elérhető már az Intune-ban, és a korábban konfigurált összes szabályzatot módosíthatja. Az Intune App Policy Protection- (APP) és Conditional Access- (CA) szabályzatok mostantól a **Feltételes hozzáférés** területen érhetők el, mely a **Microsoft Intune** panel **Kezelés** szakaszában vagy az **Azure Active Directory** panel **Biztonság** szakaszában található meg. További információ a feltételes hozzáférési szabályzatokról: [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). További információ: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>2018. május 7-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Samsung Knox Mobile Enrollment-támogatás <!--1112863-->

A Intune a Samsung Knox Mobile Enrollmenttel (KME-vel) való használatával nagy mennyiségű céges tulajdonú Android-eszközt regisztrálhat. A Wi-Fi- és mobilhálózatok felhasználói az eszköz első bekapcsolása után csupán néhány érintéssel regisztrálhatnak. A Knox Deployment App használatával az eszközök Bluetooth vagy NFC segítségével regisztrálhatók. További információ: [Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Segítségkérés a Windows 10-es Céges portálban <!-- 1874137 -->

A Windows 10 Céges portál mostantól alkalmazáshasználati naplókat küld közvetlenül a Microsoftnak, ha egy felhasználó segítséget kér egy problémához. Így könnyebben háríthatók el és oldhatók meg a Microsoftnak továbbított problémák.

## <a name="week-of-april-23-2018"></a>2018. április 23-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>PIN-jelszó támogatása MAM PIN-ként Androidon<!-- 1438086 -->

Az Intune-rendszergazdák alkalmazásindítási követelményként állíthatnak be PIN-jelszót a numerikus MAM PIN-kód helyett. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune a PIN-jelszót a hagyományos, numerikus PIN-kódhoz hasonlóan támogatja: állíthat be minimális jelszóhosszt, és engedélyezheti a karakterek és sorozatok ismétlődését a felügyeleti konzolon. Ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség Android rendszerben. Ez a funkció már elérhető az iOS rendszerben.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1473977 -->
A Microsoft Intune támogatni fogja a macOS-hoz készült LOB-alkalmazások telepítését az Azure Portalról. Ezzel a funkcióval hozzáadhat egy macOS-hoz készült LOB-alkalmazást az Intune-hoz, miután azt előkészítette egy, a GitHubon elérhető eszközzel. Válassza az Azure Portalon az **Intune** panel **Ügyfélalkalmazások** elemét. Az **Ügyfélalkalmazások** panelen válassza az **Alkalmazások** > **Hozzáadás** lehetőséget. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Beépített „Minden felhasználó” és „Minden eszköz” csoport az Android Enterprise munkahelyiprofil-alkalmazásainak hozzárendelése esetén <!-- 1813073 -->
Ön használhatja a beépített **Minden felhasználó** és **Minden eszköz** csoportokat az Android Enterprise munkahelyiprofil-alkalmazásainak hozzárendelése esetében. További információ: [Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Az Intune újratelepíti a felhasználók által eltávolított kötelező alkalmazásokat <!-- 1947010 -->
Ha egy végfelhasználó eltávolít egy kötelező alkalmazást, az Intune a 7 napos újraértékelési ciklus kivárása helyett 24 órán belül automatikusan újratelepíti az alkalmazást.

### <a name="device-configuration"></a>Eszközök konfigurálása

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Csoport minden eszközének megjelenítése az eszközprofil-diagramon és -állapotlistán <!-- 1449153 -->
Eszközprofil konfigurálásakor (**Eszközök konfigurálása** > **Profilok**) kiválasztja az eszközprofilt, például iOS. Ezután hozzárendeli ezt a profilt egy csoporthoz, mely tartalmaz iOS- és nem iOS-eszközöket is. A grafikus diagramon lévő számlálón az látható, hogy a profil alkalmazva lett az iOS- *és* a nem iOS-eszközökre is (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**). Amikor a grafikus diagramot választva megjeleníti az **Áttekintés** lapot, az **Eszközállapot** terület felsorolja a csoport összes eszközét, nemcsak az iOS-eszközöket. 

A jelen frissítés megjelenése után a grafikus diagram (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**) csak az adott eszközprofil számlálóját jeleníti meg. Ha például az eszközprofil iOS-eszközökre van alkalmazva, akkor a diagram csak az iOS-eszközök számát jeleníti meg. A grafikus diagram választása és az **Eszközállapot** lista megnyitása esetén is csak az iOS-eszközök lesznek felsorolva.

A jelen frissítés elkészültéig a grafikus felhasználói diagramot ideiglenesen eltávolítottuk. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Mindig bekapcsolva VPN Windows 10-hez <!--1333666 -->

Jelenleg a [Minden bekapcsolva](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) trigger a Windows 10-eszközökön csak OMA-URI-val létrehozott egyéni VPN-profil segítségével használható.

A frissítés révén a rendszergazdák engedélyezhetik a Mindig bekapcsolva beállítást a Windows 10 VPN-profilokban közvetlenül az Azure Portalon elérhető Intune konzolról. A Mindig bekapcsolva beállítású VPN-profilok automatikusan csatlakoznak az alábbi esetekben:

- Felhasználói bejelentkezés az eszközre
- Hálózatváltozás az eszközön
- Az eszköz képernyője ismét bekapcsol, miután ki volt kapcsolva

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Új nyomtatóbeállítások az oktatási profilokban <!-- 1308900 -->

Az oktatási profilok új beállítás érhető el a **nyomtatók** kategória: **Nyomtatók**, **alapértelmezett nyomtató**, **új nyomtatók hozzáadása**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>A hívásazonosító megjelenítése a személyes profilban – Android Enterprise-munkaprofil <!--1098984 -->
Előfordulhat, hogy az eszközön személyes profilt használó végfelhasználók nem látják egy munkahelyi kapcsolat hívásazonosítójának részleteit. 

Ezzel a frissítéssel új beállítás válik elérhetővé az **Android Enterprise** > **Eszközkorlátozások** > **Munkaprofil-beállítások** menüpontban:
- Munkahelyi kapcsolat hívásazonosítójának megjelenítése a személyes profilban

Engedélyezése (konfigurálás nélkül) esetén a munkahelyi hívó részletei megjelennek a személyes profilban. Tiltása esetén a munkahelyi hívó részletei nem jelennek meg a személyes profilban. 

A következőkre vonatkozik: Android munkahelyi profilos eszközök Android operációs rendszer v6.0 és újabb

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Új Windows Defender Credential Guard-beállítások az Endpoint Protection-beállításokban <!--1102252 --><!--from 1802 and 1804-->

Ezzel a frissítéssel a [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Eszközkonfiguráció** > **Profilok** > **Endpoint protection**) az alábbi beállításokkal bővült: 

- **Windows Defender Credential Guard**: Kapcsolja be a Credential Guard a virtualizálás-alapú biztonság. Ennek a funkciónak a bekapcsolása segít megvédeni a hitelesítő adatokat a következő újraindításkor, ha a **Platformbiztonsági szint a Biztonságos rendszerindítással** és a **Virtualizálás-alapú biztonság** egyaránt be van kapcsolva. A lehetőségek a következők:
  - **Letiltott**: Ha a Credential Guard korábban bekapcsolta az a **engedélyezve zárolás nélkül**"lehetőséget, majd azt kikapcsolja a Credential Guard távolról.

  - **Engedélyezve UEFI-zárolással**: Biztosítja, hogy a Credential Guard nem lehet letiltani, egy beállításkulcs megadásával vagy a csoportházirend használatával. Ha ennek a beállításnak a használata után le szeretné tiltani a Credential Guardot, akkor a Csoportházirendet „Letiltva” állapotra kell állítania. Ezt követően távolítsa el a biztonsági funkciót mindegyik számítógépen egy fizikailag jelen lévő felhasználóval. Ezekkel a lépésekkel törölhető az UEFI-ban megőrzött konfiguráció. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

  - **Engedélyezve zárolás nélkül**: Lehetővé teszi a Credential Guard csoportházirenddel távoli letiltását. Azokon az eszközökön, amelyek ezt a beállítást használják, legalább a Windows 10 1511-es verziójának kell futnia.

Az alábbi függő technológiák automatikusan engedélyezve lesznek a Credential Guard konfigurálásakor: 

  - **A virtualizálás-alapú biztonság (VBS) engedélyezése**: Kapcsolja be a virtualizálás-alapú biztonság (VBS a következő rendszerindításkor). A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz, és Biztonságos rendszerindítás szükséges hozzá.
  - **A biztonságos rendszerindítás közvetlen memória-hozzáféréssel (DMA)**: A biztonságos rendszerindítással és közvetlen memória-hozzáférés VBS bekapcsolása. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Egyéni tulajdonosnév használata SCEP-tanúsítványokban <!-- 2064190 -->
Használhatja az **OnPremisesSamAccountName** köznapi nevet egyéni tulajdonosként az SCEP-tanúsítványprofilokban. Így használhatja például a következőt: `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Kamera- és képernyőfelvételek letiltása az Android Enterprise munkahelyi profiljaiban <!-- 1098977 -->
Két új tulajdonság érhető el letiltásra, amikor az Android-eszközökhöz eszközkorlátozásokat állít be: 
- Kamera: Az eszköz összes kamerájának blokkolja a hozzáférést
- Képernyőfelvétel: Letiltja a képernyőfelvételt, és megakadályozza, hogy a tartalom nem jelenik meg egy biztonságos videokimenettel nem rendelkező megjelenítő eszközökön

Hatókör: Az Android Enterprise munkahelyi profiljai.


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Új regisztrációs lépések a macOS High Sierra 10.13.2 és újabb rendszert futtató eszközök felhasználóinak <!--1734567 -->
A macOS High Sierra 10.13.2 rendszer bevezette a „felhasználó által jóváhagyott” mobileszköz-kezelési regisztrációt. A jóváhagyott regisztrációk lehetővé teszik az Intune-nak bizonyos biztonsági szempontból kényes beállítások kezelését. További információt az Apple támogatási dokumentumában találhat itt: https://support.apple.com/HT208019.

A macOS rendszerhez készült Céges portál alkalmazással regisztrált eszközök „felhasználó által nem jóváhagyott” állapotúként vannak minősítve, hacsak a felhasználó manuálisan jóváhagyást nem ad a Rendszerbeállítások menü megnyitásával. Emiatt a macOS rendszerhez készült Céges portál alkalmazás mostantól a regisztrációs folyamat végén átirányítja a macOS 10.13.2 és újabb rendszerek felhasználóit a regisztrációjuk manuális jóváhagyásához. Az Intune felügyeleti konzolja jelenti, ha egy regisztrált eszközt jóváhagyott a felhasználó.



### <a name="device-management"></a>Eszközkezelés

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>A veszélyforrások elleni fejlett védelem (ATP) és az Intune teljesen integrálva van <!-- 1629303 -->

A [Komplex veszélyforrások elleni védelem](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) megállapítja a Windows 10 rendszerű eszközök kockázati szintjét. A Windows Defender biztonsági központban (ATP portál) kapcsolatot hozhat létre a Microsoft Intune-nal. Ennek létrehozása után egy Intune-megfelelőségi szabályzat alapján meg lesz határozva az elfogadható fenyegetettségi szint. Így a fenyegetettségi szint túllépése esetén egy Azure Active Directory-beli megfelelőségi szabályzat a vállalaton belül letilthatja néhány alkalmazás elérését.

Ez a funkció teszi lehetővé az ATP számára a fájlok vizsgálatát, a fenyegetések észlelését, és a Windows 10 rendszerű eszközöket érintő kockázatok jelentését.

Lásd: [Az ATP engedélyezése feltételes hozzáféréssel az Intune-ban](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Felhasználó nélküli eszközök támogatása <!-- 1637553 -->
Az Intune támogatja a megfelelőség kiértékelését a felhasználó nélküli eszközökön is, ideértve például a Microsoft Surface Hub eszközt. A megfelelőségi szabályzat alkalmazható közvetlenül eszközökre. Ezért a megfelelőség (vagy meg nem felelőség) megállapítható a társított felhasználó nélküli eszközök esetében is.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-eszközök törlése <!-- 1713650 -->
Az Intune-rendszergazdák [törölhetik az Autopilot-eszközöket](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Továbbfejlesztett eszköztörlési funkció <!--1832333 -->
Mostantól nem kell eltávolítania a céges adatokat vagy visszaállítania a gyári beállításokat, mielőtt [törölhetne egy eszközt az Intune-ból](devices-wipe.md#delete-devices-from-the-intune-portal).

Az új törlési funkció eléréséhez jelentkezzen be az Intune-ba, és válassza az **Eszközök** > **Minden eszköz** > eszköz neve > **Törlés** lehetőséget.

Ha továbbra is szeretné alaphelyzetbe állítani vagy kivonni az eszközöket, használhatja a megszokott **Céges adatok eltávolítása** és **Gyári beállítások visszaállítása** lehetőséget, mielőtt a **Törlés** lehetőséget választaná. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Hang lejátszása iOS rendszeren Elveszett üzemmódban <!-- 1947769 -->
Amikor egy felügyelt iOS-eszköz a mobileszköz-kezelés (MDM) [Elveszett üzemmódjában](device-lost-mode.md) van, [lejátszhat egy hangot](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Eszközök** > **Minden eszköz** > válasszon iOS-eszközt > **Áttekintés** > **Egyebek**). A hang lejátszása egészen addig folytatódik, amíg az eszköz ki nem lép az Elveszett üzemmódból, vagy a felhasználó le nem tiltja a hangot az eszközön. iOS 9.3-as és újabb rendszerű eszközökre érvényes.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Keresések webes találatainak letiltása vagy engedélyezése Intune-eszközön <!--1972804-->

A rendszergazdák mostantól letilthatják az eszközön a keresések webes eredményeit.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Javított hibaüzenet az Apple MDM Push-tanúsítvány feltöltési hibájához <!-- 2172331 -->

A hibaüzenet elmagyarázza, hogy ugyanazt az Apple ID-t kell használni egy meglévő MDM-tanúsítvány megújításakor.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>A macOS-hez készült Céges portál tesztelése virtuális gépeken <!-- 2216679 -->

Közzétettünk egy útmutatót IT-rendszergazdák számára, amelyben segítséget kapnak ahhoz, hogy a macOS-hez készült Céges portál alkalmazást teszteljék virtuális gépeken a Parallels Desktopban és a VMware Fusionben. További információt a [Virtuális macOS-gépek regisztrálása teszteléshez](macos-enroll.md#enroll-virtual-macos-machines-for-testing) című témakörben talál.


### <a name="user-interface"></a>Felhasználói felület

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Továbbfejlesztett eszközcsempék a Windows 10-es Céges portálban <!--2213364 -->

Frissítettük a csempéket, így most már jobban hozzáférhetőek a gyengén látó felhasználók számára is, és jobb teljesítményt nyújtanak a képernyőolvasó eszközök használatakor.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnosztikai jelentések küldése a macOS rendszerhez készült Céges portál alkalmazásban <!-- 2216677 -->
Frissült a macOS-eszközökhöz készült Céges portál alkalmazás, így jobb lehetőségeket nyújt a felhasználóknak az Intune-nal kapcsolatos hibák jelentésére. A dolgozói a Céges portál alkalmazásból a következőket tehetik meg:

- Diagnosztikai jelentések feltöltése közvetlenül a Microsoft fejlesztői csapatának.
- Incidensazonosító elküldése e-mailben a vállalata informatikai támogatási csoportjának.

További információt a [Néhány hiba macOS esetén](/intune-user-help/send-errors-macos) című témakörben talál.

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Az Intune támogatja a Fluent Design System használatát a Windows 10-hez készült Céges portál alkalmazásban <!-- 1195010 -->
A Windows 10-es Intune Céges portál alkalmazást frissítettük a [Fluent Design System navigációs nézetével](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Az alkalmazás oldalán egy statikus, függőleges lista jelenik meg a legfelső szintű oldalakkal. A gyors megtekintéshez és az oldalak közötti váltáshoz kattintson bármelyik hivatkozásra. Egy frissítéssorozattal adaptív, kényelmesebb és ismerősebb Intune-élményt szeretnénk létrehozni. Ez a sorozat első frissítése. A frissített megjelenés megtekintésez lépjen [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) területre.

## <a name="week-of-april-16-2018"></a>2018. április 16-i hét

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Cisco AnyConnect ügyfél használata iOS-hez <!-- 1333708 -->

Amikor létrehoz egy új VPN-profil iOS-hez, most már két lehetőség van: **Cisco AnyConnect** és **Cisco Legacy AnyConnect**. A Cisco AnyConnect-profilok a 4.0.7x és újabb verziókat támogatják. Meglévő iOS Cisco AnyConnect VPN-profiljai a **Cisco Legacy AnyConnect** nevet kapják, és továbbra is úgy működnek a Cisco AnyConnect 4.0.5x és régebbi verzióival, mint eddig.

> [!NOTE]
> Ez a módosítás csak az iOS-re vonatkozik. Az Android és az Android Enterprise munkahelyi profiljaiban, valamint a macOS rendszerű platformokon továbbra is csak egyetlen Cisco AnyConnect lehetőség áll rendelkezésre.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>A Jamf-ban regisztrált macOS-eszközök már regisztrálhatnak az Intune-nal <!-- 2370684 -->

A macOS-es Céges portál 1.3 és 1.4 verziója nem regisztrálta sikeresen a Jamf-eszközöket az Intune-nal. A macOS portál 1.4.2 verziója kijavítja ezt a hibát.


## <a name="week-of-april-9-2018"></a>2018. április 9-i hét  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Frissített ügyféltámogatási élmény az Androidhoz készült Céges portál alkalmazásban <!-- 1631531 -->

Az Android platform ajánlott eljárásaihoz igazodva frissítettük az Androidhoz készült Céges portál alkalmazás Súgó funkcióját. Mostantól ha a felhasználók problémát észlelnek az alkalmazásban, a **Menü** > **Súgó** lehetőségre koppintva az alábbi tevékenységeket végezhetik:
- Diagnosztikai naplókat küldhetnek a Microsoftnak.
- Egy eseményazonosítót és a hibát ismertető e-mailt írhatnak a céges ügyfélszolgálatnak.  

A frissített ügyféltámogatást a [Naplók elküldése e-mailben](/intune-user-help/send-logs-to-your-it-admin-by-email-android) és a [Hibák elküldése a Microsoftnak](/intune-user-help/send-logs-to-microsoft-android) területen érheti el.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Új regisztrációs hibákat ábrázoló trenddiagram és hibaokokat tartalmazó táblázat <!-- 1471783 -->

A Regisztráció áttekintése lapon megtekintheti a regisztrációs hibák trendjét és az öt leggyakoribb hibaokot. A diagramra vagy a táblázatra kattintva hozzáférhet a részletesebb adatokhoz, valamint hibaelhárítási tanácsokat és szervizelési javaslatokat is találhat.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Az alkalmazásvédelmi szabályzatok konfigurálási helyének frissítése <!-- 2144597 -->

A Microsoft Intune-beli Azure Portalon ideiglenesen átirányítás lesz érvényben az **Intune App Protection** szolgáltatás paneljéről a **Mobilalkalmazás** panelre. Fontos megjegyezni, hogy már minden alkalmazásvédelmi szabályzat megtalálható az Intune **Mobilalkalmazás** paneljén, az alkalmazáskonfigurációban. Az Intune App Protection szolgáltatás megnyitása helyett csak az Intune-t kell majd megnyitnia. 2018. áprilisban megszüntetjük az átirányítást, és teljes mértékben eltávolítjuk az **Intune App Protection** szolgáltatás paneljét, így az Intune alkalmazásvédelmi szabályzatait ezentúl egyetlen helyen tekintheti meg. 

**Hogyan érint ez engem?**
Ez a változás a különálló Intune-t használó ügyfeleket és a hibrid (az Intune-t a Configuration Managerrel használó) ügyfeleket egyaránt érinti. Az integráció leegyszerűsíti a felhőfelügyelet adminisztrációját.

**Hogyan készüljek fel a változásra?**
Az **Intune App Protection** szolgáltatás panelje helyett az **Intune-t** jelölje meg kedvencként, és mindenképpen ismerkedjen meg az alkalmazásvédelmi szabályzatok munkafolyamatával az Intune **Mobilalkalmazás** paneljén. Egy rövid ideig átirányítás lesz érvényben, majd az **App Protection** panel el lesz távolítva. Ne feledje, hogy már minden alkalmazásvédelmi szabályzat elérhető az Intune-ban, és bármely feltételes hozzáférési szabályzatot módosíthatja. További információ a feltételes hozzáférési szabályzatokról: [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). További információ: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>2018. április 2-i hét

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Felhasználóiélmény-frissítés az iOS-hez készült Céges portál alkalmazásban <!--1412866 -->
Nagyszabású felhasználóiélmény-frissítést adtunk ki az iOS-es Céges portál alkalmazáshoz. A frissítéshez teljes vizuális átalakulás is tartozik, amely modernebb megjelenést és élményt biztosít. Az alkalmazás működését változatlanul hagytuk, használhatóságát és kezelhetőségét azonban fejlesztettük.  

Amit még tapasztalni fog:
- IPhone X támogatása.
- Gyorsabb alkalmazásindítás és betöltés, amellyel a felhasználók időt takarítanak meg.
- A felhasználóknak a legfrissebb állapotinformációkat nyújtó újabb folyamatjelző sávok.
- A felhasználói naplófeltöltés módjának fejlesztése, hogy a hibákat egyszerűbb legyen bejelenteni.  

A frissített megjelenés megtekintésez lépjen [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) területre.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Helyszíni Exchange-adatok védelme az Intune APP és a feltételes hozzáférés segítségével <!-- 1056954 -->
Mostantól a helyszíni Exchange-adatokhoz való Outlook Mobile-hozzáférést az Intune App Policy Protection (APP) és a feltételes hozzáférés segítségével védheti. Alkalmazásvédelmi szabályzat hozzáadásához vagy módosításához az Azure Portalon válassza a **Microsoft Intune** > **Ügyfélalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget. A funkció használata előtt győződjön meg arról, hogy megfelel az [iOS-es és Androidos Outlook követelményeinek](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="notices"></a>Értesítések

### <a name="upcoming-password-enforcement-change-for-macos-10142-in-intune---1873216--"></a>Közelgő jelszó kényszerítése módosítása az Intune-ban 10.14.2 macOS-hez <!--1873216-->
A Microsoft megosztott MC145129 július az, hogy az Intune-csomagok újonnan integrálható az Apple megjelent-e a macOS 10.13 verzióit futtató eszközökön és a fenti "Módosítsa jelszavát, tovább Auth" beállítás. Jelenleg tervezzük szeretné visszaállítani ezt a beállítást meg februárban macOS 10.14.2-es és újabb. 

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ez hatással van, hogy ha van, vagy tervezi, hogy macOS 10.14.2 rendszerű eszközökhöz, és nagyobb. Most, hogy az Apple vezetett be a "Change jelszó: új hitelesítési" beállítást, az Intune kényszerítheti a felhasználókat, hogy akkor megfelelő, ha a jelszóházirend leküldéssel jelszófrissítési. A macOS-felhasználók kap egy kérelmet jelszófrissítési integrálni fogjuk az új Apple-funkció, ha akkor is, ha már megfelel a jelszavát. Vegye figyelembe, hogy ha jelszó már megfelel, és nem kell jelszavak ismételt szemben követelmény, akkor a végfelhasználók lesz képes frissíteni a meglévő jelszavát. A végfelhasználók csak jelenik meg frissíteni a jelszavát, ha megpróbálnak hitelesíteni, vagy jelentkezzen be az eszközt egy kérelmet. Ha letiltja a vállalati erőforrásokhoz, mindaddig, amíg az eszköz megfelelő van megjelölve, majd, hogy, hogy a végfelhasználók számára az eszközökön a macOS 10.14.2 blokkolva van a jelszavuk, például az e-mailben vagy a SharePoint-webhelyek a vállalati erőforrásokhoz való hozzáférését. A jövőben a konfigurációs és megfelelőségi jelszóházirendek minden frissítés kényszeríti a megcélzott felhasználók frissíthetik a jelszavukat. Ez a módosítás előtt az ügyfél kutatási jelzett ügyfelek többsége nem érinti ez a módosítás a végfelhasználók általában frissítése a jelszavát a jelszó regisztrálása vagy a megfelelőség biztosítása jelszavuk kérelem fogadása után óta

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Szüksége lehet ahhoz, hogy a segélyszolgálat ismeri. A Mi az új lap, ha ez a változás bevezetési frissítjük. Ha nem szeretné, hogy a MacOS rendszerű eszköz jelszóházirend kényszerítését, javasoljuk, Ön megszüntetése vagy a meglévő macOS-szabályzat törlése.

###<a name="plan-for-change-update-to-ios-setting-for-supervised-devices-in-the-intune-console"></a>Tervezett módosítás: IOS-beállítást a felügyelt eszközökön az Intune-konzolon való frissítéséhez  
A február frissítéssel az Intune szolgáltatásba a felügyelt iOS-eszközökön "Az Eszközbeállítások korlátozások engedélyezése" beállítást "(csak felügyelt) képernyő idő" alatt álló új. A módosítás után végfelhasználói élmény iOS-verzió alapján változik.

####<a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Miután a "Korlátozások engedélyezése az Eszközbeállítások között (csak felügyelt)" beállítását pedig átnevezi "Képernyő idő (csak felügyelt)", az alábbiakban a élményt a felügyelt eszközök (regisztrálva az Apple regisztrációs programjai): 

Eszközök iOS 11.4-és előtt: Ez a beállítás megakadályozza, hogy a felhasználók módosítása eszközkorlátozások, mielőtt használható. A végfelhasználók nem látják változik a felhasználói élményt.
 
12 vagy újabb IOS-eszközökhöz: Végfelhasználók számára már nem jelennek meg a korlátozásokat lapon, a beállítások > Általános > Eszközfelügyelet > felügyeleti profil > korlátozások.
Ehelyett a beállítások egy része lesz > Általános > képernyő idő. A "Letiltás" beállítás konfigurálása letiltja a felhasználók nem módosíthatják a képernyő beállításai az eszközeiken, amely tartalmat és adatvédelmi korlátozások is tartalmazza.

####<a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
A végfelhasználói útmutató megjegyezni a változik a élmény IOS 12-es vagy újabb rendszerre frissített eszközök frissítéséhez.


###<a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Tervezett módosítás: A munkafolyamat-módosítások az IOS-eszközök 12 regisztrálása az Intune-ban
Az Apple bejelentette, hogy néhány módosítás az iOS-eszközök regisztrálása a mobileszköz-felügyeleti (MDM) szolgáltatásra. A módosítás a spring 2019 kiadásban az IOS-es, valamint az összes jövőbeli iOS-kiadások valószínűleg lesz látható.

####<a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A végfelhasználók számára az új verzió 12 IOS-eszközeiket tavasszal frissíti, ha tudja, hogy a módosított munkafolyamat és kell Intune-ba való regisztrálást végrehajtani, további lépések végrehajtására. Apple ezeket a változásokat vezet be, amikor a végfelhasználók kell: • megkezdése a regisztrációt a céges portál alkalmazásban, töltse le a felügyeleti profil • lépjen a beállítások > Általános > profilok • válassza ki a megfelelő profilt, és kattintson a regisztráció elvégzését • térjen vissza a céges portál telepítése 

Már regisztrált eszközökre és a frissítési az új IOS-es kiadás nem befolyásolja, ha nem regisztrált, és egy friss regisztráció szükséges.
Az új kiadás az Apple regisztrációs folyamatának 12,1 vagy korábbi iOS rendszerű eszközökön nem változik.

####<a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Meg kell terveznie a dokumentációját, valamint a végfelhasználói útmutató frissítése. Érdemes azt is, ahhoz, hogy a segélyszolgálat ismeri ezeket a módosításokat. Folyamatosan tájékoztatjuk Önt folyamatosan értesíteni az üzenet központon keresztül, és az Újdonságok oldalát, amikor ez a változás élesíti.

Kattintson ide további információt a képernyőképek és a egy videót a várt regisztrációs folyamatot a támogatási blogbejegyzést.

####<a name="additional-information"></a>További információ
https://aka.ms/iOS_enrollment_changes

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Tervezett módosítás: Felhasználóiélmény-frissítést az iOS-hez készült Intune vállalati portál alkalmazás
Örömmel megosztására, hogy az Intune hamarosan adunk ki az IOS-es céges portál alkalmazás egy nagyszabású felhasználóiélmény-frissítést. A frissítés egy vizuális átalakulás a kezdőlap ügyfélszolgálatnak a speciális szűrők és az alkalmazások és könyvek gyorsabb hozzáférést.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A felhasználói élmény frissítése, miközben fenntartja az IOS-es céges portál funkciókat, ügyfélszolgálatnak:
- Egy natív iOS megjelenését és működését érintő kezdőlapján 
- A tartalom listáitól és szűrés a tartalomtípus (alkalmazások vagy e-könyvek) és a rendelkezésre állás (Eszközkezelés kötelező vagy elérhető legyen, regisztráció nélkül) például keresés szűrési képességek
- E-könyvek kereshetővé
- Keresési előzmények alkalmazásokhoz és e-könyvek Apple TestFlight programjában, ha értesítést kap az Intune frissített IOS-es céges portál alkalmazás az előzetes verzióval kapcsolatos mikor válik elérhetővé. Ha Ön nem Apple TestFlight programjában, nincs késő regisztrálni. Regisztrálása lehetővé teszi, hogy a frissített vállalati portál alkalmazást használja, mielőtt a végfelhasználók számára elérhető. A lehetőség közvetlenül az Intune-csapat a visszajelzést is megkapják.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Nem kell semmit sem kell; Ezeket a változásokat egy közelgő iOS CP alkalmazás kiadásban elérhető lesz. 

#### <a name="additional-information"></a>További információ
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="plan-for-change-exchange-online-to-intune-connector-will-not-be-available-in-intune----3105122---"></a>Tervezett módosítás: Exchange Online-t az Intune-összekötő nem lesz elérhető az Intune-ban <!-- 3105122 -->
Örömet talál az Exchange online-hoz és a feltételes hozzáférés leegyszerűsítése azt fogja kell letiltását az Exchange online-hoz az Intune-összekötő "Service to Service".

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ezt az üzenetet azért küldtük Önnek, mert adataik szerint, hogy lehet használni a "Service to Service" összekötő funkció a környezetben. A "Service to Service" összekötő az Exchange Active Sync csak az eszközök az Intune felügyeleti támogatja az Exchange online-hoz, és nem támogatja a helyszíni infrastruktúrát. Ezt az összekötőt, akkor jelenik meg a konzolon lehet, hogy szükségesek a feltételes hozzáféréssel (CA), megjelenik a valóságban ez nem szükségesek a hitelesítésszolgáltató. A február frissítéssel az Intune szolgáltatásba a konzol ezen egyértelművé teszi fog letiltjuk a gombra kattintva új összekötők beállítása. Ezt követően a március 2019, az összes meglévő Exchange Online-t az Intune-összekötő le lesz tiltva.

Ha használja ezeket az összekötőket a környezetben, akkor képes figyelésre vagy törölhetik az Exchange Active Sync csak az Intune-ban követően márciusban összekötők le lettek tiltva. Ez a módosítás során várható fennakadást a végfelhasználók számára van.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?

Ha a Service to Service connector beállításához és az Exchange Active Sync csak olyan eszközöket, váltson a más módszerek az eszközök felügyeletét. A következő lehetőségek állnak rendelkezésére:

- A mobileszköz-felügyeleti (MDM) eszközök regisztrálása
- Az Intune alkalmazásvédelmi szabályzatok használata az eszközök kezeléséhez
- Használja az Exchange vezérlőket, itt található dokumentáció foglaltak szerint. 

#### <a name="additional-information"></a>További információ
[Az Exchange-service connector konfigurálása az Intune és az Exchange online-hoz](https://docs.microsoft.com/intune/exchange-service-connector-configure)



### <a name="plan-for-change-performance-updates-to-intune-for-education---1750215--"></a>Tervezett módosítás: Az Intune for Education teljesítmény-frissítések <!--1750215-->
Hozzáadunk néhány frissítést az Intune for Education szolgáltatáshoz a sebesség és a megbízhatóság növeléséhez, amikor beállításokat rendel hozzá a felhasználókhoz vagy az eszközökhöz. A változás részeként november vége felé új csoportokba fogjuk áthelyezni a szabályzatait és beállítás-hozzárendeléseit.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

Az Intune for Education-ügyfél, mint két dinamikus Azure Active Directory (Azure AD) csoportokhoz van: "Minden felhasználó" és "Minden eszköz". Ezeknek a frissítéseknek az alkalmazása után a „Minden felhasználó” és „Minden eszköz” Azure AD-csoportok nem lesznek láthatók az Intune for Education-konzolon. Azonban továbbra is meg fognak jelenni az Intune-ban az Azure AD-konzolon, és át lesznek nevezve „Minden felhasználó (elavult, ne használja)” és „Minden eszköz (elavult, ne használja)” névre.

A frissítések bevezetése után már nem kell az Azure AD-csoportokat használnia az alkalmazások és a beállítások hozzárendelésére az Intune-ban. Ehelyett új csoportokba foguk áthelyezni a hozzárendelt beállításokat az Intune for Education-konzolon, amelyeket létre fogunk hozni az Ön számára, és amelyek továbbra is „Minden felhasználó” és „Minden eszköz” néven fognak megjelenni. Ezek a módosítások a háttérben fognak történni, ezért a Intune for Education-konzolon nem fog észlelni semmilyen változást. Nem várható, hogy ez negatív hatású lesz a végfelhasználókra vagy a regisztrált eszközökre. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Miközben mi áthelyezzük a hozzárendelt szabályzatokat, nem kell tennie semmit. Ha jelenleg a szabályzatok hozzárendelését az Intune for Education-konzolon végzi, tegye ezt továbbra is.

Ha jelenleg a fent említett Azure AD-csoportokhoz az Azure-beli Intune-ban rendeli hozzá a szabályzatokat, ehelyett inkább az Intune for Education-konzolon rendelje hozzá ezeket a Minden felhasználó és a Minden eszköz csoporthoz. Ha azt látja, hogy elavultként lettek átnevezve az Azure AD-csoportok a konzolon, a továbbiakban ne végezzen hozzárendelést az Azure AD-ben. Ha nem jelenleg használja az átnevezett csoportokat más célra, akkor törölje azokat.


### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Művelet végrehajtása: Frissítse az Android-eszköz korlátozása vagy a megfelelőségi jelszóval szabályzatbeállítások az Intune-ban
Az Intune-ból eltávolítjuk az eszköz alapértelmezett jelszavaként szolgáló jelszótípust az Android 4.4-es és újabb eszközök esetében. Az Android-platformok és az eszközök alapértelmezett beállításainak eltérései miatt az eszközök ezt a szabályzatot gyakran opcionálisként kezelik. Annak érdekében, hogy ne okozzon zavart, ha egy Android készüléken ez a beállítás van kötelezőként megadva, egy következő kiadásban eltávolítjuk a beállítást a kezelőfelületről. 
#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
- Ha az a célja, hogy az eszközökön kötelező legyen megadni valamilyen jelszót, javasoljuk, hogy az „eszköz alapértelmezett jelszavának” használata helyett úgy szerkessze az Android-platformprofilokat, hogy azok egyértelműen leírják a kívánt jelszótípust.
- Ha azt szeretné, hogy a végfelhasználók szabadon eldönthessék, létre szeretnének-e hozni egy jelszót, válassza a „Nincs konfigurálva” lehetőséget. Ha még mindig az „eszköz alapértelmezett jelszava” beállítás van érvényben, amikor eltávolítjuk ezt a beállítást a felhasználói felületről, akkor a profil következő szerkesztésekor választania kell egy másik értéket.
Hogyan készüljek fel a változásra?
Tekintse át a jelszóbeállításokat az Android vállalati eszközkorlátozási és megfelelőségi szabályzataiban. A megfelelőségi szabályzatok a Rendszerbiztonság alatt, az eszközkorlátozási szabályzatok pedig az Eszközjelszó vagy a Munkaprofil alatt találhatók meg. A további információk között talál egy hivatkozást, amelyen keresztül további részleteket és képernyőképeket talál ezekkel a beállításokkal kapcsolatban.
#### <a name="additional-information"></a>További információ
https://aka.ms/PasswordSettings 


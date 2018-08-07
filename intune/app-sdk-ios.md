---
title: A Microsoft Intune App SDK iOS rendszeren – fejlesztői útmutató
description: Az iOS-hez készült Microsoft Intune App SDK lehetővé teszi, hogy Intune-alkalmazásvédelmi szabályzatokat (vagy más néven APP- vagy MAM-szabályzatokat) építsen be natív iOS-alkalmazásába.
keywords: ''
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: f0c35caf841729aae8ce6ccdbf1c9709258a8f5b
ms.sourcegitcommit: 2e08887c07d29979300e80e6a40372aec6287103
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39249726"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>A Microsoft Intune App SDK iOS rendszeren – fejlesztői útmutató

> [!NOTE]
> Javasoljuk, hogy olvassa el az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, mely útmutatást nyújt az integráció előkészítéséhez a támogatott platformokon.

Az iOS-hez készült Microsoft Intune App SDK lehetővé teszi, hogy Intune alkalmazásvédelmi szabályzatokat (vagy más néven **alkalmazás-** vagy **MAM-szabályzatokat**) építsen be natív iOS-alkalmazásába. MAM-kompatibilisnek az Intune App SDK-val integrált alkalmazásokat nevezzük. Mindez lehetővé teszi a rendszergazdáknak, hogy alkalmazásvédelmi szabályzatokat telepítsenek a mobilalkalmazásra vonatkozóan, ha az Intune aktívan felügyeli az alkalmazást.

## <a name="prerequisites"></a>Előfeltételek

* Szüksége lesz egy OS X 10.8.5 vagy újabb verziót futtató Mac OS-számítógépre, amelyen telepítve van az Xcode 9-es vagy újabb verziója.

* Az alkalmazásnak az iOS 9.3.5-ös vagy újabb verzióival kell működnie.

* Olvassa el [az iOS-hez készült Intune App SDK licencfeltételeit](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Nyomtassa ki és őrizze meg a szerződés egy példányát. Az iOS-hez készült Intune App SDK letöltésével és használatával elfogadja licencfeltételeket.  Ha nem fogadja el, ne használja a szoftvert.

* Töltse le az iOS-re készült Intune App SDK fájljait a [GitHubról](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Az SDK tartalma

Az iOS-hoz készült Intune App SDK magában foglalja a statikus könyvtárat, az erőforrásfájlokat, az API-fejléceket, a hibakeresési beállításokat tartalmazó plist-fájlt és a konfiguráló eszközt. A mobilalkalmazások tartalmazhatják az erőforrásfájlokat, és általában statikus módon csatolhatók a könyvtárakhoz a szabályzatok érvénybe léptetéséhez. A speciális Intune APP-funkciók használata API-k segítségével kényszeríthető ki.

Ez az útmutató az iOS-hez készült Intune App SDK következő összetevőit ismerteti:

* **libIntuneMAM.a**: az Intune App SDK statikus erőforrástára. Ha az alkalmazás nem használ bővítményeket, Önnek ezt az erőforrástárat kell csatolnia a projekthez, hogy az alkalmazás felügyelhető legyen az Intune mobilalkalmazás-kezeléssel.

* **IntuneMAM.framework**: Az Intune App SDK keretrendszere. Ezt a keretrendszert kell csatolnia a projekthez, hogy az alkalmazás felügyelhető legyen az Intune mobilalkalmazás-kezelés segítségével. Akkor célszerű a keretrendszert használni a statikus kódtár helyett, ha az alkalmazás bővítményeket használ, mert így a projekt nem készít több másolatot a statikus kódtárból.

* **IntuneMAMResources.bundle**: az SDK erőforrásait tartalmazó csomag.

* **Headers**: az Intune App SDK API-jainak elérhetővé tétele. Ha API-t használ, meg kell adnia az API-t tartalmazó fejlécfájlt. Az alábbi fejlécfájlok tartalmazzák azokat az API-kat, adattípusokat és protokollokat, melyek az Intune APP SDK-val elérhetővé válnak a fejlesztők számára:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h

Az IntuneMAM.h importálásával a fenti fejlécek mindegyikének tartalma elérhetővé válik a fejlesztők számára.


## <a name="how-the-intune-app-sdk-works"></a>Az Intune App SDK működése

Az iOS-hoz készült Intune App SDK révén minimális kódmódosítással adhat hozzá felügyeleti funkciókat az iOS-alkalmazásokhoz. Minél kevesebb kódmódosítás szükséges, annál gyorsabban dobhatja piacra a mobilalkalmazást – az egységesség és a stabilitás terén kötött kompromisszumok nélkül.


## <a name="build-the-sdk-into-your-mobile-app"></a>Az SDK beépítése a mobilalkalmazásba

Az Intune App SDK az alábbi lépésekkel engedélyezhető:

1. **1. lehetőség (ajánlott)**: Az `IntuneMAM.framework` csatolása a projekthez. Húzza az `IntuneMAM.framework` keretrendszert a projekthez használni kívánt elemek **Embedded Binaries** (Beágyazott bináris fájlok) listájába.

   > [!NOTE]
   > Ha a keretrendszert használja, manuálisan kell eltávolítania a szimulátorarchitektúrákat az univerzális keretrendszerből, mielőtt beküldi az alkalmazást az App Store-ba. További információért lásd [Az alkalmazás beküldése az App Store-ba](#Submit-your-app-to-the-App-Store) című témakört.

   **2. lehetőség**: Csatolás a `libIntuneMAM.a` erőforrástárhoz. Húzza a `libIntuneMAM.a` könyvtárat a projekthez használni kívánt elemek **Linked Frameworks and Libraries** (Csatolt keretrendszerek és könyvtárak) listájába.

    ![Intune App SDK (iOS) – csatolt keretrendszerek és könyvtárak](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Írja be a `-force_load {PATH_TO_LIB}/libIntuneMAM.a` utasítást a következő helyek egyikére, kicserélve a `{PATH_TO_LIB}` sort az Intune App SDK elérési útjával:
   * a projekt `OTHER_LDFLAGS` buildkonfigurációs beállítása
   * az Xcode kezelőfelület **Other Linker Flags** (Más csatoló jelzők) területe

     > [!NOTE]
     > A `PATH_TO_LIB` megkereséséhez jelölje ki a `libIntuneMAM.a` fájlt és, és válassza a **File** (Fájl) menü **Get Info** (Információ megjelenítése) parancsát. Másolja és illessze be a **Where** (Hely) feliratnál látható információt (az elérési utat) az **Info** (Információ) ablak **General** (Általános) szakaszából.

     Húzza az `IntuneMAMResources.bundle` erőforrás-csomagot a **Copy Bundle Resources** (Erőforrás-csomagok másolása) alatti **Build Phases** (Összeállítási fázisok) elemre a projektbe való felvételhez.

     ![Intune App SDK (iOS) – erőforráscsomagok másolása](./media/intune-app-sdk-ios-copy-bundle-resources.png)

2. Vegye fel a következő iOS-keretrendszereket a projektbe:  
    * MessageUI.framework  
    * Security.framework  
    * MobileCoreServices.framework  
    * SystemConfiguration.framework  
    * libsqlite3.tbd  
    * libc++.tbd  
    * ImageIO.framework  
    * LocalAuthentication.framework  
    * AudioToolbox.framework  
    * QuartzCore.framework  
    * WebKit.framework

3. Engedélyezze a kulcsláncmegosztást (ha még nincs engedélyezve) a projekthez használni kívánt elemeken a **Capabilities** (Képességek) lehetőségre kattintva, majd kapcsolja be a **Keychain Sharing** (Kulcsláncmegosztás) kapcsolót. A következő lépéshez szükséges a kulcsláncmegosztás.

   > [!NOTE]
   > A telepítési profil esetében elengedhetetlen az új kulcsláncmegosztási értékek támogatása. A kulcslánc-hozzáférési csoportoknak támogatniuk kell a helyettesítő karaktert. Ezt a .mobileprovision fájl szövegszerkesztőben való megnyitásával ellenőrizheti, rákeresve a **keychain-access-groups** kifejezésre. Itt meggyőződhet arról, hogy használ-e helyettesítő karaktert. Például:
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Miután engedélyezte a kulcsláncmegosztást, az alábbi lépésekkel hozhat létre egy különálló hozzáférési csoportot, amelyben az Intune App SDK adatait tárolhatja. Kulcslánc-hozzáférési csoportot a felhasználói felületen vagy a jogosultságfájllal hozhat létre. Ha a kezelőfelületet használja a kulcslánc-hozzáférési csoport létrehozására, kövesse az alábbi lépéseket:

   1. Ha a mobilalkalmazás nem határozott meg kulcslánc-hozzáférési csoportokat, vegye fel az alkalmazás csomagazonosítóját az első csoport létrehozásához.

   2. Húzza a `com.microsoft.intune.mam` megosztott kulcslánccsoportot a meglévő hozzáférési csoportokhoz. Az Intune App SDK ezt a hozzáférési csoportot használja adatok tárolására.

   3. Vegye fel a `com.microsoft.adalcache` csoportot a meglévő hozzáférési csoportokba.

       ![Intune App SDK (iOS) – kulcsláncok megosztása](./media/intune-app-sdk-ios-keychain-sharing.png)

   4. Ha a jogosultságokat tartalmazó fájlt közvetlenül szerkeszti, ahelyett hogy a korábban bemutatott Xcode felhasználói felületet használná a kulcslánc-hozzáférési csoportok létrehozásához, fűzze a `$(AppIdentifierPrefix)` előtagot a kulcslánc hozzáférési csoportokhoz (az Xcode ezt automatikusan megteszi). Például:

           * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
           * `$(AppIdentifierPrefix)com.microsoft.adalcache`

      > [!NOTE]
      > A jogosultságokat tartalmazó fájl egy XML-fájl, amely minden mobilalkalmazásnál egyedi. és speciális engedélyek és képességek meghatározására szolgál az iOS-alkalmazásban. Ha az alkalmazása eddig nem rendelkezett jogosultságokat tartalmazó fájllal, a kulcsláncmegosztás engedélyezésekor (3. lépés) az Xcode generál egyet.

5. Az alkalmazáshoz tartozó Info.plist fájl `LSApplicationQueriesSchemes` tömbjében tüntessen fel minden protokollt, amelyet az alkalmazás átad az `UIApplication canOpenURL` számára. Ne felejtse el menteni a módosításokat, mielőtt folytatná a következő lépéssel.

6. Fejezze be az alkalmazás Info.plist fájljának konfigurálását az [SDK adattárában](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) található IntuneMAMConfigurator eszközzel. Az eszköz 3 paraméterrel rendelkezik:

   |Tulajdonság|Használat|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (Elhagyható) `<Path to the output plist>` |

Ha nem adja meg az „-o” paramétert, a bemeneti fájl helyben lesz módosítva. Az eszköz idempotens, és az Info.plist fájl vagy a jogosultságok változása esetén újra kell futtatnia. Emellett ha frissíti az Intune SDK-t, javasoljuk, hogy töltse le és futtassa az eszköz legújabb verzióját, mert elképzelhető, hogy megváltoztak az Info.plist fájl konfigurációs követelményei a legújabb kiadásban.

> [!NOTE]
> Ha az alkalmazás még nem használ FaceID-t, győződjön meg róla, hogy a(z) `NSFaceIDUsageDescription` info.plist kulcs az alapértelmezett üzenettel van konfigurálva. Ez kötelező, mivel az iOS így tudata a felhasználóval, hogy az alkalmazás hogyan használja a FaceID-t. A FaceID egy Intune App Protection szabályzatbeállítással alkalmazás-hozzáférési módként használható, ha ezt a rendszergazda konfigurálta.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Az Azure Active Directory Authentication Library (ADAL) konfigurálása (nem kötelező)

Az Intune App SDK az [Azure Active Directory Authentication Libraryt](https://github.com/AzureAD/azure-activedirectory-library-for-objc) hitelesítésre és a feltételes indítási forgatókönyvek készítésére használja. Az ADAL-ra támaszkodik a felhasználói identitások MAM-regisztrációjánál is az eszközbeléptetés nélküli felügyeleti megoldásokban.

Az ADAL használata során az alkalmazáshoz tartozó jogkivonatok biztonsága érdekében az alkalmazások használata legtöbbször az Azure Active Directoryban (AAD) való regisztrációhoz, valamint egyedi azonosító (ClientID) és egyéb azonosítók lekéréséhez kötött. Ha másként nincs megadva, az Intune App SDK az alapértelmezett regisztrációs értékeket használja, amikor kapcsolatba lép az Azure AD-val.  

Ha az alkalmazás már ADAL-t használ felhasználók hitelesítésére, akkor a meglévő regisztrációs értékeket kell használnia, és felül kell bírálnia az Intune App SDK alapértékeit. Ez biztosítja azt, hogy a felhasználóknak ne kelljen kétszer hitelesíteniük magukat (egyszer az Intune App SDK felé, egyszer pedig az alkalmazás felé).

Javasolt az alkalmazást a főágban az [ADAL legújabb verziójához](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) kapcsolni. Az Intune App SDK jelenleg az ADAL broker ágát használja a feltételes hozzáférést igénylő alkalmazások támogatásához. amelyekhez ennélfogva szükséges a Microsoft Authenticator alkalmazás. Az SDK ugyanakkor továbbra is kompatibilis az ADAL fő (master) ágával is. így Ön az alkalmazásának megfelelő ágat használhatja.

### <a name="link-to-adal-binaries"></a>Hivatkozás az ADAL bináris fájljaira

Az ADAL bináris fájljaira való hivatkozáshoz kövesse az alábbi lépéseket:

1. Töltse le az [Azure Active Directory Authentication Library (ADAL) for Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) erőforrástárat a GitHubról, majd kövesse az [utasításokat](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) az ADAL Git-almodulok vagy CocoaPods használatával történő letöltéséhez.

2. Vegye fel az ADAL-keretrendszert (1. lehetőség) vagy a statikus kódtárat (2. lehetőség) a projektjébe.

3. Ha az alkalmazás nem határozott meg kulcslánc-hozzáférési csoportokat, hozza létre az első csoportot az alkalmazás csomagazonosítójának felvételével.

4. Engedélyezze az ADAL egyszeri bejelentkezési (SSO) funkcióját úgy, hogy hozzáadja a `com.microsoft.adalcache` és a `com.microsoft.workplacejoin` hozzáférési csoportot a kulcslánc jogosultságai közé.

5. Ha explicit módon beállítja az ADAL megosztott gyorsítótárának kulcslánccsoportját, akkor feltétlenül a következő értékre állítsa: `<appidprefix>.com.microsoft.adalcache`. Az ADAL ezt állítja be, hacsak Ön felül nem bírálja. Ha a `com.microsoft.adalcache` helyett egyéni kulcslánccsoportot szeretne megadni, az Info.plist fájl IntuneMAMSettings szakaszában, az `ADALCacheKeychainGroupOverride` kulccsal teheti meg.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Az Intune App SDK ADAL-beállításainak konfigurálása

Ha az alkalmazás már ADAL-t használ hitelesítéshez, és saját ADAL-beállításokkal rendelkezik, akkor kényszerítheti az Intune App SDK-t, hogy az Azure Active Directory helyett ezeket a beállításokat használja. Ezzel biztosítható, hogy az alkalmazás ne kérje a hitelesítést kétszer is a felhasználótól. Az [Intune App SDK-beállítások konfigurálása](#configure-settings-for-the-intune-app-sdk) című témakörben tájékoztatást talál a következő beállítások értékének kitöltéséről:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Ha az alkalmazás már ADAL-t használ, az alábbi konfigurációs beállítások kötelezőek:

1. Adja meg az ADAL-hívásokhoz használandó ClientID-t a projekt Info.plist fájljában, az **IntuneMAMSettings** szótár alatt található `ADALClientId` nevű kulcsban.

2. A szintén az **IntuneMAMSettings** szótár alatt található `ADALAuthority` nevű kulcsban adja meg az Azure AD-szolgáltatót.

3. A szintén az **IntuneMAMSettings** szótár alatt található `ADALRedirectUri` nevű kulcsban adja meg az ADAL-hívásokhoz használandó átirányítási URI-t. Másik lehetőségként megadhatja az `ADALRedirectScheme` kulcsot is, ha az alkalmazás átirányítási URI-ja `scheme://bundle_id` formátumú.


Az alkalmazások felülbírálhatják ezeket az Azure AD-beállításokat futtatáskor. Ehhez egyszerűen állítsa be az `aadAuthorityUriOverride`, `aadClientIdOverride` és az `aadRedirectUriOverride` tulajdonságot az `IntuneMAMPolicyManager` példányon.

> [!NOTE]
> Az Info.plist fájl használatát javasoljuk az összes olyan beállításhoz, amely statikus, és nem igényel futtatáskori meghatározást. Az `IntuneMAMPolicyManager`-tulajdonságokhoz rendelt értékek elsőbbséget élveznek az Info.plist fájlban megadott hasonló értékekkel szemben, és még az alkalmazás újraindítása után is megmaradnak. Az SDK továbbra is használni fogja ezeket szabályzat-ellenőrzéshez egészen a felhasználó regisztrációjának törléséig, vagy addig, amíg nem módosítja vagy törli az értékeket.

### <a name="if-your-app-does-not-use-adal"></a>Ha az alkalmazás nem használ ADAL-t

Ha az alkalmazás nem az ADAL-t használja, az Intune App SDK szolgáltatja az ADAL-paraméterek alapértelmezett értékeit, és kezeli az Azure AD-val való hitelesítést. A fent ismertetett ADAL-beállítások egyikéhez sem szükséges értéket megadnia.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Az Intune App SDK-beállítások konfigurálása

Az Intune App SDK beállítását és konfigurálását az alkalmazás Info.plist fájljában található **IntuneMAMSettings** szótárral végezheti el. Ha az IntuneMAMSettings szótár nem látható az Info.plist fájlban, létre kell hoznia azt.

Az IntuneMAMSettings szótárban az alábbi támogatott beállításokkal konfigurálhatja a Intune App ADK-t.

Egy részükről már volt szó korábbi szakaszokban, más részük pedig nem vonatkozik minden alkalmazásra.

Beállítás  | Típus  | Meghatározás | Kötelező?
--       |  --   |   --       |  --
ADALClientId  | Sztring  | Az alkalmazás Azure AD ügyfél-azonosítója. | Kötelező, ha az alkalmazás használja az ADAL-t. |
ADALAuthority | Sztring | Az alkalmazás használatban lévő Azure AD-szolgáltatója. Használja azt a saját környezetet, ahol az AAD-fiókok konfigurálása megtörtént. | Kötelező, ha az alkalmazás használja az ADAL-t. Ha ez az érték hiányzik, a rendszer egy Intune-beli alapértelmezett értéket használ.|
ADALRedirectUri  | Sztring  | Az alkalmazás Azure AD átirányítási URI-ja. | Az ADAL-t használó alkalmazásoknak az ADALRedirectUri vagy az ADALRedirectScheme kötelező.  |
ADALRedirectScheme  | Sztring  | Az alkalmazás Azure AD átirányítási sémája. Használható az ADALRedirectUri helyett, ha az alkalmazás átirányítási URI-ja `scheme://bundle_id` formátumú. | Az ADALRedirectUri vagy az ADALRedirectScheme kötelező, ha az alkalmazás használja az ADAL-t. |
ADALLogOverrideDisabled | Logikai  | Megadásával az SDK átirányítja az összes ADAL-naplófájlt (beleértve az esetleges ADAL-hívásokat az alkalmazásból) a saját naplófájljába. Az alapértelmezett érték a Nem. Állítsa be a YES értéket, ha az alkalmazás visszahívja a saját ADAL-naplóját. | Nem kötelező. |
ADALCacheKeychainGroupOverride | Sztring  | Az ADAL-gyorsítótárhoz a „com.microsoft.adalcache” helyett használandó kulcslánccsoportot adja meg. Vegye figyelembe, hogy ez nem tartalmazza az app-id előtagot. Ezt az előtagot futás közben fogja megkapni a sztring. | Nem kötelező. |
AppGroupIdentifiers | Sztringtömb  | Az alkalmazáscsoportok tömbje az alkalmazás jogosultságainak com.apple.security.application-groups szakaszában. | Szükséges, ha az alkalmazás alkalmazáscsoportokat használ. |
ContainingAppBundleId | Sztring | Megadja a bővítményt tartalmazó alkalmazás csomagazonosítóját. | IOS-bővítményekhez szükséges. |
DebugSettingsEnabled| Logikai | Ha YES értékű, használhatók a Settings csomagban található tesztszabályzatok. Az alkalmazásokat *tilos* úgy szállítani, hogy engedélyezve van bennük ez a beállítás. | Nem kötelező. Az alapértelmezett érték a nem.|
MainNibFile <br> MainNibFile~ipad  | Sztring  | Ennek a beállításnak tartalmaznia kell az alkalmazás fő Nib-fájljának nevét.  | Kötelező, ha az alkalmazás a MainNibFile-t az Info.plist fájlban definiálja. |
MainStoryboardFile <br> MainStoryboardFile~ipad  | Sztring  | Ennek a beállításnak tartalmaznia kell az alkalmazás fő storyboard-fájljának nevét. | Kötelező, ha az alkalmazás a UIMainStoryboardFile-t az Info.plist fájlban definiálja. |
MAMPolicyRequired| Logikai| Azt adja meg, hogy megakadályozza-e a rendszer az alkalmazás elindítását, ha az alkalmazásnak nincs Intune APP-szabályzata. Az alapértelmezett érték a Nem. <br><br> Megjegyzés: Nem lehet olyan alkalmazásokat benyújtani az App Store-ba, amelyeknél a MAMPolicyRequired beállítása YES értékű. | Nem kötelező. Az alapértelmezett érték a nem.|
MAMPolicyWarnAbsent | Logikai| Azt adja meg, hogy figyelmeztesse-e az alkalmazás a felhasználót indítás közben, ha az alkalmazásnak nincs Intune APP-szabályzata. <br><br> Megjegyzés: A felhasználók a figyelmeztetés bezárása után szabályzat nélkül is használhatják az alkalmazást. | Nem kötelező. Az alapértelmezett érték a nem. |
MultiIdentity | Logikai| Azt adja meg, hogy az alkalmazás képes-e kezelni a többszörös identitást. | Nem kötelező. Az alapértelmezett érték a nem. |
SplashIconFile <br> SplashIconFile ~ ipad | Sztring  | Az Intune-kezdőképet (indítóképernyőt) tartalmazó ikonfájlt határozza meg. | Nem kötelező. |
SplashDuration | Szám | Az Intune-kezdőképernyő megjelenésének minimális időtartama (másodpercben) az alkalmazás indításakor. Az alapértelmezett érték 1.5. | Nem kötelező. |
BackgroundColor| Sztring| A kezdő- és a PIN-kód bevitelére szolgáló képernyő háttérszínét adja meg. Hexadecimális RGB-sztringet fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jel kihagyható.   | Nem kötelező. Alapértelmezése a világosszürke szín. |
ForegroundColor| Sztring| A kezdőképernyő és a PIN-kód bevitelére szolgáló képernyő előtérszínét, például a szöveg színét határozza meg. Hexadecimális RGB-sztringet fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jel kihagyható.  | Nem kötelező. Alapértelmezett értéke a fekete. |
AccentColor | Sztring| A PIN-kód megadására szolgáló képernyő kiemelőszínét (például a gombszöveg színét és a mezők kijelölésének színét) határozza meg. Hexadecimális RGB-sztringet fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jel kihagyható.| Nem kötelező. Alapértéke a rendszer kék színe. |
MAMTelemetryDisabled| Logikai| Az határozható meg vele, hogy az SDK ne küldjön telemetriai adatokat a háttérrendszerének.| Nem kötelező. Az alapértelmezett érték a nem. |
MAMTelemetryUsePPE | Logikai | Itt adhatja meg, hogy a MAM SDK-t küldjön-e adatokat a PPE telemetriai háttérrendszernek. Akkor használja ezt a beállítást, ha teszteli az alkalmazásokat az Intune szabályzatával. Megakadályozhatja vele, hogy a teszt telemetriai adatai keveredjenek az ügyfelek adataival. | Nem kötelező. Az alapértelmezett érték a nem. |
MaxFileProtectionLevel | Sztring | Nem kötelező. Itt engedélyezheti az alkalmazásnak az által támogatott maximális `NSFileProtectionType` szintnek a meghatározását. Ez az érték felülbírálja a szolgáltatás által küldött szabályzatot, ha a szint magasabb, mint amit az alkalmazás támogatni képes. A lehetséges értékek: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Logikai | A beállítása YES a műveleti bővítményekben való megnyitáshoz. További információért lásd az Adatok megosztása az UIActivityViewController használatával szakaszt. |
WebViewHandledURLSchemes | Sztringek tömbje | Az alkalmazás WebView-ja által kezelt URL-sémát határozza meg. | Kötelező, ha az alkalmazás olyan WebView-t használ, amely az URL-címeket hivatkozásokkal és/vagy javascripttel kezeli. |

## <a name="receive-app-protection-policy"></a>Alkalmazásvédelmi szabályzat fogadása

### <a name="overview"></a>Áttekintés

Az Intune alkalmazásvédelmi szabályzatának fogadásához az alkalmazásoknak regisztrációs kérelmet kell kezdeményezniük az Intune MAM szolgáltatásban. Az Intune konzollal konfigurálhatja az alkalmazásokat az alkalmazásvédelmi szabályzat eszközregisztrációtól független fogadására. Az **APP-WE** vagy MAM-WE néven is ismert eszközregisztráció nélküli alkalmazásvédelmi szabályzat lehetővé teszi, hogy az Intune anélkül is felügyelhesse az alkalmazásokat, hogy az eszközök az Intune mobileszköz-felügyeletre (MDM) regisztrálva lennének. Mindkét esetben szükséges regisztrálni az Intune MAM szolgáltatásban a szabályzat fogadásához.

### <a name="apps-that-use-adal"></a>ADAL-t használó alkalmazások

Az ADAL-t már használó alkalmazásoknak az `IntuneMAMEnrollmentManager` példány `registerAndEnrollAccount` metódusát kell meghívniuk a felhasználó sikeres hitelesítése után:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

Az SDK a `registerAndEnrollAccount` metódus meghívásával regisztrálja a felhasználói fiókot, és megpróbálja regisztrálni az alkalmazást ennek a fióknak a nevében. Ha a regisztráció bármilyen okból nem sikerül, az SDK 24 óra múlva újra próbálkozik. Hibakeresési célokra az alkalmazás egy delegálton keresztül fogadhat [értesítéseket](#Status-result-and-debug-notifications) a regisztrációs kérések eredményéről.

Az API meghívása után az alkalmazás a szokásos módon működhet tovább. Ha a regisztráció sikeres, az SDK értesíti a felhasználót, hogy újra kell indítani az alkalmazást. Ekkor a felhasználó azonnal újraindíthatja az alkalmazást.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>Az ADAL-t nem használó alkalmazások

Olyan alkalmazás is fogadhat alkalmazásvédelmi szabályzatot az Intune MAM szolgáltatástól, amely nem jelentkezteti be a felhasználót az ADAL használatával. Ez esetben az API meghívásával kell utasítani az SDK-t ennek a hitelesítésnek a kezelésére. Az alkalmazásoknak ezt a módszert kell használniuk abban az esetben, ha nem hitelesítették a felhasználót az Azure AD-vel, ugyanakkor szükség van az alkalmazásvédelmi szabályzat lekérésére az adatok védelméhez. Ilyen például, ha másik hitelesítési szolgáltatást használ az alkalmazásba való bejelentkezésre, vagy ha az alkalmazás egyáltalán nem támogatja a bejelentkezést. Ehhez az alkalmazás használhatja az `IntuneMAMEnrollmentManager` példány `loginAndEnrollAccount` metódusát:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

A metódus meghívása esetén az SDK hitelesítő adatok megadását kéri a felhasználótól, ha nem található meglévő token///jogkivonat. Az SDK ezután megpróbálja regisztrálni az alkalmazást az Intune MAM szolgáltatásban a megadott felhasználói fiók nevében. A metódus nil (nulla) identitással is meghívható. Ez esetben az SDK regisztrálja az eszköz meglévő felügyelt felhasználóját (az MDM esetében), vagy ha nem talál meglévő felhasználót, kéri a felhasználótól a felhasználónevet.

Ha a regisztráció sikertelen, az alkalmazásnak valamikor a jövőben újra meg kell vizsgálnia az API meghívásának lehetőségét, függően a sikertelenség részleteitől. Az alkalmazás egy delegálton keresztül fogadhat [értesítéseket](#Status-result-and-debug-notifications) a regisztrációs kérések eredményéről.

Az API meghívása után az alkalmazás a szokásos módon működhet tovább. Ha a regisztráció sikeres, az SDK értesíti a felhasználót, hogy újra kell indítani az alkalmazást.

Például:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Indításkor az Intune kezelheti a hitelesítést és a regisztrációt

Ha azt szeretné, hogy az Intune SDK minden hitelesítést az ADAL és a regisztráció használatával kezeljen még az alkalmazás indításának befejeződése előtt, és hogy az alkalmazás mindig kérjen APP-szabályzatot, akkor nem kell használnia a `loginAndEnrollAccount` API-t. Egyszerűen megadhatja a két alábbi beállításhoz a YES értéket az alkalmazás Info.plist fájljának IntuneMAMSettings szótárában.

Beállítás  | Típus  | Meghatározás |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Logikai| Megadja, hogy az alkalmazás megpróbáljon-e automatikusan regisztrálni indításkor, ha meglévő felügyelt identitást érzékel, és ha korábban még nem történt regisztráció. Az alapértelmezett érték a Nem. <br><br> Megjegyzés: Ha az alkalmazás nem talál felügyelt identitást, vagy nem érhető el érvényes token az identitáshoz az ADAL-gyorsítótárban, a regisztrációs kísérlet meg fog hiúsulni anélkül, hogy az alkalmazás a hitelesítő adatokat kérné, hacsak nincs a MAMPolicyRequired opció is YES-re állítva. |
MAMPolicyRequired| Logikai| Azt adja meg, hogy megakadályozza-e a rendszer az alkalmazás elindítását, ha az alkalmazásnak nincs Intune alkalmazásvédelmi szabályzata. Az alapértelmezett érték a Nem. <br><br> Megjegyzés: Nem lehet olyan alkalmazásokat benyújtani az App Store-ba, amelyeknél a MAMPolicyRequired beállítása YES értékű. HA a MAMPolicyRequired értéke IGEN, az AutoEnrollOnLaunch beállítását is IGEN értékre kell állítani. |

Ha ezt a beállítást választja az alkalmazáshoz, akkor regisztráció után nem kell az alkalmazás újraindításával foglalkoznia.

### <a name="deregister-user-accounts"></a>Felhasználói fiókok regisztrációjának megszüntetése

Mielőtt egy felhasználó kijelentkezik az alkalmazásból, az alkalmazásnak meg kell szüntetnie a felhasználó regisztrációját az SDK-ban. Ez biztosítja az alábbiakat:

1. Nem lesznek további próbálkozások a felhasználói fiók regisztrálására.

2. Az alkalmazásvédelmi szabályzat el lesz távolítva.

3. Ha az alkalmazás szelektív törlést kezdeményez (igény szerint), akkor az összes céges adat törlődik.

A felhasználó kijelentkeztetése előtt az alkalmazásnak meg kell hívnia a következő metódust az `IntuneMAMEnrollmentManager` példányon:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Ezt a metódust még a felhasználó Azure AD-jogkivonatainak törlése előtt kell meghívni. Az SDK-nak azért van szüksége a felhasználói fiók AAD-jogkivonatára vagy -jogkivonataira, hogy a felhasználó nevében küldhessen el bizonyos kéréseket az Intune MAM szolgáltatásnak.

Ha az alkalmazás saját maga gondoskodik a felhasználó céges adatainak törléséről, akkor a `doWipe` jelző false értékre állítható. Egyéb esetben az alkalmazás az SDK-val is elvégeztetheti a szelektív törlést. Ennek eredményeképpen létrejön egy hívás az alkalmazás szelektív törlési delegáltja felé.

Például:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Állapot-, eredmény- és hibakeresési értesítések

Az alkalmazás az Intune MAM-szolgáltatásokhoz intézett kérések közül a következők esetében tudja fogadni az állapot-, eredmény- és hibakeresési értesítéseket:

* Regisztrációs kérések
* Szabályzatfrissítési kérések
* Beléptetés-visszavonási kérések

Az értesítéseket delegáltmetódusok adják át. Ezeket a `IntuneMAMEnrollmentDelegate.h` fájl tartalmazza:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;
```

Ezek a delegáltmetódusok egy `IntuneMAMEnrollmentStatus` objektumot adnak vissza, amely a következő információkat tartalmazza:

* A kéréshez társított fiók identitását
* A kérés eredményét jelölő állapotkódot
* Az állapotkód leírását tartalmazó hibaüzenet-sztringet
* Egy `NSError` objektumot. Ezt az objektumot az `IntuneMAMEnrollmentStatus.h` nevű fájl definiálja a visszaadható konkrét állapotkódokkal együtt.

> [!NOTE]
> Ez az információ csak hibakeresési célra szolgál. Az alkalmazásban nem alapulhat üzleti logika ezeken az értesítéseken. Ezt az információt el lehet küldeni telemetriai szolgáltatásnak hibakeresési vagy figyelési célból.

### <a name="sample-code"></a>Mintakód

A következők a delegáltmetódusok megvalósítására szolgálnak példákkal:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Alkalmazás-újraindítás

Amikor egy alkalmazás először kap MAM-szabályzatokat, újra kell indulnia a szükséges beavatkozási pontok alkalmazása érdekében. Az SDK biztosít egy delegáltmetódust az `IntuneMAMPolicyDelegate.h` fájlban, amellyel értesíteni lehet az alkalmazást az újraindítás szükségességéről.

```objc
 - (BOOL) restartApplication
```

A metódus visszatérési értéke közli az SDK-val, hogy az alkalmazásnak kell-e kezelni a szükséges újraindítást:

* Ha a visszatérési érték true (igaz), akkor az alkalmazásnak kell kezelnie az újraindítást.

* „False” érték esetén a metódus visszatérése után az SDK indítja újra az alkalmazást. Az SDK azonnal megjelenít egy párbeszédpanelt, amely arra kéri a felhasználót, hogy indítsa újra az alkalmazást.

## <a name="customize-your-apps-behavior-with-apis"></a>Az alkalmazás viselkedésének testreszabása API-kkal

Az Intune App SDK több olyan API-val rendelkezik, amelyeket meg lehet hívni az alkalmazáshoz telepített Intune APP-szabályzat információinak beolvasásához. Ezekkel az adatokkal testre lehet szabni az alkalmazás viselkedését. Az alábbi táblázat információt biztosít néhány alapvető fontosságú Intune-osztályról, amelyeket használni fog.

Osztály | Description
----- | -----------
IntuneMAMPolicyManager.h | Az IntuneMAMPolicyManager osztály közzé teszi az alkalmazáshoz telepített Intune APP-szabályzatot. Olyan API-kat tesz közzé, amelyek hasznosak lehetnek [több identitás engedélyezésekor](#-enable-multi-identity-optional). |
IntuneMAMPolicy.h | Az IntuneMAMPolicy osztály közzétesz néhány, az alkalmazásra vonatkozó MAM-szabályzatbeállítást. Ezeknek a szabályzatbeállításoknak a közzététele azért történt, hogy az alkalmazás testre szabhassa a felhasználói felületét. A legtöbb szabályzatbeállítást az SDK kényszeríti, nem az alkalmazás. Az alkalmazás által implementálandó egyetlen beállítás a Mentés másként vezérlő. Ez az osztály közzétesz néhány, a Mentés másként vezérlő végrehajtásához szükséges API-t. |
IntuneMAMFileProtectionManager.h | Az IntuneMAMFileProtectionManager osztály olyan API-kat tesz közzé, amelyeket az alkalmazás fájlok és könyvtárak védelmére használhat a megadott identitás alapján. Az identitást kezelheti az Intune, vagy lehet nem felügyelt, és az SDK alkalmazza a megfelelő MAM-szabályzatot. Ennek az osztálynak a használata nem kötelező. |
IntuneMAMDataProtectionManager.h | A IntuneMAMDataProtectionManager osztály olyan API-kat tesz közzé, amelyeket az alkalmazás használhat adatpufferek védelmére a megadott identitás alapján. Az identitást kezelheti az Intune, vagy lehet nem felügyelt, és az SDK ennek megfelelően alkalmazza a titkosítást. |

## <a name="implement-save-as-controls"></a>A Mentés másként vezérlőinek implementálása

Az Intune lehetővé teszi a rendszergazdák számára a felügyelt alkalmazások adatmentéshez használható tárolási helyeinek meghatározását. Az alkalmazások lekérhetik az engedélyezett tárolási helyek listáját az Intune App SDK-tól az `IntuneMAMPolicy.h` fájlban meghatározott `isSaveToAllowedForLocation` API használatával.

Mielőtt az alkalmazások felügyelt adatokat menthetnének felhőbeli tárhelyre vagy helyi adattárolókba, az `isSaveToAllowedForLocation` API használatával ellenőriznie kell, hogy a rendszergazda engedélyezte-e az adatmentést az adott helyre.

Az alkalmazásoknak az `isSaveToAllowedForLocation` API használatakor át kell adniuk a tárolási hely UPN-jét, amennyiben az elérhető.

### <a name="supported-save-locations"></a>Támogatott mentési helyek

Az `isSaveToAllowedForLocation` API által biztosított állandókkal ellenőrizhető, hogy a rendszergazda engedélyezi-e az adatok mentését az `IntuneMAMPolicy.h` fájlban meghatározott alábbi helyekre:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Az alkalmazásoknak az `isSaveToAllowedForLocation` állandóival kell ellenőrizniük, hogy az adatok menthetők-e „felügyeltnek” tekintett, például a OneDrive Vállalati verziójába, vagy „személyes” helyekre. Emellett akkor is szükséges az API használata, ha az alkalmazás nem képes megállapítani egy adott helyről, hogy az „felügyelt” vagy „személyes”.

A „személyes” helyeket az `IntuneMAMSaveLocationOther` állandó képviseli.

Az `IntuneMAMSaveLocationLocalDrive` állandót akkor érdemes használni, amikor az alkalmazás a helyi eszközre ment adatot.

## <a name="share-data-via-uiactivityviewcontroller"></a>Adatok megosztása az UIActivityViewController használatával

A 8.0.2 kiadásától kezdődően az Intune App SDK képes szűrni az `UIActivityViewController`-műveleteket, hogy csak az Intune által kezelt megosztott helyek legyenek kijelölhetők. Ezt a működést az alkalmazás adatátviteli szabályzata fogja szabályozni.

### <a name="copy-to-actions"></a>„Másolás ide” műveletek

Dokumentumoknak az `UIActivityViewController` és az `UIDocumentInteractionController` általi megosztásakor az iOS másolási műveletet jelenít meg a megosztott dokumentum megnyitását támogató alkalmazások mindegyike mellett. Az alkalmazások az Info.plist fájljukban lévő `CFBundleDocumentTypes` beállításban közlik a támogatott dokumentumok típusát. Ez a megosztástípus többé nem lesz elérhető, ha a szabályzat tiltja a nem felügyelt alkalmazásokkal való megosztást. Helyette egy felhasználói felület nélküli műveleti bővítményt kell hozzáadni az alkalmazásokhoz, amely az Intune APP SDK-ra hivatkozik. A műveleti bővítmény mindössze egy kódcsonk. A fájlmegosztó viselkedést az SDK implementálja. Kövesse az alábbi lépéseket:

1. Az alkalmazás Info.plist fájljában a `CFBundleURLTypes` alatt szerepelnie kell legalább egy schemeURL-definíciónak.

2. Az alkalmazásnak és a műveleti bővítménynek benne kell lennie legalább egy közös alkalmazáscsoportban, az alkalmazáscsoportnak pedig szerepelnie kell az `AppGroupIdentifiers` tömbben az alkalmazás és bővítmény IntuneMAMSettings katalógusaiban.

3. A műveleti bővítmény neveként adja meg a „Megnyitás a következőben:” szöveget az alkalmazás nevével kiegészítve. Szükség esetén az Info.plist fájl honosítható.

4. Adjon meg egy sablonikont a bővítményhez az [Apple fejlesztői dokumentációjában](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/) leírt módon. Ezek a képek az IntuneMAMConfigurator eszközzel is generálhatók az alkalmazás .app mappájából. Ehhez futtassa a következőt:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

5. A bővítmény Info.plist fájljában az IntuneMAMSettings alatt adjon meg egy logikai típusú beállítást, melynek neve `OpenInActionExtension`, értéke pedig YES.

6. Konfigurálja az `NSExtensionActivationRule` szabályt, hogy támogasson egyetlen fájlt és az alkalmazás `CFBundleDocumentTypes` tulajdonságának minden típusát, amely `com.microsoft.intune.mam` előtaggal rendelkezik. Ha az alkalmazás például a public.text és public.image típusokat támogatja, akkor az aktiválási szabály a következő lesz:

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text” ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image”).@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Meglévő megosztási és műveleti bővítmények frissítése

Ha az alkalmazás már tartalmaz megosztási vagy műveleti bővítményeket, akkor az Intune-típusok engedélyezéséhez módosítani kell azok `NSExtensionActivationRule` beállítását. Minden kiterjesztéssel megadott támogatott típushoz új típust kell megadni a `com.microsoft.intune.mam` előtaggal. Ha a meglévő aktiválási szabály például a következő:  

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
        ).@count > 0
    ).@count > 0
    ```

Akkor az alábbi módon kell módosítani:

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data
        ).@count > 0
    ).@count > 0
    ```

> [!NOTE]
> Az Intune-típusok a IntuneMAMConfigurator-eszköz használatával adhatók az aktiválási szabályhoz. Ha a meglévő aktiválási szabály előre definiált sztringkonstansokat használ (például NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText stb.), akkor a predikátumok szintaxisa nagyon bonyolulttá válhat. Az IntuneMAMConfigurator-eszköz arra is felhasználható, hogy az aktiválási szabályt sztringkonstansokból predikátumsztringgé alakítsa az Intune-típusok hozzáadása során.

### <a name="what-the-ui-should-look-like"></a>Hogyan kell kinéznie a felhasználói felületnek?

Régi felhasználói felület:

![Régi megosztási felhasználói felület](./media/sharing-UI-old.png)

Új felhasználói felület:

![Új megosztási felhasználói felület](./media/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>Célzott konfiguráció (APP/MAM-alkalmazáskonfiguráció) engedélyezése iOS-alkalmazásokhoz

A célzott MAM-konfiguráció (másként MAM-alkalmazáskonfiguráció) lehetővé teszi, hogy az alkalmazások konfigurációs adatokat fogadjanak az Intune App SDK-ból. Ezeknek az adatoknak a formátumát és változatait az alkalmazás tulajdonosának/fejlesztőjének kell meghatároznia és kommunikálnia az Intune-ügyfelek felé.

Az Intune-rendszergazdák az Intune Azure Portalon és az Intune Graph API-val célozhatják és telepíthetik a konfigurációs adatokat. Az iOS-hez készült Intune App SDK 7.0.1-es és újabb verzióiban a célzott MAM-konfigurációban résztvevő alkalmazások a MAM szolgáltatáson keresztül kaphatják meg a célzott MAM-konfigurációs adatokat. Az alkalmazáskonfigurációs adatokat az MDM-csatorna helyett az MAM szolgáltatásán keresztül közvetlenül az alkalmazásba küldi a rendszer. Az Intune App SDK egy osztályt biztosít az ezekről a konzolokról lekért adatok eléréséhez. Az előfeltételek a következők:

* Ahhoz, hogy el lehessen érni a célzott MAM-konfigurációs felhasználói felületet, az alkalmazást regisztrálni kell az Intune MAM szolgáltatásban. További információkért lásd: [Alkalmazásvédelmi szabályzat fogadása](#receive-app-protection-policy).

* Foglalja bele az `IntuneMAMAppConfigManager.h` kódot az alkalmazás forrásfájljába.

* Az alkalmazás konfigurációs objektumának beszerzéséhez hívja az `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` funkciót.

* Hívja a megfelelő szelektort az `IntuneMAMAppConfig` objektumon. Ha például az alkalmazás kulcsa egy sztring, akkor használhatja a `stringValueForKey` vagy az `allStringsForKey` lehetőséget. A visszatérési értékek és a hibaállapotok részletes leírását lásd: `IntuneMAMAppConfig.h`.

További információ a Graph API funkcióiról: [Graph API-segédlet](https://developer.microsoft.com/graph/docs/concepts/overview).

A célzott MAM-alkalmazáskonfigurációs szabályzat iOS rendszerben való létrehozásáról lásd [A Microsoft Intune alkalmazáskonfigurációs szabályzatainak használata iOS rendszerben](https://docs.microsoft.com/intune/app-configuration-policies-use-ios) célzott MAM-alkalmazáskonfigurációról szóló szakaszát.

## <a name="telemetry"></a>Telemetria

Az iOS-hez készült Intune App SDK alapértelmezés szerint a következő eseménytípusokkal kapcsolatos telemetriai adatokat naplózza:

* **Az alkalmazások indítása:** a Microsoft Intune tájékozódhat a különböző felügyeleti típusú MAM-kompatibilis alkalmazások használatáról (MAM az MDM-mel, MAM MDM-regisztráció nélkül stb.).

* **Regisztrációs hívások**: a Microsoft Intune a sikerességi arányról és az ügyféloldalról kezdeményezett regisztrációs hívások egyéb teljesítménymutatóiról is gyűjt információkat.

* **Intune-műveletek**: A problémák diagnosztizálása és az Intune működésének biztosítása érdekében adatokat gyűjtünk az Intune SDK műveleteiről.

> [!NOTE]
> Ha nem kíván az Intune App SDK-ból származó telemetriai adatokat küldeni a Microsoft Intune-nak a mobilalkalmazásból, le kell tiltania az Intune App SDK-ban a telemetriai adatok rögzítését. Ehhez állítsa a `MAMTelemetryDisabled` tulajdonságot YES értékre az IntuneMAMSettings szótárban.

## <a name="enable-multi-identity-optional"></a>Több identitás használatának lehetővé tétele (nem kötelező)

Az SDK alapértelmezés szerint az alkalmazás egészére alkalmazza a szabályzatot. A MAM többszörös identitás szolgáltatásával engedélyezhető a szabályzatok identitásszintű alkalmazása. Ebből az alkalmazásnak nagyobb részt kell vállalnia, mint a MAM többi funkciójából.

Az alkalmazásnak tájékoztatnia kell az App SDK-t, ha módosítani kívánja az aktív identitást. Az SDK szintén értesíti az alkalmazást, ha identitásváltás szükséges. Jelenleg csak egy felügyelt identitás támogatott. Ha a felhasználó már regisztrálta az eszközt vagy az alkalmazást, az SDK ezt az identitást használja, és ezt tekinti az elsődleges felügyelt identitásnak. Az alkalmazás többi felhasználójával nem felügyeltként bánik, szabályzatbeállításaik korlátlanok.

Felhívjuk, hogy az identitás egyszerűen egy sztringként van definiálva. Az identitás karakterláncában a kis- és nagybetűk nincsenek megkülönböztetve. Az SDK nem feltétlenül olyan kis- és nagybetűkkel adja vissza a tőle kért identitásokat, mint ahogyan az az identitás beállításakor eredetileg meg volt adva.

### <a name="identity-overview"></a>Az identitások áttekintése

Az identitás egyszerűen egy fiók felhasználóneve (például user@contoso.com). A fejlesztők a következő szinteken adhatják meg az alkalmazáshoz tartozó identitást:

* **Folyamat identitása**: a folyamat szintjén állítja be az identitást, és elsősorban egyidentitású alkalmazások esetében használatos. Ez az identitás kapcsolódik minden feladathoz, fájlhoz és felhasználói felülethez.

* **Kezelőfelület identitása**: azt határozza meg, hogy milyen szabályzatok alkalmazandók a főszálban végzett kezelőfelületi műveletekre, például a kivágásra, a másolásra, a beillesztésre, a PIN-kód megadására, a hitelesítésre vagy az adatmegosztásra. A kezelőfelület identitása nincs hatással a fájlműveletekre, például a titkosításra vagy a biztonsági mentésre.

* **Szál identitása**: azt határozza meg, hogy milyen szabályzatok alkalmazandók az aktuális szálra. Ez az identitás hatással van minden műveletre, fájlra és a kezelőfelületre is.

Az identitás helyes beállítása az alkalmazás feladata, függetlenül attól, hogy felügyelt felhasználóról van-e szó vagy sem.

Minden szálnak minden pillanatban van egy effektív identitása mind a kezelőfelületi műveletekre, mind a fájlműveletekre vonatkozóan. A rendszer ennek az identitásnak az alapján határozza meg, hogy kell-e alkalmazni szabályzatokat, és ha igen, milyeneket. Ha az identitás „no identity”, vagy ha nem felügyelt felhasználóról van szó, a rendszer nem alkalmaz szabályzatokat. Az alábbi ábrán látható, hogy a rendszer miként határozza meg a tényleges identitásokat.

  ![Intune App SDK (iOS) – csatolt keretrendszerek és könyvtárak](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Szálak várólistái

Az alkalmazások gyakran küldenek szinkron és aszinkron feladatokat a szálak várólistáiba. Az SDK elfogja a Grand Central Dispatch- (GCD-) hívásokat, és a szál aktuális identitását társítja a kiosztott feladatokhoz. A feladatok befejezésekor az SDK átmenetileg módosítja a szál identitását a feladathoz társított identitásra, befejezi a feladatokat, majd visszaállítja a szál eredeti identitását.


Tekintettel arra, hogy az `NSOperationQueue` a GCD-re épül, az `NSOperations` műveletek azzal az identitással futnak, amely a szál identitása volt az adott művelet `NSOperationQueue` várólistába való felvételekor. Az `NSOperations` műveletek és a GCD segítségével közvetlenül indított függvények módosíthatják is a szál aktuális identitását, amikor futnak. felülbírálva a kiosztó száltól örökölt identitást.

### <a name="file-owner"></a>Fájltulajdonos

Az SDK nyilvántartja a helyi fájltulajdonosok identitását, és annak megfelelően alkalmazza a szabályzatokat. A rendszer a fájlhoz a létrehozásakor vagy csonkolási módban való megnyitásakor rendeli hozzá a tulajdonost. A rendszer tulajdonosként a műveletet végrehajtó szál effektív fájlműveleti identitását állítja be.

Az alkalmazások explicit módon is megadhatják a fájl tulajdonosát az `IntuneMAMFilePolicyManager` segítségével. Az alkalmazások az `IntuneMAMFilePolicyManager` segítségével kérhetik le a fájl tulajdonosát, és állíthatják be a kezelőfelület identitását a fájl tartalmának megjelenítése előtt.

### <a name="shared-data"></a>Megosztott adatok

Ha az alkalmazás olyan fájlokat hoz létre, amelyek felügyelt és nem felügyelt felhasználóktól származó adatokat is tartalmaznak, akkor az alkalmazás felelős a felügyelt felhasználó adatainak titkosításáért. Az adatokat a `protect` és az `unprotect` API-k segítségével titkosíthatja az `IntuneMAMDataProtectionManager` eszközben.

A `protect` metódus identitást fogad el paraméterként. Ez lehet felügyelt és nem felügyelt felhasználó is. Felügyelt felhasználó esetén titkosítja az adatokat. Nem felügyelt felhasználó esetén az identitást kódoló fejlécet ad hozzá az adatokhoz, de nem titkosítja az adatokat. A `protectionInfo` metódussal lehet bekérni az adat tulajdonosát.

### <a name="share-extensions"></a>Megosztási bővítmények

Ha az alkalmazás megosztási bővítményt tartalmaz, a megosztás alatt álló elem tulajdonosa az `IntuneMAMDataProtectionManager` `protectionInfoForItemProvider` metódusával kérhető le. Ha a megosztott elem fájl, akkor az SDK kezeli a fájltulajdonos beállítását. Ha a megosztott elem adat, és az adatok fájlban lesznek tárolva, akkor az alkalmazás felelős a fájl tulajdonosának beállításáért és a `setUIPolicyIdentity` API meghívásáért, mielőtt megjelenítené az adatokat a kezelőfelületen.

### <a name="turn-on-multi-identity"></a>A többszörös identitás bekapcsolása

Alapértelmezés szerint az alkalmazások egyszeres identitásnak minősülnek. Az SDK a folyamat identitását a regisztrált felhasználóhoz állítja be. A többszörös identitás támogatás engedélyezéséhez a `MultiIdentity` nevű és YES értékű beállítást kell felvenni az alkalmazás Info.plist fájljába, az IntuneMAMSettings szótárba.

> [!NOTE]
> Ha engedélyezve van a többszörös identitás, a folyamat identitása, a kezelőfelület identitása és a szálak identitása nil lesz. Ezek megfelelő beállítása az alkalmazás feladata.

### <a name="switch-identities"></a>Identitásváltás

* **Az alkalmazás által kezdeményezett identitásváltás**:

    A többszörös identitású alkalmazásokat az indításkor ismeretlen, nem felügyelt fiókkal futó alkalmazásnak tekinti a rendszer. A feltételes indítású felhasználói felület nem fut, és az alkalmazásra nem lépnek érvénybe szabályzatok. Az alkalmazás feladata, hogy értesítse az SDK-t minden alkalommal, amikor módosítani kell az identitást. Erre általában olyankor kerül sor, amikor az alkalmazás arra készül, hogy adatokat jelenítsen meg egy bizonyos felhasználói fióknak.

    Ilyen például, amikor a felhasználó megpróbál megnyitni egy dokumentumot, egy postaládát vagy egy jegyzetfüzetlapot. Az alkalmazásnak a dokumentum, postafiók vagy jegyzetfüzetlap tényleges megnyitása előtt kell értesítenie az SDK-t Ez a `IntuneMAMPolicyManager` `setUIPolicyIdentity` API-jával történik. Felügyelt és nem felügyelt felhasználó esetén egyaránt ezt az API-t kell meghívni. Ha a felhasználó felügyelt, az SDK elvégzi a feltételes indítás ellenőrzését (jailbreak-észlelés, PIN-kód, hitelesítés stb.).

    Az identitásváltás eredményét aszinkron módon, egy befejezéskezelővel adja vissza. Az alkalmazásnak egészen addig el kell halasztania a dokumentum, postaláda vagy lap megnyitását, amíg nem kap vissza sikeres eredménykódot. Ha az identitásváltás sikertelen, az alkalmazásnak vissza kell vonnia a műveletet.

* **Az SDK által kezdeményezett identitásváltás:**

    Az SDK-nak bizonyos esetekben arra kell kérnie az alkalmazást, hogy váltson át egy bizonyos identitásra. A több identitást használó alkalmazásoknak az `IntuneMAMPolicyDelegate` fejléc `identitySwitchRequired` metódusával kell ezeket a kéréseket kezelniük.

    Ha ezt a metódust meghívják, és az alkalmazás képes kezelni a megadott identitásra való átváltási kérést, akkor az `IntuneMAMAddIdentityResultSuccess` értéket kell átadnia a befejezéskezelőbe. Ha az alkalmazás nem képes kezelni az identitásváltást, akkor az `IntuneMAMAddIdentityResultFailed` értéket kell átadnia a befejezéskezelőbe.

    Az alkalmazásnak nem kell a hívásra válaszul meghívnia a `setUIPolicyIdentity` metódust. Ha az SDK-nak arra kell megkérnie az alkalmazást, hogy egy nem felügyelt felhasználói fiókra váltson, akkor az üres sztringet adja át az `identitySwitchRequired` hívásban.

* **Szelektív törlés**:

    Az alkalmazás szelektív törlésekor az SDK az `IntuneMAMPolicyDelegate` fejléc `wipeDataForAccount` metódusát hívja meg. Az alkalmazás felelős azért, hogy törölje a felhasználó fiókját és a hozzá kapcsolódó adatokat. Az SDK képes arra, hogy töröljön minden fájlt, amely a felhasználó tulajdonában van. Akkor teszi ezt, ha az alkalmazás a „FALSE” eredményt adja vissza a `wipeDataForAccount` hívásból.

    Vegye figyelembe, hogy a metódus meghívása egy háttérszálból történik. Az alkalmazás csak akkor adhat vissza értéket, ha a felhasználóhoz tartozó összes adat el lett távolítva (a fájlok kivételével, amennyiben az alkalmazás „FALSE” eredményt ad vissza).

## <a name="ios-best-practices"></a>Gyakorlati tanácsok iOS rendszerhez

Az alábbiakban néhány gyakorlati tanácsot kínálunk iOS-alapú fejlesztéshez:

* Az iOS fájlrendszere megkülönbözteti a kis-és nagybetűket. Ügyeljen a kis- és nagybetűk helyes használatára az olyan fájlneveknél, mint például a `libIntuneMAM.a` vagy az `IntuneMAMResources.bundle`.

* Ha az Xcode nem találja a `libIntuneMAM.a` könyvtárat, a probléma megoldásához vegye fel a könyvtár elérési útját a keresőútvonalakba.

## <a name="faqs"></a>GYIK

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>Az összes API címezhető natív Swift vagy Objective-C és Swift együttes használatával?

Az Intune App SDK API-k csak Objective-C nyelven érhetők el, és nem támogatják a **natív** Swiftet. A Swift Objective-C-vel való együttműködésére van szükség.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>Az alkalmazásom minden felhasználóját regisztrálni kell az APP-WE szolgáltatásban?

Nem. Valójában csak a munkahelyi vagy iskolai fiókokat kell regisztrálni az Intune App SDK-ban. Az alkalmazások feladata azt eldönteni, hogy egy fiók munkahelyi, illetve iskolai környezetben használatos-e.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>Mi a teendő azokkal a felhasználókkal, akik már bejelentkeztek az alkalmazásba? Regisztrálni kell őket?

Az alkalmazás felelős a felhasználók regisztrálásáért a sikeres hitelesítésüket követően. Szintén az alkalmazás felelős minden olyan fiók regisztrálásáért, amely már azelőtt jelen lehetett, mielőtt az alkalmazás kiegészült az MDM nélküli MAM funkcióval.

Ezt az alkalmazásnak a `registeredAccounts:` metódussal ajánlott megtennie. Ez a metódus egy NSDictionary értéket ad vissza, amely tartalmazza az Intune MAM szolgáltatásban regisztrált valamennyi fiókot. Ha nem szerepel a listában valamelyik, az alkalmazásban már meglévő fiók, akkor az alkalmazásnak regisztrálnia kell a `registerAndEnrollAccount:` metódussal.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>Milyen gyakran próbálkozik újra az SDK a regisztrációval?

Az SDK 24 órás időközönként automatikusan újrapróbálkozik minden korábban sikertelen regisztrációval. Az SDK azért teszi ezt, hogy ha egy felhasználó szervezete azután aktiválta a MAM szolgáltatást, hogy a felhasználó bejelentkezett az alkalmazásba, a felhasználó akkor is sikeresen regisztráljon, és megkapja a szabályzatokat.

Az SDK felhagy az újrapróbálkozással, ha azt észleli, hogy a felhasználó sikeresen regisztrálta az alkalmazást. Ez azért van így, mert egy adott időpontban csak egy felhasználó regisztrálhat egy alkalmazást. A felhasználó regisztrációjának visszavonása esetén újrakezdődnek az ismételt próbálkozások, ugyanolyan 24 órás időközzel.

### <a name="why-does-the-user-need-to-be-deregistered"></a>Miért kell megszüntetni a felhasználó regisztrációját?

Az SDK a következő műveleteket végzi el a háttérben, rendszeres időközönként:

* Ha az alkalmazás még nincs regisztrálva, 24 óránként megpróbál regisztrálni minden regisztrált fiókot.
* Ha az alkalmazás regisztrálva van, az SDK 8 óránként keresi meg a MAM-szabályzat esetleges frissítéseit.

A felhasználó regisztrációjának megszüntetése esetén értesíti az SDK-t arról, hogy a felhasználó nem használja tovább az alkalmazást, és hogy az SDK leállíthatja az adott felhasználói fiók esetében a rendszeres műveleteket. Az alkalmazás regisztrációjának visszavonását, és ha szükséges, az adatok szelektív törlését is kezdeményezi.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>True-ra állítsam a doWipe jelzőt a regisztrációt megszüntető metódusban?

Ezt a metódust még azelőtt kell meghívni, hogy a felhasználót kijelentkezteti az alkalmazásból.  Ha a kijelentkezés keretében törli a felhasználó adatait az alkalmazásból, akkor a `doWipe` jelző false-ra állítható. Ha viszont az alkalmazás nem törli a felhasználó adatait, akkor a `doWipe` jelzőt true-ra kell állítani, hogy az SDK törölhesse az adatokat.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>Vannak más módszerek az alkalmazások regisztrációjának megszüntetésére?

Igen, a rendszergazda szelektív törlési parancsot is küldhet az alkalmazásnak. Ezzel megszünteti és törli a felhasználó regisztrációját, és törli a felhasználó adatait is. Az SDK automatikusan kezeli ezt a helyzetet, és a regisztrációt megszüntető delegáltmetóduson keresztül küld értesítést.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>Van olyan mintaalkalmazást, amely bemutatja, hogyan kell integrálni az SDK-t?

Igen! A Microsoft nemrégiben átalakította a nyílt forráskódú mintaalkalmazást, a [Wagr for iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App) alkalmazást. A Wagr most már engedélyezve van az alkalmazásvédelmi szabályzathoz az Intune App SDK használatával.

## <a name="submit-your-app-to-the-app-store"></a>Az alkalmazás beküldése az App Store-ba

Az Intune App SDK statikus könyvtára és keretrendszere egyaránt univerzális bináris build. Ez azt jelenti, hogy az összes eszköz- és szimulátorarchitektúrához biztosítanak kódot. Az Apple elutasítja az App Store-ba beküldött alkalmazásokat, ha szimulátorkódot tartalmaznak. Ha csak eszközökön használatos buildet fordít a statikus kódtárral, a csatoló automatikusan eltávolítja a szimulátorkódot. Végezze el az alábbi lépéseket, amelyek segítségével garantáltan nem marad szimulátorkód az alkalmazásban, amikor feltölti azt az App Store-ba.

1. Ügyeljen rá, hogy az `IntuneMAM.framework` az asztalon legyen.

2. Futtassa a következő parancsokat:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    Az első parancs törli a szimulátorarchitektúrákat a keretrendszer DYLIB-fájljából. A második parancs visszamásolja a csak eszközökhöz kapcsolódó DYLIB-fájlt a keretrendszer könyvtárába.

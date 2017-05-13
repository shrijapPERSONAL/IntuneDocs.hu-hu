---
title: "Az iOS-re készült Microsoft Intune App SDK fejlesztői útmutatója | Microsoft Docs"
description: "Az iOS-re készült Microsoft Intune App SDK segítségével az Intune mobilalkalmazás-felügyeleti (MAM) funkcióját beépítheti iOS-es alkalmazásába."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df54ac3a62b5ef21e8a32f3a282dd5299974a1b0
ms.openlocfilehash: 1d2cb0d4b9442262c562e559a675f5a4a28ee572
ms.contentlocale: hu-hu
ms.lasthandoff: 05/03/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>iOS-re készült Microsoft Intune App SDK – fejlesztői útmutató

> [!NOTE]
> Célszerű először elolvasnia az [Intune App SDK bevezető dokumentumát](intune-app-sdk-get-started.md), amely ismerteti az integráció előkészítését a támogatott platformokon.

Az iOS-re készült Microsoft Intune App SDK segítségével az Intune (**APP-k** vagy **MAM-szabályzatok** néven is ismert) alkalmazásvédelmi szabályzatait beépítheti natív iOS-es alkalmazásába. MAM-kompatibilisnek az Intune App SDK-val integrált alkalmazásokat nevezzük. A rendszergazdák alkalmazásvédelmi szabályzatokat telepíthetnek a mobilalkalmazás mellé, ha azt az Intune aktívan felügyeli.

## <a name="prerequisites"></a>Előfeltételek

* Az OS X 10.8.5-ös vagy újabb, valamint az Xcode 8-as vagy újabb verziójával ellátott Mac OS-es számítógépre lesz szüksége.

* Az alkalmazásnak az iOS 9-es vagy újabb verzióját kell céloznia.

* Olvassa el az [iOS-re készült Intune App SDK licencszerződését](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Nyomtassa ki és őrizze meg a szerződés egy példányát. Az iOS-re készült Intune App SDK letöltésével és használatával Ön elfogadja a licencszerződést.  Ha nem fogadja el, ne használja a szoftvert.

* Töltse le az iOS-re készült Intune App SDK fájljait a [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)ról.

## <a name="whats-in-the-sdk"></a>Az SDK tartalma

Az iOS-re készült Intune App SDK-ban van egy statikus kódtár, erőforrásfájlok, API-fejlécek, egy, a hibakeresési beállításokat tartalmazó .plist-fájl és egy konfiguráló eszköz. A mobilalkalmazásoknak a legtöbb szabályzat betartatásához elég tartalmazni az erőforrásfájlokat és statikus módon csatolni a kódtárakat. A speciális Intune MAM-funkciók használata API-k segítségével kényszeríthető ki.

Ez az útmutató az iOS-re készült Intune App SDK alábbi összetevőinek használatát ismerteti:

* **libIntuneMAM.a**: az Intune App SDK kódtára. Ha az alkalmazása nem használ bővítményeket, akkor elég ezt a kódtárat a projekthez csatolni, és az alkalmazás együtt fog működni az Intune mobileszköz-felügyelettel.

* **IntuneMAM.framework**: az Intune App SDK keretrendszere. Ha ezt a keretrendszert a projekthez csatolja, az alkalmazás együtt fog működni az Intune mobileszköz-felügyelettel. Akkor célszerű a keretrendszert használni a statikus kódtár helyett, ha az alkalmazás bővítményeket használ, mert így a projekt nem készít több másolatot a statikus kódtárból.

* **IntuneMAMResources.Bundle**: az SDK által használt erőforrásokat tartalmazó csomag.

* **Headers**: az Intune App SDK API-jait elérhetővé tevő fejlécek. Ha API-t használ, meg kell adnia az API-t tartalmazó fejlécfájlt. Az alábbi fejlécekben megtalálhatók az Intune App SDK funkcióinak engedélyezéséhez szükséges API-függvényhívások:

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Az Intune App SDK működése

Az iOS-re készült Intune App SDK révén minimális kódmódosítással adhat hozzá felügyeleti funkciókat az iOS-alkalmazásokhoz. A kevesebb kódmódosítás gyorsabb piacra dobhatóságot jelent, ráadásul kisebb mértékben érinti az alkalmazás konzisztenciáját és stabilitását.


## <a name="build-the-sdk-into-your-mobile-app"></a>Az SDK beépítése mobilalkalmazásokba

Az Intune App SDK az alábbi lépésekkel engedélyezhető:

1. **1. lehetőség (ajánlott)**: Csatolja a `IntuneMAM.framework` keretrendszert a projektjéhez. Húzza a `IntuneMAM.framework` keretrendszert a projekthez használni kívánt elemek **Linked Frameworks and Libraries** (Csatolt keretrendszerek és könyvtárak) listájába.

    > [!NOTE]
    > Ha a keretrendszert használja, az alkalmazás App Store-ba való beküldése előtt manuálisan kell eltávolítania a szimulátorarchitektúrákat az univerzális keretrendszerből. További részleteket [Az alkalmazás beküldése az App Store-ba](#Submit-your-app-to-the-App-Store) című szakaszban talál.

2. **2. lehetőség**: a `libIntuneMAM.a` kódtár csatolása. Húzza a `libIntuneMAM.a` kódtárat a projekthez használni kívánt elemek **Linked Frameworks and Libraries** (Csatolt keretrendszerek és könyvtárak) listájába.

    ![Intune App SDK (iOS): csatolt keretrendszerek és könyvtárak](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Ha az alkalmazást szeretné közzétenni az App Store-ban, a `libIntuneMAM.a` végleges verzióját használja a hibakeresési verzió helyett. A végleges verziót a **release** mappában találja. A hibakeresési verzió részletes kimenettel segíti az Intune App SDK-val kapcsolatos hibakeresést.

    Illessze be a `-force_load {PATH_TO_LIB}/libIntuneMAM.a` sort az alábbiak valamelyikébe (a `{PATH_TO_LIB}` helyére az Intune App SDK elérési útja kerüljön):
      * a projekt `OTHER_LDFLAGS` buildkonfigurációs beállítása
      * a felhasználói felület **Other Linker Flags** (Más csatoló jelzők) területe

        > [!NOTE]
        > A `PATH_TO_LIB` értékét a `libIntuneMAM.a` fájl kijelölése után a **Fájl** menü **Adatok lekérése** parancsával kaphatja meg. Másolja ki az **Info** (Információ) lap **General** (Általános) szakaszában látható **Where** (Hely) adatot (az elérési utat).

3. Vegye fel ezeket az iOS-es keretrendszereket a projektbe:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. Vegye fel a projektbe az `IntuneMAMResources.bundle` erőforrás-csomagot a **Build Phases** (Buildelési fázisok) területen lévő **Copy Bundle Resources** (Erőforrás-csomagok másolása) elem alá.

    ![Intune App SDK (iOS): erőforrás-csomagok másolása](../media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Ha a mobilalkalmazás fő nib vagy storyboard fájlt definiál az Info.plist fájlban, vágja ki a **Main Storyboard** vagy a **Main Nib** mező(k) értékét. Illessze be az Info.plist fájlba ezeket a mezőket és értékeket egy **IntuneMAMSettings** nevű új szótár alatt, a következő kulcsnevekkel:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Ha a mobilalkalmazás nem definiál fő nib vagy storyboard fájlt az Info.plist fájlban, ezek a beállítások nem szükségesek.

    Az Info.plist fájlt nyers formátumban megtekintve láthatja a kulcsneveket. Kattintson jobb gombbal a dokumentum törzsében bárhol, és válassza a **Show Raw Keys/Values** (Nyers kulcsok/értékek megjelenítése) nézetet.

6. Engedélyezze a kulcsláncmegosztást (ha még nincs engedélyezve): a projekthez használni kívánt elemeken kattintson a **Capabilities** (Képességek) lehetőségre, majd kapcsolja be a **Keychain Sharing** (Kulcsláncmegosztás) kapcsolót. A kulcsláncmegosztás a következő lépéshez szükséges.

  > [!NOTE]
    > A kiépítési profil esetében elengedhetetlen az új kulcsláncmegosztási értékek támogatása. A kulcslánc-hozzáférési csoportoknak támogatniuk kell a helyettesítő karaktert. Ezt a .mobileprovision fájl szövegszerkesztőben való megnyitásával ellenőrizheti, rákeresve a **keychain-access-groups** (kulcslánc-hozzáférési csoportok) kifejezésre. Itt meggyőződhet a helyettesítő karakter létéről. Példa:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Miután engedélyezte a kulcsláncmegosztást, az alábbi lépéseket követve létrehozhat egy különálló hozzáférési csoportot, amelyben az Intune App SDK adatait tárolhatja. Kulcslánc-hozzáférési csoportot a felhasználói felületen vagy a jogosultságfájllal hozhat létre. Ha a felhasználói felületen hozzá létre a kulcslánc-hozzáférési csoportot, mindenképpen az alábbi lépések szerint járjon el:

    1. Ha a mobilalkalmazásban nincs definiálva kulcslánc-hozzáférési csoport, első csoportként vegye fel az alkalmazás csomagazonosítóját.

    2. Vegye fel a `com.microsoft.intune.mam` nevű közös kulcslánccsoportot a korábban létrehozott hozzáférési csoportok közé. Az Intune App SDK ezt a hozzáférési csoportot használja adatok tárolására.

    3. Vegye fel a `com.microsoft.adalcache` csoportot a korábban létrehozott hozzáférési csoportok közé.

        4. Vegye fel a `com.microsoft.workplacejoin` csoportot a korábban létrehozott hozzáférési csoportok közé.
            ![Intune App SDK (iOS): kulcsláncok megosztása](../media/intune-app-sdk-ios-keychain-sharing.png)

      5. Ha a jogosultságfájllal hozza létre a kulcslánc-hozzáférési csoportot, az `$(AppIdentifierPrefix)` előtaggal együtt illessze be a kulcslánc-hozzáférési csoportot a jogosultságfájlba. Példa:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > A jogosultságfájl egy, az Ön mobilalkalmazásához tartozó egyedi XML-fájl, amely az iOS-es alkalmazás speciális engedélyeinek és képességeinek megadására szolgál.

7. Ha az alkalmazás definiál URL-sémákat az Info.plist fájlban, mindegyikhez vegyen fel új sémát az `-intunemam` utótaggal együtt.

8. Az iOS 9-es vagy újabb verziójára fejlesztett mobilalkalmazások esetében az alkalmazás Info.plist fájljának `LSApplicationQueriesSchemes` tömbjében szerepelnie kell minden olyan protokollnak, amelyet az alkalmazás átad a `UIApplication canOpenURL` függvénynek. A felsorolt összes protokollhoz vegyen fel egy újabbat a `-intunemam` utótaggal. A tömbben szerepelnie kell továbbá a `http-intunemam`, `https-intunemam` és `ms-outlook-intunemam` elemeknek is.

9. Ha az alkalmazás a jogosultságfájljában definiál alkalmazáscsoportokat, vegye fel ezeket karakterlánctömbként az **IntuneMAMSettings** szótárban az `AppGroupIdentifiers` kulcs alá.



## <a name="configure-azure-active-directory-authentication-library-adal"></a>Az Azure Directory Authentication Library (ADAL) konfigurálása

Az Intune App SDK az [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) kódtárat használja a hitelesítési és feltételes indítási műveletekhez. Az ADAL-ra támaszkodik a felhasználói identitások MAM-regisztrációjánál is az eszközbeléptetés nélküli felügyeleti megoldásokban.

Az ADAL használata során az alkalmazásnak kiadott jogkivonatok biztonsága érdekében az alkalmazások használata legtöbbször Azure Active Directory- (AAD-) regisztrációhoz, egyedi azonosítóhoz (más néven ügyfél-azonosítóhoz) és egyéb azonosítókhoz kötött. Ha másként nincs feltüntetve, az Intune App SDK az alapértelmezett regisztrációs értékeket használja az Azure AD-hez való kapcsolódáskor.  

Ha az alkalmazás már most is az ADAL-lal hitelesíti a felhasználókat, akkor az Intune App SDK alapértelmezett értékeit felül kell írni a jelenlegi regisztrációs értékekkel. Így biztosítható, hogy a felhasználóknak ne kelljen kétszer hitelesíteniük magukat (egyszer az Intune App SDK-ban, egyszer pedig az alkalmazásban).

### <a name="recommendations"></a>Ajánlások

Az alkalmazásnak célszerű [az ADAL fő ágon lévő legfrissebb verzióját](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) csatolni. Az Intune App SDK jelenleg az ADAL brókeres ágával támogatja a feltételes hozzáférést megkövetelő alkalmazásokat, amelyekhez ennélfogva szükséges a Microsoft Authenticator alkalmazás. Az SDK ennek ellenére kompatibilis az ADAL fő ágával, így Ön az alkalmazásának megfelelő ágat használhatja.

### <a name="link-to-adal-binaries"></a>ADAL-programfájlok csatolása

Alkalmazásában az alábbi lépésekkel csatolhatja az ADAL programfájljait:

1. Töltse le az [Azure Active Directory Authentication Library (ADAL) Objective-C nyelvhez készült verzióját](https://github.com/AzureAD/azure-activedirectory-library-for-objc) a GitHubról, majd az [útmutatás](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) alapján töltse le az ADAL-t Git-almodulokkal vagy a CocoaPodsszal.

2. Vegye fel a projektbe az `ADALiOSBundle.bundle` erőforrás-csomagot a **Build Phases** (Buildelési fázisok) területen lévő **Copy Bundle Resources** (Erőforrás-csomagok másolása) elem alá.

3. Írja be a `-force_load {PATH_TO_LIB}/libADALiOS.a` utasítást a projekt `OTHER_LDFLAGS` build-konfigurációs beállításába vagy az **Other Linker Flags** (Más csatoló jelzők) helyre a felhasználói felületen. A `PATH_TO_LIB` helyett adja meg az ADAL-programfájlok helyét.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Az ADAL jogkivonat-gyorsítótárának megosztása más, ugyanazon kiépítési profillal aláírt alkalmazásokkal?**

Ha az ADAL jogkivonat-gyorsítótárát meg szeretné osztani az ugyanazon kiépítési profillal aláírt alkalmazások között, kövesse az alábbi útmutatást:

1. Ha a mobilalkalmazásban nincs definiálva kulcslánc-hozzáférési csoport, első csoportként vegye fel az alkalmazás csomagazonosítóját.

2. A `com.microsoft.adalcache` és `com.microsoft.workplacejoin` hozzáférési csoportokat a kulcslánc-jogosultságok közé felvéve engedélyezze az ADAL-os egyszeri bejelentkezést.

3. Ha konkrétan meghatározza az ADAL közös gyorsítótárhoz használatos kulcslánccsoportját, akkor az `<app_id_prefix>.com.microsoft.adalcache` érték legyen beállítva. Az ADAL ezt automatikusan beállítja, ha Ön nem bírálja felül. Ha a `com.microsoft.adalcache` helyett egyéni kulcslánccsoportot szeretne megadni, az Info.plist fájl IntuneMAMSettings szakaszában, az `ADALCacheKeychainGroupOverride` kulccsal teheti meg.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>ADAL-beállítások konfigurálása az Intune App SDK-hoz

Ha az alkalmazás már az ADAL-t használja hitelesítésre, és megvannak a saját ADAL-beállításai, akkor kikényszerítheti, hogy az Intune App SDK ugyanazokat a beállításokat használja az Azure Active Directoryval való hitelesítéskor. Így lehet biztosítani, hogy az alkalmazás ne kérje kétszer is hitelesítésre a felhasználót. Az alábbi beállítások feltöltésével kapcsolatban [Az Intune App SDK beállításainak konfigurálása](#configure-settings-for-the-intune-app-sdk) című szakasz nyújt tájékoztatást:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Ha az alkalmazás már az ADAL-t használja, a következő konfigurációs lépéseket kell végrehajtani:

1. A projekt Info.plist fájljában az **IntuneMAMSettings** szótár alatt található `ADALClientId` nevű kulcsban adja meg az ADAL-hívásokhoz használható ügyfél-azonosítót.

2. Szintén az **IntuneMAMSettings** szótár alatt az `ADALAuthority` nevű kulcsban adja meg az Azure AD-szolgáltatót.

3. Szintén az **IntuneMAMSettings** szótár alatt az `ADALRedirectUri` nevű kulcsban adja meg az ADAL-hívásokhoz használható átirányítási URI-t. Az alkalmazás átirányítási URI-formátumától függően előfordulhat, hogy az `ADALRedirectScheme` sémát is meg kell adnia.


Az Azure AD-szolgáltató URL-jét futásidőben is felülbírálhatja egy bérlőspecifikus URL-lel. Ehhez elegendő az `aadAuthorityUriOverride` tulajdonságot beállítani az `IntuneMAMPolicyManager` példányon.

> [!NOTE]
> [Alkalmazásvédelmi szabályzat eszközbeléptetés nélküli használatakor](#App-protection-policy-without-device-enrollment) kötelező megadni az AAD-szolgáltató URL-jét, hogy az SDK is felhasználhassa az alkalmazás által lekért ADAL-os frissítési jogkivonatot.

Az SDK ezt a szolgáltatói URL-t fogja használni a szabályzatfrissítésekhez és a további beléptetési kérésekhez, amíg nem törlik vagy módosítják az értéket.  Ezért fontos az értéket törölni a felügyelt felhasználók alkalmazásból való kijelentkezésekor, és átállítani másik felügyelt felhasználó bejelentkezésekor.

### <a name="if-your-app-does-not-use-adal"></a>Ha az alkalmazás nem az ADAL-t használja

Ha az alkalmazás nem az ADAL-t használja, az Intune App SDK szolgáltatja az ADAL-paraméterek alapértelmezett értékeit, és kezeli az Azure AD-val való hitelesítést. Önnek nem kell semmilyen értéket megadnia a fent felsorolt ADAL-beállításokhoz.

## <a name="app-protection-policy-without-device-enrollment"></a>Alkalmazásvédelmi szabályzat használata eszközbeléptetés nélkül

### <a name="overview"></a>Áttekintés
Az Intune-os alkalmazásvédelmi szabályzat eszközbeléptetés nélküli használata (amelyet az **APP-WE** vagy MAM-WE betűszóval is jelölnek) révén az Intune anélkül is képes felügyelni az alkalmazásokat, hogy az eszközt be kellene léptetni a mobileszköz-felügyeletbe (MDM). Ez az új funkció csak akkor használható, ha az alkalmazás képes a felhasználói fiókokat regisztrálni a felügyelet alá. Az új API-kat a következő lépésekkel veheti használatba:

1. Az Intune App SDK legújabb verzióját használja, amelyben az alkalmazásfelügyelet eszközbeléptetéssel és anélkül is elérhető.

2. Vegye fel az IntuneMAMEnrollment.h fejlécet az összes olyan fájlba, amelyik API-kat fog hívni.

### <a name="register-user-accounts"></a>Felhasználói fiókok regisztrálása

Az alkalmazások akkor kaphatnak alkalmazásvédelmi szabályzatot az Intune szolgáltatástól, ha egy konkrét felhasználói fiók nevében lesznek beléptetve az APP-WE szolgáltatásban. Az alkalmazás feladata, hogy az újonnan bejelentkező felhasználókat regisztrálja az SDK-ban. Az új felhasználói fiók hitelesítése után az alkalmazásnak meg kell hívnia a Headers/IntuneMAMEnrollment.h fejlécben lévő `registerAndEnrollAccount` metódust:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
A `registerAndEnrollAccount` metódus meghívásával az SDK regisztrálja a felhasználói fiókot, és megkísérli az alkalmazást az adott fiók nevében beléptetni. Ha ez valamilyen okból meghiúsul, az SDK 24 órával később automatikusan újból próbálkozik a beléptetéssel. Az alkalmazás hibakeresési célból egy delegálton keresztül értesítéseket fogadhat a beléptetési kérések eredményéről.

Miután az API meg lett hívva, az alkalmazás a szokott módon működhet tovább. Sikeres beléptetés esetén az SDK értesíti a felhasználót, hogy az alkalmazást újra kell indítani. A felhasználónak erre azonnal lehetősége is nyílik.

### <a name="deregister-user-accounts"></a>Felhasználói fiókok regisztrációjának törlése

Mielőtt a felhasználó kijelentkezne az alkalmazásból, az alkalmazásnak törölnie kell az SDK-ból a felhasználó regisztrációját. Ez biztosítja az alábbiakat:

1. A rendszer a későbbiekben ne próbálkozzon újra a felhasználói fiók beléptetésével.

2. Az alkalmazásvédelmi szabályzat el legyen távolítva.

3. A vállalati adatok törlődjenek, ha az alkalmazás szelektív törlést kezdeményez (ami nem kötelező).

A felhasználó kijelentkezése előtt az alkalmazásnak meg kell hívnia a következő API-t a `Headers/IntuneMAMEnrollment.h` fejlécben:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

A metódust a felhasználói fiók Azure AD-jogkivonatainak törlése előtt kell meghívni. Az SDK csak a fiók AAD-jogkivonata(i) alapján tud bizonyos kéréseket a felhasználó nevében elküldeni az APP-WE szolgáltatásnak.

Ha az alkalmazás önállóan fogja törölni a felhasználó céges adatait, a `doWipe` jelzőt false értékre lehet állítani. Egyéb esetben az alkalmazás az SDK-val is elvégeztetheti a szelektív törlést. Ilyenkor az alkalmazás szelektív törlési delegáltja lesz meghívva.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>Nem az ADAL-t használó alkalmazások

A felhasználókat nem az ADAL-lal bejelentkeztető alkalmazások is kaphatnak alkalmazásvédelmi szabályzatot az Intune szolgáltatástól, ha az API-t meghívva az SDK-val kezeltetik a hitelesítést. Akkor célszerű ezt a technikát használni, ha az alkalmazás nem hitelesített felhasználót az Azure AD-ban, de az adatok védelme érdekében szüksége van alkalmazásvédelmi szabályzatra. Ilyen eset lehet, ha az alkalmazás másik szolgáltatással kezeli vagy egyáltalán nem támogatja a bejelentkezést. Az alkalmazásnak ilyenkor a Headers/IntuneMAMEnrollment.h fejlécben lévő `loginAndEnrollAccount` metódust kell meghívnia:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Ezt a metódust meghívva az SDK bekéri a felhasználói hitelesítő adatokat, ha nem talál korábbi jogkivonatot. Ezután megpróbálja az alkalmazást a megadott felhasználói fiók nevében beléptetni az APP-WE szolgáltatásba. A metódus meghívható a „nil” identitásértékkel is. Ebben az esetben az SDK az eszköz jelenlegi felügyelt felhasználójával végzi el a beléptetést, vagy ha nincs ilyen, akkor bekéri a felhasználónevet.

Ha a beléptetés sikertelen, az alkalmazásnak célszerű a hiba természetétől függően később újra meghívnia ezt az API-t. Az alkalmazás egy delegálton keresztül [értesítéseket](#Status-result-and-debug-notifications) fogadhat a beléptetési kérések eredményéről.

Miután az API meg lett hívva, az alkalmazás a szokott módon működhet tovább. Sikeres beléptetés esetén az SDK értesíti a felhasználót, hogy az alkalmazást újra kell indítani.

## <a name="status-result-and-debug-notifications"></a>Hibakeresési, állapot- és eredményértesítések

Az alkalmazás hibakeresési, állapot- és eredményértesítéseket fogadhat az Intune szolgáltatáshoz intézett alábbi kérésekkel kapcsolatban:

 - Beléptetési kérések
 - Szabályzatmódosítási kérések
 - Beléptetés-visszavonási kérések

Az értesítéseket a `Headers/IntuneMAMEnrollmentDelegate.h` fejléc delegált metódusai szolgáltatják:

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

A delegált metódusok egy, az alábbi információkat tartalmazó `IntuneMAMEnrollmentStatus` objektumot adnak vissza:

- a kéréshez tartozó fiók identitása
- a kérés eredményét jelző állapotkód
- az állapotkód leírását tartalmazó hibaüzenet
- egy `NSError` objektum

Ez az objektum az `IntuneMAMEnrollmentStatus.h` fejlécben van definiálva az egyes visszaadható állapotkódokkal együtt.


### <a name="sample-code"></a>Kódminta

A delegált metódusok implementálására mutatunk be példákat:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Alkalmazás újraindítása

Amikor egy alkalmazás először kap alkalmazásvédelmi szabályzatokat, akkor a beavatkozási pontok érvénybe lépéséhez újra kell indítani. Az alkalmazást a Headers/IntuneMAMPolicyDelegate.h fejlécben található delegált metódussal lehet értesíteni róla, hogy újraindításra van szükség.

```objc
 - (BOOL) restartApplication
```
A metódus visszatérési értéke jelzi az SDK-nak, hogy az alkalmazásnak kell-e kezelnie az újraindítást:   

 - „True” érték esetén az alkalmazásnak kell kezelnie az újraindítást.   

 - „False” érték esetén a metódus visszatérése után az SDK indítja újra az alkalmazást. Az SDK azonnal megjeleníti a felhasználónak az újraindítást kérő párbeszédpanelt.

## <a name="customize-your-apps-behavior"></a>Az alkalmazás működésének testreszabása

Az Intune App SDK-ban számos API olyan van, amelyeket meghívva információt lehet szerezni az alkalmazáshoz telepített alkalmazásvédelmi szabályzatról. Ezen adatok alapján testre szabhatja az alkalmazás működését. Az alkalmazásvédelmi szabályzatok legtöbb beállítását az SDK tartatja be, nem az alkalmazás. A Save-as (Mentés másként) vezérlő az egyetlen, amelyet célszerű az alkalmazásban implementálni.

### <a name="get-app-protection-policy"></a>Alkalmazásvédelmi házirend beszerzése

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
Az IntuneMAMPolicyManager osztály az alkalmazáshoz telepített Intune-os alkalmazásvédelmi szabályzatot teszi elérhetővé, egyebek között a [Több identitás használatának lehetővé tételéhez](#-enable-multi-identity-optional) hasznos API-kat.

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
Az IntuneMAMPolicy osztály az alkalmazáshoz telepített Intune-os alkalmazásvédelmi szabályzatot teszi elérhetővé. Az ezen osztályban szereplő szabályzatbeállításokat az SDK tartatja be, de az alkalmazás működése a betartatás mikéntje alapján bármikor testre szabható.

Ez az osztály tesz elérhetővé bizonyos, a „mentés másként” vezérlők implementálásához szükséges API-kat is (erről bővebben a következő szakaszban olvashat).

### <a name="implement-save-as-controls"></a>„Mentés másként” vezérlők implementálása

Az Intune révén a rendszergazdák megszabhatják, hogy egy felügyelt alkalmazás mely tárhelyekre menthet adatokat. Az alkalmazások az **IntuneMAMPolicy.h** fejlécben definiált **isSaveToAllowedForLocation** API-val kérdezhetik le az Intune App SDK-tól az engedélyezett tárhelyeket.

Mielőtt az alkalmazás felügyelt adatokat menthetne valamilyen felhőbeli vagy helyi tárhelyre, az **isSaveToAllowedForLocation** API-val ellenőriznie kell, hogy a rendszergazda engedélyezte-e az oda történő mentést.

Az alkalmazásoknak az **isSaveToAllowedForLocation** API használatakor át kell adniuk a tárhelyhez tartozó egyszerű felhasználónevet, ha az rendelkezésre áll.

#### <a name="supported-save-locations"></a>Támogatott mentési helyek

Az **isSaveToAllowedForLocation** API konstansaival lehet lekérdezni, hogy a rendszergazda engedélyezte-e az alábbi, az IntuneMAMPolicy.h fejlécben definiált helyekre történő mentést:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Az alkalmazásoknak a **isSaveToAllowedForLocation** API konstansaival ajánlott ellenőrizniük, hogy az adatokat menthetik-e „felügyelt” helyekre (pl. Vállalati OneDrive), vagy „személyesekre”. Ugyanezt az API-t kell használni akkor is, ha az alkalmazás nem tudja eldönteni, hogy egy adott hely „felügyelt” vagy „személyes”-e.

A „személyes” besorolású helyeket az `IntuneMAMSaveLocationOther` konstans jelképezi.

A `IntuneMAMSaveLocationLocalDrive` konstanst kell használni minden olyan esetben, amikor az alkalmazás a helyi eszköz valamely meghajtójára ment adatokat.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Az Intune App SDK beállításainak konfigurálása

Az alkalmazás Info.plist fájljában található **IntuneMAMSettings** szótár az Intune App SDK beállítására és konfigurálására szolgál. Ha az IntuneMAMSettings szótár nem látható az Info.plist fájlban, hozzon létre a fájlban ilyen mezőnevű szótárt.

Az IntuneMAMSettings szótár alatt veheti fel az SDK konfigurálására szolgáló kulcs/érték sorokat. Az alábbi táblázatban az összes támogatott beállítás megtalálható.

Néhány beállításról már volt szó korábbi szakaszokban, néhány pedig nem vonatkozik minden alkalmazásra.

Beállítás  | Típus  | Meghatározás | Kötelező?
--       |  --   |   --       |  --
ADALClientId  | Karakterlánc  | Az alkalmazás Azure AD-beli ügyfél-azonosítója. | ADAL-t használó alkalmazásoknak kötelező. |
ADALAuthority | Karakterlánc | Az alkalmazás által használt Azure AD-szolgáltató. Azt a saját környezetét adja meg, amelyben az AAD-fiókokat konfigurálták. | ADAL-t használó alkalmazásoknak kötelező. Ha az érték nincs megadva, az Intune a saját alapértelmezését használja.|
ADALRedirectUri  | Karakterlánc  | Az alkalmazás Azure AD-beli átirányítási URI-ja. | Az ADAL-t használó alkalmazásoknak az ADALRedirectUri vagy az ADALRedirectScheme kötelező.  |
ADALRedirectScheme  | Karakterlánc  | Az alkalmazás Azure AD-beli átirányítási sémája. Használható az ADALRedirectUri helyett, ha az alkalmazás átirányítási URI-ja `scheme://bundle_id` formátumú. | Az ADAL-t használó alkalmazásoknak az ADALRedirectUri vagy az ADALRedirectScheme kötelező. |
ADALLogOverrideDisabled | Logikai  | Azt adja meg, hogy az SDK átirányítsa-e az összes ADAL-naplófájlt (beleértve az alkalmazásból eredő esetleges ADAL-hívásokat) a saját naplófájljába. Az alapértelmezett érték a Nem. Állítsa be az Igen értéket, ha az alkalmazás visszahívja a saját ADAL-naplóját. | Nem kötelező. |
ADALCacheKeychainGroupOverride | Karakterlánc  | Az ADAL-gyorsítótárhoz a „com.microsoft.adalcache” helyett használandó kulcslánccsoportot adja meg. Fontos, hogy nem kell megadni az „app-id” előtagot, az futásidőben kerül a megadott karakterlánc elé. | Nem kötelező. |
AppGroupIdentifiers | Karakterlánctömb  | Az alkalmazáscsoportok tömbje az alkalmazás jogosultságainak com.apple.security.application-groups szakaszában. | Szükséges, ha az alkalmazás alkalmazáscsoportokat használ. |
ContainingAppBundleId | Karakterlánc | A bővítményt tartalmazó alkalmazás kötegazonosítóját adja meg. | IOS-bővítményekhez szükséges. |
DebugSettingsEnabled| Logikai | Igen érték esetén a Settings (Beállítások) köteg tesztcélú szabályzatai is alkalmazhatók. Az alkalmazásokat *nem* szabad ezt a beállítást bekapcsolva forgalomba hozni. | Nem kötelező. |
MainNibFile<br>MainNibFile~ipad  | Karakterlánc  | Ebben a beállításban lehet megadni az alkalmazás fő nib-fájljának nevét.  | Kötelező, ha az alkalmazás definiálja a MainNibFile-t az Info.plist-ben. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Karakterlánc  | Ebben a beállításban lehet megadni az alkalmazás fő storyboard-fájljának nevét. | Kötelező, ha az alkalmazás definiálja a UIMainStoryboardFile-t az Info.plist-ben. |
MAMPolicyRequired| Logikai| Itt adhatja meg, hogy az alkalmazás indítása Intune-os alkalmazásvédelmi szabályzat hiányában le legyen-e tiltva. Az alapértelmezett érték a Nem. <br><br> Megjegyzés: az alkalmazást nem lehet beküldeni az App Store-ba, ha a MAMPolicyRequired beállítás értéke Igen. | Nem kötelező. |
MAMPolicyWarnAbsent | Logikai| Itt adhatja meg, hogy az alkalmazás indításakor jelenjen-e meg figyelmeztetés, ha nincs Intune-os alkalmazásvédelmi szabályzata. Fontos, hogy az alkalmazást nem lehet beküldeni az App Store-ba, ha a beállítás értéke Igen. | Nem kötelező. |
MultiIdentity | Logikai| Azt adja meg, hogy az alkalmazás tud-e több identitást kezelni. | Nem kötelező. |
SplashIconFile <br>SplashIconFile~ipad | Karakterlánc  | Az Intune kezdőképének ikonfájlját adja meg. | Nem kötelező. |
SplashDuration | Szám | Az Intune-kezdőkép megjelenésének minimális időtartama (másodpercben) az alkalmazás indításakor. Az alapértelmezett érték 1.5. | Nem kötelező. |
BackgroundColor| Karakterlánc| Az indító- és a PIN-kód megadására szolgáló képernyők háttérszíne. #XXXXXX formátumú hexadecimális RGB karakterláncként adható meg, ahol az X értéke 0–9 vagy A–F között lehet. A kettős keresztet el lehet hagyni.   | Nem kötelező. Alapértelmezés szerint világosszürke. |
ForegroundColor| Karakterlánc| Az indító- és a PIN-kód megadására szolgáló képernyők előtérszíne (pl. a szöveg színe). #XXXXXX formátumú hexadecimális RGB karakterláncként adható meg, ahol az X értéke 0–9 vagy A–F között lehet. A kettős keresztet el lehet hagyni.  | Nem kötelező. Alapértelmezés szerint fekete. |
AccentColor | Karakterlánc| A PIN-kód megadására szolgáló képernyő témaszíne (pl. a gombok szövegének és a kiemelt mezőknek a színe). #XXXXXX formátumú hexadecimális RGB karakterláncként adható meg, ahol az X értéke 0–9 vagy A–F között lehet. A kettős keresztet el lehet hagyni.| Nem kötelező. Alapértelmezés szerint a rendszer kék színe. |
MAMTelemetryDisabled| Logikai| Ezzel adható meg, hogy az SDK ne küldjön telemetrikus adatokat a háttérkiszolgálónak.| Nem kötelező. |

> [!NOTE]
> Ha az alkalmazás az App Store-ban fog megjelenni, a `MAMPolicyRequired` beállítást az App Store előírásainak megfelelően Nem értékre kell állítani.

## <a name="telemetry"></a>Telemetria

Az iOS-re készült Intune App SDK alapértelmezés szerint az alábbi eseményekhez tartozó telemetrikus adatokat naplózza. Az adatokat az SDK a Microsoft Intune-nak küldi el.

* **Az alkalmazások indítása:** a Microsoft Intune így felügyeleti típusok (MAM+MDM, MAM MDM-beléptetés nélkül stb.) szerinti bontásban tájékozódhat a MAM-kompatibilis alkalmazások használatáról.

* **Beléptetési hívások:** a Microsoft Intune így tájékozódhat az ügyféloldalon kezdeményezett beléptetési hívások sikerességi arányról és más teljesítménymutatóiról.

> [!NOTE]
> Ha nem kíván az Intune App SDK-ból származó telemetrikus adatokat küldeni a Microsoft Intune-nak a mobilalkalmazásról, le kell tiltania az Intune App SDK-ban a telemetria-rögzítést. Ehhez állítsa a `MAMTelemetryDisabled` tulajdonságot Igen értékre az IntuneMAMSettings szótárban.

## <a name="enable-multi-identity-optional"></a>Több identitás használatának lehetővé tétele (nem kötelező)

Alapértelmezés szerint az SDK az alkalmazás egészére alkalmazza a szabályzatokat. A „több identitás használata” nevű MAM-funkcióval a szabályzatok az identitások szintjén alkalmazhatók. Ez a többi MAM-funkciónál nagyobb mértékű közreműködést igényel az alkalmazástól.

Az alkalmazásnak tájékoztatnia kell az SDK-t, amikor módosítani szándékozik az aktív identitást. Az SDK is értesíti az alkalmazást, ha identitásváltásra van szükség. Jelenleg csak egy felügyelt identitás támogatott. Miután a felhasználó belépteti az eszközt vagy az alkalmazást, az SDK ezt az identitást használja és tekinti elsődleges felügyelt identitásnak. Az alkalmazás többi felhasználója nem lesz felügyelt, és nem korlátozzák őket a szabályzatok.

Fontos tudni, hogy az identitást egyszerűen karakterláncként lehet definiálni. Az identitásokban a kis- és nagybetűk különbözőnek számítanak. Előfordulhat, hogy az SDK-nak küldött identitáskérések válaszaiban nem ugyanaz a betűállás szerepel, amellyel az identitás be lett állítva.

### <a name="identity-overview"></a>Az identitások áttekintése

Az identitás egyszerűen egy fiók felhasználóneve (például user@contoso.com). A fejlesztők a következő szinteken adhatják meg az alkalmazáshoz tartozó identitást:

* **Folyamat identitása:** folyamatszinten állítja be az identitást, főleg az egy identitást használó alkalmazásokhoz használatos. Ez az identitás kapcsolódik minden feladathoz, fájlhoz és felhasználói felülethez.

* **Felhasználói felület identitása:** itt lehet megadni, hogy milyen szabályzatok legyenek érvényesek a fő szálon futó, a felhasználói felületen kezdeményezett feladatokra (például kivágás/másolás/beillesztés, PIN-kód megadása, hitelesítés, adatmegosztás). A felhasználói felület identitása nem kapcsolódik a fájlokkal végzett feladatokhoz (például titkosítás, biztonsági mentés).

* **Szál identitása**: itt lehet megadni, hogy milyen szabályzatok legyenek érvényesek az aktuális szálra. Ez az identitás kapcsolódik minden feladathoz, fájlhoz és felhasználói felülethez.

Az identitások megfelelő beállítása az alkalmazás feladata attól függetlenül, hogy felügyelt-e a felhasználó vagy sem.

Minden szálnak minden pillanatban van effektív identitása a felhasználói felületen kezdeményezett és a fájlokkal végzett feladatokhoz is. Ezen identitás alapján lehet ellenőrizni, hogy alkalmazandó-e bármilyen szabályzat. Ha az identitás értéke „no identity” („nincs identitás”), vagy a felhasználó nem felügyelt, akkor a rendszer semmilyen szabályzatot nem alkalmaz. Az alábbi ábrák mutatják be az effektív identitások meghatározási folyamatát.

  ![Intune App SDK (iOS): csatolt keretrendszerek és könyvtárak](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>Szálak várólistái

Az alkalmazások gyakran küldenek szinkron és aszinkron feladatokat a szálak várólistáiba. Az SDK elfogja a Grand Central Dispatch- (GCD-) hívásokat, és a szál aktuális identitását társítja a kiosztott feladatokhoz. A feladatok befejezésekor az SDK átmenetileg a feladatokhoz társított identitásra módosítja a szál identitását, befejezi a feladatokat, majd visszaállítja a szál eredeti identitását.


Mivel az `NSOperationQueue` a GCD-re épül, az `NSOperations` a szálnak azzal az identitásával fog futni, amely a feladatok `NSOperationQueue` várólistához adásakor volt aktuális. Az `NSOperations` és a közvetlenül a GCD-n keresztül kiosztott függvények futás közben módosítani is tudják a szál aktuális identitását, felülbírálva a kiosztó száltól örökölt identitást.

### <a name="file-owner"></a>Fájltulajdonos

Az SDK nyomon követi a helyi fájlok tulajdonosainak identitását, és ennek megfelelően alkalmazza a szabályzatokat. A fájltulajdonos a fájl létrejöttekor vagy felülírási (truncate) módban való megnyitásakor jelölődik ki, a feladatot végrehajtó szálnak a fájlokkal kapcsolatos feladatokhoz tartozó effektív identitása lesz az.

Az alkalmazások explicite is megadhatják a tulajdonost az `IntuneMAMFilePolicyManager` metódussal. Az `IntuneMAMFilePolicyManager` révén meg a fájl tartalmának megjelenítése előtt lekérhető a fájltulajdonos és beállítható a felhasználói felület identitása.

### <a name="shared-data"></a>Megosztott adatok

Ha az alkalmazás olyan fájlokat hoz létre, amelyekben egyaránt szerepelnek felügyelt és nem felügyelt felhasználóktól származó adatok, akkor az alkalmazás feladata a felügyelt felhasználó adatainak titkosítása. Ez a `IntuneMAMDataProtectionManager` fejléc `protect` és `unprotect` API-jaival végezhető el.

A `protect` metódus felügyelt és nem felügyelt felhasználó identitását is elfogadja. A felügyelt felhasználó adatai titkosítva lesznek, a nem felügyelt felhasználó adatai pedig egy, az identitást kódoló fejlécet kapnak, de maguk nem titkosítódnak. Az adatok tulajdonosát a `protectionInfo` metódussal lehet lekérni.

### <a name="share-extensions"></a>Megosztási bővítmények

Ha az alkalmazásnak megosztási bővítménye van, a megosztott elem tulajdonosát az `protectionInfoForItemProvider` fejléc `IntuneMAMDataProtectionManager` metódusával lehet lekérni. Ha a megosztott elem fájl, akkor az SDK kezeli a fájltulajdonos beállítását. Ha a megosztott elem adat, az alkalmazás feladata beállítani a fájltulajdonost, amennyiben az adat fájlba íródik, és meghívni a `setUIPolicyIdentity` API-t az adat felhasználói felületen való megjelenítése előtt.

### <a name="turning-on-multi-identity"></a>Több identitás használatának bekapcsolása

Az alkalmazások alapértelmezés szerint egyidentitásúnak minősülnek. Az SDK a beléptetett felhasználót állítja be a folyamat identitásaként. Több identitás használatának engedélyezéséhez egy `MultiIdentity` nevű logikai típusú, Igen értékű beállítást kell felvenni az Info.plist fájl IntuneMAMSettings szótárába.

> [!NOTE]
> A több identitás használatának engedélyezésekor a folyamat identitása, a felhasználói felület identitása és a szálak identitásai mind „nil” értéket kapnak. Megfelelő értékre állításuk az alkalmazás feladata.

### <a name="switching-identities"></a>Identitásváltás

* **Alkalmazás által kezdeményezett identitásváltás:**

    A több identitást használó alkalmazások indításkor ismeretlen, nem felügyelt fiók alatt futóként vannak kezelve. A feltételes indítású felhasználói felület nem fut, és az alkalmazásra nem lépnek érvénybe szabályzatok. Az alkalmazás feladata értesíteni az SDK-t, ha identitásváltásra van szükség. Ez jellemzően akkor következik be, ha az alkalmazás egy bizonyos felhasználói fiókhoz tartozó adatokat szándékozik megjeleníteni,

    például ha egy felhasználó egy dokumentumot, postafiókot vagy jegyzetfüzetlapot próbál megnyitni. Az alkalmazásnak a dokumentum, postafiók vagy jegyzetfüzetlap tényleges megnyitása előtt kell értesítenie az SDK-t az `IntuneMAMPolicyManager` fejléc `setUIPolicyIdentity` API-jával. Felügyelt és nem felügyelt felhasználó esetén egyaránt ezt az API-t kell meghívni. A felügyelt felhasználó esetében az SDK hajtja végre a feltételes indításhoz szükséges (például az eszköz feltörésével, a PIN-kóddal és a hitelesítéssel kapcsolatos) ellenőrzéseket.

    Az identitásváltás eredménye aszinkron módon, egy teljesítéskezelő útján jut vissza az alkalmazáshoz. Az alkalmazásnak el kell halasztania a dokumentum, postafiók vagy lap megnyitását, amíg sikeres eredménykódot nem kap vissza. Ha az identitásváltás sikertelen, az alkalmazásnak törölnie kell a feladatot.

* **Az SDK által kezdeményezett identitásváltás:**

    Bizonyos esetekben az SDK-nak kell kérnie az alkalmazást, hogy váltson egy adott identitásra. A több identitást használó alkalmazásoknak az `IntuneMAMPolicyDelegate` fejléc `identitySwitchRequired` metódusával kell ezeket a kéréseket kezelniük.

    A metódus meghívásakor az alkalmazásnak, amennyiben képes kezelni a kért identitásváltást, az `IntuneMAMAddIdentityResultSuccess` értéket kell átadnia a teljesítéskezelőnek. Ha nem képes kezelni az identitásváltást, az `IntuneMAMAddIdentityResultFailed` értéket kell átadnia a teljesítéskezelőnek.

    Az alkalmazásnak nem kell a hívásra válaszul meghívnia a `setUIPolicyIdentity` metódust. Ha az SDK nem felügyelt felhasználói fiókra szeretne váltani az alkalmazásban, üres karakterláncot kell átadni az `identitySwitchRequired`-hívásnak.

* **Szelektív törlés:**

    Az alkalmazás szelektív törlésekor az SDK az `IntuneMAMPolicyDelegate` fejléc `wipeDataForAccount` metódusát hívja meg. Az alkalmazás feladata a megadott felhasználói fiók és az esetleg hozzá tartozó adatok eltávolítása. Az SDK képes a felhasználó tulajdonában álló összes fájl eltávolítására, és meg is teszi, ha az alkalmazás a `wipeDataForAccount`-hívásra a „FALSE” értéket adja vissza.

    Fontos tudni, hogy ezt a metódust egy háttérszál hívja meg. Az alkalmazásnak nem szabad értéket visszaadnia, amíg a felhasználó összes adata nem törlődött (a fájlok kivételével, amennyiben az alkalmazás a „FALSE” értéket adja vissza).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Az alkalmazásvédelmi szabályzatok beállításainak tesztelése az Xcode-ban

Mielőtt éles környezetben manuálisan tesztelné Intune-kompatibilis alkalmazását, használjon Settings.bundle fájlt az Xcode-ban. Így tesztcélból Intune-kapcsolat nélkül is beállíthat alkalmazásvédelmi szabályzatokat.

### <a name="enable-policy-testing"></a>Szabályzattesztelés engedélyezése

Az Xcode-ban az alábbi lépésekkel engedélyezheti a szabályzattesztelést:

1. Ellenőrizze, hogy hibakeresési buildet nyitott-e meg. A jobb gombbal a projekt legfelső szintű mappájára kattintva vegyen fel egy Settings.bundle fájlt. Válassza a menü **Add** (Hozzáadás) > **New File** (Új fájl) elemét. A **Resources** (Erőforrások) alatt válassza a **Settings Bundle** (Beállításköteg) nevű sablont.

2.  Másolja az alábbi blokkot a hibakeresési buildhez tartozó Settings.bundle/**Root.plist** fájlba:
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. Az alkalmazás Info.plist fájljának **IntuneMAMSettings** szótárába vegyen fel egy DebugSettingsEnabled nevű logikai beállítást. Állítsa a DebugSettingsEnabled beállítást Igen értékre.



### <a name="app-protection-policy-settings"></a>Alkalmazásvédelmi szabályzatok beállításai

Az alábbi táblázat a MAMDebugSettings.plist fájllal tesztelhető szabályzatbeállításokat ismerteti. A beállításokat a MAMDebugSettings.plist fájlba felvéve lehet tesztelni.

| Szabályzatbeállítás neve | Leírás | Lehetséges értékek |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | Az az időtartam (percben), ameddig az alkalmazás offline lehet anélkül, hogy az Intune letiltaná az indítását vagy folytatását (ha engedélyezve van a hitelesítés). | 0-nál nagyobb egész szám |
|    AccessRecheckOnlineTimeout | Az az időtartam (percben), ameddig az alkalmazás futhat anélkül, hogy a felhasználónak PIN-kódot kéne megadnia vagy hitelesítésre kényszerülne az alkalmazás indításakor vagy folytatásakor (ha engedélyezve van a hitelesítés vagy a PIN-kódos elérés). | 0-nál nagyobb egész szám |
| AppSharingFromLevel | Itt lehet megadni, hogy az alkalmazás mely alkalmazásoktól fogadhat adatokat. | 0 = |
## <a name="ios-best-practices"></a>iOS-es gyakorlati tanácsok

Az alábbiakban néhány gyakorlati tanácsot ajánlunk az iOS-re történő fejlesztéshez:

* Az iOS fájlrendszere megkülönbözteti a kis-és nagybetűket. Ellenőrizze a fájlnevek (például `libIntuneMAM.a` és `IntuneMAMResources.bundle`) betűállását.

* Ha az Xcode nem találja a `libIntuneMAM.a` könyvtárat, a problémát megoldhatja a kódtár elérési útjának keresőútvonalakba való felvételével.

## <a name="faqs"></a>Gyakori kérdések


**Az összes API címezhető natív Swiftben vagy az Objective-C–Swift együttműködési környezetben?**

Az Intune App SDK API-jai csak Objective-C környezetben érhetők el, a **natív** Swiftet nem támogatják. Használatukhoz az Objective-C–Swift együttműködési környezetre van szükség.


**Az alkalmazás összes felhasználójának regisztrálnia kell az APP-WE szolgáltatásban?**

Nem. Valójában csak a munkahelyi vagy iskolai fiókokat kell az Intune App SDK-ban regisztrálni. Az alkalmazások feladata eldönteni, hogy egy adott fiók ilyen környezetben használatos-e.   

**Az alkalmazásba már bejelentkezett felhasználóknak is el kell-e végezniük a beléptetést?**

Az alkalmazás feladata a felhasználók beléptetése a sikeres hitelesítés után, ahogyan azoknak a korábban létrehozott fiókoknak a beléptetése is, amelyek esetleg az alkalmazás MDM nélküli MAM-funkciójának megjelenése előtt voltak használatban.   

Ezt az alkalmazásnak a `registeredAccounts:` metódussal ajánlott megtennie. A metódus egy NSDictionary szótárt ad vissza, amelyben szerepel az összes, az Intune MAM-szolgáltatásban regisztrált felhasználói fiók. Ha valamely, az alkalmazásban megtalálható fiók nem szerepel a listában, azt az alkalmazásnak a `registerAndEnrollAccount:` metódussal kell beléptetnie.

**Milyen gyakran próbálkozik újra az SDK a beléptetéssel?**

Az SDK 24 órás időközzel próbálkozik újra automatikusan minden korábban sikertelen beléptetéssel. Ennek az a célja, hogy a felhasználó akkor is sikeresen el tudja végezni a beléptetést és megkapja a szabályzatokat, ha a munkahelye az alkalmazásba való bejelentkezése után engedélyezte a MAM-szolgáltatást.

Az SDK addig próbálkozik, amíg nem észleli, hogy a felhasználó sikeresen beléptette az alkalmazást. Ennek az az oka, hogy egy alkalmazást egyszerre csak egy felhasználó léptethet be. Ha a felhasználó beléptetése megszűnik, az újrapróbálkozás ugyanígy 24 órás időközökkel kezdődik meg.

**Miért kell megszüntetni a felhasználó regisztrációját?**

Az SDK az alábbi műveleteket végzi el rendszeresen a háttérben:

 - Ha az alkalmazás még nincs beléptetve, akkor 24 óránként megkísérli minden regisztrált fiók beléptetését.
 - Ha az alkalmazás már be van léptetve, az SDK 8 óránként ellenőrzi, hogy frissültek-e az alkalmazásvédelmi szabályzatok.

A felhasználói regisztráció megszüntetése jelzi az SDK-nak, hogy a felhasználó a továbbiakban nem fogja használni az alkalmazást, így az ő fiókja esetében nem kell elvégezni a fenti rendszeres műveleteket; továbbá kiváltja az alkalmazás beléptetésének törlését és szükség esetén szelektív törlését is.

**A regisztrációt megszüntető metódusban „true” értékre állítsam a doWipe jelzőt?**

Ezt a metódust azelőtt kell meghívni, hogy a felhasználó kijelentkezne az alkalmazásból.  Ha a felhasználói adatok a kijelentkezés során törlődnek, a `doWipe` jelzőt „false” értékre lehet állítani. Ha azonban az alkalmazás nem távolítja el a felhasználói adatokat, a `doWipe` jelzőt ajánlott „true” értékre állítani, hogy az SDK törölhesse az adatokat.

**Más módon is vissza lehet vonni az alkalmazás beléptetését?**

Igen, a rendszergazda küldhet szelektív törlési parancsot az alkalmazásnak. Ez megszünteti a felhasználó regisztrációját és beléptetését, valamint törli a felhasználó adatait. Az SDK automatikusan kezeli ezt az esetet, és a delegált beléptetés-visszavonási metódus útján küld értesítést.



## <a name="submit-your-app-to-the-app-store"></a>Az alkalmazás beküldése az App Store-ba

Az Intune App SDK statikus kódtáras és dinamikus keretrendszeres buildjei is univerzális programfájlok, tehát minden eszköz- és szimulátorarchitektúrához megvan bennük a kód. Az Apple elutasítja az App Store-ba beküldött alkalmazásokat, ha szimulátorkód van bennük. Ha csak eszközökön használatos buildet fordít a statikus kódtárral, a csatoló automatikusan eltávolítja a szimulátorkódot. Az App Store-ba való feltöltés előtt az alábbi lépésekkel ellenőrizheti, hogy a szimulátorkód el lett-e távolítva:

1. Ellenőrizze, hogy az `IntuneMAM.framework` az asztalon van-e.

2. Futtassa az alábbi parancsokat:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    Az első parancs eltávolítja a szimulátorarchitektúrákat a keretrendszer DYLIB-fájljából. A második parancs visszamásolja a csak eszközökre utaló DYLIB-fájlt a keretrendszer könyvtárába.


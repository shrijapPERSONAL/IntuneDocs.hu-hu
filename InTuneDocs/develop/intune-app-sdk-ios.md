---
title: "iOS-hoz készült Microsoft Intune App SDK – fejlesztői útmutató | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: angrobe
ms.author: oydang
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 018faada59819938d443605a454465a38600c9a4
ms.openlocfilehash: f44d2a43c6717c9b3adde9ba49a54e014f4e3528


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>iOS-hoz készült Microsoft Intune App SDK – fejlesztői útmutató

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](intune-app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés

Az iOS-hez készült Microsoft Intune App SDK lehetővé teszi, hogy Intune-alapú alkalmazásvédelmi szabályzatokat építsen az iOS-alkalmazásába. Az Intune App SDK-ba integrált MAM-kompatibilis alkalmazások lehetővé teszik a rendszergazdák számára, hogy szabályzatokat léptessenek érvénybe az Intune-alapú mobilalkalmazás-felügyelet (MAM) által aktívan felügyelt alkalmazásokban.


## <a name="prerequisites"></a>Előfeltételek

* Szüksége lesz egy OS X 10.8.5 vagy újabb verziót futtató Mac OS-számítógépre, amelyen telepítve van az XCode eszközkészlet 5-ös vagy újabb verziója.

* Olvassa el [az iOS-hez készült Intune App SDK licencfeltételeit](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Nyomtassa ki és őrizze meg a licencfeltételeket. Az iOS-hez készült Intune App SDK letöltésével és használatával elfogadja licencfeltételeket.  Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.


## <a name="whats-in-the-sdk"></a>Az SDK tartalma

Az iOS-hoz készült Intune App SDK magában foglalja a statikus könyvtárat, az erőforrásfájlokat, az API-fejléceket, a hibakeresési beállításokat tartalmazó plist-fájlt és a konfiguráló eszközt. A mobilalkalmazások tartalmazhatják az erőforrásfájlokat, és általában statikus módon csatolhatók a könyvárakhoz a szabályzatok érvénybe léptetéséhez. A speciális Intune MAM-funkciók használata API-k segítségével kényszeríthető ki.

Ez az útmutató az iOS-hez készült Intune App SDK következő összetevőit ismerteti:

* **libIntuneMAM.a**: az Intune App SDK statikus erőforrástára. Ha az alkalmazás nem használ bővítményeket, Önnek ezt az erőforrástárat kell csatolnia a projekthez, hogy az alkalmazás felügyelhető legyen az Intune mobilalkalmazás-kezeléssel. Ehhez „Az alkalmazás elkészítése az Intune App SDK-val” című szakaszban talál útmutatást.

* **IntuneMAM.framework**: Az Intune App SDK keretrendszere. Ezt a keretrendszert kell csatolnia a projekthez, hogy az alkalmazás felügyelhető legyen az Intune mobilalkalmazás-kezelés segítségével. Akkor használja ezt a keretrendszert a statikus erőforrástár helyett, ha az alkalmazás bővítményeket használ. Ez esetben a projekt nem hoz létre több példányt a statikus erőforrástárból.

* **IntuneMAMResources.bundle**: az SDK erőforrásait tartalmazó csomag.

* **Headers**: az Intune App SDK API-jainak elérhetővé tétele. Ha API-t használ, meg kell adnia az API-t tartalmazó fejlécfájlt. A következő fejlécfájlok azokat az API-függvényhívásokat tartalmazzák, amelyek az Intune App SDK funkcióinak működéséhez szükségesek.

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Az Intune App SDK működése

Az iOS-hoz készült Intune App SDK révén minimális kódmódosítással adhat hozzá felügyeleti funkciókat az iOS-alkalmazásokhoz. Minél kevesebb kódmódosítás szükséges, annál gyorsabban dobhatja piacra a mobilalkalmazást, és stabilabbá is teheti.

Az alkalmazást a statikus erőforrástárhoz kell csatolni, és az alkalmazásnak tartalmaznia kell az erőforrás-csomagot is. A MAMDebugSettings.plist fájl használata nem kötelező, segítségével a MAM-szabályzatok által felügyelt alkalmazások működését szimulálhatja anélkül, hogy Microsoft Intune-on keresztül telepítené az alkalmazást. Hibakeresési buildekben ezenkívül a MAMDebugSettings.plist fájlban lévő szabályzatok érvénybe léptetéséhez ezt a fájlt az alkalmazás Dokumentumok könyvtárába kell másolni az iTunes-fájlmegosztás segítségével.

## <a name="building-the-sdk-into-your-mobile-app"></a>Az SDK beépítése a mobilalkalmazásba

Kövesse az alábbi lépéseket az Intune App SDK engedélyezéséhez:

1. **1. lehetőség**: Csatolás a `libIntuneMAM.a` erőforrástárhoz a következőkkel:

    Húzza a `libIntuneMAM.a` erőforrástárat a projekthez használni kívánt elemek „Linked Frameworks and Libraries”(Csatolt keretrendszerek és könyvtárak) listájába.

    ![Intune App SDK (iOS) - csatolt keretrendszerek és könyvtárak](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    **Megjegyzés**: ha azt tervezi, hogy közzéteszi az alkalmazást az App Store-ban, a `libIntuneMAM.a` végleges verzióját használja, ne a hibakeresési verziót. A végleges verziót a „release” (kiadás) mappában találja. A hibakeresési verzió részletes kimenetet ad, ami megkönnyíti az Intune App SDK problémáinak elhárítását.

    **2. lehetőség**: Az `IntuneMAM.framework` csatolása a projekthez. Húzza az `IntuneMAM.framework` könyvtárat a projekthez használni kívánt elemek „Linked Frameworks and Libraries”(Csatolt keretrendszerek és könyvtárak) listájába.

    **Megjegyzés:** Ha a keretrendszert használja, manuálisan kell eltávolítania a szimulátorarchitektúrákat az univerzális keretrendszerből, mielőtt beküldi az alkalmazást az App Store-ba. Lásd „Az alkalmazás beküldése az App Store-ba”.

2. Vegye fel a következő iOS-keretrendszereket a projektbe:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    **Megjegyzés:** ha az alkalmazást iOS7-re fejlesztették, állítsa a `LocalAuthentication.framework` „Status” (Állapot) attribútumát „Optional" (Választható) értékre. Ha a „Status" (Állapot) nincs beállítva, az alkalmazás nem indul el iOS7-en.

    **Megjegyzés**: az Xcode 7 a `.dylib` helyett már `.tbd`.

3. Húzza az `IntuneMAMResources.bundle` erőforrás-csomagot a „Copy Bundle Resources” (Erőforrás-csomagok másolása) alatti „Build Phases” (Összeállítási fázisok) elemre a projektbe való felvételhez.
![Intune App SDK(iOS) – erőforráscsomagok másolása](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Írja be a `-force_load {PATH_TO_LIB}/libIntuneMAM.a` utasítást a következő helyek egyikére, kicserélve a `{PATH_TO_LIB}` sort az Intune App SDK elérési útjával:
    * a projekt `OTHER_LDFLAGS` buildkonfigurációs beállítása
    * a felhasználói felület „Other Linker Flags" (Más csatoló jelzők) területe<br>

    **Megjegyzés**: a `PATH_TO_LIB` megkereséséhez jelölje ki a `libIntuneMAM.a` fájlt és, és válassza a „File” (Fájl) menü „Get Info” (Információ megjelenítése) parancsát. Másolja és illessze be a „Where” (Hely) feliratnál látható információt (az elérési utat) az „Info” (Információ) ablak „General” (Általános) szakaszából.

5. Ha a mobilalkalmazás fő Nib vagy a Storyboard fájlt definiál az info.plist fájlban, távolítsa el a Main Storyboard vagy a Main Nib fájlmezőket. Adja meg a korábban eltávolított Storyboard- vagy Nib-értékeket egy IntuneMAMSettings nevű új szótárban, a következő kulcsnevekkel:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad

   **Megjegyzés:** Ha a mobilalkalmazás nem definiálja a fő Nib vagy Storyboard fájlt az Info.plist fájlban, ezek a beállítások **nem szükségesek**.

    **Megjegyzés:** az info.plist fájlt nyers formátumban megtekintve láthatja a kulcsneveket. Kattintson jobb gombbal a dokumentum törzsében bárhol, és válassza a „Show Raw Keys/Values” (Nyers kulcs/érték megjelenítése) nézetet.

6. Engedélyezze a kulcsláncmegosztást (ha még nincs engedélyezve) a projekthez használni kívánt elemeken a „Capabilities” (Képességek) lehetőségre kattintva, majd kapcsolja be a „Keychain Sharing” (Kulcsláncmegosztás) csúszkát. A következő lépéshez szükséges a kulcsláncmegosztás.

    **Megjegyzés**: A telepítési profil esetében elengedhetetlen az új kulcsláncmegosztási értékek támogatása. A kulcslánc-hozzáférési csoportoknak támogatniuk kell a helyettesítő karaktert. Ezt a .mobileprovision fájl szövegszerkesztőben való megnyitásával ellenőrizheti, rákeresve a „keychain-access-groups” kifejezésre. Itt meggyőződhet arról, hogy rendelkezik-e helyettesítő karakterrel, ilyen például a következő:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. Miután engedélyezte a kulcsláncmegosztást, az alábbi lépéseket követve létrehozhat egy különálló hozzáférési csoportot, amelyen az Intune App SDK adatait tárolhatja. A kulcslánc-hozzáférési csoportokat a felhasználói felületet vagy a jogosultságokat tartalmazó fájlt használva hozhatja létre:

    A felhasználói felület használata kulcslánc-hozzáférési csoport létrehozására:

    * Ha a mobilalkalmazás nem határozott meg kulcslánc-hozzáférési csoportokat, vegye fel az alkalmazás csomagazonosítóját az első csoport létrehozásához.
    * Vegye fel a `com.microsoft.intune.mam` megosztott kulcslánc-csoportot. Ez a hozzáférési csoport az Intune App SDK-adatok tárolására szolgál.  
    * Vegye fel a `com.microsoft.adalcache` csoportot a meglévő hozzáférési csoportokba.

    ![Intune App SDK (iOS) – kulcsláncok megosztása](../media/intune-app-sdk-ios-keychain-sharing.png)

    Ha a felhasználói felület helyett a jogosultságokat tartalmazó fájlt használja a kulcslánc-hozzáférési csoport létrehozására, az `$(AppIdentifierPrefix)` előtaggal együtt be kell illesztenie a kulcslánc-hozzáférési csoportot a jogosultságokat tartalmazó fájlba. Példa:  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **Megjegyzés**: a jogosultságokat tartalmazó fájl egy egyedi XML-fájl a mobilalkalmazásban, amely speciális engedélyeket adhat meg az iOS-alkalmazásban.

8. Ha az alkalmazás az Info.plist fájlban határozza meg az URL-sémákat, mindegyikhez vegyen fel új sémát az `-intunemam` utótaggal együtt.

9. Az iOS 9-es vagy újabb verziójára fejlesztett mobilalkalmazásoknak tartalmazniuk kell minden, az `UIApplication canOpenURL` számára átadott protokollt az alkalmazás Info.plist fájljának `LSApplicationQueriesSchemes` tömbjében. Emellett minden egyes listázott protokollhoz egy új protokollt kell felvenni az `-intunemam`. A `http-intunemam`, `https-intunemam` és `ms-outlook-intunemam` elemet is fel kell venni a tömbbe.

10. Ha az alkalmazás jogosultságaiban meghatározott alkalmazáscsoportok találhatók, vegye fel ezeket a csoportokat az `AppGroupIdentitifiers` szótárba, az IntuneMAMSettings kulcs karakterlánctömbjeként.

11. Csatolja a mobilalkalmazást az Azure Directory Authentication Library (ADAL) erőforrástárhoz (nem kötelező). Az Objective C-hez készült ADAL-könyvtár [elérhető a Githubon](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Megjegyzés**: az Intune App SDK-t 2015/6/19-től az ADAL broker fiókkóddal tesztelték. Győződjön meg arról, hogy az ADAL-könyvtár legújabb/működő verziójához kapcsolódik-e.

12. Húzza az `ADALiOSBundle.bundle` erőforráscsomagot a „Copy Bundle Resources” (Erőforráscsomagok másolása) terület „Build Phases” (Összeállítási fázisok) elemére a projektbe való felvételhez.

13. Használja a `-force_load PATH_TO_ADAL_LIBRARY` összekötő lehetőséget a könyvtárhoz kapcsolódáshoz.

    Írja be a `-force_load {PATH_TO_LIB}/libADALiOS.a` utasítást a projekt `OTHER_LDFLAGS` buildkonfigurációs beállításába vagy az „Other Linker Flags” (Más csatoló jelzők) helyre a felhasználói felületen. A `PATH_TO_LIB` helyett adja meg az ADAL bináris fájljainak helyét.

## <a name="configure-azure-directory-authentication-library-adal"></a>Az Azure Directory Authentication (ADAL) konfigurálása (nem kötelező)

Az Intune App SDK az ADAL-t hitelesítésre és a feltételes indítási forgatókönyvek készítésére használja. Az ADAL-t használja ezenkívül arra, hogy regisztrálja a felhasználó identitását a MAM-szolgáltatásnál az eszközök regisztrációja nélkül történő felügyelet esetére.

Az ADAL használata során az alkalmazáshoz tartozó jogkivonatok biztonsága érdekében az alkalmazások használata legtöbbször az [Azure Active Directoryban] való regisztrációhoz, egyedi azonosítóhoz (más néven ClientID) és egyéb azonosítókhoz kötött. Az Intune App SDK az alapértelmezett regisztrációs értékeket használja, amikor kapcsolatba lép az Azure Active Directoryval.  

Ha maga az alkalmazás használja az ADAL-t a hitelesítés részeként, a meglévő regisztrációs értékeket figyelembe véve felül kell bírálnia az alapértelmezett Intune App SDK-t, hogy a felhasználók ne kapjanak két felkérést a hitelesítésre (egyszer az Intune App SDK-ban, és egyszer az alkalmazásban).

### <a name="adal-faqs"></a>ADAL – gyakori kérdések

**Melyik bináris ADAL-fájlokat használjam?**

Az Intune App SDK jelenleg a [GitHubon elérhető ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc) broker ágát használja, hogy támogassa a feltételes hozzáférést igénylő alkalmazásokat (tehát olyan alkalmazásokhoz, amelyek ebből következően függenek a Microsoft Authenticator alkalmazástól). Az SDK azonban továbbra is kompatibilis az ADAL fő (master) ágával is. Az alkalmazásának megfelelő ágat használja.

**Hogyan lehet hivatkozni az ADAL bináris fájljaira?**

Írja be a `-force_load {PATH_TO_LIB}/libADALiOS.a` utasítást a projekt `OTHER_LDFLAGS` buildkonfigurációs beállításába vagy az „Other Linker Flags” (Más csatoló jelzők) helyre a felhasználói felületen. A `PATH_TO_LIB` helyett adja meg az ADAL bináris fájljainak helyét. Ne felejtse el ezenkívül másolni az ADAL csomagot az alkalmazásba.  

Részletesebb tájékoztatást az [Github ADAL rovatában](https://github.com/AzureAD/azure-activedirectory-library-for-objc) talál.


**Hogyan oszthatom meg az ADAL gyorsítótárát más, ugyanazzal a kiépítési profillal aláírt alkalmazásokkal?**

Ha az alkalmazás nem határozott meg kulcslánc-hozzáférési csoportokat, hozza létre az első csoportot az alkalmazás csomagazonosítójának felvételével.
Engedélyezze az ADAL SSO-t: ehhez vegye fel a `com.microsoft.adalcache` és a `com.microsoft.workplacejoin` hozzáférési csoportot a kulcslánc jogosultságai közé.

Ha explicit módon beállítja az ADAL megosztott gyorsítótárának kulcslánccsoportját, akkor feltétlenül a következő értékre állítsa: `<app_id_prefix>.com.microsoft.adalcache`. Az ADAL ezt állítja be, hacsak Ön felül nem bírálja. Ha egyéni kulcslánccsoportot szeretne megadni a `com.microsoft.adalcache` helyett, az Info.plist fájl „IntuneMAMSettings” szakaszában, az `ADALCacheKeychainGroupOverride` kulccsal kell megadnia.

**Hogyan kényszeríthetem az Intune App SDK-t arra, hogy az alkalmazásom által már használt ADAL-beállításokat használja?**

Ha az alkalmazás már használja az ADAL-t, az IntuneMAMSettings beállításait ismertető szakaszban talál tájékoztatást a következő beállítások értékének kitöltéséről:  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**Hogyan válthatok az AAD éles és belső tesztkörnyezete között?**

A `MAMPolicies.plist``AadAuthorityURI` beállításával lehet megadni az ADAL-hívásokhoz használt AAD-környezetet. Jelenleg az AAD üzem előtti környezete (PPE) van megadva alapértelmezésként, de felül lehet bírálni.

A PPE környezetben való teszteléshez használhat fordításkor vagy futtatáskor történő váltást.

A MAM-szolgáltatás URL-címeinek és ADD-jének fordítás közben történő környezetváltásához állítsa a `UsePPE` logikai jelzőt true értékre a MAMEnvironment.plist fájlban (**Megjegyzés**: ennek az Info.plist fájllal történő elvégzése nem támogatott).

Ha futtatáskor szeretne környezetet váltani, az általános jogú felhasználó alapértelmezései között kell átállítania a `com.microsoft.intune.mam.useppe` beállítást az „1” értékre a PPE használatához. Ez felváltja a meglévő `com.microsoft.intune.mam.AADAuthorityEnvironment` beállítást.

**Hogyan bírálhatom felül az AAD-szolgáltató URL-címét egy bérlőspecifikus, futtatás közben megadott URL-címmel?**

Állítsa be az `aadAuthorityUriOverride` tulajdonságot az IntuneMAMPolicyManager példányon.

**Megjegyzés:** Ezt akkor kell megtennie, ha az eszközök regisztrálása nélkül használja a MAM szolgáltatást. Így az SDK újra fel tudja használni az alkalmazás által beolvasott ADAL frissítési jogkivonatot.

**Megjegyzés:** Az SDK továbbra is ezt a szolgáltatói URL-címet használja a szabályzatok frissítésére és a későbbi regisztrációs kérelmekhez, hacsak nem törlik vagy módosítják az értéket.  Ezért fontos törölni az értéket, ha egy vállalati felhasználó kijelentkezik az alkalmazásból, és újra beállítani, ha egy új vállalati felhasználó visszajelentkezik.


**Mi a teendőm, ha maga az alkalmazás már az ADAL-t használja hitelesítésre?**

Ha az alkalmazás maga az ADAL-t használja hitelesítésre, az alábbi lépéseket kell elvégeznie. Ha az alkalmazás nem az ADAL-t használja, akkor azt a szakaszt kell elolvasnia, amely arra az esetre ismerteti az Intune szolgáltatásnál való regisztrációt, ha az alkalmazás nem az ADAL-t használja.

* Adja meg az ADAL-hívásokhoz használandó ClientID-t a projekt Info.plist fájljában, az IntuneMAMSettings szótár alatt található `ADALClientId` nevű kulcsban.

* Adja meg az ADAL-hívásokhoz használandó átirányítási URI-t a projekt Info.plist fájljában, az IntuneMAMSettings szótár alatt található `ADALRedirectUri` nevű kulcsban. Az alkalmazás átirányítási URI-formátumától függően előfordulhat, hogy az `ADALRedirectScheme` beállításait is meg kell adnia.



## <a name="register-your-app-with-intune-mam-service"></a>Az alkalmazás regisztrálása az Intune MAM-szolgáltatásában

### <a name="use-the-apis"></a>Az API-k használata
Az Intune App SDK mostantól lehetőséget nyújt arra, hogy az iOS-alkalmazások anélkül fogadják az Intune-tól a MAM-szabályzatokat, hogy az Intune-ban regisztrálva kellene lenniük az MDM-re. Az új funkciót olyan új API-k segítségével biztosítja, amelyek lehetővé teszik az alkalmazás számára a MAM-házirendek fogadását. Az új API-k használatához a következő lépéseket kell elvégeznie:

1. Használja az Intune App SDK legújabb kiadását, amely az eszközregisztrációval és nélküle is lehetőséget nyújt az alkalmazások felügyeletére. Ha az alkalmazás az SDK egy régebbi, ezt a funkciót nem nyújtó változatát használja, frissítenie kell az Intune MAM-erőforrástárát és a Headers mappát a legújabb SDK fejléceivel.

2. Vegye fel a IntuneMAMEnrollment.h-t minden olyan fájlba, amely hívni fogja az API-kat.

3. A PPE környezetben való teszteléshez használhat fordításkor vagy futtatáskor történő váltást.

    A MAM-szolgáltatás URL-címeinek és AAD-jének fordítás közben történő környezetváltásához állítsa a `UsePPE` logikai jelzőt true értékre a MAMEnvironment.plist fájlban (**megjegyzés**: ennek az Info.plist fájllal történő elvégzése nem támogatott).

    Ha futtatáskor szeretne környezetet váltani, az általános jogú felhasználó alapértelmezései között kell átállítania a `com.microsoft.intune.mam.useppe` beállítást az „1” értékre a PPE használatához. Ez felváltja a meglévő `com.microsoft.intune.mam.AADAuthorityEnvironment` beállítást.


### <a name="register-accounts"></a>Fiókok regisztrálása

Egy alkalmazás akkor fogadhatja a MAM-szabályzatokat az Intune szolgáltatástól, ha az alkalmazás regisztrálva van egy megadott felhasználói fiók nevében.  Az alkalmazás feladata, hogy regisztráljon minden újonnan bejelentkezett felhasználót az Intune App SDK-val.  Az új felhasználói fiók hitelesítését követően az alkalmazásnak meg kell hívnia a `registerAndEnrollAccount` metódust, amelyet a **Headers/IntuneMAMEnrollment.h** fájl tartalmaz:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Az SDK a fenti metódus meghívásának hatására regisztrálja a felhasználói fiókot, és megpróbálja regisztrálni az alkalmazást ennek a fióknak a nevében.  Ha a regisztráció bármilyen okból nem sikerül, az SDK 24 óra múlva ismét megkísérli.  Hibakeresési célokra az alkalmazás egy delegálton keresztül fogadhat értesítéseket a regisztrációs kérések eredményéről (a részleteket lásd alább).

Az API meghívása után az alkalmazás a szokásos módon működhet tovább.  Ha a regisztráció sikeretlen, az SDK értesíti a felhasználót, hogy újra kell indítani az alkalmazást.  Ekkor a felhasználó azonnal újraindíthatja az alkalmazást.


### <a name="de-register-accounts"></a>Fiókok regisztrációjának megszüntetése


Mielőtt egy felhasználó kijelentkezik az alkalmazásból, az alkalmazásnak meg kell szüntetnie a felhasználó regisztrációját az SDK-ban.  Ez a következőket garantálja:

1. Nem lesznek további próbálkozások a felhasználói fiók regisztrálására.
2. Ha a felhasználó sikeresen regisztrálta az alkalmazást, a felhasználó és az alkalmazás regisztrációja is megszűnik az Intune MAM-szolgáltatásban, és törlődnek a MAM-szabályzatok.
3. Igény esetén szelektív törlés is kezdeményezhető, hogy törlődjön minden, a munkahellyel vagy az iskolával kapcsolatos adat.

A felhasználó kijelentkeztetése előtt az alkalmazásnak meg kell hívnia a következő, a **Headers/IntuneMAMEnrollment.h** fájlban található API-t:

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

Ezt a metódust még a felhasználó AAD-jogkivonatainak törlése előtt kell meghívni.  Az SDK-nak azért van szüksége a felhasználó alkalmazás-jogkivonatára, hogy a felhasználó nevében tudjon elküldeni bizonyos kéréseket az Intune MAM-szolgáltatásnak.

Ha az alkalmazás saját maga gondoskodik a felhasználó munkahelyi vagy iskolai adatainak törléséről, akkor a `doWipe` jelző false értékre állítható.  Ellenkező esetben az alkalmazás szelektív törlést kezdeményeztethet az SDK-val, az pedig meghívja az alkalmazás szelektív törlési delegáltját.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```


## <a name="enrolling-without-prior-sign-in"></a>Regisztráció előzetes bejelentkezés nélkül

Olyan alkalmazás is fogadhatja a MAM-szabályzatokat az Intune szolgáltatástól, amely nem jelentkezteti be a felhasználót az Azure Active Directoryval. Ez esetben az alábbi API meghívásával kell utasítani az SDK-t ennek a hitelesítésnek a kezelésére. Az alkalmazásoknak akkor kell ezt használniuk, ha nem hitelesítettek egy felhasználót az AAD-vel, mégis le kell kérniük a MAM-szabályzatokat, hogy megvédjék az alkalmazásban lévő adataikat; ilyen eset például, ha például egy másik hitelesítési szolgáltatást használnak az alkalmazás bejelentkeztetésére, vagy ha az alkalmazás egyáltalán nem támogatja a bejelentkezést. Ehhez az alkalmazásnak meg kell hívnia a `loginAndEnrollAccount` metódust, amelyet a **Headers/IntuneMAMEnrollment.h** fájl tartalmaz:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```
A metódus meghívásának hatására az SDK kéri a felhasználótól a hitelesítő adatokat (ha nem található meglévő jogkivonat), majd megpróbálja regisztrálni az alkalmazást ennek a fióknak a nevében. A metódus meghívható „nil” identitással is. Ez esetben az SDK regisztrálja a felhasználó meglévő MAM-felhasználóját, vagy ha nem talál meglévő felhasználót, kéri a felhasználótól a felhasználónevet.

Ha a regisztráció sikertelen, az alkalmazásnak valamikor a jövőben újra meg kell vizsgálnia az API meghívásának lehetőségét, függően a sikertelenség részleteitől. Az alkalmazás egy delegálton keresztül fogadhat értesítéseket a regisztrációs kérések eredményéről (lásd a részleteket).

Az API meghívása után az alkalmazás a szokásos módon működhet tovább.  Ha a regisztráció sikeretlen, az SDK értesíti a felhasználót, hogy újra kell indítani az alkalmazást, amint azt a fenti, a fiókok regisztrációjáról szóló szakasz ismerteti.

## <a name="debug-information"></a>Hibakeresési információk

Az alkalmazás az Intune MAM-szolgáltatásokhoz intézett kérések közül a következők esetében tudja fogadni a hibakeresési értesítéseket:

 - Regisztrációs kérések
 - Szabályzatfrissítési kérések
 - Regisztráció megszüntetésére irányuló kérések

Az értesítéseket delegáltmetódusok adják át. Ezeket a **Headers/IntuneMAMEnrollmentDelegate.h** fájl tartalmazza:

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

- A kéréshez társított fiók identitását
- A kérés állapotát jelölő állapotkódot
- Az állapotkód leírását tartalmazó hibaüzenet-karakterláncot
- Egy NSError objektumot

Ezt az objektumot a **Headers/IntuneMAMEnrollmentStatus.h** fájl definiálja, a visszaadható konkrét állapotkódokkal együtt.

Fontos megjegyezni, hogy ezek az információk hibakeresési célokra szolgálnak, és nem szabad ezekre az értesítésekre épülő üzleti logikát beépíteni az alkalmazásba.  Emögött az az elgondolás áll, hogy az alkalmazás elküldheti ezeket az információkat egy telemetriai szolgáltatásnak, hibakeresés vagy figyelés céljára,.


## <a name="sample-code"></a>Mintakód

A következők a delegáltmetódusok megvalósítására szolgálnak példákkal:

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


## <a name="app-restart"></a>Az alkalmazás újraindítása

Amikor egy alkalmazás először kapja meg a MAM-szabályzatokat, újra kell indulnia a szükséges beavatkozási pontok alkalmazása érdekében.  Az SDK biztosít egy delegáltmetódust a **Headers/IntuneMAMPolicyDelegate.h** fájlban, amellyel értesíteni lehet az alkalmazást az újraindítás szükségességéről.
```objc
 - (BOOL) restartApplication
```
A metódus visszatérési értéke közli az SDK-val, hogy az alkalmazás fogja-e kezelni a szükséges újraindítást.   

 - Ha a visszatérési érték true, akkor az alkalmazás lesz felelős az újraindítás kezeléséért.   
 - Ha a visszatérési érték false, akkor az SDK fogja újraindítani az alkalmazást a metódus visszatérése után.  Az SDK azonnal megjelenít egy párbeszédpanelt, amely közli a felhasználóval, hogy újra kell indítani az alkalmazást.

## <a name="implementing-save-as-controls"></a>A Mentés másként vezérlőinek implementálása

Az Intune lehetővé teszi, hogy a rendszergazdák meghatározzák a felügyelt alkalmazások adatmentéshez használt lehetséges tárolási helyeit. Az alkalmazások lekérhetik az engedélyezett tárolási helyek listáját az Intune APP SDK-tól az **isSaveToAllowedForLocation** API használatával.

A felügyelt adatok felhőbeli tárhelyre vagy helyi adattárolókba való mentése előtt az alkalmazásoknak az **isSaveToAllowedForLocation** API használatával ellenőrizniük kell, hogy a rendszergazda engedélyezte-e az adatmentést az adott helyre.

Az **isSaveToAllowedForLocation** használatakor az alkalmazásoknak át kell adniuk a tárolási hely UPN-jét, amennyiben az elérhető.

### <a name="supported-save-locations"></a>Támogatott mentési helyek

Az **isSaveToAllowedForLocation** API által biztosított állandókkal ellenőrzhető, hogy a rendszergazda engedélyezi-e az adatok mentését a következő helyekre:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationBox
* IntuneMAMSaveLocationDropbox
* IntuneMAMSaveLocationGoogleDrive
* IntuneMAMSaveLocationLocalDrive

Az alkalmazásoknak az **isSaveToAllowedForLocation** API állandóival kell ellenőrizniük, hogy az adatok menthetők-e a „felügyeltnek” tekintett, például a OneDrive Vállalati verziója, vagy a „személyes” helyekre. Emellett akkor is szükséges az API használata, ha az alkalmazás nem tudja meghatározni egy adott helyről, hogy az „felügyelt” vagy „személyes”.

A „személyes” helyeken az alkalmazásnak az **IntuneMAMSaveLocationOther** értéket kell használnia.

Az **IntuneMAMSaveLocationLocalDrive** állandót akkor kell használni, amikor az alkalmazás a helyi eszközre ment adatot.



## <a name="configure-intune-app-sdk-settings"></a>Az Intune App SDK-beállítások konfigurálása

Az alkalmazás Info.plist fájljában található IntuneMAMSettings szótár az Intune App SDK konfigurálására szolgál. A támogatott beállítások listája a következő:

Egy részükről már volt szó korábbi szakaszokban, más részük pedig nem vonatkozik minden alkalmazásra.

Beállítás  | Típus  | Meghatározás | Kötelező?
--       |  --   |   --       |  --
ADALClientId  | Karakterlánc  | Az alkalmazás AAD ügyfél-azonosítója. | Kötelező, ha az alkalmazás használja az ADAL-t.
ADALRedirectUri  | Karakterlánc  | Az alkalmazás AAD átirányítási URI-ja. | Az ADALRedirectUri vagy az ADALRedirectScheme kötelező, ha az alkalmazás használja az ADAL-t.
ADALRedirectScheme  | Karakterlánc  | Az alkalmazás AAD átirányítási sémája. Használható az ADALRedirectUri helyett, ha az alkalmazás átirányítási URI-ja `scheme://bundle_id` formátumú. | Az ADALRedirectUri vagy az ADALRedirectScheme kötelező, ha az alkalmazás használja az ADAL-t.
ADALLogOverrideDisabled | Logikai  | Megadásával az SDK átirányítja az összes ADAL naplófájlt (beleértve az esetleges ADAL-hívásokat az alkalmazásból) a saját naplófájljába. Az alapértelmezett érték a Nem. Állítsa be az Igen értéket, ha az alkalmazás visszahívná a saját ADAL-naplóját. | Nem kötelező.
ADALCacheKeychainGroupOverride | Karakterlánc  | Az ADAL-gyorsítótárhoz a „com.microsoft.adalcache” helyett használandó kulcslánccsoportot adja meg. Felhívjuk figyelmét, hogy nem tartalmazza az app-id előtagot. Ezt az előtagot futás közben fogja megkapni a karakterlánc. | Nem kötelező.
AppGroupIdentifiers | A karakterlánc tömbje  | Az alkalmazáscsoportok tömbje az alkalmazás jogosultságainak com.apple.security.application-groups szakaszában. | Szükséges, ha az alkalmazás alkalmazáscsoportokat használ.
ContainingAppBundleId | Karakterlánc | Megadja a bővítményt tartalmazó alkalmazás csomagazonosítóját. | IOS-bővítményekhez szükséges.
DebugSettingsEnabled| Logikai | Ha YES értékű, használhatók a Settings csomagban található tesztszabályzatok. Az alkalmazásokat **tilos** úgy szállítani, hogy engedélyezve van bennük ez a beállítás. | Nem kötelező.
MainNibFile<br>MainNibFile~ipad  | Karakterlánc  | Ennek a beállításnak tartalmaznia kell az alkalmazás fő Nib-fájljának nevét.  | Kötelező, ha az alkalmazás a MainNibFile-t az Info.plist-ben definiálja.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Karakterlánc  | Ennek a beállításnak tartalmaznia kell az alkalmazás fő storyboard-fájljának nevét. | Kötelező, ha az alkalmazás a UIMainStoryboardFile-t az Info.plist-ben definiálja.
MAMPolicyRequired| Logikai| Azt adja meg, hogy megakadályozza-e a rendszer az alkalmazás elindítását, ha az alkalmazásnak nincs Intune MAM-szabályzata. Az alapértelmezett érték a „No”.
MAMPolicyWarnAbsent | Logikai| Azt adja meg, hogy figyelmeztesse-e az alkalmazás a felhasználót az indítás közben, ha az alkalmazásnak nincs Intune MAM-szabályzata. Megjegyzés: nem lehet olyan alkalmazásokat benyújtani az áruházba, amelyeknek IGEN értékű ez a beállítása | Nem kötelező.
MultiIdentity | Logikai| Azt adja meg, hogy az alkalmazás képes-e kezelni a többszörös identitást. | Nem kötelező.
SplashIconFile <br>SplashIconFile ~ ipad | Karakterlánc  | Megadja az Intune-kezdőkép ikonfájlt. A „Képfájlok indításkor” témájú szakaszban talál további információt. | Nem kötelező.
SplashDuration | Szám | Az Intune kezdőképernyő megjelenésének minimális időtartama (másodpercben) az alkalmazás indításakor. Az alapértelmezett érték 1.5. | Nem kötelező.
BackgroundColor| Karakterlánc| A kezdő és a PIN-kód bevitelére szolgáló képernyő háttérszínét adja meg. Hexadecimális RGB-karakterláncot fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jelet ki lehet hagyni.   | Nem kötelező; az alapértelmezése a világosszürke szín.
ForegroundColor| Karakterlánc| A kezdő és a PIN-kód bevitelére szolgáló képernyő előtérszínét (például szövegszínét) adja meg. Hexadecimális RGB-karakterláncot fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jelet ki lehet hagyni.  | Nem kötelező; az alapértelmezése a fekete szín.
AccentColor | Karakterlánc| A PIN-kód megadására szolgáló képernyő kiemelőszínét (például a gombszöveg színét és a mezők kijelölésének színét) adja meg.  Hexadecimális RGB-karakterláncot fogad el „#XXXXXX” alakban, amelyben az X-ek helyén számjegy (0–9), illetve és A és F közötti nagybetű állhat. A kettőskereszt jelet ki lehet hagyni.| Nem kötelező; az alapértelmezése a rendszer kék színe.
MAMTelemetryDisabled| Logikai| Az adható meg vele, hogy az SDK ne küldjön telemetriai adatokat vissza a háttérrendszerének| Nem kötelező.
MAMTelemetryUsePPE | Logikai | Azt adja meg, hogy az SDK küldjön-e adatokat az üzem előtti környezet (PPE) háttérrendszerének. Akkor használja ezt a beállítást, ha teszteli az alkalmazásokat az Intune szabályzatával. Megakadályozhatja vele, hogy a teszt telemetriai adatai keveredjenek az ügyfelek adataival. | Nem kötelező.

## <a name="telemetry"></a>Telemetria

Az iOS-hoz készült Intune App SDK alapértelmezés szerint naplózza a használati eseményekkel kapcsolatos telemetriai adatokat, amelyeket a rendszer elküld a Microsoft Intune-nak. A rendszer a következő használati események adatait naplózza:

1. **Az alkalmazások indítása:** a Microsoft Intune tájékozódhat a különböző felügyeleti típusú MAM-kompatibilis alkalmazások használatáról (MAM az MDM-mel, MAM MDM-regisztráció nélkül stb.).

2. **EnrollApplication API-hívás:** a Microsoft Intune a sikerességi arányról és az `enrollApplication` ügyféloldali hívásainak egyéb teljesítménymutatóiról is gyűjt információkat.

**Megjegyzés:** ha nem kíván az Intune App SDK-ból származó telemetriai adatokat küldeni a Microsoft Intune-nak a mobilalkalmazásról, le kell tiltania az Intune App SDK-ban a telemetria-rögzítést. Ehhez állítsa a `MAMTelemetryDisabled` tulajdonság értékét „YES”-re az IntuneMAMSettings beállításaiban.





## <a name="enable-multi-identity-optional"></a>A többszörös identitás engedélyezése (nem kötelező)

Az SDK alapértelmezés szerint az alkalmazás egészére alkalmazza a szabályzatot. A többszörös identitás a MAM funkciója, amelynek engedélyezése esetén identitásonként alkalmazhatók a szabályzatok.  Ebből az alkalmazásnak nagyobb részt kell vállalnia, mint a MAM többi funkciójából.

Az alkalmazásnak tájékoztatnia kell az alkalmazás SDK-t, ha módosítani szándékozik az aktív identitást. Az SDK is értesíti az alkalmazást, ha identitásváltás szükséges. Jelenleg csak egy felügyelt identitás támogatott. Ha a felhasználó már regisztrált az eszközt vagy az alkalmazást, az SDK ezt az identitást használja, és ezt tekinti az elsődleges felügyelt identitásnak. Az alkalmazás többi felhasználójával nem felügyeltként bánik, szabályzatbeállításaik korlátlanok.

Felhívjuk, hogy az identitás egyszerűen egy karakterláncként van definiálva. Az identitásokban nem számítanak különbözőnek a kis- és a nagybetűk, és az SDK nem feltétlen olyan kis- és nagybetűkkel adja vissza a tőle kért identitásokat, mint ahogyan az az identitás beállításakor eredetileg meg volt adva.


### <a name="overview"></a>Áttekintés

Az identitás egyszerűen egy fiók felhasználóneve (például user@contoso.com). A fejlesztők a következő szinteken állíthatják be az alkalmazás identitását:

* **Folyamat identitása**: a folyamat identitása a folyamat szintjén állítja be az identitást, és főképpen egyidentitású alkalmazások esetében használatos. Ez az identitás hatással van minden műveletre, a fájlműveletekre és a felhasználói felületi műveletekre is.
* **Felhasználói felület identitása**: azt határozza meg, hogy milyen szabályzatok alkalmazandók a főszálban végzett felhasználói felületi műveletekre, például a kivágásra, a másolásra, a beillesztésre, a PIN-kód megadására, a hitelesítésre, az adatmegosztásra stb. A felhasználói felület identitása nincs hatással a fájlműveletekre (titkosítás, biztonsági mentés stb.).
* **Szál identitása**: a szál identitása azt határozza meg, hogy milyen szabályzatok alkalmazandók az aktuális szálra. Hatással van minden műveletre, a fájlműveletekre és a felhasználói felületi műveletekre is.

Az identitás helyes beállítása az alkalmazás feladata, függetlenül attól, hogy felügyelt felhasználóról van-e szó vagy sem.

Minden szálnak minden pillanatban van egy effektív identitása mind a felhasználói felületi műveletekre, mind a fájlműveletekre vonatkozóan. A rendszer ennek az identitásnak az alapján határozza meg, hogy kell-e alkalmazni szabályzatokat, és ha igen, milyeneket. Ha az identitás „no identity”, vagy ha nem felügyelt felhasználóról van szó, a rendszer nem alkalmaz szabályzatokat.



### <a name="thread-queues"></a>Szálak várólistái

Az alkalmazások gyakran indítanak aszinkron és szinkron feladatokat a szálak várólistáinak. Az SDK elfogja a Grand Central Dispatch (GCD) típusú hívásokat, és az aktuális szál identitását társítja az indított hívásokhoz. A feladatok végrehajtásakor az SDK átmenetileg módosítja a szál identitását a feladathoz társított identitásra, végrehajtja a feladatokat, majd visszaállítja a szál eredeti identitását. Tekintettel arra, hogy az `NSOperationQueue` a GCD-re épül, az `NSOperations` műveletek azzal az identitással futnak, amely a szál identitása volt a műveletnek az `NSOperationQueue` várólistába való felvételekor. Az `NSOperations` műveletek és a GCD segítségével közvetlenül indított függvények módosíthatják is a szál aktuális identitását, amikor futnak. Ez az identitás felülbírálja az indító száltól örökölt identitást.

### <a name="file-owner"></a>A fájl tulajdonosa

Az SDK nyilvántartja a helyi fájltulajdonos identitását, és annak megfelelően alkalmazza a szabályzatokat. A fájlhoz a létrehozásakor vagy csonkolási módban való megnyitásakor rendeli hozzá a tulajdonost a rendszer. A tulajdonost a műveletet végrehajtó szál effektív fájlműveleti identitására állítja be a rendszer. Az alkalmazások explicit módon is megadhatják a fájl tulajdonosát az `IntuneMAMFilePolicyManager` segítségével. Az alkalmazások az `IntuneMAMFilePolicyManager` segítségével kérhetik be a fájl tulajdonosát, és állíthatják be a felhasználói felület identitását a fájl tartalmának megjelenítése előtt.


### <a name="shared-data"></a>Megosztott adatok

Ha az alkalmazás olyan fájlokat hoz létre, amelyek felügyelt és nem felügyelt felhasználóktól származó adatokat is tartalmaznak, akkor az alkalmazás feladata, hogy titkosítsa a felügyelt felhasználó adatait. Az adatok az `IntuneMAMDataProtectionManager` `protect` és `unprotect` API-jával titkosíthatók. A `protect` metódus egy identitást fogad el paraméterként. Ez lehet felügyelt és nem felügyelt felhasználó is. Felügyelt felhasználó esetén titkosítja az adatokat. Nem felügyelt felhasználó esetén egy az identitást kódoló fejlécet ad hozzá az adatokhoz, de nem titkosítja az adatokat.  A `protectionInfo` metódussal lehet bekérni az adat tulajdonosát.

### <a name="share-extensions"></a>Megosztási bővítmények

Ha az alkalmazás megosztási bővítményt tartalmaz, a megosztás alatt álló elem tulajdonosa az `IntuneMAMDataProtectionManager` `protectionInfoForItemProvider` metódusával kérhető be. Ha a megosztott elem fájl, az SDK kezeli a fájl tulajdonosának beállítását. Ha a megosztott elem adat, az alkalmazás feladata, hogy beállítsa a fájl tulajdonosát (ha az adatot fájlba menti az alkalmazás), és meghívja az (alább ismertetett) `setUIPolicyIdentity` API-t, mielőtt megjeleníti ezt az adatot a felhasználói felületen.

### <a name="turn-on-multi-identity"></a>A többszörös identitás bekapcsolása

Az alkalmazások alapértelmezés szerint egyetlen identitásnak minősülnek, és a folyamat identitását az SDK által regisztrált felhasználóra állítja a rendszer. A többszörös identitás támogatás engedélyezéséhez a `MultiIdentity` nevű és „YES” értékű beállítást kell felvenni az alkalmazás Info.plist fájljába, az **IntuneMAMSettings** szótárba.

> [!NOTE]
> Ha engedélyezve van a többszörös identitás, a folyamat identitása, a felhasználói felület identitása és a szálak identitása nil lesz. Ezek helyes beállítása az alkalmazás feladata.


### <a name="switching-identities"></a>Identitásváltás

* **Az alkalmazás által kezdeményezett identitásváltás**:

    A többszörös identitású alkalmazásokat az indításkor ismeretlen, nem felügyelt fiókkal futó alkalmazásnak tekinti a rendszer. A feltételes indítási felhasználói felület nem fut le, és a szabályzatokat sem foganatosítja a rendszer az alkalmazásra. Az alkalmazás feladata, hogy értesítse az SDK-t minden alkalommal, amikor módosítani kell az identitást. Erre általában olyankor kerül sor, amikor az alkalmazás arra készül, hogy adatokat jelenítsen meg egy bizonyos felhasználói fióknak.

    Ilyen például, amikor a felhasználó megpróbál megnyitni egy dokumentumot, egy postaládát vagy egy jegyzetfüzet egy lapját. Az alkalmazásnak értesítenie kell az SDK-t, mielőtt ténylegesen megnyitja a fájlt, a postaládát vagy a lapot. Ez a `IntuneMAMPolicyManager` `setUIPolicyIdentity` API-jával történik. Ezt az API-t kell meghívni attól függetlenül, hogy felügyelt vagy nem felügyelt felhasználóról van-e szó,. Ha a felhasználó felügyelt, az SDK elvégzi a feltételes indítás ellenőrzését (jailbreakészlelés, PIN-kód, hitelesítés stb.). Az identitásváltás eredményét aszinkron módon, egy befejezéskezelővel adja vissza. Az alkalmazásnak el kell halasztania a dokumentum, postaláda, lap stb. megnyitását mindaddig, amíg sikert jelző eredménykódot nem kap vissza. Ha az identitásváltás sikertelen, az alkalmazásnak vissza kell vonnia a műveletet.

* **Az SDK által kezdeményezett identitásváltás**:

    Vannak esetek, amikor az SDK-nak meg kell kérnie az alkalmazást, hogy váltson át egy bizonyos identitásra. A többszörös identitású alkalmazásoknak meg kell valósítaniuk az `IntuneMAMPolicyDelegate` `identitySwitchRequired` metódusát ahhoz, hogy kezelni tudják az ilyen kérést. Ha az alkalmazás kezelni tudja a megadott identitásra való átváltási kérést, akkor az `IntuneMAMAddIdentityResultSuccess` értéket kell átadnia a befejezéskezelőbe. Ha az alkalmazás nem tudja kezelni az identitásváltást, akkor az `IntuneMAMAddIdentityResultFailed` értéket kell átadnia a befejezéskezelőbe. Az alkalmazásnak nem kell meghívnia az `setUIPolicyIdentity` metódust erre a hívásra válaszul. Ha az SDK-nak arra kell megkérnie az alkalmazást, hogy egy nem felügyelt felhasználói fiókra váltson, akkor az üres karakterláncot adja át az `identitySwitchRequired` hívásban.

* **Szelektív törlés**:

    Az alkalmazás szelektív törlése esetén az SDK a `IntuneMAMPolicyDelegate` `wipeDataForAccount` metódusát hívja meg. Az alkalmazás felelős azért, hogy törölje a felhasználó fiókját és a hozzá kapcsolódó adatokat. Az SDK képes arra, hogy töröljön minden fájlt, amely a felhasználó tulajdonában van. Akkor teszi ezt, ha az alkalmazás a „FALSE” eredményt adja vissza a `wipeDataForAccount` hívásból. Megjegyzendő, hogy ennek a metódusnak a hívása a háttérszálból történik, és az alkalmazásnak mindaddig nem szabad visszatérnie, amíg meg nem történt a felhasználó minden adatának törlése (a fájlok kivételével, ha az alkalmazás a „FALSE” értéket adja vissza).

## <a name="debug-the-intune-app-sdk-in-xcode"></a>Intune App SDK-hibakeresés Xcode-ban

A MAM-kompatibilis alkalmazások Microsoft Intune-beli manuális tesztelése előtt használhatja az Xcode-ban a **Settings.bundle** fájlt. Ez lehetővé teszi a tesztszabályzatok beállítását az Intune elérése nélkül. Az engedélyezéshez tegye a következőket:

* Vegye fel a Settings.bundle fájlt a projekt legfelső mappájára jobb gombbal kattintva. Válassza a „Hozzáadás -> Új fájl” lehetőséget a menüből. Válassza a „Források” alatt található „Settings Bundle" nevű sablont, és vegye fel.

* Ha hibakeresési buildet használ, másolja a MAMDebugSettings.plist fájlt a Settings.bundle csomagba.

* A Settings.bundle csomagban megtalálható Root.plist fájlba vegyen fel egy preference bejegyzést, amelynél a Type=Child Pane, és FileName=MAMDebugSettings.

* A **Settings (Beállítások) > Az alkalmazás neve** területen kapcsolja be az „Enable Test Policies (Tesztszabályzatok engedélyezése)” beállítást.

* Indítsa el az alkalmazást (az Xcode-on kívül vagy belül).

* A **Settings > Az alkalmazás neve -> Enable Test Policies** területen kapcsolja be például a „PIN” szabályzatot.

* Indítsa el az alkalmazást (az Xcode-on kívül vagy belül). Ellenőrizze, hogy a PIN-kód megfelelően működik-e.

> [!NOTE]
> Most már használhatja a **Settings -> Az alkalmazás neve -> Enable Test Policies** lehetőséget a beállítások ki- és bekapcsolására.

## <a name="recommended-ios-best-practices"></a>Ajánlott gyakorlati tanácsok iOS-ben

Az alábbiakban néhány gyakorlati tanácsot ajánlunk az iOS-alapú fejlesztéshez:

Az iOS fájlrendszere megkülönbözteti a kis-és nagybetűket. Győződjön meg arról, hogy a megfelelő betűk szerepelnek a fájlnevekben, például a `libIntuneMAM.a` és `IntuneMAMResources.bundle`.

Ha az Xcode nem találja a `libIntuneMAM.a`könyvtárat, a problémát megoldhatja a könyvtár elérési útjának keresőútvonalakba való felvételével.



## <a name="faq"></a>Gyakori kérdések

 **Az alkalmazásom minden felhasználóját regisztrálni kell a MAM-szolgáltatásban?**

Nem.  Valójában csak a munkahelyi vagy iskolai fiókokat kell regisztrálni az Intune App SDK-ban.  Az alkalmazások feladata azt eldönteni, hogy egy fiók munkahelyi, illetve iskolai környezetben használatos-e.   

**Mi a teendő az olyan felhasználókkal, akik már bejelentkeztek az alkalmazásba?  Regisztrálni kell őket?**

Az alkalmazás feladata ugyan regisztrálni a felhasználókat, miután sikeresen túlestek a hitelesítésen, az is feladata, hogy regisztráljon minden olyan meglévő fiókot, amely már jelen volt, még mielőtt az alkalmazás kiegészült a MDM nélküli MAM funkcióval.   


Erre a célra az alkalmazásnak a `registeredAccounts:` metódust kell használnia.  Ez a metódus egy NSDictionary értéket ad vissza, amely tartalmaz minden, az Intune MAM szolgáltatásban regisztrált fiókot.  Ha nem szerepel a listában egy az alkalmazásban már meglévő fiók, akkor az alkalmazásnak regisztrálnia kell a `registerAndEnrollAccount:` metódussal:




**Milyen gyakran próbálkozik újra az SDK a regisztrációval?**

Az SDK 24 órás időközönként automatikusan újrapróbálkozik minden korábban sikertelen regisztrációval.  Az SDK azért teszi ezt, hogy ha egy felhasználó szervezete azután aktiválta a MAM szolgáltatást, hogy a felhasználó bejelentkezett az alkalmazásba, a felhasználó akkor is sikeresen regisztráljon, és megkapja a szabályzatokat.

Az SDK felhagy az újrapróbálkozással, ha azt észleli, hogy a felhasználó sikeresen regisztrálta az alkalmazást.  Ez azért van így, mert egy időpontban csak egy felhasználó regisztrálhat egy alkalmazást. A felhasználó regisztrációjának visszavonása esetén újrakezdődnek az ismételt próbálkozások, ugyanolyan 24 órás időközzel.


**Miért kell megszüntetni a felhasználó regisztrációját?**

Az SDK a következő műveleteket végzi el a háttérben, rendszeres időközönként:

 - Ha az alkalmazás még nincs regisztrálva, 24 óránként megpróbál regisztrálni minden regisztrált fiókot.
 - Ha az alkalmazás regisztrálva van, az SDK 8 óránként keresi meg a MAM-szabályzat esetleges frissítéseit.

A felhasználó regisztrációjának megszüntetésével értesíti az SDK-t arról, hogy a felhasználó ezentúl nem fogja használni az alkalmazást, és hogy az SDK beszüntetheti az adott felhasználói fiók esetében a fenti rendszeres műveleteket.  Az alkalmazás regisztrációjának visszavonását, és ha szükséges, az adatok szelektív törlését is kezdeményezi.

**True értékre állítsam a doWipe jelzőt a regisztrációt megszüntető metódusban?**
Ezt a metódust még azelőtt kell meghívni, hogy a felhasználót kijelentkezteti az alkalmazásból.  Ha a kijelentkezés részeként törli a felhasználó adatait az alkalmazásból, akkor a `doWipe` jelző false-ra állítható.  Ha viszont az alkalmazás nem törli a felhasználó adatait, akkor a jelzőt true-ra kell állítani, hogy az SDK maga törölje az adatokat.

**Vannak más módszerek az alkalmazások regisztrációjának megszüntetésére?**
Igen, a rendszergazda elküldhet egy szelektív törlési parancsot az alkalmazásnak. Ez azt eredményezi, hogy megszűnik a felhasználó regisztrációja az alkalmazásban és a szolgáltatásban, és törlődnek az adatai.  Az SDK automatikusan kezeli ezt a helyzetet, és a regisztrációt megszüntető delegáltmetóduson keresztül küld értesítést.

## <a name="submitting-your-app-to-the-app-store"></a>Az alkalmazás beküldése az App Store-ba
Az Intune App SDK statikus erőforrástár és keretrendszer buildje is univerzális bináris, ami azt jelenti, hogy minden eszköz- és szimulátorarchitektúra kódját tartalmazza. Az Apple elutasítja az App Store-ba beküldött alkalmazásokat, ha szimulátorkódot tartalmaznak. Ha a statikus erőforrástáron alapuló fordítást végez csak eszközön használható build elkészítésére, akkor a csatoló automatikusan törli a szimulátorkódot.

Ha az alkalmazás az Intune App SDK **keretrendszer buildjét** használja, manuálisan kell eltávolítania a szimulátorarchitektúrákat az univerzális keretrendszerből, mielőtt beküldi az alkalmazást az App Store-ba. Az alábbi útmutatás segít ezt elvégezni:

1. Ügyeljen rá, hogy az `IntuneMAM.framework` az asztalon legyen.
2. Futtassa a következő parancsokat:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    Az első parancs törli a szimulátorarchitektúrákat a keretrendszer dylibjéből.
    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    A második parancs másolja a csak eszközökhöz kapcsolódó dylibet a keretrendszer könyvtárába.



<!--HONumber=Nov16_HO3-->



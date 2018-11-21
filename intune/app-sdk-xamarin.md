---
title: Microsoft Intune App SDK Xamarin Bindings
description: Az Intune App SDK Xamarin Bindings lehetővé teszik az Intune alkalmazásvédelmi szabályzatok használatát a Xamarinnal készített iOS- és Android-alkalmazásokban.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: d8e9dd1e38fdc693bd30372f2961244e4e809771
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180340"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lehetővé teszi az [Intune alkalmazásvédelmi szabályzatok](app-protection-policy.md) használatát a Xamarinnal készített iOS- és Android-alkalmazásokban. A kötések lehetővé teszik a fejlesztők számára, hogy Intune alkalmazásvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

A Microsoft Intune App SDK Xamarin Bindings lehetővé teszi, hogy Intune alkalmazásvédelmi szabályzatokat (vagy más néven alkalmazás- vagy MAM-szabályzatokat) építsen be a Xamarinnal fejlesztett alkalmazásokba. A MAM-kompatibilis alkalmazás az, amelyik integrálva van az Intune App SDK-val. Mindez lehetővé teszi a rendszergazdáknak, hogy alkalmazásvédelmi szabályzatokat telepítsenek a mobilalkalmazásra vonatkozóan, ha az Intune aktívan felügyeli az alkalmazást.

## <a name="whats-supported"></a>Támogatott források és műveletek

### <a name="developer-machines"></a>Fejlesztői gépek
* Windows (Visual Studio version 15.7+)
* macOS

### <a name="mobile-app-platforms"></a>Mobilalkalmazás-platformok
* Android
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Intune mobilalkalmazás-kezelési helyzetek

* Intune APP-WE (eszközregisztráció nélkül)
* Intune MDM által regisztrált eszközök
* Külső EMM által regisztrált eszközök

Az Intune App SDK Xamarin Bindingsszal létrehozott Xamarin-alkalmazásokra mostantól alkalmazhatók az Intune alkalmazásvédelmi szabályzatai az Intune mobileszköz-felügyeletében (MDM) regisztrált eszközökön és a nem regisztrált eszközökön is.

## <a name="prerequisites"></a>Előfeltételek

A [licencfeltételek](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) áttekintése. Nyomtassa ki és őrizze meg a licencfeltételeket. Az Intune App SDK Xamarin Bindings letöltésével és használatával elfogadja licencfeltételeket. Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.

Az SDK támaszkodik [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) számára annak [hitelesítési](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) és feltételes indítási forgatókönyvek, melyek konfigurálhatók, az alkalmazásokat szükség [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése az iOS-mobilalkalmazásban
1. Adja hozzá Xamarin.iOS-projektjéhez a [Microsoft.Intune.MAM.Xamarin.iOS NuGet-csomagot](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS).
2.  Kövesse az Intune App SDK iOS-mobilalkalmazásokba való integrálásához szükséges általános lépéseket. Kezdhet az [iOS-hez készült Intune App SDK – fejlesztői útmutató](app-sdk-ios.md#build-the-sdk-into-your-mobile-app) című témakör integrálási útmutatásának 3. lépésével. Az IntuneMAMConfigurator futtatásáról szóló szakasz utolsó lépését átugorhatja, mivel az eszköz része a Microsoft.Intune.MAM.Xamarin.iOS csomagnak, és a build időpontjában automatikusan futtatva lesz.
    **Fontos**: A kulcslánc megosztásának alkalmazások számára való engedélyezése kissé eltérő a Visual Studióban és az Xcode-ban. Nyissa meg az alkalmazás jogosultságokat tartalmazó plist-fájlját, és győződjön meg arról, hogy az „Enable Keychain” („Kulcslánc engedélyezése”) lehetőség engedélyezve van, és hogy ebben a szakaszban a megfelelő kulcslánc-megosztási csoportok szerepelnek. Ezután győződjön meg arról, hogy a projekt „iOS Bundle Signing” („iOS-kötegaláírási”) beállításai között a konfigurációk és platformok összes megfelelő kombinációjához meg van adva a jogosultságokat tartalmazó plist-fájl a „Custom Entitlements” („Egyéni jogosultságok”) mezőben.
3.  Miután hozzáadta a kötéseket, és megfelelően konfigurálta az alkalmazást, az alkalmazás megkezdheti az Intune SDK API-jának használatát. Ehhez a következő névteret kell hozzáadnia:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Az alkalmazásvédelmi szabályzatok fogadásának megkezdéséhez az alkalmazást regisztrálni kell az Intune MAM szolgáltatásban. Ha az alkalmazás nem az [Azure Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) vagy a [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) tárral hitelesíti a felhasználókat, Ön pedig ezt az Intune SDK-val szeretné kezelni, az alkalmazásnak át kell adnia a felhasználó egyszerű felhasználónevét az IntuneMAMEnrollmentManager LoginAndEnrollAccount metódusának:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Az alkalmazások üres értékűek is lehetnek, ha a felhasználó egyszerű felhasználóneve ismeretlen a hívás idején. Ebben az esetben a rendszer az e-mail-címet és a jelszót kéri a felhasználóktól.
      
      Ha az alkalmazás már az ADA vagy az MSAL segítségével hitelesíti a felhasználókat, egyszeri bejelentkezést (SSO) konfigurálhat az alkalmazás és az Intune SDK között. Elsőként konfigurálnia kell az ADAL/MSAL szolgáltatást a tokenek az iOS-es Intune Xamarin-kötések által is használt ugyanazon kulcslánc-hozzáférési csoport használatára (com.microsoft.adalcache). Az ADAL esetében ehhez az [AuthenticationContext KeychainSecurityGroup tulajdonságát kell beállítania](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications). Az MSAL esetében ehhez a [PublicClientApplication KeychainSecurityGroup tulajdonságát kell beállítania](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios). Ezután felül kell bírálnia az Intune SDK alapértelmezett AAD-beállításait az alkalmazáséival. Ezt az alkalmazás Info.plist fájljában található IntuneMAMSettings szótárban teheti meg az [iOS-hez készült Intune App SDK – fejlesztői útmutató](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk) című témakörben leírtaknak megfelelően, vagy használhatja az IntuneMAMPolicyManager-példány AAD-felülbírálási tulajdonságait. Az Info.plist fájlt alkalmazó módszer használata ajánlott az olyan alkalmazások esetében, melyek ADAL-beállításai statikusak, míg a felülbírálási tulajdonságok használata ajánlott olyan alkalmazások esetében, melyek futásidőben határozzák meg ezeket az értékeket. Az SSO-beállítások konfigurálása után az alkalmazásnak a sikeresen hitelesítést követően át kell adnia a felhasználó egyszerű felhasználónevét az IntuneMAMEnrollmentManager RegisterAndEnrollAccount metódusának:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Az alkalmazások meghatározhatják a regisztrációs kísérleteke eredményeit az EnrollmentRequestWithStatus metódus az IntuneMAMEnrollmentDelegate egyik alosztályában való alkalmazásával, valamint az IntuneMAMEnrollmentManager Delegate tulajdonságának az osztály egyik példányához való beállításával. Erről példát a [Xamarin.iOS-mintaalkalmazásban](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) találhat.

      Sikeres regisztráció esetén az alkalmazások meghatározhatják a regisztrált fiók egyszerű felhasználónevét a következő tulajdonság lekérdezésével (amennyiben azt addig nem ismerték): 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> iOS rendszerre nincs remapper. A Xamarin.Forms-alkalmazásokba való integrálásnak ugyanúgy kell történnie, mint általában a Xamarin.iOS-projektek esetén. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése Androidos mobilalkalmazásban

Olyan Xamarin-alapú androidos alkalmazások esetén, amelyek nem használnak felhasználóifelület-keretrendszert, olvassa el és kövesse az [Androidhoz készült Intune App SDK fejlesztői útmutatójában](app-sdk-android.md) leírtakat. Xamarin-alapú Android-alkalmazások, osztály, a metódusok és a tevékenységek lecserélése a MAM-megfelelőikre alapján kell a [osztályt és metódust cseréjére tábla](app-sdk-android.md#class-and-method-replacements) az útmutatóban. Ha az alkalmazás nem rendelkezik meghatározott `android.app.Application` osztállyal, akkor hozzon létre egyet, és győződjön meg arról, hogy az a `MAMApplication` osztálytól örököl. Az ADAL konfigurációs értékek közlik az SDK az AndroidManifest metaadatain keresztül közli. Olvassa el dokumentációnkat, amelyből megtudhatja, hogyan [konfigurálhatja az ADAL-t az alkalmazásához](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="xamarinandroid-integration"></a>Xamarin.Android-integráció

1. Adja hozzá Xamarin.Android-projektjéhez a [Microsoft.Intune.MAM.Xamarin.Android NuGet-csomag](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) legfrissebb verzióját. Ezzel elérhetővé válnak az Intune alkalmazáshoz való engedélyezéséhez szükséges hivatkozások.

2. Olvassa el és kövesse [A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek](app-sdk-android.md) című cikk lépéseit, és fordítson kiemelt figyelmet a következő szakaszokra:

    1. A [teljes osztályok és metódusok lecserélése szakasz](app-sdk-android.md#class-and-method-replacements). 
    2. A [MAMApplication szakasz](app-sdk-android.md#mamapplication). Ügyeljen rá, hogy az alosztály megfelelően jelölve legyen a `[Application]` attribútummal, és felülbírálja a `(IntPtr, JniHandleOwnership)` konstruktort.
    3. Az [ADAL-integráció szakaszt](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) amennyiben az alkalmazás AAD-ben történő hitelesítést is végrehajt. 
    4. A [MAM-WE regisztrációs szakaszt](app-sdk-android.md#app-protection-policy-without-device-enrollment) ha az alkalmazás a MAM-szolgáltatásból fog lekérni szabályzatot.

> [!NOTE]
> Ha az [A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek](app-sdk-android.md) alapján keres egyenértékű API-kat a `Microsoft.Intune.MAM.Xamarin.Android` kötések között, vagy amikor az útmutatóból konvertál kódrészleteket, akkor ügyeljen rá, hogy a Xamarin kötésgenerátora a következő jelentős módokon módosítja az Android-API-kat:
> * Az összes azonosító Pascal case írásmódra módosul (com.foo.bar -> Com.Foo.Bar)
> * Minden get/set művelet tulajdonság típusú műveletté lesz konvertálva (pl. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Minden interfész neve elé be lesz illesztve az 'I' karakter (FooInterface -> IFooInterface)

### <a name="xamarinforms-integration"></a>Xamarin.Forms-integráció

**Az előző lépések végrehajtása mellett** a `Xamarin.Forms`-alkalmazásokhoz egy `Microsoft.Intune.MAM.Remapper`-csomagot is elérhetővé tettünk. Ez a csomag úgy cseréli le az osztályokat, hogy `MAM`-osztályokat injektál az olyan gyakran használt `Xamarin.Forms`-osztályok osztályhierarchiájába mint a `FormsAppCompatActivity` és a `FormsApplicationActivity`, így nyugodtan használhatja osztályait továbbra is, csupán felülbírálást kell biztosítania az olyan MAM-kompatibilis funkcióknak, mint a `OnMAMCreate` és a `OnMAMResume`. A használatához hajtsa végre a következőket:

1.  Projektjéhez adja hozzá a [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet-csomagot. Ezzel automatikusan hozzáadhatja az Intune APP SDK Xamarin-kötéseit, ha esetleg még nem adta volna őket meg.

2.  Adjon hozzá egy `Xamarin.Forms.Forms.Init(Context, Bundle)`-hívást a 2.2-es lépésnél létrehozott `MAMApplication`-osztály `OnMAMCreate`-funkciójához. Erre azért van szükség, mert az Intune-felügyelet használata esetén az alkalmazás a háttérben is elindítható.

> [!NOTE]
> Mivel ez a művelet felülír egy olyan függőséget, amit a Visual Studio az Intellisense automatikus kiegészítéshez használ, lehet, hogy újra kell indítania a Visual Studiot a remapper eszköz első futtatását követően ahhoz, hogy az Intellisense felismerje a változtatásokat. 

Elvégezte az összetevő alkalmazásba történő beépítésének alapvető lépéseit. Következőnek kövesse a Xamarin-alapú Android-mintaalkalmazásban lévő lépéseket. Két mintát biztosítottunk, egyet a Xamarin.Forms-hoz és egyet az Androidhoz.

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Intune alkalmazásvédelmi szabályzatok megkövetelése a Xamarin-alapú Android LOB-alkalmazások (nem kötelező) használatához 

A következő útmutatóból megtudhatja, hogyan biztosíthatja, hogy a Xamarin-alapú androidos üzletági alkalmazásokat csak az Intune által védett felhasználók használhassák eszközeiken. 

### <a name="general-requirements"></a>Általános követelmények
* Győződjön meg arról, a Xamarin-alkalmazás engedélyt az alkalmazásvédelmi szabályzat (alkalmazás) app Service lépéseit követi. Útmutatásait a [első lépések az Intune SDK útmutatóját](app-sdk-get-started.md#next-steps-after-integration) alatt "az alkalmazás hozzáférést biztosít az Intune app protection szolgáltatás (nem kötelező)". 
    
### <a name="working-with-the-intune-sdk"></a>Az Intune SDK használata
Ezek az utasítások minden olyan Android- és Xamarin-alkalmazásra vonatkoznak, amelyek Intune-alkalmazásvédelmi szabályzatokat szeretnének kérni a végfelhasználói eszközöktől.

1. Konfigurálja az ADAL-t az [Androidos Intune SDK útmutatójában](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) megadott lépések alapján.
> [!NOTE] 
> Az alkalmazáshoz tartozó „ügyfél-azonosító” kifejezés megfelel az Azure Portalon az „alkalmazásazonosító” kifejezésnek. 
* Az SSO engedélyezéséhez a 2. „Common ADAL configurationre” van szükség.

2. Az alapértelmezett regisztráció engedélyezéséhez írja az alábbi értéket a jegyzékfájlba: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> Ez lehet az alkalmazás egyetlen MAM-WE-integrációja. Ha az alkalmazás többször próbál meg MAMEnrollmentManager API-kat hívni, problémák merülhetnek fel.

3. A MAM-szabályzat engedélyezéséhez írja az alábbi értéket a jegyzékfájlba: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> Ez kényszeríti az alkalmazást, hogy letöltse a Céges portált az eszközre, és a használat előtt elvégezze az alapértelmezett regisztrációt.

### <a name="working-with-adal"></a>Az ADAL használata
Ezek az utasítások minden olyan .NET- és Xamarin-alkalmazásra vonatkoznak, amelyek Intune-alkalmazásvédelmi szabályzatokat használatát követelik meg a végfelhasználói eszközökön.

1. Kövesse az ADAL dokumentációjában a [Brokered Authentication for Android](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/tree/dev/adal#brokered-authentication-for-android) (Közvetített hitelesítés az Androidhoz) szakaszban meghatározott lépéseket.
> [!NOTE] 
> A .NET ADAL által kibocsátott következő verzió (3.17.4) várhatóan tartalmazni fogja az ennek a működéséhez szükséges javítást.

## <a name="support"></a>Support
Ha vállalata már Intune-ügyfél, akkor a Microsoft támogató szolgálat képviselőjével együttműködve nyisson meg egy támogatási jegyet, és hozzon létre bejelentést [a GitHub hibabejelentő oldalán](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), mi pedig segítünk, amint tudunk. 

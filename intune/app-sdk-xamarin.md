---
title: Microsoft Intune App SDK Xamarin Bindings
description: Az Intune App SDK Xamarin Bindings lehetővé teszik az Intune alkalmazásvédelmi szabályzatok használatát a Xamarinnal készített iOS- és Android-alkalmazásokban.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 421dede4b0da71fe04649e21bfcf7c15d2270507
ms.sourcegitcommit: 399f34cd169e2e352b49aad1dcb7e88294a4a9f1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37869355"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lehetővé teszi az [Intune alkalmazásvédelmi szabályzatok](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) használatát a Xamarinnal készített iOS- és Android-alkalmazásokban. A kötések lehetővé teszik a fejlesztők számára, hogy Intune alkalmazásvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

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

* **[Csak az Android esetében]** Az eszközön a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni.

## <a name="get-started"></a>Első lépések

1. Olvassa el Microsoft Intune MAM Xamarin összetevő [licencfeltételeit](https://components.xamarin.com/license/microsoft.intune.mam).

2.  Töltse le az Intune App SDK Xamarin Component mappát a [GitHubról](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) vagy a [Nuget.orgról](https://www.nuget.org/profiles/msintuneappsdk), és csomagolja ki. Az 1. és a 3. lépésben letöltött fájlnak ugyanazon a könyvtárszinten kell lennie.

3.  Futtassa rendszergazdaként a következő parancsot a parancssorban: `Xamarin.Component.exe install <.xam> file`.

4.  A Visual Studióban kattintson a jobb gombbal a korábban létrehozott Xamarin-projektben a **components** (összetevők) elemre.

5.  Válassza az **Edit Components** (Összetevők szerkesztése) lehetőséget, és vegye fel az Intune App SDK összetevőt, amelyet helyileg töltött le a számítógépére.

A [licencfeltételek](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) áttekintése. Nyomtassa ki és őrizze meg a licencfeltételeket. Az Intune App SDK Xamarin Bindings letöltésével és használatával elfogadja licencfeltételeket. Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése az iOS-mobilalkalmazásban
1. Adja hozzá Xamarin.iOS-projektjéhez a [Microsoft.Intune.MAM.Xamarin.iOS NuGet-csomagot](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS).
2.  Kövesse az Intune App SDK iOS-mobilalkalmazásokba való integrálásához szükséges általános lépéseket. Kezdhet az [iOS-hez készült Intune App SDK – fejlesztői útmutató](app-sdk-ios.md#build-the-sdk-into-your-mobile-app) című témakör integrálási útmutatásának 3. lépésével. Az IntuneMAMConfigurator futtatásáról szóló szakasz utolsó lépését átugorhatja, mivel az eszköz része a Microsoft.Intune.MAM.Xamarin.iOS csomagnak, és a build időpontjában automatikusan futtatva lesz.
    **Fontos**: A kulcslánc megosztásának alkalmazások számára való engedélyezése kissé eltérő a Visual Studióban és az Xcode-ban. Nyissa meg az alkalmazás jogosultságokat tartalmazó plist-fájlját, és győződjön meg arról, hogy az „Enable Keychain” („Kulcslánc engedélyezése”) lehetőség engedélyezve van, és hogy ebben a szakaszban a megfelelő kulcslánc-megosztási csoportok szerepelnek. Ezután győződjön meg arról, hogy a projekt „iOS Bundle Signing” („iOS-kötegaláírási”) beállításai között a konfigurációk és platformok összes megfelelő kombinációjához meg van adva a jogosultságokat tartalmazó plist-fájl a „Custom Entitlements” („Egyéni jogosultságok”) mezőben.
3.  Miután hozzáadta a kötéseket, és megfelelően konfigurálta az alkalmazást, az alkalmazás megkezdheti az Intune SDK API-jának használatát. Ehhez a következő névteret kell hozzáadnia:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Az alkalmazásvédelmi szabályzatok fogadásának megkezdéséhez az alkalmazást regisztrálni kell az Intune MAM szolgáltatásban. Ha az alkalmazás már az Azure Active Directory Authentication Library (ADAL) tárral hitelesíti a felhasználókat, az alkalmazásnak a sikeresen hitelesítést követően át kell adnia a felhasználó egyszerű felhasználónevét az IntuneMAMEnrollmentManager registerAndEnrollAccount metódusának:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Fontos**: Mindenképpen bírálja felül az Intune App SDK alapértelmezett ADAL-beállításait az alkalmazáséival. Ezt az alkalmazás Info.plist fájljában található IntuneMAMSettings szótárban teheti meg az [iOS-hez készült Intune App SDK – fejlesztői útmutató](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk) című témakörben leírtaknak megfelelően, vagy használhatja az IntuneMAMPolicyManager-példány AAD-felülbírálási tulajdonságait. Az Info.plist fájlt alkalmazó módszer használata ajánlott az olyan alkalmazások esetében, melyek ADAL-beállításai statikusak, míg a felülbírálási tulajdonságok használata ajánlott olyan alkalmazások esetében, melyek futásidőben határozzák meg ezeket az értékeket. 
      
      Ha az alkalmazás nem az ADAL-t használja, és azt szeretné, hogy az Intune SDK kezelje a hitelesítést, az alkalmazásnak az IntuneMAMEnrollmentManager loginAndEnrollAccount metódusát kell meghívnia:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      
> [!NOTE] 
> iOS rendszerre nincs remapper. A Xamarin.Forms-alkalmazásokba való integrálásnak ugyanúgy kell történnie, mint általában a Xamarin.iOS-projektek esetén. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése Androidos mobilalkalmazásban

Olyan Xamarin-alapú androidos alkalmazások esetén, amelyek nem használnak felhasználóifelület-keretrendszert, olvassa el és kövesse az [Androidhoz készült Intune App SDK fejlesztői útmutatójában](app-sdk-android.md) leírtakat. Xamarin-alapú Android-alkalmazások esetén le kell cserélnie az osztályt, a metódusokat és a tevékenységeket a MAM-beli megfelelőikre az útmutatóban található [táblázat](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) alapján. Ha az alkalmazás nem rendelkezik meghatározott `android.app.Application` osztállyal, akkor hozzon létre egyet, és győződjön meg arról, hogy az a `MAMApplication` osztálytól örököl.

### <a name="xamarinandroid-integration"></a>Xamarin.Android-integráció

1. Adja hozzá Xamarin.Android-projektjéhez a [Microsoft.Intune.MAM.Xamarin.Android NuGet-csomag](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) legfrissebb verzióját. Ezzel elérhetővé válnak az Intune alkalmazáshoz való engedélyezéséhez szükséges hivatkozások.

2. Olvassa el és kövesse [A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek](app-sdk-android.md) című cikk lépéseit, és fordítson kiemelt figyelmet a következő szakaszokra:
    1. A [teljes osztályok és metódusok lecserélése szakasz](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
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


## <a name="support"></a>Támogatás

Elvégezte az összetevő alkalmazásba történő beépítésének alapvető lépéseit. Következőnek kövesse a Xamarin-alapú Android-mintaalkalmazásban lévő lépéseket. Két mintát biztosítottunk, egyet a Xamarin.Forms-hoz és egyet az Androidhoz.

## <a name="requiring-intune-app-protection-policies-in-order-to-use-your-xamarin-based-android-lob-app-optional"></a>Intune alkalmazásvédelmi szabályzatok megkövetelése a Xamarin-alapú Android LOB-alkalmazások (nem kötelező) használatához 

A következő útmutatóból megtudhatja, hogyan biztosíthatja, hogy a Xamarin-alapú androidos üzletági alkalmazásokat csak az Intune által védett felhasználók használhassák eszközeiken. 

### <a name="general-requirements"></a>Általános követelmények
* Az Intune SDK csapata kérni fogja az alkalmazás azonosítóját. Ezt az [Azure Portalon](https://portal.azure.com/), a **Minden alkalmazás** terület **Alkalmazásazonosító** oszlopában találhatja meg. Az Intune SDK csapatát e-mailen keresztül érdemes felkeresni (msintuneappsdk@microsoft.com).
     
### <a name="working-with-the-intune-sdk"></a>Az Intune SDK használata
Ezek az utasítások minden olyan Android- és Xamarin-alkalmazásra vonatkoznak, amelyek Intune-alkalmazásvédelmi szabályzatokat szeretnének kérni a végfelhasználói eszközöktől.

1. Konfigurálja az ADAL-t az [Androidos Intune SDK útmutatójában](https://docs.microsoft.com/en-us/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal) megadott lépések alapján.
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

Ha vállalata már Intune-ügyfél, akkor a Microsoft támogató szolgálat képviselőjével együttműködve nyisson meg egy támogatási jegyet, és hozzon létre bejelentést [a GitHub hibabejelentő oldalán](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), mi pedig segítünk, amint tudunk. 


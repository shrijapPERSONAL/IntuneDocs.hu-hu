---
title: Microsoft Intune App SDK Xamarin Bindings
description: Az Intune App SDK Xamarin Bindings lehetővé teszik az Intune alkalmazásvédelmi szabályzatok használatát a Xamarinnal készített iOS- és Android-alkalmazásokban.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5c9f81761e7e24393471f44da4cf619f017e9bbd
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lehetővé teszi az [Intune alkalmazásvédelmi szabályzatok](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) használatát a Xamarinnal készített iOS- és Android-alkalmazásokban. A kötések lehetővé teszik a fejlesztők számára, hogy Intune alkalmazásvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

A Microsoft Intune App SDK Xamarin Bindings lehetővé teszi, hogy Intune alkalmazásvédelmi szabályzatokat (vagy más néven alkalmazás- vagy MAM-szabályzatokat) építsen be a Xamarinnal fejlesztett alkalmazásokba. A MAM-kompatibilis alkalmazás az, amelyik integrálva van az Intune App SDK-val. Mindez lehetővé teszi a rendszergazdáknak, hogy alkalmazásvédelmi szabályzatokat telepítsenek a mobilalkalmazásra vonatkozóan, ha az Intune aktívan felügyeli az alkalmazást.

## <a name="whats-supported"></a>Támogatott források és műveletek

### <a name="developer-machines"></a>Fejlesztői gépek
* Windows
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

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése Androidos mobilalkalmazásban

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

## <a name="support"></a>Support

Ha vállalata már Intune-ügyfél, akkor a Microsoft támogató szolgálat képviselőjével együttműködve nyisson meg egy támogatási jegyet, és hozzon létre bejelentést [a GitHub hibabejelentő oldalán](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), mi pedig segítünk, amint tudunk. 
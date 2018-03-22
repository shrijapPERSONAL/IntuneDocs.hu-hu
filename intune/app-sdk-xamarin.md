---
title: Microsoft Intune App SDK Xamarin összetevő
description: Az Intune App SDK Xamarin összetevő lehetővé teszi az Intune alkalmazásvédelmi szabályzatainak használatát a Xamarin platformmal fejlesztett iOS- és Android-alkalmazásokban.
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
ms.openlocfilehash: b69cccca8c8be859de94ca8bdb50d6030439233a
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/20/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune App SDK Xamarin összetevő

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin összetevő](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) lehetővé teszi az [Intune alkalmazásvédelmi szabályzatainak](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) használatát a Xamarin platformmal fejlesztett iOS- és Android-alkalmazásokban. Az összetevő lehetővé teszi a fejlesztők számára, hogy Intune alkalmazásvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

> [!NOTE]
> A Xamarinhoz készült Intune SDK jelenleg előzetes verzióban érhető el. 

A Microsoft Intune App SDK Xamarin összetevő lehetővé teszi, hogy Intune alkalmazásvédelmi szabályzatokat (vagy más néven alkalmazás- vagy MAM-szabályzatokat) építsen be a Xamarinnal fejlesztett alkalmazásokba. A MAM-kompatibilis alkalmazás az, amelyik integrálva van az Intune App SDK-val. Mindez lehetővé teszi a rendszergazdáknak, hogy alkalmazásvédelmi szabályzatokat telepítsenek a mobilalkalmazásra vonatkozóan, ha az Intune aktívan felügyeli az alkalmazást.

## <a name="whats-supported"></a>Támogatott források és műveletek

### <a name="developer-machines"></a>Fejlesztői gépek
* macOS


### <a name="mobile-app-platforms"></a>Mobilalkalmazás-platformok
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune mobilalkalmazás-kezelési helyzetek

* Intune MDM által regisztrált eszközök
* Külső EMM által regisztrált eszközök
* Nem felügyelt (semmilyen MDM által nem regisztrált) eszközök

Az Intune App SDK Xamarin összetevővel létrehozott Xamarin-alkalmazásokra mostantól alkalmazhatók az Intune alkalmazásvédelmi szabályzatai az Intune mobileszköz-felügyeletében (MDM) regisztrált eszközökön és a nem regisztrált eszközökön is.

## <a name="prerequisites"></a>Előfeltételek

* **[Csak az Android esetében]** Az eszközön a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni.

## <a name="get-started"></a>Első lépések

1. Olvassa el Microsoft Intune MAM Xamarin összetevő [licencfeltételeit](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf).

2.  Az Intune App SDK Xamarin összetevő NuGet-csomagjait letöltheti a [GitHubról](https://github.com/msintuneappsdk/intune-app-sdk-xamarin). Ezek a csomagok hamarosan elérhetők lesznek a Nuger.org oldalon.  

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése az iOS-mobilalkalmazásban
1. Adja hozzá a(z) `Microsoft.Intune.MAM.Xamarin.iOS` NuGet-csomagot a Xamarin.iOS projekthez.
2.  Kövesse az Intune App SDK iOS-mobilalkalmazásokba való integrálásához szükséges általános lépéseket. Kezdhet az [iOS-hez készült Intune App SDK – fejlesztői útmutató](app-sdk-ios.md#build-the-sdk-into-your-mobile-app) című témakör integrálási útmutatásának 3. lépésével. Az IntuneMAMConfigurator futtatásáról szóló szakasz utolsó lépését átugorhatja, mivel az eszköz része a Microsoft.Intune.MAM.Xamarin.iOS csomagnak, és a build időpontjában automatikusan futtatva lesz.
    **Fontos**: A kulcslánc megosztásának alkalmazások számára való engedélyezése kissé eltérő a Visual Studióban és az Xcode-ban. Nyissa meg az alkalmazás jogosultságokat tartalmazó plist-fájlját, és győződjön meg arról, hogy az „Enable Keychain” („Kulcslánc engedélyezése”) lehetőség engedélyezve van, és hogy ebben a szakaszban a megfelelő kulcslánc-megosztási csoportok szerepelnek. Ezután győződjön meg arról, hogy a projekt „iOS Bundle Signing” („iOS-kötegaláírási”) beállításai között a konfigurációk és platformok összes megfelelő kombinációjához meg van adva a jogosultságokat tartalmazó plist-fájl a „Custom Entitlements” („Egyéni jogosultságok”) mezőben.
3.  Miután hozzáadta az összetevőt és megfelelően konfigurálta az alkalmazást, az alkalmazás megkezdheti az Intune SDK API-jának használatát. Ehhez a következő névteret kell hozzáadnia:

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

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Az alkalmazásvédelmi szabályzatok engedélyezése androidos mobilalkalmazásban
Adja hozzá a(z) `Microsoft.Intune.MAM.Xamarin.Android` NuGet-csomagot a Xamarin.Android projekthez.

Olyan Xamarin-alapú androidos alkalmazások esetén, amelyek nem használnak felhasználóifelület-keretrendszert, olvassa el és kövesse az [Androidhoz készült Intune App SDK fejlesztői útmutatójában](app-sdk-android.md) leírtakat. Xamarin-alapú Android-alkalmazások esetén le kell cserélnie az osztályt, a metódusokat és a tevékenységeket a MAM-beli megfelelőikre az útmutatóban található [táblázat](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) alapján. Ha az alkalmazás nem rendelkezik meghatározott `android.app.Application` osztállyal, akkor hozzon létre egyet, és győződjön meg arról, hogy az a `MAMApplication` osztálytól örököl.

A Xamarin Formshoz és más felhasználóifelület-keretrendszerekhez biztosítunk egy `MAM.Remapper` nevű eszközt. Az eszköz elvégzi Ön helyett az osztály lecserélését. Ehhez azonban el kell végezni a következő lépéseket:

1.  Adja hozzá a(z) `Microsoft.Intune.MAM.Remapper.Tasks` NuGet-csomagot.

2.  Adja hozzá az alábbi sort az Android csproj projekthez (helyettesítse az x.x.x.x részt a valós csomagverzióval):
  ```xml
 <Import Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.x.x.x.x\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  A hozzáadott `remapping-config.json` fájl felépítési műveleteként a **RemappingConfigFile** műveletet kell beállítania. A felvett `remapping-config.json` fájl kizárólag a Xamarin.Forms-szal működik. Más felhasználóifelület-keretrendszerek esetén tekintse meg a Remapper NuGet-csomaghoz tartozó fontos fájlt.

## <a name="next-steps"></a>További lépések

Elvégezte az összetevő alkalmazásba történő beépítésének alapvető lépéseit. Következőnek kövesse a Xamarin-alapú Android-mintaalkalmazásban lévő lépéseket. Két mintát biztosítottunk, egyet a Xamarin.Forms-hoz és egyet az Androidhoz.

---
title: "Microsoft Intune App SDK Xamarin összetevő"
description: 
keywords: sdk, Xamarin, intune
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f50ecfbf5a0ac0b05de38e0ad29b27a729ab824b
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune App SDK Xamarin összetevő

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.



## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin összetevő](https://components.xamarin.com/view/microsoft.intune.mam) lehetővé teszi az [Intune alkalmazásvédelmi szabályzatainak](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) használatát a Xamarin platformmal fejlesztett iOS- és Android-alkalmazásokban. Az összetevő lehetővé teszi a fejlesztők számára, hogy Intune alkalmazásvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

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

1.  Töltse le a **Xamarin-component.exe** fájlt [innen](https://components.xamarin.com/submit/xpkg), és csomagolja ki.

2. Olvassa el Microsoft Intune MAM Xamarin összetevő [licencfeltételeit](https://components.xamarin.com/license/microsoft.intune.mam).

3.  Töltse le az Intune App SDK Xamarin Component mappát a [Githubról](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) vagy a [Xamarinról](https://components.xamarin.com/license/microsoft.intune.mam), és csomagolja ki. Az 1. és a 3. lépésben letöltött fájlnak ugyanazon a könyvtárszinten kell lennie.

4.  Futtassa rendszergazdaként a következő parancsot a parancssorban: `Xamarin.Component.exe install <.xam> file`.

5.  A Visual Studióban kattintson a jobb gombbal a korábban létrehozott Xamarin-projektben a **components** (összetevők) elemre.

6.  Válassza az **Edit Components** (Összetevők szerkesztése) lehetőséget, és vegye fel az Intune App SDK összetevőt, amelyet helyileg töltött le a számítógépére.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Az Intune alkalmazásvédelmi szabályzatainak engedélyezése az iOS-mobilalkalmazásban
1.  Az Intune App SDK inicializálásához az `AppDelegate.cs` osztályban lévő összes API esetén hívást kell kezdeményeznie. Példa:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Most, hogy megtörtént az összetevő hozzáadása és inicializálása, kövesse az App SDK iOS-mobilalkalmazásba való beépítéséhez szükséges általános lépéseket. A natív iOS-alkalmazások engedélyezéséről szóló teljes dokumentációt [az iOS-hez készült Intune App SDK fejlesztői útmutatójában](app-sdk-ios.md) találja.
3. **Fontos**: Számos, kizárólag a Xamarin-alapú iOS-alkalmazásokra vonatkozó módosítás van. A kulcslánccsoportok engedélyezésekor például a következőt kell hozzáadnia ahhoz, hogy felvegye azt a Xamarin-mintaalkalmazást, amelyet az összetevőhöz hozzáadott. Alább talál egy példát arra, hogy milyen csoportokat kell tartalmazniuk a kulcslánchozzáférési csoportoknak:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Teljesítette az összetevő Xamarin-alapú iOS-alkalmazásba való beépítéséhez szükséges lépéseket. Ha a projekt elkészítéséhez Xcode-ot használ, akkor használhatja az `Intune App SDK Settings.bundle` csomagot is. Ezzel a projekt elkészítése során ki- és bekapcsolhatja az Intune-szabályzatok beállításait a teszteléshez és a hibakereséshez. Ha ki szeretné használni ennek a csomagnak az előnyeit, kövesse [az iOS-hez készült Intune App SDK fejlesztői útmutatójában](app-sdk-ios.md) található lépéseket, és olvassa el [az Xcode-ban történő hibakeresésről szóló szakaszt](app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Az alkalmazásvédelmi szabályzatok engedélyezése androidos mobilalkalmazásban
Olyan Xamarin-alapú androidos alkalmazások esetén, amelyek nem használnak felhasználóifelület-keretrendszert, olvassa el és kövesse az [Androidhoz készült Intune App SDK fejlesztői útmutatójában](app-sdk-android.md) leírtakat. Xamarin-alapú Android-alkalmazások esetén le kell cserélnie az osztályt, a metódusokat és a tevékenységeket a MAM-beli megfelelőikre az útmutatóban található [táblázat](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) alapján. Ha az alkalmazás nem rendelkezik meghatározott `android.app.Application` osztállyal, akkor hozzon létre egyet, és győződjön meg arról, hogy az a `MAMApplication` osztálytól örököl.

A Xamarin Formshoz és más felhasználóifelület-keretrendszerekhez biztosítunk egy `MAM.Remapper` nevű eszközt. Az eszköz elvégzi Ön helyett az osztály lecserélését. Ehhez azonban el kell végezni a következő lépéseket:

1.  Fel kell vennie egy hivatkozást a `Microsoft.Intune.MAM.Remapper.Tasks` NuGet-csomag 0.1.0.0-s vagy frissebb verziójára.

2.  Hozzá kell adnia a következő sort az Androidhoz készült csproj-fájlhoz:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  A hozzáadott `remapping-config.json` fájl felépítési műveleteként a **RemappingConfigFile** műveletet kell beállítania. A felvett `remapping-config.json` fájl kizárólag a Xamarin.Forms-szal működik. Más felhasználóifelület-keretrendszerek esetén tekintse meg a Remapper NuGet-csomaghoz tartozó fontos fájlt.

## <a name="next-steps"></a>További lépések

Elvégezte az összetevő alkalmazásba történő beépítésének alapvető lépéseit. Következőnek kövesse a Xamarin-alapú Android-mintaalkalmazásban lévő lépéseket. Két mintát biztosítottunk, egyet a Xamarin.Forms-hoz és egyet az Androidhoz.

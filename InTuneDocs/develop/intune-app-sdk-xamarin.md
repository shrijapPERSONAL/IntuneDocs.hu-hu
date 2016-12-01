---
title: "Microsoft Intune App SDK Xamarin összetevő | Microsoft Intune"
description: 
keywords: sdk, Xamarin, intune
author: oydang
manager: karthikaraman
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4623db80d711f3543b6d688fb1bb1ef228c62c
ms.openlocfilehash: e2d43fff8772046fe7426b267e39d53b278d4e5c


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune App SDK Xamarin összetevő

## <a name="overview"></a>Áttekintés
Az [Intune App SDK Xamarin összetevő](https://components.xamarin.com/view/microsoft.intune.mam) lehetővé teszi az [Intune mobilalkalmazás-felügyeleti funkcióinak](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) igénybevételét a Xamarin használatával létrehozott iOS- és Android-alkalmazásokban. Az összetevő lehetővé teszi a fejlesztők számára, hogy alkalmazáskorlátozási és adatvédelmi funkciókat építsenek be a Xamarin-alapú alkalmazásaikba.

Tapasztalni fogja, hogy az SDK funkcióit az alkalmazás működésének módosítása nélkül is engedélyezheti. Miután beépítette a összetevőt az iOS vagy az Android rendszerhez készített mobilalkalmazásába, a rendszergazda olyan szabályzatot tud érvénybe léptetni a Microsoft Intune-nal, amely számos adatvédelmi funkciót támogat.

## <a name="supported-scenarios"></a>Támogatott helyzetek

### <a name="platforms"></a>Platformok
* Android
* iOS


### <a name="emm-scenarios"></a>EMM-forgatókönyvek

* Az Intune MAM az Intune MDM-ben regisztrált eszközökön
* Az Intune MAM a külső féltől származó EMM-ben regisztrált eszközökön
* Az Intune MAM a nem regisztrált és nem felügyelt eszközökön

Az Intune App SDK Xamarin összetevővel létrehozott Xamarin-alapú alkalmazások mostantól fogadni tudják az Intune mobilalkalmazás-felügyeleti (MAM-) szabályzatait az Intune mobileszköz-felügyeletben (MDM) regisztrált eszközökön és a nem regisztrált eszközökön is.

## <a name="prerequisites"></a>Előfeltételek

* **[Csak az Android esetében]** Az eszközön mindig a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni.

## <a name="get-started"></a>Első lépések

1.  Töltse le a **Xamarin-component.exe** fájlt [innen](https://components.xamarin.com/submit/xpkg), és csomagolja ki.

2. Olvassa el Microsoft Intune MAM Xamarin összetevő [licencfeltételeit](https://components.xamarin.com/license/microsoft.intune.mam).

3.  Töltse le az Intune App SDK Xamarin Component mappát a [Githubról](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) vagy a [Xamarinról](https://components.xamarin.com/license/microsoft.intune.mam), és csomagolja ki. Az 1. és a 2. lépésben letöltött fájlnak ugyanazon a könyvtárszinten kell lennie.

4.  Futtassa rendszergazdaként a következő parancsot a parancssorban: `Xamain.Component.exe install <.xam> file`.

5.  A Visual Studióban kattintson jobb gombbal a korábban létrehozott Xamarin-projektben az **components** (összetevők) elemre.

6.  Válassza az **Edit Components** (Összetevők szerkesztése) lehetőséget, és vegye fel az Intune App SDK összetevőt, amelyet helyileg töltött le a számítógépére.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Intune MAM engedélyezése iOS-mobilalkalmazásban
1.  Az Intune App SDK inicializálásához az `AppDelegate.cs` osztályban lévő összes API esetén hívást kell kezdeményeznie. Példa:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Most, hogy megtörtént az összetevő hozzáadása és inicializálása, kövesse az App SDK iOS-mobilalkalmazásba való beépítéséhez szükséges általános lépéseket. A natív iOS-alkalmazások engedélyezéséről szóló teljes dokumentációt [az iOS-hez készült Intune App SDK fejlesztői útmutatójában](intune-app-sdk-ios) találja.
3. **Fontos**: Számos, kizárólag a Xamarin-alapú iOS-alkalmazásokra vonatkozó módosítás van. A kulcslánccsoportok engedélyezésekor például a következőt kell hozzáadnia ahhoz, hogy felvegye a Xamarin-mintaalkalmazást, amelyet az összetevőhöz hozzáadott. Alább talál egy példát arra, hogy milyen csoportokat kell tartalmazniuk a kulcslánchozzáférési csoportoknak:

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

Teljesítette az összetevő Xamarin-alapú iOS-alkalmazásba való beépítéséhez szükséges lépéseket. Ha a projekt elkészítéséhez Xcode-ot használ, akkor használhatja az `Intune App SDK Settings.bundle` csomagot is. Ezzel a projekt elkészítése során ki- és bekapcsolja az Intune-szabályzatok beállításait a teszteléshez és a hibakereséshez. Ha ki szeretné használni ennek a csomagnak az előnyeit, kövesse [az iOS-hez készült Intune App SDK fejlesztői útmutatójában](intune-app-sdk-ios) található lépéseket, és olvassa el [az Xcode-ban történő hibakeresésről szóló szakaszt](intune-app-sdk-ios#debug-information).

## <a name="enabling-mam-in-your-android-mobile-app"></a>MAM engedélyezése Android-mobilalkalmazásban
Olyan Xamarin-alapú Android-alkalmazások esetén, amelyek nem használnak felhasználóifelület-keretrendszert, olvassa el és kövesse az [Androidhoz készült Intune App SDK fejlesztői útmutatójában] leírtakat. Xamarin-alapú Android-alkalmazások esetén le kell cserélnie az osztályt, a metódusokat és a tevékenységeket a MAM-beli megfelelőikre az útmutatóban található [táblázat](intune-app-sdk-android#replace-classes-methods-and-activities-with-their-mam-equivalent-required) alapján. Ha az alkalmazás nem rendelkezik meghatározott `android.app.Application` osztállyal, akkor hozzon létre egyet, és győződjön meg arról, hogy az a `MAMApplication` osztálytól örököl.

A Xamarin Formshoz és más felhasználóifelület-keretrendszerekhez biztosítunk egy `MAM.Remapper` nevű eszközt. Az eszköz elvégzi Ön helyett az osztály lecserélését. Ehhez azonban el kell végezni a következő lépéseket:

1.  Fel kell vennie egy hivatkozást a ` Microsoft.Intune.MAM.Remapper.Tasks` NuGet-csomag 0.1.0.0-s vagy frissebb verziójára.

2.  Hozzá kell adnia a következő sort az Androidhoz készült csproj-fájlhoz:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  A hozzáadott `remapping-config.json` fájl felépítési műveleteként a **RemappingConfigFile** műveletet kell beállítania. A felvett `remapping-config.json` fájl kizárólag a Xamarin.Forms-szal működik. Más felhasználóifelület-keretrendszerek esetén tekintse meg a Remapper NuGet-csomaghoz tartozó fontos fájlt.

## <a name="test-your-app"></a>Az alkalmazás tesztelése

Elvégezte az összetevő alkalmazásba történő beépítésének alapvető lépéseit. Következőnek kövesse a Xamarin-alapú Android-mintaalkalmazásban lévő lépéseket. Két mintát biztosítottunk, egyet a Xamarin.Forms-hoz és egyet az Androidhoz.



<!--HONumber=Nov16_HO3-->



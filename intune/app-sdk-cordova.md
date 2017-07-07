---
title: "Microsoft Intune App SDK Cordova beépülő modul"
description: 
keywords: SDK, Cordova, Intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0329720b6f02c718ef27a59e6efc5f3a76eed1c5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune App SDK Cordova beépülő modul

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.

## <a name="overview"></a>Áttekintés

Az [Intune App SDK Cordova beépülő modul](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) Cordovával készített iOS- és Android alkalmazásokban. A beépülő modullal a fejlesztők beépíthetik az Intune alkalmazásfelügyeleti és adatvédelmi funkcióit a Cordova-alapú alkalmazásaikba.

Tapasztalni fogja, hogy az SDK funkcióit az alkalmazás működésének módosítása nélkül is engedélyezheti. Miután beépítette a beépülő modult az iOS vagy az Android rendszerhez készített mobilalkalmazásába, a Microsoft Intune rendszergazdája telepíteni tud olyan Intune alkalmazásvédelmi szabályzatot, amely számos adatvédelmi funkciót támogat. A beépülő modult azért készítettük el, hogy a lépések többségét automatikusan lehessen végrehajtani a Cordovában a build létrehozásakor. Ennek eredményeképpen gyorsan felkészítheti az alkalmazását az Intune alkalmazásvédelemre. A kezdéshez kövesse az alábbi lépéseket a célplatformnak megfelelően.

## <a name="supported-platforms"></a>Támogatott platformok

* A beépülő modul Windows, Mac és Linux rendszereken is működik
* A beépülő modul Android-alkalmazások esetében `minSdkVersion` >= 14 és `targetSdkVersion` <= 24 verziókkal működik
* A beépülő modul iOS-alkalmazások esetében iOS 9.0 vagy újabb verziókkal működik.

## <a name="intune-mobile-application-management-scenarios"></a>Intune mobilalkalmazás-kezelési helyzetek

* Intune MDM által regisztrált eszközök
* Külső EMM által regisztrált eszközök
* Nem felügyelt (semmilyen MDM által nem regisztrált) eszközök

Az Intune App SDK Cordova beépülő modullal létrehozott Cordova-alapú alkalmazások mostantól fogadni tudják az Intune alkalmazásvédelmi szabályzatokat az Intune mobileszköz-felügyeletben (MDM) regisztrált eszközökön és a nem regisztrált eszközökön is.

## <a name="prerequisites"></a>Előfeltételek

### <a name="android"></a>Android

* Az eszközön mindig a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni.
* A beépülő modul használatakor a Cordova-build végrehajtásának elérési útján legalább a Java 7-nek elérhetőnek kell lennie.

### <a name="ios"></a>iOS

* Az MDM-funkciók elérhetősége érdekében az eszközön mindig a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni. Az eszközregisztráció nélküli alkalmazásvédelmi szabályzat funkcióihoz azonban *nincs* szükség erre.

### <a name="both-platforms"></a>Mindkét platform

* Az [Azure Active Directory Authentication Libraries (ADAL) Cordova rendszerhez készült beépülő moduljának](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) 0.8.0+ verziója szükséges.

> [!NOTE]
> Az Apache Cordova [itt](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) ismertetett programhibája miatt a beépülő modultól már függő alkalmazások nem frissítik automatikusan a beépülő modult a szükséges verzióra.



## <a name="quick-start"></a>Gyors kezdés

1. Frissítse az ADAL verzióját:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Vegye fel az Intune App SDK for Cordova beépülő modult:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>A beépülő modul beépítése iOS-alkalmazásba

Végre kell hajtania néhány lépést ahhoz, hogy felkészítse az alkalmazását az Intune alkalmazásvédelmi szabályzat használatára. A művelet megkönnyítéséhez az ehhez szükséges lépések végrehajtása automatikusan történik a Cordova létrehozási folyamatában, a létrehozás előtti beavatkozási pontként. Ennek következtében az automatikusan végrehajtott lépések módosítani fogják a projektkonfigurációhoz társított `*.pbxproj`, `*-Info.plist` és `*.entitlements` fájlokat. Ha a projektje nem tartalmaz jogosultságfájlt, akkor a beépülő modul automatikusan létrehoz egy ilyen fájlt.

Ez a beállítás csak egy célt támogat, és több cél esetén az első megtalált célra vonatkozóan fogja végrehajtani a konfigurálást. Ha a folyamat sikertelen, ellenőrizze a következőket:

1. Az alkalmazás Xcode-projektje `[name].xcodeproj`, ahol a `[name]` a `config.xml` fájlban meghatározott érték.
2. A projekt a [Cordova szabványos alkalmazástár-struktúráját](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) használja.

## <a name="build-the-plugin-into-your-android-app"></a>A beépülő modul beépítése Android-alkalmazásba

1. Importálja a beépülő modult a Cordova legújabb eszközeivel. A beépülő modul hívása automatikusan fog történni `after_compile` lépésként.

2. A beépülő modul a létrehozási folyamat végén összeállítja az alkalmazáscsomag (Android API 14+) Intune-ra felkészített verzióját. A művelet kimenete tartalmazni fog egy `[Project]-intunewrapped-[Build_Configuration].apk` alkalmazáscsomagot (például: `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> A beépülő modul csak a gradle típusú buildeket támogatja.

A Cordova [itt](https://issues.apache.org/jira/browse/CB-9434) ismertetett programhibája miatt – amely a Cordova egyes beavatkozási pontjainak figyelmen kívül hagyását okozza a `cordova run` esetében – a beburkolt alkalmazásnak a parancssorból történő indításához a következőket kell tennie:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Az Android-alkalmazás aláírása

A beépülő modul automatikusan felismeri a Cordova számára megadott aláírási információkat az alábbi helyeken:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Az elvárt formátumról további információkat talál a [Cordova gradle típusú aláírását](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) bemutató cikkben.

Jelenleg nincsenek támogatva a `build.json` vagy más tetszőleges helyeken megadott aláírási információk a Cordova-build létrehozásakor megadott paraméterekkel.

## <a name="debugging-from-visual-studio"></a>Hibakeresés a Visual Studióból

Az alkalmazás első indítását követően meg kell jelennie egy párbeszédpanelnek, amely arról tájékoztatja, hogy az alkalmazást az Intune felügyeli. Válassza a „Ne jelenjen meg többé” lehetőséget, és kattintson ismét a VS hibakeresési/futtatási gombjára a töréspontok megjelenítéséhez.

## <a name="known-limitations"></a>Ismert korlátozások

### <a name="android"></a>Android

* A MultiDex támogatása nem teljes.
* Az alkalmazásnak legfeljebb `minSdkVersion` 14-es és `targetSdkVersion` 24-es verziókkal kell rendelkeznie. Az API 25 jelenleg nincs támogatva az alkalmazásoknál
* A V2-es aláírási sémával aláírt alkalmazásokat nem lehetséges újra aláírni. Ha V2-aláírású alkalmazást csomagol be a beépülő modullal, a kimeneti becsomagolt .apk nem lesz aláírva.
*
  * A Cordova alapértelmezett V2-aláírását letilthatja, ha a `build-extras.gradle` fájlhoz hozzáadja a következőket:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Amikor módosítja az egységes típusazonosítók (UTI) listáját az **Info.plist** fájl **CFBundleDocumentTypes** csomópontjában, az újbóli létrehozás előtt minden esetben törölnie kell az Intune UTI-kat az adott plist fájl importált UTI-kat tartalmazó szakaszában (**UTImportedTypeDeclarations** csomópont). Minden Intune UTI a `com.microsoft.intune.mam` előtaggal kezdődik.

* Ha el szeretné távolítani az Intune App SDK for Cordova beépülő modult a Cordova-projektjéből, akkor az iOS platformot is el kell távolítania, majd újból fel kell vennie, hogy visszavonja az Intune egyes konfigurációs beállításait az .xcodeproj- és a .plist-fájlokban.

---
title: "Microsoft Intune App SDK Cordova beépülő modul | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 9ef09f43e6c878af689a500457bab578149de499


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune App SDK Cordova beépülő modul

> [!NOTE]
> Először célszerű elolvasnia az [Intune App SDK használatának első lépései](intune-app-sdk-get-started.md) című cikket, amely bemutatja az integráció előkészítését a támogatott platformokon.


## <a name="overview"></a>Áttekintés

Az [Intune APP SDK Cordova beépülő modul](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) lehetővé teszi az [Intune mobilalkalmazás-felügyeleti funkcióinak](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) igénybevételét a Cordova használatával létrehozott iOS- és Android-alkalmazásokban. A beépülő modullal a fejlesztők beépíthetik az Intune alkalmazásfelügyeleti és adatvédelmi funkcióit a Cordova-alapú alkalmazásaikba.

Tapasztalni fogja, hogy az SDK funkcióit az alkalmazás működésének módosítása nélkül is engedélyezheti. Miután beépítette a beépülő modult az iOS vagy az Android rendszerhez készített mobilalkalmazásába, a rendszergazda a Microsoft Intune mobilalkalmazás-kezelési szolgáltatásával (MAM) telepíteni tud olyan szabályzatot, amely számos adatvédelmi funkciót támogat. A beépülő modult azért készítettük el, hogy a lépések többségét automatikusan lehessen végrehajtani a Cordovában, a build létrehozásakor. Ennek eredményeképpen gyorsan felkészítheti az alkalmazását a felügyeletre. A kezdéshez kövesse az alábbi lépéseket a célplatformnak megfelelően.




## <a name="whats-supported"></a>Támogatott források és műveletek

### <a name="developer-machines"></a>Fejlesztői gépek
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Mobilalkalmazás-platformok
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Intune mobilalkalmazás-kezelési helyzetek

* Intune MDM által regisztrált eszközök
* Külső EMM által regisztrált eszközök
* Nem felügyelt (semmilyen MDM által nem regisztrált) eszközök

Az Intune App SDK Cordova beépülő modullal létrehozott Cordova-alapú alkalmazások mostantól fogadni tudják az Intune mobilalkalmazás-felügyeleti (MAM) szabályzatokat az Intune mobileszköz-felügyeletben (MDM) regisztrált eszközökön és a nem regisztrált eszközökön is.



## <a name="prerequisites"></a>Előfeltételek

### <a name="technical-prerequisites"></a>Technikai előfeltételek

* **[Csak az Android esetében]** Az eszközön mindig a legújabb Microsoft Intune Céges portál alkalmazást kell telepíteni.


* Az [Azure Active Directory Authentication Libraries (ADAL) Cordova rendszerhez készült beépülő moduljának](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) 0.8.0+ verziója szükséges.
  * **Fontos:** Az Apache Cordova [itt](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) ismertetett programhibája miatt a beépülő modultól már függő alkalmazások nem frissítik automatikusan a beépülő modult a szükséges verzióra.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>A Microsoft Intune App SDK Cordova beépülő modul telepítése és használata **előtt**:

* Olvassa el az [Intune App SDK Cordova beépülő modul licencfeltételeit](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Nyomtassa ki és őrizze meg a licencfeltételeket. Az Intune App SDK Cordova beépülő modul letöltésével és használatával Ön elfogadja a beépülő modul licencfeltételeit.  Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.


## <a name="quick-start"></a>Gyors kezdés

1. Frissítse az ADAL verzióját:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Vegye fel az Intune App SDK for Cordova beépülő modult:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>A beépülő modul beépítése iOS-alkalmazásba

Végre kell hajtania néhány lépést ahhoz, hogy felkészítse az alkalmazását az Intune MAM használatára. A művelet megkönnyítéséhez az ehhez szükséges lépések végrehajtása automatikusan történik a Cordova létrehozási folyamatában, a létrehozás előtti beavatkozási pontként. Ennek következtében az automatikusan végrehajtott lépések módosítani fogják a projektkonfigurációhoz társított `*.pbxproj`, `*-Info.plist` és `*.entitlements` fájlokat. Ha a projektje nem tartalmaz jogosultságfájlt, akkor a beépülő modul automatikusan létrehoz egy ilyen fájlt.

Ez a beállítás csak egy célt támogat, és több cél esetén az első megtalált célra vonatkozóan fogja végrehajtani a konfigurálást. Ha a folyamat sikertelen, ellenőrizze a következőket:

1. Az alkalmazás Xcode-projektje `[name].xcodeproj`, ahol a `[name]` a `config.xml` fájlban meghatározott érték.
2. A projekt a [Cordova szabványos alkalmazástár-struktúráját](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) használja.

## <a name="how-to-build-the-plugin-into-your-android-app"></a>A beépülő modul beépítése Android-alkalmazásba

1. Importálja a beépülő modult a Cordova legújabb eszközeivel. A beépülő modul hívása automatikusan fog történni `after_compile` lépésként.

2. A beépülő modul a létrehozási folyamat végén összeállítja az alkalmazáscsomag (Android API 14+) mobilalkalmazás-felügyeletre felkészített verzióját. A művelet kimenete tartalmazni fog egy `[Project]-intunewrapped-[Build_Configuration].apk` alkalmazáscsomagot (például: `helloWorld-intunewrapped-debug.apk`).

A beépülő modul csak a gradle típusú buildeket támogatja.

A Cordova [itt](https://issues.apache.org/jira/browse/CB-9434) ismertetett programhibája miatt – amely a Cordova egyes beavatkozási pontjainak figyelmen kívül hagyását okozza a `cordova run` esetében – a beburkolt alkalmazásnak a parancssorból történő indításához a következőket kell tennie:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Az Android-alkalmazás aláírása
A beburkolt alkalmazáscsomag aláírási információjának hozzáadásához módosítsa a `build.json` fájlt úgy, ahogy azt szokásosan tenné az aláírási információk hozzáadásához. Példa:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Létrehozás csak az Android rendszerbeli teszteléshez

1. Adja hozzá a `android:testOnly="true"` értéket az `AndroidManifest.xml` fájl alkalmazás-csomópontjához.


2. **Cordova 6.x.x:** A `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js` fájlban módosítsa a 60. sort. Eredeti sor:

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    Módosított sor:
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Ennek hatására az `adb install` futtatása a „-t” jelzővel fog történni, mivel a `testOnly` alkalmazások nem telepíthetők enélkül.

### <a name="debugging-from-visual-studio"></a>Hibakeresés a Visual Studióból
Az alkalmazás első indítását követően meg kell jelennie egy párbeszédpanelnek, amely arról tájékoztatja, hogy az alkalmazást az Intune felügyeli. Válassza a „Ne jelenjen meg többé” lehetőséget, és kattintson ismét a VS hibakeresési/futtatási gombjára a töréspontok megjelenítéséhez.

## <a name="known-limitations"></a>Ismert korlátozások
### <a name="android"></a>Android
* A MultiDex támogatása nem teljes.
* Az alkalmazásnak az Android 4.0 (Android API 14) vagy újabb verzióval kell működnie.

### <a name="ios"></a>iOS
* Amikor módosítja az egységes típusazonosítók (UTI) listáját az **Info.plist** fájl **CFBundleDocumentTypes** csomópontjában, az újbóli létrehozás előtt minden esetben törölnie kell az Intune UTI-kat az adott plist fájl importált UTI-kat tartalmazó szakaszában (**UTImportedTypeDeclarations** csomópont). Minden Intune UTI a `com.microsoft.intune.mam` előtaggal kezdődik.

* Ha el szeretné távolítani az Intune beépülő modult a Cordova-projektjéből, akkor az iOS platformot is el kell távolítania, majd újból fel kell vennie, hogy visszavonja az Intune egyes konfigurációs beállításait az .xcodeproj- és a .plist-fájlokban.



<!--HONumber=Dec16_HO2-->



---
title: MTD-alkalmazások hozzáadása és hozzárendelése a Microsoft Intune-hoz
titleSuffix: ''
description: Az Intune-nal Mobile Threat Defense-alkalmazásokat, a Microsoft Authenticator alkalmazást és iOS-es konfigurációs szabályzatokat adhat hozzá az Azure Portalon.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c64c267623db93128177d56ced29586d3a877b19
ms.sourcegitcommit: 973a06f4a35b74314fece2bae17dd6885b4211c3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42823052"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Mobile Threat Defense- (MTD) alkalmazások felvétele és hozzárendelése az Intune-nal

> [!NOTE] 
> Ez a témakör minden Mobile Threat Defense-partnerre vonatkozik.

Az Intune segítségével MTD-alkalmazásokat vehet fel és helyezhet üzembe annak érdekében, hogy a végfelhasználók értesítést kapjanak a mobileszközeiken észlelt fenyegetésekről, és útmutatást kapjanak azok elhárításához.


## <a name="before-you-begin"></a>Előkészületek

Az [Azure Portalon](https://portal.azure.com/) végre kell hajtani az alábbi lépéseket. Előzőleg ismerkedjen meg a következő eljárásokkal:

  -   [Alkalmazás felvétele az Intune-ba](apps-add.md)
  -   [iOS-es alkalmazáskonfigurációs szabályzat felvétele az Intune-ba](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)
  -   [Alkalmazás hozzárendelése az Intune-hoz](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).
  -   [iOS-es alkalmazáskonfigurációs szabályzat felvétele](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

> [!TIP]
> Androidos eszközökön a felhasználó a Céges portál közvetítésével hajthatja végre az identitás-ellenőrzést az Azure AD-n.

## <a name="configure-microsoft-authenticator-for-ios"></a>Az iOS-hez készült Microsoft Authenticator alkalmazás konfigurálása
iOS-eszközök esetén a [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) használatára van szükség, hogy az Azure AD ellenőrizhesse a felhasználók identitását. Szükség van továbbá az iOS-es alkalmazáskonfigurációs szabályzatra is, amely az MTD iOS-alkalmazást az Intune-nal történő használatra utasítja.

Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** használja a [ Microsoft Authenticator alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

## <a name="configure-mtd-applications"></a>MTD-alkalmazások konfigurálása

Válassza ki az MTD-szolgáltatójának megfelelő szakaszt:

  - [Lookout for Work](#configure-lookout-for-work-apps)
  - [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
  - [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
  - [Zimperium](#configure-zimperium-apps)
  - [Pradeo](#configure-pradeo-apps)
  - [Better Mobile](#configure-better-mobile-apps)

### <a name="configure-lookout-for-work-apps"></a>Lookout for Work-alkalmazások konfigurálása

- **Android**
  - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Lookout for Work Google alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.lookout.enterprise).

- **iOS**

  - Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** használja a [ Lookout for Work iOS alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8).

-   **Lookout for Work alkalmazás az Apple áruházon kívül**
    - A Lookout for Work iOS-alkalmazást újra alá kell írnia. A Lookout az iOS App Store-on kívül terjeszti a Lookout for Work alkalmazását. Az alkalmazás terjesztése előtt újra alá kell írnia az alkalmazást az iOS vállalati fejlesztői tanúsítványával.
    - A részletes leírást a Lookout for Work iOS-alkalmazás újbóli aláírásáról lásd: [Lookout for Work iOS-alkalmazás újbóli aláírásának folyamata](https://personal.support.lookout.com/hc/articles/114094038714) a Lookout oldalán.

    - **Azure AD-hitelesítés engedélyezése a Lookout for Work iOS-alkalmazás felhasználói számára**

        1. Lépjen az [Azure Portalra](https://portal.azure.com), jelentkezzen be a hitelesítő adataival, majd nyissa meg az alkalmazás lapot.

        2. Adja hozzá a **Lookout for Work iOS alkalmazást natív ügyfélalkalmazásként**.

        3. Cserélje le a **com.lookout.enterprise.yourcompanyname** sort az IPA aláírásakor választott ügyfélcsomag-azonosítóval.

        4.  Adja hozzá ezt az átirányítási URI-t:**&lt;companyportal://code/>**, valamint az eredeti átirányítási URI-ja URL-kódolású verzióját.

        5.  Adjon hozzá **Delegált engedélyeket** az alkalmazásához.

        > [!NOTE] 
        > További részletekért lásd:[Natív ügyfélalkalmazás konfigurálása az Azure AD-val](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

     - **Adja hozzá a Lookout for Work ipa-fájlt.**

        - Töltse fel az újból aláírt .ipa-fájlt az[iOS LOB alkalmazások hozzáadása az Intune-nal](lob-apps-ios.md) című témakörben leírtaknak megfelelően. Ezenkívül a minimum OS-verziót iOS 8.0-ra vagy újabbra kell állítania.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>A Symantec Endpoint Protection Mobile-alkalmazások konfigurálása

 - **Android**

    - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja ezt a [SEP Mobile alkalmazás-áruházbeli URL-címet](https://play.google.com/store/apps/details?id=com.skycure.skycure).  **Minimális operációs rendszerként** jelölje be az **Android 4.0 (Ice Cream Sandwich)** rendszert.

 - **iOS**

    - Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** használja ezt a [SEP Mobile alkalmazás-áruházbeli URL-címet](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile-alkalmazások konfigurálása

 - **Android**

    - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). Adja meg ezt a [Check Point SandBlast Mobile alkalmazás-áruházbeli URL-címet](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) a  **7. lépésben**.

 - **iOS**

    - Szerezze be az iOS alkalmazást a [Check Point SandBlast Mobile-tól](https://www.checkpoint.com/products/sandblast-mobile/). Tekintse át az [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md) témát, majd az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** adja meg az Apple áruházbeli URL-címet.

### <a name="configure-zimperium-apps"></a>Zimperium-alkalmazások konfigurálása

 - **Android**

    - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Zimperium alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en).

 - **iOS**

    - Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** használja ezt a [Zimperium alkalmazás-áruházbeli URL-címet](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8).

### <a name="configure-pradeo-apps"></a>Pradeo-alkalmazások konfigurálása

 - **Android**

    - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [Pradeo alkalmazás-áruházbeli URL-címet](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US).

 - **iOS**

    - Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **12. lépésében** használja ezt a [Pradeo alkalmazás-áruházbeli URL-címet](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8).

### <a name="configure-better-mobile-apps"></a>Better Mobile-alkalmazások konfigurálása

 - **Android**

    - Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). Használja az [Active Shield ezen alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) a **7. lépésben**.

 - **iOS**

    - Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Használja az [Active Shield ezen alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) a **12. lépésében**, **Az alkalmazás adatainak konfigurálása** szakaszban.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>MTD-alkalmazások konfigurálása egy iOS-es alkalmazáskonfigurációs szabályzattal

### <a name="lookout-for-work-app-configuration-policy"></a>Konfigurációs szabályzat az Lookout for Workhöz

- Hozza létre az iOS-es alkalmazáskonfigurációs szabályzatot az [iOS-es alkalmazáskonfigurációs szabályzat használata](app-configuration-policies-use-ios.md) témakör leírása alapján.

### <a name="sep-mobile-app-configuration-policy"></a>SEP Mobile-alkalmazások konfigurációs szabályzata

-   Ehhez a művelethez a korábban a [Symantec Endpoint Protection Management konzolon](https://aad.skycure.com) konfigurált Microsoft Azure Active Directory-fiókot kell használni, amely megegyezik a klasszikus Intune-portálra való bejelentkezéshez használttal.

-   **Töltse le** az iOS-es alkalmazáskonfigurációs szabályzatot tartalmazó fájlt: 
    -   Lépjen a [Symantec Endpoint Protection Management konzolra](https://aad.skycure.com), és jelentkezzen be rendszergazdai azonosító adataival.

    -   Lépjen a **Settings** (Beállítások) lapra, majd az **Integrations** (Integrációk) alatt válassza az **Intune** lehetőséget. Válassza az **EMM Integration Selection** (EMM-integráció kiválasztása) lehetőséget. Válassza a **Microsoft** lehetőséget, majd mentse a kijelölés.

    -   Kattintson az **Integration setup files** (Integráció-telepítőfájlok) hivatkozásra, és mentse a létrejövő \*.zip fájlt. A .zip-fájlban található a ***.plist**-fájl, amellyel létrehozható az iOS-es alkalmazáskonfigurációs szabályzat az Intune-ban.

    -   A SEP Mobile iOS-es alkalmazáskonfigurációs szabályzat felvételéhez lásd a következő útmutatót:[A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md).

    - A **8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be a ***.plist**-fájl tartalmát a konfigurációs szabályzat törzsébe.

> [!NOTE]
> Ha nem sikerült beolvasni a fájlokat, lépjen kapcsolatba a [Symantec Endpoint Protection Mobile nagyvállalati támogatási szolgálatával](https://support.symantec.com/en_US/contact-support.html).

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Check Point SandBlast Mobile-alkalmazások konfigurációs szabályzata

- A Check Point SandBlast Mobile iOS-es alkalmazáskonfigurációs szabályzat felvételéhez tekintse át a következő útmutatót: [A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md).
    - A**8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be az alábbi tartalmat a konfigurációs szabályzat törzsébe.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Zimperium-alkalmazások konfigurációs szabályzata

- A Zimperium iOS-es alkalmazáskonfigurációs szabályzat felvételéhez kövesse [A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md) című útmutatót.
    - A**8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be az alábbi tartalmat a konfigurációs szabályzat törzsébe.

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>
```

### <a name="better-mobile-app-configuration-policy"></a>Better Mobile-alkalmazások konfigurációs szabályzata

- A Better Mobile iOS-es alkalmazáskonfigurációs szabályzat megadásához lásd [a Microsoft Intune alkalmazáskonfigurációs szabályzatainak iOS-hez történő használatával](app-configuration-policies-use-ios.md) foglalkozó útmutatót.
    - A**8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be az alábbi tartalmat a konfigurációs szabályzat törzsébe. Cserélje le a `https://client.bmobi.net` URL-címet a konzol URL-címére.

```
<dict>
<key>better_server_url</key>
<string>https://client.bmobi.net</string>
<key>better_udid</key>
<string>{{aaddeviceid}}</string>
<key>better_user</key>
<string>{{userprincipalname}}</string>
</dict>
```

## <a name="assign-apps-to-groups"></a>Alkalmazások hozzárendelése csoportokhoz

- Ez a lépés minden MTD-partnerre vonatkozik. Lásd a következő útmutatót: [Alkalmazások csoportokhoz rendelése az Intune-nal](apps-deploy.md).

## <a name="next-steps"></a>További lépések

- [Az MTD eszközmegfelelőségi szabályzatának konfigurálása](mtd-device-compliance-policy-create.md)

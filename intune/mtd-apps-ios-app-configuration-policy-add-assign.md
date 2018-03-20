---
title: "MTD-alkalmazások hozzáadása és hozzárendelése a Microsoft Intune-hoz"
titleSuffix: 
description: "Az Intune-nal Mobile Threat Defense-alkalmazásokat, a Microsoft Authenticator alkalmazást és iOS-es konfigurációs szabályzatokat adhat hozzá az Azure Portalon."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fc71620fee1b1df907a4027c1c57cd91b53032e
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Mobile Threat Defense- (MTD) alkalmazások felvétele és hozzárendelése az Intune-nal

> [!NOTE] 
> Ez a témakör minden Mobile Threat Defense-partnerre vonatkozik.

Az Intune segítségével MTD-alkalmazásokat vehet fel és helyezhet üzembe annak érdekében, hogy a végfelhasználók értesítést kapjanak a mobileszközeiken észlelt fenyegetésekről, és útmutatást kapjanak azok elhárításához.

iOS-eszközök esetén a [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) használatára van szükség, hogy az Azure AD ellenőrizhesse a felhasználók identitását. Szükség van továbbá az iOS-es alkalmazáskonfigurációs szabályzatra is, amely az MTD iOS-alkalmazást az Intune-nal történő használatra utasítja.

> [!TIP]
> Androidos eszközökön a felhasználó a Céges portál közvetítésével hajthatja végre az identitás-ellenőrzést az Azure AD-n.

## <a name="before-you-begin"></a>Előkészületek

-   Az [Azure Portalon](https://portal.azure.com/) végre kell hajtani az alábbi lépéseket.

-   Előzőleg ismerkedjen meg a következő eljárásokkal:

    -   [Alkalmazás felvétele az Intune-ba](apps-add.md)

    -   [iOS-es alkalmazáskonfigurációs szabályzat felvétele az Intune-ba](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

    -   [Alkalmazás hozzárendelése az Intune-hoz](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [iOS-es alkalmazáskonfigurációs szabályzat felvétele](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Az alkalmazások felvételéhez

### <a name="all-mtd-partners"></a>Minden MTD-partner

#### <a name="microsoft-authenticator-app-for-ios"></a>iOS-hez készült Microsoft Authenticator alkalmazás

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [ Microsoft Authenticator alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Lookout for Work Google alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.lookout.enterprise).

#### <a name="ios"></a>iOS

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [ Lookout for Work iOS alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8).

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Lookout for Work alkalmazás az Apple áruházon kívül

A Lookout for Work iOS-alkalmazást újra alá kell írnia. A Lookout az iOS App Store-on kívül terjeszti a Lookout for Work alkalmazását. Az alkalmazás terjesztése előtt újra alá kell írnia az alkalmazást az iOS vállalati fejlesztői tanúsítványával.

A részletes leírást a Lookout for Work iOS-alkalmazás újbóli aláírásáról lásd: [Lookout for Work iOS-alkalmazás újbóli aláírásának folyamata](https://personal.support.lookout.com/hc/articles/114094038714) a Lookout oldalán.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Azure AD-hitelesítés engedélyezése a Lookout for Work iOS-alkalmazáshoz

Engedélyezze az Azure Active Directory-hitelesítést iOS-felhasználók számára az alábbiak szerint:

1. Lépjen az [Azure Portalra](https://portal.azure.com), jelentkezzen be a hitelesítő adataival, majd nyissa meg az alkalmazás lapot.
  
2. Adja hozzá a **Lookout for Work iOS alkalmazást****natív ügyfélalkalmazásként**.

3. Cserélje le a **com.lookout.enterprise.yourcompanyname** sort az IPA aláírásakor választott ügyfélcsomag-azonosítóval.

4.  Adja hozzá ezt az átirányítási URI-t:**&lt;companyportal://code/>**, valamint az eredeti átirányítási URI-ja URL-kódolású verzióját.

5.  Adjon hozzá **Delegált engedélyeket** az alkalmazásához.

    > [!NOTE] 
    > További részletekért lásd:[Natív ügyfélalkalmazás konfigurálása az Azure AD-val](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

##### <a name="add-the-lookout-for-work-ipa-file"></a>A Lookout for Work .ipa-fájl hozzáadása

- Töltse fel az újból aláírt .ipa-fájlt az[iOS LOB alkalmazások hozzáadása az Intune-nal](lob-apps-ios.md) című témakörben leírtaknak megfelelően. Ezenkívül a minimum OS-verziót iOS 8.0-ra vagy újabbra kell állítania.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Skycure alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.skycure.skycure).

#### <a name="ios"></a>iOS

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [Skycure alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

### <a name="check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

#### <a name="android"></a>Android

- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). Adja meg ezt a [Check Point SandBlast Mobile alkalmazás-áruházbeli URL-címet](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) a  **7. lépésben**.

#### <a name="ios"></a>iOS

- Szerezze be az iOS alkalmazást a [Check Point SandBlast Mobile-tól](https://www.checkpoint.com/products/sandblast-mobile/). Tekintse át az [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md) témát, majd az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** adja meg az Apple áruházbeli URL-címet.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Zimperium alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en).

#### <a name="ios"></a>iOS

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [Zimperium alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8).

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Az MTD-alkalmazás társításához az iOS-es alkalmazáskonfigurációs szabályzatával

### <a name="for-lookout"></a>Lookout

- Hozza létre az iOS-es alkalmazáskonfigurációs szabályzatot az [iOS-es alkalmazáskonfigurációs szabályzat használata](app-configuration-policies-use-ios.md) témakör leírása alapján.

### <a name="for-skycure"></a>Skycure

-   Ehhez a művelethez a korábban a [Skycure Management konzolon](https://aad.skycure.com) konfigurált Azure AD-fiókot kell használni, amely megegyezik a klasszikus Intune-portálra való bejelentkezéshez használttal.

-   **Töltse le** az iOS-es alkalmazáskonfigurációs szabályzatot tartalmazó fájlt: 
    -   Lépjen a [Skycure Management konzolra](https://aad.skycure.com), és jelentkezzen be rendszergazdai azonosító adataival.
    
    -   Kattintson a **Settings** (Beállítások) &gt; **Device Management Integrations** (Eszközfelügyelet-integráció) &gt; **EMM Integration Selection** (EMM-integráció kiválasztása) elemre, válassza a **Microsoft Intune** lehetőséget, és mentse a választást.
    
    -   Kattintson az **Integration setup files** (Integráció-telepítőfájlok) hivatkozásra, és mentse a létrejövő \*.zip fájlt. A .zip-fájlban található a **skycure\_configuration.plist** fájl, amellyel létrehozható az iOS-es alkalmazáskonfigurációs szabályzat az Intune-ban.
    
    -   A Skycure iOS-es alkalmazáskonfigurációs szabályzat felvételéhez lásd a következő útmutatót:[A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md).
    
    - A **8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be a **skycure_configuration.plist** fájl tartalmát a konfigurációs szabályzat törzsébe.

A **skycure_configuration.plist**-tartalmat innen is kimásolhatja:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

- A Check Point SandBlast Mobile iOS-es alkalmazáskonfigurációs szabályzat felvételéhez tekintse át a következő útmutatót: [A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md).
    - A**8. lépésnél** válassza az **XML adatok megadása** lehetőséget, majd másolja be az alábbi tartalmat a konfigurációs szabályzat törzsébe.

```
<dict><key>MDM</key><string>INTUNE</string></dict>

```

### <a name="for-zimperium"></a>A Zimperium esetében

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

## <a name="to-assign-apps-all-mtd-partners"></a>Alkalmazások hozzárendelése (minden MTD partner)

- Lásd a következő útmutatót: [Alkalmazások csoportokhoz rendelése az Intune-nal](apps-deploy.md).

## <a name="next-steps"></a>További lépések

- [Eszközmegfelelőségi szabályzat hozzáadása MTD-hez](mtd-device-compliance-policy-create.md)

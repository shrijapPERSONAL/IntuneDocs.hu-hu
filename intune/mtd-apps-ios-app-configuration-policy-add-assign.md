---
title: "MTD-alkalmazások felvétele és hozzárendelése az Intune-hoz"
titleSuffix: Intune on Azure
description: "Az MTD-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat felvétele az Azure-beli Intune-ba"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Mobile Threat Defense- (MTD) alkalmazások felvétele és hozzárendelése az Intune-nal

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

### <a name="skycure-app-for-android"></a>Androidra készült Skycure alkalmazás

- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Skycure alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.skycure.skycure).

### <a name="skycure-app-for-ios"></a>iOS-re készült Skycure alkalmazás

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [Skycure alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/skycure/id695620821?mt=8).

### <a name="microsoft-authenticator-app-for-ios"></a>iOS-hez készült Microsoft Authenticator alkalmazás

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [ Microsoft Authenticator alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8).

### <a name="lookout-for-work-android-app"></a>Lookout for Work – Android-alkalmazás

- Lásd a következő útmutatót: [Android Áruházbeli alkalmazás felvétele a Microsoft Intune-ba](store-apps-android.md). A **7. lépésben** használja a [ Lookout for Work Google alkalmazás-áruházbeli URL-címét](https://play.google.com/store/apps/details?id=com.lookout.enterprise).

### <a name="lookout-for-work-ios-app"></a>Lookout for Work – iOS-alkalmazás

- Lásd a következő útmutatót: [iOS Store-alkalmazás felvétele a Microsoft Intune-ba](store-apps-ios.md). Az **Alkalmazásadatok konfigurálása** szakasz **5. lépésében** használja a [ Lookout for Work iOS alkalmazás-áruházbeli URL-címét](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8).

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Lookout for Work alkalmazás az Apple áruházon kívül

A Lookout for Work iOS-alkalmazást újra alá kell írnia. A Lookout az iOS App Store-on kívül terjeszti a Lookout for Work alkalmazását. Az alkalmazás terjesztése előtt újra alá kell írnia az alkalmazást az iOS vállalati fejlesztői tanúsítványával.

A részletes leírást a Lookout for Work iOS-alkalmazás újbóli aláírásáról lásd: [Lookout for Work iOS-alkalmazás újbóli aláírásának folyamata](https://personal.support.lookout.com/hc/articles/114094038714) a Lookout oldalán.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Azure AD-hitelesítés engedélyezése a Lookout for Work iOS-alkalmazáshoz

Engedélyezze az Azure Active Directory-hitelesítést iOS-felhasználók számára az alábbiak szerint:

1. Lépjen az [Azure Portalra](https://portal.sazure.com), jelentkezzen be a hitelesítő adataival, majd nyissa meg az alkalmazás lapot.
  
2. Adja hozzá a **Lookout for Work iOS alkalmazást** **natív ügyfélalkalmazásként**.

3. Cserélje le a **com.lookout.enterprise.yourcompanyname** sort az IPA aláírásakor választott ügyfélcsomag-azonosítóval.

4.  Adja hozzá ezt az átirányítási URI-t:**&lt;companyportal://code/>**, valamint az eredeti átirányítási URI-ja URL-kódolású verzióját.

5.  Adjon hozzá **Delegált engedélyeket** az alkalmazásához.

    > [!NOTE] 
    > További részletekért lásd:[Natív ügyfélalkalmazás konfigurálása az Azure AD-val](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>A Lookout for Work .ipa-fájl hozzáadása

- Töltse fel az újból aláírt .ipa-fájlt az[iOS LOB alkalmazások hozzáadása az Intune-nal](lob-apps-ios.md) című témakörben leírtaknak megfelelően. Ezenkívül a minimum OS-verziót iOS 8.0-ra vagy újabbra kell állítania.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Az MTD-alkalmazás társításához az iOS-es alkalmazáskonfigurációs szabályzatával

### <a name="for-skycure"></a>Skycure

-   A korábban a Skycure Management konzolon konfigurált Azure AD-fiókot használja, amely elvileg megegyezik a klasszikus Intune-konzolra való bejelentkezéshez használttal.

-   Készítse elő a Skycure-integrációs fájlt, amelyet korábban .zip formátumban letöltött a Skycure Management konzolról, és amelyben megtalálható az iOS-es alkalmazáskonfigurációs szabályzat paramétereit tároló **skycure\_configuration.plist** fájl.

- A Skycure iOS-es alkalmazáskonfigurációs szabályzat felvételéhez lásd a következő útmutatót:[A Microsoft Intune alkalmazáskonfigurációs szabályzatának használata iOS-hez](app-configuration-policies-use-ios.md).
    - A 8. lépésnél válassza az **XML adatok megadása** lehetőséget, majd másolja be a **skycure_configuration.plist** fájl tartalmát a konfigurációs szabályzat törzsébe.

A **skycure_configuration.plist**-tartalmat innen is kimásolhatja:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Lookout

- Hozza létre az iOS-es alkalmazáskonfigurációs szabályzatot az [iOS-es alkalmazáskonfigurációs szabályzat használata](app-configuration-policies-use-ios.md) témakör leírása alapján.

## <a name="to-assign-mtd-apps"></a>Az MTD-alkalmazások hozzárendeléséhez

- Lásd a következő útmutatót: [Alkalmazások csoportokhoz rendelése az Intune használatával](apps-deploy.md).

## <a name="next-steps"></a>További lépések

[A Skycure és az Intune közötti integráció beállítása](skycure-mtd-connector-integration.md)
[A Lookout és az Intune közötti integráció beállítása](lookout-mtd-connector-integration.md)

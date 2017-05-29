---
title: "Eszközmegfelelőségi és alkalmazásfelügyeleti szabályzatok konfigurálása Intune-migráció során | Microsoft Docs"
description: "Ez a cikk az eszközmegfelelőségi és alkalmazásfelügyeleti szabályzatok Intune-migráció során történő konfigurálásához szükséges lépéseket ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 50a8929ef31e0a322e9460f82af3ed821ade69cf
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>1. fázis: Eszközmegfelelőségi és alkalmazásfelügyeleti szabályzatok konfigurálása

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Az Intune-migráció során a fő cél az, hogy minden eszköz regisztrálva legyen, és megfeleljenek a rájuk vonatkozó szabályzatoknak. Az eszközszabályzatok nem csak a vállalati tulajdonban lévő egyfelhasználós eszközök felügyeletét segítik, hanem a saját tulajdonú (BYOD), valamint a közösen használt eszközökét is (például kioszkok, POS-eszközök, közös használatú iskolai táblagépek, illetve felhasználó nélküli iOS-es eszközök).

Lehet, hogy minden eszközplatform más beállítási lehetőségeket kínál, de az Intune eszközszabályzatai minden platformmal a következő mobileszköz-felügyeleti képességek alapján működnek együtt:

-   az egyes felhasználók által regisztrálható eszközök számának korlátozása;

-   eszközbeállítások (például eszközszintű titkosítás, jelszóhossz, kamerahasználat) kezelése;

-   alkalmazások, e-mail-profilok, VPN-profilok stb. távoli telepítése;

-   eszközszintű feltételek kiértékelése a biztonsági megfelelőségi szabályzatokhoz.

> [!IMPORTANT]
> Az eszközfelügyeleti szabályzatokat nem közvetlenül az egyes eszközökhöz vagy felhasználókhoz rendelik hozzá, hanem felhasználói csoportokhoz. A közvetlenül felhasználói csoportokra alkalmazott szabályzatok a felhasználók eszközeire, az eszközcsoportokra alkalmazottak pedig az adott csoportok tagjaira lesznek érvényesek.

## <a name="task-list-for-device-compliance-policies"></a>Feladatlista az eszközmegfelelőségi szabályzatokhoz

### <a name="task-1-add-device-groups-optional"></a>1. feladat: eszközcsoportok létrehozása (nem kötelező)

A [klasszikus Intune-portálon](https://manage.microsoft.com/) létrehozhat eszközcsoportokat, ha bizonyos felügyeleti feladatokat eszközidentitás, nem pedig felhasználói identitás alapján kell elvégeznie.

Az eszközcsoportok elsősorban kioszkok, adott helyszínre telepített vagy műszakonként mások által használt eszközök felügyelete esetén hasznosak, amelyeknek nincs kizárólagos felhasználója.

Ha az eszközök regisztrálása előtt eszközcsoportokat konfigurál, az eszközkategóriák alapján a regisztrációnál automatikusan csoportosíthatja is az eszközöket, amelyek így rögtön megkapják a csoportjukra érvényes eszközszabályzatokat.

-   Útmutató [eszközcsoportok felvételéhez](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)

-   Útmutató [eszközkategóriák konfigurálásához](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune)

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>2. feladat: erőforrás-hozzáférési profilok (Wi-Fi-, VPN- és e-mail-tanúsítványok) használata

Az erőforrás-hozzáférési profilok tanúsítványokat és hozzáférési konfigurációkat telepítenek a regisztrált eszközökre.

Amint azt az MDM-követelmények felmérése című részben már említettük, a Wi-Fi-, VPN- és e-mail-tanúsítványok üzembe helyezéséhez [működő PKI-infrastruktúrára](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) van szükség, amennyiben a cég tanúsítványalapú hitelesítést használ.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Erőforrás-hozzáférési profilok közvetlen importálása (nem kötelező)

Ha korábbi a MDM-megoldásban van a Wi-Fi-, VPN- és e-mail-tanúsítványok XML formátumú exportálását lehetővé tévő funkció, akkor lehet, hogy ezt az XML-fájlt egyszerűen be tudja importálni az Intune-ba, ha az OMA-URI-val hoz létre egyéni profilokat az androidos, iOS-es és windowsos eszközökhöz.

-   Ismertető: egyéni szabályzat hozzáadása [iOS](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)-eszközökhöz.

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>3. feladat: eszközkonfigurációs profilok létrehozása és telepítése

Az eszközszintű beállítások (például kamera letiltása, alkalmazás-áruház, egyalkalmazásos mód, kezdőképernyő stb.) betartatásához eszközkonfigurációs profilt kell létrehozni.

- További tudnivalók az [eszközkonfigurációs profilokról](https://docs.microsoft.com/intune/device-profile-create).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>iOS-es konfigurációs profilok közvetlen importálása (nem kötelező)

-   **Apple Configurator iOS-profilok (iOS 7.1 és újabb):** Ha a korábbi MDM-megoldás Apple Configurator-profilokat (.mobileconfig-fájlokat) használ, az Intune ezeket közvetlenül be tudja importálni egyéni konfigurációs szabályzatokként.

-   **iOS Mobile Application Configuration-szabályzatok:** Ha a korábbi MDM-megoldás iOS Mobile Application Configuration-szabályzatokat használ, az Intune ezeket közvetlenül be tudja importálni, amennyiben megfelelnek az Apple által tulajdonságlistákhoz megadott XML-formátumnak.

- Útmutató egyéni szabályzat felvételéhez [iOS-en](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings)

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>4. feladat: eszközmegfelelőségi szabályzatok létrehozása és telepítése (nem kötelező)

Az eszközmegfelelőségi szabályzatok biztonsági jellegű beállítások értékét vizsgálják, és jelentik, hogy mely eszközök felelnek meg a vállalati előírásoknak, és melyek nem. Az eszközmegfelelőségi szabályzatok által vizsgált biztonsági tényezők közé tartoznak például a következők:

-   PIN-kód hossza

-   Feltört állapot

-   Operációs rendszer verziója

További források az eszközmegfelelőségi szabályzatokkal kapcsolatban:

-   Az [eszközmegfelelőségi szabályzatok](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) ismertetése

-   Útmutató [eszközmegfelelőségi szabályzat létrehozásához](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)

### <a name="task-5-publish-and-deploy-apps"></a>5. feladat: alkalmazások közzététele és telepítése

Az Intune MDM használata esetén alkalmazásokat telepíthet automatikus telepítésük megkövetelésével vagy a Céges portálon való közzétételükkel.

-   Útmutató [alkalmazások felvételéhez](/intune-classic/deploy-use/add-apps)

-   Útmutató [alkalmazások telepítéséhez](/intune-classic/deploy-use/deploy-apps)

### <a name="task-6-enable-device-enrollment"></a>6. feladat: eszközök regisztrálásának lehetővé tétele

A regisztráció során kiépül a szabályozás lehetősége, és az eszköz felügyelet alá kerül.

-   Útmutató [a vállalati és a személyes tulajdonú eszközök regisztrációra való felkészítéséhez](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

-   Útmutató [a vállalati tulajdonú eszközök regisztrálásához](/intune-classic/deploy-use/manage-corporate-owned-devices)

Ha megosztott vagy felhasználó nélküli eszközöket kell regisztrálnia, használhatja a [készülékregisztráció-kezelőt /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>További lépések 

[1. fázis: Alkalmazásvédelmi szabályzatok konfigurálása /intune-classic/plan-design/migration-phase1-configure-app-protection-policies)


---
title: A dedikált vállalati Android-eszköz Intune-regisztráció beállítása
titlesuffix: Microsoft Intune
description: Ismerje meg, hogy miként regisztrálhatják az Android enterprise dedikált eszközök Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 4a6818f67ab4e3b04364b412fb8ecf71227328d4
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/17/2019
ms.locfileid: "54386915"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Dedikált vállalati Android-eszköz regisztrálása az Intune beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android-eszközök a vállalat által birtokolt, egyszer használható, teljes képernyős stílust a dedikált eszközök megoldás beállítása támogatja. Az ilyen eszközöknek egyetlen rendeltetése van, például digitális aláírás, jegynyomtatás vagy leltárkezelés, hogy csak néhányat említsünk. A rendszergazdák alkalmazások és webes hivatkozások egy adott körére korlátozzák az eszköz használatát. Ez azt is megakadályozza, hogy a felhasználók más alkalmazásokat adjanak az eszközhöz, vagy más műveleteket hajtsanak végre rajta.

Az Intune segít a beállítások és alkalmazások telepítése Android dedikált eszközökre. A Vállalati Androidra vonatkozó részletekről az [A Vállalati Android követelményei](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) című weboldal nyújt tájékoztatást.

Az ezen a módon felügyelt eszközök felhasználói fiók nélkül vannak regisztrálva az Intune-ban, és egyetlen végfelhasználóhoz sincsenek hozzárendelve. Nem rendeltetésük olyan személyes használatra szánt, vagy sok felhasználóspecifikus adatot igénylő alkalmazások futtatása, mint az Outlook vagy a Gmail.

## <a name="device-requirements"></a>Eszközkövetelmények

Eszközök az Android enterprise-dedikált eszközként kezelt követelménynek kell megfelelnie:

- Android 5.1 vagy újabb operációs rendszer.
- Az eszközökön olyan Android-disztribúciónak kell futnia, amely kapcsolódni tud a Google Mobile Services (GMS) szolgáltatáshoz. Az eszközöknek el kell érniük a GMS-t, és képesnek kell lenniük a GMS-hez való kapcsolódásra.

## <a name="set-up-android-dedicated-device-management"></a>Dedikált Androidos eszközök kezelésének beállítása

Dedikált Android-eszközök kezelésének beállításához, kövesse az alábbi lépéseket:

1. A mobileszközök kezelésének előkészítését a [**Microsoft Intune** mint mobileszköz-felügyeleti (MDM) szolgáltató megadása](mdm-authority-set.md) című témakör ismerteti. Ezt elég egyszer beállítani, amikor először állítja be az Intune-t a mobileszközök felügyeletére.
2. [Az Intune-bérlő csatlakoztatása a Vállalati Android-fiókjához](connect-intune-android-enterprise.md).
3. [Regisztrációs profil létrehozása](#create-an-enrollment-profile).
4. [Eszközcsoport létrehozása](#create-a-device-group).
5. [A dedikált eszközök regisztrálása](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Beléptetési profil létrehozása

Létre kell hoznia egy regisztrációs profilt, úgy, hogy a dedikált eszközöket regisztrálni. A profil a létrehozásakor ad egy regisztrációs jogkivonatot (véletlenszerű karakterlánc) és egy QR-kódot. Az Android operációs rendszer és az eszköz verziója, használhatja a jogkivonattal vagy QR-kód [dedikált regisztrációhoz](#enroll-the-dedicated-devices).

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza az **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** lehetőséget.
2. Válassza a **Létrehozás** lehetőséget, és töltse ki a kötelező mezőket.
    - **Név**: Írja be a nevet fogja használni a profil hozzárendelésekor a dinamikus eszközcsoporthoz.
    - **Jogkivonat-lejárati dátum**: A jogkivonat lejáratának dátuma A Google legfeljebb 90 napos érvényességi időszakot engedélyez.
3. Válassza a **Létrehozás** elemet a profil mentéséhez.

### <a name="create-a-device-group"></a>Eszközcsoport létrehozása

A cél lehet alkalmazás, és hozzárendelt vagy dinamikus eszközcsoportokra vonatkozó szabályzat is. A dinamikus AAD-eszközcsoportokat a következő lépesekkel konfigurálhatja úgy, hogy automatikusan felvegyék a megadott regisztrációs profillal regisztrált eszközöket:

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza a **Csoportok** > **Minden csoport** > **Új csoport** lehetőséget.
2. A **Csoport** panelen töltse ki a kötelező mezőket az alábbiak szerint:
    - **Csoport típusa**: Biztonság
    - **Csoport neve**: Adjon meg egy intuitív nevet (például az eszközök gyári 1)
    - **Tagság típusa**: Dinamikus eszköz
3. Válassza a **Dinamikus lekérdezés hozzáadása** lehetőséget.
4. A **Dinamikus tagsági szabályok** panelen töltse ki a mezőket az alábbiak szerint:
    - **A dinamikus tagsági szabály hozzáadása**: Egyszerű szabály
    - **Eszközök hozzáadásának helye**: enrollmentProfileName
    - A középső mezőben válassza az **Egyezés** (Match) lehetőséget.
    - Az utolsó mezőben adja meg a korábban létrehozott regisztrációs profilt.
    A dinamikus tagságra vonatkozó szabályokról bővebben lásd [az AAD-csoportok dinamikus tagsági szabályait](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) ismertető témakört. 
5. Válassza a **Lekérdezés hozzáadása** > **Létrehozás** lehetőséget.

### <a name="replace-or-remove-tokens"></a>Jogkivonatok cseréje vagy eltávolítása

A jogkivonatok és QR-kódok cserélhetők vagy eltávolíthatók.

- **Cserélje le jogkivonatot**: Létrehozhat egy új jogkivonattal vagy QR-kódot, amikor lejár egy cserélje le jogkivonatot használatával.
- **Jogkivonat visszavonása**: A jogkivonattal vagy QR-kódot azonnal lejárhat. Ettől kezdve a jogkivonat/QR-kód többé nem használható. Ez a lehetőség a következő esetekben lehet hasznos:
    - a jogkivonat/QR-kód véletlenül meg lett osztva egy jogosulatlan féllel
    - minden regisztráció befejeződött, és a jogkivonatra/QR-kódra többé nincs szükség

Egy jogkivonat/QR-kód cseréje vagy visszavonása a már regisztrált eszközöket nem érinti.

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza az **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** lehetőséget.
2. Válassza ki a profilt, amellyel dolgozni kíván.
3. Válassza a **Jogkivonat** lehetőséget.
4. A jogkivonat cseréjéhez válassza a **Jogkivonat cseréje** lehetőséget.
5. A jogkivonat visszavonásához válassza a **Jogkivonat visszavonása** lehetőséget.

## <a name="enroll-the-dedicated-devices"></a>A dedikált eszközök regisztrálása

Mostantól [dedikált eszköz](android-dedicated-devices-fully-managed-enroll.md).

## <a name="managing-apps-on-android-dedicated-devices"></a>Az Android-eszközökön dedikált alkalmazások felügyelete

Csak olyan alkalmazásokat, hozzárendelés-típus [beállítása szükséges](apps-deploy.md#to-assign-an-app) dedikált Androidos eszközökön telepíthető. Az alkalmazások a felügyelt Google Play Áruházból lesznek telepítve ugyanúgy, mint az androidos munkahelyi profilos eszközök esetében.

Az alkalmazások automatikusan frissítve lesznek a felügyelt eszközökön, amikor az alkalmazás fejlesztője frissítést tesz közzé a Google Playben.

Távolítsa el az alkalmazás Android dedikált eszközökről, a következők bármelyikét teheti:
-   Törölje az alkalmazástelepítés Kötelező értékét.
-   Hozzon létre központi eltávolítást az alkalmazáshoz.

## <a name="next-steps"></a>További lépések
- [Android-alkalmazások üzembe helyezése](apps-deploy.md)
- [Androidos alkalmazáskonfigurációs szabályzatok hozzáadása](device-profiles.md)

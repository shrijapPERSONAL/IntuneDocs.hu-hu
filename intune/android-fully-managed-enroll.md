---
title: Az Intune-regisztráció beállítása az Android Enterprise teljes körűen felügyelt eszközök
titleSuffix: Microsoft Intune
description: Ismerje meg, hogyan teljes körűen felügyelt Android Enterprise-eszközök regisztrálása az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e3615f1f090af3ce589e83f11d12e95a2f07641
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799400"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices-preview"></a>Az Intune beállítása az Android Enterprise beléptetési teljes körűen felügyelt eszközök (előzetes verzió)

Teljes körűen felügyelt vállalati Android-eszközök a vállalat által birtokolt eszközök társított egy egyetlen felhasználó, és kizárólag használt munkahelyi és személyes nem használja. A rendszergazdák a teljes eszköz kezelése és a nem érhető el a munkahelyi profilok, mint például a házirend-vezérlők kényszerítésére:
- alkalmazások telepítésének engedélyezése csak a felügyelt Google Play
- felügyelt alkalmazások eltávolításának letiltása
- megakadályozhatja, hogy a felhasználók a gyári beállításainak visszaállítása eszközökön, és így tovább.

Alkalmazások telepítése az Intune segítségével, és a beállítások az Android Enterprise eszközökre, beleértve az Android Enterprise teljes körűen felügyelt eszközök. Android Enterprise kapcsolatos részleteket lásd: [Android Enterprise követelmények](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Technikai követelmények

Az Intune önálló bérlő teljes körűen felügyelt Android Enterprise-eszközök kezeléséhez rendelkeznie kell. Teljes körűen felügyelt kezelés nem érhető el, vagy hibrid (Configuration Manager-csatlakozik) módban vagy a hagyományos Silverlight-felügyeleti konzolon.

Eszközök kezelhető, mivel az Android Enterprise teljes körűen felügyelt eszköz követelménynek kell megfelelnie:

- Android 5.1 vagy újabb operációs rendszer.
- Eszközök az Android Google Mobile Services (Konzervdobozokba) kapcsolódik, build kell futtatnia. Az eszközöknek el kell érniük a GMS-t, és képesnek kell lenniük a GMS-hez való kapcsolódásra.

Eszköz gyártója/OEM korlátozva van, ha a fenti követelmények teljesülnek-e.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Teljes körűen felügyelt Android Enterprise-eszközök kezelésének beállítása

Állítsa be az Android Enterprise teljes körűen felügyelt eszközkezelés, kövesse az alábbi lépéseket:

1. Mobileszközök kezelésének előkészítéseként kell [beállítása mobileszköz-felügyelet (MDM) szolgáltatóként **a Microsoft Intune**](mdm-authority-set.md). Ezt elég egyszer beállítani, amikor először állítja be az Intune-t a mobileszközök felügyeletére.
2. [Az Intune-bérlői fiókkal csatlakozzon az Android Enterprise-fiókjához](connect-intune-android-enterprise.md).
3. [A felhasználó a vállalat által birtokolt eszközök engedélyezése](#enable-corporate-owned-user-devices)
4. [A teljes körűen felügyelt eszközök regisztrálása](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Vállalati tulajdonban lévő felhasználói eszköz engedélyezése

1. Nyissa meg a [Intune-portálon](https://portal.azure.com) válassza **eszközregisztráció** > **Android-eszközök regisztrálási** > **vállalat által birtokolt, teljes mértékben felügyelt felhasználói eszközök (előzetes verzió)**.
2. A **felhasználói a vállalat által birtokolt eszközök beléptetésének engedélyezése**, válassza a **Igen**.

Ha ez a beállítás értéke **Igen**, is tartalmaz az alkalmazásregisztrációs adatblokkot (egy véletlenszerű karakterlánc) és a egy QR-kódot az Intune-bérlőhöz. Ez egyetlen regisztrációs jogkivonat érvényes, a felhasználók számára, és nem jár le. Attól függően, az Android operációs rendszer és az eszköz verziója, használhatja a jogkivonattal vagy QR-kódot a teljes képernyős eszköz regisztrálását.

## <a name="enroll-the-fully-managed-devices"></a>A teljes körűen felügyelt eszközök regisztrálása
Mostantól [a teljes körűen felügyelt eszközök regisztrálása](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Az előzetes verziójú funkció szempontjai
A nyilvános előzetes verziója az Android Enterprise teljes körűen felügyelt megoldás set core számos funkciót tartalmaz. Funkciójának használatával az előzetes verziójú funkciók, az aktuális kommunikációs csatornákon, a csapat valamelyik használatával kapcsolatos visszajelzését hallani szeretnénk (például [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Ebben az előzetes verzióban a következő szolgáltatásokat támogatja, az Android Enterprise teljes körűen felügyelt eszközök:
- Eszközök regisztrálása az NFC, jogkivonat bejegyzést, QR-kódot, és Zero Touch
- Eszközök konfigurálása a felhasználói csoportok számára
- Alkalmazásterjesztési és felhasználói csoportok konfigurálása


Ezen előzetes verziójú funkciók használatakor vegye figyelembe a következőket:
- Az előzetes verzió szolgáltatásai nem ajánlottak az alapvető fontosságú vagy éles környezetben üzembe helyezéséhez. 
- Előzetes verziójú funkciók vannak megvalósítva a Microsoft Intune éles szabványoknak. Azonban nem minden Intune-funkciók érhetők el a teljes körűen felügyelt Android Enterprise felhasználói eszközök segítségével. Előzetes verziójú funkciók egyértelműen címkével rendelkező "(előzetes verzió)" az Intune-konzolon. 
- Az előzetes verziójú funkciók teljes mértékben támogatottak a szokásos Intune támogatási csatornái keresztül.
- Samsung Knox mobileszköz beléptetési használatával teljes mértékben felügyelt Android Enterprise-eszközök regisztrálása nem támogatott előzetes verzióban érhető el. 
- Használatát az Intune vállalati portál alkalmazás nem támogatott az Android Enterprise teljes körűen felügyelt eszközökre. 
- Az Intune-funkciók, például a feltételes hozzáférés, az alkalmazásvédelmi szabályzatok és tanúsítvány üzembe helyezése nem támogatott előzetes verzióban érhető el. 
- Eszköz csoportokat fognak megcélozni a profil vagy alkalmazás nem támogatott előzetes verzióban érhető el. Csak felhasználói csoportot célzó használata támogatott. 
- Nincs kiváló felhasználói felület e-mail, Wi-Fi vagy VPN konfigurálásához. Alkalmazás-konfigurációs házirendek segítségével a támogatott konfigurációs beállításainak konfigurálása.

## <a name="next-steps"></a>További lépések
- [Android Enterprise teljes körűen felügyelt eszközkonfigurációs szabályzat hozzáadása](device-restrictions-android-for-work.md#device-owner-only)
- [Alkalmazáskonfigurációs szabályzatok beállítása az Android Enterprise teljes körűen felügyelt eszközök](app-configuration-policies-use-android.md)


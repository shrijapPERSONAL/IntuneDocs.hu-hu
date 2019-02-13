---
title: Az Intune-regisztráció beállítása az Android a teljes körűen felügyelt eszközök
titlesuffix: Microsoft Intune
description: Ismerje meg, miként regisztrálhatják az Android a teljes körűen felügyelt eszközöket az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 482ae185f221b3ff77534c1cfd8cccd8278965b7
ms.sourcegitcommit: 84ab7a49aad853591a4ae362382f293e29b360df
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56156168"
---
# <a name="set-up-intune-enrollment-of-android-fully-managed-devices-preview"></a>Az Intune beállítása az Android-regisztrációs teljes körűen felügyelt eszközök (előzetes verzió)

Teljes körűen felügyelt Android-eszközök társítva egy egyetlen felhasználó, és kizárólag használt munkahelyi és személyes nem használja, vállalati tulajdonú eszközök. A rendszergazdák a teljes eszköz kezelése és a nem érhető el a munkahelyi profilok, mint például a házirend-vezérlők kényszerítésére:
- alkalmazások telepítésének engedélyezése csak a felügyelt Google Play áruházban
- felügyelt alkalmazások eltávolításának letiltása
- megakadályozhatja, hogy a felhasználók a gyári beállításainak visszaállítása eszközökön, és így tovább.

Alkalmazások telepítése az Intune segítségével, és a beállítások az Android enterprise eszközökre, például Android teljes mértékben felügyelt eszközök. A Vállalati Androidra vonatkozó részletekről az [A Vállalati Android követelményei](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) című weboldal nyújt tájékoztatást.

## <a name="technical-requirements"></a>Technikai követelmények

Rendelkeznie kell az Intune önálló bérlő Android kezelése teljes mértékben felügyelt eszközökre. Teljes körűen felügyelt kezelés nem érhető el, vagy hibrid (SCCM-csatlakozik) módban vagy a hagyományos Silverlight-felügyeleti konzolon.

Eszközök kezelhető, mivel az Android a teljes körűen felügyelt eszköz követelménynek kell megfelelnie:

- Android 5.1 vagy újabb operációs rendszer.
- Eszközök az Android Google Mobile Services (Konzervdobozokba) kapcsolódik, build kell futtatnia. Az eszközöknek el kell érniük a GMS-t, és képesnek kell lenniük a GMS-hez való kapcsolódásra.

Eszköz gyártója/OEM korlátozva van, ha a fenti követelmények teljesülnek-e.

## <a name="set-up-android-fully-managed-device-management"></a>Állítsa be az Android a teljes körűen felügyelt eszköz kezelése

Beállítása az Android teljes körűen felügyelt eszközkezelés, kövesse az alábbi lépéseket:

1. Mobileszközök kezelésének előkészítéseként kell [beállítása mobileszköz-felügyelet (MDM) szolgáltatóként **a Microsoft Intune**](mdm-authority-set.md). Ezt elég egyszer beállítani, amikor először állítja be az Intune-t a mobileszközök felügyeletére.
2. [Az Intune-bérlő csatlakoztatása a Vállalati Android-fiókjához](connect-intune-android-enterprise.md).
3. [A felhasználó a vállalat által birtokolt eszközök engedélyezése](#enable-corporate-owned-user-devices)
4. [A teljes körűen felügyelt eszközök regisztrálása](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Vállalati tulajdonban lévő felhasználói eszköz engedélyezése

1. Nyissa meg a [Intune-portálon](https://portal.azure.com) válassza **eszközregisztráció** > **Android-eszközök regisztrálási** > **vállalat által birtokolt, teljes mértékben felügyelt felhasználói eszközök (előzetes verzió)**.
2. A **felhasználói a vállalat által birtokolt eszközök beléptetésének engedélyezése**, válassza a **Igen**.

Ha ez a beállítás értéke **Igen**, is tartalmaz az alkalmazásregisztrációs adatblokkot (egy véletlenszerű karakterlánc) és a egy QR-kódot az Intune-bérlőhöz. Ez egyetlen regisztrációs jogkivonat érvényes, a felhasználók számára, és nem jár le. Attól függően, az Android operációs rendszer és az eszköz verziója, használhatja a jogkivonattal vagy QR-kódot a teljes képernyős eszköz regisztrálását.

## <a name="enroll-the-fully-managed-devices"></a>A teljes körűen felügyelt eszközök regisztrálása
Mostantól [a teljes körűen felügyelt eszközök regisztrálása](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Az előzetes verziójú funkció szempontjai
A nyilvános előzetes verziója az Android a teljes körűen felügyelt megoldás set core számos funkciót tartalmaz. Funkciójának használatával az előzetes verziójú funkciók, az aktuális kommunikációs csatornákon, a csapat valamelyik használatával kapcsolatos visszajelzését hallani szeretnénk (például [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Ebben az előzetes verzióban a következő szolgáltatásokat támogatja, az Android a teljes körűen felügyelt eszközök:
- Eszközök regisztrálása az NFC, jogkivonat bejegyzést, QR-kódot, és Zero Touch
- Eszközök konfigurálása a felhasználói csoportok számára
- Alkalmazásterjesztési és felhasználói csoportok konfigurálása


Ezen előzetes verziójú funkciók használatakor vegye figyelembe a következőket:
- Az előzetes verzió szolgáltatásai nem ajánlottak az alapvető fontosságú vagy éles környezetben üzembe helyezéséhez. 
- Előzetes verziójú funkciók vannak megvalósítva a Microsoft Intune éles szabványoknak. Azonban nem minden Intune-funkciók Android rendszerű eszközökön használható-e teljes körűen felügyelt felhasználói eszközök. Előzetes verziójú funkciók egyértelműen címkével rendelkező "(előzetes verzió)" az Intune-konzolon. 
- Az előzetes verziójú funkciók teljes mértékben támogatottak a szokásos Intune támogatási csatornái keresztül.
- Android regisztrálása teljes körűen felügyelt mobileszköz beléptetési előzetes verzióban nem támogatott Samsung Knox eszközök. 
- Használatát az Intune vállalati portál alkalmazás nem támogatott Android a teljes körűen felügyelt eszközökre. 
- Az Intune-funkciók, például a feltételes hozzáférés, az alkalmazásvédelmi szabályzatok és tanúsítvány üzembe helyezése nem támogatott előzetes verzióban érhető el. 
- Eszköz csoportokat fognak megcélozni a profil vagy alkalmazás nem támogatott előzetes verzióban érhető el. Csak felhasználói csoportot célzó használata támogatott. 
- Nincs kiváló felhasználói felület e-mail, Wi-Fi vagy VPN konfigurálásához. Alkalmazás-konfigurációs házirendek segítségével a támogatott konfigurációs beállításainak konfigurálása.

## <a name="next-steps"></a>További lépések
- [Az Android a teljes körűen felügyelt eszközkonfigurációs szabályzat hozzáadása](device-restrictions-android-for-work.md#device-owner-only)
- [Konfigurációs szabályzatok konfigurálása az Android a teljes körűen felügyelt eszközök](app-configuration-policies-use-android.md)


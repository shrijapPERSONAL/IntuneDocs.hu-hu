---
title: Alkalmazáskonfigurációs szabályzatok a Microsoft Intune-hoz
titleSuffix: ''
description: Ismertető a Microsoft Intune alkalmazáskonfigurációs szabályzatainak iOS- vagy Android-eszközön való használatához.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 703fafec3799b1552ec275c7c88b24b42d2259b9
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044009"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Alkalmazáskonfigurációs szabályzatok a Microsoft Intune-hoz

iOS- vagy Android-alkalmazáshoz a Microsoft Intune alkalmazáskonfigurációs szabályzatainak használatával adhat meg konfigurációs beállításokat. Ezek a konfigurációs beállítások lehetővé teszik az alkalmazás testre szabását. A konfigurációs házirendek nem rendel közvetlenül a felhasználók vagy eszközök számára. Ehelyett a konfigurációs szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A konfigurációs szabályzatbeállítások akkor használatosak, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

Alkalmazáskonfigurálási szabályzatot rendelhet a felhasználók és eszközök egy csoportjához belefoglalási és kizárási hozzárendelések kombinációjával. Miután hozzáadta az alkalmazáskonfigurálási szabályzatot, beállíthatja az alkalmazáskonfigurálási szabályzat hozzárendeléseit. A szabályzat hozzárendeléseinek beállításakor felvehet vagy kizárhat a szabályzat hatálya alá eső felhasználói csoportokat. Amikor felvesz egy vagy több csoportot, kiválaszthat bizonyos csoportokat, vagy választhat beépített csoportokat. Beépített csoportok a következők: **Minden felhasználó**, **Minden eszköz**, és **Minden felhasználó és minden eszköz**.

Egy alkalmazás-konfigurációs beállítás, például szükség lehet, hogy adhatók meg a következő adatokat:

- Egyéni portszám
- Nyelvi beállítások
- Biztonsági beállítások
- Márkajelzési beállítások, például a vállalat logója

Ha megadja ezeket a beállításokat felhasználók ehelyett sikerült terjednek helytelenül, amely képes növelheti az segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

Alkalmazáskonfigurációs szabályzatok segítséget nyújt a problémák alkalmazás-telepítés nyújthatnak azáltal, hogy configation beállításokat rendelhet egy szabályzatot, amely van hozzárendelve a felhasználókhoz, az alkalmazás futtatása előtt. A beállítások megadása ezek után automatikusan történik, és nincs szükség felhasználói beavatkozásra.

A konfigurációs beállítások akkor használatosak, amikor egy alkalmazás keresi azokat. Az alkalmazások általában a felhasználó általi első futtatásukkor keresik a konfigurációs beállításokat.

Az Intune alkalmazáskonfigurációinak használatára két lehetőség van:
 - **Felügyelt eszközök** – Az eszköz mobileszköz-kezelő (MDM) szolgáltatója az Intune.
 - **Felügyelt alkalmazások** – Az alkalmazás eszközregisztráció nélküli felügyelet alá tartozik.

> [!NOTE]
> A Microsoft Intune rendszergazdájaként szabályozhatja, hogy melyik felhasználói fiókok legyenek hozzáadva a Microsoft Office-alkalmazásokhoz a felügyelt eszközökön. A hozzáférést korlátozhatja csak a szervezeti felhasználói fiókokra, és blokkolhatja a személyes fiókok használatát a regisztrált eszközökön. A támogató alkalmazások feldolgozzák az alkalmazáskonfigurációt, majd eltávolítják és letiltják a nem jóváhagyott fiókokat.

## <a name="apps-that-support-app-configuration"></a>Az alkalmazáskonfigurációt támogató alkalmazások

Az alkalmazáskonfigurációs szabályzatokat az azokat támogató alkalmazásokhoz használhatja. Az Intune alkalmazáskonfigurációjának támogatásához az alkalmazásoknak támogatniuk kell az alkalmazáskonfigurációk használatát. Részletekért forduljon az alkalmazás forgalmazójához.

Előkészítheti az üzletági alkalmazásokat az Intune App SDK az alkalmazásba való belefoglalásával, vagy az alkalmazás annak fejlesztése utáni burkolásával. Az Intune App SDK, iOS és Android rendszeren is elérhető lehetővé teszi, hogy az alkalmazás az Intune alkalmazáskonfigurációs szabályzatainak. Arra törekszik, hogy minimálisra csökkentse az alkalmazásfejlesztő által végzendő kódmódosítás mennyiségét. További információ: [Az Intune App SDK áttekintése](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Graph API-támogatás az alkalmazáskonfigurációhoz

Mindezek mellett az alkalmazáskonfigurációs feladatok elvégzéséhez a Graph API-t is használhatja. További információk: [Graph API-kézikönyv ‒ MAM célzott konfiguráció](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>További lépések

### <a name="managed-devices"></a>Felügyelt eszközök

 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt az iOS-eszközeivel.  Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása kezelt iOS-eszközökhöz](app-configuration-policies-use-ios.md).
 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt az Android-eszközeivel.  Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása kezelt Android-eszközökhöz](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Felügyelt alkalmazások

 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt a felügyelt alkalmazásokkal. Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül](app-configuration-policies-managed-app.md).

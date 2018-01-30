---
title: "Az Intune alkalmazáskonfigurációs szabályzatai | Microsoft Docs"
titlesuffix: Azure portal
description: "Ismerkedés az Intune alkalmazáskonfigurációs szabályzatainak használatával."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7267de95d36ed0e27c8a720599cc78004cd71d3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="app-configuration-policies-for-intune"></a>Az Intune alkalmazáskonfigurációs szabályzatai

A Microsoft Intune alkalmazáskonfigurációs szabályzataival beállításokat adhat meg a felhasználók által futtatott iOS- és Android-alkalmazásokhoz. Egy alkalmazás kérheti a felhasználótól például a következők megadását:

- Egyéni portszám.
- Nyelvi beállítások.
- Biztonsági beállítások.
- Márkajelzési beállítások, például a vállalat logója.

Ha ezeket a beállításokat a felhasználó helytelenül adja meg, az növelheti a segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

Az alkalmazáskonfigurációs szabályzatok segítséget nyújthatnak e problémák megoldásában, mivel még az alkalmazás futtatása előtt hozzá tudják rendelni a beállításokat a szabályzat által érintett felhasználókhoz. A beállítások megadása ezek után automatikusan történik, és nincs szükség felhasználói beavatkozásra.

A házirendeket nem kell közvetlenül felhasználókhoz vagy eszközökhöz rendelni. Ehelyett a szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A szabályzatban meghatározott beállítások használatára akkor kerül sor, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

Az Intune alkalmazáskonfigurációinak használatára két lehetőség van:
 - **Felügyelt eszközök**  
   Az eszköz mobileszköz-kezelő (MDM) szolgáltatója az Intune.
 - **Felügyelt alkalmazások**  
   Az alkalmazás eszközregisztráció nélküli felügyelet alá tartozik.

## <a name="apps-that-support-app-configuration"></a>Az alkalmazáskonfigurációt támogató alkalmazások

Az alkalmazáskonfigurációs szabályzatokat az azokat támogató alkalmazásokhoz használhatja. Az Intune alkalmazáskonfigurációjának támogatásához az alkalmazásoknak támogatniuk kell az alkalmazáskonfigurációk használatát. Részletekért forduljon az alkalmazás forgalmazójához.

Előkészítheti az üzletági alkalmazásokat az Intune App SDK az alkalmazásba való belefoglalásával, vagy az alkalmazás annak fejlesztése utáni burkolásával. Az iOS és az Android platformhoz is elérhető Intune App SDK lehetővé teszi az alkalmazások számára az Intune alkalmazásvédelmi szabályzatainak használatát. Arra törekszik, hogy minimálisra csökkentse az alkalmazásfejlesztő által végzendő kódmódosítás mennyiségét. További információ: [Az Intune App SDK áttekintése](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Graph API-támogatás az alkalmazáskonfigurációhoz

Mindezek mellett az alkalmazáskonfigurációs feladatok elvégzéséhez a Graph API-t is használhatja. További információk: [Graph API-kézikönyv ‒ MAM célzott konfiguráció](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>További lépések

### <a name="managed-devices"></a>Felügyelt eszközök

 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt az iOS-eszközeivel.  Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása kezelt iOS-eszközökhöz](app-configuration-policies-use-ios.md).
 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt az Android-eszközeivel.  Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása kezelt Android-eszközökhöz](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Felügyelt alkalmazások

 - Megtudhatja, hogyan használhatja az alkalmazáskonfigurációt a felügyelt alkalmazásokkal. Lásd: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül](app-configuration-policies-managed-app.md).
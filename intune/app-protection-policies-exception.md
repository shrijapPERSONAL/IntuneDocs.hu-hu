---
title: Az adatátviteli szabályzat kivételei alkalmazások esetén
titleSuffix: Microsoft Intune
description: Kivételeket hozhat létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30e1ae80ccfdc94bf352b9596df5ea4b0752d43a
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61490178"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Kivételek létrehozása az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz

A rendszergazdák kivételeket hozhatnak létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz. A kivételekkel meghatározható, hogy mely nem felügyelt alkalmazások végezhetnek felügyelt alkalmazásokból kiinduló és oda irányuló adatátvitelt. Az informatikai RÉSZLEG meg kell bízniuk a nem felügyelt alkalmazásokban, beleértve az a kivételek listáján. 

>[!WARNING] 
> Az adatátviteli szabályzat kivételeinek módosítása az Ön felelőssége. A szabályzathoz való hozzáadással engedélyezi, hogy a nem felügyelt alkalmazások (azaz az Intune által nem kezelt alkalmazások) hozzáférjenek a felügyelt alkalmazások által védett adatokhoz. A védett adatokhoz való hozzáférés azonban biztonsági kockázatokkal járhat. Ezért csak olyan alkalmazások esetén hozzon létre adatátviteli kivételeket, amelyeket megbízhatónak tekint a cég, de amelyek nem támogatják az Intune alkalmazásvédelmi szabályzatokat (más néven APP-t). Emellett csakis olyan alkalmazásokhoz ajánlott kivételeket megadni, amelyek nem jelentenek adatszivárgási kockázatot.

Az Intune alkalmazásvédelmi szabályzattal, beállítás belül **///az alkalmazás átadhat adatokat más alkalmazásoknak** való **szabályzattal felügyelt alkalmazások** azt jelenti, hogy az alkalmazás csak az Intune által felügyelt alkalmazások küldhetnek adatokat. Adott alkalmazásokra, amelyek nem támogatják az Intune APP adatátvitel engedélyeznie kell, ha a házirend alóli kivételek használatával létrehozhat **válassza ki a mentesítendő alkalmazásokat**. A kivételekkel az Intune által kezelt alkalmazások URL-protokoll (iOS) vagy csomagnév (Android) alapján hívhatnak meg nem kezelt alkalmazásokat. Alapértelmezés szerint az Intune hozzáadja a fontos natív alkalmazásokat a kivételek alapértelmezett listájához. 

> [!NOTE]
> Az adatátviteli szabályzat kivételeinek módosítása vagy bővítése, például a korlátozások kivágása, másolása és beillesztése, nincs hatással más alkalmazásvédelmi szabályzatokra. 

## <a name="ios-data-transfer-exceptions"></a>Az iOS-es adatátviteli szabályzat kivételei
Az iOS-es szabályzatok esetén URL-protokoll alapján konfigurálhatók az adatátviteli kivételek. Ha kivételt szeretne hozzáadni, olvassa el az alkalmazás fejlesztője által készített dokumentációt, és ellenőrizze, milyen URL-protokollok vannak támogatva. IOS-es adatátviteli kivételekről kapcsolatos további információkért lásd: [iOS alkalmazás alkalmazásvédelmi szabályzat beállításai – adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> A Microsoft nem rendelkezik olyan módszerrel, amellyel manuálisan megkereshető lenne az URL protokoll alkalmazáskivételek külső alkalmazásokhoz való létrehozáshoz. 

## <a name="android-data-transfer-exceptions"></a>Az androidos adatátviteli szabályzat kivételei
Az androidos szabályzatok esetén alkalmazáscsomagok alapján konfigurálhatók az adatátviteli kivételek. A kivétel létrehozásához a kivételként hozzáadni kívánt alkalmazás csomagnevét a **Google Play** áruházban az alkalmazás oldalán találja meg. Az Androidos adatátviteli kivételekről kapcsolatos további információkért lásd: [Android-alkalmazások alkalmazásvédelmi szabályzat beállításai – adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Az alkalmazás csomagazonosítóját úgy tudja megtalálni, hogy a Google Play áruházban megkeresi az alkalmazás oldalát. A csomagazonosítót az alkalmazáscsomag URL-címe tartalmazza. Például a Microsoft Word alkalmazás azonosítója **com.microsoft.office.word**.

### <a name="example"></a>Példa
Ha a **Webex** csomagot kivételként hozzáadja a MAM adatátviteli szabályzatához, akkor a felügyelt Outlook-e-mailekben a Webex-hivatkozásokat közvetlenül a Webex-alkalmazásban lehet megnyitni. Az adatátvitel azonban továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban.

- iOS-es **Webex** példa:   Ha a **Webex** alkalmazást meg tudja, hogy az informatikai engedélyezett az Intune által felügyelt alkalmazások, a következő karakterláncot egy adatátviteli kivételt kell adnia: <code>wbx</code>
    
 - iOS-es **Maps** példa:  A natív való **Maps** alkalmazást meg tudja, hogy az informatikai engedélyezett az Intune által felügyelt alkalmazások, a következő karakterláncot egy adatátviteli kivételt kell adnia: <code>maps</code>

- Android **Webex** példa:   Ha a **Webex** alkalmazást meg tudja, hogy az informatikai engedélyezett az Intune által felügyelt alkalmazások, a következő karakterláncot egy adatátviteli kivételt kell adnia: <code>com.cisco.webex.meetings</code>
    
- Android **SMS** példa:   A natív való **SMS** alkalmazást meg tudja, hogy az informatikai engedélyezett az Intune által kezelt alkalmazás különböző üzenetkezelő alkalmazásokban és Android-eszközökhöz, hozzá kell adnia az adatátviteli kivételekről a következő sztringekhez: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>További lépések

- [Alkalmazásvédelmi szabályzatok létrehozása és telepítése](app-protection-policies.md)
- [iOS-es alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Androidos alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions)

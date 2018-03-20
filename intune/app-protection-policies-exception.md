---
title: "Az adatátviteli szabályzat kivételei alkalmazások esetén"
titleSuffix: Microsoft Intune
description: "Kivételeket hozhat létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1e37e78f7272b0f53f974eccb20c7e02574a9a9
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Kivételek létrehozása az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A rendszergazdák kivételeket hozhatnak létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz. A kivételekkel meghatározható, hogy mely nem felügyelt alkalmazások végezhetnek felügyelt alkalmazásokból kiinduló és oda irányuló adatátvitelt. A kivételek listáján csak olyan nem felügyelt alkalmazások szerepelhetnek, amelyeket az informatikai szolgálat megbízhatónak minősít. 

>[!WARNING] 
> Az adatátviteli szabályzat kivételeinek módosítása az Ön felelőssége. A szabályzathoz való hozzáadással engedélyezi, hogy a nem felügyelt alkalmazások (azaz az Intune által nem kezelt alkalmazások) hozzáférjenek a felügyelt alkalmazások által védett adatokhoz. A védett adatokhoz való hozzáférés azonban biztonsági kockázatokkal járhat. Ezért csak olyan alkalmazások esetén hozzon létre adatátviteli kivételeket, amelyeket megbízhatónak tekint a cég, de amelyek nem támogatják az Intune alkalmazásvédelmi szabályzatokat (más néven APP-t). Emellett csakis olyan alkalmazásokhoz ajánlott kivételeket megadni, amelyek nem jelentenek adatszivárgási kockázatot.

Ez a funkció akkor érvényes, ha olyan Intune alkalmazásvédelmi szabályzatot hoz létre, amelynél az adatátvitel a **Csak felügyelt alkalmazások** lehetőséggel van beállítva. Ha az adatátviteli szabályzat **Csak felügyelt alkalmazások** beállítással lett létrehozva, akkor a kivételektől eltekintve az adatátvitel továbbra is az Intune által kezelt alkalmazásokra korlátozódik. Korlátozásokat protokollokkal (iOS) vagy csomagokkal hozhat létre (Android).

Ezt a funkciót úgy is konfigurálhatja, hogy engedélyezve legyenek a kivételek az Intune MAM alkalmazásvédelmi szabályzatának **adatátvételi korlátozásai** alól. Ez a szabályzat csak akkor szükséges, ha engedélyezni szeretné, hogy az Intune APP-t nem támogató alkalmazásokba is végezhető legyen adatátvitel. Ez a szabályzat lehetővé teszi az Intune által kezelt alkalmazások számára, hogy a **Csak felügyelt alkalmazások** beállítás mellett is meg tudjanak hívni nem felügyelt alkalmazásokat URL-protokoll (iOS) vagy csomagnév (Android) alapján. A fontos natív alkalmazásokat az Intune hozzáadja a kivételek alapértelmezett listájához. 

## <a name="ios-data-transfer-exceptions"></a>Az iOS-es adatátviteli szabályzat kivételei
Az iOS-es szabályzatok esetén URL-protokoll alapján konfigurálhatók az adatátviteli kivételek. Ha kivételt szeretne hozzáadni, olvassa el az alkalmazás fejlesztője által készített dokumentációt, és ellenőrizze, milyen URL-protokollok vannak támogatva. Az iOS-es adatátviteli kivételekről az [iOS-es alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions) című témakörben talál további információt.

## <a name="android-data-transfer-exceptions"></a>Az androidos adatátviteli szabályzat kivételei
Az androidos szabályzatok esetén alkalmazáscsomagok alapján konfigurálhatók az adatátviteli kivételek. A kivétel létrehozásához a kivételként hozzáadni kívánt alkalmazás csomagnevét a **Google Play** áruházban az alkalmazás oldalán találja meg. Az androidos adatátviteli kivételekről az [Androidos alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions) című témakörben talál további információt.

### <a name="example"></a>Példa
Ha a **Webex** csomagot kivételként hozzáadja a MAM adatátviteli szabályzatához, akkor a felügyelt Outlook-e-mailekben a Webex-hivatkozásokat közvetlenül a Webex-alkalmazásban lehet megnyitni. Az adatátvitel azonban továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban.

- iOS-es **Webex**-példa: ha engedélyezni szeretné, hogy a **Webex** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás, adatátviteli kivételt kell hozzáadnia a következő sztringhez: <code>wbx</code>.

- Androidos **Webex**-példa: ha engedélyezni szeretné, hogy a **Webex** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás, adatátviteli kivételt kell hozzáadnia a következő sztringhez: <code>com.cisco.webex.meetings</code>. 

## <a name="next-steps"></a>További lépések

- [Alkalmazásvédelmi szabályzatok létrehozása és telepítése](app-protection-policies.md)
- [iOS-es alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Androidos alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions)

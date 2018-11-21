---
title: Az adatátviteli szabályzat kivételei alkalmazások esetén
titleSuffix: Microsoft Intune
description: Kivételeket hozhat létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6a2507dc7b920d446b6f7fe78aa7b90f6c31322f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52178403"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Kivételek létrehozása az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A rendszergazdák kivételeket hozhatnak létre az Intune Mobilalkalmazás-kezelés (MAM) adatátviteli szabályzataihoz. A kivételekkel meghatározható, hogy mely nem felügyelt alkalmazások végezhetnek felügyelt alkalmazásokból kiinduló és oda irányuló adatátvitelt. A kivételek listáján csak olyan nem felügyelt alkalmazások szerepelhetnek, amelyeket az informatikai szolgálat megbízhatónak minősít. 

>[!WARNING] 
> Az adatátviteli szabályzat kivételeinek módosítása az Ön felelőssége. A szabályzathoz való hozzáadással engedélyezi, hogy a nem felügyelt alkalmazások (azaz az Intune által nem kezelt alkalmazások) hozzáférjenek a felügyelt alkalmazások által védett adatokhoz. A védett adatokhoz való hozzáférés azonban biztonsági kockázatokkal járhat. Ezért csak olyan alkalmazások esetén hozzon létre adatátviteli kivételeket, amelyeket megbízhatónak tekint a cég, de amelyek nem támogatják az Intune alkalmazásvédelmi szabályzatokat (más néven APP-t). Emellett csakis olyan alkalmazásokhoz ajánlott kivételeket megadni, amelyek nem jelentenek adatszivárgási kockázatot.

Ha az Intune alkalmazásvédelmi szabályzataiban a **Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak** beállítást a **Szabályzat által felügyelt alkalmazások** beállításra állítja, az alkalmazás csak olyan alkalmazásokba vihet át adatokat, amelyeket az Intune kezel. Ha olyan alkalmazások számára szeretné engedélyezni az adatátvitelt, amelyek nem támogatják az Intune APP-t, a **Kivételt képező alkalmazások** lehetőség használatával kivételeket hozhat létre. A kivételekkel az Intune által kezelt alkalmazások URL-protokoll (iOS) vagy csomagnév (Android) alapján hívhatnak meg nem kezelt alkalmazásokat. Alapértelmezés szerint az Intune hozzáadja a fontos natív alkalmazásokat a kivételek alapértelmezett listájához. 

> [!NOTE]
> Az adatátviteli szabályzat kivételeinek módosítása vagy bővítése, például a korlátozások kivágása, másolása és beillesztése, nincs hatással más alkalmazásvédelmi szabályzatokra. 

## <a name="ios-data-transfer-exceptions"></a>Az iOS-es adatátviteli szabályzat kivételei
Az iOS-es szabályzatok esetén URL-protokoll alapján konfigurálhatók az adatátviteli kivételek. Ha kivételt szeretne hozzáadni, olvassa el az alkalmazás fejlesztője által készített dokumentációt, és ellenőrizze, milyen URL-protokollok vannak támogatva. Az iOS-es adatátviteli kivételekről az [iOS-es alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions) című témakörben talál további információt.

> [!NOTE]
> A Microsoft nem rendelkezik olyan módszerrel, amellyel manuálisan megkereshető lenne az URL protokoll alkalmazáskivételek külső alkalmazásokhoz való létrehozáshoz. 

## <a name="android-data-transfer-exceptions"></a>Az androidos adatátviteli szabályzat kivételei
Az androidos szabályzatok esetén alkalmazáscsomagok alapján konfigurálhatók az adatátviteli kivételek. A kivétel létrehozásához a kivételként hozzáadni kívánt alkalmazás csomagnevét a **Google Play** áruházban az alkalmazás oldalán találja meg. Az androidos adatátviteli kivételekről az [Androidos alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions) című témakörben talál további információt.


>[!TIP]
> Az alkalmazás csomagazonosítóját úgy tudja megtalálni, hogy a Google Play áruházban megkeresi az alkalmazás oldalát. A csomagazonosítót az alkalmazáscsomag URL-címe tartalmazza. Például a Microsoft Word alkalmazás azonosítója **com.microsoft.office.word**.

### <a name="example"></a>Példa
Ha a **Webex** csomagot kivételként hozzáadja a MAM adatátviteli szabályzatához, akkor a felügyelt Outlook-e-mailekben a Webex-hivatkozásokat közvetlenül a Webex-alkalmazásban lehet megnyitni. Az adatátvitel azonban továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban.

- iOS-es **Webex**-példa: ha engedélyezni szeretné, hogy a **Webex** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás, adatátviteli kivételt kell hozzáadnia a következő sztringhez: <code>wbx</code>
    
 - iOS-es **Maps**-példa: ha engedélyezni szeretné, hogy a natív **Maps** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás, adatátviteli kivételt kell hozzáadnia a következő sztringhez: <code>maps</code>

- Androidos **Webex**-példa: ha engedélyezni szeretné, hogy a **Webex** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás, adatátviteli kivételt kell hozzáadnia a következő sztringhez: <code>com.cisco.webex.meetings</code>
    
- Androidos **SMS**-példa: ha engedélyezni szeretné, hogy a natív **SMS** alkalmazást meg tudja hívni egy Intune által kezelt alkalmazás különböző üzenetkezelő alkalmazásokban és Android-eszközökön, adatátviteli kivételeket kell hozzáadnia a következő sztringekhez: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>További lépések

- [Alkalmazásvédelmi szabályzatok létrehozása és telepítése](app-protection-policies.md)
- [iOS-es alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Androidos alkalmazásvédelmi szabályzat beállításai – Adatátviteli kivételek](app-protection-policy-settings-android.md#data-transfer-exemptions)

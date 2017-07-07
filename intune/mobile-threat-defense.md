---
title: Mobile Threat Defense az Intune-nal
titleSuffix: Intune Azure preview
description: "A vállalati eszközökhöz való hozzáférés védelme az eszközkockázat alapján"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec45b9445f2737ad99852ebf46cc40c03537a2e5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>A Mobile Threat Defense integrációja az Intune-nal


Az Intune Mobile Threat Defense-összekötők segítségével saját megfelelőségi szabályzataihoz és feltételes hozzáférési szabályaihoz olyan információkat használhat fel, amelyek egy Ön által kiválasztott, mobilfenyegetések elleni védelmet biztosító szállítótól származnak. Ez lehetővé teszi, hogy a rendszergazda magán a veszélyeknek kitett mobileszközön egy újabb védelmi réteggel védje a vállalati erőforrásokat, például az Exchange-et vagy a SharePointot.

## <a name="what-problem-does-this-solve"></a>Milyen problémára nyújt ez megoldást?

A vállalatoknak meg kell védeniük érzékeny adataikat a folyamatosan keletkező különböző veszélyforrásoktól, így a fizikai, az alkalmazás- és a hálózati alapú fenyegetésektől, valamint az operációs rendszer biztonsági réseitől.
A vállalatok hagyományosan a számítógépeiket védik a rosszindulatú támadásoktól, miközben a mobileszközök figyelés és védelem nélkül maradnak. Noha a mobilplatformok operációs rendszerei rendelkeznek olyan beépített védelmi technikákkal, mint az alkalmazások elkülönítése és az ellenőrzött alkalmazásáruházak, e platformok továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Ma már egyre több alkalmazott használ mobileszközöket munkatevékenységekre, így bizalmas adatokhoz is hozzá kell férniük. Az eszközöknek védelemre van szükségük az egyre kifinomultabb támadásokkal szemben.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Az Intune Mobile Threat Defense-összekötők működése

Az összekötő úgy védi a vállalati erőforrásokat, hogy egy kommunikációs csatornát hoz létre az Intune és egy Ön által választott, mobilfenyegetések elleni védelmet nyújtó szállító között. Az Intune Mobile Threat Defense-partnerek olyan intuitív, egyszerűen üzembe helyezhető alkalmazásokat kínálnak a mobileszközökhöz, amelyek folyamatosan vizsgálják és elemzik a fenyegetéseket, majd az információt jelentés vagy végrehajtás céljából megosztják az Intune-nal. Ha például egy ilyen Mobile Threat Defense-alkalmazás azt jelzi a szállítónak, hogy a hálózat valamely telefonja egy közbeékelődéses támadásnak kitett hálózathoz csatlakozott, akkor ezt az információt megosztja, és megtörténik a kockázat besorolása is (alacsony, közepes vagy magas). Ez összevethető az Ön által az Intune-ban engedélyezett kockázati szintekkel, és eldönthető, hogy a hozzáférés bizonyos erőforrásokhoz fel legyen-e függesztve, amíg az eszköz a veszélynek kitett hálózathoz csatlakoztatva van.

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Ha a Mobile Threat Defense rendszer fertőzöttnek tekint egy eszközt:

![A Mobile Threat Defense fertőzöttnek minősíti az eszközt](./media/MTD-image-1.png)

Ha az eszközről elhárul a veszély, a hozzáférés újra engedélyezett:

![A Mobile Threat Defense megadja a hozzáférést](./media/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partnerek

A vállalati erőforrásokhoz való hozzáférés védelme az eszköz-, a hálózati és az alkalmazáskockázat alapján:

- [A Lookout használatával](lookout-mobile-threat-defense-connector.md)
- [A Skycure használatával](skycure-mobile-threat-defense-connector.md)
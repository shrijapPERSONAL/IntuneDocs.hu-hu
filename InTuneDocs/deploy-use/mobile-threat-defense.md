---
title: Intune Mobile Threat Defense | Microsoft Docs
description: "A vállalati eszközökhöz való hozzáférés védelme az eszközkockázat alapján."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b7ab3041a38bd394195a67690d245d1ad9fd0566
ms.openlocfilehash: fd54a1c94c9a4a279710d6be9f7cfe3b48468cb7
ms.lasthandoff: 03/03/2017


---

# <a name="intune-mobile-threat-defense-connectors"></a>Intune Mobile Threat Defense-összekötők

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune Mobile Threat Defense-összekötők segítségével saját megfelelőségi szabályzataihoz és feltételes hozzáférési szabályaihoz olyan információkat használhat fel, amelyek egy Ön által kiválasztott, mobilfenyegetések elleni védelmet biztosító szállítótól származnak. Ez lehetővé teszi, hogy a rendszergazda magán a veszélyeknek kitett mobileszközön egy újabb védelmi réteggel védje a vállalati erőforrásokat, például az Exchange-et vagy a SharePointot.

## <a name="what-problem-does-this-solve"></a>Milyen problémára nyújt ez megoldást?

A vállalatoknak meg kell védeniük érzékeny adataikat a folyamatosan keletkező különböző veszélyforrásoktól, így a fizikai, az alkalmazás- és a hálózati alapú fenyegetésektől, valamint az operációs rendszer biztonsági réseitől.
A vállalatok hagyományosan a számítógépeiket védik a rosszindulatú támadásoktól, miközben a mobileszközök figyelés és védelem nélkül maradnak. Noha a mobilplatformok operációs rendszerei rendelkeznek olyan beépített védelmi technikákkal, mint az alkalmazások elkülönítése és az ellenőrzött alkalmazásáruházak, e platformok továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Ma már egyre több alkalmazott használ mobileszközöket munkatevékenységekre, így bizalmas adatokhoz is hozzá kell férniük. Az eszközöknek védelemre van szükségük az egyre kifinomultabb támadásokkal szemben.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Az Intune Mobile Threat Defense-összekötők működése

Az összekötő úgy védi a vállalati erőforrásokat, hogy egy kommunikációs csatornát hoz létre az Intune és egy Ön által választott, mobilfenyegetések elleni védelmet nyújtó szállító között. Az Intune Mobile Threat Defense-partnerek olyan intuitív, egyszerűen üzembe helyezhető alkalmazásokat kínálnak a mobileszközökhöz, amelyek folyamatosan vizsgálják és elemzik a fenyegetéseket, majd az információt jelentés vagy végrehajtás céljából megosztják az Intune-nal. Ha például egy ilyen Mobile Threat Defense-alkalmazás azt jelzi a szállítónak, hogy a hálózat valamely telefonja egy közbeékelődéses támadásnak kitett hálózathoz csatlakozott, akkor ezt az információt megosztja, és megtörténik a kockázat besorolása is (alacsony, közepes vagy magas). Ez összevethető az Ön által az Intune-ban engedélyezett kockázati szintekkel, és eldönthető, hogy a hozzáférés bizonyos erőforrásokhoz fel legyen-e függesztve, amíg az eszköz a veszélynek kitett hálózathoz csatlakoztatva van.

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Ha a Mobile Threat Defense rendszer fertőzöttnek tekint egy eszközt:

![](http://i.imgur.com/kF8tI42.png)

Ha az eszközről elhárul a veszély, a hozzáférés újra engedélyezett:

![](http://i.imgur.com/zG4ZrzX.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partnerek

A vállalati erőforrásokhoz való hozzáférés védelme az eszköz-, a hálózati és az alkalmazáskockázat alapján:

- [A Lookout használatával](https://docs.microsoft.com/intune/deploy-use/lookout-mobile-threat-defense-connector)

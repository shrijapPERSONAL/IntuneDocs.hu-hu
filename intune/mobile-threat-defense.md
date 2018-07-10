---
title: Mobile Threat Defense a Microsoft Intune-nal
titleSuffix: ''
description: Az Intune Mobile Threat Defense (MTD) szolgáltatást a mobileszköz-védelmi partnerével együtt használva eszközkockázaton alapuló módon védheti meg a vállalati erőforrásokhoz való hozzáférést.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8c8fa146f01caae08f35ae824563ceb328c9d7f4
ms.sourcegitcommit: 7daa778b3a5adb41acfe23495cb63754afda1c58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123401"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Mit jelent a Mobile Threat Defense integrációja az Intune-nal?


Az Intune Mobile Threat Defense-összekötők segítségével saját megfelelőségi szabályzataihoz és feltételes hozzáférési szabályaihoz olyan információkat használhat fel, amelyek egy Ön által kiválasztott, mobilfenyegetések elleni védelmet biztosító szállítótól származnak. Ez lehetővé teszi, hogy a rendszergazda magán a veszélyeknek kitett mobileszközön egy újabb védelmi réteggel védje a vállalati erőforrásokat, például az Exchange-et vagy a SharePointot.

## <a name="what-problem-does-this-solve"></a>Milyen problémára nyújt ez megoldást?

A vállalatoknak meg kell védeniük érzékeny adataikat a folyamatosan keletkező különböző veszélyforrásoktól, így a fizikai, az alkalmazás- és a hálózati alapú fenyegetésektől, valamint az operációs rendszer biztonsági réseitől.

A vállalatok hagyományosan a számítógépeiket védik a rosszindulatú támadásoktól, miközben a mobileszközök figyelés és védelem nélkül maradnak. Noha a mobilplatformok operációs rendszerei rendelkeznek olyan beépített védelmi technikákkal, mint az alkalmazások elkülönítése és az ellenőrzött alkalmazásáruházak, e platformok továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Ma már egyre több alkalmazott használ mobileszközöket munkatevékenységekre, így bizalmas adatokhoz is hozzá kell férniük. Az eszközöknek védelemre van szükségük az egyre kifinomultabb támadásokkal szemben.

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Az Intune Mobile Threat Defense-összekötők működése

Az összekötő úgy védi a vállalati erőforrásokat, hogy egy kommunikációs csatornát hoz létre az Intune és egy Ön által választott, mobilfenyegetések elleni védelmet nyújtó szállító között. Az Intune Mobile Threat Defense-partnerek olyan intuitív, egyszerűen üzembe helyezhető alkalmazásokat kínálnak a mobileszközökhöz, amelyek folyamatosan vizsgálják és elemzik a fenyegetéseket, majd az információt jelentés vagy végrehajtás céljából megosztják az Intune-nal. 

Ha például egy ilyen Mobile Threat Defense-alkalmazás azt jelzi a szállítónak, hogy a hálózat valamely telefonja egy közbeékelődéses támadásnak kitett hálózathoz csatlakozott, akkor ezt az információt megosztja, és megtörténik a kockázat besorolása is (alacsony, közepes vagy magas). Ez összevethető az Ön által az Intune-ban engedélyezett kockázati szintekkel, és eldönthető, hogy a hozzáférés bizonyos erőforrásokhoz fel legyen-e függesztve, amíg az eszköz a veszélynek kitett hálózathoz csatlakoztatva van.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Milyen adatokat gyűjt az Intune a Mobile Threat Defense szolgáltatás számára?

Ha engedélyezte ezt a funkciót, az Intune mind a személyes, mind a vállalati tulajdonban lévő eszközökről alkalmazásleltár-adatokat gyűjt, amelyeket elérhetővé tesz a Mobile Threat Defense szolgáltatói, például a Lookout for Work számára. Az alkalmazásleltárt iOS operációs rendszerrel rendelkező felhasználóktól gyűjtheti be.

Ez a szolgáltatás nem kötelező, a leltáradatokat pedig nem osztjuk meg alapértelmezés szerint. Az alkalmazásleltár-adatok megosztása előtt egy Intune-rendszergazdának engedélyeznie kell a szolgáltatásbeállításokban az iOS-eszközök alkalmazásszinkronizációját.

**Alkalmazásleltár**  
Ha engedélyezi az iOS-eszközök alkalmazásszinkronizáicóját, az Intune mind a személyes, mind a vállalati tulajdonban lévő, iOS rendszerű eszközöktől alkalmazásleltár-adatokat küld az Ön MTD-szolgáltatójának. Az alkalmazásleltár adatai az alábbiakat tartalmazzák:

 - Alkalmazásazonosító
 - Alkalmazásverzió
 - Alkalmazás rövid verziója
 - Alkalmazásnév
 - Alkalmazás csomagjának mérete
 - Alkalmazás dinamikus mérete
 - Az alkalmazás ellenőrzött állapota
 - Az alkalmazás felügyelt állapota

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Ha a Mobile Threat Defense rendszer fertőzöttnek tekint egy eszközt:

![Kép: A Mobile Threat Defense által fertőzöttnek minősített eszköz](./media/MTD-image-1.png)

Ha az eszközről elhárul a veszély, a hozzáférés újra engedélyezett:

![Kép: A Mobile Threat Defense megadja a hozzáférést](./media/MTD-image-2.png)

> [!NOTE] 
> Az Intune nem támogatja egyszerre több Mobile Threat Defense-szolgáltató használatát. Egyszerre több MTD-eszköz engedélyezése minden MTD-alkalmazás telepítését váltja ki, és minden elérhető eszközön elvégzik a fenyegetések keresését.

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partnerek

A vállalati erőforrásokhoz való hozzáférés védelme az eszköz-, a hálózati és az alkalmazáskockázat alapján:

- [A Lookout használatával](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)

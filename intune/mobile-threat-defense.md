---
title: Mobile Threat Defense a Microsoft Intune-nal
titleSuffix: Microsoft Intune
description: Az Intune Mobile Threat Defense (MTD) szolgáltatást a mobileszköz-védelmi partnerével együtt használva eszközkockázaton alapuló módon védheti meg a vállalati erőforrásokhoz való hozzáférést.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e364ad88591b8ecc945702659255d9378723624f
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897245"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Mit jelent a Mobile Threat Defense integrációja az Intune-nal?
Intune Mobile Threat Defense külső szállítótól származó adatok integrálhatók a megfelelőségi szabályzatokról és a feltételes hozzáférési szabályok információforrásként. Ez az információ segítségével védheti a vállalati erőforrásokhoz, mint az Exchange és SharePoint-, blokkolja a hozzáférést a kitett mobileszközön.  

## <a name="what-problem-does-this-solve"></a>Milyen problémára nyújt ez megoldást?
Integrálás a Mobile Threat Defense külső szállítótól származó információk segíthetnek a vállalati erőforrások védelme a fenyegetésekkel szemben, amelyek befolyásolják a mobil platformokra.  

Általában vállalatok proaktív a számítógépeiket védik a biztonsági rések és támadásokkal szemben, miközben a mobileszközök gyakran nem figyelt és nem védett. Mobil platformokhoz beépített védelmi technikákkal, mint az alkalmazások elkülönítése és alkalmazásáruházak rendelkezik, ahol az ezeken a platformokon a rendszer továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Több alkalmazott használja az eszközök a munkahelyi és a bizalmas adatok eléréséhez, a Mobile Threat Defense szállítótól információ segíthet a eszközök és az erőforrások védelme az egyre kifinomultabb támadásokkal szemben.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Az Intune Mobile Threat Defense-összekötők működése

Intune-ban egy Mobile Threat Defense-összekötő használatával hozzon létre egy Intune-ban és a kiválasztott Mobile Threat Defense gyártója által biztosított közötti kommunikációs csatornát. Az Intune Mobile Threat Defense-partnerekkel intuitív, egyszerűen üzembe helyezhető alkalmazások mobileszközökre vonatkozó ajánlat. Ezek az alkalmazások aktívan vizsgálata és elemzése veszélyforrásokkal kapcsolatos megosztani az Intune-nal. Intune-ban használhatja az adatok a jelentés vagy végrehajtás céljából.  

Példa: Egy csatlakoztatott Mobile Threat Defense-alkalmazás jelentések, a Mobile Threat Defense szállítónak, hogy a hálózaton a telefon jelenleg kapcsolódik egy hálózatot, amely ki van téve a Man ki a középső támadások. Ez az információ kategorizálva egy megfelelő kockázati szint alacsony, közepes vagy magas. A kockázati szint majd összeveti a kockázati szint keretek beállította az Intune-ban. Ez az összehasonlítás alapján a hozzáférést bizonyos erőforrásokhoz, a választott visszavonhatja közben az eszköz biztonsága sérül.

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
- [Better Mobile](better-mobile-threat-defense-connector.md)
- A Sophos (a részleteket hamarosan elérhető)
- Wandera (a részleteket hamarosan elérhető)

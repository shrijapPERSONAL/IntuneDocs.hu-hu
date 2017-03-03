---
title: "Intune-os használati esetek azonosítása | Microsoft Docs"
description: "Ez a cikk segít az Intune használati esetek, valamint alesetek azonosításában a Microsoft Intune felhőalapú implementációja esetében."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: c834b0282b8f9b47566ab1da2125d993ba8febdf
ms.lasthandoff: 12/30/2016


---

# <a name="identify-intune-use-case-scenarios"></a>Intune-os használati esetek azonosítása

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A mobileszköz-felügyeleti használati esetek ismertetik a felhasználó típusát vagy szerepkörét és az eszköz tulajdonosát (például céges vagy személyes). A felhasználói használati esetek segítségével kezelhető csoportokba oszthatja a felhasználóit. A használati esetek azonosítása az Intune sikeres telepítése szempontjából fontos részét képezi a tervezési folyamatnak.

Ebben a témakörben néhány példán keresztül segítünk abban, hogy cége könnyedén azonosíthassa az Intune használati eseteit, a cégen belüli csoportokat, valamint az egyes használati esetekhez kapcsolódó mobileszköz-platformokat.

## <a name="use-case-scenarios"></a>Használati esetek

Első lépésként tekintse át a cégnél az Intune telepítésével elérni kívánt célokat, ezzel segítve a telepítés fő használati eseteinek azonosítását. Az Intune telepítési tervének hatókörén belül az alábbi kérdésekre kell válaszolnia:

-   Tervezi a céges tulajdonú eszközök támogatását?

-   Tervezi a magántulajdonban lévő eszközök (BYOD) támogatását?

### <a name="sub-use-case-scenarios"></a>Használati alesetek

A fő használati esetek azonosítását követően meg kell határoznia, hogy az egyes használati esetek tartalmazzanak-e aleseteket is. Például a cég megállapíthatja, hogy igény van egy vállalati használati eset támogatására, amely tartalmaz további aleseteket:

-   Infomunkás

-   Vezetők

-   Kioszkmód

Íme néhány példa a használati esetekre és alesetekre. Az alábbi táblázatot felhasználhatja a munkahelye használati eseteinek és aleseteinek meghatározásához:

| **Használati esetek** | **Használati alesetek** |
|:---:|:---:|
| Vállalat | Infomunkás |              
| Vállalat | Vezetők |           
| Vállalat | Kioszkmód |
| BYOD | Infomunkás |           
| BYOD | Vezetők |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>A használati esetekhez kapcsolódó munkahelyi csoportok azonosítása

Ezután azonosítania kell az egyes használati esetekhez és alesetekhez kapcsolódó munkahelyi csoportokat. Íme néhány példa használati esetekhez és alesetekhez kapcsolódó vállalati csoportokra, amelyet sablonként használhat munkahelye információinak megadásához:

| **Használati esetek** | **Használati alesetek** | **Munkahelyi csoportok** |
|:---:|:---:|:---:|
| Vállalat | Infomunkás | HR, pénzügy |               
| Vállalat | Vezető | HR, pénzügy |            
| Vállalat | Kioszkmód | Kereskedelem |
| BYOD | Infomunkás | Marketing, értékesítés |            
| BYOD | Vezető | Marketing, értékesítés |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Mobileszköz-platformok azonosítása a használati esetekhez

Itt azonosítania kell az egyes használati esetekhez kapcsolódó mobileszköz-platformokat. Például a vállalati használati eset támogathatja az iOS és az Android Samsung KNOX eszközplatformot, és a BYOD-szabályzat támogathat további mobileszköz-platformokat is, például az Androidot (nem Samsung KNOX) és a Windows 10 Mobile-t. Íme egy példa az egyes használati esetekhez kapcsolódó mobileszköz-platformokra. Az alábbi táblázatban megadhatja a munkahelye használati eseteihez kapcsolódó eszközplatformokat:

| **Használati esetek** | **Használati alesetek** | **Csoportok** | **Eszközplatformok** |   
|:---:|:---:|:---:|:---:|
| Vállalat | Infomunkás | HR, pénzügy | iOS |                                                           
| Vállalat | Vezetők | HR, pénzügy | iOS |                                                           
| Vállalat | Kioszkmód | Kereskedelem | Android |
| BYOD | Infomunkás | Marketing, értékesítés | iOS |                                                           
| BYOD | Vezetők | Marketing, értékesítés | iOS |

## <a name="next-section"></a>Következő szakasz

A következő szakaszban útmutatást talál arra, hogy [hogyan azonosíthatja az egyes használati esetek követelményeit](section-3-determine-use-case-requirements.md).


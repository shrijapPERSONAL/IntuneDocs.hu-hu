---
title: "Használatieset-forgatókönyvek kidolgozása"
description: "Ez a cikk segít az Intune használati esetek, valamint alesetek azonosításában a Microsoft Intune felhőalapú implementációja esetében."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Mobileszköz-kezelési használati esetek azonosítása

A használati esetek azonosítása az Intune sikeres telepítése szempontjából fontos részét képezi a tervezési folyamatnak. A használati esetek azért hasznosak, mert lehetővé teszik a felhasználók kezelhető csoportokba szegmentálását felhasználótípus vagy -szerepkör és a felhasználói eszköz tulajdonosa (például céges vagy személyi tulajdonú) alapján.

Ebben a témakörben néhány példán keresztül segítünk abban, hogy cége könnyedén azonosíthassa az Intune használati eseteit, a cégen belüli csoportokat, valamint az egyes használati esetekhez kapcsolódó mobileszköz-platformokat.

## <a name="device-ownership"></a>Az eszközök tulajdonjoga
Első lépésként tekintse át a cégnél az Intune telepítésével elérni kívánt célokat, így könnyebben azonosíthatja a telepítés fő használati eseteit. Az Intune telepítési tervének hatókörén belül válaszoljon az alábbi kérdésekre:

-   Tervezi a céges tulajdonú eszközök támogatását?

-   Tervezi a magántulajdonban lévő eszközök (BYOD) támogatását?

Ezek nem egymást kizáró lehetőségek. A cég céljainak eléréséhez lehet, hogy az eszköztulajdon mindkét formáját támogatnia kell. Az alárendelt használati esetek segítenek tisztázni, hol kell alkalmazni a különböző eszközkezelési szabályzatokat.

### <a name="user-type-or-device-role"></a>Felhasználó típusa vagy eszköz szerepköre

Határozza meg, hogy az egyes használati esetek tartalmaznak-e alárendelt használati eseteket is. Például a cég megállapíthatja, hogy igény van egy vállalati használati eset támogatására, amely tartalmaz további, felhasználói típuson vagy eszközszerepkörön alapuló, aleseteket, például:

-   Infomunkás

-   Vezető

-   Kioszkmód

Íme néhány példa a használati esetekre és alesetekre:

| **Használati esetek** | **Használati alesetek** |
|:---:|:---:|
| Vállalati | Infomunkás |              
| Vállalat | Vezetők |           
| Vállalat | Kioszkmód |
| BYOD | Infomunkás |           
| BYOD | Vezetők |

[Letöltheti a fenti táblázat sablonját](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), hogy beírja a cég használati eseteit és aleseteit.

## <a name="organizational-groups-for-your-scenarios"></a>Céges csoportok a használati eseteihez

Ezután azonosítania kell az egyes használati esetekhez és alesetekhez kapcsolódó munkahelyi csoportokat. Példa:

| **Használati esetek** | **Használati alesetek** | **Munkahelyi csoportok** |
|:---:|:---:|:---:|
| Vállalat | Infomunkás | HR, pénzügy |               
| Vállalat | Vezető | HR, pénzügy |            
| Vállalat | Kioszkmód | Kereskedelem |
| BYOD | Infomunkás | Marketing, értékesítés |            
| BYOD | Vezető | Marketing, értékesítés |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Mobileszköz-platformok a használat esetekhez

A következő lépés az egyes használati esetekhez kapcsolódó mobileszköz-platformok azonosítása. Egynél több is lehet.

A vállalati használati esetei támogathatják például az iOS és az Androidra fejlesztett Samsung KNOX eszközplatformokat. A saját eszközhasználati (BYOD) szabályzata tartalmazhat támogatást további mobileszköz-platformokhoz, például Androidhoz (nem Samsung KNOX) és Windows 10 Mobile-hoz. Az előző példákból kiindulva mobileszköz-platformokat társítottunk mindegyik használati esethez.

| **Használati esetek** | **Használati alesetek** | **Csoportok** | **Eszközplatformok** |   
|:---:|:---:|:---:|:---:|
| Vállalat | Infomunkás | HR, pénzügy | iOS |                                                           
| Vállalat | Vezetők | HR, pénzügy | iOS |                                                           
| Vállalat | Kioszkmód | Kereskedelem | Android |
| BYOD | Infomunkás | Marketing, értékesítés | iOS |                                                           
| BYOD | Vezetők | Marketing, értékesítés | iOS |

## <a name="next-steps"></a>További lépések

A következő szakaszban útmutatást talál arra, hogy [hogyan azonosíthatja az egyes használati esetek követelményeit](planning-guide-requirements.md).

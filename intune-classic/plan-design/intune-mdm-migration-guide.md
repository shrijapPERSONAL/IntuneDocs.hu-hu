---
title: "Útmutató az Intune mobileszköz-felügyeleti (MDM) szolgáltatásra történő migrációhoz | Microsoft Docs"
description: "Ez az útmutató végigvezeti az ügyfeleket a külső MDM-szolgáltatói megoldásról a Microsoft Intune-ra való migráció különféle részletein."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cce6d997c1aad73819b8cfcf31a1505f0ce75923
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="intune-migration-guide"></a>Intune migrációs útmutató

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Intune MDM-migrációs útmutató – grafika](../media/MDM-migration-guide-art.PNG)

Az Intune-ra való sikeres migráció kiindulópontja egy alapos, a jelenlegi MDM-környezetet, a vállalkozás céljait és a műszaki követelményeket is számításba vevő terv. Ezen kívül szükség lesz a főbb érintettek támogatására és együttműködésére is.

Ez az útmutató végigvezeti Önt a külső MDM-szolgáltatói megoldásról az Intune-ra való migráció különféle részletein.

## <a name="whats-included-in-this-guide"></a>Az útmutató tartalma

Az útmutató két fázist taglal. A bennük szereplő teendők, stratégiák és taktikai útmutatások segítségével végighaladhat az Intune MDM-re való migráció teljes folyamatán.

-   [1. fázis: Az Intune előkészítése mobileszköz-kezelésre] (/ intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Az MDM-migráció követelményeinek felmérése](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Alapszintű beállítás](/intune-classic/plan-design/migration-phase1-basic-setup)

    -   [Eszköz- és alkalmazásszabályzatok konfigurálása](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Alkalmazásvédelmi szabályzatok konfigurálása] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Speciális áttelepítési megfontolások](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

-   [2. fázis: áttelepítési kampány](/intune-classic/plan-design/migration-phase2-migration-campaign)

    -   [Kommunikációs terv](/intune-classic/plan-design/migration-phase2-communication-plan)

    -   [A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](/intune-classic/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [A szokásos migrációs ciklus](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)
        -   [A migráció figyelése](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Migráció utáni feladatok](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Előfeltételek

-   Ön már kiértékelte az Intune-t egy megvalósíthatósági tesztkörnyezetben, és úgy döntött, hogy MDM-megoldásként üzembe helyezi a munkahelyén.

-   Ön már ismeri az Intune-t és funkcióit. 

> [!NOTE]
> Az Intune-nal kapcsolatban az [Útmutató az Intune próbaverziójához](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune) című segédanyagban ismerkedhet meg részletesebben a migráció előtt.

## <a name="before-you-begin"></a>Előkészületek

Fontos észrevenni, hogy az új Intune-környezet eltérhet a korábban használt MDM-megoldástól. A hagyományos MDM-szolgáltatásokkal szemben az Intune az identitásalapú hozzáférés-vezérlésre helyezi a hangsúlyt, és ennélfogva hálózati proxykészülék nélkül is képes szabályozni a vállalati adatok mobileszközökről, a szervezeti hálózaton kívülről történő elérését. A Microsoft az együttesen Enterprise Client + Security éven ismert, szorosan integrált felhőszolgáltatásaira építi azokat a megoldásait, amelyek a felhőn belül biztosítják az adatkezelő szolgáltatásokat.

-   Tekintse át az [Intune gyakori használati módjait](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>További lépések

[1. fázis: Az Intune előkészítése mobileszköz-kezelésre] (/ intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)


---
title: "Útmutató az Intune mobileszköz-felügyeleti (MDM) szolgáltatásra történő migrációhoz | Microsoft Docs"
description: "Ez az útmutató végigvezeti az ügyfeleket a külső MDM-szolgáltatói megoldásról a Microsoft Intune-ra való migráció különféle részletein."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Intune migrációs útmutató

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Intune MDM-migrációs útmutató – grafika](../media/MDM-migration-guide-art.PNG)

Az Intune-ra való sikeres migráció kiindulópontja egy alapos, a jelenlegi MDM-környezetet, a vállalkozás céljait és a műszaki követelményeket is számításba vevő terv. Ezen kívül szükség lesz a főbb érintettek támogatására és együttműködésére is.

Ez az útmutató végigvezeti Önt a külső MDM-szolgáltatói megoldásról az Intune-ra való migráció különféle részletein.

## <a name="whats-included-in-this-guide"></a>Az útmutató tartalma

Az útmutató két fázist taglal. A bennük szereplő teendők, stratégiák és taktikai útmutatások segítségével végighaladhat az Intune MDM-re való migráció teljes folyamatán.

-   [1. fázis: az Intune előkészítése az MDM-hez](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Az MDM-migráció követelményeinek felmérése](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Alapszintű beállítás](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Eszköz- és alkalmazásszabályzatok konfigurálása](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Alkalmazásvédelmi szabályzatok konfigurálása (nem kötelező)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Speciális áttelepítési megfontolások](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [2. fázis: áttelepítési kampány](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [Kommunikációs terv](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [A szokásos migrációs ciklus](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [A migráció figyelése](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Migráció utáni feladatok](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Előfeltételek

-   Ön már kiértékelte az Intune-t egy megvalósíthatósági tesztkörnyezetben, és úgy döntött, hogy MDM-megoldásként üzembe helyezi a munkahelyén.

-   Ön már ismeri az Intune-t és funkcióit. 

> [!NOTE]
> Az Intune-nal kapcsolatban az [Útmutató az Intune próbaverziójához](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune) című segédanyagban ismerkedhet meg részletesebben a migráció előtt.

## <a name="before-you-begin"></a>Előkészületek

Fontos észrevenni, hogy az új Intune-környezet eltérhet a korábban használt MDM-megoldástól. A hagyományos MDM-szolgáltatásokkal szemben az Intune az identitásalapú hozzáférés-vezérlésre helyezi a hangsúlyt, és ennélfogva hálózati proxykészülék nélkül is képes szabályozni a vállalati adatok mobileszközökről, a szervezeti hálózaton kívülről történő elérését. A Microsoft az együttesen Enterprise Client + Security éven ismert, szorosan integrált felhőszolgáltatásaira építi azokat a megoldásait, amelyek a felhőn belül biztosítják az adatkezelő szolgáltatásokat.

-   Olvassa el [Az Intune használatának gyakori módjai](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) című cikket, és kezdjen el válaszokat összeállítani az [1. fázis: Az MDM-migráció követelményeinek felmérése](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements) című részben található kérdésekre.

## <a name="next-steps"></a>További lépések

[1. fázis: az Intune előkészítése a mobileszköz-felügyeletre (MDM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)


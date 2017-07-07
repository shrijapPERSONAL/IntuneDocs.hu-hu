---
title: "Útmutató az Intune mobileszköz-kezelési szolgáltatásra történő migráláshoz"
description: "Ez az útmutató végigvezeti az ügyfeleket a külső MDM-szolgáltatói megoldásról a Microsoft Intune-ra való migráció különféle részletein."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Intune migrációs útmutató

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Intune MDM-migrációs útmutató – grafika](./media/MDM-migration-guide-art.PNG)

Az Intune-ra való sikeres migráció kiindulópontja egy alapos, a jelenlegi mobileszköz-kezelési (MDM-) környezetet, a vállalkozás céljait és a műszaki követelményeket is számításba vevő terv. Ezen kívül szükség lesz a főbb érintettek támogatására és együttműködésére is.

Ez az útmutató végigvezeti Önt a külső MDM-szolgáltatói megoldásról az Intune-ra való migráció különféle részletein.

## <a name="whats-included-in-this-guide"></a>Az útmutató tartalma

Az útmutató két fázist taglal. A bennük szereplő teendők, stratégiák és taktikai útmutatások segítségével végighaladhat az Intune MDM-re való migráció teljes folyamatán.

-   [1. fázis: az Intune előkészítése a mobileszköz-kezelésre] (migration-guide-prepare.md)

    -   [Az MDM-migráció követelményeinek felmérése](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Alapszintű beállítás](migration-guide-setup.md)

    -   [Eszköz- és alkalmazásszabályzatok konfigurálása](migration-guide-configure-policies.md)

    -   [Alkalmazásvédelmi szabályzatok konfigurálása] (migration-guide-app-protection-policies.md)

    -   [Speciális áttelepítési megfontolások](migration-guide-considerations.md)

-   [2. fázis: áttelepítési kampány](migration-guide-campaign.md)

    -   [Kommunikációs terv](migration-guide-communication-plan.md)

    -   [A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](migration-guide-drive-adoption.md)
    
    -   [A szokásos migrációs ciklus](migration-guide-cycle.md)
        -   [A migráció figyelése](migration-guide-cycle.md#monitoring-migration)
        -   [Migráció utáni feladatok](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Előfeltételek

-   Ön már kiértékelte az Intune-t egy megvalósíthatósági tesztkörnyezetben, és úgy döntött, hogy MDM-megoldásként üzembe helyezi a munkahelyén.

-   Ön már ismeri az Intune-t és funkcióit. 

> [!NOTE]
> Az Intune-nal kapcsolatban az [Útmutató az Intune próbaverziójához](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune) című segédanyagban ismerkedhet meg részletesebben a migráció előtt.

## <a name="before-you-begin"></a>Előkészületek

Fontos észrevenni, hogy az új Intune-környezet eltérhet a korábban használt MDM-megoldástól. A hagyományos MDM-szolgáltatásokkal szemben az Intune az identitásalapú hozzáférés-vezérlésre helyezi a hangsúlyt, és ennélfogva hálózati proxykészülék nélkül is képes szabályozni a vállalati adatok mobileszközökről, a szervezeti hálózaton kívülről történő elérését. A Microsoft az együttesen Enterprise Client + Security éven ismert, szorosan integrált felhőszolgáltatásaira építi azokat a megoldásait, amelyek a felhőn belül biztosítják az adatkezelő szolgáltatásokat.

-   Tekintse át az [Intune gyakori használati módjait](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="next-steps"></a>További lépések

[1. fázis: az Intune előkészítése a mobileszköz-kezelésre] (migration-guide-prepare.md)

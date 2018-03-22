---
title: Útmutató az Intune mobileszköz-kezelési szolgáltatásra történő migráláshoz
titlesuffix: Microsoft Intune
description: Ez az útmutató végigvezeti a külső MDM-szolgáltatói megoldásról a Microsoft Intune-ra történő migrálás különböző lépésein.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 9bfefff2ef5960b6e52a8a37c2fd31466d16cbff
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="intune-migration-guide"></a>Intune migrációs útmutató

![Microsoft Intune MDM-migrációs útmutató – grafika](./media/MDM-migration-guide-art.PNG)

A Microsoft Intune-ba történő sikeres migráláshoz kell egy alapos terv, amely számításba veszi a jelenlegi mobileszköz-kezelési (MDM-) környezetét, az üzleti céljait és a műszaki követelményeket. Ezen kívül szükség lesz a főbb érintettek támogatására és együttműködésére is.

Ez az útmutató végigvezeti a külső MDM-szolgáltatói megoldásról az Intune-ra történő migrálás különböző lépésein.

## <a name="whats-included-in-this-guide"></a>Az útmutató tartalma

Ez az útmutató két fázisra osztja a migrálást, és mindkét fázisban felsorolja azon feladatokat, stratégiákat és taktikai útmutatásokat, amelyek végigvezetik az Intune MDM-re történő migrálás teljes folyamatán.

-   [1. fázis: Az Intune előkészítése a mobileszköz-felügyeletre](migration-guide-prepare.md)

    -   [Az MDM-migráció követelményeinek felmérése](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Alapszintű beállítás](migration-guide-setup.md)

    -   [Eszköz- és alkalmazásszabályzatok konfigurálása](migration-guide-configure-policies.md)

    -   [Alkalmazásvédelmi szabályzatok konfigurálása](migration-guide-app-protection-policies.md)

    -   [Speciális áttelepítési megfontolások](migration-guide-considerations.md)

-   [2. fázis: áttelepítési kampány](migration-guide-campaign.md)

    -   [Kommunikációs terv](migration-guide-communication-plan.md)

    -   [A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](migration-guide-drive-adoption.md)

    -   [A szokásos áttelepítési ciklus](migration-guide-cycle.md)
        -   [A migráció figyelése](migration-guide-cycle.md#monitoring-migration)
        -   [Migráció utáni feladatok](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Előfeltételek

-   Ön már kiértékelte az Intune-t egy megvalósíthatósági tesztkörnyezetben, és úgy döntött, hogy MDM-megoldásként üzembe helyezi a munkahelyén.

-   Ön már ismeri az Intune-t és funkcióit.

## <a name="before-you-begin"></a>Előkészületek

Fontos észrevenni, hogy az új Intune-környezet eltérhet a korábban használt MDM-megoldástól. A hagyományos MDM-szolgáltatásokkal szemben az Intune az identitásalapú hozzáférés-vezérlésre helyezi a hangsúlyt, és ennélfogva hálózati proxykészülék nélkül is képes szabályozni a vállalati adatok mobileszközökről, a szervezeti hálózaton kívülről történő elérését. A Microsoft az együttesen Enterprise Mobility + Security ajánlat néven ismert, szorosan integrált felhőszolgáltatásain keresztül kínál megoldásokat az adatkezelő szolgáltatások biztosításához a felhőben.

-   Tekintse át az [Intune gyakori használati módjait](common-scenarios.md).

## <a name="next-steps"></a>További lépések

[1. fázis: Az Intune előkészítése a mobileszköz-felügyeletre](migration-guide-prepare.md)

---
title: "Speciális migrációs megfontolások"
description: "Ez a cikk bemutatja az ügyfél különleges migrálási szempontjait a migrációs kampányok indítása előtt."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Speciális migrációs megfontolások

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

A meglévő MDM-szolgáltatói környezettől függően speciális migrációs megfontolások alkalmazandók.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>A gyári beállítások visszaállítása az Apple Készülékregisztrációs programjához (DEP)

Az Apple Készülékregisztrációs programja (DEP) által elvégzett beállításokat a végfelhasználó nem távolíthatja el az eszközről. A DEP speciális felügyeleti funkcióinak megőrzéséhez az eszközt a gyári beállítások visszaállítása útján újszerű állapotba kell visszaállítani az Intune-beli regisztráláshoz.

A DEP használatának folytatásához az eszközök Intune-beli felügyeletére lásd: [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>További lépések 

[2. fázis: áttelepítési kampány](migration-guide-campaign.md)

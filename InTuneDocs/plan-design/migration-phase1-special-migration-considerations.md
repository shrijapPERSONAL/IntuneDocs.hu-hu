---
title: "Speciális migrációs megfontolások |Microsoft Docs"
description: "Ez a cikk bemutatja az ügyfél különleges migrálási szempontjait a migrációs kampányok indítása előtt."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>1. fázis: Speciális migrációs megfontolások

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A meglévő MDM-szolgáltatói környezettől függően speciális migrációs megfontolások alkalmazandók.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>A gyári beállítások visszaállítása az Apple Készülékregisztrációs programjához (DEP)

Az Apple Készülékregisztrációs programja (DEP) által elvégzett beállításokat a végfelhasználó nem távolíthatja el az eszközről. A DEP speciális felügyeleti funkcióinak megőrzéséhez az eszközt a gyári beállítások visszaállítása útján újszerű állapotba kell visszaállítani az Intune-beli regisztráláshoz.

A DEP használatának folytatásához az eszközök Intune-beli felügyeletére:

1.  Vezesse be a [DEP-et az Intune-ban](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

2.  Lépjen Apple DEP-fiókjába és [rendelje hozzá a DEP-eszközök sorozatszámait](https://help.apple.com/deployment/business/#/tesf9562af26) az Intune-hoz a meglévő MDM-szolgáltatótó helyett.

3.  [Szinkronizálja](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) az Intune-nal DEP-fiókját

4.  [Hozza létre és rendelje hozzá](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) a megfelelő DEP regisztrációs profilokat a megfelelő sorozatszámokhoz az Intune-ban.

5.  Állítsa vissza az eszközök gyári beállításait (akár a jelenlegi MDM-szolgáltatón keresztül távolról, akár manuálisan minden egyes eszközön)

6.  Adja ki az eszközöket a végfelhasználóknak.

## <a name="next-steps"></a>További lépések 

[2. fázis: áttelepítési kampány](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)


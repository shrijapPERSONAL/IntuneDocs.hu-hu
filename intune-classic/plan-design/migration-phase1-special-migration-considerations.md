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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>1. fázis: Speciális migrációs megfontolások

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A meglévő MDM-szolgáltatói környezettől függően speciális migrációs megfontolások alkalmazandók.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>A gyári beállítások visszaállítása az Apple Készülékregisztrációs programjához (DEP)

Az Apple Készülékregisztrációs programja (DEP) által elvégzett beállításokat a végfelhasználó nem távolíthatja el az eszközről. A DEP speciális felügyeleti funkcióinak megőrzéséhez az eszközt a gyári beállítások visszaállítása útján újszerű állapotba kell visszaállítani az Intune-beli regisztráláshoz.

A DEP használatának folytatásához az eszközök Intune-beli felügyeletére:

1.  Vezesse be a [DEP-et az Intune-ban](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

2.  Lépjen Apple DEP-fiókjába és [rendelje hozzá a DEP-eszközök sorozatszámait](https://help.apple.com/deployment/business/#/tesf9562af26) az Intune-hoz a meglévő MDM-szolgáltatótó helyett.

3.  [Szinkronizálja](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) az Intune-nal DEP-fiókját

4.  [Hozza létre és rendelje hozzá](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) a megfelelő DEP regisztrációs profilokat a megfelelő sorozatszámokhoz az Intune-ban.

5.  Állítsa vissza az eszközök gyári beállításait (akár a jelenlegi MDM-szolgáltatón keresztül távolról, akár manuálisan minden egyes eszközön)

6.  Adja ki az eszközöket a végfelhasználóknak.

## <a name="next-steps"></a>További lépések 

[2. fázis: áttelepítési kampány](/intune-classic/plan-design/migration-phase2-migration-campaign)


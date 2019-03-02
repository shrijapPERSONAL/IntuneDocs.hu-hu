---
title: Speciális migrációs megfontolások
titlesuffix: Microsoft Intune
description: Ez a cikk a Microsoft Intune-beli migrációs kampány megkezdése előtt ellenőrizendő speciális migrációs szempontokat ismerteti.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea7c7b0d454b91389e51ed93a59768af8b280602
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237588"
---
# <a name="special-migration-considerations"></a>Speciális migrációs megfontolások

A meglévő MDM-szolgáltatói környezettől függően speciális migrációs megfontolások alkalmazandók.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Adattörlés az Apple készülékregisztrációs programjához (DEP)

Az Apple Készülékregisztrációs programja (DEP) által elvégzett beállításokat a végfelhasználó nem távolíthatja el az eszközről. A DEP speciális felügyeleti funkcióinak megőrzéséhez az eszközön adattörlést kell végrehajtani az újszerű állapotba történő visszaállításához az Intune-beli regisztráláshoz.

A DEP használatának folytatásához az eszközök Intune-beli felügyeletére lásd: [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>További lépések

[2. fázis: Áttelepítési kampány](migration-guide-campaign.md)

---
title: "Az eszközmegfelelőség figyelése"
titlesuffix: Microsoft Intune
description: "A cikk az eszközmegfelelőség figyelését ismerteti.”"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 708ed5a335d3475c213a536da9072afb1ad32ef9
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2018
---
# <a name="monitor-device-compliance-in-intune"></a>Az eszközmegfelelőség figyelése az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **megfelelőségi profilok** állapotának összegzését az **Áttekintés** panelen tekintheti meg.
A diagramokon keresztüli interaktív átkattintással feltárhatja a részleteket. Ha több megfelelőségi profil is konfigurálva van, a szabályzatállapotot a szabályzat panelen, a **Kezelés** > **Jelentések** területen érheti el.

##  <a name="device-compliance"></a>Eszközmegfelelőség

Az eszközmegfelelőségi jelentés összesített nézete az alábbi állapotok valamelyikét jelentő eszközök számára vonatkozó összesített adatokat listázza:

- **Megfelelő**: Az eszköz kiértékelése nemrég történt, és megfelel az Ön által meghatározott megfelelőségi profilnak.
- **Nem megfelelő**: Az eszköz kiértékelése megtörtént, és nem megfelelőként került meghatározásra.  Ha a profilban meg volt adva türelmi időszak, az lejárt, és az eszköz nem megfelelő állapotba került.
- **Türelmi időszak**: Az eszköz kiértékelése megtörtént, és nem megfelelőként került meghatározásra. A türelmi időszak azonban továbbra is érvényben marad, amíg az eszköz nem megfelelőként lesz megjelölve.

Az egyes eszközök és a felhasználók további adatainak megtekintéséhez megjelenítheti az egyes szakaszok részleteit.

## <a name="setting-compliance"></a>Beállítás-megfelelőség

A beállítás-megfelelőségi jelentés részletesen megjeleníti az egyes megfelelőségi beállítások adatait, például:

- A beállításnak nem megfelelő eszközök számát.
- A platformot, amelyre a beállítás vonatkozik.

Az egyes beállítások részletezésével további információkat jeleníthet meg azokról a profilokról, amelyeken engedélyezve vannak ezek a beállítások, illetve megtekintheti a beállítás értékét.

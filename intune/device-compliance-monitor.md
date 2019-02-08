---
title: Az eszközmegfelelőség figyelése
titlesuffix: Microsoft Intune
description: A cikk az eszközmegfelelőség figyelését ismerteti.”
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 534e8316e584259a818130ea9f83c88b44b67fee
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848083"
---
# <a name="monitor-device-compliance-in-intune"></a>Az eszközmegfelelőség figyelése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A **megfelelőségi profilok** állapotának összegzését az **Áttekintés** panelen tekintheti meg.
A diagramokon keresztüli interaktív átkattintással feltárhatja a részleteket. Ha több megfelelőségi profil is konfigurálva van, a szabályzatállapotot a szabályzat panelen, a **Kezelés** > **Jelentések** területen érheti el.

##  <a name="device-compliance"></a>Eszközmegfelelőség

Az eszközmegfelelőségi jelentés összesített nézete az alábbi állapotok valamelyikét jelentő eszközök számára vonatkozó összesített adatokat listázza:

- **Megfelelő**: Az eszköz kiértékelése nemrég történt, és megfelel a megadott megfelelőségiprofil-beállításoknak.
- **Nem megfelelő**: Az eszköz kiértékelése megtörtént, és nem megfelelőnek minősül.  Ha a profilban meg volt adva türelmi időszak, az lejárt, és az eszköz nem megfelelő állapotba került.
- **Türelmi időszak**: Eszköz kiértékelése megtörtént, és nem megfelelőnek minősül. A türelmi időszak azonban továbbra is érvényben marad, amíg az eszköz nem megfelelőként lesz megjelölve.

Az egyes eszközök és a felhasználók további adatainak megtekintéséhez megjelenítheti az egyes szakaszok részleteit.

## <a name="setting-compliance"></a>Beállítás-megfelelőség

A beállítás-megfelelőségi jelentés részletesen megjeleníti az egyes megfelelőségi beállítások adatait, például:

- A beállításnak nem megfelelő eszközök számát.
- A platformot, amelyre a beállítás vonatkozik.

Az egyes beállítások részletezésével további információkat jeleníthet meg azokról a profilokról, amelyeken engedélyezve vannak ezek a beállítások, illetve megtekintheti a beállítás értékét.

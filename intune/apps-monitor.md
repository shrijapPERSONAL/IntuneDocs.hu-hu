---
title: "Alkalmazásadatok és -hozzárendelések monitorozása"
titleSuffix: Intune on Azure
description: "Miután társított egy alkalmazást a felhasználókhoz vagy eszközökhöz, ezekkel az információkkal monitorozhatja az alkalmazás állapotát."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d588ecc8f2e211b5a8ccdfe7b7720869cc6327b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune több módot is kínál a felügyelt alkalmazások jellemzőinek, valamint hozzárendelési állapotának figyelésére.

1. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
2. Az alkalmazáslista paneljén válassza ki azt az alkalmazást, melynek adatait meg szeretné tekinteni. Ekkor megjelenik az <*alkalmazásnév*> **eszköz telepítési állapota** panel: ![Alkalmazás telepítésének állapota panel.](./media/monitor-apps.png)

Ezután a következő lépések egyikével tudhat meg többet az alkalmazásokról és azok hozzárendeléseiről.

## <a name="general"></a>Általános

- **Áttekintés** – Alapvető áttekintést nyújt az alkalmazásról és a hozzá tartozó esetleges hozzárendelések állapotáról. A diagramok egyikének kiválasztásával megnyithatja az **Eszköz telepítési állapota** vagy a **Felhasználó telepítési állapota** panelt, melyeken részletesebb információkat találhat.

## <a name="manage"></a>A számítógépeken futó

- **Tulajdonságok** – Megjelenítheti és módosíthatja a kijelölt alkalmazáshoz tartozó információkat. Az alkalmazások tulajdonságairól az [Alkalmazás hozzáadása a Microsoft Intune-hoz](apps-add.md) című témakörben találhat további információt.
- **Hozzárendelések** – Az alkalmazás hozzárendeléseiről nyújt információt. További információ: [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal).

## <a name="monitor"></a>Figyelő

- **Eszköz telepítési állapota** – Részletes információt biztosít minden egyes eszközről, amelyhez hozzárendelte a kiválasztott alkalmazást, beleértve az eszköz nevét, operációs rendszerét, az utolsó Intune-ba való bejelentkezés időpontját és az alkalmazás telepítésének állapotát.
- **Felhasználó telepítési állapota** – Részletes információt biztosít minden felhasználóról, amelyhez hozzárendelte a kiválasztott alkalmazást, beleértve az alkalmazás a felhasználó eszközein lévő telepítéseinek számát és az esetleges telepítési hibák adatait.
---
title: "Alkalmazásadatok és -hozzárendelések figyelése | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Miután már társított alkalmazást a felhasználókhoz vagy eszközökhöz, ezen információ segítségével figyelheti annak állapotát."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7c39c904cd2a7bd20525d9072067c6e484b4437a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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

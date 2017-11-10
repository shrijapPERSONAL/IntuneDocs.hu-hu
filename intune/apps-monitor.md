---
title: "Alkalmazásadatok és -hozzárendelések monitorozása"
titlesuffix: Azure portal
description: "Miután társított egy alkalmazást a felhasználókhoz vagy eszközökhöz, ezekkel az információkkal monitorozhatja az alkalmazás állapotát."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune több módot is kínál a felügyelt alkalmazások jellemzőinek, valamint hozzárendelési állapotának figyelésére.

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. A **Mobilalkalmazások** területen válassza az **Alkalmazások** elemet a **Felügyelet** csoportban.
     
    ![Alkalmazástelepítés állapota panel.](./media/monitor-apps.png)
5. Az alkalmazáslista panelen válasszon egy alkalmazást. Ekkor megjelenik az <*alkalmazásnév*> **Eszköz telepítési állapota** panel.

Az eszköz telepítési állapotjelentése az alábbi oszlopokat tartalmazza:

1.  **Eszköz neve** Az eszköztípus neve.
2.  **Felhasználónév** A felhasználónév.
3.   **Platform** Az eszközön telepített operációs rendszer.
4.  **Verzió** Az alkalmazás verziószáma.
5.   **Állapot** Az alkalmazások lehetséges állapotai: **Telepítve**, **Nincs telepítve**, **Telepítés folyamatban** és **Hiba**.
6. **Állapot részletei** Az eszközön található alkalmazás állapotának olvasható leírása.
7. **Utolsó bejelentkezés** Az eszköz legutóbbi bejelentkezése az Intune-ba.

Ezután a következő lépések egyikével tudhat meg többet az alkalmazásokról és azok hozzárendeléseiről.

## <a name="general"></a>Általános

- **Áttekintés** – Alapvető áttekintést nyújt az alkalmazásról és a hozzá tartozó esetleges hozzárendelések állapotáról. A diagramok egyikének kiválasztásával megnyithatja az **Eszköz telepítési állapota** vagy a **Felhasználó telepítési állapota** panelt, melyeken részletesebb információkat találhat.

## <a name="manage"></a>A számítógépeken futó

- **Tulajdonságok** – Megjelenítheti és módosíthatja a kijelölt alkalmazáshoz tartozó információkat. Az alkalmazások tulajdonságairól az [Alkalmazás hozzáadása a Microsoft Intune-hoz](apps-add.md) című témakörben találhat további információt.
- **Hozzárendelések** – Az alkalmazás hozzárendeléseiről nyújt információt. További információ: [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal).

## <a name="monitor"></a>Figyelő

- **Eszköz telepítési állapota** – Részletes információt biztosít minden egyes eszközről, amelyhez hozzárendelte a kiválasztott alkalmazást, beleértve az eszköz nevét, operációs rendszerét, az utolsó Intune-ba való bejelentkezés időpontját és az alkalmazás telepítésének állapotát.
- **Felhasználó telepítési állapota** – Részletes információt biztosít minden felhasználóról, akikhez hozzárendelte a kiválasztott alkalmazást, beleértve az alkalmazás a felhasználó eszközein lévő telepítéseinek számát és az esetleges telepítési hibák adatait.
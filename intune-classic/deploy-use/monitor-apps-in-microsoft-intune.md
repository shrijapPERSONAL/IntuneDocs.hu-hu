---
title: "Az alkalmazások telepítésének figyelése| Microsoft Docs"
description: "Tudja meg, hogyan figyelhetők meg az Intune segítségével telepített alkalmazások."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 808268faa797d8576f5fb693d9940d97d17abf21
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---


# <a name="monitor-app-deployments-in-microsoft-intune"></a>Az alkalmazások telepítésének figyelése a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="monitor-an-app-deployment"></a>Alkalmazástelepítés figyelése
Az Intune felügyeleti konzolján láthatja a felügyelt alkalmazásokat, illetve a telepítések állapotát. <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <a name="to-view-apps-that-you-manage-and-their-status"></a>A felügyelt alkalmazások és azok állapotának megtekintése
Az **Alkalmazások** munkaterületen válassza ki az **Alkalmazások** csomópontot, majd válassza az **Alkalmazások** elemet.

Megjelenik a felügyelt alkalmazások listája. A kívánt alkalmazást kiválasztva megtekintheti annak telepítési állapotát a konzol alsó ablaktáblájában. Az állapotadatok kiválasztásával további információkat jeleníthet meg. Ha például az **1 felhasználó rendelkezik ezzel a szoftverrel** állapotüzenet látható, válassza ki az üzenetet a felhasználó nevének megtekintéséhez.

> [!TIP]
> A **Szűrők** legördülő lista lehetővé teszi, hogy csak azokat az alkalmazásokat jelenítse meg, amelyek megfelelnek az Ön által megadott feltételeknek, például csak a sikertelenül telepített alkalmazásokat vagy csak a sikeresen telepített alkalmazásokat.
>
> ![Alkalmazásszűrők – példa](./media/app-filters.png)

Emellett az **Irányítópult** munkaterületen is áttekintheti az alkalmazások állapotát. Az áttekintésre kattintva megjelenítheti az alkalmazások listáját.

## <a name="to-view-more-detailed-information-about-an-app"></a>Részletes információk megjelenítése az alkalmazásról
Az alkalmazások listájában jelölje ki a kívánt alkalmazást, majd válassza a **Tulajdonságok megjelenítése** elemet.

Válassza ki valamelyik lapfület az alkalmazás **Szoftver tulajdonságai** lapján: **Általános** – Általános információk az alkalmazásról és a telepítési állapotáról, **Eszközök** – Az alkalmazás célzott telepítését sikeresen telepítő eszközök, **Felhasználók** – Az alkalmazás célzott telepítését sikeresen telepítő felhasználók.

A korábbiakhoz hasonlóan, a **Szűrők** legördülő listával konfigurálhatja az egyes lapokon megjelenő értékeket.


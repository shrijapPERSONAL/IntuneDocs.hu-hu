---
title: "Intune-eszközleltár megtekintése"
titleSuffix: Intune on Azure
description: "A cikkből elsajátíthatja az Intune-nal felügyelt eszközök megjelenítését, illetve hardverük és a rájuk telepített alkalmazások megismerését.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dae92c117bcf8a4a8ff133ed613f9f77ea0c07c2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Az Intune-eszközleltár megtekintése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszközök** tevékenységprofil lehetővé teszi az eszközök kezelését, beleértve a betekintést hardveres képességeikbe és a rajtuk telepített alkalmazásokba. 

Az eszközleltár megtekintéséhez:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.

Most válasszon egyet az alábbi lehetőségek közül:

- **Áttekintés** – Tájékoztatást nyújt a regisztrált eszközökről és az egyes eszközökön futó operációs rendszerekről.
- **Kezelés** – A **Minden eszköz** lehetőséget választva megjelenítheti az összes kezelt eszköz listáját.
    Ha kijelöl egy eszközt a listán, megnyílik az <*eszköznév*> **Áttekintés** panel, amelyen az alábbiak közül választhat:
    - **Áttekintés** – Általános információk az eszközről, mint például a neve, a tulajdonosa, hogy BYOD-eszköz-e, és hogy mikor jelentkezett be.
    ![Az eszköz áttekintése](./media/device-overview.png)
    - **Hardver** – Részletes információk az eszközről, mint például a rendelkezésre álló szabad tárhely, a modell és a gyártó neve.
    ![Felügyelt eszköz hardverleltára](./media/hardware-inventory.png)
    - **Észlelt alkalmazások** – Felsorolja azon telepített alkalmazásokat, amelyet az Intune talált az eszközön.
    ![Észlelt alkalmazások csomópont](./media/detected-applications.png)
    - **Eszközmegfelelőség** – Megjeleníti az eszközhöz rendelt összes megfelelőségi szabályzat megfelelőségi állapotát.
    - **Az eszköz konfigurációja** – Megjeleníti az eszközhöz rendelt összes eszközkonfigurációs szabályzat megfelelőségi állapotát.
- **Figyelés** Az **Eszközműveletek** lehetőséget választva megjeleníthetők az adott eszközön végrehajtott műveletek és jelenlegi állapotuk.
- **Telepítő** > **TeamViewer-összekötő** – Segítségével távoli felügyeletet konfigurálhat TeamViewer-szoftvert használó eszközökön. Részletesebb információk: [Távsegítség nyújtása az Intune által felügyelt Android-eszközökhöz](/intune/device-profile-android-teamviewer).



---
title: "Intune-eszközleltár megtekintése"
titlesuffix: Azure portal
description: "A cikkből elsajátíthatja az Intune-nal felügyelt eszközök megjelenítését, illetve hardverük és a rájuk telepített alkalmazások megismerését.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45ef07d68248ab4c0c6f3a3e6e8da83cb210c5c7
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
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

>[!NOTE]
> Az Intune csak a vállalat tulajdonában lévő eszközökön található alkalmazásokról készít leltárt. A magántulajdonú eszközökön futó alkalmazásokat nem veszi bele a leltárba. A vállalat tulajdonában lévő Windows 10 rendszerű számítógépekről csak a modern alkalmazásokat veszi figyelembe a leltár készítésekor. A Win32-es alkalmazásokról az Intune nem gyűjt információkat.
> Attól függően, hogy mely szolgáltatót használja az eszközökön, előfordulhat, hogy a rendszer nem gyűjt be minden leltárelemet.

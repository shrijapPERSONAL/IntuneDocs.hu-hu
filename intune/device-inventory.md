---
title: Az eszközök megtekintése a Microsoft Intune-nal – Azure | Microsoft Docs
description: Megtekintheti az eszközei adatait, például az operációs rendszereket, a tárhelyet, a gyártót és a modelladatokat. Az Azure-beli Microsoft Intune-nal lekérheti a telepített alkalmazások listáját, ellenőrizheti a megfelelőségi szabályzatokat, és beállíthatja a TeamViewert. Ez hasonlít a kezelt eszközök leltárának áttekintéséhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaaf3e9807a8eab66c24f4d1bb3c3c5ea9f4cfe0
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="see-device-details-in-intune"></a>Eszközadatok megtekintése az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszközök** funkció további részletekkel szolgál a kezelt eszközökkel kapcsolatban, például hardveradatokkal és a telepített alkalmazások listájával. 

Ez a cikk bemutatja, hogyan tekintheti meg az összes eszközét és azok tulajdonságait az Azure Portalon.

## <a name="view-your-device-details"></a>Eszközadatok megtekintése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** lehetőséget. Az Eszközök területen több lehetősége van:

   - **Áttekintés**: Tájékoztatást nyújt a regisztrált eszközökről és az egyes eszközökön futó operációs rendszerekről.
   - **Kezelés**: A **Minden eszköz** vagy az **Azure AD-eszközök** lehetőséget választva megjelenítheti az összes kezelt eszköz listáját.
    Válassza ki a listáról az egyik eszközt. Ekkor megnyílik az <*eszköznév*> **áttekintése**, ahol kiválaszthatja a következőket:
     - **Áttekintés**: Az eszköz neve, tulajdonosa, BYOD-típusa, bejelentkezési időpontja és egyéb adatok megjelenítése.
     - **Hardver**: A rendelkezésre álló szabad tárhely, a modell és a gyártó neve és egyéb részletek.
     - **Észlelt alkalmazások**: Felsorolja azon telepített alkalmazásokat, amelyet az Intune talált az eszközön.
     - **Eszközmegfelelőség**: Megjeleníti az eszközhöz rendelt összes megfelelőségi szabályzat állapotát.
     - **Az eszköz konfigurációja**: Megjeleníti az eszközhöz rendelt összes eszközkonfigurációs szabályzat megfelelőségi állapotát.
   - **Figyelés**: Az **Eszközműveletek** lehetőséget választva megjeleníthetők a kezelt eszközökön végrehajtott műveletek és jelenlegi állapotuk. A **naplók** a különböző feladatok állapotát jelenítik meg.
   - **Telepítő** > **TeamViewer-összekötő**: Távoli felügyeletet konfigurálhat az eszközökön a TeamViewer-szoftverrel. Részletesebb információk: [Távsegítség nyújtása az Intune által felügyelt Android-eszközökhöz](device-profile-android-teamviewer.md).

Az Intune csak a vállalat tulajdonában lévő eszközökön található alkalmazásokról készít listát. A személyes eszközökön található alkalmazásokat nem ellenőrzi. A vállalat tulajdonában lévő Windows 10 rendszerű számítógépekről csak a modern alkalmazásokat veszi figyelembe a lista készítésekor. A Win32-es alkalmazásokról az Intune nem gyűjt információkat. Az eszközök szolgáltatójától függően előfordulhat, hogy nem minden alkalmazásról talál információt.

## <a name="next-steps"></a>További lépések
Ismerje meg az Intune-beli [eszközkezelés](device-management.md) további funkcióit.

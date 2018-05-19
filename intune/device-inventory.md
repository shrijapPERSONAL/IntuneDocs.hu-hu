---
title: Eszköz részletes adatainak megtekintése az Azure-beli Microsoft Intune-nal | Microsoft Docs
description: Megtekintheti az eszközei adatait, például az operációs rendszereket, a tárhelyet, a gyártót és a modelladatokat. Az Azure-beli Microsoft Intune-nal lekérheti a telepített alkalmazások listáját, ellenőrizheti a megfelelőségi szabályzatokat, és beállíthatja a TeamViewert. Ez hasonlít a kezelt eszközök leltárának áttekintéséhez.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2018
---
# <a name="see-device-details-in-intune"></a>Eszközadatok megtekintése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Eszközök** funkció további részletekkel szolgál a kezelt eszközökkel kapcsolatban, például hardveradatokkal és a telepített alkalmazások listájával.

Ez a cikk bemutatja, hogyan tekintheti meg az összes eszközét és azok tulajdonságait az Azure Portalon.

## <a name="view-the-device-details"></a>Eszköz részletes adatainak megtekintése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget, majd jelölje ki a listában szereplő eszközök egyikét, hogy megnyissa annak részletes adatait:

   - Az **Áttekintés** az eszköz nevét és néhány lényeges tulajdonságát tartalmazza, köztük sok más mellett azt is, hogy saját eszköz-e (BYOD), és mikor jelentkezett be. A továbbiakhoz válassza a **További részletek** lehetőséget:
     - Céges adatok eltávolítása
     - Eszköz törlése
     - Az eszköz távoli zárolása
     - Törlés
     - Távsegítség-munkamenet indítása
   - [Saját létrehozású eszközkategória](device-group-mapping.md) hozzárendelésére és az eszköz tulajdonosának (saját eszköz vagy vállalati eszköz) átállítására használja a **Tulajdonságok** lehetőséget.
   - A **Hardver** sok részletet tartalmaz az eszközről, köztük sok más mellett az eszköz azonosítóját, operációs rendszerét és annak verzióját, a tárhelyet, a modellt és a gyártót és a feltételes hozzáférés beállításait.
   - Az **Észlelt alkalmazások** verziójukkal együtt sorolja fel azon telepített alkalmazásokat, amelyet az Intune talált az eszközön. Az alkalmazások listáját **Exportálni** is tudja egy .csv-fájlba.
   - Az **Eszközmegfelelőség** a hozzárendelt megfelelőségi szabályzatok listája mellett azt is tartalmazza, hogy az eszköz megfelelő vagy nem.
   - Az **Eszközkonfiguráció** az eszközhöz rendelt összes eszközkonfigurációs szabályzat listáját mutatja meg, és hogy a szabályzat alkalmazása sikeres vagy sikertelen.

Az Intune csak a vállalat tulajdonában lévő eszközökön található alkalmazásokról készít listát. A személyes eszközökön található alkalmazásokat nem ellenőrzi. A vállalat tulajdonában lévő Windows 10 rendszerű számítógépekről csak a modern alkalmazásokat veszi figyelembe a lista készítésekor. A Win32-es alkalmazásokról az Intune nem gyűjt információkat. Az eszközök szolgáltatójától függően előfordulhat, hogy nem minden alkalmazásról talál információt.

|Platform|Személyes tulajdonú eszközök esetében|Vállalati tulajdonú eszközök esetében|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (a Configuration Manager-ügyfél nélkül)|Csak felügyelt alkalmazások|Csak felügyelt alkalmazások|
|Windows 8.1 (a Configuration Manager-ügyfél nélkül)|Csak felügyelt alkalmazások|Csak felügyelt alkalmazások|  
|Windows Phone 8|Csak felügyelt alkalmazások|Csak felügyelt alkalmazások|  
|Windows RT|Csak felügyelt alkalmazások|Csak felügyelt alkalmazások|  
|iOS|Csak felügyelt alkalmazások|Az összes, az eszközön telepített alkalmazás|
|macOS|Az összes, az eszközön telepített alkalmazás|Az összes, az eszközön telepített alkalmazás|  
|Android|Csak felügyelt alkalmazások|Az összes, az eszközön telepített alkalmazás|  

## <a name="next-steps"></a>További lépések
Ismerje meg az Intune-beli [eszközkezelés](device-management.md) további funkcióit.
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
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ad3593dfab0326cec4003b794d50d415cf3c536
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55844122"
---
# <a name="see-device-details-in-intune"></a>Eszközadatok megtekintése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Eszközök** funkció további részletekkel szolgál a kezelt eszközökkel kapcsolatban, például hardveradatokkal és a telepített alkalmazások listájával.

Ez a cikk bemutatja, hogyan tekintheti meg az összes eszközét és azok tulajdonságait az Azure Portalon.

## <a name="view-the-device-details"></a>Eszköz részletes adatainak megtekintése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget, majd jelölje ki a listában szereplő eszközök egyikét, hogy megnyissa annak részletes adatait:

   - Az **Áttekintés** az eszköz nevét és néhány lényeges tulajdonságát tartalmazza, köztük sok más mellett azt is, hogy saját eszköz-e (BYOD), és mikor jelentkezett be. Az eszközön a következő műveleteket hajthatja végre:
      - [Kivonás](devices-wipe.md#retire)
        - [Törlés](devices-wipe.md#wipe)
        - [Távoli zárolás](device-remote-lock.md)
        - [Eszköz szinkronizálása](device-sync.md)
        - [Új PIN-kód](device-passcode-reset.md)
        - [Újraindítás](device-restart.md) (kizárólag Windowson)
        - [Újrakezdés](device-fresh-start.md) (kizárólag Windowson)
     - Távsegítség-munkamenet indítása
   - [Saját létrehozású eszközkategória](device-group-mapping.md) hozzárendelésére és az eszköz tulajdonosának (saját eszköz vagy vállalati eszköz) átállítására használja a **Tulajdonságok** lehetőséget.
   - A **Hardver** sok részletet tartalmaz az eszközről, köztük sok más mellett az eszköz azonosítóját, operációs rendszerét és annak verzióját, a tárhelyet, a modellt és a gyártót és a feltételes hozzáférés beállításait.
   - Az **Észlelt alkalmazások** verziójukkal együtt sorolja fel azon telepített alkalmazásokat, amelyet az Intune talált az eszközön. Az alkalmazások listáját **Exportálni** is tudja egy .csv-fájlba. Ez a lista 7 naponta frissül.
   - Az **Eszközmegfelelőség** a hozzárendelt megfelelőségi szabályzatok listája mellett azt is tartalmazza, hogy az eszköz megfelelő vagy nem.
   - Az **Eszközkonfiguráció** az eszközhöz rendelt összes eszközkonfigurációs szabályzat listáját mutatja meg, és hogy a szabályzat alkalmazása sikeres vagy sikertelen.

Az Intune csak a vállalat tulajdonában lévő eszközökön található alkalmazásokról készít listát. A személyes eszközökön található alkalmazásokat nem ellenőrzi. A vállalat tulajdonában lévő Windows 10 rendszerű számítógépekről csak a modern alkalmazásokat veszi figyelembe a lista készítésekor. A Win32-es alkalmazásokról az Intune nem gyűjt információkat. Az eszközök szolgáltatójától függően előfordulhat, hogy nem minden alkalmazásról talál információt.

|Platform|Személyes tulajdonú eszközök esetében|A vállalat által birtokolt eszközök|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (a Configuration Manager-ügyfél nélkül)|Csak a felügyelt alkalmazások|Csak a felügyelt alkalmazások|
|Windows 8.1 (a Configuration Manager-ügyfél nélkül)|Csak a felügyelt alkalmazások|Csak a felügyelt alkalmazások|  
|Windows Phone 8|Csak a felügyelt alkalmazások|Csak a felügyelt alkalmazások|  
|Windows RT|Csak a felügyelt alkalmazások|Csak a felügyelt alkalmazások|  
|iOS|Csak a felügyelt alkalmazások|Az eszközön telepített összes alkalmazás|
|macOS|Az eszközön telepített összes alkalmazás|Az eszközön telepített összes alkalmazás|  
|Android|Csak a felügyelt alkalmazások|Az eszközön telepített összes alkalmazás|  
|Vállalati Android|Csak a felügyelt alkalmazások|Csak a munkahelyi profilban található telepített alkalmazások|  

## <a name="hardware-device-details"></a>Hardvereszköz részletes adatai
Az eszközök által használt szolgáltatótól, függően nem minden adata gyűjthető

|Részletek|Leírás|Platform| 
|--------------|----------------------|----|  
|Name (Név)|Az eszköz neve.|Windows, iOS|
|Felügyeleti név|A csak a konzolon használt eszköznév. Ennek a névnek a módosítása nem változtatja meg a nevet az eszközön.|Windows, iOS|
|UDID|Az eszköz egyedi eszközazonosítója.|Windows, iOS|
|Intune-eszközazonosító|Az eszközt egyedileg azonosító GUID.|Windows, iOS|
|Sorozatszám|Az eszköz gyártótól származó sorozatszáma.|Windows, iOS|
|Megosztott eszköz|Ha **Igen**, akkor az eszköz több felhasználó között van megosztva.|Windows, iOS|
|Felhasználó által jóváhagyott regisztráció|Ha **Igen**, akkor az eszközön felhasználó által jóváhagyott regisztráció van érvényben. Ezáltal a rendszergazdák felügyelni tudják az eszköz bizonyos biztonsági beállításait.|Windows, iOS|
|Operációs rendszer|Az eszközön futó operációs rendszer.|Windows, iOS|
|Operációs rendszer verziója|Az eszközön futó operációs rendszer verziója.|Windows, iOS|
|Operációs rendszer nyelve|Az eszközön futó operációs rendszerhez beállított nyelv.|Windows, iOS|
|Teljes tárterület|Az eszközön lévő teljes tárterület (gigabájtban).|Windows, iOS|
|Szabad tárterület|Az eszközön lévő felhasználatlan tárterület (gigabájtban).|Windows, iOS|
|IMEI|Az eszköz Nemzetközi mobilkészülék-azonosító (IMEI) száma.|Windows, iOS, Android|
|MEID|Az eszköz mobilkészülék-azonosító száma.|Windows, iOS, Android|
|Gyártó|Az eszköz gyártója.|Windows, iOS, Android|
|Modell|Az eszköz típusa.|Windows, iOS, Android|
|Telefonszám|Az eszközhöz rendelt telefonszám.|Windows, iOS, Android|
|Előfizetés-szolgáltató|Az eszköz vezeték nélküli szolgáltatója.|Windows, iOS, Android|
|Mobiltechnológia|Az eszköz által használt rádiórendszer.|Windows, iOS, Android|
|Wi-Fi MAC|Az eszköz MAC-címe.|Windows, iOS, Android|
|ICCID|Az integrált áramköri kártya (ICC) azonosítója, amely a SIM-kártya egyedi azonosítószáma.|Windows, iOS, Android|
|Regisztrálás dátuma|Az eszköz Intune-ban történt regisztrálásának dátuma és időpontja.|Windows, iOS, Android|
|Utolsó kapcsolat|Az eszköz Intune-hoz való utolsó kapcsolódásának dátuma és időpontja.|Windows, iOS, Android|
|Kód az aktiválási zár megkerüléséhez|Az aktiválási zár megkerüléséhez használható kód.|Windows, iOS, Android|
|Az Azure AD-ban regisztrálva|Ha **Igen**, akkor az eszköz regisztrálva van az Azure Active Directoryban.|Windows, iOS, Android|
|Megfelelőség|Az eszköz megfelelőségi állapota.|Windows, iOS, Android|
|EAS aktiválva|Ha **Igen**, akkor az eszköz szinkronizálva van egy Exchange-postafiókkal.|Windows, iOS, Android|
|EAS-aktiválási azonosító|Az eszköz Exchange ActiveSync-azonosítója.|Windows, iOS, Android|
|Felügyelt|Ha **Igen**, akkor a rendszergazdák fokozott felügyelettel rendelkeznek az eszköz felett.|Windows, iOS, Android|
|Titkosítva|Ha **Igen**, akkor az eszközön tárolt adatok titkosítva vannak.|Windows, iOS, Android|



## <a name="next-steps"></a>További lépések
Ismerje meg az Intune-beli [eszközkezelés](device-management.md) további funkcióit.

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
ms.openlocfilehash: a658182800f480f27097e078f28adc95c35aa3ea
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313178"
---
# <a name="see-device-details-in-intune"></a>Eszközadatok megtekintése az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Eszközök** funkció további részletekkel szolgál a kezelt eszközökkel kapcsolatban, például hardveradatokkal és a telepített alkalmazások listájával.

Ez a cikk bemutatja, hogyan tekintheti meg az összes eszközét és azok tulajdonságait az Azure Portalon.

## <a name="view-the-device-details"></a>Eszköz részletes adatainak megtekintése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
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

## <a name="hardware-device-details"></a>Hardvereszköz részletes adatai

### <a name="windows-and-ios-device-details"></a>Windows és iOS rendszerű eszköz részletes adatai:
|Részletek|Description|  
|--------------|----------------------|  
|Név|Az eszköz neve.|
|Felügyeleti név|A csak a konzolon használt eszköznév. Ennek a névnek a módosítása nem változtatja meg a nevet az eszközön.|
|UDID|Az eszköz egyedi eszközazonosítója.|
|Intune-eszközazonosító|Az eszközt egyedileg azonosító GUID.|
|Sorozatszám|Az eszköz gyártótól származó sorozatszáma.|
|Megosztott eszköz|Ha **Igen**, akkor az eszköz több felhasználó között van megosztva.|
|Felhasználó által jóváhagyott regisztráció|Ha **Igen**, akkor az eszközön felhasználó által jóváhagyott regisztráció van érvényben. Ezáltal a rendszergazdák felügyelni tudják az eszköz bizonyos biztonsági beállításait.|
|Operációs rendszer|Az eszközön futó operációs rendszer.|
|Operációs rendszer verziója|Az eszközön futó operációs rendszer verziója.|
|Operációs rendszer nyelve|Az eszközön futó operációs rendszerhez beállított nyelv.|
|Teljes tárterület|Az eszközön lévő teljes tárterület (gigabájtban).|
|Szabad tárterület|Az eszközön lévő felhasználatlan tárterület (gigabájtban).|


### <a name="windows-ios-and-macos-device-details"></a>Windows, iOS és macOS rendszerű eszköz részletei
|Részletek|Description|  
|--------------|----------------------|  
|IMEI|Az eszköz Nemzetközi mobilkészülék-azonosító (IMEI) száma.|
|MEID|Az eszköz mobilkészülék-azonosító száma.|
|Gyártó|Az eszköz gyártója.|
|Modell|Az eszköz típusa.|
|Telefonszám|Az eszközhöz rendelt telefonszám.|
|Előfizetés-szolgáltató|Az eszköz vezeték nélküli szolgáltatója.|
|Mobiltechnológia|Az eszköz által használt rádiórendszer.|
|Wi-Fi MAC|Az eszköz MAC-címe.|
|ICCID|Az integrált áramköri kártya (ICC) azonosítója, amely a SIM-kártya egyedi azonosítószáma.|
|Regisztrálás dátuma|Az eszköz Intune-ban történt regisztrálásának dátuma és időpontja.|
|Utolsó kapcsolat|Az eszköz Intune-hoz való utolsó kapcsolódásának dátuma és időpontja.|
|Kód az aktiválási zár megkerüléséhez|Az aktiválási zár megkerüléséhez használható kód.|
|Az Azure AD-ban regisztrálva|Ha **Igen**, akkor az eszköz regisztrálva van az Azure Active Directoryban.|
|Megfelelőség|Az eszköz megfelelőségi állapota.|
|EAS aktiválva|Ha **Igen**, akkor az eszköz szinkronizálva van egy Exchange-postafiókkal.|
|EAS-aktiválási azonosító|Az eszköz Exchange ActiveSync-azonosítója.|
|Felügyelt|Ha **Igen**, akkor a rendszergazdák fokozott felügyelettel rendelkeznek az eszköz felett.|
|Titkosítva|Ha **Igen**, akkor az eszközön tárolt adatok titkosítva vannak.|



## <a name="next-steps"></a>További lépések
Ismerje meg az Intune-beli [eszközkezelés](device-management.md) további funkcióit.
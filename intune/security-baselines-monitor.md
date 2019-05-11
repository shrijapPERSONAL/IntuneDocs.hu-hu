---
title: Ellenőrizze a sikeres vagy sikertelen biztonsági előírások a Microsoft Intune – Azure |} A Microsoft Docs
description: Ellenőrizze a hiba történt, ütközés és sikerességének állapotát, amikor a biztonsági előírások telepítése felhasználók és eszközök a Microsoft Intune mobileszköz-kezelést. Hibaelhárítás a naplókba, és a jelentési szolgáltatások használatával az Intune-ban való használatáról.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/19/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a013698e56b342953e52296270e7571a257db860
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135092"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Biztonsági alapterv, illetve a Microsoft Intune-ban a profilok figyelése  

Intune-ban figyelheti a biztonsági előírások számos lehetőséget kínál. Figyelheti a biztonsági alaptervek profilt, amely a felhasználókra és eszközökre alkalmazható. A tényleges alapkonfiguráció és azokat az eszközöket, amelyek az ajánlott értékek egyeznie (vagy nem egyezik) is figyelheti.

Ez a cikk végigvezeti mindkét megfigyelési lehetőségeket.

[Az Intune-ban biztonsági előírások](security-baselines.md) további részleteket a biztonsági alapterveket szolgáltatás a Microsoft Intune-ban.

## <a name="monitor-the-baseline-and-your-devices"></a>Az alapkonfiguráció és az eszközök figyelése  

Amikor alapkonfigurációt, akkor információkhoz juthat az eszközök a Microsoft javaslatok alapján biztonsági állapotát. Ezek is használható elemzéseket készítsenek az Áttekintés ablaktábláján, a biztonsági alapkonfiguráció az Intune-konzolon tekintheti meg.  Az adatok jelennek meg először az alapterv hozzárendelése után akár 24 órát vesz igénybe. Újabb módosításokat jelennek meg akár hat órát is igénybe vehet.  

Az eredeti és az eszközöket a figyelési adatok megtekintéséhez jelentkezzen be a [Intune-portálon](https://go.microsoft.com/fwlink/?linkid=2090973). Majd **eszközbiztonsági** > **biztonsági előírások (előzetes verzió)**, jelölje be egy alapterv, és tekintse meg a **áttekintése** ablaktáblán.

A **áttekintése** ablaktábla állapotának figyelése kétféle módszert biztosít:
- **Eszköz megtekintése** – összegzését, hogy hány eszköz van az egyes állapota az alapterv esetében.  
- **Kategória –** – A nézet jeleníti meg az egyes kategóriák az alaptervet, és tartalmazza az állapot csoportonkénti alapkonfiguráció kategóriákhoz tartozó eszközök hány százalékát. 

Egyes eszközök a következő állapotok, mindkét használt egyik képviseli a *eszköz* nézet, és a *kategória* nézetek:  
- **Egyezések alapkonfiguráció** -az alapkonfiguráció összes beállításai megfelelnek az ajánlott beállításokat.
- **Nem felel meg a referenciakonfiguráció** -az alapkonfiguráció legalább egy beállítást nem felel meg az ajánlott beállításokat.
- **Nincs megfelelően konfigurálva** – legalább egy beállítást nincs megfelelően konfigurálva. Ez az állapot azt jelenti, hogy a beállítás az ütközést, hiba vagy függőben van.
- **Nem alkalmazható** – legalább egy beállítást nem alkalmazható, és nem érvényesek.


### <a name="device-view"></a>Eszköz megtekintése
Az áttekintő panel összefoglaló diagram-alapú, hogy hány eszköz van egy adott állapotát az alaptervhez; **Biztonsági alapkonfiguráció állapotát hozzárendelt Windows 10 rendszerű eszközökhöz**.  

![Az eszközök állapotának ellenőrzése](./media/security-baselines-monitor/overview.png)

Ha egy eszköz különböző kategóriák eltérő állapottal rendelkezik az alaptervet, az eszköz egyetlen állapotát jelképezi. Az állapot, amely az eszköz átveszi a rendszer az alábbi sorrendben: **Nincs megfelelően konfigurálva**, **nem egyezik meg a referenciakonfiguráció**, **nem alkalmazható**, **egyezések alapkonfiguráció**.  

Például, ha egy eszközhöz tartozik egy beállítás besorolt *helytelenül konfigurált* és besorolva egy vagy több beállítások *nem egyezik meg a referenciakonfiguráció*, az eszköz akkor minősül *konfigurációja*.  

Kattinthat, áthatoló részletezést, és az eszközök különböző állapotok listájának megtekintéséhez a diagramban. Ezután kiválaszthatja az egyes eszközök a listából az egyes eszközök részletes információinak megtekintéséhez. Példa:
- Válassza ki **eszközkonfiguráció** > Válassza ki a profilt a hibás állapotú:

  ![Az eszközök állapotának ellenőrzése](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Válassza ki a hibát profilt. A profil, és azok állapotát az összes beállítás listája látható. Most görgethet keresse meg a hibát okozó beállítást:

  ![A hibát okozó beállítást](./media/security-baselines-monitor/profile-with-error-status.png)

Ez a jelentéskészítés segítségével tekintse meg a problémát okozó profil beállításait. A házirendek és profilok eszközökre telepített további részleteket is kaphat.

> [!NOTE]
> Ha egy tulajdonság értéke **nincs konfigurálva** az alaptervet, a rendszer figyelmen kívül hagyja, és nincs korlátozás érvényben vannak. A tulajdonság nem jelenik meg minden olyan jelentési.

### <a name="per-category-view"></a>Egy kategória nézet
Az Áttekintés ablaktábláján az alaptervhez; kategória diagramot jelenít meg. **Biztonsági alapkonfiguráció állapotát kategória szerint**.  Ez a nézet jeleníti meg az egyes kategóriák az alaptervből, és azonosítja az eszközöket, melyek állapota besorolást az egyes kategóriákhoz aránya. 
 
![Állapot kategória nézete](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Az állapot **egyezések alapkonfiguráció** nem jelennek meg, amíg a 100 %-án jelentés kategóriájára vonatkozó állapota.   

Minden oszlop-kategória nézetében az oszlop tetején fel-le nyíl ikonra kattintva rendezheti.  


## <a name="monitor-the-profile"></a>A profil figyelése

Figyelés a profil lehetővé teszi az eszközök üzembe helyezési állapotát, de nem a biztonsági állapotot az általános javaslatok alapján betekintést.

1. Válassza ki az Intune-ban **biztonsági előírások** > Válassza ki az alapkonfigurációt > **létrehozott profilok**.

2. Válasszon egy profilt. A **áttekintése**, a kép bemutatja, hogy hány eszköz és a felhasználók rendelkeznek a hozzárendelt profil:

    ![Tekintse meg, hány eszközök és felhasználók hozzárendelése biztonsági alapterveket profiljának](./media/security-baselines-monitor/existing-profile-overview.png)

3. A **kezelés** > **tulajdonságok**, az összes jelennek meg a beállításokat az alaptervet. Ezek a beállítások bármelyikét is módosíthatja:

    ![Tekintse meg, és a biztonsági alapterveket profil beállításainak frissítése](./media/security-baselines-monitor/manage-settings.png)

4. A **figyelő**, a profil telepítési állapotát láthatja az egyes eszközöket, a felhasználók állapotát és az egyes beállítások az alapkonfiguráció állapotát:

    ![Biztonsági alapterveket profil különböző figyelő beállításainak megjelenítéséhez](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Hibaelhárítás a használatával állapot beállításonként

Üzembe helyezett egy biztonsági alaptervet, de a központi telepítés állapota: Hiba történt. Az alábbi lépéseket a hiba elhárításáról útmutatást nyújtanak.

1. Válassza ki az Intune-ban **biztonsági előírások** > Válassza ki az alapkonfigurációt > **létrehozott profilok**.
2. Profil kiválasztása > alatt **figyelő** > **állapot beállításonként**.
3. A tábla összes beállítás és az egyes beállítások állapotát mutatja. Válassza ki a **hiba** oszlop vagy a **ütközés** oszlop a hibát okozó beállítást.

### <a name="mdm-diagnostic-information"></a>Mobileszköz-kezelési diagnosztikai információk

Most már ismeri a problémás beállítást. A következő lépés, hogy ismerje meg, hogy miért Ez a beállítás okozza-e hiba vagy ütközés. 

A Windows 10-eszközökön nincs MDM beépített diagnosztikai adatokat jelentést. Ez a jelentés az alapértelmezett értékeket, aktuális értékeit tartalmazza, sorolja fel a szabályzat, jeleníti meg, ha az eszköz és a felhasználó több telepítették. Ez a jelentés a segítségével megállapítható, hogy miért a beállítás egy ütközés vagy hiba okozza.

1. Az eszközön, Ugrás **beállítások** > **fiókok** > **hozzáférés munkahelyi vagy iskolai**.
2. Válassza ki a fiókot > **Info** > **speciális diagnosztikai jelentés** > **jelentés létrehozása**.
3. Válasszon **exportálása**, és nyissa meg a létrehozott fájlt.
4. Keresse meg a jelentést, a hiba vagy ütközés beállítás a jelentés különböző szakaszaiban.

  Keresse meg például a **konfigurációs források és célerőforrások regisztrált** szakasz vagy a **házirendek nem felügyelt** szakaszban. Miért hiba vagy ütközés miatt képet kaphat.

[A Windows 10 MDM hibáinak diagnosztizálása](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) további információkkal szolgál a beépített jelentés.

> [!TIP]
> - Egyes beállítások is listázza a GUID Azonosítót. Ez a helyi beállításjegyzékben (regedit) minden olyan értékek beállítása a GUID kereshet.
> - Az eseménynaplókat is tartalmazhat néhány hiba adatok a problémás (**Eseménynapló** > **alkalmazások és szolgáltatásnaplók**  >   **A Microsoft** > **Windows** > **DeviceManagement – Enterprise-diagnosztikai-szolgáltató** > **rendszergazda** ).

## <a name="next-steps"></a>További lépések

[Eszközprofilok figyelése](device-profile-monitor.md) és [tekintse meg néhány gyakori problémák és megoldásuk](device-profile-troubleshoot.md).

---
title: 'Lásd: Eszközprofilok a Microsoft Intune-ban – Azure | Microsoft Docs'
description: Megtekintheti és kezelheti az eszközkonfigurációs profilok adatait a Microsoft Intune-ban, egy grafikus diagramon tekintheti meg a profilokhoz rendelt eszközök számát, és megtekintheti, mely eszközök rendelkeznek hozzárendelt vagy üzembe helyezett profillal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bffb6832200379fca0221d8718afdebe06163980
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744788"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Eszközprofilok figyelése a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune egyes Azure Portalbeli funkcióival figyelheti és kezelheti az eszközkonfigurációs profilokat. Például ellenőrizheti egy profil állapotát, megtekintheti a hozzárendelt eszközöket, és frissítheti a profiltulajdonságokat.

## <a name="view-existing-profiles"></a>Meglévő profilok megtekintése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **Profilok** lehetőséget.

Itt mindegyik meglévő profil megjelenik olyan adatokkal, mint a platform, vagy a profil eszköz-hozzárendelési állapota.

## <a name="view-details-on-a-profile"></a>Egy profil adatainak megtekintése

Az eszközprofil létrehozása után az Intune grafikus diagramokat nyújt. Ezek a diagramok a profilok állapotát jelenik meg, például, hogy hozzá vannak-e rendelve eszközökhöz, vagy tartalmaznak-e ütközéseket.

1. Válasszon ki egy meglévő profilt, például egy macOS-profilt.
2. Lépjen az **Áttekintés** fülre.

    A felső grafikus diagramon megtekintheti az adott eszközprofilhoz rendelt eszközök számát. Ha például az eszközprofil macOS-eszközökre van alkalmazva, akkor a diagram csak a macOS-eszközök számát jeleníti meg.

    Emellett más platformok eszközeinek számát is megjeleníti, ha ezek ugyanahhoz az eszközprofilhoz vannak rendelve. Például megtekintheti a nem macOS-eszközök számát.

    ![Az eszközprofilhoz rendelt eszközök számának megtekintése](./media/device-configuration-profile-graphical-chart.png)

    Az alsó grafikus diagramon megtekintheti az adott eszközprofilhoz rendelt felhasználók számát. Ha például az eszközprofil macOS-felhasználókra van alkalmazva, akkor a diagram a macOS-felhasználók számát jeleníti meg.

3. Kattintson a felső grafikus diagramon látható körre. Ekkor megnyílik az **Eszközállapot** menü.

    Itt láthatja a profilhoz rendelt eszközöket, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Ne feledje, hogy itt csak a megadott platform eszközei jelennek meg (például macOS).

    Zárja be az **Eszközállapot** adatait.

4. Kattintson az alsó grafikus diagramon látható körre. Ekkor megnyílik a **Felhasználó állapota** menü. 

    Itt láthatja a profilhoz rendelt felhasználókat, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Ne feledje, hogy itt csak a megadott platform (például macOS) felhasználói jelennek meg.

    Zárja be a **Felhasználó állapota** adatait.

5. Miután visszalépett a **Profilok** listára, válasszon ki egy adott profilt. A meglévő tulajdonságokat is módosíthatja:
  - **Tulajdonságok**: Módosíthatja a nevet, vagy frissítheti a meglévő beállításokat.
  - **Hozzárendelések**: Belefoglalhat vagy kizárhat a szabályzat hatálya alá tartozó eszközöket. Adott csoportok kiválasztásához válassza a **Kiválasztott csoportok** lehetőséget.
  - **Eszközállapot**: Itt láthatja a profilhoz rendelt eszközöket, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Egy adott eszközt kijelölve még több adatot megtekinthet, például a telepített alkalmazásokat.
  - **Felhasználói állapot**: A profil hatálya alá tartozó eszközök felhasználóinak neveit jeleníti meg, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Egy adott felhasználót kijelölve még több adatot megtekinthet.
  - **Állapot beállításonként**: A kimenetet szűri a profil egyes beállításait megjelenítve, valamint megmutatja, hogy a beállítást sikeresen alkalmazták-e.

## <a name="next-steps"></a>További lépések
[Felhasználói és eszközprofilok hozzárendelése](device-profile-assign.md)  
[Eszközprofilokkal kapcsolatos gyakori problémák és azok megoldása](device-profile-troubleshoot.md)
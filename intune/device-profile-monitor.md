---
title: 'Lásd: Eszközprofilok a Microsoft Intune-ban – Azure | Microsoft Docs'
description: Megtekintheti és kezelheti az eszközkonfigurációs profilok adatait a Microsoft Intune-ban, egy grafikus diagramon tekintheti meg a profilokhoz rendelt eszközök számát, és megtekintheti, mely eszközök rendelkeznek hozzárendelt vagy üzembe helyezett profillal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1c2eb08db58940ed575b3dea011395edd6711fc
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
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

    A grafikus diagramon megtekintheti az adott eszközprofilhoz rendelt eszközök számát. Ha például az eszközprofil macOS-eszközökre van alkalmazva, akkor a diagram csak a macOS-eszközök számát jeleníti meg.

    Emellett más platformok eszközeinek számát is megjeleníti, ha ezek ugyanahhoz az eszközprofilhoz vannak rendelve. Például megtekintheti a nem macOS-eszközök számát.

    ![Az eszközprofilhoz rendelt eszközök számának megtekintése](./media/device-configuration-profile-graphical-chart.png)

3. A grafikus diagramon kattintson a körre. Ekkor megnyílik az **Eszközállapot** menü.

    Itt láthatja a profilhoz rendelt eszközöket, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Ne feledje, hogy itt csak a megadott platform eszközei jelennek meg (például macOS).

    Zárja be az eszközállapot adatait.

4. A profil tulajdonságai között (**Profilok** > Válassza ki az adott profilt) módosíthatja a meglévő tulajdonságokat is:
  - **Tulajdonságok**: Módosíthatja a nevet, vagy frissítheti a meglévő beállításokat.
  - **Hozzárendelések**: Belefoglalhat vagy kizárhat a szabályzat hatálya alá tartozó eszközöket. Adott csoportok kiválasztásához válassza a **Kiválasztott csoportok** lehetőséget.
  - **Eszközállapot**: Itt láthatja a profilhoz rendelt eszközöket, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Egy adott eszközt kijelölve még több adatot megtekinthet, például a telepített alkalmazásokat.
  - **Felhasználói állapot**: A profil hatálya alá tartozó eszközök felhasználóinak neveit jeleníti meg, valamint azt, hogy a profilt sikeresen üzembe helyezték-e. Egy adott felhasználót kijelölve még több adatot megtekinthet.
  - **Állapot beállításonként**: A kimenetet szűri a profil egyes beállításait megjelenítve, valamint megmutatja, hogy a beállítást sikeresen alkalmazták-e.

## <a name="next-steps"></a>További lépések
[Felhasználói és eszközprofilok hozzárendelése](device-profile-assign.md)  
[Eszközprofilokkal kapcsolatos gyakori problémák és azok megoldása](device-profile-troubleshoot.md)
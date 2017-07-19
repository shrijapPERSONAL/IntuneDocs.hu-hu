---
title: "Megosztott eszközök Intune-beli konfigurációs beállításai iOS-re"
titleSuffix: Intune on Azure
description: "Ismertető az iOS-eszköz zárolási képernyőjén információ megjelenítéséhez használható beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bb1f8c7a9b6c92c128f32910f2ad8d390b6c64
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/05/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Közös használatú eszköz konfigurációs beállításai üzenetek megjelenítéséhez az iOS-eszköz zárolási képernyőjén

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A közös használatú eszköz konfigurációs beállításai lehetővé teszik választható szöveg megjelenítését a bejelentkezési ablakban és a zárolási képernyőn. Megadhat például „Elvesztés esetén küldje vissza” üzenetet és eszközcímkeadatokat. 

>[!IMPORTANT]
> Ez a funkció az iOS 9.3-as vagy újabb verzióját futtató felügyelt eszközökön támogatott.

## <a name="create-shared-device-settings"></a>Közös használatú eszköz beállításainak létrehozása

1. Az **Eszközfunkciók** panelen válassza a **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** lehetőséget.
2. A **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** panelen konfigurálja a következőket:
    - **Eszközcímke-információ** – Adjon meg információkat az eszköz eszközcímkéjéről. Például: **A Contoso vállalat tulajdona**. A megadott információ minden eszközön megjelenik, amelyhez ezt a profilt hozzárendeli.
    - **Lábjegyzet a zárolási képernyőn** – Adjon meg egy szöveget, amely elősegíti, hogy az elvesztett vagy ellopott eszközt visszahozzák. Például: **Ha megtalálta, kérjük, hívja ezt a számot: <telefonszám>**.
3. Ha végzett, válassza az **OK** lehetőséget annyiszor, amíg vissza nem tér a **Profil létrehozása** panelhez, majd válassza a **Létrehozás** elemet. 


## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).

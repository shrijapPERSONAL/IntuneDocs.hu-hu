---
title: Megosztott eszközök Microsoft Intune-beli konfigurációs beállításai iOS-re
titlesuffix: ''
description: Ismertető az iOS-eszköz zárolási képernyőjén információ megjelenítéséhez használható Microsoft Intune-beállításokról.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73c4f96e3057227bc601175c4e8f42802eb322bc
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Közös használatú eszköz konfigurációs beállításai üzenetek megjelenítéséhez az iOS-eszköz zárolási képernyőjén

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk ismerteti az iOS-eszköz zárolási képernyőjén információ megjelenítéséhez használható Microsoft Intune-beállításokat.

A közös használatú eszköz konfigurációs beállításai lehetővé teszik választható szöveg megjelenítését a bejelentkezési ablakban és a zárolási képernyőn. Megadhat például „Elvesztés esetén küldje vissza” üzenetet és eszközcímkeadatokat. 

>[!IMPORTANT]
> Ez a funkció az iOS 9.3-as vagy újabb verzióját futtató felügyelt eszközökön támogatott.

## <a name="create-shared-device-settings"></a>Közös használatú eszköz beállításainak létrehozása

1. Az [Intune az Azure Portalon](https://portal.azure.com) felületről lépjen az eszközkonfigurációs terület [**Eszközfunkciók** részére](device-features-configure.md). 
1. Az **Eszközfunkciók** panelen válassza a **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** lehetőséget.
2. A **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** panelen konfigurálja a következőket:
    - **Eszközcímke-információ** – Adjon meg információkat az eszköz eszközcímkéjéről. Például: **A Contoso vállalat tulajdona**. A megadott információ minden eszközön megjelenik, amelyhez ezt a profilt hozzárendeli.
    - **Lábjegyzet a zárolási képernyőn** – Adjon meg egy szöveget, amely elősegíti, hogy az elvesztett vagy ellopott eszközt visszahozzák. Például: **Ha megtalálta, kérjük, hívja ezt a számot: <telefonszám>**.
3. Ha végzett, válassza az **OK** lehetőséget annyiszor, amíg vissza nem tér a **Profil létrehozása** panelhez, majd válassza a **Létrehozás** elemet. 


## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).

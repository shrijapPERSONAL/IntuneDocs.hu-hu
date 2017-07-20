---
title: "Az Intune eszközfunkció-beállításainak konfigurálása"
titleSuffix: Intune on Azure
description: "A cikk azt ismerteti, hogyan használható az Intune a funkciók kezelt eszközökön való konfigurálásához.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f286119019bb26d8851c766a9d88ad818d7e600b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Az eszközfunkció-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az eszközkorlátozásokkal lehet szabályozni az iOS- és macOS-eszközök funkcióit, például az AirPrintet, az értesítéseket és a megosztott eszközkonfigurációkat.

A témakörben található információk alapján megismerheti az eszközfunkció-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az eszközfunkció-profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet eszközfunkció-beállításokat megadni:
    - **iOS**
    - **macOS**
6. A **Profil típusa** legördülő listában válassza az **Eszközfunkciók** lehetőséget. 
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [AirPrint-beállítások iOS-re és MacOS-re](air-print-settings-ios-macos.md)
    - [AirPlay-beállítások iOS-re](airplay-settings-ios.md)
    - [Kezdőképernyő-elrendezési beállítások iOS-re](home-screen-settings-ios.md)
    - [Alkalmazások értesítési beállításai iOS-re](app-notification-settings-ios.md)
    - [Közös használatú eszközök konfigurációs beállításai iOS-re](shared-device-settings-ios.md)
    - [Webtartalomszűrő-beállítások iOS-re](web-content-filter-settings-ios.md)

8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.



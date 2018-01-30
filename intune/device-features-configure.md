---
title: "Az Intune eszközfunkció-beállításainak konfigurálása"
titleSuffix: Azure portal
description: "A cikk azt ismerteti, hogyan használható az Intune a funkciók kezelt eszközökön való konfigurálásához.”"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98512f3d36af8c1c90440279d84b3a336bba339b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
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
    - [Az Intune konfigurálása egyszeri bejelentkezéshez iOS-eszközökön](sso-ios.md)
    - [Webtartalomszűrő-beállítások iOS-re](web-content-filter-settings-ios.md)

8. Miután elkészült, lépjen vissza a **Profil létrehozása** panelre, és kattintson a **Létrehozás** elemre.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.




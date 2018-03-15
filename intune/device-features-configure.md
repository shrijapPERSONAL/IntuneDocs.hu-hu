---
title: "A Microsoft Intune eszközfunkció-beállításainak konfigurálása"
titleSuffix: 
description: "Megtudhatja, hogyan használható a Microsoft Intune a funkciók kezelt eszközökön való konfigurálásához."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Az eszközfunkció-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az eszközfunkciókkal lehet szabályozni az iOS- és macOS-eszközök funkcióit, például az AirPrintet, az értesítéseket és a megosztott eszközkonfigurációkat.

A cikkben található információk alapján megismerheti az eszközfunkció-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további cikkekben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Eszközfunkciós beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** lapon válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** lap **Kezelés** területén válassza a **Profilok** lehetőséget.
3. A profilok lapján válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** lapon adja meg az eszközfunkció-profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet eszközfunkció-beállításokat megadni:
    - **iOS**
    - **macOS**
6. A **Profil típusa** legördülő listában válassza az **Eszközfunkciók** lehetőséget. 
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi cikkekben találja a beállítások részletes ismertetését:
    - [AirPrint-beállítások iOS-re és MacOS-re](air-print-settings-ios-macos.md)
    - [AirPlay-beállítások iOS-re](airplay-settings-ios.md)
    - [Kezdőképernyő-elrendezési beállítások iOS-re](home-screen-settings-ios.md)
    - [Alkalmazások értesítési beállításai iOS-re](app-notification-settings-ios.md)
    - [Közös használatú eszközök konfigurációs beállításai iOS-re](shared-device-settings-ios.md)
    - [Az Intune konfigurálása egyszeri bejelentkezéshez iOS-eszközökön](sso-ios.md)
    - [Webtartalomszűrő-beállítások iOS-re](web-content-filter-settings-ios.md)

8. Ha elkészült, kattintson az **OK** gombra, lépjen vissza a **Profil létrehozása** lapra, és válassza a **Létrehozás** lehetőséget.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó lapon.
## <a name="next-steps"></a>További lépések

Ha a profilt csoportokhoz szeretné rendelni, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.




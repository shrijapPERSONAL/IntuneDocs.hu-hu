---
title: iOS- és macOS-eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-nal hozzáadhat vagy létrehozhat egy iOS- vagy macOS-eszközprofilt, és konfigurálhatja az AirPrint és AirPlay funkciót, a kezdőképernyő elrendezését, az alkalmazásértesítéseket, a megosztott eszközöket, az egyszeri bejelentkezést és a webtartalomszűrő beállításait.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d823a7f8d3478c0ff6c0049a6bbaa76bb4247479
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>iOS-es vagy macOS-es eszközfunkció-beállítások megadása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az eszközfunkciókkal az iOS és macOS rendszerű eszközök számos különböző beállítását és szolgáltatását szabályozhatja, ideértve például a következőket:

- Az AirPrint és az AirPlay beállításai
- A kezdőképernyő elrendezése
- Alkalmazások értesítései
- Megosztott eszköz konfigurációja
- Az egyszeri bejelentkezés beállítása
- Webtartalomszűrés

Ez a cikk bemutatja az iOS-es eszközfunkció-profilok konfigurálásának alapjait. Ezután további cikkek elolvasásával megtudhatja, hogyan konfigurálhatja az eszközei platformspecifikus beállításait.

## <a name="create-a-device-profile"></a>Eszközprofil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
4. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Leírás:** Itt adhatja meg a profil leírását. (Nem kötelező, de ajánlott a használata.)
   - **Platform**: Válassza ki a platform típusát:
     - **iOS**
     - **macOS**
   - **Profil típusa**: Válassza az **Eszközfunkciók** lehetőséget.
   - **Beállítások**: Az elérhető beállításokat a választott platform határozza meg. Az alábbi cikkek ismertetik az egyes profiltípusok beállításait:

     - [AirPrint-beállítások iOS-re és MacOS-re](air-print-settings-ios-macos.md)
     - [AirPlay-beállítások iOS-re](airplay-settings-ios.md)
     - [Kezdőképernyő-elrendezési beállítások iOS-re](home-screen-settings-ios.md)
     - [Alkalmazások értesítési beállításai iOS-re](app-notification-settings-ios.md)
     - [Közös használatú eszközök konfigurációs beállításai iOS-re](shared-device-settings-ios.md)
     - [Az Intune konfigurálása egyszeri bejelentkezéshez iOS-eszközökön](sso-ios.md)
     - [Webtartalomszűrő-beállítások iOS-re](web-content-filter-settings-ios.md)

5. Ha elkészült, a változások mentéséhez válassza az **OK** gombot, majd a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a listában.

## <a name="next-step"></a>Következő lépés

Ha a profilt csoportokhoz szeretné rendelni, az [Eszközprofilok hozzárendelése](device-profile-assign.md) című cikkben talál további információt.
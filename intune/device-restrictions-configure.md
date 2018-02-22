---
title: "Eszközkorlátozásokra vonatkozó beállítások konfigurálása az Intune-ban"
titleSuffix: Azure portal
description: "A cikk azt ismerteti, hogyan használható az Intune a beállítások és funkciók kezelt eszközökön való konfigurálásához.”"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93b6a642f26ec6273853f75d063fd368698f3864
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Az eszközkorlátozásokra vonatkozó beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az eszközkorlátozások révén számos kategóriában szabályozhatja a kezelt beállítások és funkciók széles körét, például:
- Biztonság
- Böngésző
- Hardver
- Adatmegosztási beállítások

Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.

A témakörben található információk alapján megismerheti az eszközkorlátozási profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az eszközkorlátozási profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre egyéni beállításokat szeretne alkalmazni. Jelenleg az alábbi platformok egyikét választhatja ki az eszközkorlátozási beállításokhoz:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza az **Eszközkorlátozások** lehetőséget. Ha Windows 10 Team-eszközökhöz, például egy Surface Hubhoz szeretne létrehozni egy eszközkorlátozási profilt, válassza az **Eszközkorlátozások (Windows 10 Team)** lehetőséget.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](device-restrictions-android.md)
    - [iOS-beállítások](device-restrictions-ios.md)
    - [macOS-beállítások](device-restrictions-macos.md)
    - [Windows Phone 8.1-beállítások](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10-beállítások](device-restrictions-windows-10.md)
    - [Windows 10 Team-beállítások](device-restrictions-windows-10-teams.md)
    - [A Windows Holographic for Business beállításai](device-restrictions-windows-holographic.md)
    - [Az Android for Work beállításai](device-restrictions-android-for-work.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
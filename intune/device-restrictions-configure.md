---
title: "Eszközkorlátozásokra vonatkozó beállítások konfigurálása a Microsoft Intune-ban"
titleSuffix: 
description: "A cikk azt ismerteti, hogyan használható a Microsoft Intune a beállítások és funkciók kezelt eszközökön való konfigurálásához."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 62c12cde5ca128a26b10e0e4516e0bbf7e0f0bbb
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Az eszközkorlátozásokra vonatkozó beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az eszközkorlátozások révén számos kategóriában szabályozhatja a kezelt beállítások és funkciók széles körét, például:
- Biztonság
- Böngésző
- Hardver
- Adatmegosztási beállítások

Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.

A cikk az eszközkorlátozási profilok alapjait ismerteti, és további cikkeket ajánl a különféle platformokhoz tartozó eszközspecifikus kérdésekhez.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** lapon válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** lap **Kezelés** területén válassza a **Profilok** lehetőséget.
3. A **Profilok** lapon válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** lapon adjon meg egy **Nevet** és **Leírást** az eszközkorlátozási profilra vonatkozóan.
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
8. Miután elkészült, lépjen vissza a **Profil létrehozása** panelre, és kattintson a **Létrehozás** elemre.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó lapon.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
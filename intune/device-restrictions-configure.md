---
title: Eszközkorlátozási beállítások konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Eszközprofillal korlátozhatja a funkciókat Android, macOS, iOS, Windows Phone és Windows 10 rendszerű eszközökön a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e040743975a482c702e0c0168a4fd6315a2dac8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57387915"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Ezközkorlátozásokra vonatkozó beállítások konfigurálása a Microsoft Intune-ban

Az eszközkorlátozások révén számos kategóriában szabályozhatja a kezelt beállítások és funkciók széles körét, például:
- Biztonság
- Böngésző
- Hardver
- Adatmegosztási beállítások

Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.

A cikk az eszközkorlátozási profilok alapjait ismerteti, és további cikkeket ajánl a különféle platformokhoz tartozó eszközspecifikus kérdésekhez.

## <a name="create-the-profile"></a>A profil létrehozása

1. A, a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg az eszközkorlátozási profil nevét és leírását a **Név** és a **Leírás** mezőben.
4. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre egyéni beállításokat szeretne alkalmazni. Jelenleg az alábbi platformok egyikét választhatja ki az eszközkorlátozási beállításokhoz:

    - **Android**
    - **Vállalati Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**

5. A **Profil típusa** legördülő listában válassza az **Eszközkorlátozások** lehetőséget. Eszköz létrehozásához korlátozások Windows 10 Team eszközök, például a Surface hubon és a profilt, majd válassza **eszközkorlátozások (Windows 10 Team)**.
6. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Válassza ki a platformot a részletes beállításokat:

    - [Android-beállítások](device-restrictions-android.md)
    - [Android enterprise-beállítások](device-restrictions-android-for-work.md)
    - [iOS-beállítások](device-restrictions-ios.md)
    - [macOS-beállítások](device-restrictions-macos.md)
    - [Windows Phone 8.1-beállítások](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10-beállítások](device-restrictions-windows-10.md)
    - [Windows 10 Team-beállítások](device-restrictions-windows-10-teams.md)
    - [A Windows Holographic for Business beállításai](device-restrictions-windows-holographic.md)

7. Ha elkészült, a módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A profil létrehozásáról és a profilok listájában jelenik meg.

## <a name="next-steps"></a>További lépések

A profil létrehozását követően készen áll hozzá kell rendelni. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

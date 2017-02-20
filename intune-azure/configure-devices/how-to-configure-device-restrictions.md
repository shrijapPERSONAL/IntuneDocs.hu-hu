---
title: "Az Intune eszközkorlátozási beállításainak konfigurálása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: További információ arról, hogyan használható az Intune a beállítások és funkciók a kezelt eszközökön való konfigurálásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 67e3481f9cf01bd1b298cfb26f25d1a3205e0f29
ms.openlocfilehash: 0c22d8a85d90139b3ac17c54668890d5b4c0afe6


---

# <a name="how-to-configure-device-restriction-settings-in-intune-azure-preview"></a>Az eszközkorlátozási beállítások konfigurálása a következőben: Intune az Azure-on – előzetes

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az eszközkorlátozások révén számos olyan kategóriában szabályozhatja a kezelt beállítások és funkciók széles körét, mint például a biztonsági, a böngésző-, a hardver- és az adatmegosztási beállítások. Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.

A témakörben található információk alapján megismerheti az eszközkorlátozási profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
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
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek lesznek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](device-restrictions-for-android.md)
    - [iOS-beállítások](device-restrictions-for-ios.md)
    - [macOS-beállítások](device-restrictions-for-macos.md)
    - [Windows Phone 8.1-beállítások](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Windows 10-beállítások](device-restrictions-for-windows-10.md)
    - [Windows 10 Team-beállítások](device-restrictions-for-windows-10-team.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és nyomja meg a **Létrehozás** gombot.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profilt csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](how-to-assign-device-profiles.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.

## <a name="example-of-device-restriction-settings"></a>Eszközkorlátozási beállítások – példa

Ebben a magas szintű példában egy olyan eszközkorlátozási szabályzatot hozhat létre, amely letiltja a beépített kameraalkalmazás használatát az androidos eszközökön.

![A kamera letiltása androidos eszközökön](./media/disable-android-camera.png)




<!--HONumber=Feb17_HO1-->


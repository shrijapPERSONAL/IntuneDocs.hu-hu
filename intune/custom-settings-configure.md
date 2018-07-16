---
title: Egyéni eszközbeállítások az Azure-beli Intune-ban | Microsoft Docs
description: Profilok hozzáadása és létrehozása egyéni beállítások használatához Windows, Android és iOS-eszközökön a Microsoft Intune-nal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d917d2449e75b89db00d453b72940a93efb03321
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905002"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Egyéni beállításokkal rendelkező profil létrehozása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Előfordulhat, nem talál meg minden szükséges vagy igényelt beépített beállítást az Intune-ban. Az is megtörténhet, hogy olyan beállítást kíván használni, amely más eszközprofilokban is elérhető. A beállítások hozzáadásához létrehozhat egy eszközprofilt, és egyéni eszközbeállításokkal konfigurálhatja azt.

Ez a cikk az egyéni beállításokkal rendelkező profil létrehozásának alapvető lépéseit mutatja be. A felsorolt hivatkozások segítségével megtekintheti az egyéni beállítások létrehozásának részleteit a különböző platformokon.

## <a name="custom-settings-on-different-platforms"></a>Egyéni beállítások különböző platformokon
Az egyéni beállításokat minden platformra külön-külön kell konfigurálni. Az Android és Windows rendszerű eszközök funkcióinak vezérléséhez például Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket adhat meg. Apple-eszközök esetében importálhatja az [Apple Configuratorral](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) létrehozott fájlokat.

## <a name="create-the-profile"></a>A profil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** lehetőséget, kattintson a **Profilok** elemre, majd válassza a **Profil létrehozása** lehetőséget.
4. A **Név** és **Leírás** mezőben adja meg az egyéni profil nevét és leírását.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre az egyéni beállításokat alkalmazni fogja. A következő platformok közül választhat:

    - **Android**
    - **Vállalati Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**

6. A **Profil** típusa legördülő listában válassza az **Egyéni** lehetőséget.
7. A konfigurálható beállítások különböznek az egyes kiválasztott platformokon. Az alábbi hivatkozások további részletekkel szolgálnak az egyes platformok egyéni beállításaihoz:

    - [Android-beállítások](custom-settings-android.md)
    - [iOS-beállítások](custom-settings-ios.md)
    - [macOS-beállítások](custom-settings-macos.md)
    - [Windows Phone 8.1-beállítások](custom-settings-windows-phone-8-1.md)
    - [Windows 10-beállítások](custom-settings-windows-10.md)
    - [A Windows Holographic for Business beállításai](custom-settings-windows-holographic.md)
    - [Androidos munkahelyi profil beállításai](custom-settings-android-for-work.md)

8. Amikor elkészült, kattintson a **Létrehozás** elemre.

Ekkor létrejön a profil, és megjelenik a profilok listájában. Ha a profilt csoportokhoz szeretné rendelni, az [Eszközprofilok hozzárendelése](device-profile-assign.md) című cikkben talál további információt.

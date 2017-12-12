---
title: "Egyéni eszközbeállítások konfigurálása az Intune-ban"
titleSuffix: Azure portal
description: "Információ arról, hogyan használható az Intune az Ön által kezelt eszközök egyéni beállításainak konfigurálására."
keywords: 
author: vhorne
ms.author: victorh
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
ms.openlocfilehash: d7568a74256688271794b6baa752a23e24cf8d67
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Mikor kell egyéni beállításokat használni?

Az egyéni eszközbeállítások akkor lehetnek hasznosak, ha az Intune nem rendelkezik a kívánt beépített beállítással, vagy ha azok nem érhetőek el más eszközprofilokból.
Az egyéni beállításokat minden platformra külön-külön kell konfigurálni. Például Android és Windows rendszerű eszközökre megadhat OMA-URI (Open Mobile Alliance Uniform Resource Identifier) értékeket az eszköz funkcióinak vezérléséhez. Apple-eszközök esetében importálhatja az [Apple Configuratorral](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) létrehozott fájlokat.

A témakörben található információk alapján megismerheti az egyéni beállításokkal rendelkező profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-custom-settings"></a>Az egyéni beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni profilra vonatkozó **Név** és **Leírás** szövegét.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre egyéni beállításokat szeretne alkalmazni. Jelenleg az alábbi platformokra vonatkozóan lehet egyéni eszközbeállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 és újabb**
6. A **Profil** típusa legördülő listában válassza az **Egyéni** lehetőséget.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](custom-settings-android.md)
    - [iOS-beállítások](custom-settings-ios.md)
    - [macOS-beállítások](custom-settings-macos.md)
    - [Windows Phone 8.1-beállítások](custom-settings-windows-phone-8-1.md)
    - [Windows 10-beállítások](custom-settings-windows-10.md)
    - [Az Android for Work beállításai](custom-settings-android-for-work.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.

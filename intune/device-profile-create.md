---
title: Eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-ban eszközprofilokat adhat hozzá és konfigurálhat, így megadhatja a platform típusát és konfigurálhatja a beállításokat az Azure Portalon.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e5070052c0d4cce3cfd81a7bae259bc7dfb22e7f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/20/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Eszközprofil létrehozása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>A profil létrehozása
1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, majd keresse meg a **Microsoft Intune** elemet.

2. A **Microsoft Intune** területen válassza az **Eszközkonfiguráció** lehetőséget, majd a **Profilok** elemet. Ezt követően válassza a **Profil létrehozása** lehetőséget.

3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Leírás:** Itt adhatja meg a profil leírását. (Nem kötelező, de ajánlott a használata.)
    - **Platform**: Válassza ki a platform típusát:  

        - **Android**
        - **Android for Work**
        - **iOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 és újabb**
        - **Windows 10 és újabb**

    - **Profiltípus**: Válassza ki a létrehozni kívánt profil típusát. A lista a választott platformtól függ.
    - **Beállítások**: Az alábbi témakörök az egyes profiltípusok beállításait ismertetik:

        -  [Eszközfunkciók beállításai](device-features-configure.md)
        -  [Eszközkorlátozási beállítások](device-restrictions-configure.md)
        -  [E-mail-beállítások](email-settings-configure.md)
        -  [VPN-beállítások](vpn-settings-configure.md)
        -  [Wi-Fi-beállítások](wi-fi-settings-configure.md)
        -  [A Windows 10 kiadásfrissítési beállításai](edition-upgrade-configure-windows-10.md)
        -  [Tanúsítványbeállítások](certificates-configure.md)
        -  [A Windows Információvédelem beállításai](windows-information-protection-configure.md)
        -  [Oktatási beállítások](education-settings-configure.md)
        -  [Egyéni beállítások](custom-settings-configure.md)

    ![A Profil létrehozása képernyőképe](./media/create-device-profile.png)

4. Ha kész, válassza a **Létrehozás** lehetőséget.

Ekkor létrejön a profil, és megjelenik a listában.


## <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendeléséhez tekintse meg az [Eszközprofilok hozzárendelése a Microsoft Intune-nal](device-profile-assign.md) című témakört.

---
title: Eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-ban eszközprofilokat adhat hozzá és konfigurálhat, így megadhatja a platform típusát és konfigurálhatja a beállításokat az Azure Portalon.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f62e306574606ffa1eb1e6f242c3cb30b1a9c1b
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744652"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Eszközprofil létrehozása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

       -  [Eszközfunkciók](device-features-configure.md)
       -  [Eszközkorlátozások](device-restrictions-configure.md)
       -  [Endpoint Protection](endpoint-protection-configure.md)
       -  [Kioszkmód](kiosk-settings.md)
       -  [Email](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Education [Windows 10](education-settings-configure.md) és [iOS](wi-fi-settings-ios.md) rendszerhez
       -  [Windows 10 kiadásfrissítés](edition-upgrade-configure-windows-10.md)
       -  [iOS-es frissítési szabályzatok](software-updates-ios.md)
       -  [Tanúsítványok](certificates-configure.md)
       -  [Windows Információvédelem](windows-information-protection-configure.md)
       -  [Egyéni](custom-settings-configure.md)

     ![A Profil létrehozása képernyőképe](./media/create-device-profile.png)

4. Ha kész, válassza a **Létrehozás** lehetőséget.

Ekkor létrejön a profil, és megjelenik a listában.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

---
title: Eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-ban eszközprofilokat adhat hozzá és konfigurálhat, így megadhatja a platform típusát és konfigurálhatja a beállításokat az Azure Portalon.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d36f1c36656be6fab8a9566d34b946f80450e97
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389487"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Eszközprofil létrehozása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.

2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.

3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza ki a platform típusát:  

       - **Android**
       - **Vállalati Android**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 és újabb**
       - **Windows 10 és újabb**

   - **Profil típusa**: Válassza ki a létrehozni kívánt. A lista a választott platformtól függ.
   - **Beállítások**: Az alábbi cikkek ismertetik az egyes profiltípusok beállításait:

       -  [Eszközfunkciók](device-features-configure.md)
       -  [Eszközkorlátozások](device-restrictions-configure.md)
       -  [Endpoint Protection](endpoint-protection-configure.md)
       -  [Identity protection](identity-protection-configure.md)  
       -  [Kioszkmód](kiosk-settings.md)
       -  [E-mail](email-settings-configure.md)
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

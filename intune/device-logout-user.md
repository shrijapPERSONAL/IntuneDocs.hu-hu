---
title: "Intune által felügyelt iOS-eszköz felhasználójának kijelentkeztetése"
titleSuffix: Intune on Azure
description: "Ez a cikk ismerteti, hogy hogyan lehet kijelentkeztetni egy Intune által felügyelt iOS-eszköz aktuális felhasználóját.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1de2069b7b25ee5e5c21a8e4caa7512f13d4ca0e
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Intune által felügyelt iOS-eszköz aktuális felhasználójának kijelentkeztetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Az **Aktuális felhasználó kijelentkeztetése** művelet kijelentkezteti az aktuális felhasználót egy olyan megosztott használatú iPad-eszközről, amelyen [iOS-es oktatási profil](education-settings-configure-ios.md) felügyeli az iOS-es Osztályterem alkalmazást. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-logout-the-current-user"></a>Aktuális felhasználó kijelentkeztetése

1.  Jelentkezzen be az Azure Portalra.
2.  Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4.  Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5.  A felügyelt eszközök listájából válasszon ki egy iOS-eszközt, majd kattintson az **Aktuális felhasználó kijelentkeztetése** távoli eszközműveletre.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

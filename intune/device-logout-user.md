---
title: "Intune által felügyelt iOS-eszköz felhasználójának kijelentkeztetése"
titlesuffix: Azure portal
description: "Ez a cikk ismerteti, hogy hogyan lehet kijelentkeztetni egy Intune által felügyelt iOS-eszköz aktuális felhasználóját.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e59eee3660f56fdd967237563e69324b8307e3a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
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

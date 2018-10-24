---
title: iOS-eszköz felhasználójának kijelentkeztetése
titlesuffix: Microsoft Intune
description: Ez a cikk ismerteti, hogy hogyan lehet kijelentkeztetni egy Intune által felügyelt iOS-eszköz aktuális felhasználóját.”
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d80d7a05dc01298dc7bc347098cf85fbdfc3689f
ms.sourcegitcommit: 2795255e89cbe97d0b17383d446cca57c7335016
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47403493"
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Intune által felügyelt iOS-eszköz aktuális felhasználójának kijelentkeztetése


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Aktuális felhasználó kijelentkeztetése** művelet kijelentkezteti egy megosztott iPad aktuális felhasználóját. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-log-out-the-current-user"></a>Aktuális felhasználó kijelentkeztetése

1.  Jelentkezzen be az Azure Portalra.
2.  Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4.  Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5.  A felügyelt eszközök listájából válasszon ki egy iOS-eszközt, majd kattintson az **Aktuális felhasználó kijelentkeztetése** távoli eszközműveletre.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

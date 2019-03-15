---
title: A Microsoft Intune által felügyelt iOS-eszköz felhasználójának eltávolítása
titlesuffix: ''
description: Ismerje meg, hogyan távolíthat el felhasználót egy Intune által felügyelt, megosztott iOS-eszközről.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7265ee47beb6fc9d82410044a535a291466365af
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57399191"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Felhasználó eltávolítása megosztott iOS-eszközről


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A **Felhasználó eltávolítása** művelettel törölheti a kiválasztott felhasználót az iPad eszköz helyi gyorsítótárából. Az iPad eszközt úgy kell beállítani egy [iOS oktatási profillal](education-settings-configure-ios.md), hogy kezelje az iOS Osztályterem alkalmazást. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="remove-a-user"></a>Felhasználó eltávolítása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy iOS-eszközt.
6. Az eszköz ablaktábláján válassza a **Felhasználók** lehetőséget.
7. A listán a jobb gombbal kattintson az eltávolítani kívánt felhasználóra, majd kattintson a **Felhasználó eltávolítása** elemre.

## <a name="next-steps"></a>További lépések

- A **Felhasználók eltávolítása** művelet állapotának megtekintéséhez válassza az **Eszközök** > **Eszközműveletek** lehetőséget.

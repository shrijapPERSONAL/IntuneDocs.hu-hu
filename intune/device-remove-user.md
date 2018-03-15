---
title: "A Microsoft Intune által felügyelt iOS-eszköz felhasználójának eltávolítása"
titlesuffix: 
description: "Ismerje meg, hogyan távolíthat el felhasználót egy Intune által felügyelt, megosztott iOS-eszközről."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b2321de0c0541111fdf6f18345bd952ca8b5448
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Felhasználó eltávolítása megosztott iOS-eszközről


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azoknak a megosztott iPad- eszközöknek a helyi gyorsítótárából, amelyeken [iOS-es oktatási profil](education-settings-configure-ios.md) kezeli az iOS-es Osztályterem alkalmazást, a **Felhasználó eltávolítása** művelettel távolítható el egy kiválasztott felhasználó. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-remove-a-user"></a>Felhasználó eltávolítása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy iOS-eszközt.
6. Az eszköz paneljén kattintson a **Felhasználók** elemre.
7. A listán jobb gombbal kattintson az eltávolítani kívánt felhasználóra, majd kattintson a **Felhasználó eltávolítása** elemre.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

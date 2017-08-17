---
title: "Intune által felügyelt iOS-eszköz felhasználójának eltávolítása"
titleSuffix: Intune on Azure
description: "Ismerje meg, hogyan távolíthat el felhasználót egy Intune által felügyelt, megosztott iOS-eszközről.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f5898d0f2cc167a66026dd108d6bbd54c39cec
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Felhasználó eltávolítása Intune által felügyelt, megosztott iOS-eszközről


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azoknak a megosztott iPad- eszközöknek a helyi gyorsítótárából, amelyeken [iOS-es oktatási profil](education-settings-configure-ios.md) kezeli az iOS-es Osztályterem alkalmazást, a **Felhasználó eltávolítása** művelettel távolítható el egy kiválasztott felhasználó. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-remove-a-user"></a>Felhasználó eltávolítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy iOS-eszközt.
6. Az eszköz paneljén kattintson a **Felhasználók** elemre.
7. A listán jobb gombbal kattintson az eltávolítani kívánt felhasználóra, majd kattintson a **Felhasználó eltávolítása** elemre.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

---
title: "Eszközök PIN-kódjainak átállítása és eltávolítása az Intune-ban"
titlesuffix: Azure portal
description: "Útmutató az Intune által kezelt eszközök PIN-kódjainak átállításához és eltávolításához."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e1496d24fd9d3bb636a4eab00c254b753210f63
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Az Intune által kezelt eszközök PIN-kódjainak átállítása és eltávolítása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A *törlés* és az *eltávolítás* kifejezések a cikkben felcserélhetők egymással.

A **PIN-kód eltávolítása** művelet új PIN-kódot hoz létre az eszközhöz. A kód az <*eszköznév*> **Áttekintés** panelen jelenik meg.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – támogatott a Windows Phone 8.1-es verziótól a Windows 10 alkotói frissítés nem Azure AD-hoz csatlakoztatott verziójáig, illetve a Windows 10 alkotói frissítés és újabb verziói esetén
- iOS – támogatott
- macOS – nem támogatott
- Android – az Android 7-nél régebbi verziók esetén támogatott. Az Android for Work nem támogatott.

## <a name="how-to-reset-a-passcode"></a>A PIN-kód alaphelyzetbe állítása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, és válassza a **...Továbbiak** lehetőséget, majd a **PIN-kód eltávolítása** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

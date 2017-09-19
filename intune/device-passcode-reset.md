---
title: "Eszköz PIN-kódjának alaphelyzetbe állítása az Intune-nal"
titlesuffix: Azure portal
description: "Útmutató az Intune-nal kezelt eszközök PIN-kódjának alaphelyzetbe állításához.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3defec3624944918d14b9c4527487c368c487dd6
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Az Intune által kezelt eszközök PIN-kódjának alaphelyzetbe állítása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Új PIN-kód** művelet új PIN-kódot generál az eszközhöz. A kód az <*eszköznév*> **Áttekintés** panelen jelenik meg.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – támogatott a Windows Phone 8.1-es verziótól a Windows 10 alkotói frissítés nem Azure AD-hoz csatlakoztatott verziójáig, illetve a Windows 10 alkotói frissítés és újabb verziói esetén
- iOS – támogatott
- macOS – nem támogatott
- Android – az Android 7-nél régebbi verziók esetén támogatott. Az Android for Work nem támogatott.

## <a name="how-to-reset-a-passcode"></a>A PIN-kód alaphelyzetbe állítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza a távoli **Új PIN-kód** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

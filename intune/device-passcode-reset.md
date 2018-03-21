---
title: "Eszközök PIN-kódjának visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs"
description: "A PIN-kód eltávolítása kódművelettel eltávolíthatja vagy visszaállíthatja a PIN-kódot az Intune-nal kezelt vagy figyelt eszközökön."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ha új PIN-kódot szeretne létrehozni egy eszközhöz, használja a  **PIN-kód eltávolítása** műveletet.

## <a name="supported-platforms"></a>Támogatott platformok

- A Windows Phone 8.1-es verziótól a Windows 10 alkotói frissítés nem Azure AD-hoz csatlakoztatott verziójáig, valamint Windows 10 alkotói frissítés és újabb
- iOS
- Az Android 7-nél régebbi verziói

Ez a funkció **nem** támogatott a következő rendszereken:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Új PIN-kód kérése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
3. Kattintson az **Eszközök**, majd a **Minden eszköz** elemre.
4. A felügyelt eszközök listájából válassza ki az eszközt, és válassza a **...Továbbiak** lehetőséget, majd a **PIN-kód eltávolítása** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

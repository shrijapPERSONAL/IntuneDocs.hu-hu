---
title: "Céges adatok eltávolítása az Intune-ban felügyelt eszközökről"
titleSuffix: Intune on Azure
description: "Ismerje meg, hogyan távolíthatja el csak a céges adatokat az Intune-ban felügyelt eszközökről."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b0cc7d62770057ff9df5a36e6e5df58b29430534
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Céges adatok eltávolítása az Intune-ban felügyelt eszközökről


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Céges adatok eltávolítása** eszközművelet csak a céges adatokat távolítja el az Intune által felügyelt eszközökről. A művelet személyes adatokat nem távolít el az eszközről. Az eltávolítást követően az eszköz már nem áll az Intune felügyelete alatt, és nem fér hozzá a vállalati erőforrásokhoz.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – támogatott (nem támogatott az Azure Active Directory szolgáltatáshoz csatlakoztatott Windows-eszközökön)
- Windows Phone – támogatott
- iOS – támogatott
- macOS – támogatott
- Android – támogatott

## <a name="how-to-remove-company-data"></a>A céges adatok eltávolítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. Az eszközök listájából válassza ki az eszközt, majd válassza a **Céges adatok eltávolítása** távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

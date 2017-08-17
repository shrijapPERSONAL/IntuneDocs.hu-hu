---
title: "Eszközök gyári alapállapotra való visszaállítása az Intune-nal"
titleSuffix: Intune on Azure
description: "Ebből a témakörből megtudhatja, hogyan állíthatja vissza az Intune-nal felügyelt eszközöket gyári alapállapotukba."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44f69179f76c8d5eeca1594485ca3a9c1b036188
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Az Intune-nal felügyelt eszközök gyári beállításainak visszaállítása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Gyári beállítások visszaállítása** funkció visszaállítja az eszköz alapbeállításait. Az eszközt a továbbiakban nem felügyeli az Intune, és a vállalati és a személyes adatok is törlődnek róla. Ez a művelet nem vonható vissza.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows - A Windows 8.1-es és újabb verziói esetén támogatott (nem EAS-ban kezelt eszközök)
- Windows Phone – támogatott
- iOS – támogatott
- macOS – nem támogatott
- Android – támogatott (az Android for Work nem támogatott)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Az eszköz gyári beállításainak visszaállítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza a **Gyári beállítások visszaállítása** nevű távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.


---
title: Eszközök újraindítása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Újraindíthatja a Windows- és iOS-eszközöket a Microsoft Intune használatával az Azure Portalon az Újraindítás távoli művelettel.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b68d7eda57d50c3a1cb55979590e8b07d9daf50
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37904948"
---
# <a name="remotely-restart-devices-with-intune"></a>Az eszközök távoli újraindítása az Intune-nal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **újraindítási** eszközművelettel a kiválasztott eszköz újraindítható. Az eszköz tulajdonosa nem kap automatikus értesítést az újraindításról, ezért a munkája elveszhet.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – A Windows 8.1-es és újabb verziói esetén támogatott
- Windows Phone – A Windows Phone 8.1-es és újabb verziói esetén támogatott
- Androidos kioszk módú eszközök – támogatottak
- iOS – támogatott

    > [!Note]  
    > Ehhez a parancshoz felügyelt eszközökre és az **Eszközzárolás** hozzáférési jogosultságra van szükség. Az eszköz azonnal újraindul. Újraindítás után a PIN-kóddal zárolt iOS-eszközök nem csatlakoznak újra a Wi-Fi-hálózathoz. Újraindítás után az eszköz lehet, hogy nem fog tudni kommunikálni a kiszolgálóval.
- macOS – nem támogatott
- Androidos és androidos munkahelyi profillal rendelkező eszközök – nem támogatottak

## <a name="restart-a-device"></a>Eszköz újraindítása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget.
4. A kezelt eszközök listájában válasszon ki egy eszközt, válassza a **További** lehetőséget, majd az **Újraindítás** távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

- Az **Újraindítás** eszközművelet állapotának megtekintéséhez válassza az **Eszközök** > **Eszközműveletek** lehetőséget.

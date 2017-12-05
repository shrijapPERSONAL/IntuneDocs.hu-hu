---
title: "Az eszközök távoli újraindítása az Intune-nal"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt az eszközök újraindítási eszközművelettel történő távoli újraindításáról."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dde251482dd951200e5c1a7f19749ee863cd71b4
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-restart-devices-with-intune"></a>Az eszközök távoli újraindítása az Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **újraindítási** eszközművelettel a kiválasztott eszköz újraindítható. Az eszköz tulajdonosa nem kap automatikus értesítést az újraindításról, ezért a munkája elveszhet.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – A Windows 8.1-es és újabb verziói esetén támogatott
- Windows Phone – A Windows Phone 8.1-es és újabb verziói esetén támogatott
- iOS – támogatott

    > [!Note]  
    > Ehhez a parancshoz felügyelt eszközökre és az **Eszközzárolás** hozzáférési jogosultságra van szükség. Az eszköz azonnal újraindul. A PIN-kóddal zárolt iOS-eszközök nem csatlakoznak újra a Wi-Fi-hálózatokra az újraindítás után, így előfordulhat, hogy ilyen esetekben nem tudnak kommunikálni a kiszolgálóval.
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-restart-a-device"></a>Eszköz újraindítása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza a távoli **újraindítási** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

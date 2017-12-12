---
title: "Felügyelt eszközök távoli zárolása"
titlesuffix: Azure portal
description: "Útmutató az Intune-nal felügyelt eszközök távoli zárolásához.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Felügyelt eszközök távoli zárolása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Távoli zárolás** eszköz zárolja a kijelölt eszközt. Az eszköz zárolását a PIN-kódjával vagy jelszavával kell feloldania a tulajdonosnak. Csak olyan eszköz zárolható távolról, amelyhez PIN-kód vagy jelszó van megadva.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – A Windows Phone 8.1-es és újabb verziói esetén támogatott
- iOS – támogatott
- macOS – támogatott

    > [!Note]  
    > Adjon meg egy 6 számjegyből álló helyreállítási PIN-kódot. A zárolt eszköz **Az eszköz áttekintése** panelén megjelenik a PIN-kód mindaddig, amíg az eszköznek nem kell egy másik műveletet végrehajtania.
- Android – támogatott

## <a name="how-to-remote-lock-a-device"></a>Eszköz távoli lezárása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza a **Távoli zárolás** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

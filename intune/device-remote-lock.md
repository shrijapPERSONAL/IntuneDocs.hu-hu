---
title: "Felügyelt eszközök távoli zárolása"
titlesuffix: Azure portal
description: "Útmutató az Intune-nal felügyelt eszközök távoli zárolásához.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Felügyelt eszközök távoli zárolása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Távoli zárolás** eszköz zárolja a kijelölt eszközt. Az eszköz zárolását a PIN-kódjával vagy jelszavával kell feloldania a tulajdonosnak. Csak olyan eszköz zárolható távolról, amelyhez PIN-kód vagy jelszó van megadva.

## <a name="supported-platforms"></a>Támogatott platformok

A távoli zárolás az alábbi platformokon van támogatva:

|Platform|Támogatás állapota|
|---|---|
|Android|Igen|
|iOS|Igen|
|macOS|Igen|
|Windows 10|Igen|
|Windows 10 mobil verzió|Igen|
|Windows Phone|Igen, a Windows Phone 8.1-es és újabb verzióihoz|

> [!NOTE]  
> MacOS eszközökhöz egy hatjegyű helyreállítási PIN-kódot kell megadnia. A zárolt eszköz **Az eszköz áttekintése** panelén megjelenik a PIN-kód mindaddig, amíg az eszköznek nem kell egy másik műveletet végrehajtania.

## <a name="how-to-remote-lock-a-device"></a>Eszköz távoli lezárása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza a **Távoli zárolás** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.

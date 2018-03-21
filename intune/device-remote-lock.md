---
title: "Eszközök zárolása az Azure-beli Microsoft Intune-ban | Microsoft Docs"
description: "A Microsoft Intune-ban elérhető Távoli zárolás művelettel zárolhatja a PIN-kóddal vagy jelszóval védett eszközöket."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Eszközök távoli zárolása az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Távoli zárolás** művelet zárolja az eszközt. A zárolás feloldásához az eszköz tulajdonosának be kell írnia a PIN-kódját. Csak olyan eszköz zárolható távolról, amelyhez PIN-kód vagy jelszó van megadva. A PIN-kód vagy jelszó nélküli eszközöket nem tudja távolról zárolni.

## <a name="supported-platforms"></a>Támogatott platformok

A távoli zárolás az alábbi platformokon van támogatva:

- Android
- iOS
- macOS
- Windows 10 mobil verzió
- Windows Phone 8.1 és újabb verziók

**Nem** támogatott az alábbi platformokon:
- Windows 10 asztali verzió

> [!NOTE]
> MacOS eszközökhöz egy hatjegyű helyreállítási PIN-kódot kell megadnia. A zárolt eszköz **Az eszköz áttekintése** panelén látható marad a PIN-kód mindaddig, amíg az eszköznek nem kell egy másik műveletet végrehajtania.

## <a name="remote-lock-a-device"></a>Egy eszköz távoli zárolása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. Válasszon egy eszközt az eszközlistáról, majd válassza a **Távoli zárolás** műveletet.

## <a name="next-steps"></a>További lépések

A művelet állapotának megtekintéséhez nyissa meg az **Eszközműveletek** panelt (Microsoft Intune > Eszközök). Az eszközök kezeléséhez rendelkezésre álló további műveletekről a [Rendelkezésre álló műveletek](device-management.md) című témakörben tájékozódhat.
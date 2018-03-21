---
title: "Elveszett iOS-eszközök megkeresése az Azure-beli Microsoft Intune-ban | Microsoft Docs"
description: "A Microsoft Intune Eszköz megkeresése funkciójával meghatározhatja az elveszett vagy ellopott iOS-eszközök helyét. A funkció használatakor emellett biztonsági és adatvédelmi információkat is kaphat."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Elveszett vagy ellopott iOS-eszközök megkeresése az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszköz megkeresése** művelettel megjelenítheti térképen az elveszett vagy ellopott iOS-eszközök helyét. Ez a funkció csak felügyelt módban lévő, készülékregisztrációs programban (DEP) regisztrált, céges tulajdonú iOS-eszközökön használható. A művelet használata előtt győződjön meg róla, hogy az eszközt [Elveszett módba](device-lost-mode.md) állította.

## <a name="supported-platforms"></a>Támogatott platformok

- iOS 9.3 és újabb verziók

Ez a funkció **nem** támogatott a következő rendszereken: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Elveszett vagy ellopott eszköz megkeresése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. A felügyelt eszközök listájából válassza ki az eszközt, és válassza a **...Továbbiak** lehetőséget, majd az **Eszköz megkeresése** távoli eszközműveletet.
5. Miután a rendszer megtalálta az eszközt, megjeleníti annak helyét az **Eszköz megkeresése** panelen.
    ![Eszköz megkeresése az Azure-beli Intune-nal](./media/locate-device.png)

>[!NOTE]
>Adatvédelmi okokból korlátozva van, hogy mennyire nagyíthatja a térképet.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Az Elveszett eszköz módhoz és az eszközkeresési műveletekhez kapcsolódó biztonsági és adatvédelmi információk
- A művelet elindításáig a rendszer semmilyen információt nem küld az Intune-nak az eszköz helyéről.
- Az eszközkeresési művelet használatakor a rendszer az eszköz szélességi és hosszúsági koordinátáit küldi el az Intune-nak, és ezeket az adatokat jeleníti meg az Azure Portalon.
- A rendszer 24 óráig tárolja az adatokat, majd törli azokat. A helyadatokat manuálisan nem lehet eltávolítani.
- A helyadatok tároláskor és továbbításkor egyaránt titkosítva vannak.
- Az Elveszett eszköz mód konfigurálásakor megadhat egy egyéni üzenetet, mely megjelenik az eszköz zárolási képernyőjén. Ebben az üzenetben mindenképp célszerű pontosan jeleznie, hogy az eszközt megtaláló személy miként tudja visszaszolgáltatni az eszközt a cégének.

## <a name="next-steps"></a>További lépések

Az Eszköz megkeresése művelet állapotát az **Eszközök** > **Eszközműveletek** lehetőség választásával tekintheti meg.

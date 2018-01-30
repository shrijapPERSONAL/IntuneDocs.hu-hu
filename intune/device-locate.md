---
title: "Elveszett iOS-eszközök megkeresése az Intune-nal"
titlesuffix: Azure portal
description: "Megtudhatja, hogyan keresse meg az elveszett vagy ellopott iOS-eszközöket az Intune-ban.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90b1321c0df49f446bfdeccbacdfd5642396dacd
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Elveszett vagy ellopott iOS-eszközök megkeresése az Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszköz megkeresése** eszközművelet használatával jelenítheti meg az elveszett vagy ellopott iOS-eszköz helyét a térképen. A funkció csak felügyelt módban lévő, DEP-pel regisztrált, céges tulajdonban lévő iOS-eszközökön használható. A művelet használata előtt az eszközt [Elveszett eszköz módba](/intune-azure/manage-devices/lost-mode.md) kell állítani.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióin támogatott (elveszett eszköz módban), felügyelt és vállalati tulajdonú eszközök esetén
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Elveszett vagy ellopott eszköz megkeresése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza az **Eszköz megkeresése** távoli eszközműveletet.
6. Miután a rendszer megtalálta az eszközt, megjeleníti annak helyét az **Eszköz megkeresése** panelen.
    ![Eszköz megkeresése panel](./media/locate-device.png)

>[!NOTE]
>Adatvédelmi okokból korlátozva van, hogy mennyire nagyíthatja a térképet.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Az Elveszett eszköz módhoz és az eszközkeresési műveletekhez tartozó biztonsági és adatvédelmi tudnivalók
- A művelet elindításáig a rendszer semmilyen információt nem küld az Intune-nak az eszköz helyéről.
- Az eszközkeresési művelet használatakor a rendszer az eszköz szélességi és hosszúsági koordinátáit küldi el az Intune-nak, és ezeket az adatokat jeleníti meg az Azure Portalon.
- A rendszer 24 óráig tárolja az adatokat, majd törli azokat. A helyadatokat manuálisan nem lehet eltávolítani.
- A helyadatok tároláskor és továbbításkor egyaránt titkosítva vannak.
- Az Elveszett eszköz mód konfigurálásakor ajánlott a zárolási képernyőn megjelenő üzenetben az eszköz visszajuttatásához segítséget nyújtó információkat feltüntetni.


## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.
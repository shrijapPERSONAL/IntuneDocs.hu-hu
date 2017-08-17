---
title: "Az iOS Elveszett eszköz módjának aktiválása az Intune-nal"
titleSuffix: Intune on Azure
description: "Megtudhatja, hogyan aktiválhatja az elveszett eszköz módját az elveszett vagy ellopott iOS-eszközökön az Intune használatával.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ed792011de9109dd415ba2fac3c9428e955e5e7
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/10/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Elveszett eszköz mód aktiválása iOS-eszközökön


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Elveszett eszköz mód** eszközművelet segítségével engedélyezheti az elveszett eszköz módot elveszett vagy ellopott iOS-es eszközökön. Az eszköz elvesztése esetére megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS - az iOS 9.3-as és újabb verzióin támogatott, felügyelt és vállalati tulajdonú eszközökön
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-activate-lost-mode"></a>Az Elveszett eszköz mód aktiválása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki az eszközt, majd válassza az **Elveszett eszköz mód** távoli eszközműveletet.
6. Engedélyezze az Elveszett eszköz módot az **Elveszett eszköz mód** panelen. Ezt követően írja be a megjelenítendő üzenetet, és szükség esetén adjon meg egy kapcsolattartói telefonszámot is.
7. Kattintson az **OK**gombra.

Az Elveszett eszköz mód engedélyezésével teljesen letiltja az eszköz használatát. A végfelhasználó az Elveszett eszköz mód kikapcsolásáig nem tud hozzáférni az eszközhöz. Ha az Elveszett eszköz mód engedélyezve van, az **Eszköz megkeresése** művelet használatával derítheti ki, hogy merre található az eszköz.
Az Elveszett eszköz mód csak felügyelt módban lévő, vállalati tulajdonú iOS-eszközök esetén használható.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Az Elveszett eszköz módhoz és az eszközkeresési műveletekhez tartozó biztonsági és adatvédelmi tudnivalók
- A művelet elindításáig a rendszer semmilyen információt nem küld az Intune-nak az eszköz helyéről.
- Az eszközkeresési művelet használatakor a rendszer az eszköz szélességi és hosszúsági koordinátáit küldi el az Intune-nak, és ezeket az adatokat jeleníti meg az Azure Portalon.
- A rendszer 24 óráig tárolja az adatokat, majd törli azokat. A helyadatokat manuálisan nem lehet eltávolítani.
- A helyadatok tároláskor és továbbításkor egyaránt titkosítva vannak.
- A zárolási képernyőn megjelenő üzenetben ajánlott feltüntetni az eszköz visszajuttatásához segítséget nyújtó információkat.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.


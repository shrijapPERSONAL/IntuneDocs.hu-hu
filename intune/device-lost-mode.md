---
title: "Az iOS Elveszett eszköz módjának aktiválása az Azure-beli Microsoft Intune-ban | Microsoft Docs"
description: "Az Elveszett eszköz mód bekapcsolásakor megadhat egy egyéni üzenetet a Microsoft Intune-nal, mely megjelenik az elveszett vagy ellopott iOS-eszköz zárolási képernyőjén. Emellett az Elveszett eszköz mód használatakor biztonsági és adatvédelmi információkat is kaphat."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47d6314dfaed546e5b4cff7f93a5540ba512bde9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Az Elveszett eszköz mód bekapcsolása egy iOS-eszközön az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Elveszett eszköz mód** eszközművelet segítségével engedélyezheti az elveszett eszköz módot elveszett vagy ellopott iOS-es eszközökön. Az eszköz elvesztése esetére megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén. Az Elveszett eszköz mód csak felügyelt módban lévő, vállalati tulajdonú iOS-eszközök esetén használható.

## <a name="supported-platforms"></a>Támogatott platformok

- iOS 9.3 és újabb verziók

Ez a funkció **nem** támogatott a következő rendszereken: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Az Elveszett mód engedélyezése

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. A felügyelt eszközök listájából válassza ki az eszközt, és válassza a **...Továbbiak** lehetőséget, majd az **Elveszett eszköz mód** távoli eszközműveletet.
5. Az **Elveszett eszköz** területen aktiválja a funkciót. Ezután írja be a megjelenítendő üzenetet, és adjon meg egy kapcsolatfelvételi telefonszámot.
6. A módosítások mentéséhez válassza az **OK** gombot.

Az Elveszett eszköz mód engedélye teljesen letiltja az eszköz használatát. A végfelhasználó az Elveszett eszköz mód kikapcsolásáig nem tud hozzáférni az eszközhöz. Ha az Elveszett eszköz mód engedélyezve van, az [Eszköz megkeresése](device-locate.md) művelettel meghatározhatja az eszköz földrajzi helyét.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Az Elveszett eszköz módhoz és az eszközkeresési műveletekhez tartozó biztonsági és adatvédelmi tudnivalók
- A művelet elindításáig a rendszer semmilyen információt nem küld az Intune-nak az eszköz helyéről.
- Az eszközkeresési művelet használatakor a rendszer az eszköz szélességi és hosszúsági koordinátáit küldi el az Intune-nak, és ezeket az adatokat jeleníti meg az Azure Portalon.
- A rendszer 24 óráig tárolja az adatokat, majd törli azokat. A helyadatokat manuálisan nem lehet eltávolítani.
- A helyadatok tároláskor és továbbításkor egyaránt titkosítva vannak.
- A zárolási képernyőn megjelenítendő üzenet megadásakor mindenképp jelezze, hogy miként lehet visszaszolgáltatni az elveszett eszközt.

## <a name="next-steps"></a>További lépések

Az Elveszett eszköz mód aktiválásának állapotát az **Eszközök** > **Eszközműveletek** lehetőség választásával tekintheti meg.
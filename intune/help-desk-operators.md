---
title: "Ügyfélszolgálati hibaelhárítási portál"
titleSuffix: Intune on Azure
description: "Az ügyfélszolgálat munkatársai a hibaelhárítási portál segítségével oldják meg a felhasználók műszaki problémáit"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>A felhasználók segítése a Microsoft Intune hibaelhárítási portáljával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A hibaelhárítási portál segítségével az ügyfélszolgálat munkatársai és az Intune-rendszergazdák felhasználói információkat tekinthetnek meg a felhasználói segítségkérések teljesítéséhez. Az ügyfélszolgálattal rendelkező cégek **Ügyfélszolgálat** jogosultságot oszthatnak ki egy felhasználói csoport részére, amely a továbbiakban a Hibaelhárítás panel segítségével nyújthat támogatást a felhasználóknak.

Például ha egy felhasználó Intune-nal kapcsolatos műszaki problémával fordul az ügyfélszolgálathoz, az ügyfélszolgálat munkatársa megadja a felhasználó nevét. Az Intune hasznos adatokat jelenít meg, amelyek számos 1. szintű probléma megoldásában segíthetnek, mint például:
- Felhasználó állapota
- Hozzárendelések
- Sikertelen alkalmazástelepítés
- Megfelelőségi problémák
- Az eszköz nem válaszol
-   Az eszközön nem működnek a VPN- vagy Wi-Fi-beállítások
-   Alkalmazástelepítési hiba


## <a name="add-help-desk-operators"></a>Ügyfélszolgálati operátorok felvétele
Intune-rendszergazdaként hozzárendelheti az Ügyfélszolgálat szerepkört egy felhasználói csoporthoz. A csoport tagjai a felügyeleti portál segítségével elháríthatják a felhasználók problémáit. Minden ügyfélszolgálati munkatársnak Intune-licenccel kell rendelkeznie az Intune-portál eléréséhez. Ismerje meg, [hogyan oszthat ki Intune-licenceket](licenses-assign.md).

Ügyfélszolgálati felhasználók hozzáadása:
1. [Felhasználó hozzáadása az Intune-hoz](users-add.md) szükség esetén
2. [Ügyfélszolgálati csoport létrehozása](groups-add.md) és felhasználók hozzáadása a csoporthoz
3. [RBAC Ügyfélszolgálati Munkatárs szerepkör hozzárendelése](role-based-access-control.md#built-in-roles) vagy [egyéni szerepkör létrehozása](role-based-access-control.md#custom-roles) a következő engedélyekkel:
  - MobileApps (mobilalkalmazások): Olvasás
  - ManagedApps (felügyelt alkalmazások): Olvasás
  - ManagedDevices (felügyelt eszközök): Olvasás
  - Organization (Munkahely): Olvasás
  - DeviceCompliancePolices: Olvasás
  - DeviceConfigurations: Olvasás

  ![Az Intune-portál képernyőképe a kiemelt Intune-szerepkörökkel és a beépített szerepkörök listájával, köztük a Help Desk Operator (Ügyfélszolgálati munkatárs) szerepkörrel](./media/help-desk-user-add.png)

4. **Szolgáltatás-rendszergazdaként** [rendszergazdai engedélyek kiosztásával](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) engedélyezze az ügyfélszolgálati munkatársaknak a szolgáltatás állapotának megtekintését és az Intune-támogatási jegyek megnyitását. Ne adjon **Intune-beli szolgáltatás-rendszergazda** engedélyt, mert ez a címtárszerepkör több jogosultsággal rendelkezik, mint amennyire az ügyfélszolgálati munkatársaknak szükségük van.

## <a name="access-the-troubleshooting-portal"></a>A hibaelhárítási portál elérése

Az ügyfélszolgálati munkatársak és az Intune-rendszergazdák kétféleképpen érhetik el a hibaelhárítási portált:
- A hibaelhárítási portál megtekintéséhez nyissa meg a [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) oldalt egy böngészőben.
  ![A hibaelhárítás konzoljának képernyőképe](./media/help-desk-console.png)
- Jelentkezzen be az Azure Portalon, válassza a **More Services (további szolgáltatások** > **Figyelés + Felügyelet** > **Intune**, majd a **Súgó és támogatás** > **Hibaelhárítás** lehetőséget.

A **Felhasználó kijelölése** elemre kattintva tekintse meg a felhasználót és adatait.

![Képernyőkép: az Intune Hibaelhárítás feladata a Felhasználó kijelölése hivatkozással](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>A hibaelhárítási portál használata

A hibaelhárítási portálon a **Felhasználó kijelölése** hivatkozással lehet megnézni az egyes felhasználók adatait. A felhasználói adatok segítséget nyújtanak a felhasználók és eszközeik aktuális állapotának áttekintésében. A hibaelhárítási portál a következő hibaelhárítási részleteket jeleníti meg:
- **Fiók állapota**
- **Felhasználó állapota**
- **Eszközök** az eszközműveletekkel együtt
- **Csoporttagság**
- **Alkalmazásvédelmi állapot**

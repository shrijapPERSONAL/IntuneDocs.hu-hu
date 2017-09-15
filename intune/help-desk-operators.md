---
title: "Ügyfélszolgálati hibaelhárítási portál"
titlesuffix: Azure portal
description: "Az ügyfélszolgálat munkatársai a hibaelhárítási portál segítségével oldják meg a felhasználók műszaki problémáit"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 14b47727428fcd6a16f9960e21f70ee64c7757d1
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Segítségnyújtás a felhasználóknak a hibaelhárítási portál használatával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A hibaelhárítási portál segítségével az ügyfélszolgálat munkatársai és az Intune-rendszergazdák felhasználói információkat tekinthetnek meg a felhasználói segítségkérések teljesítéséhez. Az ügyfélszolgálattal rendelkező cégek **Ügyfélszolgálat** jogosultságot oszthatnak ki egy felhasználói csoport részére, amely a továbbiakban a Hibaelhárítás panel segítségével nyújthat támogatást a felhasználóknak.

Például ha egy felhasználó Intune-nal kapcsolatos műszaki problémával fordul az ügyfélszolgálathoz, az ügyfélszolgálat munkatársa megadja a felhasználó nevét. Az Intune hasznos adatokat jelenít meg, amelyek számos 1. szintű probléma megoldásában segíthetnek, mint például:
- Felhasználó állapota
- Hozzárendelések
- Megfelelőségi problémák
- Az eszköz nem válaszol
-   Az eszközön nem működnek a VPN- vagy Wi-Fi-beállítások
-   Alkalmazástelepítési hiba

## <a name="add-help-desk-operators"></a>Ügyfélszolgálati operátorok felvétele
Intune-rendszergazdaként hozzárendelheti az Ügyfélszolgálat szerepkört egy felhasználói csoporthoz. A csoport tagjai az Azure Portal webhelyen elháríthatják a felhasználók problémáit. Minden ügyfélszolgálati munkatársnak Intune-licenccel kell rendelkeznie az Azure Portal eléréséhez. Ismerje meg, [hogyan oszthat ki Intune-licenceket](licenses-assign.md).

Ügyfélszolgálati felhasználók hozzáadása:
1. [Felhasználók hozzáadása az Intune-hoz](users-add.md) szükség esetén.
2. [Ügyfélszolgálati csoport létrehozása](groups-add.md) és felhasználók hozzáadása a csoporthoz.
3. [Végezz el az RBAC ügyfélszolgálati munkatárs szerepkör hozzárendelését](role-based-access-control.md#built-in-roles).

  ![Képernyőkép az Azure Portalról, amelyen ki vannak emelve az Intune-szerepkörök és látható a beépített szerepkörök listája, köztük az Ügyfélszolgálati munkatárs szerepkör is](./media/help-desk-user-add.png) Az ügyfélszolgálati munkatársaknak hozzáférést adhat egy [egyéni szerepkör létrehozásával](role-based-access-control.md#custom-roles) és személyre szabásával is.  Az ügyfélszolgálati munkatársaknak a következő jogosultságokkal kell rendelkezniük a felhasználói problémák hibaelhárításához:
    - MobileApps (mobilalkalmazások): Olvasás
    - ManagedApps (felügyelt alkalmazások): Olvasás
    - ManagedDevices (felügyelt eszközök): Olvasás
    - Organization (Munkahely): Olvasás
    - DeviceCompliancePolices: Olvasás
    - DeviceConfigurations: Olvasás

4. **Szolgáltatás-rendszergazdaként** [rendszergazdai engedélyek kiosztásával](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) engedélyezze az ügyfélszolgálati munkatársaknak a szolgáltatás állapotának megtekintését és az Intune-támogatási jegyek megnyitását. Ne adjon **Intune-beli szolgáltatás-rendszergazda** engedélyt, mert ez a címtárszerepkör több jogosultsággal rendelkezik, mint amennyire az ügyfélszolgálati munkatársaknak szükségük van.

## <a name="access-the-troubleshooting-portal"></a>A hibaelhárítási portál elérése

Az ügyfélszolgálati munkatársak és az Intune-rendszergazdák kétféleképpen érhetik el a hibaelhárítási portált:
- A hibaelhárítási portál megtekintéséhez nyissa meg a [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) oldalt egy böngészőben.
  ![A hibaelhárítás konzoljának képernyőképe](./media/help-desk-console.png)
- Jelentkezzen be az Azure Portalon, válassza a **More Services (további szolgáltatások** > **Figyelés + Felügyelet** > **Intune**, majd a **Súgó és támogatás** > **Hibaelhárítás** lehetőséget.

A **Felhasználó kijelölése** elemre kattintva tekintse meg a felhasználót és adatait.

## <a name="use-the-troubleshooting-portal"></a>A hibaelhárítási portál használata

A hibaelhárítási portálon a **Felhasználó kijelölése** hivatkozással lehet megnézni az egyes felhasználók adatait. A felhasználói adatok segítséget nyújtanak a felhasználók és eszközeik aktuális állapotának áttekintésében. A hibaelhárítási portál a következő hibaelhárítási részleteket jeleníti meg:
- **Fiók állapota**
- **Felhasználó állapota**
- **Eszközök** az eszközműveletekkel együtt
- **Csoporttagság**
- **Alkalmazásvédelmi állapot**

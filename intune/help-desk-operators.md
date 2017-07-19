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
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>A felhasználók segítése a Microsoft Intune hibaelhárítási portáljával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A hibaelhárítási portál segítségével az ügyfélszolgálat munkatársai és az Intune-rendszergazdák felhasználói információkat tekinthetnek meg a felhasználói segítségkérések teljesítéséhez. Az ügyfélszolgálattal rendelkező cégek **Ügyfélszolgálat** jogosultságot oszthatnak ki egy felhasználói csoport részére, amely a továbbiakban a Hibaelhárítás panel segítségével nyújthat támogatást a felhasználóknak.

Például ha egy felhasználó Intune-nal kapcsolatos műszaki problémával fordul az ügyfélszolgálathoz, az ügyfélszolgálat munkatársa megadja a felhasználó nevét. Az Intune ekkor feltünteti azokat a lényeges információkat, amelyek számos 1. szintű probléma megoldásában segíthetnek, mint például a felhasználó állapota, az alkalmazástelepítés hibái, vagy a megfelelőségi problémák. Többek között az alábbi problémák kezelhetők így:
- Az eszköz nem válaszol
-   Az eszközön nem működnek a VPN- vagy Wi-Fi-beállítások
-   Alkalmazástelepítési hiba


## <a name="add-help-desk-operators"></a>Ügyfélszolgálati operátorok felvétele
Az Intune-rendszergazda kétféleképpen oszthat ki ügyfélszolgálati jogosultságot a felhasználóknak:
- Beépített **Ügyfélszolgálat** szerepkör hozzárendelése
- Egyéni szerepkör létrehozása és hozzárendelése

## <a name="assign-help-desk-operator-role"></a>Ügyfélszolgálat-szerepkör hozzárendelése
Intune-rendszergazdaként hozzárendelheti az Ügyfélszolgálat szerepkört egy felhasználói csoporthoz. Ennek a csoportnak a tagjai használhatják a felügyeleti portált. Minden ügyfélszolgálati munkatársnak Intune-licenccel kell rendelkeznie az Intune-portál eléréséhez. Ismerje meg, [hogyan oszthat ki Intune-licenceket](licenses-assign.md).

1. Intune-rendszergazdaként jelentkezzen be az Intune-portálra, és kattintson az **Intune-szerepkörök** elemre.
2. Az **Intune-szerepkörök** feladatnál kattintson az **Ügyfélszolgálati munkatárs** > **Hozzárendelések**, majd a **Hozzárendelés** elemre.
  ![Az Intune-portál képernyőképe a kiemelt Intune-szerepkörökkel és a beépített szerepkörök listájával, köztük a Help Desk Operator (Ügyfélszolgálati munkatárs) szerepkörrel, valamint a kiemelt Hozzárendelések és a piros keretes Hozzárendelés elemmel](./media/help-desk-user-assign.png)
3. Töltse ki a **Hozzárendelés neve** (kötelező) és a **Hozzárendelés leírása** (nem kötelező) mezőt, majd adja meg a **Tagok (csoportok)** és a **Hatókör (csoportok)** beállításokat.
4. Az Ügyfélszolgálati operátor szerepkör tagjai mostantól használhatják a hibaelhárítási portált.

Az Intune-szerepkörökről az [Intune-os szerepkörök (RBAC)](role-based-access-control.md) című témakörben olvashat bővebben.

## <a name="create-a-custom-role-for-troubleshooting"></a>Egyéni szerepkör létrehozása a hibaelhárításhoz
Intune-rendszergazdaként létrehozhat egy egyéni szerepkört, amelynek segítségével a felhasználók a cég igényeinek megfelelő jogosultságokkal használhatják a hibaelhárítási portált. Az Intune-szerepkörökről az [Intune-os szerepkörök (RBAC)](role-based-access-control.md) című témakörben olvashat bővebben.

![Az Intune-portál képernyőképe a kiemelt Intune-szerepkörökkel és a beépített szerepkörök listájával, köztük a Help Desk Operator (Ügyfélszolgálati munkatárs) szerepkörrel](./media/help-desk-user-add.png)

Az Intune-konzol ügyfélszolgálati nézetének használatához az egyéni ügyfélszolgálati szerepkörnek a következő jogosultságokkal kell rendelkeznie:
- MobileApps (mobilalkalmazások): Olvasás
- ManagedApps (felügyelt alkalmazások): Olvasás
- ManagedDevices (felügyelt eszközök): Olvasás
- Organization (Munkahely): Olvasás

## <a name="access-the-troubleshooting-portal"></a>A hibaelhárítási portál elérése

Az ügyfélszolgálati munkatársak és az Intune-rendszergazdák kétféleképpen érhetik el a hibaelhárítási portált:
- A [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) címet böngészőben megnyitva.
- Az Intune-portálon kattintson a **Súgó és támogatás** > **Hibaelhárítás** elemre.

![Képernyőkép: az Intune Hibaelhárítás feladata a Felhasználó kijelölése hivatkozással](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>A hibaelhárítási portál használata

A hibaelhárítási portálon a **Felhasználó kijelölése** hivatkozással lehet megnézni az egyes felhasználók adatait. A felhasználói adatok segítséget nyújtanak a felhasználók és eszközeik aktuális állapotának áttekintésében. A hibaelhárítási portál a következő hibaelhárítási részleteket jeleníti meg:
- **Bérlői állapota**
- **Felhasználó állapota**
- **Eszközök** és eszközműveletek
- **Csoporttagság**
- **Alkalmazásvédelmi állapot**

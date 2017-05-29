---
title: "Ügyfélszolgálati hibaelhárítási portál | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Az ügyfélszolgálat munkatársai a hibaelhárítási portál segítségével oldják meg a felhasználók műszaki problémáit"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6bc22ccaf8c2c98cd67667f8fe30071ccdbc714
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>A felhasználók segítése a Microsoft Intune hibaelhárítási portáljával

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A hibaelhárítási portálon az ügyfélszolgálati munkatársak és az Intune-rendszergazdák áttekinthetik a felhasználók és eszközeik listáját, és az Intune technikai problémáinak elhárítását is elvégezhetik.

## <a name="add-help-desk-operators"></a>Ügyfélszolgálati operátorok felvétele
Az Intune-rendszergazdák kioszthatnak ügyfélszolgálati jogosultságot a felhasználóknak. Az ügyfélszolgálatos felhasználók láthatják az Intune-portált, de a hibaelhárítási feladatokon kívül nem férnek hozzá más felügyeleti feladathoz.

1. Intune-rendszergazdaként jelentkezzen be az [Azure Portalra](https:portal.azure.com), válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet.
2. A bal oldali navigációs ablaktáblában válassza az **Intune-szerepkörök** elemet.
3. Az **Intune-szerepkörök** feladatnál válassza a **Help Desk Operator** (Ügyfélszolgálati operátor), majd a **Hozzárendelés** lehetőséget.
4. Töltse ki a **Hozzárendelés neve** (kötelező) és a **Hozzárendelés leírása** (nem kötelező) mezőt, majd adja meg a **Tagok (csoportok)** és a **Hatókör (csoportok)** beállításokat.
5. Az Ügyfélszolgálati operátor szerepkör tagjai mostantól használhatják a hibaelhárítási portált.

Az Intune-szerepkörökről az [Intune-os szerepkörök (RBAC)](role-based-access-control.md) című témakörben olvashat bővebben.

## <a name="access-the-troubleshooting-portal"></a>A hibaelhárítási portál elérése

Az ügyfélszolgálati munkatársak és az Intune-rendszergazdák kétféleképpen érhetik el a hibaelhárítási portált:
- Az [Azure Portalon](https://portal.azure.com) a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet, majd a bal oldali navigációs ablaktáblában a **Hibaelhárítás** lehetőséget választva. A bal oldali navigációs ablaktáblában további feladatok is láthatók, de nem érhetők el.

![Képernyőkép: az Intune Hibaelhárítás feladata a Felhasználó kijelölése hivatkozással](media/help-desk-user.png)
- A [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) címet böngészőben megnyitva. Ilyenkor csak a hibaelhárítási portál látható.

## <a name="use-the-troubleshooting-portal"></a>A hibaelhárítási portál használata

A hibaelhárítási portálon a **Felhasználó kijelölése** hivatkozással lehet megnézni az egyes felhasználók adatait. A felhasználói adatok segítséget nyújtanak a felhasználók és eszközeik aktuális állapotának áttekintésében. A hibaelhárítási portálon a következő Intune-felhasználói és eszközadatok láthatók:
- Felhasználói fiókok adatai
- Felhasználói csoporttagság
- Eszközadatok

Az ügyfélszolgálati felhasználók távoli feladatokat (például **Távoli zárolást**) is végezhetnek az eszközökön.


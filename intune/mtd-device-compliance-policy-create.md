---
title: "A Mobile Threat Defense eszközmegfelelőségi szabályzatának létrehozása az Intune-ban"
titleSuffix: Intune on Azure
description: "A Mobile Threat Defense eszközmegfelelőségi szabályzatának létrehozása az Intune-ban"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1354d3170f007af2a4bf7f5b2f233a186175c621
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>A Mobile Threat Defense (MTD) eszközmegfelelőségi szabályzatának létrehozása az Intune-nal

Az Intune és az MTD együttes használata segíti a mobileszközökön megjelenő fenyegetések észlelését és a kockázat felmérését. Az Intune eszközmegfelelési szabályzaton belül létrehozhat egy szabályt, amely kockázatfelméréssel állapítja meg az eszköz megfelelőségét. Ezután egy feltételes hozzáférési szabályzattal letilthatja a hozzáférést bizonyos szolgáltatásokhoz az eszközmegfelelés alapján.

## <a name="before-you-begin"></a>Előkészületek

Az MTD beállítása során az MTD-partnerkonzolon már létrehozott egy szabályzatot, amely a fenyegetéseket magas, közepes és alacsony szintű csoportba sorolja. Most be kell állítania a Mobile Threat Defense szintjét az Intune megfelelőségi szabályzatában.

Az MTD-eszközmegfelelési szabályzat előfeltételei:

-   Az MTD és az Intune közötti integráció beállítása

-   Az MTD-összekötő engedélyezése az Intune-ban

## <a name="to-create-a-mtd-device-compliance-policy"></a>Az MTD-eszközmegfelelési szabályzat létrehozásához

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be az Intune-os hitelesítő adataival.

2.  Az **Azure-irányítópulton** válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3.  Ha az **Intune** elemre kattint, megnyílik az **Intune irányítópultja**.

4. Az **Intune-irányítópulton** a **Kezelés** szakaszban kattintson az **Eszköz megfelelősége**, majd a **Szabályzatok** elemre.

5.  Kattintson a **Szabályzat létrehozása** elemre, írja be az eszközmegfelelés **Név** és **Leírás** adatait, kattintson a **Platform** elemre, majd a**Beállítás** szakaszban kattintson a **Konfigurálás** elemre.

6.  A **Megfelelőségi szabályzat** panelen kattintson az **Eszközállapot** lehetőségre.

7.  Az **Eszközállapot** panelen a **Maximálisan elérhető mobileszköz-fenyegetettségi szint használata** alatti legördülő menüből válassza ki a mobilfenyegetés védelmi szintjét.

    a.  **Védett**: Ez a legbiztonságosabb lehetőség. Az eszköz csak akkor fér hozzá a céges erőforrásokhoz, ha semmilyen veszélyforrás nincs rajta. Ha bármilyen veszélyforrás észlelhető, az eszköz nem megfelelőnek minősül.

    b.  **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű veszélyforrások vannak rajta. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.

    c.  **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt veszélyforrások alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.

    d.  **Magas**: Ez a legkevésbé biztonságos beállítás. Nem léptet életbe korlátozást semmilyen veszélyforrás-szinten, és a Skycure Mobile Threat Defense szoftvert csak jelentéskészítésre használja.

8.  Kattintson kétszer az **OK** elemre, majd válassza a **Létrehozás** lehetőséget.

> [!IMPORTANT]
> Ha az Office 365 vagy más szolgáltatások számára feltételes hozzáférési szabályzatokat hoz létre, a rendszer a megfelelőségi értékelés alapján letiltja a nem megfelelő eszközök hozzáférését a céges erőforrásokhoz, amíg az eszközön a fenyegetés el nem hárul.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>MTD-eszközmegfelelőségi szabályzat hozzárendelése

Ha a felhasználókhoz eszközmegfelelőségi szabályzatot kíván rendelni, olyan szabályzatot válasszon, amelyet előzőleg már konfigurált. A meglévő szabályzatokat az **Eszközmegfelelőségi szabályzatok** panelen tekintheti meg.

1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-beli biztonsági csoportokat**, és hozzárendelheti őket a szabályzathoz.

2. Válassza a **Csoportok kiválasztása** lehetőséget az Azure AD biztonsági csoportjait megjelenítő panel megnyitásához.  A **Kiválasztás** elemre kattintva telepítheti a szabályzatot a felhasználók számára.

    > [!NOTE] 
    > Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A szabályzattal megcélzott felhasználók által használt eszközök megfelelőségét értékelni fogja a rendszer.
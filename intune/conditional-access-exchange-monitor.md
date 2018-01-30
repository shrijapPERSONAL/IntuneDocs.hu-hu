---
title: "Feltételes hozzáférési megfelelőség figyelése helyszíni Exchange-hez és Exchange Online-hoz"
titlesuffix: Azure portal
description: "Feltételes hozzáférési megfelelőség figyelése helyszíni Exchange-hez és Exchange Online-hoz az Intune Azure Portal használatával"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2025bbb008be090420ebb3778fc37a0b1790608b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Feltételes hozzáférési megfelelőség figyelése helyszíni Exchange-hez és Exchange Online-hoz az Intune-ban

Az Intune 1704-es kiadásától kezdve a rendszergazdák jelentési információkat kapnak az Exchange ActiveSync eszközrekordjaival kapcsolatban, amelyek vagy a helyszíni Exchange-összekötő, vagy az Intune szolgáltatások közötti összekötő (Exchange Online-összekötő) révén az Intune-nal vannak szinkronizálva. A feltételes hozzáférési megfelelőség jelentései összefoglaló információt nyújtanak a különböző szinkronizálási állapotban lévő eszközökről:

-   **Engedélyezés**

-   **Tiltás**

-   **Karantén**

## <a name="to-monitor-conditional-access-compliance"></a>Feltételes hozzáférési megfelelőség figyelése

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be az Intune-os hitelesítő adataival.

2.  Miután sikeresen bejelentkezett, megjelenik az **Azure irányítópultja**.

3.  Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

4.  Az **Intune** kiválasztásával megjelenik az **Intune irányítópultja**.

5.  Válassza a **Feltételes hozzáférés**, majd az **Áttekintés** lehetőséget.

6.  A feltételes hozzáférési megfelelőséggel kapcsolatos jelentésének megtekintéséhez a diagramban válassza ki a három lehetőség (**Letiltva**, **Karantén** vagy **Engedélyezett**) egyikét.

    ![Feltételes hozzáférési irányítópult](./media/CA-reporting-intune-1.png)

A három terület egyikének kiválasztása után bővebb információt kap az engedélyezett, a tiltott vagy a karanténba helyezett eszközökről.

Az egyes eszközökről további részletes információkat is megjeleníthet. Az alábbi képen szereplő eszköz például le van tiltva. Az Intune arra is lehetőséget ad, hogy a feltételes hozzáférési megfelelőség jelentésének paneljéről eltávolítsa a vállalati adatokat.

![Feltételes hozzáférési jelentés – részletes eszközinformációk](./media/CA-reporting-intune-3.png)

Az eszközinformációk panelen további információk jelennek meg:

-   **Áttekintés:** Eszköztulajdonságokat jelenít meg, például: operációs rendszer verziója, eszközmodell, tulajdonos, sorozatszám, eszköz gyártója, telefonszám és az eszköz utolsó bejelentkezésének ideje.

-   **Tulajdonságok:** Megadhatja az eszköz tulajdonosi adatát (személyes vagy vállalati).

-   **Hardver:** Az Áttekintésnél található információn kívül megjeleníti a tárhelyre vonatkozó információkat (teljes terület és szabad terület), a rendszerházra, a hálózati adatokra, a hálózati szolgáltatásokra és további feltételes hozzáférési tiltásokra vonatkozó információkat.

-   **Felderített alkalmazások:** Az eszközön telepített összes alkalmazást megmutatja. A telepített alkalmazások listáját .CSV formátumban is exportálhatja.

-   **Megfelelőség:** Az eszközmegfelelőségi szabályzatokkal kapcsolatos információkat jeleníti meg.

-   **Eszközkonfiguráció:** Az eszköz konfigurációs adatait jeleníti meg.

-   **Exchange-hozzáférés:** További információkat kínál az eszköz állapotáról a feltételes hozzáférési szabályzatok alkalmazása után.

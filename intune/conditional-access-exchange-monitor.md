---
title: Az Exchange feltételes hozzáférésének figyelése a Microsoft Intune-ban
titlesuffix: ''
description: Figyelheti a feltételes hozzáférési megfelelőséget a helyszíni Exchange-hez és Exchange Online-hoz az Intune Azure Portal használatával.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 20a99290d2a84c22bc2bee823d7a3bb42e43aced
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180578"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Feltételes hozzáférési megfelelőség figyelése helyszíni Exchange-hez és Exchange Online-hoz az Intune-ban

Az Intune 1704-es kiadásától kezdve is látnak a rendszergazdák jelentési információkat az Intune-t a helyszíni Exchange-összekötő vagy az Intune szolgáltatások közötti összekötő (Exchange szinkronizált Exchange ActiveSync eszközrekordjaival Online-összekötő). A feltételes hozzáférési megfelelőség jelentései a különböző szinkronizálási állapotban eszközök összegzését tartalmazza:

-   **Engedélyezés**

-   **Tiltás**

-   **Karantén**

## <a name="to-monitor-conditional-access-compliance"></a>Feltételes hozzáférési megfelelőség figyelése

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be az Intune-os hitelesítő adataival.

2.  Miután sikeresen bejelentkezett, megjelenik a **Azure irányítópultján**.

3.  Válasszon **minden szolgáltatás** a bal oldali menüben, majd írja be **Intune** box szűrő szövegmezőbe.

4.  Válasszon **Intune**, megjelenik a **Intune irányítópultján**.

5.  Válassza a **Feltételes hozzáférés**, majd az **Áttekintés** lehetőséget.

6.  A feltételes hozzáférési megfelelőséggel kapcsolatos jelentésének megtekintéséhez a diagramban válassza ki a három lehetőség (**Engedélyezett**, **Letiltva** vagy **Karantén**) egyikét.

    ![A Feltételes hozzáférési irányítópult képe](./media/CA-reporting-intune-1.png)

A három terület egyikének kiválasztása után bővebb információt kap az engedélyezett, a tiltott vagy a karanténba helyezett eszközökről.

Emellett részletezhet az adott eszközök további részletek megtekintéséhez. A következő képen szereplő eszköz például le van tiltva. Az Intune arra is lehetőséget ad, hogy a feltételes hozzáférési megfelelőség jelentésének paneljéről eltávolítsa a vállalati adatokat.

![Feltételes hozzáférési jelentés – részletes eszközinformációk képe](./media/CA-reporting-intune-3.png)

Az eszközinformációk panelen további információk jelennek meg:

-   **Áttekintés:** Eszköztulajdonságokat jelenít meg, például: operációs rendszer verziója, eszközmodell, tulajdonos, sorozatszám, eszköz gyártója, telefonszám és az eszköz utolsó bejelentkezésének ideje.

-   **Tulajdonságok:** Megadhatja az eszköz tulajdonosi adatát (személyes vagy vállalati).

-   **Hardver:** Az Áttekintésnél található információn kívül megjeleníti a tárhelyre vonatkozó információkat (teljes terület és szabad terület), a rendszerházra, a hálózati adatokra, a hálózati szolgáltatásokra és további feltételes hozzáférési tiltásokra vonatkozó információkat.

-   **Felderített alkalmazások:** Az eszközön telepített összes alkalmazást megmutatja. A telepített alkalmazások listáját .CSV formátumban is exportálhatja.

-   **Megfelelőség:** Az eszközmegfelelőségi szabályzatokkal kapcsolatos információkat jeleníti meg.

-   **Eszközkonfiguráció:** Az eszköz konfigurációs adatait jeleníti meg.

-   **Exchange-hozzáférés:** További információkat kínál az eszköz állapotáról a feltételes hozzáférési szabályzatok alkalmazása után.

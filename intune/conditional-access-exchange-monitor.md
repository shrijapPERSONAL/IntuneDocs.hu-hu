---
title: A Microsoft Intune Exchange feltételes hozzáférésének figyelése |} A Microsoft Intune-ban
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 383370aaaca10cb44b614be6e250218106406cb4
ms.sourcegitcommit: e0374b3ced83c8876a4f78b326869c10588a55e5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56307753"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Feltételes hozzáférési megfelelőség figyelése helyszíni Exchange-hez és Exchange Online-hoz az Intune-ban

Az Intune 1704-es kiadásától kezdve a rendszergazdák jelentési információkat kapnak az Exchange ActiveSync eszközrekordjaival kapcsolatban, amelyek vagy a helyszíni Exchange-összekötő, vagy az Intune szolgáltatások közötti összekötő (Exchange Online-összekötő) révén az Intune-nal vannak szinkronizálva. A feltételes hozzáférési megfelelőség jelentései összefoglaló információt nyújtanak a különböző szinkronizálási állapotban lévő eszközökről:

-   **Engedélyezés**

-   **Tiltás**

-   **Karantén**

## <a name="to-monitor-conditional-access-compliance"></a>Feltételes hozzáférési megfelelőség figyelése

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be az Intune-os hitelesítő adataival.

2.  Miután sikeresen bejelentkezett, megjelenik az **Azure irányítópultja**.

3.  Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

4.  Az **Intune** kiválasztásával megjelenik az **Intune irányítópultja**.

5.  Válassza a **Feltételes hozzáférés**, majd az **Áttekintés** lehetőséget.

6.  A feltételes hozzáférési megfelelőséggel kapcsolatos jelentésének megtekintéséhez a diagramban válassza ki a három lehetőség (**Engedélyezett**, **Letiltva** vagy **Karantén**) egyikét.

    ![A Feltételes hozzáférési irányítópult képe](./media/CA-reporting-intune-1.png)

A három terület egyikének kiválasztása után bővebb információt kap az engedélyezett, a tiltott vagy a karanténba helyezett eszközökről.

Az egyes eszközökről további részletes információkat is megjeleníthet. A következő képen szereplő eszköz például le van tiltva. Az Intune arra is lehetőséget ad, hogy a feltételes hozzáférési megfelelőség jelentésének paneljéről eltávolítsa a vállalati adatokat.

![Feltételes hozzáférési jelentés – részletes eszközinformációk képe](./media/CA-reporting-intune-3.png)

Az eszközinformációk panelen további információk jelennek meg:

-   **Áttekintés:** Eszköztulajdonságok például tekintheti meg: Operációs rendszer verziója, eszközmodell, tulajdonjogát, sorozatszám, eszköz gyártója, telefonszám, és az utolsó az eszköz bejelentkezésének ideje.

-   **Tulajdonságok:** Az eszköz tulajdonosi adatát (személyes vagy vállalati) állíthatja be.

-   **Hardver:** Rendszerház, a hálózati adatok, a hálózati szolgáltatás és a további feltételes hozzáférési szabályzat letiltotta az részletei az áttekintés, és emellett a tárhelyre vonatkozó információkat (teljes terület és szabad terület), a megjelenő adatokat biztosít.

-   **Felderített alkalmazások:** Az eszközön telepített összes alkalmazást megmutatja. A telepített alkalmazások listáját .CSV formátumban is exportálhatja.

-   **Megfelelőség:** Az eszközmegfelelőségi szabályzat részleteit mutatja.

-   **Eszközök konfigurálása:** Azt mutatja, hogy az eszköz konfigurációs adatait.

-   **Exchange-hozzáférés:** Itt további információ az eszköz állapotát a feltételes hozzáférési szabályzatok alkalmazása után.

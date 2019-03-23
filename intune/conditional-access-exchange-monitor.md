---
title: A Microsoft Intune Exchange feltételes hozzáférésének figyelése |} A Microsoft Intune-ban
description: Figyelheti a feltételes hozzáférési megfelelőséget a helyszíni Exchange-hez és Exchange Online-hoz az Intune Azure Portal használatával.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ebca668ba3e02ec6088bb72370d7d5061241627
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394932"
---
# <a name="monitor-conditional-access-compliance-for-exchange-on-premises-in-intune"></a>A helyszíni Exchange-hez az Intune feltételes hozzáférési megfelelőség figyelése

Intune-rendszergazdák tekintheti meg az Exchange ActiveSync eszközrekordjaival keresztül a helyszíni Exchange-összekötő az Intune-nal szinkronizált kapcsolatos jelentéskészítés. A feltételes hozzáférési megfelelőség jelentései összefoglaló információt nyújtanak a különböző szinkronizálási állapotban lévő eszközökről:

- **Engedélyezés**

- **Tiltás**

- **Karantén**

## <a name="to-monitor-conditional-access-compliance"></a>Feltételes hozzáférési megfelelőség figyelése

1. Jelentkezzen be a [Intune](https://aka.ms/intuneportal), és nyissa meg **feltételes hozzáférési**, majd válassza a **áttekintése**.

2. A feltételes hozzáférési megfelelőséggel kapcsolatos jelentésének megtekintéséhez a diagramban válassza ki a három lehetőség (**Engedélyezett**, **Letiltva** vagy **Karantén**) egyikét.

   ![A Feltételes hozzáférési irányítópult képe](./media/CA-reporting-intune-1.png)

A három terület egyikének kiválasztása után bővebb információt kap az engedélyezett, a tiltott vagy a karanténba helyezett eszközökről.

Az egyes eszközökről további részletes információkat is megjeleníthet. A következő képen szereplő eszköz például le van tiltva. Az Intune arra is lehetőséget ad, hogy a feltételes hozzáférési megfelelőség jelentésének paneljéről eltávolítsa a vállalati adatokat.

![Feltételes hozzáférési jelentés – részletes eszközinformációk képe](./media/CA-reporting-intune-3.png)

Az eszközinformációk panelen további információk jelennek meg:

- **Áttekintés:** Eszköztulajdonságok például tekintheti meg: Operációs rendszer verziója, eszközmodell, tulajdonjogát, sorozatszám, eszköz gyártója, telefonszám, és az utolsó az eszköz bejelentkezésének ideje.

- **Tulajdonságok:** Az eszköz tulajdonosi adatát (személyes vagy vállalati) állíthatja be.

- **Hardver:** Rendszerház, a hálózati adatok, a hálózati szolgáltatás és a további feltételes hozzáférési szabályzat letiltotta az részletei az áttekintés, és emellett a tárhelyre vonatkozó információkat (teljes terület és szabad terület), a megjelenő adatokat biztosít.

- **Felderített alkalmazások:** Az eszközön telepített összes alkalmazást megmutatja. A telepített alkalmazások listáját .CSV formátumban is exportálhatja.

- **Megfelelőség:** Az eszközmegfelelőségi szabályzat részleteit mutatja.

- **Eszközök konfigurálása:** Azt mutatja, hogy az eszköz konfigurációs adatait.

- **Exchange-hozzáférés:** Itt további információ az eszköz állapotát a feltételes hozzáférési szabályzatok alkalmazása után.

---
title: "Meg nem felelés esetén végrehajtandó műveletek az Intune-nal"
titleSuffix: Intune on Azure
description: "Ismertető: meg nem felelés esetén végrehajtandó műveletek létrehozása az Intune-nal"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek automatizálása

A **Meg nem felelés esetén végrehajtandó műveletek** panelen időrendbe állított műveleteket alkalmazhat a nem megfelelőnek minősülő eszközökre. Az Intune alapértelmezés szerint az első olyan alkalommal nem megfelelőként jelöli meg az eszközt, amikor azt érzékeli, hogy az nem felel meg a megfelelőségi szabályzat feltételeinek, az Azure AD feltételes hozzáférése pedig ezt követően letiltja az eszközt. A **Meg nem felelés esetén végrehajtandó műveletek** panelen rugalmasabban dönthet arról, hogy mi történjen, ha egy eszköz nem megfelelő. Például úgy is dönthet, hogy nem tiltja le azonnal az eszközt, hanem egy türelmi időszakot határoz meg az eszköz megfelelőségének visszaállítására.

Kétféle művelet használható:

-   **Végfelhasználók értesítése e-mailben**: Az e-mailes értesítést testre szabhatja, mielőtt elküldené a felhasználónak. Az Intune-nal testre szabhatja az e-mail címzettjeit és tárgyát, az üzenet szövegét, a vállalati logót és a kapcsolattartási adatokat.

    Ezenkívül az Intune a nem megfelelő eszköz adatait is szerepelteti az értesítésben.

-   **Eszköz megjelölése nem megfelelőként:** Megadhatja, hogy hány napon belül legyen megjelölve az eszköz nem megfelelőként. A műveletet konfigurálhatja azonnali kezdettel, de meghatározhat egy türelmi időszakot is, amelyen belül a felhasználónak vissza kell állítania az eszköz megfelelőségét.

## <a name="before-you-begin"></a>Előkészületek

Meg nem felelés esetén alkalmazandó műveletek beállításához rendelkeznie kell legalább egy eszközmegfelelőségi szabályzattal. 

- Az alábbi forrásokból megtudhatja, hogyan hozhat létre eszközmegfelelőségi szabályzatot az egyes platformokhoz:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

A vállalati erőforrásokhoz való hozzáférés letiltásához használandó eszközmegfelelőségi szabályzatok felállításához már üzembe helyezett Azure AD feltételes hozzáféréssel kell rendelkeznie. 

- További információ az [EMS feltételes hozzáférés beállításáról](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Ezen kívül létre kell hoznia az értesítési üzenethez használandó üzenetsablont is. Az értesítési üzenet sablonjára a meg nem felelés esetén alkalmazandó műveletek létrehozásánál lesz szüksége, melynek része lehet a felhasználónak küldött e-mail.

### <a name="to-create-a-notification-message-template"></a>Értesítési üzenet sablonjának létrehozásához

1. Az [Azure Portalbeli Intune-ban](https://portal.azure.com) jelentkezzen be az Intune-os hitelesítő adataival.
2. Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.
3. Válassza az **Intune** lehetőséget
4. A **Kezelés** szakaszban válassza az **Eszközmegfelelőség**, majd az **Értesítések** elemet.
5. Válassza az **Értesítés létrehozása** lehetőséget, majd adja meg az alábbi adatokat:
    - Név
    - Tárgy
    - Üzenet
    - E-mail fejléce – a cég emblémájának megjelenítése
    - E-mail lábléce – a cég emblémájának megjelenítése
    - E-mail lábléce – kapcsolatfelvételi adatok megjelenítése

5. Válassza az **Értesítés létrehozása** lehetőséget, majd adja meg az alábbi adatokat:

    a. Név

    b. Tárgy

    c.  Üzenet

    d. e-mail fejléce – a cég emblémájának megjelenítése

    e. e-mail lábléce – a cég emblémájának megjelenítése

    f. e-mail lábléce – kapcsolatfelvételi adatok megjelenítése

![példa az értesítési üzenet sablonjára](./media/actionsfornoncompliance-1.PNG)

Ha megadta a szükséges információkat, válassza a **Létrehozás** elemet. Az értesítési üzenet sablonja használatra kész.

> [!NOTE]
> A korábban létrehozott értesítési sablonokat szerkesztheti is.

## <a name="to-create-actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek létrehozása

> [!TIP]
> Az Intune alapértelmezés szerint egy előre definiált műveletet kínál fel a nem megfelelőség esetén végrehajtandó műveletek szakaszban. Ez a művelet az eszközt nem megfelelőként jelöli meg, miután a rendszer azt észlelte, hogy az nem teljesíti az eszközmegfelelőségi szabályzatban foglalt feltételeket. Beállíthatja, hogy az eszköz az észlelés után mennyi ideig legyen nem megfelelőként megjelölve. A művelet nem távolítható el.

Adhat hozzá műveletet az új eszközmegfelelőségi szabályzat létrehozásakor, vagy a már létező eszközmegfelelőségi szabályzat szerkesztésével is.

1.  Az Intune-tevékenységprofilban az **Eszközmegfelelőségi szabályzatok** panelen válassza a **Kezelés** szakasz alatti **Szabályzatok** elemet.

2.  Kattintással válassza ki az eszközmegfelelőségi szabályzatot, majd a **Kezelés** szakaszban válassza a **Tulajdonságok** elemet.

3.  A megnyíló **eszközmegfelelőségi szabályzat tulajdonságai** panelen válassza a **Meg nem felelési műveletek** lehetőséget.

4.  A műveletek paramétereinek megadásához a **Műveletek meg nem felelés esetén** panelen válassza a **Hozzáadás** elemet. Kiválaszthatja az előzőleg létrehozott üzenetsablont, további címzetteket, valamint a türelmi időszak ütemezését is. Az ütemezésben megadhatja a napok számát (0 és 365 között), és ezt követően kötelezővé teheti a feltétele hozzáférési szabályzatok érvénybe léptetését. Ha a napok számánál **0** értéket ad meg, akkor a feltételes hozzáférés **azonnal** letiltja a hozzáférést a vállalati erőforrásokhoz, amennyiben az eszköz nem felel meg az eszközmegfelelőségi szabályzatnak.

5.  Ha megadta az összes szükséged adatot, válassza a **Hozzáadás**, majd az **OK** elemet.

## <a name="next-steps"></a>További lépések
Az eszközmegfelelőségi tevékenységet az eszközmegfelelőségi panelen elérhető jelentéseket futtatva figyelheti. További információt [Az eszközmegfelelőség figyelése az Intune-ban](device-compliance-monitor.md) című témakörben talál.

---
title: "Hardver- és szoftverleltár megtekintése Windows rendszerű számítógépeken | Microsoft Intune"
description: "Hogyan tekintheti meg az Intune által kezelt Windows-számítógépek hardver- és szoftverinformációit."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 807599d4a6a979c88732ab969fdecb64552a83d5


---

# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Hardver- és szoftverleltár megtekintése Windows rendszerű számítógépeken

Az Intune részletes információkat gyűjt a felügyelt számítógépek hardvereiről és szoftvereiről. Az alábbi eljárásokban lévő információkból megtudhatja:

-   Hogyan hozhat létre olyan jelentést, amely az Ön által kezelt számítógépek hardvertulajdonságaival kapcsolatos információkat tartalmazza.

-   Hogyan hozhat létre olyan jelentést, amely az egyes számítógépekre telepített szoftvereket tartalmazza.

-   Hogyan frissítheti a számítógépleltárat, hogy a jelentésben szereplő adatok naprakészek legyenek.

## <a name="to-display-information-about-computers-you-manage"></a>Az Ön által kezelt számítógépekkel kapcsolatos információk megjelenítése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Jelentések** &gt; **Számítógépleltár-jelentések** lehetőséget.

2.  Az **Új jelentés létrehozása** lapon fogadja el az alapértelmezett értékeket, vagy állítsa be őket a jelentés által visszaadott eredmények szűrésére. Kiválaszthatja például, hogy csak a Windows 8.1-et futtató számítógépek jelenjenek meg a jelentésben.

3.  A **Jelentés megtekintése** elemet választva megnyithatja a **Számítógépleltár-jelentést** egy új ablakban.

    Az egyes oszlopok fejlécét választva a jelentést bármelyik oszlop, például a **Név**, a **Ház típusa** vagy a **Gyártó** szerint rendezheti.

## <a name="to-display-software-installed-on-computers-you-manage"></a>Az Ön által kezelt számítógépekre telepített szoftverek megjelenítése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Jelentések** &gt; **Észlelt szoftverek jelentései** elemet.

2.  Az **Új jelentés létrehozása** lapon fogadja el az alapértelmezett értékeket, vagy állítsa be őket a jelentés által visszaadott eredmények szűrésére. Kiválaszthatja például, hogy csak a Microsoft által kiadott szoftverek jelenjenek meg a jelentésben.

3.  A **Jelentés megtekintése** elemet választva megnyithatja az **Észlelt szoftverek jelentéseit** egy új ablakban.

    Az egyes oszlopok fejlécét választva a jelentést bármelyik oszlop, például a **Név**, a **Kiadó** vagy a **Kategória** alapján rendezheti. A listában lévő frissítések kibontásával, a listaelem mellett lévő, irányt mutató nyílra kattintva részletes információkat jeleníthet meg (például a számítógépeket, amelyeken telepítve van).

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>A számítógépleltár frissítése a naprakész állapot biztosításához

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Csoportok** &gt; **Minden eszköz** elemet (vagy egy másik csoportot, amely tartalmazza azt a számítógépet, amelynek a leltárát frissíteni szeretné).

2.  Válasszon ki egy számítógépet, vagy tartsa lenyomva a **Ctrl** billentyűt több számítógép kijelöléséhez.

3.  A tálcán válassza a **Távoli feladatok** &gt; **Leltár frissítése** elemet.

4.  A feladat állapotának megtekintéséhez válassza a lap jobb alsó sarkában található **Távoli feladatok** elemet.

    A **Feladat állapota** párbeszédpanel megjeleníti az aktuális távoli feladatokat, a feladatok állapotát, az eszköz nevét és minden jelentett hibát, valamint egy hivatkozást kínál a hibaelhárítási információkhoz.

### <a name="see-also"></a>További információ

[A Windows rendszerű számítógépek Intune-szoftverügyféllel való felügyeletének általános feladatai](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->



---
title: "Alkalmazás-hozzárendelések belefoglalása vagy kizárása"
titlesuffix: Microsoft Intune
description: "Tájékoztató arról, hogyan használható az Intune az alkalmazás-hozzárendelések belefoglalására vagy kizárására."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban

Az Intune-ban úgy határozhatja meg, hogy ki férhet hozzá az alkalmazáshoz, ha csoportokat rendel hozzá akár az engedélyezéshez, akár a kizáráshoz. Az alkalmazás-hozzárendeléseket felhasználók vagy eszközök csoportjaira vonatkozóan végezheti el csoport-hozzárendelések belefoglalásával vagy kizárásával. Az alkalmazás kiválasztása után meghatározhatja az alkalmazás hozzárendelési módját. Ez a funkció akkor különösen hasznos, ha nagyobb csoportok számára szeretné elérhetővé tenni az alkalmazást, majd pedig szűkíteni szeretné a felhasználók körét, miközben egy kisebb csoportot is kizárhat. A kisebb csoport lehet például tesztcsoport, vagy vezetők egy csoportja. 

Amikor csoportot zár ki egy hozzárendelésből, akkor vagy csak felhasználói vagy csak eszközcsoportot kell kizárnia, vegyesen nem. Az Intune nem veszi számításba a felhasználók és eszközök közötti társításokat a csoportok kizárásánál. Felhasználói csoportok belefoglalása és eszközcsoportok egyidejű kizárása minden bizonnyal nem éri el a kívánt eredményt, mivel a belefoglalás felülírja a kizárást. Ha például egy iOS-alkalmazást **Minden felhasználóra** céloz, és kizárja a **Minden iPad** csoportot, az eredmény az lesz, hogy minden iPadet használó felhasználó továbbra is hozzáfér az alkalmazáshoz. Ha azonban az iOS-alkalmazás célzása **Minden eszköz**, és kizárja a **Minden iPad** csoportot, akkor a beállítás sikeres lesz.  

>[!NOTE]
>Alkalmazások csoport-hozzárendelésénél a **Nem alkalmazható** típus nem használható többé, helyette a csoport kizárása lehetőség használható. 
>
>Az Intune biztosítja az előre létrehozott **Minden felhasználó** és **Minden eszköz** csoportok beépített optimalizálását a felhasználók kényelme érdekében a konzolon. Mindenképpen ajánlott ezeket a csoportokat használni az összes felhasználó és az összes eszköz megcélzására az Ön által létrehozott „Minden felhasználó” vagy „Minden eszköz” csoport helyett.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Csoportok belefoglalása és kizárása alkalmazások hozzárendelésénél 
Ha csoportokhoz szeretne alkalmazást hozzárendelni a belefoglalás és kizárás használatával:
1. A Microsoft Intune panelen válassza a **Mobilalkalmazások** lehetőséget.
2. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** lehetőséget. Megjelenik a hozzáadott alkalmazások listája.
3. Válassza ki a hozzárendelni kívánt alkalmazást. Megjelenik az alkalmazáshoz tartozó irányítópult. 
4. A **Kezelés** szakaszban válassza a **Hozzárendelések** elemet. 

    ![Alkalmazás-hozzárendelések az Intune-ban](./media/apps-inc-exl-01.png)
5. Az alkalmazáshoz hozzárendelt felhasználói csoportok hozzáadásához válassza a **Csoport hozzáadása** lehetőséget. 
6. A **Csoport hozzáadása** panelen válasszon egy **Hozzárendelési típust** az elérhető típusok közül.
7. Hozzárendelési típusként válassza ki az **Elérhető regisztrációval és anélkül** lehetőséget.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoport hozzáadása](./media/apps-inc-exl-02.png)
8. A **Belefoglalt csoportok** lehetőséggel választhatja ki azokat a felhasználói csoportokat, amelyek számára elérhetővé szeretné tenni az alkalmazást.

    >[!NOTE]
    >Csoportok hozzáadásakor, ha bármely más csoport már bele lett foglalva egy adott hozzárendelés-típus esetében, az előre ki lesz jelölve, és nem módosítható más belefoglalási hozzárendelés-típusok esetében. Ezért az adott csoport használatba lett véve, és így nem használható kizárt csoportként.

9. Az **Igen** választásával teheti elérhetővé az alkalmazást minden felhasználó számára.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoportok belefoglalása](./media/apps-inc-exl-03.png)
10. Az **OK** választásával foglalhatja bele a csoportot.
11. A **Kizárt csoportok** lehetőséggel választhatja ki azokat a felhasználói csoportokat, amelyek számára nem szeretné elérhetővé tenni az alkalmazást. 
12. Válassza ki azokat a csoportokat, amelyek számára elérhetetlenné szeretné tenni az alkalmazást.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoportok kizárása](./media/apps-inc-exl-04.png)
13. A csoportkiválasztás befejezéséhez kattintson a **Kiválasztás** lehetőségre.
14. A **Csoport hozzáadása** panelen kattintson az **OK** lehetőségre. Megjelenik az alkalmazáshoz tartozó **Hozzárendelések** listája.
15. A **Mentés** lehetőségre kattintva aktiválhatja az alkalmazásra vonatkozó csoport-hozzárendeléseket.

Csoport-hozzárendeléseknél a már hozzárendelt vagy kiválasztott csoportok nem elérhetőek. Ha jelenleg nem elérhető csoportot szeretne kiválasztani, akkor először távolítsa azt el az alkalmazás hozzárendelési listájából. Az alkalmazás **Hozzárendelések** listáját úgy szerkesztheti, ha kiválasztja azt a sort, amely a módosítandó hozzárendelést tartalmazza. Ezen kívül úgy is eltávolíthat hozzárendelést, ha a sor végén található három pontra (...) kattint, majd az **Eltávolítás** lehetőséget választja. A **Hozzárendelések** lista megjelenítését is módosíthatja: választhat **Hozzárendelési típus** vagy **Belefoglalt/Kizárt** állapot szerinti csoportosíts között.

![Alkalmazás-hozzárendelések az Intune-ban – befejezés](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>További lépések

* A [Microsoft Intune blogján](https://aka.ms/new_app_assignment_process) további információt talál az alkalmazások csoport-hozzárendelésénél alkalmazható belefoglalásról és kizárásról.

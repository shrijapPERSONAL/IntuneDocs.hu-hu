---
title: "Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban"
titlesuffix: 
description: "Az Intune az alkalmazás-hozzárendelések belefoglalására vagy kizárására való használatának ismertetése."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dbe8669dc2bf448e0738147758d90ba6d2d69b06
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban

Az Intune-ban úgy határozhatja meg, hogy ki férhet hozzá az alkalmazáshoz, ha csoportokat rendel hozzá akár az engedélyezéshez, akár a kizáráshoz. Azonban mielőtt csoportokat rendelne az alkalmazáshoz, meg kell adnia az alkalmazás hozzárendelési típusát. A hozzárendelés típusával az alkalmazás elérhetővé vagy kötelezővé tehető, illetve törölhető. 

Amikor egy alkalmazás elérhetősége van a középpontban, az alkalmazás-hozzárendeléseket felhasználók vagy eszközök csoportjaira vonatkozóan végezheti el csoport-hozzárendelések belefoglalásával vagy kizárásával. Ez a funkció akkor különösen hasznos, ha nagyobb csoportok számára szeretné elérhetővé tenni az alkalmazást, majd pedig szűkíteni szeretné a felhasználók körét, miközben egy kisebb csoportot is kizárhat. A kisebb csoport lehet például tesztcsoport, vagy vezetők egy csoportja. 

Amikor csoportot zár ki egy alkalmazás-hozzárendelésből, akkor vagy csak felhasználói vagy csak eszközcsoportot kell kizárnia, vegyesen nem. Az Intune nem veszi számításba a felhasználók és eszközök közötti társításokat a csoportok kizárásánál. Felhasználói csoportok belefoglalása és eszközcsoportok egyidejű kizárása minden bizonnyal nem éri el a kívánt eredményt, mivel a belefoglalás felülírja a kizárást. Ha például egy iOS-alkalmazást **Minden felhasználóra** céloz, és kizárja a **Minden iPad** csoportot, az eredmény az lesz, hogy minden iPadet használó felhasználó továbbra is hozzáfér az alkalmazáshoz. Ha azonban az iOS-alkalmazás célzása **Minden eszköz**, és kizárja a **Minden iPad** csoportot, akkor a beállítás sikeres lesz.  

>[!NOTE]
>Alkalmazások csoport-hozzárendelésénél a **Nem alkalmazható** típus nem használható többé, helyette a csoport kizárása lehetőség használható. 
>
>Az Intune biztosítja az előre létrehozott **Minden felhasználó** és **Minden eszköz** csoportok beépített optimalizálását a felhasználók kényelme érdekében a konzolon. Mindenképpen ajánlott ezeket a csoportokat használni az összes felhasználó és az összes eszköz megcélzására az Ön által létrehozott „Minden felhasználó” vagy „Minden eszköz” csoport helyett.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Csoportok belefoglalása és kizárása alkalmazások hozzárendelésénél 
Ha csoportokhoz szeretne alkalmazást hozzárendelni a belefoglalás és kizárás használatával:
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. A Microsoft Intune panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** lehetőséget. Megjelenik a hozzáadott alkalmazások listája.
5. Válassza ki a hozzárendelni kívánt alkalmazást. Megjelenik az alkalmazáshoz tartozó irányítópult. 
6. A **Kezelés** szakaszban válassza a **Hozzárendelések** elemet. 

    ![Alkalmazás-hozzárendelések az Intune-ban](./media/apps-inc-exl-01.png)
7. Az alkalmazáshoz hozzárendelt felhasználói csoportok hozzáadásához válassza a **Csoport hozzáadása** lehetőséget. 
8. A **Csoport hozzáadása** panelen válasszon egy **Hozzárendelési típust** az elérhető típusok közül.
9. Hozzárendelési típusként válassza ki az **Elérhető regisztrációval és anélkül** lehetőséget.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoport hozzáadása](./media/apps-inc-exl-02.png)
10. A **Belefoglalt csoportok** lehetőséggel választhatja ki azokat a felhasználói csoportokat, amelyek számára elérhetővé szeretné tenni az alkalmazást.

    >[!NOTE]
    >Csoportok hozzáadásakor, ha bármely más csoport már bele lett foglalva egy adott hozzárendelés-típus esetében, az előre ki lesz jelölve, és nem módosítható más belefoglalási hozzárendelés-típusok esetében. Ezért az adott csoport használatba lett véve, és így nem használható kizárt csoportként.

11. Az **Igen** választásával teheti elérhetővé az alkalmazást minden felhasználó számára.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoportok belefoglalása](./media/apps-inc-exl-03.png)
12. Az **OK** választásával foglalhatja bele a csoportot.
13. A **Kizárt csoportok** lehetőséggel választhatja ki azokat a felhasználói csoportokat, amelyek számára nem szeretné elérhetővé tenni az alkalmazást. 
14. Válassza ki azokat a csoportokat, amelyek számára elérhetetlenné szeretné tenni az alkalmazást.

    ![Alkalmazás-hozzárendelések az Intune-ban – Csoportok kizárása](./media/apps-inc-exl-04.png)
15. A csoportkiválasztás befejezéséhez kattintson a **Kiválasztás** lehetőségre.
16. A **Csoport hozzáadása** panelen kattintson az **OK** lehetőségre. Megjelenik az alkalmazáshoz tartozó **Hozzárendelések** listája.
17. A **Mentés** lehetőségre kattintva aktiválhatja az alkalmazásra vonatkozó csoport-hozzárendeléseket.

Csoport-hozzárendeléseknél a már hozzárendelt vagy kiválasztott csoportok nem elérhetőek. Ha jelenleg nem elérhető csoportot szeretne kiválasztani, akkor először távolítsa azt el az alkalmazás hozzárendelési listájából. Az alkalmazás **Hozzárendelések** listáját úgy szerkesztheti, ha kiválasztja azt a sort, amely a módosítandó hozzárendelést tartalmazza. Ezen kívül úgy is eltávolíthat hozzárendelést, ha a sor végén található három pontra (...) kattint, majd az **Eltávolítás** lehetőséget választja. A **Hozzárendelések** lista megjelenítését is módosíthatja: választhat **Hozzárendelési típus** vagy **Belefoglalt/Kizárt** állapot szerinti csoportosíts között.

![Alkalmazás-hozzárendelések az Intune-ban – befejezés](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>További lépések

- A [Microsoft Intune blogján](https://aka.ms/new_app_assignment_process) további információt talál az alkalmazások csoport-hozzárendelésénél alkalmazható belefoglalásról és kizárásról.
- [Alkalmazásadatok és -hozzárendelések figyelése](apps-monitor.md)
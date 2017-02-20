---
title: "MAM-szabályzatok figyelése a Microsoft Intune-nal | Microsoft Docs"
description: "Megtudhatja, hány felhasználóra érvényes a szabályzat, és lefúrással megjelenítheti a részleteket."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 22c30f51bf83219053f97310ed1830ad9e01acd8
ms.openlocfilehash: bd270cd4b04894d4824487d36ea4f0c1929dd568


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Mobilalkalmazás-felügyeleti szabályzatok figyelése a Microsoft Intune-nal
Figyelheti a felhasználókra alkalmazott mobilalkalmazás-kezelési (MAM) szabályzatok megfelelőségi állapotát. Itt információkat találhat a MAM-szabályzatok által érintett felhasználókról, azok megfelelőségi állapotáról, valamint a felhasználók által esetlegesen tapasztalt problémákról.

Három különböző helyen figyelheti a megfelelőségi állapotot:

-   Összesített nézet

-   Részletes nézet

-   Jelentéskészítés nézet

## <a name="summary-view"></a>Összesített nézet

Kövesse az alábbi három lépést az Összegzés nézet megnyitásához:

1. Nyissa meg az [Azure Portal](https://portal.azure.com) webhelyet, és adja meg hitelesítő adatait.
2. Válassza a **További szolgáltatások** lehetőséget, a szűrési szövegmezőbe írja be az **Intune** szót.
3. Válassza az **Intune alkalmazásvédelem** lehetőséget.

Az **Intune mobilalkalmazás-kezelés** panelen megtekintheti a megfelelési állapot összefoglalását:

![Az Intune mobilalkalmazás-kezelés panel Összefoglalás csempéje](../media/mam-azure-portal-user-status-summary.png)

-   **Felhasználók:** a szabályzathoz társított alkalmazásokat használó felhasználók száma a vállalatnál.

-   **HÁZIREND ÁLTAL KEZELT:** azon felhasználók száma, akik az alkalmazások közül legalább egyet már használtak a munkahelyi környezetben.

-   **NEM TALÁLHATÓ HÁZIREND:** azon felhasználók száma, akik használják ugyan a szabályzathoz társított alkalmazásokat, de akikre nem vonatkozik a beállított szabályzat. Érdemes megfontolni ezen felhasználók bevonását a szabályzat hatálya alá.

- **Megjelölt felhasználók:** a problémákat tapasztaló felhasználók száma. A rendszer jelenleg a **Megjelölt felhasználók** részben kizárólag a jailbreakelt eszközt használó felhasználókat jelöli meg.


## <a name="detailed-view"></a>Részletes nézet
Ha meg szeretné tekinteni az összefoglalás részleteit, válassza a **Felhasználói állapot** csempét (az eszköz operációsrendszer-platformjának megfelelően), majd a **Megjelölt felhasználók** csempét.

### <a name="user-status"></a>Felhasználó állapota
Itt megkeresheti az adott felhasználókat, és ellenőrizheti a megfelelési állapotukat. Az **Alkalmazásjelentések** panelen a következő információk tekinthetők meg a kiválasztott felhasználóról:
- A felhasználói fiókhoz társított eszközök listája

- Az eszközön futó, MAM-szabályzat hatálya alá tartozó alkalmazások listája

- Állapot:

  - **Beadva:** a szabályzat települt a felhasználónál, és az alkalmazást legalább egyszer már használták a munkahelyi környezetben.

  - **Nincs beadva:** a szabályzat települt a felhasználónál, de az alkalmazást még egyszer sem használták a munkahelyi környezetben.

>[!NOTE]
> Ha a keresett felhasználók nem rendelkeznek telepített MAM-szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen MAM-szabályzat sem.

A felhasználóhoz tartozó jelentések megtekintéséhez kövesse az alábbi lépéseket:

1.  Egy felhasználó kijelöléséhez válassza az **Összefoglalás** csempét.

    ![3. képernyőkép](../media/MAM-reporting-6.png)

2. A megjelenő **Alkalmazásjelentések** panelen válassza a **Felhasználó kijelölése** lehetőséget, és keresse meg a kívánt Azure Active Directory-felhasználót.

    ![A Felhasználó kijelölése elem az Alkalmazásjelentések panelen](../media/MAM-reporting-2.png)

3. Válassza ki a listából a felhasználót. Megjelennek a felhasználó megfelelési állapotára vonatkozó információk.

### <a name="flagged-users"></a>Megjelölt felhasználók
A részletes nézetben látható a hibaüzenet, annak az alkalmazásnak a neve, amelynek a használata közben fellépett a hiba, az eszközök érintett operációsrendszer-platformja, valamint egy időbélyeg.

## <a name="reporting-view"></a>Jelentéskészítés nézet

Itt megtalálhatja a Részletes nézetben is szereplő jelentéseket, illetve további jelentéseket, melyek segítséget nyújtanak a mobilalkalmazás-kezelési szabályzat megfelelőségi állapotával kapcsolatban:

![4. képernyőkép](../media/MAM-reporting-7.png)

-   **Alkalmazásvédelmi felhasználói jelentés:** Ugyanazokat az információkat ismerteti, mint a Részletes nézetre vonatkozó fentebbi szakaszban említett **Felhasználói állapot** jelentés.

-   **Alkalmazásvédelmi alkalmazásjelentés:** Két különböző alkalmazásvédelmi állapotot biztosít, melyeket a rendszergazdák kiválaszthatnak a jelentés létrehozása előtt. Az állapot védett vagy nem védett lehet.

    -   Felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (védett): Ez a jelentés az egyes felügyelt MAM-alkalmazások tevékenységeit ismerteti, felhasználónként.

        -   Megjelenik benne minden olyan alkalmazás az egyes felhasználókra vonatkozóan, melyekre MAM-szabályzatok lettek érvényesítve, illetve az egyes alkalmazások állapotának felbontása aszerint, hogy az adott alkalmazásra lettek-e érvényesítve MAM-szabályzatok, vagy vonatkozik rá egy MAM-szabályzat, de az nem lett érvényesítve az alkalmazásra.
<br></br>
    -   Nem felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (védett): Ez a jelentés a jelenleg nem felügyelt MAM-kompatibilis alkalmazások tevékenységeit ismerteti, felhasználónként. Ez a következő okokból fordulhat elő:

        -   Ezeket az alkalmazásokat egy olyan felhasználó vagy alkalmazás használja, akire vagy amelyre jelenleg nem vonatkozik MAM-szabályzat.

        -   Minden alkalmazás érvényesítve lett, de nincsenek rájuk vonatkozó MAM-szabályzatok.

![2. képernyőkép](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Táblacsoportosítás

Amint az **alkalmazásvédelmi felhasználói jelentés** adatai megjelennek, az alábbiak szerint összesítheti azokat:

- **Ellenőrzés eredménye:** az alkalmazásvédelmi állapot (amely lehet hiba, figyelmeztetés vagy sikeres) szerint csoportosított adatokat jelenít meg.
- **Alkalmazás neve:** az alkalmazások neve (a tényleges alkalmazásnév) szerint csoportosított adatokat jelenít meg hiba, figyelmeztetés vagy sikeres állapottal.

## <a name="export-app-protection-activities-to-csv"></a>Az alkalmazásvédelmi tevékenységek exportálása CSV-fájlba

Az alkalmazásvédelmi szabályzatokkal kapcsolatos összes tevékenységet egyetlen .csv-fájlba exportálhatja. Ez hasznos lehet az összes, a felhasználók felől jelentett alkalmazásvédelmi állapot elemzésében.

Az alkalmazásvédelmi jelentés létrehozásához kövesse az alábbi lépéseket:

1. Az Intune-os mobilalkalmazás-kezelés paneljén válassza az alkalmazásvédelmi jelentést.

    ![Képernyőkép-6](../media/app-protection-report-csv-2.png)

2. Válassza az Igen lehetőséget a jelentés mentéséhez, majd válassza a Mentés másként lehetőséget, és válassza ki azt a mappát, ahova a jelentést menteni szeretné.

    ![Képernyőkép-7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>További információ
[iOS-alkalmazások közti adatátvitel kezelése](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Mi várható az Android-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Mi várható az iOS-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->



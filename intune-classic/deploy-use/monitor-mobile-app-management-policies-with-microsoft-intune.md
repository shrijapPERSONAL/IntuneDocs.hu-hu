---
title: "MAM-szabályzatok figyelése a Microsoft Intune-nal"
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
ms.custom: intune-classic
ms.openlocfilehash: 5be08d2535acefe099429ab732d6d5d99205b2e7
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>Alkalmazásvédelmi szabályzatok figyelése a Microsoft Intune-ban
Figyelheti a felhasználókra vonatkozó alkalmazásvédelmi szabályzatok megfelelőségi állapotát. Itt információkat találhat az alkalmazásvédelmi szabályzatok által érintett felhasználókról, azok megfelelőségi állapotáról, valamint a felhasználók által esetlegesen tapasztalt problémákról.

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

-   **Felhasználók**: A cég összes olyan felhasználója, akik egy adott szabályzathoz társított alkalmazást használnak a munkahelyi környezetben.

-   **SZABÁLYZAT ÁLTAL KEZELT**: Azon felhasználók, akik már használtak egy alkalmazást, és szabályzat van hozzájuk rendelve a munkahelyi környezetben.

-   **NINCS SZABÁLYZAT**: Azon felhasználók, akik szabályzat nélküli alkalmazást használnak a munkahelyi környezetben. Érdemes megfontolni ezen felhasználók bevonását a szabályzat hatálya alá.
    > [!NOTE]
    > Platformonként több szabályzat esetén a felhasználó akkor minősül szabályzat által kezeltnek, ha legalább egy szabályzat hozzá van rendelve.

- **Megjelölt felhasználók:** a problémákat tapasztaló felhasználók száma. A rendszer jelenleg a **Megjelölt felhasználók** részben kizárólag a jailbreakelt eszközt használó felhasználókat jelöli meg.


## <a name="detailed-view"></a>Részletes nézet
Ha meg szeretné tekinteni az összefoglalás részleteit, válassza a **Felhasználói állapot** csempét (az eszköz operációsrendszer-platformjának megfelelően), majd a **Megjelölt felhasználók** csempét.

### <a name="user-status"></a>Felhasználó állapota
Itt megkeresheti az adott felhasználókat, és ellenőrizheti a megfelelési állapotukat. Az **Alkalmazásjelentések** panelen a következő információk tekinthetők meg a kiválasztott felhasználóról:
- A felhasználói fiókhoz társított eszközök listája

- Az eszközön lévő, alkalmazásvédelmi szabályzat által érintett alkalmazások listája

- Állapot:

  - **Beadva:** a szabályzat települt a felhasználónál, és az alkalmazást legalább egyszer már használták a munkahelyi környezetben.

  - **Nincs beadva:** a szabályzat települt a felhasználónál, de az alkalmazást még egyszer sem használták a munkahelyi környezetben.

>[!NOTE]
> Ha a keresett felhasználók nem rendelkeznek telepített alkalmazásvédelmi szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen alkalmazásvédelmi szabályzat sem.

A felhasználóhoz tartozó jelentések megtekintéséhez kövesse az alábbi lépéseket:

1.  Egy felhasználó kijelöléséhez válassza az **Összefoglalás** csempét.

    ![3. képernyőkép](../media/MAM-reporting-6.png)

2. A megjelenő **Alkalmazásjelentések** panelen válassza a **Felhasználó kijelölése** lehetőséget, és keresse meg a kívánt Azure Active Directory-felhasználót.

    ![A Felhasználó kijelölése elem az Alkalmazásjelentések panelen](../media/MAM-reporting-2.png)

3. Válassza ki a listából a felhasználót. Megjelennek a felhasználó megfelelési állapotára vonatkozó információk.

### <a name="flagged-users"></a>Megjelölt felhasználók
A részletes nézetben látható a hibaüzenet, annak az alkalmazásnak a neve, amelynek a használata közben fellépett a hiba, az eszközök érintett operációsrendszer-platformja, valamint egy időbélyeg.

## <a name="reporting-view"></a>Jelentéskészítés nézet

Itt megtalálhatja a Részletes nézetben is szereplő jelentéseket, illetve további jelentéseket, melyek segítséget nyújtanak az alkalmazásvédelmi szabályzat megfelelőségi állapotával kapcsolatban:

![4. képernyőkép](../media/MAM-reporting-7.png)

-   **Alkalmazásvédelmi felhasználói jelentés:** Ugyanazokat az információkat ismerteti, mint a Részletes nézetre vonatkozó fentebbi szakaszban említett **Felhasználói állapot** jelentés.

-   **Alkalmazásvédelmi alkalmazásjelentés:** Két különböző alkalmazásvédelmi állapotot biztosít, melyeket a rendszergazdák kiválaszthatnak a jelentés létrehozása előtt. Az állapot védett vagy nem védett lehet.

    -   Felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (védett): Ez a jelentés az egyes felügyelt MAM-alkalmazások tevékenységeit ismerteti, felhasználónként.

        -   Minden felhasználóhoz olvasható benne azon alkalmazások listája, amelyeket alkalmazásvédelmi szabályzatok céloznak, aszerint csoportosítva, hogy az adott alkalmazásra lettek-e érvényesítve alkalmazásvédelmi szabályzatok, vagy célozza alkalmazásvédelmi szabályzat, de az nem lett érvényesítve az alkalmazásra.
<br></br>
    -   Nem felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (védett): Ez a jelentés a jelenleg nem felügyelt MAM-kompatibilis alkalmazások tevékenységeit ismerteti, felhasználónként. Ez a következő okokból fordulhat elő:

        -   Ezeket az alkalmazásokat egy olyan felhasználó vagy alkalmazás használja, akire vagy amelyre jelenleg nem vonatkozik alkalmazásvédelmi szabályzat.

        -   Minden alkalmazás érvényesítve lett, de nincsenek rájuk vonatkozó alkalmazásvédelmi szabályzatok.

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

* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-android)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-ios)

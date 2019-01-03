---
title: Az alkalmazásvédelmi szabályzatok figyelése
titleSuffix: Microsoft Intune
description: Az Intune-ban figyelheti a mobilalkalmazás-kezelési szabályzatok megfelelőségi állapotát.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c0603b3cfd2b8fbe1d26e782118fb07526849cfa
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816840"
---
# <a name="how-to-monitor-app-protection-policies"></a>Az alkalmazásvédelmi szabályzatok figyelése
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az [Azure Portal](https://portal.azure.com) Intune alkalmazásvédelem paneljén figyelheti a felhasználókra alkalmazott mobilalkalmazás-kezelési (MAM) szabályzatok megfelelőségi állapotát. Itt információkat találhat a MAM-szabályzatok által érintett felhasználókról, azok megfelelőségi állapotáról, valamint a felhasználók által esetlegesen tapasztalt problémákról.

Három különböző helyen figyelheti a megfelelőségi állapotot:

-   Összefoglalás megtekintése

-   Részletes nézet

-   Jelentéskészítés nézet

> [!NOTE]
> Az alkalmazásvédelmi szabályzatok létrehozásával kapcsolatban további információt az [alkalmazásvédelmi szabályzatok létrehozásával és hozzárendelésével](app-protection-policies.md) foglalkozó cikkben talál.

## <a name="summary-view"></a>Összefoglalás megtekintése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** területen válassza a **Figyelés** > **Alkalmazásvédelem állapota** lehetőséget az összefoglaló nézet megjelenítéséhez:

![Az Intune mobilalkalmazás-kezelés panel Összefoglalás csempéje](./media/app-protection-user-status-summary.png)

-   **Felhasználók**: A teljes száma a vállalatnál lévő felhasználóknál, akik a munkahelyi környezetben házirenddel társított alkalmazást használnak.

-   **HÁZIREND ÁLTAL KEZELT**: A felhasználók számát, akik már használtak egy alkalmazást, amelyekre érvényes a szabályzat hozzájuk rendelve a munkahelyi környezetben.

-   **NINCS SZABÁLYZAT**: A felhasználók száma, akik egy alkalmazást, amelyre nem vonatkozik szabályzat nélküli munkahelyi környezetben használja. Érdemes megfontolni ezen felhasználók bevonását a szabályzat hatálya alá.
    > [!NOTE]
    > Platformonként több szabályzat esetén a felhasználó akkor minősül szabályzat által kezeltnek, ha legalább egy szabályzat hozzá van rendelve.

- **Megjelölt felhasználók**: A problémákat tapasztaló felhasználók száma. A rendszer jelenleg a **Megjelölt felhasználók** részben kizárólag a jailbreakelt eszközt használó felhasználókat jelöli meg.


## <a name="detailed-view"></a>Részletes nézet
Ha meg szeretné tekinteni az összefoglalás részleteit, válassza a **Felhasználói állapot** csempét (az eszköz operációsrendszer-platformjának megfelelően), majd a **Megjelölt felhasználók** csempét.

### <a name="user-status"></a>Felhasználó állapota
Itt megkeresheti az adott felhasználókat, és ellenőrizheti a megfelelési állapotukat. Az **Alkalmazásjelentések** panelen a következő információk tekinthetők meg a kiválasztott felhasználóról:
- A felhasználói fiókhoz társított eszközök listája

- Az eszközön futó, MAM-szabályzat hatálya alá tartozó alkalmazások listája

- Állapot:

  - **Beadva**: A házirend telepítve van a felhasználónál, és az alkalmazást munkahelyi környezetben legalább egyszer már használták.

  - **Nincs beadva**: A házirend telepítve van a felhasználónál, de az alkalmazás nem használták a munkahelyi környezetben azóta.

>[!NOTE]
> Ha a keresett felhasználók nem rendelkeznek telepített MAM-szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen MAM-szabályzat sem.Ha a keresett felhasználók nem rendelkeznek telepített MAM-szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen MAM-szabályzat sem.

A felhasználóhoz tartozó jelentések megtekintéséhez kövesse az alábbi lépéseket:

1.  Egy felhasználó kijelöléséhez válassza az **Összefoglalás** csempét.

    ![Képernyőkép az összefoglalás csempére az Intune mobilalkalmazás-kezelés](./media/MAM-reporting-6.png)

2. A megjelenő **Alkalmazásjelentések** panelen válassza a **Felhasználó kijelölése** lehetőséget, és keresse meg a kívánt Azure Active Directory-felhasználót.

    ![Képernyőkép az alkalmazásjelentés panel felhasználó kiválasztása beállításának](./media/MAM-reporting-2.png)

3. Válassza ki a listából a felhasználót. Megjelennek a felhasználó megfelelési állapotára vonatkozó információk.

### <a name="flagged-users"></a>Megjelölt felhasználók
A részletes nézetben látható a hibaüzenet, annak az alkalmazásnak a neve, amelynek a használata közben fellépett a hiba, az eszközök érintett operációsrendszer-platformja, valamint egy időbélyeg.

## <a name="reporting-view"></a>Jelentéskészítés nézet

Itt megtalálhatja a Részletes nézetben is szereplő jelentéseket, illetve további jelentéseket, melyek segítséget nyújtanak a mobilalkalmazás-kezelési szabályzat megfelelőségi állapotával kapcsolatban:

![Képernyőkép a Beállítások panel két elérhető jelentéséről](./media/MAM-reporting-7.png)

-   **Alkalmazásvédelem – felhasználói jelentés:** Ismerteti, ugyanazokat az információkat, annak a **felhasználói állapot** jelentés a részletes nézetben a fenti szakaszban.

-   **Alkalmazásvédelmi alkalmazásjelentés:** Két különböző alkalmazásvédelmi állapotot melyeket a rendszergazdák a jelentés létrehozása előtt biztosít. Az állapot védett vagy nem védett lehet.

    -   Felhasználó állapota felügyelt MAM-tevékenységekre (védett): Ez a jelentés minden egyes felügyelt MAM-alkalmazás, felhasználónkénti alapon tevékenységeit ismerteti.

        -   Megjelenik benne minden olyan alkalmazás az egyes felhasználókra vonatkozóan, melyekre MAM-szabályzatok lettek érvényesítve, illetve az egyes alkalmazások állapotának felbontása aszerint, hogy az adott alkalmazásra lettek-e érvényesítve MAM-szabályzatok, vagy vonatkozik rá egy MAM-szabályzat, de az nem lett érvényesítve az alkalmazásra.
<br></br>
    -   Felhasználó állapota nem felügyelt MAM-tevékenységekre (védett): Ez a jelentés a jelenleg nem felügyelt, felhasználónkénti alapon MAM-kompatibilis alkalmazások tevékenységeit ismerteti. Ez a következő okokból fordulhat elő:

        -   Ezeket az alkalmazásokat egy olyan felhasználó vagy alkalmazás használja, akire vagy amelyre jelenleg nem vonatkozik MAM-szabályzat.

        -   Minden alkalmazás érvényesítve lett, de nincsenek rájuk vonatkozó MAM-szabályzatok.

![Képernyőkép egy felhasználói alkalmazásjelentések panelen adatokkal 3 alkalmazások](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Táblacsoportosítás

Amint az **alkalmazásvédelmi felhasználói jelentés** adatai megjelennek, az alábbiak szerint összesítheti azokat:

- **Ellenőrzés eredménye:** Az adatok megjelenik-e alkalmazásvédelmi állapot, amely lehet hiba, figyelmeztetés vagy sikeres szerint csoportosítva.
- **Alkalmazásnév:** Az adatokat jelenít meg hiba, figyelmeztetés vagy sikeres alkalmazások (a tényleges alkalmazásnév) szerint csoportosítva.

## <a name="export-app-protection-activities-to-csv"></a>Az alkalmazásvédelmi tevékenységek exportálása CSV-fájlba

Az alkalmazásvédelmi szabályzatokkal kapcsolatos összes tevékenységet egyetlen .csv-fájlba exportálhatja. Ez hasznos lehet az összes, a felhasználók felől jelentett alkalmazásvédelmi állapot elemzésében.

Az alkalmazásvédelmi jelentés létrehozásához kövesse az alábbi lépéseket:

1. Az Intune-os mobilalkalmazás-kezelés paneljén válassza az **Alkalmazásvédelmi jelentés** lehetőséget.

    ![Az App protection letöltési hivatkozás képernyőképe](./media/app-protection-report-csv-2.png)

2. Válassza az Igen lehetőséget a jelentés mentéséhez, majd válassza a Mentés másként lehetőséget, és válassza ki azt a mappát, ahova a jelentést menteni szeretné.

    ![Képernyőkép a Jelentés mentése jóváhagyó mezőről](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Lásd még:
[iOS-alkalmazások közti adatátvitel kezelése](data-transfer-between-apps-manage-ios.md)

* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)

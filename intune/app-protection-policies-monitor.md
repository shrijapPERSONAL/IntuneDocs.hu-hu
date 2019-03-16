---
title: Az alkalmazásvédelmi szabályzatok figyelése
titleSuffix: Microsoft Intune
description: Ez a témakör ismerteti, hogyan figyelheti az Intune-ban mobilalkalmazás-felügyeleti szabályzatok megfelelőségi állapotát.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cee1cbc05164a418148ecea8d93f6c8c45c73e01
ms.sourcegitcommit: c4258bb5824daf3f7e0ac3bb8afc539bde4d95da
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/16/2019
ms.locfileid: "57991136"
---
# <a name="how-to-monitor-app-protection-policies"></a>Az alkalmazásvédelmi szabályzatok figyelése
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazott a felhasználók számára az Intune app protection panel az a mobilalkalmazás-felügyeleti (MAM) szabályzatok megfelelőségi állapotát figyelemmel kísérheti a [az Azure portal](https://portal.azure.com). Ezenkívül a MAM-szabályzatok, mobilalkalmazás-kezelési szabályzat megfelelőségi állapot és az esetlegesen tapasztalt problémákat által érintett felhasználók adatait is megtalálhatja.

Nincsenek három különböző helyen figyelheti a MAM-szabályzatok megfelelőségi állapotát:
-   Összefoglalás megtekintése
-   Részletes nézet
-   Jelentéskészítés nézet

> [!NOTE]
> Az alkalmazásvédelmi szabályzatok létrehozásával kapcsolatban további információt az [alkalmazásvédelmi szabályzatok létrehozásával és hozzárendelésével](app-protection-policies.md) foglalkozó cikkben talál.

## <a name="summary-view"></a>Összefoglalás megtekintése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az a **ügyfélalkalmazások** területen válassza a **alkalmazásvédelem állapota** a a **figyelő** szakaszban, az összefoglaló nézet megjelenítéséhez:

![Az Intune mobilalkalmazás-kezelés panel Összefoglalás csempéje](./media/app-protection-user-status-summary.png)

- **Hozzárendelt felhasználók**: Egy alkalmazást, amely a munkahelyi környezetben a szabályzathoz társított védett és licencelt, valamint a hozzárendelt felhasználók nem védett és licencelt használó a vállalatnál hozzárendelt felhasználók teljes száma.
- **Megjelölt felhasználók**: A problémákat tapasztaló felhasználók száma. Értékelni a feltört eszközöket jelentett alatt **megjelölt felhasználók**.
- **Felhasználó állapota (iOS)** és **felhasználói állapot (Android)**: A felhasználók számát, akik már használtak egy alkalmazást, amelyekre érvényes a szabályzat hozzájuk rendelve a munkahelyi környezetben a kapcsolódó platform. Ezt az információt a házirend, valamint a felhasználók száma, akik használ egy alkalmazást, amelyre nem vonatkozik szabályzat nélküli munkahelyi környezetben kezeli a felhasználók számát jeleníti meg. Érdemes megfontolni ezen felhasználók bevonását a szabályzat hatálya alá.
- **Legnépszerűbb védett iOS-alkalmazások**: A leggyakrabban használt iOS-alkalmazások alapján, ezeket az adatokat a védett, és nem védett iOS-alkalmazások számát jeleníti meg.
- **Legnépszerűbb védett Androidos alkalmazások**: A leggyakrabban használt Android-alkalmazások alapján, ezeket az adatokat a védett, és nem védett Androidos alkalmazások számát jeleníti meg.
- **Az első konfigurált iOS-eszközök regisztrálása nélkül alkalmazások**: A leggyakrabban használt iOS-alkalmazások a nem regisztrált eszközök alapján, ezeket az információkat a beállított iOS-alkalmazások számát jeleníti meg.
- **A leggyakoribb konfigurált, Android-alkalmazások regisztráció nélkül**: A leggyakrabban használt Android-alkalmazások a nem regisztrált eszközök alapján, az ezeket az információkat a konfigurált Android-alkalmazások számát jeleníti meg.

    > [!NOTE]
    > Platformonként több szabályzat van, ha a felhasználó akkor minősül, szabályzat által kezeltnek, ha van legalább egy szabályzat rendelve.

## <a name="detailed-view"></a>Részletes nézet
Ha meg szeretné tekinteni az összefoglalás részleteit, válassza a **Felhasználói állapot** csempét (az eszköz operációsrendszer-platformjának megfelelően), majd a **Megjelölt felhasználók** csempét.

### <a name="user-status"></a>Felhasználó állapota
Itt megkeresheti az adott felhasználókat, és ellenőrizheti a megfelelési állapotukat. Az **Alkalmazásjelentések** panelen a következő információk tekinthetők meg a kiválasztott felhasználóról:
- **Ikon**: Megjeleníti, hogy naprakészek-e az alkalmazás állapota.
- **Alkalmazásnév**: Az alkalmazás neve.
- **Eszköz neve**: A felhasználói fiókhoz társított eszközök.
- **Eszköz típusa**: Az eszköz fut az eszköz vagy az operációs rendszer típusa.
- **Házirendek**: A házirendek az alkalmazáshoz társított.
- **Állapot**:
  - **Beadva**: A házirend telepítve van a felhasználónál, és az alkalmazást munkahelyi környezetben legalább egyszer már használták.
  - **Nincs beadva**: A házirend telepítve van a felhasználónál, de az alkalmazás nem használták a munkahelyi környezetben azóta.
- **Utolsó szinkronizálás**: Ha az eszköz volt a legutóbbi szinkronizálásra.

>[!NOTE]
> Ha a keresett felhasználók nem rendelkeznek telepített MAM-szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen MAM-szabályzat sem.Ha a keresett felhasználók nem rendelkeznek telepített MAM-szabályzattal, egy üzenet jelenik meg, amely arról tájékoztatja, hogy a felhasználóra nem vonatkozik egyetlen MAM-szabályzat sem.

A felhasználóhoz tartozó jelentések megtekintéséhez kövesse az alábbi lépéseket:

1.  Válasszon ki egy felhasználót, válassza a **felhasználói állapot** összefoglaló csempét.

    ![Képernyőkép az összefoglalás csempére az Intune mobilalkalmazás-kezelés](./media/MAM-reporting-6.png)

2. A megjelenő **Alkalmazásjelentések** panelen válassza a **Felhasználó kijelölése** lehetőséget, és keresse meg a kívánt Azure Active Directory-felhasználót.

    ![Képernyőkép az alkalmazásjelentés panel felhasználó kiválasztása beállításának](./media/MAM-reporting-2.png)

3. Válassza ki a listából a felhasználót. Megjelennek a felhasználó megfelelési állapotára vonatkozó információk.

### <a name="flagged-users"></a>Megjelölt felhasználók
A részletes nézetben látható a hibaüzenet, annak az alkalmazásnak a neve, amelynek a használata közben fellépett a hiba, az eszközök érintett operációsrendszer-platformja, valamint egy időbélyeg.

## <a name="reporting-view"></a>Jelentéskészítés nézet

Az azonos jelentések tetején találhatók a **alkalmazásvédelmi állapot** panelen.

> [!NOTE]
> Az Intune további eszköz területén, beleértve az alkalmazás regisztrációs azonosító, Android gyártója, modell, és biztonsági javítást, valamint IOS-es modell reporting biztosít. Az Intune-ban, ezek a mezők érhetők el kiválasztásával **ügyfélalkalmazás** > **alkalmazásvédelmi állapot** választva **alkalmazásvédelmi jelentés: iOS, Android**. Emellett ezek a paraméterek segítségével konfigurálja a **engedélyezése** lista az eszköz gyártója (Android), a **engedélyezése** lista az eszköz modellje (Android és iOS) és a minimális Android biztonsági javítási szintnek verzió beállítását. 

További jelentések érhetők el segíti a MAM-szabályzat megfelelőségi állapotát. Ezek a jelentések megtekintéséhez jelölje ki **ügyfélalkalmazás** > **alkalmazásvédelmi állapot** > **jelentések**. 

A **jelentések** panel nyújt több olyan jelentést, a felhasználó és az alkalmazás többek között az alábbiak alapján:


- **Felhasználói jelentés**: Ez a jelentés említett ugyanazokat az információkat ismerteti a **felhasználói állapot** alatt a [részletes nézet](app-protection-policies-monitor.md#detailed-view) című fenti szakaszban.

- **Alkalmazásjelentés**: Jelölje meg a platformot és alkalmazást, ez a jelentés tartalmazza a két különböző alkalmazásvédelmi állapotot választhat a jelentés létrehozása előtt. Az állapotok lehet **védett** vagy **nem védett**.

    -   Felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (**védett**): Ez a jelentés minden egyes felügyelt MAM-alkalmazás, felhasználónkénti alapon tevékenységeit ismerteti. Megjelenik benne minden olyan alkalmazás az egyes felhasználókra vonatkozóan, melyekre MAM-szabályzatok lettek érvényesítve, illetve az egyes alkalmazások állapotának felbontása aszerint, hogy az adott alkalmazásra lettek-e érvényesítve MAM-szabályzatok, vagy vonatkozik rá egy MAM-szabályzat, de az nem lett érvényesítve az alkalmazásra.
    -   Nem felügyelt MAM-tevékenységekre vonatkozó felhasználói állapot (**nem védett**): Ez a jelentés a jelenleg nem felügyelt, felhasználónkénti alapon MAM-kompatibilis alkalmazások tevékenységeit ismerteti. Ez a következő okokból fordulhat elő:
        -   Ezeket az alkalmazásokat egy olyan felhasználó vagy alkalmazás használja, akire vagy amelyre jelenleg nem vonatkozik MAM-szabályzat.
        -   Minden alkalmazás érvényesítve lett, de nincsenek rájuk vonatkozó MAM-szabályzatok.

        ![Képernyőkép egy felhasználói alkalmazásjelentések panelen adatokkal 3 alkalmazások](./media/MAM-reporting-4.png)

- **Felhasználói konfigurációról készült jelentés**: A kiválasztott felhasználó alapján, ez a jelentés a felhasználó kapott alkalmazáskonfigurációt részletesen ismerteti.
- **Alkalmazáskonfigurációs jelentés**: Alapszámláló a kiválasztott platform és az alkalmazás, az ebben a jelentésben arról, hogy mely felhasználók kapott konfiguráció a kiválasztott alkalmazáshoz tartozó részletek.
- **App learning-jelentése Windows Information Protection**: Ez a jelentés mutatja meg, mely alkalmazások próbált házirend határok adatbázisközi.
- **Windows Information Protection learning webhely**: Ez a jelentés mutatja meg, mely webhelyeket próbál adatbázisközi házirend határok.

## <a name="table-grouping"></a>Táblacsoportosítás

Miután a **alkalmazásvédelmi felhasználói jelentés** adatai jelennek meg, az alábbiak szerint összesítheti azokat:

- **Ellenőrzés eredménye:** Az adatok megjelenik-e alkalmazásvédelmi állapot, amely lehet hiba, figyelmeztetés vagy sikeres szerint csoportosítva.
- **Alkalmazásnév:** Az adatokat jelenít meg hiba, figyelmeztetés vagy sikeres alkalmazások (a tényleges alkalmazásnév) szerint csoportosítva.

## <a name="export-app-protection-activities-to-csv"></a>Az alkalmazásvédelmi tevékenységek exportálása CSV-fájlba

Minden az alkalmazásvédelmi szabályzat tevékenységek exportálhatja egy *.csv* fájlt. Ez hasznos lehet az összes, a felhasználók felől jelentett alkalmazásvédelmi állapot elemzésében.

Az alkalmazásvédelmi jelentés létrehozásához kövesse az alábbi lépéseket:

1. Az Intune-os mobilalkalmazás-kezelés paneljén válassza az **Alkalmazásvédelmi jelentés** lehetőséget.

    ![Az App protection letöltési hivatkozás képernyőképe](./media/app-protection-report-csv-2.png)

2. Válasszon **Igen** a jelentés mentéséhez, majd válassza ki **Mentés másként** , és válassza ki a mappát a jelentést menteni szeretné.

    ![Képernyőkép a Jelentés mentése jóváhagyó mezőről](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Lásd még:
- [iOS-alkalmazások közti adatátvitel kezelése](data-transfer-between-apps-manage-ios.md)
- [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
- [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)

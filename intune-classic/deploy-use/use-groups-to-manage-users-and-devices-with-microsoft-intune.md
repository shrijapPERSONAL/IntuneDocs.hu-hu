---
title: Csoportok használata felhasználók és eszközök kezelésére
description: Csoportok létrehozása és kezelése a Csoportok munkaterület használatával.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f84469f0514d2e644db2ec9b0700644af143d81
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a>Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör ismerteti, hogy hogyan lehet csoportokat létrehozni az Intune-ban. Azt is megtudhatja belőle, hogy hogyan változik majd a csoportok kezelése az elkövetkező hónapok során. 

>[!IMPORTANT]
>
>Ha az Intune-portál Csoportok munkaterületét megnyitva megjelenik egy hivatkozás, amely az Azure Active Directory (Azure AD) portálra mutat, akkor ön az *új* Azure AD biztonságicsoport-alapú csoportkezelését használja az Intune-ban, amelynek ismertetése a [Csoportok áttelepítése az Azure Active Directoryba](migrating-groups-to-azure-active-directory.md) című részben található. Kattintson az Azure AD-portálra mutató hivatkozásra.
>
>![Képernyőkép az Azure csoportfelügyeletre mutató hivatkozásról](../media/groups-link-azure.png) 
>
>Ha nem látja az Azure AD-portálra mutató hivatkozást, akkor Ön még a *jelenlegi* csoportkezelési módszert használja, amelynek leírása a jelen témakör [Csoportok létrehozása](#create-groups) című részében található.

Ez a témakör azt ismerteti, hogy hogyan hozhat létre Intune-csoportokat az Intune felügyeleti konzolján.

Csoportok létrehozásához és kezeléséhez lépjen a **Csoportok** munkaterületre a Microsoft Intune felügyeleti konzolon. A **Csoportok áttekintése** oldalon olyan állapotösszegzések láthatók, amelyek segíthetnek az intézkedést igénylő problémák azonosításában és rangsorolásában. Az állapotösszegzések a következő területeket fedik le:

-   Riasztások
-   Szoftverfrissítések
-   Endpoint Protection
-   Házirend
-   Szoftverkezelés

A csoporthierarchia is megjelenít állapotösszegzéseket, amelyek segítenek azonosítani és megoldani a kiválasztott csoport tagjaival kapcsolatos problémákat.

## <a name="create-groups"></a>Csoportok létrehozása

> [!TIP]
> A csoportok létrehozásakor gondolja át, hogyan szeretné alkalmazni a szabályzatokat. Lehetnek például az eszközök operációs rendszereire szabott, vagy a szervezet különböző szerepköreinek, illetve az Active Directoryban már definiált szervezeti egységeknek megfelelő szabályzatok. Hasznos lehet külön eszközcsoportokat létrehozni az iOS, Android és Windows operációs rendszerekhez rendelt eszközcsoportok számára, valamint külön felhasználói csoportokat az egyes szerepekörök számára a szervezeten belül.
>
> Érdemes létrehozni egy valamennyi csoportra és eszközre vonatkozó alapértelmezett szabályzatot a szervezetre vonatkozó alapvető megfelelőségi követelmények meghatározásához. Ezt követően létrehozhatók részletesebb szabályzatok a felhasználók és eszközök legszélesebb kategóriáira. Létrehozhat például levelezési szabályzatokat az eszközök különböző operációs rendszerei számára.
>
> A későbbi könnyű azonosíthatóság érdekében érdemes odafigyelni a szabályzatok elnevezésére. Ilyen könnyen érthető, leíró szabályzatnév lehet például a következő: **WP e-mail szabályzat a teljes vállalat számára**.
>
> Valahányszor korlátozó szabályzatot hoz létre, arról értesíteni kell a felhasználókat. A felesleges kommunikáció csökkentése érdekében az általánosabb csoportok és szabályzatok létrehozása után különösen ügyeljen a kisebb csoportok létrehozására.

## <a name="to-create-a-device-group"></a>Eszközcsoport létrehozása

1.  Az Intune felügyeleti konzolján kattintson a **Csoportok** &gt; **Áttekintés** &gt; **Csoport létrehozása** elemre.

2.  Adja meg a csoport nevét és leírását (az utóbbi nem kötelező), majd válasszon egy eszközcsoportot szülőcsoportként. Kattintson a **Tovább** gombra.

3.  A **Tagság feltételeinek meghatározása** oldalon válassza ki, hogy a csoport milyen típusú eszközökből álljon. A kiválasztott eszközök típusán alapuló további konfigurációs lehetőségek között szerepelnek a következők:

    -   **Számítógép**. Megadhatja, hogy a szülőcsoport minden tagját fel kívánja-e venni a csoportba, illetve meghatározhatja a felvenni és kizárni kívánt szervezeti egységeket és tartományokat. A számítógép szervezeti egységére és tartományára vonatkozó információk a leltárból érhetők el.

    -   **Mobil**. Megadhatja, hogy csak az Intune, csak az Exchange ActiveSync vagy mindkettő által felügyelt eszközök tartozzanak a csoportba.

    -   **Minden eszköz**. Ez a beállítás minden eszközt magában foglal, feltételeken alapuló kivételek nélkül.

4.  A **Közvetlen tagság meghatározása** oldalon a **Tallózás** lehetőséget választva vonhat be vagy zárhat ki egyedi eszközöket. Ha olyan eszközöket választ ki, amelyek nem tagjai a megadott szülőcsoportnak, akkor az Intune ezeket automatikusan hozzáadja a szülőcsoporthoz.

5.  Az **Összegzés** lapon ellenőrizze a beállításokat, majd kattintson a **Befejezés** gombra.

Az újonnan létrehozott csoport megjelenik a **Csoportok** munkaterület **Csoportok** listáján, a szülőcsoport alatt. Ugyanitt szerkesztheti és törölheti is a csoportot.

## <a name="to-create-a-user-group"></a>Felhasználói csoport létrehozása

1.  Az Intune felügyeleti konzolján kattintson a **Csoportok** &gt; **Áttekintés** &gt; **Csoport létrehozása** elemre.

2.  Adja meg a csoport nevét és leírását (az utóbbi nem kötelező), majd válasszon egy felhasználói csoportot szülőcsoportként. Kattintson a **Tovább** gombra.

3.  A **Tagság feltételeinek meghatározása** oldalon válassza ki, hogy a szülőcsoport minden tagját be kívánja-e vonni vagy inkább üres csoportot használ első lépésként. Ezután bevonhat vagy kizárhat tagokat a felhasználók olyan biztonsági csoportjai alapján, amelyeket vagy manuálisan konfigurál az [Office 365 felügyeleti központjában](http://go.microsoft.com/fwlink/?LinkId=698854), vagy az Active Directoryból szinkronizál. Ha egy biztonsági csoport tagsága megváltozik, akkor az azon a csoporton alapuló felhasználói csoportok tagsága is módosulhat.

    > [!IMPORTANT]
    > Jelenleg ha a csoport meghatározott biztonsági, illetve menedzseri csoportokból tartalmaz tagokat, és kizárja meghatározott csoportok tagjait, a rendszer eltávolítja a korábban bevont tagokat. Az javasoljuk, hogy olyan csoport létrehozásához, amely egyaránt tartalmaz bevont és kizárt tagokat, mindenekelőtt hozzon létre egy szülőcsoportot, amely a bevont tagokat tartalmazza. Ezután hozzon létre ehhez a szülőcsoporthoz egy gyermekcsoportot. Az új gyermekcsoportban adja meg a kizárt tagok listáját. Ezt a gyermekcsoportot használja az Intune szabályzatainak, profiljainak és alkalmazás-terjesztésének kezelésére.

    > [!NOTE]
    > Az Azure-portálon létrehozhat csoportokat a felhasználók felettesei alapján. Az ilyen csoport dinamikus és aszerint változik, ahogy az Azure Active Directoryban alkalmazottakat adnak hozzá az adott menedzser csapatához vagy távolítanak el onnan. Az Azure-csoportok menedzser alapján történő létrehozását a [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) (Speciális szabályok létrehozása attribútumokkal) című témakör **To configure a group as a “Manager” group** (Csoport konfigurálása „Menedzser” csoportként) című szakasza ismerteti.

4.  A **Közvetlen tagság meghatározása** oldalon a **Tallózás** lehetőséget választva vonhat be vagy zárhat ki egyedi felhasználókat. Ha olyan felhasználókat választ ki, akik nem tagjai a megadott szülőcsoportnak, akkor ezeket a rendszer automatikusan hozzáadja a szülőcsoporthoz. A **Tagok kiválasztása** párbeszédpanel alsó részén található a felhasználó manuális felvételére szolgáló beállítás. Ez akkor hasznos, ha olyan felhasználót szeretne felvenni a csoportba, aki még nem rendelkezik regisztrált eszközzel.

5.  Az **Összegzés** lapon ellenőrizze a beállításokat, majd kattintson a **Befejezés** gombra.

Az újonnan létrehozott csoport megjelenik a **Csoportok** munkaterület **Csoportok** listáján, a szülőcsoport alatt. Ugyanitt szerkesztheti és törölheti is a csoportot.

> [!TIP]
> A biztonsági csoportok jól használhatók a felhasználói csoportok feltöltésekor. Mivel a biztonsági csoportok határozzák meg, hogy mely erőforrásokhoz kinek van hozzáférése, azok egyszerűen leképezhetők Intune felhasználói csoportokra. Azok a biztonsági csoportok, amelyeket az Active Directoryból szinkronizált az Azure Active Directoryba, illetve amelyeket közvetlenül az Azure Active Directoryban hoz létre az Office 365 Felügyeleti központban vagy az Azure felügyeleti portálján, mind elérhetők a felhasználói csoportok létrehozásához az Intune-ban.

## <a name="filter-admin-views-by-role"></a>Felügyeleti nézetek szűrése szerepkör alapján
A szűrt csoportnézetekben szabható meg, hogy szerepköre alapján mit láthat a rendszergazda. A szűrt csoportnézetek révén az egyes rendszergazdák által kezelhető csoportok köre is korlátozható. Ez a következő esetekben lehet hasznos:

-   Azt szeretné, hogy a rendszergazdák csak bizonyos felhasználókra és eszközökre vonatkozóan végezhessenek központi telepítéseket
-   Azt szeretné, hogy a rendszergazdák csak a számukra releváns csoportokat láthassák

A szolgáltatás-rendszergazdák számára az Intune felügyeleti konzolján állíthat be szűrt csoportnézeteket. Részletekért lásd: [Tudnivalók a Microsoft Intune elindítása előtt](/intune/supported-devices-browsers).

Miután beállította a szűrt csoportnézeteket valamelyik szolgáltatás-rendszergazda számára, akkor, amikor az illető rendszergazda szoftverek vagy szabályzatok központi telepítését végzi vagy jelentéseket futtat, csak a meghatározott csoportokat láthatja és választhatja ki. Emellett a rendszergazda számára a felügyeleti konzol alábbi oldalain nem jelennek meg állapotinformációk:

-   **Rendszer áttekintése**
-   **Csoportok áttekintése**
-   **Az Endpoint Protection áttekintése**
-   **Riasztások áttekintése**
-   **Szoftverek áttekintése**
-   **Szabályzatok áttekintése**

### <a name="to-create-a-filtered-group-view"></a>Szűrt csoportnézetek konfigurálása

1.  Az Intune felügyeleti konzolon válassza a **Felügyelet** &gt; **Rendszergazdák kezelése** &gt; **Szolgáltatás-rendszergazdák** lehetőséget.

2.  Válassza ki a szolgáltatás-rendszergazdát, akihez szűrt csoportnézetet kíván létrehozni, majd válassza a **Csoportok kezelése** lehetőséget.

3.  A **Szolgáltatás-rendszergazda számára látható csoportok kiválasztása** párbeszédpanelen adja hozzá azokat a csoportokat, amelyekhez a rendszergazda hozzáférhet, majd kattintson az **OK**gombra.

Miután konfigurálta a szűrt csoportnézeteket, a rendszergazda csak a kiválasztott csoportokat tudja megnézni és kijelölni.

## <a name="manage-your-groups"></a>Csoportok kezelése
Létrehozásuk után a csoportokat a szervezet igényeinek megfelelően kezelheti.

Szerkesztheti a csoportot, hogy módosítsa a nevét, leírását és a hozzá tartozó felhasználókat.

Ha úgy látja, hogy egy csoport már nem szükséges a szervezet számára, törölheti az Intune-ból. A csoport törlése nem érinti a csoporthoz tartozó felhasználókat.

## <a name="next-steps"></a>További lépések
A csoportok és szabályzatok beállítását követően a **Kívánt érték** és az **Állapot** alapján ellenőrizheti a felügyelet gyakorlati megvalósítását.

### <a name="to-check-your-design"></a>A megvalósítás ellenőrzése

1. Válassza ki bármelyik eszközt valamelyik eszközcsoportból, és tallózzon a képernyő tetején található információs kategóriák között.
2. Válassza a **Szabályzat** lehetőséget. Az Androidos eszközök házirend-beállításaihoz tartozó alábbi képernyőfelvételéhez hasonlót fog látni.

![Android szabályzat-beállítás – példa](../media/Intune-Device-Policy-v.2.jpg)

Minden egyes házirend rendelkezik egy **Kívánt érték** és egy **Állapot**jellemzővel. A kívánt érték az az érték, amelyet a szabályzat hozzárendelésekor el kívánt érni. Az állapot az eszközre érvényes valamennyi szabályzat alkalmazása, valamint a hardver és az operációs rendszer által szabott korlátozások és rendszerkövetelmények együttese alapján elért érték. Ezen a képernyőfelvételen két egyszerű példa látható:

-   Az **Egyszerű jelszavak engedélyezése** beállított értéke **Igen**, ahogy az a **Kívánt érték** oszlopban látható, az **Állapot** értéke azonban **Nem alkalmazható**. Ez azért van, mert az egyszerű jelszavak az Android-eszközökön nem támogatottak.
-   Ehhez hasonlóan az **iOS-eszközök e-mail beállításai** kiterjesztett szabályzat erre az eszközre nem alkalmazható, mivel ez egy Android-eszköz.

> [!NOTE]
> Ne feledje, hogy ha két különböző korlátozási szintű szabályzat vonatkozik egy eszközre vagy felhasználóra, akkor a gyakorlatban a szigorúbb szabályzat lesz érvényes.

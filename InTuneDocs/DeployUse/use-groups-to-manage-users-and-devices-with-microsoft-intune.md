---
title: "Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal | Microsoft Intune"
description: "Csoportokat hozhat létre és kezelhet a Csoportok munkaterületről."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab9592c253238fd832f8b48372e5474fcfc5331
ms.openlocfilehash: 96b0cd997544b2013efaca818d614c9802baaa46


---
## Értesítés a csoportkezeléssel kapcsolatos rendszergazdai feladatok fejlesztéséről

A felhasználók jelezték, hogy egységes csoportosítási és célcsoport-kezelési felületet szeretnének a Nagyvállalati mobilitás + biztonság egészéhez, ezért az Intune-csoportokat átalakítjuk Azure Active Directory-alapú biztonsági csoportokká. Ez egységesíti a csoportfelügyeletet az Intune és az Azure Active Directory (Azure AD) egészében. Az új felület jóvoltából a jövőben nem kell csoportokat duplikálni a szolgáltatások között, és támogatott lesz PowerShell- és a Graph-alapú bővíthetőség is. 

### Hogyan érint ez engem jelen pillanatban?
A változás most még nem érinti Önt, de eláruljuk, mi várható:

-   Szeptembertől a havi szolgáltatásverzió kiadása után létesített új fiókok már az Azure AD-alapú biztonsági csoportokat fogják használni az Intune-os felhasználói csoportok helyett.   
-   Októbertől a havi szolgáltatásverzió kiadása után létesített új fiókok a felhasználó- és eszközalapú csoportokat is az Azure AD portálján kezelik majd. A meglévő ügyfeleket nem érinti
-   Novemberben az Intune-termékcsapat elkezdi a meglévő ügyfelek migrálását az új, Azure AD-alapú csoportfelügyeleti rendszerbe. A jelenleg az Intune-ban lévő felhasználó- és eszközcsoportok mindegyike migrálva lesz az Azure AD-alapú biztonsági csoportokba. A migrálás novemberben kezdődik, és kötegekben történik. Mindaddig nem kezdjük meg a migrálást, amíg nem sikerül minimalizálni annak hatását a napi munkára, és nem biztosított, hogy a végfelhasználók semmiféle hatást ne érzékeljenek. A fiókjuk áttelepítését megelőzően is küldünk értesítést.


### Hogyan és mikor kerülök át az új csoportkezelési rendszerbe?
A meglévő ügyfelek migrálása nem azonnal, hanem folyamatosan történik. A migrálás ütemezését jelenleg véglegesítjük, és néhány héten belül további információkkal frissítjük ezt a témakört. A migrálás előtt értesíteni fogjuk. Ha bármilyen kérdése vagy problémája van a migrálással kapcsolatban, kérjük, forduljon a migrálási csapathoz az [intunegrps@microsoft.com](intunegrps@microsoft.com) címen.

### Mi történik a meglévő felhasználó- és eszközcsoportjaimmal?
 Az Ön által létrehozott felhasználó- és eszközcsoportok átkerülnek az Azure AD-alapú biztonsági csoportokba. Az olyan alapértelmezett Intune-csoportok, mint a Minden felhasználó, csak akkor lesznek migrálva, ha a migrálás időpontjában üzemelő példányokban használják őket. Bizonyos csoportok esetében a migrálás összetettebb feladatot képezhet; értesítjük, ha további lépések szükségesek.

### Milyen új funkciókat érhetek el?
A bevezetésre kerülő új funkciók:

-    Az Intune minden telepítéstípus esetében támogatni fogja az Azure AD-alapú biztonsági csoportokat.
-    Az Azure AD-alapú biztonsági csoportok támogatni fogják az eszközök csoportosítását a felhasználók csoportosításával együtt.
-    Az Azure AD-alapú biztonsági csoportok támogatni fogják az Intune-eszközattribútumokkal rendelkező dinamikus csoportokat. Lehetséges lesz többek között platform (például iOS) alapján dinamikusan csoportosítani az eszközöket. Így amikor új iOS-eszközt regisztrálnak a szervezetnél, az automatikusan hozzáadódik az iOS dinamikus eszközcsoporthoz.
-    Egységes csoportfelügyelet az Azure AD-ben és az Intune-ban.
- Az Azure AD-be bekerül az *Intune-szolgáltatásadminisztrátor* szerepkör, így az Intune szolgáltatásadminisztrátorai az Azure AD-ben is végrehajthatnak csoportfelügyeleti feladatokat.




### Mely Intune-funkciók nem lesznek elérhetők?
Jóllehet a csoportfelügyelet minősége javulni fog, vannak olyan Intune-funkciók, amelyek a migrálás után elérhetetlenné válnak.

#### Csoportfelügyeleti funkciók

-   Új csoport létrehozásakor nem lesz lehetséges tagok vagy csoportok kizárása. Az Azure AD-alapú dinamikus csoportok ugyanakkor lehetővé teszik, hogy attribútumok alkalmazásával összetett szabályokat alakítson ki bizonyos tagok feltételalapú kizárására.
-   A **Nem csoportosított felhasználók** és a **Nem csoportosított eszközök** csoportjai nem támogatottak. Ezek csoportok nem kerülnek migrálásra.


#### Csoportfüggő funkciók

-   A Szolgáltatásadminisztrátor szerepkör nem rendelkezik majd **Csoportok kezelése** engedéllyel.
-   Az Exchange ActiveSync-eszközök nem lesznek csoportosíthatók.  A **Minden EAS által kezelt eszköz** csoport csoportnézetből jelentésnézetté alakul.
-  A jelentésekben nem lesz elérhető a csoportok alapján történő kimutatás.
-  Az értesítési szabályok egyedi csoportcélzási lehetősége megszűnik.

### Hogyan készüljek fel a változásra?
 A következőket ajánljuk a zökkenőmentes átállás érdekében:

- A migrálás előtt töröljön minden olyan Intune-csoportot, amelyre nincs szüksége.
- Vizsgálja felül a csoportokból való kizárás eddigi használatát, és próbálja meg úgy átalakítani a csoportokat, hogy a jövőben ne legyen szüksége erre a funkcióra.
-  Ha vannak olyan rendszergazdák, akik számára nem engedélyezett csoportok létrehozása az Azure AD-ben, kérje meg Azure AD-rendszergazdáját, hogy adja hozzá őket az **Intune-szolgáltatásadminisztrátor** Azure AD-szerepkörhöz.


# Csoportok létrehozása felhasználók és eszközök kezelésére a Microsoft Intune-nal

Ez a szakasz azt ismerteti, hogy hogyan hozhat létre Intune-csoportokat az Intune felügyeleti konzolján.

Csoportok létrehozásához és kezeléséhez lépjen a **Csoportok** munkaterületre a Microsoft Intune felügyeleti konzolon. A **Csoportok áttekintése** oldal olyan állapotösszegzéseket tartalmaz, amelyek segítenek az alábbiakkal kapcsolatos problémák kezelésében és rangsorolásában:

-   Riasztások
-   Szoftverfrissítések
-   Endpoint Protection
-   Házirend
-   Szoftverkezelés

Emellett a csoporthierarchia is megjelenik összesítő állapotinformációkkal, amelyek segítenek azonosítani és megoldani a kiválasztott csoport adott tagjaival kapcsolatos problémákat.


> [!TIP]
> A csoportok létrehozásakor fontolja meg a házirend alkalmazási módját. Például rendelkezhet az eszköz operációs rendszerére szabott házirendekkel, illetve a szervezeten belüli különböző szerepeknek vagy az Active Directory-ban már megadott szervezeti egységeknek megfelelő házirendekkel. Bizonyos esetekben hasznos lehet az iOS, Android és Windows operációs rendszerekhez rendelt eszközcsoportok, valamint az egyes szervezeti szerepekhez tartozó felhasználói csoportok létrehozása.
>
> Érdemes létrehozni egy valamennyi csoportra és eszközre vonatkozó alapértelmezett házirendet a vállalatára érvényes alapszintű megfelelőségi követelmények meghatározásához. Ezután hozzon létre a felhasználók és az eszközök legszélesebb kategóriáira szabott házirendeket, például az eszközök különféle operációs rendszereire vonatkozó levelezési házirendeket.
>
> A későbbi könnyű azonosíthatóság érdekében figyelmesen járjon el a házirend elnevezésekor. Egy megfelelő, leíró házirendnév például a következő lehet: **WP e-mail házirend a teljes vállalat számára**.
>
> Szigorú házirendek létrehozásakor minden esetben érdemes tájékoztatni a felhasználókat, így a szükségtelen kommunikáció csökkentése érdekében az általánosabb csoportok és házirendek létrehozása után különös figyelemmel hozza létre a kisebb csoportokat.


## Eszközcsoport létrehozása

1.  Az Intune felügyeleti konzolján kattintson a **Csoportok** &gt; **Áttekintés** &gt; **Csoport létrehozása** elemre.

2.  Adja meg a csoport nevét és leírását (az utóbbi nem kötelező), majd válasszon egy eszközcsoportot szülőcsoportként. Kattintson a **Tovább** gombra.

3.  A **Tagság feltételeinek meghatározása** oldalon válassza ki, hogy a csoport milyen típusú eszközökből álljon. A csoport konfigurálásának további lehetőségei a kiválasztott eszköztípustól függnek:

    -   **Számítógép:** Megadhatja, hogy a szülőcsoport minden tagját be kívánja-e vonni a csoportba, illetve meghatározhatja a bevonni és kizárni kívánt szervezeti egységeket és tartományokat. Egy számítógép szervezeti egységekre és tartományokra vonatkozó adatait a leltár tartalmazza.

    -   **Mobileszközök:** Megadhatja, hogy csak az Intune, csak az Exchange ActiveSync vagy mindkettő által felügyelt eszközök tartozzanak egy csoportba.

    -   **Minden eszköz:** Ez a beállítás minden eszközt magában foglal, feltételeken alapuló kivételek nélkül.

4.  A **Közvetlen tagság meghatározása** oldalon bevonhat vagy kizárhat egyes eszközöket, ha a **Tallózás**gombra kattint. Ha olyan eszközöket választ ki, amelyek nem tagjai a megadott szülőcsoportnak, akkor ezeket a rendszer automatikusan hozzáadja a szülőcsoporthoz.


5.  Az **Összefoglalás** lapon tekintse át a végrehajtandó műveleteket. Válassza a **Befejezés** lehetőséget.

Az újonnan létrehozott csoportot megtalálhatja a **Csoportok** munkaterület **Csoportok** listáján, a szülőcsoport alatt. Itt szerkesztheti és törölheti is a csoportot.

## Felhasználói csoport létrehozása

1.  Az Intune felügyeleti konzolján kattintson a **Csoportok** &gt; **Áttekintés** &gt; **Csoport létrehozása** elemre.

2.  Adja meg a csoport nevét és leírását (az utóbbi nem kötelező), majd válasszon egy felhasználócsoportot szülőcsoportként. Kattintson a **Tovább** gombra.

3.  A **Tagság feltételeinek meghatározása** oldalon adja meg, hogy a szülőcsoport minden tagját be kívánja-e vonni vagy inkább üres csoportot használ első lépésként.  Ezután bevonhat vagy kizárhat tagokat felhasználók olyan **biztonsági csoportjai** alapján, amelyeket manuálisan konfigurál az [Office 365 felügyeleti központjában](http://go.microsoft.com/fwlink/?LinkId=698854), vagy a helyi Active Directoryból szinkronizál. Ha egy biztonsági csoport tagsága megváltozik, akkor az azon a csoporton alapuló felhasználói csoportok tagsága is módosulhat.

    > [!IMPORTANT]
    > Jelenleg ha a csoportba meghatározott biztonsági, illetve menedzseri csoportokból vannak bevonva a tagok, és emellett kizárja meghatározott csoportok tagjait, a rendszer először bevonja, majd eltávolítja a tagokat. Egy bevont tagokkal és kizárt tagokkal is rendelkező csoport létrehozásához javasoljuk, hogy először hozzon létre egy szülőcsoportot a bevont tagokkal, majd hozzon létre egy gyermeket ehhez a csoporthoz, melyben felsorolja a kizárt tagokat. Ezt a gyermekcsoportot az Intune házirendjeinek, profiljainak és terjesztésének megfelelő módon használhatja.

    > [!NOTE]
    > Az Azure felügyeleti portálon létrehozhat egy csoportot a menedzser alapján, akinek a felhasználók jelentést készítenek. A csoport dinamikus lesz, és változni fog, ahogy alkalmazottakat ad hozzá az adott menedzser csapatából, vagy távolít el abból az Azure Active Directoryban. Az Azure-csoportok menedzser alapján való létrehozásának eljárása a [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) (Speciális szabályok létrehozása attribútumokkal) című témakör **To configure a group as a “Manager” group** (Csoport konfigurálása „kezelő” csoportként) című szakaszában található.


4.  A **Közvetlen tagság meghatározása** oldalon bevonhat vagy kizárhat egyes felhasználókat, ha a **Tallózás**gombra kattint. Ha olyan felhasználókat választ ki, amelyek nem tagjai a megadott szülőcsoportnak, akkor ezeket a rendszer automatikusan hozzáadja a szülőcsoporthoz. A **Tagok kiválasztása** párbeszédpanel alsó részén található a felhasználó manuális felvételére szolgáló beállítás. Ez akkor hasznos, ha olyan felhasználót szeretne felvenni a csoportba, aki még nem rendelkezik regisztrált eszközzel.


5.  Az **Összefoglalás** lapon tekintse át a végrehajtandó műveleteket. Válassza a **Befejezés** lehetőséget.

Az újonnan létrehozott csoportot megtalálhatja a **Csoportok** munkaterület **Csoportok** listáján, a szülőcsoport alatt. Itt szerkesztheti és törölheti is a csoportot.

> [!TIP]
> A biztonsági csoportok kiváló forrást biztosítanak a felhasználói csoportok feltöltéséhez. Mivel a biztonsági csoportok esetében meg van adva, hogy mely erőforrásokhoz kinek van hozzáférése, azok könnyedén átfordíthatók Intune felhasználói csoportokra. Azok a biztonsági csoportok, amelyeket az Active Directoryból szinkronizált az Azure Active Directoryba, illetve amelyeket közvetlenül az Azure Active Directoryban hozott létre az Office 365 Felügyeleti központban vagy az Azure felügyeleti portálján, mind elérhetők a felhasználói csoportok létrehozásához az Intune-ban.

## Nézetek testreszabása a rendszergazdai szerepköröknek megfelelően
A szűrt csoportnézetekkel szerepkör alapján testreszabhatja a rendszergazdák számára látható nézeteket, és korlátozhatja az egyes rendszergazdák által felügyelhető csoportokat. Ez a következő esetekben lehet hasznos:

-   Azt szeretné, hogy a rendszergazdák csak bizonyos felhasználókra és eszközökre vonatkozóan végezhessenek telepítéseket.

-   Csak az egyes rendszergazdák számára fontos csoportokat kívánja megjeleníteni.

A szolgáltatás-rendszergazdák számára az Intune felügyeleti konzolján állíthat be szűrt csoportnézeteket. Részletekért lásd: [Tudnivalók a Microsoft Intune elindítása előtt](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Ha szűrt csoportnézeteket konfigurált egy szolgáltatás-rendszergazda számára:

-   Csak a megadott csoportokat láthatja és választhatja ki, amikor szoftvereket vagy házirendeket telepít vagy jelentéseket használ

-   Nem kap állapotinformációkat a felügyeleti konzol következő oldalain:

    -   **Rendszer áttekintése**

    -   **Csoportok áttekintése**

    -   **Az Endpoint Protection áttekintése**

    -   **Riasztások áttekintése**

    -   **Szoftverek áttekintése**

    -   **Házirendek áttekintése**

### Szűrt csoportnézetek konfigurálása

1.  Az Intune felügyeleti konzolon kattintson a **Felügyelet** &gt; **Rendszergazdák kezelése** &gt; **Szolgáltatás-rendszergazdák** elemre.

2.  Válassza ki azt a szolgáltatás-rendszergazdát, amely számára szűrni kívánja a csoportokat, és kattintson a **Csoportok kezelése**elemre.

3.  A **Szolgáltatás-rendszergazda számára megjelenített csoportok kiválasztása** párbeszédpanelen adja hozzá azokat a csoportokat, amelyekhez a rendszergazda hozzáférhet, majd kattintson az **OK**gombra.

Miután konfigurálta a szűrt csoportnézeteket, a rendszergazda csak a kiválasztott csoportokat tudja megnézni és kijelölni.

## Csoportok kezelése
A csoportok létrehozása után azokat a szervezet igényeinek megfelelően kezelheti.

A csoport szerkesztése során megváltoztathatja annak nevét, leírását és a csoporthoz tartozó felhasználókat.

Ha úgy látja, hogy egy csoport már nem szükséges a szervezet számára, törölheti az Intune-ból. A csoport törlése nem érinti a csoporthoz tartozó felhasználókat.

## További lépések

### A megvalósítás ellenőrzése
A csoportok és házirendek előkészítését követően a **Kívánt érték** és az **Állapot** alapján ellenőrizheti a felügyelet gyakorlati megvalósítását.

1. Válassza ki bármelyik eszközt az eszközcsoportból, és tallózzon a képernyő tetején található információs kategóriák között.
2. Válassza a **Házirend** lehetőséget. Az Androidos eszközök házirend-beállításaihoz tartozó alábbi képernyőfelvételéhez hasonlót fog látni.

![Példa: iOS-es házirend-beállítások](../media/Intune-Device-Policy-v.2.jpg)

Minden egyes házirend rendelkezik egy **Kívánt érték** és egy **Állapot**jellemzővel. A kívánt érték az az érték, amelyet a házirend hozzárendelésekor el kívánt érni. Az állapot az eszközre érvényes összes házirend alkalmazása, valamint a hardver és az operációs rendszer által szabott korlátozások és rendszerkövetelmények együttese alapján elért érték.  Ezen a képernyőfelvételen két egyszerű példát látható:

-   Az **Egyszerű jelszavak engedélyezése** beállított értéke **Igen**, ahogy az a **Kívánt érték** oszlopban látható, az **Állapot** értéke azonban **Nem alkalmazható**. Ez azért van, mert az egyszerű jelszavak az Android-eszközökön nem támogatottak.

-   Ehhez hasonlóan az **iOS-eszközök e-mail beállításai** kiterjesztett házirend erre az eszközre nem alkalmazható, mivel ez egy Android-eszköz.

> [!NOTE]
> Ne felejtse el, hogy ha két különböző korlátozási szintű házirend vonatkozik egy eszközre vagy felhasználóra, akkor gyakorlatban a szigorúbb házirend lesz érvényes.



<!--HONumber=Aug16_HO3-->



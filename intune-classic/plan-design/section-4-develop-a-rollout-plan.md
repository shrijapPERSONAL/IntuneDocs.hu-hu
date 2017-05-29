---
title: "Az Intune-bevezetés célcsoportjainak és időkeretének meghatározása | Microsoft Docs"
description: "Ez cikk segít meghatározni a bevezetési célcsoportokat és időkereteket a Microsoft Intune csak felhőalapú megvalósításához."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2a970badf5ac18a05115a72dc267ee455ba4628d
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="develop-an-intune-rollout-plan"></a>Intune bevezetési terv kidolgozása

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Ez a szakasz segít meghatározni az Intune bevezetésének munkahelyi célcsoportjait, a csoportonkénti bevezetési időkeretet, valamint az alkalmazandó bevezetési módszereket.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Az Intune-bevezetés célcsoportjainak és időkeretének meghatározása

Fontos, hogy először meghatározza azokat a csoportokat, amelyeket az Intune bevezetése érinteni fog. Ezekről a célcsoportokról korábban már esett szó az útmutató Intune használatieset-forgatókönyveinek meghatározásakor.

Másodszor határozza meg azt az időkeretet, amellyel az egyes csoportokat célozza meg az Intune bevezetésekor. Az egyes csoportoknak legmegfelelőbb bevezetési időkeret meghatározásához rendszerint szükség van az Intune telepítési csapaton belüli és a célcsoporttal való megbeszélésre.

Például a bevezetési időkeret megállapításához az Intune telepítési csapat olyan tényezőket vitathat meg, mint a csoport változás iránti fogékonysága, a felhasználók és az eszközök száma, az eszközplatformok típusa, a követelmények, a földrajzi helyzet, valamint az üzleti kockázatok.

A szervezetek többnyire az informatikai részleg kisebb csoportjára irányuló kezdeti próbaüzemmel kezdik meg az Intune bevezetését. A próbaüzem később kiterjeszthető az informatikai részleg több felhasználójára, valamint más munkahelyi csoportok is bevonhatók. A sikeres próbaüzemet követően a cégek készen állnak a teljes bevezetésre, megcélozva ezzel az eddig nem érintett munkahelyi csoportokat. A különböző bevezetési csoportok és fázisok az alábbiakban találhatók:

-   **Próbaüzem:** A bevezetés első fázisa próbafelhasználók számára történjen. A próbafelhasználóknak meg kell érteniük, hogy ők egy új megoldás első felhasználói, és fontos, hogy visszajelzésekkel szolgáljanak a konfiguráció, a dokumentáció és az értesítések fejlesztése érdekében, valamint hogy megkönnyítsék a bevezetés későbbi fázisaiban részt vevő felhasználók dolgát. A próbafelhasználók között ne legyenek vezetők vagy VIP-ek.

-   **Részlegek:** Bármelyik részleg lehet bevezetési fázis. Ebben a forgatókönyvben egyszerre egy egész részleget céloz meg. Az ilyen típusú bevezetéskor valószínű, hogy minden egyes fázis ugyanúgy használja a mobileszközöket, és ugyanazokat az alkalmazásokat éri el. Valószínű az is, hogy a felhasználókra ugyanolyan típusú szabályzatok vonatkoznak.

-   **Földrajzi hely:** Az ilyen típusú telepítéskor ugyanazon a földrészen, országban, régióban vagy akár épületben lévő felhasználók számára történik a telepítés. Az ilyen fajta szakaszos bevezetés a felhasználók földrajzi helyére való összpontosítást teszi lehetővé. Így [körültekintő](#user-assisted-enrollment) megközelítés alkalmazható, ugyanis azt Intune-t egyidejűleg telepítő helyek száma csökken. Mivel esély van arra, hogy különböző részlegek vagy használati esetek ugyanazon a helyen legyenek, ezért a különböző használati esetek egyidejűleg is telepíthetők.

-   **Platform:** Ez a típusú telepítés hasonló platformok egyidejű telepítését jelenti. Erre jó példa lehet az, hogy az első hónapban az összes iOS-eszköz, majd az összes Android-, végül az összes Windows-eszköz kerül sorra. Ez a fajta szakaszos telepítés segíti a segélyszolgálat-támogatás egyszerűsítését. Ugyanis a segélyszolgálatnak ekkor egyszerre csak egy platformú támogatást kell biztosítania.

Itt egy olyan Intune bevezetési tervre található példa, amely magába foglalja a célcsoportokat és az ütemterveket:

| **Bevezetési fázis** | **Július** | **Augusztus** | **Szeptember** | **Október** |
|:---:|:---:|:---:|:---:|:---:|
| Korlátozott próbaüzem | Informatika (50 felhasználó) |  |  |  |                                                         
| Bővített próbaüzem | Informatika (200 felhasználó), informatikai vezetők (10 felhasználó) |  |  |  |                                                         
| Éles bevezetés, 1. fázis |  | Értékesítés és marketing (2000 felhasználó) |  |  |
| Éles bevezetés, 2. fázis |  |  | Kereskedelem (1000 felhasználó) |  |
| Éles bevezetés, 3. fázis |  |  |  | HR (50 felhasználó), Pénzügy (40 felhasználó), vezetők (30 felhasználó) |

## <a name="determine-the-intune-enrollment-approach"></a>Az Intune-regisztrálás módszerének meghatározása

Most, hogy meghatározta az Intune bevezetéséhez kapcsolódó célcsoportokat és ütemterveket, a következő lépésként válassza ki minden egyes csoportra vonatkozóan a legmegfelelőbb Intune-beli regisztrálási módszert. Az Intune-beli regisztrálásra többféle módszer létezik. A néhány gyakoribb regisztrálási módszer között található például az önkiszolgáló felhasználó, a felhasználót segítő regisztrálás, valamint az informatikai kiállítás.

### <a name="user-self-service"></a>Önkiszolgáló felhasználó

E módszer használatával a felhasználó felelős saját eszközének regisztrálásáért, rendszerint munkahelye informatikai részlegének regisztrálási utasításait követve. Ezt a módszert többnyire cégek alkalmazzák, és jobban skálázható, mint a felhasználót segítő regisztrálás.

### <a name="user-assisted-enrollment"></a>Felhasználót segítő regisztrálás

Ez az úgynevezett „körültekintő” módszer, amely során egy informatikai csapattag személyesen vagy Skype-on keresztül segíti a felhasználót a regisztrálás során. Ez a módszer rendszerint a vezetőkkel vagy olyan csoportokkal alkalmazandó, akiknek több segítségre van szüksége bevezetés során.

### <a name="it-tech-fair"></a>Informatikai vásár

Az Intune bevezetésének további lehetősége egy informatikai vásár megtartása. Az informatikai csoport az eseményen felállít egy regisztrálástámogatási standot, ahol a felhasználók információt kaphatnak, kérdéseket tehetnek fel és támogatásban részesülhetnek az Intune-beli regisztrálással kapcsolatban. Ez a lehetőség az informatikai csoportnak és a felhasználónak egyaránt hasznára válhat, kiváltképpen az Intune bevezetésének korai szakaszában.

A továbbiakban egy célcsoportokkal, ütemtervekkel és regisztrálási módszerekkel felvértezett Intune-bevezetési terv található:

| **Bevezetési fázis** | **Július** | **Augusztus** | **Szeptember** | **Október** |
|:---:|:---:|:---:|:---:|:---:|
| Korlátozott próbaüzem |  |  |  |  |                                                         
| Önkiszolgáló | Informatikai részleg |  |  |  |
| Bővített próbaüzem |  |  |  |  |                                                         
| Önkiszolgáló | Informatikai részleg |  |  |  |
| Körültekintő | Informatikai vezetők |  |  |  |
| Éles bevezetés, 1. fázis |  | Értékesítés, Marketing |  |  |
| Önkiszolgáló |  | Értékesítés és marketing |  |  |
| Éles bevezetés, 2. fázis |  |  | Kereskedelem |  |
| Önkiszolgáló |  |  |  |  |
| Éles bevezetés, 3. fázis |  |  | Kereskedelem |  |
| Önkiszolgáló |  |  |  | HR, Pénzügy |
| Körültekintő |  |  |  | Vezetők |

## <a name="next-section"></a>Következő szakasz

A következő szakaszban az [Intune bevezetési kommunikációs terv összeállításáról](section-5-develop-a-rollout-communication-plan.md) található információ.


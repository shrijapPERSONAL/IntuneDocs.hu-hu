---
title: "A bevezetés és az időkeretek által érintett csoportok meghatározása"
description: "Ennek a cikknek a segítségével könnyebben meghatározhatja, mely csoportoknál vezeti be az Intune-t és az üzembe helyezések időkeretét."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9dda530be47b5449a9c1ed610d8e409fd62148d7
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2017
---
# Bevezetési terv kidolgozása
<a id="develop-a-rollout-plan" class="xliff"></a>

A bevezetési terve azonosítja az Intune bevezetésében érintett céges csoportokat, a bevezetés időkeretét az egyes csoportoknál és a bevezetéshez használt megközelítési módokat.

## Célcsoportok és időkeretek
<a id="targeted-groups-and-timeframes" class="xliff"></a>

Először tekintse át az Intune bevezetése által érintett célcsoportokat és azokat, amelyeket a [használati eseteket tartalmazó forgatókönyvekben](planning-guide-scenarios.md) azonosított.

Másodszor határozza meg az egyes célcsoportok időkeretét. Az egyes csoportoknak legmegfelelőbb bevezetési időkeret meghatározásához rendszerint szükség van az Intune üzembe helyezési csapat és a célcsoportok közötti megbeszélésre. Ezeken többek között a következőket szükséges megbeszélni:
* A csoport változtatási szándékát
* A felhasználók és eszközök száma
* Az eszközplatformok típusa
* Követelmények
* Földrajzi hely
* Üzleti kockázat

## Bevezetési fázisok
<a id="rollout-phases" class="xliff"></a>
A szervezetek többnyire az informatikai részleg kisebb csoportjára irányuló kezdeti próbaüzemmel kezdik meg az Intune bevezetését. A próbaüzem később kiterjeszthető az informatikai részleg több felhasználójára, valamint más munkahelyi csoportok is bevonhatók.

### Próbaüzem
<a id="pilot" class="xliff"></a>
A bevezetés első fázisa próbafelhasználók számára történjen. A próbafelhasználóknak meg kell érteniük, hogy ők egy új megoldás első felhasználói. El kell fogadniuk, hogy visszajelzéseket fognak adni a konfiguráció, dokumentáció és értesítések javításához, és hogy megkönnyítésék a többi felhasználó dolgát a későbbi bevezetési fázisokban. A próbafelhasználók között ne legyenek vezetők vagy VIP-ek.

A próbaüzem jó lehetőség a [kihívások](planning-guide-deployment-goals.md) tesztelésére és a korábban összegyűjtött [követelmények](planning-guide-requirements.md) finomítására.

Foglalja bele a [kommunikációs](planning-guide-communication-plan.md) tervet, a [támogatási](planning-guide-support-plan.md) tervet és a [tesztelést és érvényesítést](planning-guide-test-validation.md), hogy a problémákat még akkor megoldhassa, amikor azok felhasználókra gyakorolt hatása még kicsi.

### Éles bevezetés
<a id="production-rollout" class="xliff"></a>
A sikeres próbaüzemet követően készen áll az éles bevezetésre a cég többi csoportjánál. Néhány példa a különböző bevezetési csoportokra és fázisokra:

-   **Részlegek** <br/>Bármelyik részleg lehet bevezetési fázis. Egyszerre lehet célcsoport az egész részleg. Ebben a bevezetési típusban a felhasználók minden részlegben általában ugyanolyan módon használják a mobileszközöket, és ugyanazokhoz az alkalmazásokhoz férnek hozzá. A felhasználók valószínűleg ugyanolyan szabályzattípusokkal rendelkeznek.

-   **Földrajzi hely** <br/>Ezzel a megközelítéssel az üzembe helyezést egy meghatározott földrajzi hely, például egyazon kontinens, ország, régió vagy vállalati épület összes felhasználója számára végzi el. A több fázisú bevezetésnek ez a típusa lehetővé teszi, hogy a felhasználók meghatározott helye legyen a középpontban. Ez lehetővé teszi [körültekintőbb](#user-assisted-enrollment) megközelítési mód alkalmazását, mert az egyidejűleg üzembe helyezett Intune-helyek száma kevesebb. Mivel esély van arra, hogy különböző részlegek vagy használati esetek ugyanazon a helyen legyenek, ezért a különböző használati esetek egyidejűleg is telepíthetők.

-   **Platform** <br/>Ez a típusú telepítés hasonló platformok egyidejű telepítését jelenti. Erre jó példa lehet az, hogy az első hónapban az összes iOS-eszköz, majd az összes Android-, végül az összes Windows-eszköz kerül sorra. A több fázisú üzembe helyezésnek ez a típusa leegyszerűsíti a segélyszolgálati támogatást, mert egyszerre csak egyetlen platformot kell támogatnia.

Itt egy olyan Intune bevezetési tervre található példa, amely magába foglalja a célcsoportokat és az ütemterveket:

| **Bevezetési fázis** | **Július** | **Augusztus** | **Szeptember** | **Október** |
|:---:|:---:|:---:|:---:|:---:|
| Korlátozott próbaüzem | Informatika (50 felhasználó) |  |  |  |                                                         
| Bővített próbaüzem | Informatika (200 felhasználó), informatikai vezetők (10 felhasználó) |  |  |  |                                                         
| Éles bevezetés, 1. fázis |  | Értékesítés és marketing (2000 felhasználó) |  |  |
| Éles bevezetés, 2. fázis |  |  | Kereskedelem (1000 felhasználó) |  |
| Éles bevezetés, 3. fázis |  |  |  | HR (50 felhasználó), Pénzügy (40 felhasználó), vezetők (30 felhasználó) |

[Letöltheti a fenti táblázat sablonját](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), és beírhatja cégének bevezetési fázisait.
## Bevezetési csoportok és regisztrációs módszerek társítása
<a id="match-rollout-groups-to-enrollment-approaches" class="xliff"></a>

Most, hogy meghatározta az Intune bevezetéséhez kapcsolódó célcsoportokat és ütemterveket, a következő lépésként válassza ki minden egyes csoportra vonatkozóan a legmegfelelőbb Intune-beli regisztrálási módszert. Különböző regisztrációs módszereket használhat, többek között ezeket:
* Önkiszolgáló felhasználó
* Felhasználót segítő regisztrálás
* Informatikai vásár

### Önkiszolgáló felhasználó
<a id="user-self-service" class="xliff"></a>

Ebben az esetben a felhasználó felelős saját eszközének regisztrálásáért, rendszerint munkahelye informatikai részlegének regisztrálási utasításait követve. Ezt a módszert többnyire cégek alkalmazzák, és jobban skálázható, mint a felhasználót segítő regisztrálás.

### Felhasználót segítő regisztrálás
<a id="user-assisted-enrollment" class="xliff"></a>

Ez másként „körültekintő” módszerként is ismert. Az IT-csoport egy tagja személyesen vagy Skype-on segít a felhasználónak a regisztrációs folyamat során. Ez a módszer rendszerint a vezetőkkel vagy olyan csoportokkal alkalmazandó, akiknek több segítségre lehet szüksége bevezetés során.

### Informatikai vásár
<a id="it-tech-fair" class="xliff"></a>

Az Intune bevezetésének további lehetősége egy informatikai vásár megtartása. Az informatikai csoport az eseményen felállít egy regisztrálástámogatási standot, ahol a felhasználók információt kaphatnak, kérdéseket tehetnek fel és támogatásban részesülhetnek az Intune-beli regisztrálással kapcsolatban. Ez a lehetőség az informatikai csoportnak és a felhasználónak egyaránt hasznára válhat, kiváltképpen az Intune bevezetésének korai szakaszaiban.

Itt következik a fenti Intune-regisztrációs terv regisztrációs módszerekkel frissített példája:

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

## További lépések
<a id="next-steps" class="xliff"></a>

A következő szakaszban az [Intune bevezetési kommunikációs terv összeállításáról](planning-guide-communication-plan.md) található információ.

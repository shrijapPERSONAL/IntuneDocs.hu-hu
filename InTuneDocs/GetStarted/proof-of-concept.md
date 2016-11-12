---
title: "A koncepció igazolása | Microsoft Intune"
description: "Javaslatok az Intune üzembe helyezésének koncepcióigazolási fázisához."
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3c97380-23ca-40da-acbc-78108507cad7
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8921043334630bbd2955c0423ca9cd1b76c27758
ms.openlocfilehash: 5b19835e7f726e23d402bbab408796cad9028bd0


---

# A koncepció igazolása (Proof of Concept, PoC)
A koncepció igazolási fázisa annak meghatározására irányul, hogy az üzemelő példány képes-e megfelelni a vállalati követelményeknek. Ez a fázis egy egyszerű topológiát tartalmaz, amely meghatározott műszaki helyzetek ellenőrzésére készült.  A telepítésnek tesztkörnyezetben kell történnie, és nem tartalmazhat éles üzemű felhasználókat.

## Miért fontos ez?
A koncepció igazolása azért fontos, hogy a telepítés megvalósíthatóságát még a próbafelhasználókkal való tesztelés előtt fel lehessen mérni. Kis léptékű kísérletnek kell tekinteni, amelyből megismerhető, hogy hogyan fog működni a Microsoft Intune az adott környezetben. Továbbá ezzel a fázissal meghatározott helyzeteket is ellenőrizni kell, a próbaüzemhez szükséges erőforrásokba történő beruházások előtt. A koncepció igazolása során szerzett tapasztalatokat fel kell használni a próbaüzem és az éles üzem kialakításához.
A koncepció igazolása meghatározásához és hatókörének felméréséhez kezdje a munkát a feltáró kérdések áttekintésével.

## Feltáró kérdések
Vitassa meg ezeket a kérdéseket a projektcsapattal, hogy felvázolhassa a projekt részleteit, felderíthesse az esetleges kockázatokat és meghatározhassa a végrehajtandó feladatokat.

-   Melyek azok a fő helyzetek, amelyekre az Intune-nak megoldást kell adnia, hogy megfeleljen a szervezet eszközfelügyeleti igényeinek?

-   Milyen funkciókat kíván megvizsgálni és ellenőrizni?

-   E helyzetek ellenőrzésének elvégzéséhez milyen erőforrásokról kell a tesztkörnyezetben gondoskodni?

## A fókuszterületek céljai
Ebben a szakaszban áttekintés kap a bevezetés adott fázisához tartozó fókuszterületi tevékenységekről.

### Tervezés
Már a koncepció igazolására szolgáló infrastruktúra telepítése előtt ismernie kell az ellenőrzendő helyzeteket és az ellenőrzés elvégzéséhez szükséges elemeket.

### Ügyfélszolgálat
A segélyszolgálatnak erre a fázisra nem kell felkészülnie, mert ez nem érint éles felhasználókat vagy eszközöket. Mindazonáltal ez lehetőséget nyújt a segélyszolgálat számára, hogy megismerkedjen az Intune telepítésével és üzemeltetésével.

### Tájékoztatás
A műszaki csapatnak és a vezetői támogatóknak betekintéssel kell rendelkezniük a helyzetek tesztelésének folyamatába. A tervezőcsapatnak ismernie kell a megszerzett tapasztalatokat, hogy azokat a tervezőmunka során hasznosíthassák.

### Képzés
A felhasználókat, eszközöket, szabályzatokat és alkalmazásokat felügyelő rendszergazdáknak érdemes kihasználni a koncepció igazolása által az Intune-konzol és az Intune-funkciók megismerésére kínált lehetőséget.

### Üzemeltetés
A koncepció igazolásához nincs szükség folyamatos működésre. Előfordulhatnak azonban olyan meghatározott helyzetek, amelyeket az üzemeltető munkatársak szeretnének megismerni, vagy a koncepció igazolása során ellenőrizni.

## Ellenőrzőlista a kezdéshez
Az alábbi lista tartalmazza **A koncepció igazolása** fázis első lépéseit.

-   A koncepció igazolása sikerfeltételeinek meghatározása. Ezeknek az üzleti és műszaki követelményeken kell alapulniuk.

-   A tesztelési helyzetek ellenőrzéséhez szükséges erőforrások meghatározása.

-   Az éles környezetet utánzó, megfelelő tesztkörnyezeteknek, például az eszközök különféle operációs rendszerek esetén szükséges számának meghatározása.

## Gyakori problémák
Az alábbiakban áttekinthet néhány problémát, amely felmerülhet **A koncepció igazolása** fázisban.

-   **Probléma:** Műszaki és emberi erőforrások biztosítása az éleshez hasonlító helyzetek ellenőrzéséhez.

    **Megoldás:** Egyértelműen fogalmazza meg, hogy a koncepció igazolására szolgáló környezetben szerzett tapasztalatok segítik a műszaki tervezést, és javítják az ezt követő fázisok minőségét. Ha a koncepció igazolásához hiányoznak az erőforrások, akkor ezek a tapasztalatok csak a műszaki tervezés befejezése után szerezhetők meg, ez pedig egyes elemek újratervezését is szükségessé teheti.

-   **Probléma:** Az éles üzemben szükséges teszthelyzetek meghatározása.

    **Megoldás:** A támogató vezetővel, a hálózattal és a felhasználói csoportokkal együttműködve ismerje meg az ügyfélkezelési megoldások követelményeit.

### További lépések
[Próbaüzem](pilot.md)



<!--HONumber=Oct16_HO4-->



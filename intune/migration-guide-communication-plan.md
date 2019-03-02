---
title: Migrálás kommunikációjának megtervezése
titlesuffix: Microsoft Intune
description: Ez a cikk egy migrációs kommunikációs tervet és stratégiát mutat be a Microsoft Intune-ba való migráláshoz.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e6a52506-2d29-41f7-a171-5d684a740dd4
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a55cce627e02730ab3f217381ab8d6f92ddc3bb1
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238130"
---
# <a name="plan-communications"></a>A kommunikáció tervezése

A kommunikációs terv az Intune-migráció kulcseleme. A migrálás egyes fázisaiban ugyanazt a kommunikációs tervet követheti.

## <a name="email-templates"></a>E-mail-sablonok

A következő e-mail-kommunikációs terv követését javasoljuk. A mellékelt sablonokat saját kommunikációs tervéhez igazíthatja:

-   **E-mailek \#1:** Az előnyök, az elvárások és az ütemezés ismertetik. Használja ki a lehetőséget az Intune által felügyelt eszközökön elérhető új szolgáltatások bemutatására.<br/><br/>


    -   [Az \#1. e-mail-sablon](https://gallery.technet.microsoft.com/Intune-migration-guide-end-e3209b35) letöltése
<br></br>

-   **E-mailek \#2:** Jelentjük be, hogy szolgáltatások az Intune-on keresztül hozzáférhető készen állnak. Szólítsa fel a felhasználókat, hogy most regisztráljanak. Emlékeztesse a felhasználókat a migrálás előnyeire és stratégiai okaira.<br/><br/>


    -   [A \#2. e-mail-sablon](https://gallery.technet.microsoft.com/Intune-migration-guide-end-a9d25eb5) letöltése
<br></br>

-   **E-mailek \#3:** Engedélyezheti a felhasználók egy idővonalon a hozzáférése az érintett előtt. Emlékeztesse ismét a felhasználókat a migrálás előnyeire és stratégiai okaira. Az e-maileket a fázisok szerint eltoltan kell időzíteni. Például júniusban küldje el az \#1. e-mailt az 1. fázis felhasználóinak, a \#2. e-mailt a 2. fázis felhasználóinak és a \#3. e-mailt a 3. fázis felhasználóinak.<br/><br/>

    -   [A \#3. e-mail-sablon](https://gallery.technet.microsoft.com/Intune-migration-guide-end-831521b5) letöltése

Adott időszak elteltével megkezdheti a megfelelőség kényszerítését a feltételes hozzáférési házirendek betartatásával, és feltételként használhatja azokat a vállalati adatok eléréséhez [A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](migration-guide-drive-adoption.md) részben leírtak szerint.

## <a name="additional-communication-templates"></a>További kommunikációs sablonok

Az Intune további sablonokat nyújt, amelyeket az eszközök regisztrálásának ösztönzésére használhat a felhasználók körében:

-   Az [A végfelhasználók oktatása az Intune használatával kapcsolatban](end-user-educate.md) című témakör részletezi a regisztrálás lépéseit az egyes mobiloperációsrendszer-platformok esetében.

-   Az [Intune végfelhasználói regisztrálási sablon rendszergazdák számára](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) testreszabható Word-dokumentum ismerteti az Android, iOS és Mac rendszerű eszközök regisztrálását az Intune-ban.

-   A [FastTrack az EMS útmutatóihoz és e-mail-üzeneteihez](https://gallery.technet.microsoft.com/FastTrack-for-EMS-How-To-f170da4c) a vállalat emblémájával személyre szabható, ezzel is elősegítve az Intune és az EMS szervezeten belüli bevezetését.

-   Megosztás a [céges portál alkalmazás URL-címe](http://go.microsoft.com/fwlink/?LinkID=396941) az Android, iOS és Windows felhasználókkal. Az URL-címet átirányítja a megfelelő vállalati portál alkalmazást az Android, iOS és Windows-eszközök listázása.

## <a name="next-steps"></a>További lépések

[A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel](migration-guide-drive-adoption.md).

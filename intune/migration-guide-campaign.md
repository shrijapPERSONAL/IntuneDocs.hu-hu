---
title: "Intune-migrációs kampány indítása"
description: "Ez a cikk útmutatást nyújt a migrációs kampány indításához."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9690572fd5f17fece0de7b533c98bfc52d77615b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="phase-2-migration-campaign"></a>2. fázis: migrációs kampány

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

A szervezeteknek a saját igényeiknek leginkább megfelelő migrációs megközelítéseket kell alkalmazniuk, és az adott követelményekhez kell igazítaniuk bevezetési taktikájukat. A jelen útmutató fennmaradó részében ismertetjük azon eszközöket, amelyekre szüksége lesz a felhasználók eszközeinek az Intune-ban való sikeres regisztrálásához.

## <a name="keys-to-a-successful-migration"></a>A migrálás sikerességének ellenőrzése

A külső MDM-szolgáltatótól az Intune-ba való migrálások tanulságai a következők:

-   A kommunikáció kulcsfontosságú az állásidő minimalizálása és a végfelhasználói elégedettség érdekében.

-   Győződjön meg róla, hogy rendelkezik az adott helyzetre vonatkozó és konkrét migrálási utasításokkal.

-   Az összes felügyelt eszköz regisztrációját meg kell szüntetni a meglévő MDM-szolgáltatónál annak Intune-ban való regisztrálása előtt.

-   Kérjen útmutatást a meglévő MDM-szolgáltatótól a végfelhasználók számára arra vonatkozóan, hogy miként szüntethetik meg eszközeik regisztrációját.

-   Alkalmazzon fázisos megközelítést. Kezdje a próbafelhasználók kis csoportjával, és növekményesen vegye fel a felhasználók további csoportjait, amíg el nem éri a teljes körű bevezetést.

-   Minden ciklusban figyelje az ügyfélszolgálat terhelését és a regisztráció sikerességét. Hagyjon időt a sikerességi feltételek értékelésére az egyes csoportok esetében a következő csoport migrálása előtt. A próbabevezetés során ellenőrizni kell a következőket:

    -   A sikeres és sikertelen regisztrációk aránya az elvárásokon belül van-e.

    -   A felhasználók termelékenységét:

        -   A vállalati erőforrások, például a VPN, a Wi-Fi, a levelezés és a tanúsítványok működését.

        -   A telepített alkalmazások elérhetőségét.

    -   Az adatbiztonságot:

        -   Megfelelőségi jelentések készítése

        -   Mobilalkalmazás-védelmi funkciók betartatása

-   Ha elégedett a migrálás első fázisával, ismételje meg (az alábbiakban tipikus migrációs ciklusként ismertetett) migrációs ciklust a következő fázis esetében.

-   Ismételje a fázisos ciklusokat mindaddig, amíg az összes felhasználót migrálta az Intune-ba.

-   Győződjön meg arról, hogy az ügyfélszolgálat készen áll a végfelhasználók támogatására a teljes migrációs kampány során. Végezzen önkéntes migrálást, amíg meg tudja becsülni a támogatási hívások jelentette munkaterhelést.

-   Ne szabjon meg a regisztrációra vonatkozó határidőket, amíg az ügyfélszolgálata nem tudja kezelni a fennmaradó felhasználómennyiséget

> [!IMPORTANT] 
> Ne állítsa be az Intune-ban és a meglévő külső MDM-megoldásban egyaránt a hozzáférés-vezérlés alkalmazását az erőforrásokhoz, például az Exchange-hez vagy a SharePoint online-hoz. Emellett az eszközök egyszerre csak az egyik megoldásban regisztrálhatók.

## <a name="next-steps"></a>További lépések

[Kommunikációs terv](migration-guide-communication-plan.md)

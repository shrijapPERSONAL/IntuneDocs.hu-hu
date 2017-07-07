---
title: "Az eszköz regisztrációjának törlése, ha nem fogadta el a használati feltételeket | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope: User help
ROBOTS: 
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b99ce8b30e25960e09e39b81f0f58aa09af2affa
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="unenroll-your-device-if-you-declined-terms-of-use"></a>Az eszköz regisztrációjának törlése, ha nem fogadta el a használati feltételeket

A legjobb módszer az androidos eszköz regisztrációjának törlésére, ha elfogadja a Használati feltételeket, bejelentkezik a Vállalati portál alkalmazásba, majd [az itt elérhető útmutatásnak megfelelően](unenroll-your-device-from-intune-android.md) törli a regisztrációt. Azonban ha nem fogadja el a Használati feltételeket, amikor megpróbál bejelentkezni a Munkahelyi portál alkalmazásba, akkor a jövőbeni bejelentkezési próbálkozásai sikertelenek lesznek. Ebben az esetben a következő „áthidaló” megoldásokat kell alkalmaznia az eszköz regisztrációjának törléséhez.

Amikor eltávolítja a Vállalati portál alkalmazást, azzal az eszköz Intune-beli regisztrálását is törli. Az eszköz többé nem tud hozzáférni a vállalati erőforrásokhoz. A törlés további következményeiről további információért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

A Vállalati portál alkalmazás eltávolítása előtt az **Eszközadminisztrátorok** beállításba kell lépnie, és ki kell kapcsolnia a **Vállalati portál** elemet. A lépések kissé eltérőek lehetnek attól függően, hogy milyen androidos eszközzel rendelkezik.

Az eszköz Intune-regisztrációjának törlése és a Vállalati portál alkalmazás eltávolítása:

1.  Lépjen a **Settings** (Beállítások)&gt;**Security (Biztonság) &amp; Screen Lock (Képernyőzár)**&gt;**Device administrators** (Eszközadminisztrátorok) elemhez.

    A lépés elvégzésével azonnal törli az eszköz regisztrációját.

2.  Törölje a **Vállalati portál** melletti jelölőnégyzet jelölését a kikapcsoláshoz.

    Most már eltávolíthatja a Vállalati portál alkalmazást.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.

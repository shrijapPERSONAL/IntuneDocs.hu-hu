---
title: Unenroll your device from Intune if you declined "Terms of Use" | Microsoft Intune
description: "A cikk ismerteti, hogyan törölhető egy Android-eszköz Intune-regisztrációja, ha nem fogadta el a Használati feltételeket, és nem tud bejelentkezni a Vállalati portál alkalmazásba"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: 6303400645bf26ede733413fe2dabdb360e3bafb


---


# <a name="unenroll-your-device-from-intune-if-you-declined-terms-of-use"></a>Az eszköz Intune-regisztrációjának törlése, ha nem fogadta el a használati feltételeket

A legjobb módszer az androidos eszköz regisztrációjának törlésére, ha elfogadja a Használati feltételeket, bejelentkezik a Vállalati portál alkalmazásba, majd [az itt elérhető útmutatásnak megfelelően](unenroll-your-device-from-intune-android.md) törli a regisztrációt. Azonban ha nem fogadja el a Használati feltételeket, amikor megpróbál bejelentkezni a Munkahelyi portál alkalmazásba, akkor a jövőbeni bejelentkezési próbálkozásai sikertelenek lesznek. Ebben az esetben a következő „áthidaló” megoldásokat kell alkalmaznia az eszköz regisztrációjának törléséhez.

Amikor eltávolítja a Vállalati portál alkalmazást, azzal az eszköz Intune-beli regisztrálását is törli. Az eszköz többé nem tud hozzáférni a vállalati erőforrásokhoz. A törlés további következményeiről további információért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

A Vállalati portál alkalmazás eltávolítása előtt az **Eszközadminisztrátorok** beállításba kell lépnie, és ki kell kapcsolnia a **Vállalati portál** elemet. A lépések kissé eltérőek lehetnek attól függően, hogy milyen androidos eszközzel rendelkezik.

Az eszköz Intune-regisztrációjának törlése és a Vállalati portál alkalmazás eltávolítása:

1.  Lépjen a **Settings** (Beállítások)&gt;**Security (Biztonság) &amp; Screen Lock (Képernyőzár)**&gt;**Device administrators** (Eszközadminisztrátorok) elemhez.

    A lépés elvégzésével azonnal törli az eszköz regisztrációját.

2.  Törölje a **Vállalati portál** melletti jelölőnégyzet jelölését a kikapcsoláshoz.

    Most már eltávolíthatja a Vállalati portál alkalmazást.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a [Microsoft Android-csapatának](mailto:wintunedroidfbk@microsoft.com).



<!--HONumber=Nov16_HO1-->



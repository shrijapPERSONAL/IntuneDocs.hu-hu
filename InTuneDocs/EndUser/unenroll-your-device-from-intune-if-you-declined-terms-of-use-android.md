---
title: Unenroll your device from Intune if you declined "Terms of Use" | Microsoft Intune
description: "A cikk ismerteti, hogyan törölhető egy Android-eszköz Intune-regisztrációja, ha nem fogadta el a Használati feltételeket, és nem tud bejelentkezni a Vállalati portál alkalmazásba"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d32aa982cf9d45da36f71be5554f31375521e35
ms.openlocfilehash: 4f5088bc645fed0451885078f5ab0dcd04a33d81


---


# Az eszköz Intune-regisztrációjának törlése, ha nem fogadta el a használati feltételeket

A legjobb módszer az androidos eszköz regisztrációjának törlésére, ha elfogadja a Használati feltételeket, bejelentkezik a Vállalati portál alkalmazásba, majd [az itt elérhető útmutatásnak megfelelően](unenroll-your-device-from-intune-android.md) törli a regisztrációt. Ha azonban nem fogadja el a Használati feltételeket, amikor megpróbál bejelentkezni a Vállalati portál alkalmazásba, akkor a jövőbeni bejelentkezési próbálkozásai sikertelenek lesznek. Ebben az esetben a következő „áthidaló” megoldásokat kell alkalmaznia az eszköz regisztrációjának törléséhez.

Amikor eltávolítja a Vállalati portál alkalmazást, azzal az eszköz Intune-beli regisztrálását is törli. Az eszköz többé nem tud hozzáférni a vállalati erőforrásokhoz. A törlés további következményeiről további információért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

A Vállalati portál alkalmazás eltávolítása előtt az **Eszközadminisztrátorok** beállításba kell lépnie, és ki kell kapcsolnia a **Vállalati portál** elemet. A lépések kissé eltérőek lehetnek attól függően, hogy milyen androidos eszközzel rendelkezik.

Az eszköz Intune-regisztrációjának törlése és a Vállalati portál alkalmazás eltávolítása:

1.  Lépjen a **Settings** (Beállítások)&gt;**Security (Biztonság) &amp; Screen Lock (Képernyőzár)**&gt;**Device administrators** (Eszközadminisztrátorok) elemhez.

    A lépés elvégzésével azonnal törli az eszköz regisztrációját.

2.  Törölje a **Vállalati portál** melletti jelölőnégyzet jelölését a kikapcsoláshoz.

    Most már eltávolíthatja a Vállalati portál alkalmazást.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Vállalati portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a Microsoft Android-csapatának a wintunedroidfbk@microsoft.com címre.



<!--HONumber=Oct16_HO2-->



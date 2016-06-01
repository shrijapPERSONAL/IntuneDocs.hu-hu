---
# required metadata

title: Az eszköz Intune-regisztrációjának törlése, ha nem fogadta el a használati feltételeket | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Az eszköz Intune-regisztrációjának törlése, ha nem fogadta el a használati feltételeket

A legjobb módszer az androidos eszköz regisztrációjának törlésére, ha elfogadja a Használati feltételeket, bejelentkezik a Vállalati portál alkalmazásba, majd [az itt elérhető útmutatásnak megfelelően](unenroll-your-device-from-intune-android.md) törli a regisztrációt. Ha azonban nem fogadja el a Használati feltételeket, amikor megpróbál bejelentkezni a Vállalati portál alkalmazásba, akkor a jövőbeni bejelentkezési próbálkozásai sikertelenek lesznek. Ebben az esetben a következő „áthidaló” megoldásokat kell alkalmaznia az eszköz regisztrációjának törléséhez.

A Vállalati portál alkalmazás eltávolításakor az eszköz Intune-regisztrációját is törli, vagyis az eszköz nem fog tudni többé hozzáférni a vállalati erőforrásokhoz.  A törlés további következményeiről további információért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

A Vállalati portál alkalmazás eltávolítása előtt az **Eszközadminisztrátorok** beállításba kell lépnie, és ki kell kapcsolnia a **Vállalati portál** elemet. A lépések kissé eltérőek lehetnek attól függően, hogy milyen androidos eszközzel rendelkezik.

Az eszköz Intune-regisztrációjának törlése és a Vállalati portál alkalmazás eltávolítása:

1.  Lépjen a **Settings** (Beállítások) &gt; **Security (Biztonság) &amp; Screen Lock (Képernyőzár)** &gt; **Device administrators** (Eszközadminisztrátorok) elemhez..

    A lépés elvégzésével azonnal törli az eszköz regisztrációját.

2.  Törölje a **Company Portal** (Vállalati portál) melletti jelölőnégyzet jelölését, vagy kapcsolja ki azt..

    Most már eltávolíthatja a Vállalati portál alkalmazást.


### További információ
[Android-eszköz használata az Intune-nal](using-your-android-device-with-intune.md)

<!--HONumber=May16_HO1-->



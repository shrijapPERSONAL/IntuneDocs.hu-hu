---
title: "Az eszköz jelszavának alaphelyzetbe állítása a Vállalati portál webhelyén | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: beba9603ffb43d025132d2d86f0996ff505a9019
ms.openlocfilehash: f9d66fe07173245ff831f204dd120598ad7564db


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Az eszköz jelszavának alaphelyzetbe állítása a Vállalati portál webhelyén

Ha elveszíti egy Intune-ban regisztrált eszköz PIN-kódját vagy jelszavát, az eszköz alaphelyzetbe állításához a [Vállalati portál webhelyét](http://portal.manage.microsoft.com) használhatja. A Vállalati portál webhelyét az Intune-ban regisztrált számítógépek és eszközök felügyeletére, illetve a Vállalati portál alkalmazásban elvégezhető legtöbb feladat végrehajtására használhatja.

> [!NOTE]
> Előfordulhat, hogy a **Jelszó alaphelyzetbe állítása** gomb nem jelenik meg a Vállalati portál webhelyén. Ebben az esetben forduljon a rendszergazdához támogatásért a Vállalati portál webhelyén.

A jelszó alaphelyzetbe állítása:

1.  Nyissa meg a [Vállalati portál webhelyét](http://portal.manage.microsoft.com), és válassza ki azt az eszközt, amelynek a jelszavát alaphelyzetbe kívánja állítani.

2.  Válassza a **Jelszó alaphelyzetbe állítása** elemet.

    ![Az eszköz részletei a Jelszó alaphelyzetbe állítása gombbal](./media/iwp-screen-with-all-options.png)

3.  Válassza a **Kijelentkezés** elemet, és jelentkezzen be újra a munkahelyi vagy iskolai hitelesítő adataival. Az újbóli bejelentkezésnek öt percen belül meg kell történnie.

    ![Alaphelyzetbe állítási üzenet a Kijelentkezés gombbal](./media/iwp-2-sign-out.png)

4.  Válassza a **Jelszó alaphelyzetbe állítása** elemet.

    ![Üzenet, amely elmagyarázza, hogy mi történik a jelszó alaphelyzetbe állításakor](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Az alábbi táblázatban ellenőrizheti, hogyan működik eszközén a **Jelszó alaphelyzetbe állítása** funkció.

    |Eszköz típusa|Mi történik az alaphelyzetbe állításkor?|
    |------------|-----------|
    |Android|Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre|
    |iOS|Eltávolítja a meglévő jelszót, és nem hoz létre ideiglenes jelszót. Ha a Touch ID ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához vagy vásárláshoz, azt újra be kell állítania.|
    |Windows 10 mobil verzió|Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre. Ha a Windows Hello arcfelismerési funkcióját használja a bejelentkezéshez, az továbbra is támogatott lesz.|
    |Windows Phone 8.1|Eltávolítja a meglévő jelszót, és egy számokból álló ideiglenes jelszót hoz létre.|

    5.  Oldja fel az eszköz zárolását, és adjon meg egy új jelszót vagy módosítsa az ideiglenes jelszót az eszköz **Beállítások** menüjében.

    Ha szeretne egy megerősítő értesítést megjeleníteni arról, hogy a jelszó átállítása sikeresen megtörtént, kattintson a Vállalati portál webhelyének felső sarkában található értesítésjelzőre.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Jan17_HO1-->



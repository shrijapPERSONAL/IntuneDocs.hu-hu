---
title: "Az eszköz alaphelyzetbe állítása a Vállalati portál webhelyéről | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: b3a3b7c2a983776f79ffa8562e130bb11e714e29


---


# <a name="reset-your-device-passcode-from-the-company-portal-website"></a>Az eszköz alaphelyzetbe állítása a Vállalati portál webhelyéről

Ha elveszíti egy Intune-ban regisztrált eszköz PIN-kódját vagy jelszavát, az eszköz alaphelyzetbe állításához a [Vállalati portál webhelyét](http://portal.manage.microsoft.com) használhatja. A Vállalati portál webhelyét az Intune-ban regisztrált számítógépek és eszközök felügyeletére, illetve a Vállalati portál alkalmazásban elvégezhető legtöbb feladat végrehajtására használhatja.

> [!NOTE]
> Attól függően, hogy a rendszergazda hogyan konfigurálta az Intune-t, előfordulhat, hogy a Vállalati portál webhelyén nem jelenik meg a **Jelszó alaphelyzetbe állítása** gomb. A jelszó alaphelyzetbe állítása nem támogatott a Windows 8.1 rendszerű eszközökön.

A jelszó alaphelyzetbe állítása:

1.  Nyissa meg a [Vállalati portál webhelyét](http://portal.manage.microsoft.com), és válassza ki azt az eszközt, amelynek a jelszavát alaphelyzetbe kívánja állítani.

2.  Válassza a **Jelszó alaphelyzetbe állítása** elemet.

    ![Az eszköz részletei a Jelszó alaphelyzetbe állítása gombbal](./media/iwp-screen-with-all-options.png)

3.  Válassza a **Kijelentkezés** elemet, és jelentkezzen be újra a munkahelyi vagy iskolai hitelesítő adataival. Az újbóli bejelentkezésnek öt percen belül meg kell történnie.

    ![Alaphelyzetbe állítási üzenet a Kijelentkezés gombbal](./media/iwp-2-sign-out.png)

4.  Válassza a **Jelszó alaphelyzetbe állítása** elemet.

    ![Üzenet, amely elmagyarázza, hogy mi történik a jelszó alaphelyzetbe állításakor](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Az alábbi táblázatban ellenőrizheti, hogyan működik eszközén a **Jelszó alaphelyzetbe állítása** funkció.

    |Platfésm|Support|
    |------------|-----------|
    |Android|Létrehoz egy ideiglenes, alfanumerikus jelszót.|
    |iOS|Eltávolítja a jelszót az eszközről, és nem hoz létre ideiglenes jelszót. Touch ID használata esetén újra be kell állítania azt az eszközön, mert a jelszó alaphelyzetbe állításakor ez az azonosító is törlődik.|
    |Windows 10 (csak mobileszközök esetén)|Létrehoz egy ideiglenes, alfanumerikus jelszót. A Windows Hello támogatott.|
    |Windows Phone 8.1|Létrehoz egy ideiglenes, numerikus jelszót.|
    Miután feloldotta az eszköz zárolását, az új jelszót az eszköz **Beállítások** menüjében állíthatja be.

5.  Oldja fel az eszköz zárolását, majd adjon meg egy új jelszót, vagy módosítsa az ideiglenes jelszót az eszköz **Beállítások** menüjében.

    Ha szeretne egy megerősítő értesítést megjeleníteni arról, hogy a jelszó átállítása sikeresen megtörtént, kattintson a Vállalati portál webhelyének felső sarkában található értesítésjelzőre.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->



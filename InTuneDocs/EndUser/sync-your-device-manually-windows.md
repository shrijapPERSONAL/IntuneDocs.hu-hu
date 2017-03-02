---
title: "Windows-eszköz manuális szinkronizálása | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 4b5f0129d6824a51c36662a1cc7ef4e8a2de9e20
ms.openlocfilehash: ff5a4313337c89da00cb87e0f4dd6c8dcc233361
ms.lasthandoff: 02/18/2017


---

# <a name="sync-your-windows-device-manually"></a>Windows-eszköz manuális szinkronizálása

Előfordulhat, hogy egy alkalmazás telepítése a windowsos eszközre a várhatónál hosszabb időt vesz igénybe. Ilyen esetben megpróbálhatja manuálisan szinkronizálni a windowsos eszközt. A szinkronizálással esetleg gyorsítható a telepítés.

> [!Note]
> Alacsonyabb sebességű hálózatokon, vagy ha egyszerre nagy számú eszközön végeznek letöltést, az alkalmazások telepítése hosszabb időt is igénybe vehet.

A Windows alábbi verzióit manuálisan is lehet szinkronizálni. Ha az eszközön a Windows más verziója fut, a manuális szinkronizálás sajnos nem elérhető.

* [Windows 10 asztali verzió szinkronizálása](#windows-10-desktop)
* [Windows 10 mobil verzió szinkronizálása](#windows-10-mobile)
* [Windows Phone 8.1 szinkronizálása](#windows-phone-81)

## <a name="windows-10-desktop"></a>Windows 10 asztali verzió
A Windows 10 rendszernek egynél több verziója van, így a lépések két részre oszthatók. Annak megállapításához, hogy mely lépések szükségesek, tekintse meg a képernyőképeket, és kövesse azokat a lépéseket, amelyek a leginkább hasonlítanak az eszközön látható állapotra.

1. Kattintson a **Start** gombra, majd a **Beállítások** elemre.

    ![A Start gomb](./media/win10pc-sync-1-start-button.png)

2. A **Beállítások** lapon válassza **Fiókok** lehetőséget.

    ![A Fiókok lehetőség kiválasztása a Beállítások lapon](./media/win10pc-sync-2-settings-accounts.png)

3. A következő két képernyő közül válassza ki azt, amelyen ugyanaz látszik, mint az eszközön. Hajtsa végre a kiválasztott képernyőhöz tartozó lépéseket.

    Ha a „Hozzáférés munkahelyi vagy iskolai rendszerhez” feliratú képernyőt látja, hajtsa végre a [Teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](#steps-to-follow-if-you-see-access-work-or-school) című részben leírt lépéseket.

    ![Szinkronizálási teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Ha a „Hozzáférés munkahelyi rendszerhez” feliratú képernyőt látja, hajtsa végre a [Teendők, ha ezt látja: Hozzáférés munkahelyi rendszerhez](#steps-to-follow-if-you-see-your-account) című részben leírt lépéseket.

    ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>Teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez

1. A **Fiókok** lapon válassza ki a **Munkahelyi vagy iskolai hozzáférés** elemet.

    ![A Hozzáférés munkahelyi vagy iskolai rendszerhez elem kiválasztása](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Válassza ki a munkahelyi vagy iskolai fiókját. Attól függően, hogy a rendszergazda hogyan állította be a rendszert, két fiókot láthat, amelyek az alábbiakban látható példához hasonlóak. Az egyik fiók mellett egy aktatáska látható, a másik mellett a Microsoft emblémája.

    - Ha az aktatáskás fiókot látja, válassza ki azt, és keresse az alatta lévő **Információ** gombot.
    - Ha csak a Microsoft emblémás fiókot látja, válassza ki azt, és keresse az alatta lévő **Információ** gombot.

    ![Válassza ki az aktatáska vagy a Microsoft emblémája melletti fiókot](./media/win10pc-rs1-sync-info-button.png)

3. Kattintson az **Információ** gombra. Az alábbi példához hasonlóan megnyílik egy párbeszédpanel.

    ![Válassza ki az aktatáska vagy a Microsoft emblémája melletti fiókot](./media/win10pc-rs1-sync-button.png)

4. Kattintson a **Szinkronizálás** gombra. Az eszköz Intune-nal való szinkronizálása megtörténik.

### <a name="steps-to-follow-if-you-see-work-access"></a>Teendők, ha ezt látja: Munkahelyi hozzáférés

1. A **Fiókok** lapon válassza a **Munkahelyi hozzáférés** elemet.

    ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10pc-sync-3-work-access.png)

2. A **Regisztrálás eszközfelügyeletre** részen válassza ki a cég nevét.

    ![A cég nevének kiválasztása az eszközfelügyelethez](./media/win10pc-sync-4-tap-com-name.png)

3. Kattintson a **Szinkronizálás** gombra.

    ![Kattintás a Szinkronizálás gombra](./media/win10pc-sync-5-tap-sync.png)

   A gomb a szinkronizálás befejezéséig szürke marad.

   ## <a name="windows-10-mobile"></a>Windows 10 mobil verzió
   Windows 10 Mobile rendszerű eszköz manuális szinkronizálása a lassú alkalmazástelepítés felgyorsítása érdekében:

   1. Lépjen a **Minden alkalmazás** > **Beállítások** > **Fiókok** menüpontra.

       ![Fiókok kiválasztása a Beállítások képernyőn](./media/win10m-sync-1-settings-accounts.png)

   2. Válassza a **Munkahelyi hozzáférés** elemet.

       ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10m-sync-2-work-access.png)

   3. A **Regisztrálás eszközfelügyeletre** részen válassza ki a cég nevét.

       ![A cég nevének kiválasztása az eszközfelügyelethez](./media/win10m-sync-3-tap-comp-name.png)

   4. Kattintson a **Szinkronizálás** ikonra.

       ![Kattintás a Szinkronizálás ikonra](./media/win10m-sync-4-tap-sync.png)

       A képernyő tetején megjelenik a „Fiók szinkronizálása” üzenet. Amíg az eszköz szinkronizálása be nem fejeződik, a **Szinkronizálás** gomb inaktív marad.

## <a name="windows-phone-81"></a>Windows Phone 8.1
Windows Phone 8.1 rendszerű eszköz manuális szinkronizálása a lassú alkalmazástelepítés felgyorsítása érdekében:

1. Lépjen a **Minden alkalmazás** > **Beállítások** > **Munkahely** menüpontra.

    ![Beállítások listája](./media/wp81-1-sync-settings-workplace.png)

2. Válassza ki a cég nevét.

    ![Cég nevének kiválasztása munkahelyi fiókhoz](./media/wp81-2-sync-tap-compname.png)

3. Kattintson a **Szinkronizálás** ikonra.

    ![Kattintás a Szinkronizálás ikonra](./media/wp81-3-sync-tap-sync-button.png)

   A képernyő tetején a „Fiók szinkronizálása” üzenet lesz látható egészen addig, amíg az eszköz szinkronizálása be nem fejeződik.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).


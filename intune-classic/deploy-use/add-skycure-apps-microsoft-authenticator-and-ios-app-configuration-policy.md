---
title: Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat felvétele
description: A Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat felvétele a klasszikus Intune-portálra.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 45412855db4afd9dd03b2139a3720d1619d293e2
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat felvétele

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Skycure-alkalmazásokat az Intune-nal fel kell vennie és üzembe kell helyeznie annak érdekében, hogy a felhasználók értesítést kapjanak a mobileszközükön észlelt fenyegetésekről, illetve útmutatást azok elhárításához.

Ezenfelül a [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) alkalmazásra is szükség van, hogy az Azure AD ellenőrizni tudja a felhasználók identitását, továbbá arra az iOS-es alkalmazáskonfigurációs szabályzatra, amely az iOS-es Skycure-alkalmazást az Intune és az Azure AD egyszeri bejelentkezés (SSO) használatára utasítja, hogy a felhasználóknak ne kelljen minden alkalommal beírni a felhasználónevüket és jelszavukat, amikor bejelentkeznek a Skycure alkalmazásba.

## <a name="before-you-begin"></a>Előkészületek

-   Az alábbi lépéseket a [klasszikus Intune-portálon](https://manage.microsoft.com/) kell elvégezni.

-   Ehhez a művelethez a korábban a Skycure Management konzolon konfigurált Azure AD-fiókot kell használni, amely megegyezik a klasszikus Intune-portálra való bejelentkezéshez használttal.

-   Készítse elő a Skycure-integrációs fájlt, amelyet korábban .zip formátumban letöltött a Skycure Management konzolról, és amelyben megtalálható az iOS-es alkalmazáskonfigurációs szabályzat paramétereit tároló **skycure\_configuration.plist** fájl.

-   Előzőleg ismerkedjen meg a következő eljárásokkal:

    -   [Alkalmazás felvétele az Intune-ba](/intune-classic/deploy-use/add-apps)

    -   [iOS-es alkalmazáskonfigurációs szabályzat felvétele az Intune-ba](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-add-the-skycure-app-for-android"></a>Az Androidra készült Skycure alkalmazás felvétele

1.  A klasszikus Intune-portálon az **Alkalmazások** &gt; **Alkalmazások felvétele** elemet választva indítsa el az Intune Software Publishert, és kattintson a **Tovább** gombra.

2.  A **Szoftver telepítése** lapon válassza a **Külső hivatkozás** lehetőséget, majd az [Adja meg az URL-címet](https://play.google.com/store/apps/details?id=com.skycure.skycure) mezőbe illessze be az **Androidra készült Skycure alkalmazás URL-címét**.

    ![URL-cím megadása az Intune Software Publisherben](../media/mtp/skycure-add-apps-1.png)

3.  A **Szoftver leírása** lapon töltse ki a **Gyártó**, a **Név** és a **Leírás** mezőket, jelölje be a **Megjelenítés kiemelt alkalmazásként és kiemelés a vállalati portálon** jelölőnégyzetet, majd kattintson a **Tovább** gombra.

    ![A Szoftver leírása lap az Intune Software Publisherben](../media/mtp/skycure-add-apps-2.png)

4.  Kattintson a **Feltöltés**, majd a **Bezárás** gombra.

## <a name="to-add-the-skycure-app-for-ios"></a>Az iOS-re készült Skycure alkalmazás felvétele

1.  A klasszikus Intune-portálon az **Alkalmazások** &gt; **Alkalmazások felvétele** elemet választva indítsa el az Intune Software Publishert, és kattintson a **Tovább** gombra.

2.  A **Szoftver telepítése** lapon válassza a **Felügyelt iOS-alkalmazás az App Store-ból** lehetőséget, majd az [Adja meg az URL-címet](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) mezőbe illessze be az **iOS-re készült Skycure alkalmazás URL-címét**.

    ![Felügyelt iOS-alkalmazás megadása az Intune Software Publisherben](../media/mtp/skycure-add-apps-3.png)

3.  A **Szoftver leírása** lapon töltse ki a **Gyártó**, a **Név** és a **Leírás** mezőket, jelölje be a **Megjelenítés kiemelt alkalmazásként és kiemelés a vállalati portálon** jelölőnégyzetet, majd kattintson a **Tovább** gombra.

    ![Az Intune Software Publisher beállításai](../media/mtp/skycure-add-apps-4.png)

4.  A **Követelmények** lapon a **Mobileszköz** típusa listából válassza a **Bármely** elemet, majd kattintson a **Tovább** gombra.

5.  Kattintson a **Feltöltés**, majd a **Bezárás** gombra.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Az iOS-re készült Microsoft Authenticator alkalmazás felvétele

1.  A klasszikus Intune-portálon az **Alkalmazások** &gt; **Alkalmazások felvétele** elemet választva indítsa el az Intune Software Publishert, és kattintson a **Tovább** gombra.

2.  A **Szoftver telepítése** lapon válassza a **Felügyelt iOS-alkalmazás az App Store-ból** lehetőséget, majd az [Adja meg az URL-címet](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) mezőbe illessze be az **iOS-re készült Microsoft Authenticator alkalmazás URL-címét**.

    ![Felügyelt iOS-alkalmazás megadása az Intune Software Publisherben 2](../media/mtp/skycure-add-apps-5.png)

3.  A **Szoftver leírása** lapon töltse ki a **Gyártó**, a **Név** és a **Leírás** mezőket, jelölje be a **Megjelenítés kiemelt alkalmazásként és kiemelés a vállalati portálon** jelölőnégyzetet, majd kattintson a **Tovább** gombra.

    ![Felügyelt iOS-alkalmazás megadása az Intune Software Publisherben 3](../media/mtp/skycure-add-apps-6.png)

4.  A **Követelmények** lapon a **Mobileszköz** típusa listából válassza a **Bármely** elemet, majd kattintson a **Tovább** gombra.

5.  Kattintson a **Feltöltés**, majd a **Bezárás** gombra.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat felvétele

1.  A klasszikus Intune-portálon válassza a **Házirend** &gt; **Áttekintés &gt; Házirend hozzáadása** lehetőséget.

2.  A szabályzatok listájában bontsa ki az **iOS** csomópontot, válassza a **Mobilalkalmazás-konfigurációs házirend (iOS 8.0 és újabb)** lehetőséget, majd a **Házirend létrehozása** elemet.

    ![iOS-alkalmazáskonfigurációs szabályzat](../media/mtp/skycure-add-apps-7.png)

3.  A **Házirend létrehozása** lap **Általános** részében adja meg az iOS-es alkalmazáskonfigurációs szabályzat nevét és igény szerint a leírását.

    a.  Nyissa meg a **skycure\_configuration.plist** fájlt a Jegyzettömbbel vagy hasonló szövegszerkesztővel, másolja ki a tartalmát, illessze be a **Mobilalkalmazás-konfigurációs házirend** szövegtörzsébe, és válassza az **Érvényesítés**, majd a **Házirend mentése** lehetőséget.

       ![iOS-alkalmazáskonfigurációs szabályzat 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>További lépések

[Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es alkalmazáskonfigurációs szabályzat üzembe helyezése](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

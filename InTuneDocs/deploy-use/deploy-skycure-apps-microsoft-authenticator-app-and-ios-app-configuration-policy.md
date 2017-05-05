---
title: "Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat üzembe helyezése | Microsoft Docs"
description: "A Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat üzembe helyezése a klasszikus Intune-konzolon."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 0b6f9bde77b5b88cc66ab10419b7d6e083f7cb6b
ms.lasthandoff: 04/25/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es alkalmazáskonfigurációs szabályzat üzembe helyezése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Előkészületek

-   Az alábbi lépéseket a [klasszikus Intune-konzolon](https://manage.microsoft.com/) kell elvégezni.

-   A korábban a Skycure Management konzolon konfigurált Azure AD-fiókot használja, amely elvileg megegyezik a klasszikus Intune-konzolra való bejelentkezéshez használttal.

-   Előzőleg ismerkedjen meg a következő eljárásokkal:

    -   [Alkalmazás üzembe helyezése az Intune-nal](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)

    -   [iOS-es alkalmazáskonfigurációs szabályzat üzembe helyezése](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>A Skycure-alkalmazások, a Microsoft Authenticator alkalmazás és az iOS-es alkalmazáskonfigurációs szabályzat üzembe helyezése

1.  A klasszikus Intune-konzolon az **Alkalmazások** &gt; **Alkalmazások** elemet választva nézheti meg a felügyelhető alkalmazások listáját.

2.  Jelölje ki az alábbi alkalmazásokat:

    a.  Microsoft Authenticator

    b.  Androidra készült Skycure alkalmazás

    c.  iOS-re készült Skycure alkalmazás

       ![A klasszikus Intune-konzol a telepítendő alkalmazásokkal](../media/mtp/skycure-deploy-app-1.png)

3.  Kattintson az **Üzembe helyezés kezelése** elemre, válassza ki azt az Azure AD biztonsági csoportot, amelyben a Skycure-felhasználók vannak, és kattintson a **Tovább** gombra.

4.  A **Központi telepítési művelet** lapon válassza a **Szükséges telepítés** elemet a **Jóváhagyás** listából, majd kattintson a **Tovább** gombra.

    ![A klasszikus Intune-konzol Központi telepítési művelet lapja](../media/mtp/skycure-deploy-app-2.png)

5.  A **VPN-profil** lapon válassza a **Nincs** lehetőséget a **VPN-szabályzat** listából, majd kattintson a **Tovább** gombra.

6.  A **Mobilalkalmazás konfigurálása** lapon válassza az előzőleg létrehozott iOS-es alkalmazáskonfigurációs szabályzatot az **Alkalmazáskonfigurálási szabályzat** listából, és kattintson a **Befejezés** gombra.

    ![A klasszikus Intune-konzol Mobilalkalmazás konfigurálása lapja](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>További lépések

[A Skycure és az Intune közötti integráció beállítása](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)


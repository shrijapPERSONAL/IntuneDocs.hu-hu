---
title: "Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése az Intune-nal való használathoz"
titleSuffix: Intune on Azure
description: "Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése az Intune-nal való használathoz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ffe1027e90203d4e300a2446f15e72cc5bf53973
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése

## <a name="before-you-begin"></a>Előkészületek

A következő lépések előtt be kell jelentkezni a Skycure Management konzolon.

> [!TIP] 
> Ha Microsoft Internet Explorer 11-et vagy Edge-et használ, akkor lehet, hogy a Skycure Management konzolt InPrivate módban kell megnyitnia.

## <a name="to-download-the-ios-app-configuration-policy"></a>Az iOS-es alkalmazáskonfigurációs szabályzat letöltése

1.  Nyissa meg a [Skycure Management konzolt](https://aad.skycure.com).

2.  Írja be **Skycure-adminisztrátori hitelesítő adatait**, majd kattintson a **Tovább** gombra.

    ![Bejelentkezés a Skycure Management konzolra](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > A Skycure-adminisztrátor felhasználóneve egy olyan e-mail-fiók, amely egyúttal érvényes felhasználói fiókot is jelöl az Azure Active Directoryban. Ellenkező esetben nem fog tudni bejelentkezni. A Skycure az Azure Active Directoryval hitelesíti egyszeri bejelentkezéshez (SSO) az adminisztrátor felhasználónevét.

3.  Kattintson a **Settings** (Beállítások) &gt; **Device Management Integrations** (Eszközfelügyelet-integráció) &gt; **EMM Integration Selection** (EMM-integráció kiválasztása) elemre, válassza a **Microsoft Intune** lehetőséget, és mentse a választást.

4.  Kattintson az **Integration setup files** (Integráció-telepítőfájlok) hivatkozásra, és mentse a létrejövő \*.zip fájlt. A .zip-fájlban található a **skycure\_configuration.plist** fájl, amellyel létrehozható az iOS-es alkalmazáskonfigurációs szabályzat a klasszikus Intune-konzolon.

![A Skycure-integráció telepítőfájljai](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>További lépések

[Skycure-alkalmazások, Microsoft Authenticator-alkalmazás és az iOS-es konfigurációs szabályzat felvétele és hozzárendelése](mtd-apps-ios-app-configuration-policy-add-assign.md)
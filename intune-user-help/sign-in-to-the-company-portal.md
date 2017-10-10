---
title: "Hogyan kell bejelentkezni a Céges portál alkalmazásba | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ca6d811d884b5405bdb4e5f096366c123d8e00d1
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/28/2017
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Hogyan jelentkezhetek be a Céges portál alkalmazásba? <!--User Story 1132123-->

A Céges portál használatával hozzáférhet olyan céges erőforrásokhoz, mint az e-mailek és az üzletági alkalmazások. A Céges portálra kétféleképpen jelentkezhet be:

* Munkahelyi e-mail-cím és jelszó használata
* Más eszközről történő bejelentkezés

Az alábbi képeken az iOS rendszer látható, de a folyamat gyakorlatilag ugyanilyen az Android és Windows rendszerű eszközökön is.

## <a name="signing-in-with-your-email-address-and-password"></a>Bejelentkezés e-mail-cím és jelszó használatával

1. Nyissa meg az eszközön a Céges portált, és koppintson a **Bejelentkezés** elemre.

  ![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](/intune/media/cp_ios_aad_signin_after_1704_001.png)

  Nincs telepítve az eszközén a Céges portál alkalmazás? Itt olvashat a telepítésről és a letöltésről [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) vagy [Android](install-the-company-portal-app-android.md) rendszerű eszközök esetén.

2. Adja meg a **munkahelyi vagy iskolai fiókját**.

  ![A felhasználónak ugyanazon az oldalon csak az e-mail-címét kell megadnia, nem pedig mind az e-mail-címét, mind a jelszavát.](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. Várjon egy pillanatig, amíg a rendszer elfogadja az e-mail-címet, majd adja meg a jelszót.

  ![A felhasználótól csak akkor kéri a rendszer a jelszavát ha már helyesen megadta az e-mail-címét.](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. Amint a Céges portál elfogadta az adatokat, lezajlik a bejelentkezés, és hozzáférhet a céges erőforrásokhoz.   

  ![A hitelesítési folyamat végeztével a Céges portál alkalmazás bejelentkezik, amit egy betöltést jelző sáv jelez.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-from-another-device"></a>Más eszközről történő bejelentkezés

Ha nem jelszóval jelentkezik be a céges erőforrások használatához, más eszköz segítségével is megerősítheti a jogosultságát, és azt hogy a megfelelő hozzáférési szintekkel rendelkezik. Ha a vállalat intelligens kártyákat használ a számítógépek eléréséhez, valószínű hogy egy másik eszköz használatával kell bejelentkeznie.

1. Az e-mail-cím megadása helyett koppintson az e-mail szövegmező alatti **Bejelentkezés másik eszközről** hivatkozásra.

  ![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. Ekkor egy egyedi, egyszer használatos kódot kap a Céges portálra történő bejelentkezéshez.

  ![A rendszer arra kéri a felhasználót, hogy látogassa meg a aka.ms/devicelogin oldalt a munkagéphez tartozó, megjelenített egyedi kódot használva a bejelentkezéshez.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. Nyissa meg a böngészőt az egyéb eszközön, és navigáljon a [https://aka.ms/devicelogin](https://aka.ms/devicelogin) címre, ahol megadhatja a kódot.

  ![A felhasználó munkagépén futó böngészőablak képe (nem pedig a Céges portál alkalmazásé). A megjelenített „Eszközbejelentkezés” oldal arra kéri a felhasználót, hogy adja meg a Céges portál alkalmazástól kapott kódot.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Miután a **Eszközbejelentkezés** oldal ellenőrizte a kódot, a __Folytatás__ elem kijelölésével engedélyezze az eszközön a Céges portál bejelentkezését.

  ![A felhasználó beírta a mezőbe az egyedi kódját, az „Eszközbejelentkezés” webhely pedig a felhasználó megerősítését kéri, hogy az Intune Céges portálnak kell-e bejelentkezési engedélyt kapnia.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. A kód ellenőrzése után bezárhatja az ablakot.

  ![Jóváhagyást jelző oldal, amely megerősíti, hogy a felhasználó bejelentkezett a Céges portál alkalmazásra az eszközén, és hogy ez az oldal bezárható.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Az eredetileg használt eszközön kezdetét veszi a Céges portál bejelentkezése.

  ![Miután a hitelesítési folyamat lezárult, bejelentkezik a Céges portál alkalmazás, és a folyamatot egy betöltést jelző sáv mutatja.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com).

---
title: "Telepítenie kell a Symantec Endpoint Protection Mobile alkalmazást az Android-eszközön | Microsoft Docs"
description: "Tájékoztató a SEP Mobile alkalmazás Android-eszközön való telepítéséről."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 627cd171-6e1b-439e-809a-2e6f007c4b3d
searchScope: User help
ROBOTS: 
ms.custom: intune-enduser
ms.openlocfilehash: f94a7cdb4feeea19527efec6486d09efcaca9b67
ms.sourcegitcommit: 1135765fd3ac2149663341d8107f656aba236493
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2017
---
# <a name="you-need-to-install-symantec-endpoint-protection-mobile-on-your-android-device"></a>Telepítenie kell a Symantec Endpoint Protection Mobile alkalmazást az Android-eszközön

A cég informatikai támogató szolgálata csak a Symantec Endpoint Protection (SEP) Mobile alkalmazás telepítését követően teszi lehetővé, hogy hozzáférjen a munkájához. Ez az alkalmazás az esetleges fenyegetések felderítésével segíti az eszköz védelmét.

Ha problémája akad a telepítéssel, próbálja ki a témakör végén olvasható hibaelhárítási lépéseket.

**A következőket kell tennie:**

1. Húzza le az értesítési sávot a képernyő tetejéről és koppintson a **Szükséges alkalmazás – A(z) Skycure telepítése a Play Áruházból** gombra. Ugyanez a Céges portál alkalmazásban is elérhető a __Megfelelőségi részletek__ között.

  <!--![The compliance details page on an Android device. The device is not in compliance, with a message at the bottom of the Company Portal page that says the device doesn't meet the mobile risk policy, and that Skycure must be opened to resolve the issue.](./media/skycure-resolves-compliance-android.png)-->

2. Ekkor megnyílik a SEP Mobile telepítési lapja a Play Áruházban. Telepítse a SEP Mobile-t, majd az **ELFOGADÁS** elemre kattintva adjon hozzáférést a SEP Mobile-nak az eszközhöz.

3. Nyissa meg a SEP Mobile-t, és koppintson a **VERIFY** (Ellenőrzés) elemre.

4. Koppintson a **Bejelentkezés a következővel: Azure Active Directory** gombra, majd lépjen be abba a fiókba, amelyet a munkahelyi vagy iskolai e-mailek és fájlok elérésére használ.

5. Válassza ki azt a fiókot, amit munkahelyi vagy iskolai e-mailekhez és fájlokhoz való hozzáféréshez használ, majd koppintson a **FIÓK HOZZÁADÁSA** gombra.

6. Az **Elfogadás** gombra koppintva engedélyezze a SEP Mobile-nak a bejelentkeztetést és a profilja olvasását.

7. Olvassa el, hogy a SEP Mobile miként védi az eszközét, majd koppintson az **OK** gombra. A SEP Mobile beállítása néhány másodperc alatt lezajlik, utána pedig megkezdődik az eszközön a biztonsági fenyegetések keresése.

8. A SEP Mobile elindul, és azonnal elkezd biztonsági fenyegetéseket keresni az eszközén.

  <!--![Skycure is analyzing your device for security threats.](./media/skycure-scan-in-progress-android.png)-->

  Ha a SEP Mobile biztonsági fenyegetést talál az eszközén, megjeleníti a problémamegoldáshoz szükséges tudnivalókat.

  <!--![Skycure found a security threat.](./media/skycure-found-a-threat-android.png)-->

  Ha nem talál fenyegetést, mindhárom veszélyforrástípus zölddel jelenik meg.

    A Céges portál **Eszköz adatai** képernyőjén látható, hogy az eszköz immár megfelel a cég biztonsági előírásainak.

    ![Eszköze most már megfelel a szabályzatoknak](./media/mtd-device-now-compliant-android.png)

**Ha sikertelen a telepítés**

Egyes esetekben előfordulhat, hogy a telepítés Öntől független technikai okokból meghiúsul. Ilyenkor próbálja a SEP Mobile alkalmazást [manuálisan telepíteni a Play Áruházból](https://play.google.com/store/apps/details?id=com.skycure.skycure).

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).

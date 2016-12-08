---
title: "A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0d357dc0-3e14-43d0-9874-6886ebc847fc
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: d55c7d4a7c77472453e6d317a22c4ad6209255a5


---

# <a name="you-are-prompted-to-install-lookout-for-work"></a>A rendszer felszólítja a Lookout for Work telepítésére

A rendszergazda csak a Lookout for Work alkalmazás telepítését követően teszi lehetővé, hogy hozzáférjen a munkájához. Ez a szolgáltatás az esetleges biztonsági fenyegetések felderítésével segít az eszköz védelmében.

Ha problémája akad a telepítéssel, próbálja ki a témakör végén olvasható hibaelhárítási lépéseket.


**A következőket kell tennie:**

1.  Húzza le az értesítési sávot a képernyő tetejéről és koppintson a **Szükséges alkalmazás – A(z) Lookout for Work telepítése a Play Áruházból** gombra.

    ![a rendszer felszólítja a Lookout for Work telepítésére](./media/lookout-required-app-install-android.png)

    Ekkor megnyílik a Lookout for Work telepítési lapja a Play Áruházban.

2.  Telepítse a Lookout for Worköt, majd koppintson az **ELFOGADÁS** gombra, hogy a Lookout for Work hozzáférjen eszközéhez.

    ![koppintson az Elfogadás gombra, hogy a Lookout for Work hozzáférhessen eszközéhez](./media/lookout-accept-store-permissions-android.png)

3. Nyissa meg a Lookout for Worköt, és koppintson az **AKTIVÁLÁS** gombra.

    ![nyissa meg a Lookout for Worköt és koppintson az Aktiválás gombra](./media/lookout-activate-button-android.png)

4. Koppintson a **Bejelentkezés a következővel: Azure Active Directory** gombra, majd lépjen be abba a fiókba, amelyet a munkahelyi vagy iskolai e-mailek és fájlok elérésére használ.

    ![bejelentkezés a munkahelyi vagy iskolai fiókba](./media/lookout-sign-in-azure-android.png)

5. Válassza ki azt a fiókot, amit munkahelyi vagy iskolai e-mailekhez és fájlokhoz való hozzáféréshez használ, majd koppintson a **FIÓK HOZZÁADÁSA** gombra.

    ![válassza ki munkahelyi vagy iskolai fiókját, majd koppintson a Fiók hozzáadása gombra](./media/lookout-pick-account-android.png)

6. Koppintson az **Elfogadás** gombra, hogy engedélyezze a Lookout for Wordnek, hogy beléptesse és beolvassa a profilját.

    ![koppintson az Elfogadás gombra, hogy engedélyezze a Lookout for Wordnek, hogy beolvassa a profilját](./media/lookout-needs-permission-to-view-profile-android.png)

    A képernyőn látható, hogy a Lookout for Work éppen csatlakozik a Lookout Security Cloudhoz.

7. Ellenőrizze azon elemeket, amelyek arról tájékoztatnak, hogy a Lookout miként védi eszközét, majd koppintson az **OK** gombra.

    ![tekintse át, hogy a Lookout for Work miként védi eszközét](./media/lookout-how-it-protects-your-device-android.png)

    Ha az alábbi képernyőt látja, akkor a Lookout telepítése befejeződött, és létrejött a kapcsolat.

    ![sikeresen létrejött a kapcsolat a Lookout for Workhöz](./media/lookout-you-are-now-connected-android.png)

    A Lookout for Work azonnal elkezd biztonsági fenyegetéseket keresni az eszközén. Ha nem talál egyet sem, az alábbi képernyő jelenik meg.

    ![A Lookout for Work nem talált biztonsági fenyegetést](./media/lookout-scan-no-threats-found-android.png)

    A Munkahelyi portál Eszköz adatai képernyőjén látható, hogy immár megfelel vállalata biztonsági előírásainak.

    ![eszköze megfelel a szabályzatoknak](./media/lookout-device-now-compliant-android.png)

    Ha a Lookout for Work biztonsági fenyegetést talál eszközén, megjeleníti a problémamegoldáshoz szükséges tudnivalókat.

**Ha sikertelen a telepítés**

Egyes esetekben előfordulhat, hogy a telepítés Öntől független technikai okokból meghiúsul. Ha ez történik, próbálja meg a Play Áruházból telepíteni a Lookout for Worköt: [https://play.google.com/store/apps/details?id=com.lookout.enterprise](https://play.google.com/store/apps/details?id=com.lookout.enterprise) 

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->



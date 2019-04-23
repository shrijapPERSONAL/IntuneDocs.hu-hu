---
title: Az Intune vállalati portál Android-eszköz regisztrálása |} A Microsoft Docs
description: Az Intune vállalati portál Android-eszköz regisztrálását mutatja
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e9120110b1840d1f5075549737722328ef2551f
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901821"
---
# <a name="enroll-your-device-with-company-portal"></a>Regisztrálja az eszközét a vállalati portál  
Személyes vagy vállalati tulajdonú Android-eszköz regisztrálása a vállalati e-mailekhez, alkalmazásokhoz és adatokhoz való biztonságos eléréséhez. Vállalati portál Android-eszközön támogatja, beleértve a Samsung Knox-, Android 4.4-es vagy újabb rendszerű.  

> [!NOTE]
> A Samsung Knox olyan biztonsági szolgáltatás, amelyek bizonyos Samsung-eszközöknek további védelem lehetőségeken natív Android nyújtotta. Ha Samsung Knox-eszközzel rendelkezik-e > lépjen a **beállítások** > **eszközről**. Ha nem lát **Knox verzió** felsorolásban, akkor natív Android-eszközzel rendelkezik.    

## <a name="enroll-device"></a>Eszköz regisztrálása  
Ügyeljen arra, hogy [telepítése az Intune vállalati portál nevű ingyenes alkalmazást a Google Play áruházból](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). 

A beléptetés során előfordulhat, hogy megkérdezi, hogy az válasszon egy kategóriát, amely a legjobban ismerteti, hogyan használhatja az eszközt. A cég informatikai támogatási válasz használatával ellenőrizni az alkalmazásokat, amely hozzáféréssel rendelkezik.  

1. Nyissa meg a Vállalati portál alkalmazást.  

3. A Vállalati portál alkalmazás **üdvözlőképernyőjén** koppintson a **Bejelentkezés** elemre, és jelentkezzen be a munkahelyi vagy az iskolai fiókjával.

   ![Androidos üdvözlőképernyőre készült Céges portál alkalmazás, amely arra kéri a felhasználót, hogy jelentkezzen be a szükséges munkahelyi vagy iskolai fiókjával. Arra is figyelmeztet, hogy a Microsoft-fiókok és egyéb személyes fiókok nincsenek engedélyezve.](./media/and-enroll-0-welcome-screen.png)   

4. Ha a cég használati feltételeinek elfogadására kéri, koppintson **ELFOGADÁS**. Ezen a képernyőn kis mértékben eltérhet az alábbi képernyőképet. 

   ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5. Jelentkezzen be a Vállalati portál alkalmazásba a munkahelyi vagy az iskolai e-mail címének és jelszavának használatával, majd koppintson a **Bejelentkezés** elemre.

   ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6. A **Vállalati hozzáférés beállítása** képernyőn koppintson a **FOLYTATÁS** elemre.

   ![A vállalati hozzáférés beállítási képernyője](/intune/media/android_cp_enroll_01_1709_new.png)

   > [!NOTE]
   > A sárga háromszög nem hibát jelez, hanem azt mutatja, hogy néhány lépés még hátravan a regisztráció folyamatából.

7. Tekintse át a listában, hogy a cég informatikai támogatási szolgálata milyen tartalmakhoz férhet hozzá az eszközén, majd koppintson a **FOLYTATÁS** gombra.

   ![Adatvédelmi beállítások](/intune/media/android_cp_enroll_02_after_1710.png)

8. A **Következő lépések** képernyőn olvassa el, mi történik a regisztráció során, majd koppintson a **REGISZTRÁCIÓ** elemre.

   ![A „Mi a következő lépés?” képernyő](/intune/media/android_cp_enroll_03_after_1710.png)

9. Ha az Android 6.0-s vagy újabb verzióját használja, végezze el ezt a lépést. Egyéb esetben lépjen a következő lépésre.

   Ha a cég informatikai támogatási szolgálata létrehozott bizonyos szabályzatokat, akkor előfordulhat, hogy megjelennek az alábbi üzenetek:
   - **Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)**

     ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

   Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert **a Microsoft soha nem indít telefonhívásokat, és nem is kezeli az Ön hívásait**! A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. A hozzáférés engedélyezésekor csupán annyi történik, hogy engedélyezi az eszköz számára az eszköz nemzetközi mobilkészülék-azonosító (IMEI) számának elküldését az Intune-nak. A sorozatszámhoz hasonló IMEI szám a mobileszköz egyedi azonosítója.

   Ha megtagadja a hozzáférést, az üzenet jelenik meg újra a legközelebb bejelentkezik a vállalati portálhoz. Kapcsolja ki a további üzeneteket, jelölje be **ne kérdezzen rá ismét**. A hozzáférési engedély fordított, lépjen a **beállítások** > **alkalmazások** > **céges portál** > **engedélyek**   >  **Phone**, majd kapcsolja be az engedélyt.  

   - **Allow Company Portal to access your contacts? (Engedélyezi, hogy a Munkahelyi portál hozzáférjen a névjegyekhez?)**

     ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

     Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert **a Microsoft soha nem fér hozzá a névjegyekhez.** A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. Ha engedélyezi a hozzáférést, lehetővé teszi a Vállalati portál alkalmazásnak munkahelyi fiók létrehozását, használatát és kezelését.

     Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb bejelentkezik a Vállalati portálba, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket. Amennyiben később ismét engedélyezni szeretné a hozzáférést, a **Beállítások** &gt; **Alkalmazások** &gt; **Vállalati portál** &gt; **Engedélyek** &gt; **Telefon** lapon teheti ezt meg.

10. Az **Activate device administrator** (Eszközadminisztrátor aktiválása) képernyőn koppintson az **Aktiválás** elemre.

    ![Az „Eszközadminisztrátor aktiválása” képernyő](./media/and-enroll-5-activate.png)

    A Céges portálnak az eszközfelügyelethez eszközadminisztrátori szerepkörre van szüksége. Ez feljogosítja a rendszergazdát bizonyos információ megnézésére (például hogy Ön hányszor próbálta meg feloldani a zárolási képernyőt), és bizonyos műveletek elvégzésére.    

    A Microsoftnak nincs befolyása erre az üzenetre, és értjük, hogy a megfogalmazása drasztikusnak tűnhet, de a Céges portál nem tudja csak azokat a korlátozásokat és hozzáféréseket megjeleníteni, amelyek az adott szervezetre érvényesek: csak ezek mindegyikét lehet egyszerre engedélyezni ezen a képernyőn. Ha az eszköz szervezeti használatával kapcsolatos kérdése van, a [Céges portál webhelyen](https://go.microsoft.com/fwlink/?linkid=2010980) látható elérhetőségek valamelyikén kérjen tájékoztatást a cég informatikai támogatási szolgálatától.  

11. Az útmutatást követve írja be a PIN-kódját vagy a jelszavát. Ha korábban már beállított egy PIN-kódot vagy egy jelszót a szóban forgó eszközön, ez a képernyő nem jelenik meg, és új PIN-kódot vagy jelszót sem kell megadnia.  

    ![Adjon meg PIN-kódot vagy jelszót](./media/and-enroll-6-PIN-native.png)

12. Ha Samsung Knox-eszközt használ, koppintson a **Megerősítés** elemre. Ekkor megjelenik egy üzenet, hogy az eszköz regisztrálása folyamatban van. Ha natív Android-eszközt használ, akkor csak egy üzenet jelenik meg arról, hogy az eszköz regisztrálása folyamatban van, ahogy az alábbi képernyőképen látható.

    ![Samsung Knox adatvédelmi szabályzat](./media/and-enroll-7-knox-privacy-policy.png)

    Ezen a képernyőképen az látható, hogy az eszköz regisztrálása folyamatban van.

    ![„Eszköz regisztrálása” képernyő](./media/and-enroll-8-device-enrolling.png)

13. Amikor megjelenik a **Vállalati hozzáférés beállítása** képernyő, koppintson a **FOLYTATÁS** elemre. Ha megjelenik egy üzent arról, hogy az eszköz nem megfelelő, kövesse az utasításokat a probléma megoldásához, majd koppintson a **FOLYTATÁS** elemre.

    ![Az eszköz nem megfelelő, de regisztrálva van](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Megoldásra váró eszközmegfelelőségi problémák jelennek meg](/intune/media/android_cp_enroll_03_post_1709.png)

    A részletek megtekintéséhez koppintson a problémára.

    ![Bővített eszközmegfelelőségi problémák](/intune/media/android_cp_enroll_04_post_1709.png)

    ![A vállalati hozzáférés beállítási képernyője](./media/and-enroll-9d-comp-access-setup.png)  

14. A **Vállalati hozzáférés beállítása befejeződött** képernyőn koppintson a **KÉSZ** elemre. Ezzel megtörtént az eszköz regisztrálása.

    ![„A vállalati hozzáférés beállítása befejeződött” képernyő](./media/and-enroll-10-comp-access-setup-complete.png)

## <a name="next-steps"></a>További lépések  

Mielőtt vállalati alkalmazások telepítése, Ugrás **beállítások** > **biztonsági**, és kapcsolja be a **ismeretlen források**. Alkalmazások telepítésének megkísérlése előtt nem kapcsolja ezt a beállítást, ha a következő üzenetet láthatja: "A telepítés letiltva. Biztonsági okokból az eszköz blokkolja az ismeretlen forrásból származó alkalmazások telepítését.” A hiba-párbeszédpanelen található **Beállítások** elemre koppintva könnyen az **Ismeretlen források** beállításhoz ugorhat.  

> [!Note]
> Ha a szervezete távközlésiköltség-kezelő szoftvert használ, az eszköz teljes regisztrálásához még néhány lépést el kell végezni. További információért [kattintson ide](enroll-your-device-with-telecom-expense-management-android.md).

Ha hibaüzenet jelenik meg az Intune-ban az eszköz regisztrálása közben, akkor az [e-mailt a cég informatikai támogatási](send-logs-to-your-it-admin-by-email-android.md).  

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.

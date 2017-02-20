---
title: "Android-eszköz regisztrálása az Intune-ban | Microsoft Docs"
description: "Egy Android-eszköz regisztrálását mutatja be az Intune-ban"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 9530eb45bf027c66c4a36e4cea1ec05c5f15a6e5
ms.openlocfilehash: b1de425a00e3c4200f71c8bf03661e4d0aca45c7


---


# <a name="enroll-your-android-device-in-intune"></a>Android-eszköz regisztrálása az Intune-ban

Ha munkahelye vagy iskolája a Microsoft Intune-t használja, Android-eszközének regisztrálásával hozzáférhet a vállalati levelezéséhez, fájljaihoz és egyéb vállalati forrásokhoz. Az eszközök regisztrálása lehetővé teszi az informatikai osztály számára ezeknek a munkahelyi vagy iskolai erőforrásoknak a kezelését és védelmét, miközben Ön a kívánt eszközön végezheti a feladatait. További információk a regisztrációval kapcsolatban: [Mi történik a Vállalati portál alkalmazás telepítésekor és az eszköz regisztrálásakor?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md),

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

Ezek a regisztrálási útmutatók a natív és a Samsung KNOX Android-eszközökre vonatkoznak. A Samsung KNOX olyan biztonsági szolgáltatás, amelynek segítségével bizonyos Samsung-eszközöknek további védelmet biztosíthat a natív Android nyújtotta lehetőségeken felül. A **Beállítások** > **Az eszköz névjegye** területen megállapíthatja, hogy Samsung KNOX-eszközzel rendelkezik-e. Ha nem jelenik meg a „KNOX verzió” kifejezés, akkor natív Android-eszközzel rendelkezik.

A regisztráció előtt vagy után a rendszer megkérheti, hogy válasszon ki egy olyan kategóriát, amely a leginkább illik az Ön eszközhasználatára. A rendszergazda ezen a kategórián keresztül segít ellenőrizni az alkalmazásokat, amelyekhez hozzáfér.

Ha hibaüzenet jelenik meg az eszköz Intune-regisztrálása közben, akkor a [regisztrálási hibák elküldhetők a rendszergazdának](send-enrollment-errors-to-your-it-admin-android.md).

**Android-eszköz regisztrálása:**

1.  Telepítse az Intune Vállalati portál nevű ingyenes alkalmazást a [Google Play áruházból](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Nyissa meg a Microsoft Intune Vállalati portál alkalmazást.

3.  A Vállalati portál alkalmazás **üdvözlőképernyőjén** koppintson a **Bejelentkezés** elemre, és jelentkezzen be a munkahelyi vagy az iskolai fiókjával.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Ha a rendszergazda kikötéseket és feltételeket írt elő a munkahely erőforrásainak használatához, az **ELFOGADÁS** gombra koppintva fogadja el őket.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Jelentkezzen be a Vállalati portál alkalmazásba a munkahelyi vagy az iskolai e-mail címének és jelszavának használatával, majd koppintson a **Bejelentkezés** elemre.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  A **Vállalati hozzáférés beállítása** képernyőn koppintson a **KEZDÉS** gombra.

    ![A vállalati hozzáférés beállítási képernyője](./media/and-enroll-4a-comp-access-setup.png)

7.  A **Miért érdemes regisztrálnia az eszközét?** képernyőn olvassa el, mi mindent tesz lehetővé az eszköz regisztrálása, majd koppintson a **FOLYTATÁS** gombra.

    ![A „Miért érdemes regisztrálni az eszközt?” képernyője](./media/and-enroll-4b-why-enroll.png)

8.  Tekintse át a listában, hogy a rendszergazda milyen tartalmakhoz férhet hozzá az eszközén, majd koppintson a **FOLYTATÁS** gombra.

    ![Adatvédelmi beállítások](./media/and-enroll-4c-we-care-privacy.png)

9.  A **What comes next** (Mi a következő lépés?) képernyőn olvassa el, mi történik a regisztráció során, majd koppintson a **REGISZTRÁCIÓ** elemre.

    ![A „Mi a következő lépés?” képernyő](./media/and-enroll-4d-what-comes-next.png)

10.  Ha az Android 6.0-s vagy újabb verzióját használja, végezze el ezt a lépést. Egyéb esetben lépjen a következő lépésre.

    Ha a rendszergazda létrehozott bizonyos szabályzatokat, akkor előfordulhat, hogy megjelennek az alábbi üzenetek:
    -    **Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)**

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert **a Microsoft soha nem indít telefonhívásokat, és nem is kezeli az Ön hívásait**! A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. A hozzáférés engedélyezésekor csupán annyi történik, hogy engedélyezi az eszköz számára az eszköz nemzetközi mobilkészülék-azonosító (IMEI) számának elküldését az Intune-nak. A sorozatszámhoz hasonló IMEI szám a mobileszköz egyedi azonosítója.

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb bejelentkezik a Vállalati portálba, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket. Amennyiben később ismét engedélyezni szeretné a hozzáférést, a **Beállítások** &gt; ** **Alkalmazások&gt; **Vállalati portál** &gt; **Engedélyek** &gt; **Telefon** lapon teheti ezt meg.

    -    **Allow Company Portal to access your contacts? (Engedélyezi, hogy a Munkahelyi portál hozzáférjen a névjegyekhez?)**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert **a Microsoft soha nem fér hozzá a névjegyekhez.** A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. Ha engedélyezi a hozzáférést, lehetővé teszi a Vállalati portál alkalmazásnak munkahelyi fiók létrehozását, használatát és kezelését.

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb bejelentkezik a Vállalati portálba, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket. Amennyiben később ismét engedélyezni szeretné a hozzáférést, a **Beállítások** &gt; ** **Alkalmazások&gt; **Vállalati portál** &gt; **Engedélyek** &gt; **Telefon** lapon teheti ezt meg.

11.  Az **Activate device administrator** (Eszközadminisztrátor aktiválása) képernyőn koppintson az **Aktiválás** elemre.

    ![Az „Eszközadminisztrátor aktiválása” képernyő](./media/and-enroll-5-activate.png)

12.  Az útmutatást követve írja be a PIN-kódját vagy a jelszavát. Ha korábban már beállított egy PIN-kódot vagy egy jelszót a szóban forgó eszközön, ez a képernyő nem jelenik meg, és új PIN-kódot vagy jelszót sem kell megadnia.

    ![Adjon meg PIN-kódot vagy jelszót](./media/and-enroll-6-PIN-native.png)

13.  Ha Samsung Knox-eszközt használ, koppintson a **Megerősítés** elemre. Ekkor megjelenik egy üzenet, hogy az eszköz regisztrálása folyamatban van. Ha natív Android-eszközt használ, akkor csak egy üzenet jelenik meg arról, hogy az eszköz regisztrálása folyamatban van, ahogy az alábbi képernyőképen látható.

    ![Samsung KNOX adatvédelmi szabályzat](./media/and-enroll-7-knox-privacy-policy.png)

    Ezen a képernyőképen az látható, hogy az eszköz regisztrálása folyamatban van.

    ![„Eszköz regisztrálása” képernyő](./media/and-enroll-8-device-enrolling.png)

14. Amikor megjelenik a **Vállalati hozzáférés beállítása** képernyő, koppintson a **FOLYTATÁS** elemre. Ha megjelenik egy üzent arról, hogy az eszköz nem megfelelő, kövesse az utasításokat a probléma megoldásához, majd koppintson a **FOLYTATÁS** elemre.

    ![A vállalati hozzáférés beállítási képernyője](./media/and-enroll-9-comp-access-setup.png)  

11. A **Vállalati hozzáférés beállítása befejeződött** képernyőn koppintson a **KÉSZ** elemre. Ezzel megtörtént az eszköz regisztrálása.

    ![„A vállalati hozzáférés beállítása befejeződött” képernyő](./media/and-enroll-10-comp-access-setup-complete.png)

Mielőtt vállalati alkalmazások telepítésével próbálkozna, a **Beállítások** &gt; **Biztonság** területen kapcsolja be az **Ismeretlen források** beállítást. Ha az alkalmazások telepítésének megkísérlése előtt nem kapcsolja be ezt a beállítást, a következő üzenet jelenik meg: „A telepítés letiltva. Biztonsági okokból az eszköz blokkolja az ismeretlen forrásból származó alkalmazások telepítését.” A hiba-párbeszédpanelen található **Beállítások** elemre koppintva könnyen az **Ismeretlen források** beállításhoz ugorhat.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Vállalati portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a Microsoft Android-csapatának a wintunedroidfbk@microsoft.com címre.



<!--HONumber=Feb17_HO2-->



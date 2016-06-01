---
# required metadata

title: Android-eszköz regisztrálása az Intune-ban | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Android-eszköz regisztrálása az Intune-ban

Ha munkahelye vagy iskolája a Microsoft Intune-t használja, Android-eszközének regisztrálásával hozzáférhet a vállalati levelezéséhez, fájljaihoz és egyéb vállalati forrásokhoz. Az eszközök regisztrálása lehetővé teszi az IT-részleg számára ezen munkahelyi vagy iskolai erőforrások kezelését és védelmét, miközben Ön a kívánt eszközön végezheti feladatait. További információk a regisztrációval kapcsolatban: [Mi történik a Vállalati portál alkalmazás telepítésekor és az eszköz regisztrálásakor?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md),.

Ezek a regisztrálási útmutatók a Samsung Knox Android-eszközökre és a „natív” (nem Samsung Knox) Android-eszközökre vonatkoznak. A **Settings** (Beállítások) &gt; **About phone** (Az eszköz névjegye) területen megállapíthatja, hogy Samsung Knox eszközzel rendelkezik-e. Ha nem jelenik meg a „Knox” szó, akkor natív Android-eszközzel rendelkezik.

A regisztráció előtt vagy után a rendszer megkérheti, hogy válasszon ki egy olyan kategóriát, amely a leginkább illik az Ön eszközhasználatára. A rendszergazda a kategória alapján dönti el, hogy milyen alkalmazásokhoz kaphat hozzáférést.

Ha hibaüzenet jelenik meg az eszköz Intune-regisztrálása közben, akkor a [regisztrálási hibák elküldhetők a rendszergazdának](send-enrollment-errors-to-your-it-administrator-android.md)..

**Android-eszköz regisztrálása:**

1.  Telepítse az Intune Vállalati portál nevű ingyenes alkalmazást a [Google Play áruházból](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)..

2.  Nyissa meg a Microsoft Intune Vállalati portál alkalmazást.

3.  A Vállalati portál alkalmazás **üdvözlőképernyőjén** koppintson a **Bejelentkezés** elemre, és jelentkezzen be a munkahelyi vagy az iskolai fiókjával.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Ha a rendszergazda kikötéseket és feltételeket írt elő a munkahely erőforrásainak használatához, az **ELFOGADÁS** gombra koppintva fogadja el azokat.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Ha az Android 6.0-s vagy újabb verzióját használja, végezze el ezt a lépést. Egyéb esetben lépjen a következő lépésre. 

    Ha a rendszergazda létrehozott bizonyos szabályzatokat, akkor előfordulhat, hogy megjelennek az alábbi üzenetek:
    -   **Allow Company Portal to make and manage phone calls? (Engedélyezi, hogy a Munkahelyi portál alkalmazás telefonhívásokat indítson és kezeljen?)**

    ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert a **Microsoft soha nem indít telefonhívásokat, és nem is kezeli az Ön hívásait.** A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. Amikor engedélyezi a hozzáférést, csak azt engedélyezi, hogy az eszköz adatnaplókat írjon az eszköz SD-kártyájára, miáltal USB-kábelen keresztül áthelyezhetők lesznek a naplók. Erre a képességre szüksége lehet, hogy elküldhesse a naplókat a rendszergazdának, ha a vállalati portál alkalmazás használata során problémába ütközik. Ismertető: [Regisztrálási hibák elküldése a rendszergazdának](send-enrollment-errors-to-your-it-administrator-android.md).

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb bejelentkezik a Vállalati portálba, de a **Never ask again** (Ne kérdezzen rá ismét) jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket.  Ha később úgy dönt, hogy engedélyezi a hozzáférést, lépjen a **Settings** (Beállítások) &gt; **Apps** (Alkalmazások) &gt; **Company Portal** (Vállalati portál) &gt; **Permissions** (Engedélyek) &gt; **Phone** (Eszköz) menüpontra, majd kapcsolja be az engedélyezést.

    -   **Engedélyezi, hogy a Vállalati Portál hozzáférjen a névjegyekhez?**

    ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    Ha ez az üzenet jelenik meg, koppintson az **ENGEDÉLYEZÉS** elemre. Nyugodtan rákoppinthat az ENGEDÉLYEZÉS elemre, mert a **Microsoft soha nem éri el a névjegyeket.** A Google szabályozza az üzenet szövegét, és a Microsoft nem módosíthatja azt. Ha engedélyezi a hozzáférést, az a Vállalati Portál számára csak az adatnaplók elérését teszi lehetővé, ami segíthet az eszközzel kapcsolatos problémák elhárításában.

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb az **Adatok küldése** elemre koppint, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket. Ha később úgy dönt, hogy engedélyezi a hozzáférést, lépjen a **Settings** (Beállítások) &gt; **Apps** (Alkalmazások) &gt; **Company Portal** (Vállalati portál) &gt; **Permissions** (Engedélyek) &gt; **Storage** (Tárhely) menüpontra, majd kapcsolja be az engedélyezést.

6.  Jelentkezzen be a Vállalati portál alkalmazásba a munkahelyi vagy az iskolai e-mail címének és jelszavának használatával, majd koppintson a **Bejelentkezés** elemre..

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

7.  A **Vállalati hozzáférés beállítása** képernyőn koppintson a **KEZDÉS** gombra..

    ![A vállalati hozzáférés beállítási képernyője](./media/and-enroll-4a-comp-access-setup.png)

8.  A **Miért érdemes regisztrálni az eszközt?** képernyőn olvassa el, mi mindent tesz lehetővé az eszköz regisztrálása, majd koppintson a **FOLYTATÁS** gombra..

    ![A „Miért érdemes regisztrálni az eszközt?” képernyője](./media/and-enroll-4b-why-enroll.png)

9.  Tekintse át a listában, hogy a rendszergazda milyen tartalmakhoz férhet hozzá az eszközén, majd koppintson a **FOLYTATÁS** gombra..

    ![Adatvédelmi beállítások](./media/and-enroll-4c-we-care-privacy.png)

10.  A **What comes next** (Mi a következő lépés?) képernyőn olvassa el, mi történik a regisztráció során, majd koppintson a **REGISZTRÁCIÓ** elemre..

    ![A „Mi a következő lépés?” képernyő](./media/and-enroll-4d-what-comes-next.png)

11.  Az **Activate device administrator** (Eszközadminisztrátor aktiválása) képernyőn koppintson az **Activate** (Aktiválás) elemre..

    ![Az „Eszközadminisztrátor aktiválása” képernyő](./media/and-enroll-5-activate.png)

12.  Az útmutatást követve írja be a PIN-kódját vagy a jelszavát. Ha korábban már beállított egy PIN-kódot vagy egy jelszót a szóban forgó eszközön, ez a képernyő nem jelenik meg, és új PIN-kódot vagy jelszót sem kell megadnia.

    ![Adjon meg PIN-kódot vagy jelszót](./media/and-enroll-6-PIN-native.png)

13.  Kövesse az alábbiakban azokat az utasításokat, amelyek megfelelnek az Ön által használt eszköznek (natív Android vagy Samsung Knox). A **Settings** (Beállítások) &gt; **About phone** (Az eszköz névjegye) területen megállapíthatja, hogy Samsung Knox eszközzel rendelkezik-e. Ha nem jelenik meg a „Knox” szó, akkor natív Android-eszközzel rendelkezik.

    -   Natív (nem Samsung Knox típusú) eszköz: Az alapértelmezett tanúsítvány elfogadásához **A tanúsítvány elnevezése** képernyőn koppintson az **OK** gombra.

    ![„A tanúsítvány elnevezése” képernyő](./media/and-enroll-7-cert-native.png)

    -   Samsung Knox eszköz: Fogadja el az adatvédelmi szabályzatot, majd koppintson a **JÓVÁHAGYÁS** elemre..

    ![Samsung KNOX adatvédelmi szabályzat](./media/and-enroll-7-knox-privacy-policy.png)

    Amint az Intune regisztrálja az eszközt, a képernyőn a következő üzenet jelenik meg.

    ![„Eszköz regisztrálása” képernyő](./media/and-enroll-8-device-enrolling.png)

14. Amikor megjelenik a **Vállalati hozzáférés beállítása** képernyő, koppintson a **FOLYTATÁS** elemre. Ha megjelenik egy üzent arról, hogy az eszköz nem megfelelő, kövesse az utasításokat a probléma megoldásához, majd koppintson a **FOLYTATÁS** elemre..

    ![A vállalati hozzáférés beállítási képernyője](./media/and-enroll-9-comp-access-setup.png)  

11. A **Vállalati hozzáférés beállítása befejeződött** képernyőn koppintson a **KÉSZ** elemre. Ezzel megtörtént az eszköz regisztrálása.

    ![„A vállalati hozzáférés beállítása befejeződött” képernyő](./media/and-enroll-10-comp-access-setup-complete.png)

Mielőtt vállalati alkalmazások telepítésével próbálkozna, a **Beállítások**  &gt; **Biztonság** területen kapcsolja be az **Ismeretlen források** beállítást. Ha az alkalmazások telepítésének megkísérlése előtt nem kapcsolja be ezt a beállítást, a következő üzenet jelenik meg: „A telepítés letiltva”. Biztonsági okokból a telefon blokkolja az ismeretlen forrásból származó alkalmazások telepítését.” A hiba-párbeszédpanelen található **Beállítások** elemre koppintva könnyen az **Ismeretlen források** beállításhoz ugorhat.


### További információ
[Android-eszköz használata az Intune-nal](using-your-android-device-with-intune.md)


<!--HONumber=May16_HO1-->



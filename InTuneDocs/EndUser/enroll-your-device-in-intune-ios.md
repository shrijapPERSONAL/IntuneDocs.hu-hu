---
title: "iOS-eszköz regisztrálása az Intune-ban | Microsoft Docs"
description: "Egy iOS-eszköz regisztrálását mutatja be az Intune-ban"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 9530eb45bf027c66c4a36e4cea1ec05c5f15a6e5
ms.openlocfilehash: c7fa06ea443523c51a79c33af7e8094d7a7777c5


---


# <a name="enroll-your-ios-device-in-intune"></a>iOS-eszköz regisztrálása az Intune-ban

Ha munkahelye vagy iskolája a Microsoft Intune-t használja, iOS-eszközének regisztrálásával hozzáférhet a vállalati levelezéséhez, fájljaihoz és egyéb vállalati forrásokhoz. Az eszközök regisztrálása lehetővé teszi az informatikai osztály számára ezeknek a munkahelyi vagy iskolai erőforrásoknak a kezelését és védelmét, miközben Ön a kívánt eszközön végezheti a feladatait. További információk a regisztrációval kapcsolatban: [Mi történik a Vállalati portál alkalmazás telepítésekor és az eszköz Intune-beli regisztrálásakor?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

> [!NOTE]
> Ha valójában egy macOS-eszközt (például MacBook Pro-t vagy iMac-et) szeretne regisztrálni, [ezt az útmutatást kövesse](enroll-your-device-in-intune-macos.md).

**Előkészületek:**

- Miután elkezdte, ne hagyja félbe a regisztrációt. Ha elkezdi, de nem fejezi be, előfordulhat, hogy nem tud majd regisztrálni, ha később újra próbálkozik.
- Győződjön meg róla, hogy működik a Wi-Fi. Ellenkező esetben a regisztráció sikertelen lesz.
- Ha az eszközön letiltotta a Safari böngészőt, oldja fel a tiltást. A regisztrációhoz mindenképpen a Safarit kell használnia.


**iOS-eszköz regisztrálása:**

1.  Végezze el [Az Intune Vállalati portál alkalmazásának telepítése, majd bejelentkezés a portálra](install-and-sign-in-to-the-intune-company-portal-app-ios.md) című részben ismertetett lépéseket.

2. A **Vállalati hozzáférés beállítása** lapon koppintson a **Kezdés** elemre.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. A **Miért érdemes regisztrálnia az eszközét?** képernyőn olvassa el, mi mindent tesz lehetővé az eszköz regisztrálása, majd koppintson a **Folytatás** elemre.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

4. Tekintse át a listában, hogy a rendszergazda milyen tartalmakhoz férhet/nem férhet hozzá a regisztrált eszközén, majd koppintson a **Folytatás** gombra.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  A **Mi a következő lépés?** képernyőn olvassa el, mi történik a regisztráció során, majd koppintson a **Regisztráció** elemre.

     ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  A **Profil telepítése** képernyőn koppintson a **Telepítés** elemre, és ha az alkalmazás kéri, írja be a PIN-kódját.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  Koppintson a **Telepítés** elemre.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  A **Telepítés** elemre koppintva jelezze, hogy elolvasta a figyelmeztetést.

       ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  Koppintson a **Megbízhatóság** elemre.

       ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Amikor a rendszer a profil telepítésének befejezését jelző képernyőre vált, koppintson a **Kész** elemre.

     ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    A képernyőn megjelenik az „Eszköz regisztrálása” üzenet.

11.  Amikor egy üzenet arra kéri, hogy nyissa meg az oldalt a Vállalati portálon, koppintson a **Megnyitás** elemre.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. A **Vállalati hozzáférés beállítása** képernyőn koppintson a **Folytatás** elemre. Ha a rendszergazda további biztonsági követelményeket (például a jelszó beállításának szükségességét) állított be, kövesse a képernyőn megjelenő utasításokat, amíg ki nem elégíti az összes megfelelőségi követelményt. Ekkor a rendszer visszalépteti a Vállalati hozzáférés beállítása képernyőre. Itt koppintson a **Folytatás** elemre.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. Koppintson a **Kész** gombra.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Ezzel megtörtént az eszköz Intune-beli regisztrálása, és a rendszer visszalépteti a Vállalati portál alkalmazásba.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Feb17_HO2-->



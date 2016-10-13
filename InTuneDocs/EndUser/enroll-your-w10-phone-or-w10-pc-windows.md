---
title: "Windows 10 rendszerű eszköz regisztrálása az Intune-ban | Microsoft Intune"
description: "Egy Windows 10 Mobile-eszköz vagy Windows 10 asztali eszköz regisztrálását mutatja be az Intune-ban"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e0321b23bbbaaa16c28c23e56b5fbcaee0d3c24
ms.openlocfilehash: 75f19a1c613b2d018e0cb89862f15aa4be2bc138


---


# Windows 10 Mobile-eszköz vagy Windows 10 asztali eszköz regisztrálása az Intune-ban

Ha munkahelye vagy iskolája a Microsoft Intune-t használja, eszközének regisztrálásával hozzáférhet a vállalati levelezéséhez, fájljaihoz és egyéb vállalati erőforrásaihoz. Az eszközök regisztrálása lehetővé teszi munkahelye számára, hogy megóvhassa a vállalati adatokat. További információk a regisztrációval kapcsolatban: [Mi történik a Vállalati portál alkalmazás telepítésekor és az eszköz Intune-beli regisztrálásakor?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md), illetve [Mit láthat a rendszergazda az eszközén, és mit nem?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) témakörben.


Windows 10 Mobile-eszköz vagy Windows 10 asztali eszköz regisztrálása:

1.  Válassza a Windows **Gépház** területét, majd koppintson a **Fiókok** elemre.

    ![Windows Gépház](./media/w10-enroll-rs1-settings-accounts.png)

2.  A következő két képernyő közül válassza ki azt, amelyen ugyanaz látszik, mint az eszközön. Hajtsa végre a kiválasztott képernyőhöz tartozó lépéseket.

    Ha ezt a képernyőt látja, hajtsa végre a [Teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](#steps-to-follow-if-you-see-access-work-or-school) című részben leírt lépéseket.

    ![Csatlakozás munkahelyi vagy iskolai rendszerhez](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Ha ezt a képernyőt látja, hajtsa végre a [Teendők, ha ezt látja: Saját fiók](#steps-to-follow-if-you-see-your-account) részben leírt lépéseket.

    ![Saját fiók](./media/w10-enroll-2-accounts-your-account.png)

## Teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez

1.  Koppintson a **Hozzáférés munkahelyi vagy iskolai rendszerhez** lehetőségre, majd a **Kapcsolódás** elemre.

    ![Koppintson a Hozzáférés munkahelyi vagy iskolai fiókhoz lehetőségre](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Adja meg a munkahelyi vagy iskolai e-mail címét és koppintson a **Tovább** elemre.

    ![Adja meg a munkahelyi vagy iskolai fiókját](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Jelentkezzen be az Intune-ba munkahelyi vagy iskolai fiókjával.

    ![Munkahelyi vagy iskolai fiók beállítása](./media/w10-enroll-rs1-enter-your-credentials.png)

    Ekkor megjelenik egy üzenet arról, hogy a munkahely vagy iskola regisztrálja az eszközt.

4. Amikor megjelenik a **Készen vagyunk!** képernyő, koppintson a **Bezárás** elemre. Ezzel készen is van.

  ![Koppintson a bezárás elemre a „Készen vagyunk!” képernyőn](./media/w10-enroll-rs1-youre-all-set.png)

5. Ha szeretné még egyszer ellenőrizni, hogy a kapcsolat megfelelően működik-e, lépjen vissza a **Gépház** területre, ahol most már meg kell jelennie a listán a munkahelyi vagy iskolai fiókjának.

    ![A kapcsolat megfelelő beállításának ellenőrzése](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Ha követte a fenti lépéseket, de továbbra sem tud hozzáférni munkahelyi vagy iskolai e-mail fiókjához és fájljaihoz, kövesse a [Hibaelhárítási teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) című részben leírt lépéseket.


## Teendők, ha ezt látja: Saját fiók

1.  Válassza a Windows **Gépház** területét, majd koppintson a **Fiókok** elemre.

    ![Lépjen be a Beállítások és fiókok munkaterületre](./media/W10-enroll-1-settings-accounts.png)

2.  Koppintson a **Saját fiók** elemre.

    ![Koppintson a Saját fiók elemre](./media/W10-enroll-2-accounts-your-account.png)

3.  Koppintson a **Munkahelyi vagy iskolai fiók beállítása** pontra.

    ![Koppintson a Munkahelyi vagy iskolai fiók beállítása pontra](./media/w10-enroll-3-add-work-school-acct.png)

4.  Jelentkezzen be a munkahelyi vagy iskolai fiókjával.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Ha követte a fenti lépéseket, de továbbra sem tud hozzáférni munkahelyi vagy iskolai e-mail címéhez, fájljaihoz és egyéb adataihoz, kövesse a [Hibaelhárítási teendők, ha ezt látja: Saját fiók](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) című részben leírt utasításokat.

Azt javasoljuk, hogy telepítse a Vállalati portál alkalmazást, mert azzal egyszerűen megismerheti és letöltheti az Ön és munkaköre szempontjából fontos vállalati alkalmazásokat. Attól függően, hogy a vállalat hogyan konfigurálta az Intune-t, előfordulhat, hogy a Vállalati portál alkalmazás már a regisztrációs folyamat részeként települt.

Ha az alkalmazáslistában szerepel a **Vállalati portál**, akkor már rendelkezik az alkalmazással. Ha a vállalati portál nem jelenik meg az alkalmazáslistán, akkor a következő lépésekkel telepítheti.

1.  Koppintson a **Start** &gt; **Áruház** parancsra.

2.  Koppintson a **Keresés** elemre, majd írja be a **vállalati portál** kifejezést.

3.  Az eredmények listájában koppintson a **Vállalati portál** &gt; **Telepítés** lehetőségre.

4.  Koppintson a **Telepítés** vagy az **Ingyenes** lehetőségre. Attól függ, hogy melyik beállítás jelenik meg, hogy a vállalat hogyan konfigurálta az alkalmazást.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).





<!--HONumber=Oct16_HO1-->



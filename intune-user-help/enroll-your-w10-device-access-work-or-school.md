---
title: Windows 10 rendszerű eszköz regisztrálása az Intune-ban | Microsoft Docs
description: 1607-es vagy újabb verziójú Windows 10 rendszerű eszköz regisztrációja az Intune-ban
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 21332f5441d6b2318a8739feb0457021cb7e442b
ms.sourcegitcommit: 8117444cfdddf6d9bdbc4ac715af8d88e72f411d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48260217"
---
# <a name="enroll-your-windows-10-device-in-intune"></a>Windows 10 rendszerű eszköz regisztrálása az Intune-ban

> [!NOTE]
> A Windows 10 az összes eszköztípuson működik. Akár asztali gépet, akár telefont vagy táblagépet használ, a lépések ugyanazok lesznek – még ha némileg eltérnek is az itt látható képektől.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]

1. Lépjen a **Start** menüre.

   - Ha **Windows 10 rendszerű asztali** eszközt használ, lépjen a **Start** menüre.
   - Ha **Windows 10 Mobile** rendszerű eszközt használ, nyissa meg a **kezdőképernyőt**, és pöccintsen a **Minden alkalmazás** listára.

2. A keresősávban keressen a „beállítások” kifejezésre, majd nyissa meg a Windows **Beállítások** alkalmazását.

3. Válassza a **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** > **Csatlakozás** elemet.

    ![Válassza a Hozzáférés munkahelyi vagy iskolai fiókhoz lehetőséget](./media/w10-enroll-rs1-connect-to-work-or-school.png)

4. Adja meg a munkahelyi vagy iskolai e-mail-címét, és válassza a **Tovább** elemet.

   ![Adja meg a munkahelyi vagy iskolai fiókját](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

5. Jelentkezzen be az Intune-ba munkahelyi vagy iskolai fiókjával.

    ![Munkahelyi vagy iskolai fiók beállítása](./media/w10-enroll-rs1-enter-your-credentials.png)

    Ekkor megjelenik egy üzenet arról, hogy a munkahely vagy iskola regisztrálja az eszközt.

6. Amikor megjelenik a **Készen vagyunk!** képernyő, válassza a **Bezárás** elemet. Ezzel készen is van.

   ![Válassza a Bezárás elemet a „Készen vagyunk!” képernyőn](./media/w10-enroll-rs1-youre-all-set.png)

7. Ha szeretné még egyszer ellenőrizni, hogy a kapcsolat megfelelően működik-e, lépjen vissza a **Gépház** területre, ahol most már meg kell jelennie a listán a munkahelyi vagy iskolai fiókjának.

    ![A kapcsolat megfelelő beállításának ellenőrzése](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Ha követte a fenti lépéseket, de továbbra sem tud hozzáférni munkahelyi vagy iskolai e-mail fiókjához és fájljaihoz, kövesse a [Hibaelhárítási teendők, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) című részben leírt lépéseket.

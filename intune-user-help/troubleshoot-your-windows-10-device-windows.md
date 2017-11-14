---
title: "Windows 10-es eszközök regisztrálásával kapcsolatos problémák elhárítása | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 651df0e6ba3f8b3b2727d3194c8bf5e1a40cffc3
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2017
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a>Windows 10-es eszközök regisztrálásával kapcsolatos problémák elhárítása
Ha végrehajtotta a [Windows 10 Mobile-eszköz vagy Windows 10 asztali eszköz regisztrálása az Intune-ban](enroll-your-w10-phone-or-w10-pc-windows.md) című témakörben leírt lépéseket, de mégsem tudja elérni munkahelyi vagy iskolai levelezését vagy fájljait, próbálkozzon a következő hibaelhárítási lépésekkel.

1.  A következő két képernyő közül válassza ki azt, amelyen ugyanaz látszik, mint az eszközön. Hajtsa végre a kiválasztott képernyőhöz tartozó lépéseket.

    Ha ezt a képernyőt látja, hajtsa végre a [Hibaelhárítási lépések, ha ezt látja: Hozzáférés munkahelyi vagy iskolai rendszerhez](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) című részben leírt lépéseket.

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Ha ezt a képernyőt látja, hajtsa végre a [Hibaelhárítási lépések, ha ezt látja: Saját fiók](#troubleshooting-steps-to-follow-if-you-see-your-account) című részben leírt lépéseket.

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a>Hibaelhárítási lépések, ha ezt látja: „Hozzáférés munkahelyi vagy iskolai rendszerhez”

1.  Ha követte a fenti lépéseket, de továbbra sem tud hozzáférni munkahelyi vagy iskolai e-mailjeihez és fájljaihoz, lépjen vissza a **Hozzáférés munkahelyi vagy iskolai rendszerhez** lapra.

2. Tegye a következők valamelyikét:

    - Ha olyan kapcsolatot lát, amely hasonlít az alábbi képen láthatóhoz, koppintson rá, és ellenőrizze, hogy megjelenik-e a Kezelés, az Információ és a Leválasztás lehetőség. Ha látja ezeket a lehetőségeket, akkor sikeresen regisztrált és csatlakoztatva van.

    ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

    - Ha nem látja a fenti csatlakozási információkat, vagy az opciók egy része nem jelenik meg, kattintson a **Csatlakozás** elemre, majd jelentkezzen be munkahelyi vagy iskolai hitelesítő adataival. Ezzel létrejön a kapcsolat.

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a>Hibaelhárítási lépések, ha ezt látja: „Saját fiók”

Ha követte a fenti lépéseket, de továbbra sem tud hozzáférni munkahelyi vagy iskolai e-mailjeihez vagy fájljaihoz, lépjen vissza a **Fiókok** lapra, és koppintson a **Munkahelyi hozzáférés** elemre.

- Ha megjelenik a munkahelyi vagy iskolai fiók, akkor minden rendben van, mert sikerült csatlakoznia.

- Ha nem látja saját munkahelyi vagy iskolai fiókját, koppintson a **Csatlakozás** elemre, majd jelentkezzen be munkahelyi vagy iskolai hitelesítő adataival.

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a>Hibaelhárítási lépések, ha ezt látja: „Munkahelyi vagy iskolai fiók beállítása”

Ha a következő üzenetet látja:  __Nem találtunk a megadott felhasználónévvel egyező felügyeleti végpontot. Ellenőrizze, hogy helyesen írta-e be a felhasználónevét, és próbálkozzon újra. Ha ismeri a felügyeleti végpontja URL-címét, írja be.__, akkor próbálja ismét beírni a felhasználónevét és a jelszavát. Ha továbbra sem működik, ellenőrizze a cég informatikai támogatási szolgáltatásánál azt a webhelyet, amelyet a **Felügyeleti végpont** szövegmezőben meg kell adnia. Ez a webhely valószínűleg a következőhöz hasonlít: **www.azöncége.onmicrosoft.com**.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com).

---
title: "A felhasználókezelés első lépései"
titlesuffix: Azure portal
description: "A felhasználók Intune-ba való felvételével engedélyezheti nekik, hogy mobileszközről is elérjék a céges erőforrásokat."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a33eb2d5dc96a2647cf2582bbc6cd4ba2d9c0961
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-managing-users"></a>A felhasználók felügyeletének első lépései

Gondolja végig, hányan dolgoznak a munkahelyén. Mindegyiküknek, aki céges adatokkal dolgozik, szüksége lesz egy felhasználói fiókra, amelynek az adatokhoz való hozzáférése felügyelhető az Intune-ban.

## <a name="how-do-i-create-a-user"></a>Felhasználó létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. A **Erőforrások keresése** használatával keressen rá az **Intune** kifejezésre.
3. Miután megnyitotta a **Microsoft Intune** panelt, válassza a **Felhasználók** lehetőséget. Nyissa meg a **Minden felhasználó** lapot, és válassza az **+ Új felhasználó** lehetőséget.
4. Adja meg az új felhasználó adatait, például **Név** és a **Felhasználónév**. A felhasználónév részét képező tartománynév csak az eredeti, alapértelmezett “contoso.onmicrosoft.com” tartománynév, vagy olyan ellenőrzött, nem összevont tartománynév lehet, amilyen a “contoso.com”.
5. A **Csoportok** részen válassza ki a tesztcsoportot, amelyhez a felhasználót hozzá kívánja adni.
6. Mentse az automatikusan generált jelszót, hogy be tudjon jelentkezni vele a teszthez használt eszközön. Ezt a jelszót meg kell adni a felhasználónak, hogy megváltoztathassák egy saját jelszóra, amelyet meg tudnak jegyezni.
7. A **Felhasználó** panelen válassza a **Létrehozás** lehetőséget.

## <a name="assigning-licenses-to-users"></a>Licencek kiosztása a felhasználók számára

Felhasználó létrehozása után az [Office 365-portál](http://go.microsoft.com/fwlink/p/?LinkId=698854) használatával kell Intune licencet rendelnie az új felhasználóhoz. Ha nem oszt ki nekik licencet, akkor nem fogják tudni felügyeletre regisztrálni eszközeiket.

1. Jelentkezzen be a [Office 365-portálra](http://go.microsoft.com/fwlink/p/?LinkId=698854) az Intune-ba való bejelentkezéshez használt hitelesítő adatokkal.
2. Válassza a **Felhasználók** > **Aktív felhasználók** menüpontot, majd a korábban létrehozott felhasználót.
3. Az összes felhasználói információ betöltődésére esetleg várnia kell valamennyi ideig. Ha betöltődött, válassza a **Szerkesztés** lehetőséget a felhasználó **terméklicenceinél**.
4. Rendeljen **Hely**et a felhasználóhoz, majd állítsa az Intune kapcsolót **be** értékre.

 > [!NOTE]
 > Ezzel elhasználja a licencei egyikét ehhez a felhasználóhoz. Ha az éles környezetben dolgozik, akkor később kikapcsolhatja a licenc használatát, hogy kiossza egy valódi felhasználónak.

5. Válassza a **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések

[A csoportok felügyeletének első lépései](get-started-groups.md) – Csoportokba rendezheti a felhasználókat, hogy könnyebben felügyelhesse az általuk elérhető szabályzatokat és alkalmazásokat.

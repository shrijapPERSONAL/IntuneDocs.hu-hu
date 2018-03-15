---
title: "A felhasználók kezelésének első lépései"
titlesuffix: Microsoft Intune
description: "Ha a felhasználókat hozzáadja az Intune-hoz és licenceket rendel hozzájuk, akkor ők is hozzáférhetnek a céges erőforrásokhoz a mobileszközükről."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e06b335c03caee0bd997748f9c48ed78d7d379b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-managing-users"></a>A felhasználók kezelésének első lépései

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

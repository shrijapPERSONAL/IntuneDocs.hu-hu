---
title: "A felhasználókezelés első lépései"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e711f32ebd77a83b17e6db468f8cb23a409c8d31
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="get-started-with-users"></a>A felhasználókezelés első lépései

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Azure Active Directory kezeli a szervezet objektumait, például eszközök és alkalmazások csoportjait, és felhasználók csoportjait is. A felhasználók vagy eszközök csoportokba sorolhatók, így nem szükséges mindegyiket egyedileg kezelni. Ezáltal az alkalmazások és beállítások egyszerűen rendelhetők hozzá egyszerre nagy számú felhasználóhoz vagy eszközhöz.

## <a name="how-do-i-create-a-user"></a>Felhasználó létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Az **Erőforrások keresése** alatt keresse meg a **Felhasználók és csoportok** elemet.
3. A **Felhasználók és csoportok** panelen válassza a **Minden felhasználó**, majd az **+ Új felhasználó** lehetőséget.
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

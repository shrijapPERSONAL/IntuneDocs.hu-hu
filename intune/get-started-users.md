---
title: A felhasználók kezelésének első lépései
titlesuffix: Microsoft Intune
description: Ha a felhasználókat hozzáadja az Intune-hoz és licenceket rendel hozzájuk, akkor ők is hozzáférhetnek a céges erőforrásokhoz a mobileszközükről.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7b584fe9d56cd02ce8ee066113c033d8b124559
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57461226"
---
# <a name="get-started-managing-users"></a>A felhasználók kezelésének első lépései

Gondolja végig, hányan dolgoznak a munkahelyén. Mindegyiküknek, aki céges adatokkal dolgozik, szüksége lesz egy felhasználói fiókra, amelynek az adatokhoz való hozzáférése felügyelhető az Intune-ban.

## <a name="how-do-i-create-a-user"></a>Felhasználó létrehozása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Miután megnyitotta a **Microsoft Intune** panelt, válassza a **Felhasználók** lehetőséget. Nyissa meg a **Minden felhasználó** lapot, és válassza az **+ Új felhasználó** lehetőséget.
4. Adja meg a felhasználó adatait (például **Név** és **Felhasználónév**). A felhasználónév tartománynév részének a következő tartományok egyikének kell lennie:
    - a kezdeti alapértelmezett tartománynév: „contoso.onmicrosoft.com” vagy
    - egy ellenőrzött, nem összevont tartománynév, például „contoso.com”.
5. A **Csoportok** szakaszban válassza ki a [csoportot](get-started-groups.md), amelyhez a felhasználót hozzá kívánja adni.
6. Mentse az automatikusan generált felhasználói jelszót, hogy be tudjon jelentkezni vele a teszthez használt eszközön. Ezt a jelszót meg kell adni a felhasználónak, hogy megváltoztathassák egy saját jelszóra, amelyet meg tudnak jegyezni.
7. A **Felhasználó** panelen válassza a **Létrehozás** lehetőséget.

## <a name="assigning-licenses-to-users"></a>Licencek kiosztása a felhasználók számára

Miután létrehozott egy felhasználó, szeretné-e használni a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) , hogy a felhasználó Intune-licenc hozzárendelése. Ha nem oszt ki nekik licencet, akkor nem fogják tudni felügyeletre regisztrálni eszközeiket.

1. Jelentkezzen be a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) bejelentkezni az Intune-hoz használt hitelesítő adatokkal együtt.
2. Válassza a **Felhasználók** > **Aktív felhasználók** menüpontot, majd a korábban létrehozott felhasználót.
3. Az összes felhasználói információ betöltődésére esetleg várnia kell valamennyi ideig. Ha betöltődött, válassza a **Szerkesztés** lehetőséget a felhasználó **terméklicenceinél**.
4. Rendeljen **Hely**et a felhasználóhoz, majd állítsa az Intune kapcsolót **be** értékre.

   > [!NOTE]
   > Ezzel elhasználja a licencei egyikét ehhez a felhasználóhoz. Ha az éles környezetben dolgozik, akkor később kikapcsolhatja a licenc használatát, hogy kiossza egy valódi felhasználónak.

5. Kattintson a **Mentés** gombra.

## <a name="next-steps"></a>További lépések

[A csoportok felügyeletének első lépései](get-started-groups.md) – Csoportokba rendezheti a felhasználókat, hogy könnyebben felügyelhesse az általuk elérhető szabályzatokat és alkalmazásokat.

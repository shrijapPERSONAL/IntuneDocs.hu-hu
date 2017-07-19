---
title: "Csoportok – első lépések"
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
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Csoportok – első lépések

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

A Microsoft Intune az Azure Active Directoryt (Azure AD) használja a [vállalati erőforrásokhoz való hozzáférés kezelésére](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Ez a hozzáférés a címtárban található szabályzatokkal vezérelhető. Ezt a hozzáférést ekkor az Intune kezeli a mobileszközöknél, ami lehetővé teszi a csoport tagjainak az erőforrások elérését.

__Hogyan hozhatok létre csoportot?__

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Az **Erőforrások keresése** alatt keresse meg a **Felhasználók és csoportok** elemet.
3. Miután megnyitotta a **Felhasználók és csoportok** panelt, válassza az **Összes csoport** lehetőséget.
4. A **Felhasználók és csoportok – Összes csoport** panelen válassza az **Új csoport** parancsot.
5. A **Csoport** panelen adja meg a csoport **Nevét** és **Leírását**.
6. Adja meg a **Tagság típusa** elemhez a **Hozzárendelt** beállítást. Ne **engedélyezze az Office-funkciókat** a tesztcsoporthoz.
7. Kattintson a **Létrehozás** gombra.

Ha sikeresen létrehozott egy csoportot, annak meg kell jelennie az **Összes csoport** listáján. Ha itt nem jelenik meg, próbáljon létrehozni egy másik csoportot.

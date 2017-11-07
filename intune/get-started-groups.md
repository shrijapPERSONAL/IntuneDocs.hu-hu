---
title: "Csoportok – első lépések"
titleSuffix: Azure portal
description: "Csoportokba rendezheti a felhasználókat, hogy könnyebben kezelhesse a szabályzatokat és az általuk elérhető alkalmazásokat."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 964732be680273c62f341086ce23f0e40d981479
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="get-started-with-groups"></a>Csoportok – első lépések

Csoportok segítéségével kezelheti a felhasználókat, és tarthatja ellenőrzés alatt, hogy a felhasználók milyen céges erőforrásokat érhetnek el. Ezek az erőforrások lehetnek a könyvtára részei, vagy lehetnek külső erőforrások, például SaaS-alkalmazások vagy SharePoint-helyek.

A Microsoft Intune az Azure Active Directoryt (Azure AD) használja a vállalati erőforrásokhoz való hozzáférés kezelésére. Ez a hozzáférés a címtárban található szabályzatokkal vezérelhető. Ezt a hozzáférést ekkor az Intune kezeli a mobileszközöknél, ami lehetővé teszi a csoport tagjainak az erőforrások elérését.

## <a name="how-do-i-create-a-group"></a>Hogyan hozhatok létre csoportot?

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. A **Erőforrások keresése** használatával keressen rá az **Intune** kifejezésre.
3. Miután megnyitotta a **Microsoft Intune** panelt, válassza a **Csoportok** lehetőséget.
4. A **Felhasználók és csoportok – Összes csoport** panelen válassza az **Új csoport** parancsot.
5. A **Csoport** panelen adja meg a csoport **Nevét** és **Leírását**.
6. Adja meg a **Tagság típusa** elemhez a **Hozzárendelt** beállítást. Ne **engedélyezze az Office-funkciókat** a tesztcsoporthoz.
7. Kattintson a **Létrehozás** gombra.

Ha sikeresen létrehozott egy csoportot, annak meg kell jelennie az **Összes csoport** listáján. Ha itt nem jelenik meg, próbáljon létrehozni egy másik csoportot.

## <a name="next-steps"></a>További lépések

[Bevezetés a szabályzatok használatába](get-started-policies.md) – Szabályzatok létrehozásával megakadályozhatja a felhasználókat abban, hogy olyan dolgokat hajtsanak végre az eszközeikkel, amelyekre nincs felhatalmazásuk.

## <a name="learn-more"></a>További információ

* [Regisztrációs korlátozások beállítása csoportok használatával az Intune-ban](groups-add.md)
* [A céges erőforrások elérésének kezelése az Azure Active Directory csoportjainak használatával](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)

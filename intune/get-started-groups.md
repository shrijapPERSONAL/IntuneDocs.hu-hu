---
title: Csoport létrehozása a Microsoft Intune-ban
titleSuffix: ''
description: Csoportokba rendezheti a felhasználókat, hogy könnyebben kezelhesse a szabályzatokat és az általuk elérhető alkalmazásokat.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b7e187bb182db0491e055ce3af3833d82e578de
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842405"
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Csoport létrehozása a felhasználók és az adathozzáférés kezeléséhez

Csoportokkal kezelheti a felhasználókat, és ellenőrzés alatt tarthatja, hogy a felhasználók milyen céges erőforrásokat érhetnek el. Ezek az erőforrások lehetnek a könyvtára részei, vagy lehetnek külső erőforrások, például SaaS-alkalmazások vagy SharePoint-helyek.

A Microsoft Intune az Azure Active Directoryt (Azure AD) használja a vállalati erőforrásokhoz való hozzáférés kezelésére. Ez a hozzáférés a címtárban található szabályzatokkal vezérelhető. Ezt a hozzáférést ekkor az Intune kezeli a mobileszközöknél, ami lehetővé teszi a csoport tagjainak az erőforrások elérését.

## <a name="how-do-i-create-a-group"></a>Hogyan hozhatok létre csoportot?

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Miután megnyitotta a **Microsoft Intune** panelt, válassza a **Csoportok** lehetőséget.
4. A **Felhasználók és csoportok – Összes csoport** panelen válassza az **Új csoport** parancsot.
5. A **Csoport** panelen válassza a **Csoport típusa** lehetőséget.
5. Töltse ki a csoporthoz a **Név** és a **Leírás** mezőt.
6. Adja meg a **Tagság típusa** elemhez a **Hozzárendelt** beállítást. Ne **engedélyezze az Office-funkciókat** a tesztcsoporthoz.
7. Adja meg a csoport tagjait a **Tagok** lehetőség választásával.
7. Kattintson a **Create** (Létrehozás) gombra.

Ha sikeresen létrehozott egy csoportot, annak meg kell jelennie az **Összes csoport** listáján. Ha itt nem jelenik meg, próbáljon létrehozni egy másik csoportot.

## <a name="next-steps"></a>További lépések

[Bevezetés a szabályzatok használatába](get-started-policies.md) – Szabályzatok létrehozásával megakadályozhatja a felhasználókat abban, hogy olyan dolgokat hajtsanak végre az eszközeikkel, amelyekre nincs felhatalmazásuk.

## <a name="learn-more"></a>További információ

* [Regisztrációs korlátozások beállítása csoportok használatával az Intune-ban](groups-add.md)
* [A céges erőforrások elérésének kezelése az Azure Active Directory csoportjainak használatával](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)

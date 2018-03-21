---
title: "Csoportok hozzáadása a felhasználók és eszközök rendszerezéséhez"
titlesuffix: Microsoft Intune
description: "Csoportokat adhat hozzá azzal a céllal, hogy a felhasználókat és az eszközöket földrajzi hely, részleg vagy hardvertulajdonságok alapján rendszerezhesse."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7d2b551832d8d0e467d079df673954318623e4c
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Csoportok hozzáadása a felhasználók és eszközök rendszerezéséhez
Az Intune Azure Active Directory- (AD-) csoportokat használ az eszközök és felhasználók kezelésére. Intune-rendszergazdaként csoportokat állíthat be a vállalat igényeinek megfelelően. Létrehozhat csoportokat a felhasználók és eszközök földrajzi hely, részleg vagy hardverjellemzők szerinti rendezéséhez. Használjon csoportokat a feladatok nagy számban való végrehajtásához. Beállíthat például szabályzatokat számos felhasználóhoz, vagy üzembe helyezhet alkalmazásokat eszközök egy csoportján.

Ez a témakör elmagyarázza, hogyan vehet fel csoportokat az Intune-ban való használatra.

A következő típusú csoportokat veheti fel:
- **Hozzárendelt csoportok** – Felhasználók vagy eszközök manuális hozzáadása egy statikus csoporthoz
- **Dinamikus csoportok** – (Az Azure Active Directory Premium használatánál) Lehetővé teszi egyszerű vagy speciális szabályokkal meghatározott felhasználói vagy eszközcsoportok dinamikus felépítését

## <a name="add-a-new-group"></a>Új csoport felvétele

Új csoport létrehozásához használja a következő lépéseket.
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Csoportok** lehetőséget, majd válassza az **Összes csoport** panelen az **Új csoport** lehetőséget.
  ![Az Azure Portal képernyőképe a kijelölt Új csoport lehetőséggel](./media/groups-add-new.png)
2. Töltse ki az új csoporthoz a **Csoport típusa** a **Név** és a **Leírás** mezőt. Ezek a tulajdonságok csak a felügyeleti portálon jelennek meg, és a felhasználók nem láthatják.

3. Válassza a **Tagságtípus**:
  - **Hozzárendelt** lehetőséget manuálisan hozzárendelt tagokkal rendelkező csoport létrehozásához. További tudnivalók az [Azure AD hozzárendelt csoportjairól](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dinamikus felhasználó** **Dinamikus lekérdezéssel** meghatározott felhasználói csoport létrehozásához.
  - **Dinamikus eszköz** **Dinamikus lekérdezéssel** meghatározott eszközcsoport létrehozásához.

  ![Az Intune-csoporttulajdonságok képernyőképe](./media/groups-add-properties.png)

  Az Azure AD lehetővé teszi dinamikus csoportok létrehozását a tagságot meghatározó szabályok alapján. Az [attribútumalapú dinamikus csoportok létrehozásának](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) elsajátítása.

4. Kiválaszthatja az **Engedélyezi az Office-funkciókat** lehetőséget, hogy a felhasználói csoport tagjai elérhessék a megosztott Office 365-alkalmazásokat. További információk az [Office 365-csoportokról](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Az új csoport hozzáadásához válassza a **Létrehozás** lehetőséget.

## <a name="see-also"></a>Lásd még:
- [Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md)

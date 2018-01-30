---
title: "Regisztrációs korlátozások beállítása az Intune-ban"
titlesuffix: Azure portal
description: "Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. \""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e55a96ee1bee5b1f25a4ddf3366f3e7dc94122a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="add-groups-in-intune"></a>Csoportok felvétele az Intune-ban
Az Intune Azure Active Directory- (AD-) csoportokat használ az eszközök és felhasználók kezelésére. Intune-rendszergazdaként csoportokat állíthat be a vállalat igényeinek megfelelően. Létrehozhat csoportokat a felhasználók és eszközök földrajzi hely, részleg vagy hardverjellemzők szerinti rendezéséhez. Használjon csoportokat a feladatok nagy számban való végrehajtásához. Beállíthat például szabályzatokat számos felhasználóhoz, vagy üzembe helyezhet alkalmazásokat eszközök egy csoportján.

Ez a témakör elmagyarázza, hogyan vehet fel csoportokat az Intune-ban való használatra.

A következő típusú csoportokat veheti fel:
- **Hozzárendelt csoportok** – Felhasználók vagy eszközök manuális hozzáadása egy statikus csoporthoz
- **Dinamikus csoportok** – (Az Azure Active Directory Premium használatánál) Lehetővé teszi egyszerű vagy speciális szabályokkal meghatározott felhasználói vagy eszközcsoportok dinamikus felépítését

## <a name="add-a-new-group"></a>Új csoport felvétele

Új csoport létrehozásához használja a következő lépéseket.
1. Az Azure Portalon lépjen a **Csoportok** elemre, majd válassza az **Új csoport** lehetőséget az **Összes csoport** panelen.
  ![Az Azure Portal képernyőképe a kijelölt Új csoport lehetőséggel](./media/groups-add-new.png)
2. Töltse ki az új csoporthoz a **Név** és a **Leírás** mezőt. Ezek a tulajdonságok csak a felügyeleti portálon jelennek meg, és a felhasználók nem láthatják.

3. Válassza a **Tagságtípus**:
  - **Hozzárendelt** lehetőséget manuálisan hozzárendelt tagokkal rendelkező csoport létrehozásához. További tudnivalók az [Azure AD hozzárendelt csoportjairól](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dinamikus felhasználó** **Dinamikus lekérdezéssel** meghatározott felhasználói csoport létrehozásához.
  - **Dinamikus eszköz** **Dinamikus lekérdezéssel** meghatározott eszközcsoport létrehozásához.

  ![Képernyőkép egy Intune-csoport tulajdonságairól Név, Leírás, Tagságtípus, Office engedélyezése funkciókkal és tagokkal](./media/groups-add-properties.png)

  Az Azure AD lehetővé teszi dinamikus csoportok létrehozását a tagságot meghatározó szabályok alapján. Az [attribútumalapú dinamikus csoportok létrehozásának](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) elsajátítása.

4. Kiválaszthatja az **Engedélyezi az Office-funkciókat** lehetőséget, hogy a felhasználói csoport tagjai elérhessék a megosztott Office 365-alkalmazásokat. További információk az [Office 365-csoportokról](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Az új csoport hozzáadásához válassza a **Létrehozás** lehetőséget.

## <a name="see-also"></a>Lásd még:
- [Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md)

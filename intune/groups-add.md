---
title: "Regisztrációs korlátozások beállítása az Intune-ban"
titleSuffix: Intune on Azure
description: "Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce779e8dad2c9813d5faf1f03bca9b33690508fe
ms.sourcegitcommit: b287025b1a0d09d41faf51cf98c34b676fa1d98e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2017
---
# <a name="add-groups-in-intune"></a>Csoportok felvétele az Intune-ban
Az Intune Azure Active Directory- (AD-) csoportokat használ az eszközök és felhasználók kezelésére. Intune-rendszergazdaként csoportokat állíthat be a vállalat igényeinek megfelelően. Létrehozhat csoportokat a felhasználók és eszközök földrajzi hely, részleg vagy hardverjellemzők szerinti rendezéséhez. Használjon csoportokat a feladatok nagy számban való végrehajtásához. Beállíthat például szabályzatokat számos felhasználóhoz, vagy üzembe helyezhet alkalmazásokat eszközök egy csoportján.

Ez a témakör elmagyarázza, hogyan vehet fel csoportokat az Intune-ban való használatra.

A következő típusú csoportokat veheti fel:
- **Hozzárendelt csoportok** – Felhasználók vagy eszközök manuális hozzáadása egy statikus csoporthoz
- **Dinamikus csoportok** – Az (Azure Active Directory Premium) lehetővé teszi egyszerű vagy speciális szabályokkal meghatározott felhasználói vagy eszközcsoportok dinamikus felépítését

## <a name="add-a-new-group"></a>Új csoport felvétele

Új csoport létrehozásához használja a következő lépéseket.
1. Az Intune-portálon lépjen a **Csoportok** elemre, és válassza az **Összes csoport** panelen az **Új csoport** lehetőséget.
  ![Az Intune-portál képernyőképe a kijelölt Új csoport lehetőséggel](./media/groups-add-new.png)
2. Töltse ki az új csoporthoz a **Név** és a **Leírás** mezőt. Ezek a tulajdonságok csak az Intune-portálon jelennek meg, és a felhasználók nem láthatják.

3. Válassza a **Tagságtípus**:
  - **Hozzárendelt** lehetőséget manuálisan hozzárendelt tagokkal rendelkező csoport létrehozásához. További tudnivalók az [Azure AD hozzárendelt csoportjairól](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dinamikus felhasználó** **Dinamikus lekérdezéssel** meghatározott felhasználói csoport létrehozásához.
  - **Dinamikus eszköz** **Dinamikus lekérdezéssel** meghatározott eszközcsoport létrehozásához.

  ![Képernyőkép egy Intune-csoport tulajdonságairól Név, Leírás, Tagságtípus, Office engedélyezése funkciókkal és tagokkal](./media/groups-add-properties.png)

  Az Azure AD lehetővé teszi dinamikus csoportok létrehozását a tagságot meghatározó szabályok alapján. Az [attribútumalapú dinamikus csoportok létrehozásának](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) elsajátítása.

4. Kiválaszthatja az **Engedélyezi az Office-funkciókat** lehetőséget, hogy a felhasználói csoport tagjai elérhessék a megosztott Office 365-alkalmazásokat.
5. Az új csoport hozzáadásához válassza a **Létrehozás** lehetőséget.

## <a name="see-also"></a>További információ
- [Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md)

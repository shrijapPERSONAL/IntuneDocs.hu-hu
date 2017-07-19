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
ms.openlocfilehash: 2c9d10e4e2a1d2a745b9e327bf9a8a9cd99e5ce4
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2017
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
[Erőforrásokhoz való hozzáférés kezelése az Azure Active Directoryval](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
[Klasszikus Intune-csoportok az Azure-portálon](groups-get-started.md)

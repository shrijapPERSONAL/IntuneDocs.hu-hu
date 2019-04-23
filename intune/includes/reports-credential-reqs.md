---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511329"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Az Azure AD-beli és az Intune-beli hitelesítő adatokra vonatkozó követelmények

A hitelesítés és az engedélyezés az Azure AD-beli hitelesítő adatokon és az Intune szerepköralapú hozzáférés-vezérlésén (RBAC) alapul. Alapértelmezés szerint a bérlő valamennyi globális rendszergazdája és Intune-beli szolgáltatás-rendszergazdája hozzáféréssel rendelkezik az adattárházhoz. Az Intune-szerepkörök használatával azáltal biztosíthat több felhasználónak is hozzáférést, hogy hozzáférést ad nekik az **Intune-adattárház** erőforráshoz.

Az Intune-adattárházhoz való hozzáférésre (beleértve az API-t is) vonatkozó követelmények a következők:

  -  A felhasználónak a következők egyikének kell lennie:
      -  Azure AD-beli globális rendszergazda
      -  Intune-beli szolgáltatás-rendszergazda
      -  Felhasználó szerepköralapú hozzáféréssel az **Intune-adattárház** erőforráshoz
      -  Felhasználó nélküli hitelesítés [csak alkalmazásalapú hitelesítés](../data-warehouse-app-only-auth.md) 

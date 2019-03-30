---
title: Az Intune felhasználói szerepkör hozzárendelése
description: Megtudhatja, hogyan beépített vagy egyéni szerepkör hozzárendelése egy felhasználóhoz, a Microsoft Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a59c413fcc11dfce76152a7325517703a71785d2
ms.sourcegitcommit: 0adb41c0640743d5cb726e66ad2427e3ad6faf20
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58658795"
---
# <a name="assign-a-role-to-an-intune-user"></a>Az Intune felhasználói szerepkör hozzárendelése

Hozzárendelhet egy [beépített](role-based-access-control.md#built-in-roles) vagy [egyéni](create-custom-role.md) az Intune felhasználói szerepkört.

A szerepkörök létrehozásához, szerkesztéséhez vagy hozzárendeléséhez a fióknak rendelkeznie kell a következő jogosultságok egyikével az Azure AD-ben:
- **Globális rendszergazda**
- **Intune-beli szolgáltatás-rendszergazda**

Az engedélyek minden beépített szerepkör teljes listáját lásd: a [Intune RBAC-táblázat](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).

2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.

3. Az a **Intune** panelen válassza a **szerepkörök** > **minden szerepkör**.

4. Az a **az Intune-szerepkörök – minden szerepkör** panelen válassza ki a hozzárendelni kívánt szerepkört.

5. Az a <*szerepkörnév*>- **áttekintése** panelen válassza a **kezelés** > **hozzárendelések**.

6. Kattintson a **Hozzárendelés** elemre az Egyéni szerepkör panelen.

7. Az a **szerepkör-hozzárendelések** panelen adjon meg egy **hozzárendelés neve** és választható **hozzárendelés leírása** a hozzárendelés.

8. A **tagok (csoportok)**, válasszon egy csoportot, amely tartalmazza azt a felhasználót szeretne adni az engedélyeket.

9. A **hatókör (csoportok)**, válassza ki a felhasználók és eszközök kezeléséhez engedélyezni a fenti tag tartalmazó csoport.

10. A **hatókör (címkék)**, válassza ki a címkét, ahol a szerepkör-hozzárendelés alkalmazza.

11. Ha elkészült, válassza az **OK** gombot. Az új hozzárendelés megjelenik a hozzárendelések listájában.


## <a name="next-steps"></a>További lépések
- [További információ a szerepköralapú hozzáférés-vezérlés az Intune-ban](role-based-access-control.md)
- [Egyéni szerepkör létrehozása](create-custom-role.md)

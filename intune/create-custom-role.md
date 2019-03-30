---
title: Egyéni szerepkör létrehozása az Intune-ban
description: Ismerje meg, hogy egy egyéni szerepkör létrehozása a Microsoft Intune-ban.
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
ms.openlocfilehash: f7e1e67f617c0a345b17aa731fd193e611eba71e
ms.sourcegitcommit: 0adb41c0640743d5cb726e66ad2427e3ad6faf20
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58658794"
---
# <a name="create-a-custom-role-in-intune"></a>Egyéni szerepkör létrehozása az Intune-ban

Létrehozhat egy egyéni Intune-szerepkör, amely tartalmazza az adott munkakörhöz szükséges összes engedélyt. Például ha egy IT-részleg alkalmazásokat, szabályzatokat, és konfigurációs profilokat kezel, mindezeket az engedélyeket együtt adhatja meg egy egyéni szerepkör segítségével. Egy egyéni szerepkör létrehozása után is [hozzárendelése](assign-role.md) , hogy azokat a felhasználókat, ezeket az engedélyeket kell.

A szerepkörök létrehozásához, szerkesztéséhez vagy hozzárendeléséhez a fióknak rendelkeznie kell a következő jogosultságok egyikével az Azure AD-ben:
- **Globális rendszergazda**
- **Intune-beli szolgáltatás-rendszergazda**

## <a name="to-create-a-custom-role"></a>Egyéni szerepkör létrehozása

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com) az Intune-os hitelesítő adataival.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Válasszon **Intune** > **szerepkörök** > **minden szerepkör** > **Hozzáadás**.

4. Az **Egyéni szerepkör hozzáadása** panelen adja meg az új szerepkör nevét és leírását, majd kattintson az **Engedélyek** elemre.

5. Az **Engedélyek** panelen válassza ki az ehhez a szerepkörhöz használni kívánt engedélyeket. Az [Intune-os RBAC-táblázat](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) segít eldönteni, hogy milyen engedélyeket alkalmazzon.

6. Az a **hatókör (címkék)** panelen válassza ki a címkék ehhez a szerepkörhöz. Ez a szerepkör hozzáférhet ezekkel a címkékkel rendelkező erőforrásokat.

7. Ha elkészült, válassza az **OK** gombot.

8. Az **Egyéni szerepkör hozzáadása** panelen kattintson a **Létrehozás** elemre. Az új szerepkör megjelenik a listában a **az Intune-szerepkörök – minden szerepkör** panelen.

## <a name="next-steps"></a>További lépések
- [Szerepkör hozzárendelése felhasználóhoz](assign-role.md)
- [További információ a szerepköralapú hozzáférés-vezérlés az Intune-ban](role-based-access-control.md)

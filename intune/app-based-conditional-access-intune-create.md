---
title: "Alkalmazásalapú feltételes hozzáférési szabályzat az Intune-nal"
description: "Ez a témakör ismerteti, hogy hogyan konfigurálhat alkalmazásalapú feltételes hozzáférési szabályzatot az Intune-nal."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör utasításokat tartalmaz alkalmazásalapú feltételes hozzáférési szabályzatok beállításához a jóváhagyott alkalmazások listáján szereplő alkalmazásokhoz. A jóváhagyott alkalmazások listája a Microsoft által tesztelt alkalmazásokból áll.

> [!IMPORTANT]
> Ez a témakör az alkalmazásalapú feltételes hozzáférési szabályzat Exchange Online-nal való felvételének lépésein vezeti végig, de ugyanezekkel a lépésekkel vehet fel más alkalmazásokat is a jóváhagyott alkalmazások listájáról, például a SharePoint Online, a Microsoft Teams stb. alkalmazást.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása
1.  Nyissa meg az [Azure Portal](https://portal.azure.com) webhelyet, és jelentkezzen be a hitelesítő adataival.

2.  Válassza a **További szolgáltatások** lehetőséget, majd írja be az Intune kifejezést.

3.  Válassza az **Intune alkalmazásvédelem** lehetőséget.

4.  Az **Intune mobilalkalmazás-kezelés** panelen kattintson a **Minden beállítás** csempére.

5.  A **Feltételes hozzáférés** szakaszban válassza az **Exchange Online** elemet.

    ![Képernyőfelvétel a beállítások panel feltételes hozzáférés területéről, amelyen kiemelve látható az Exchange Online opció](./media/MAM-conditional-access-1.png)

6. Az **Engedélyezett alkalmazások** panelen válassza **Az Intune alkalmazásszabályzatait támogató alkalmazások engedélyezése** lehetőséget, hogy csak az Intune alkalmazásvédelmi szabályzatai által támogatott alkalmazások férhessenek hozzá az Exchange Online-hoz. Amikor kiválasztja ezt a beállítást, megjelenik a támogatott alkalmazások listája.

    > [!NOTE]
    > Ebben az esetben egyik Exchange Active Sync e-mail ügyfélprogram sem, így az iOS és az Android Exchange Online-hoz csatlakozó beépített e-mail ügyfélprogramjai sem küldhetnek vagy fogadhatnak leveleket. A felhasználók ehelyett egyetlen e-mail üzenetet kapnak, amely tájékoztatja őket, hogy az Outlook e-mail alkalmazást kell használniuk.

7. A szabályzatnak a felhasználókra való alkalmazásához nyissa meg a **Korlátozott felhasználói csoportok** panelt, és válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válasszon ki egy vagy több felhasználói csoportot, amelyre alkalmazni kívánja ezt a szabályzatot.

    ![A korlátozott felhasználói csoportok panel a felhasználói csoport hozzáadás opció kiemelésével – képernyőfelvétel](./media/mam-ca-add-user-group.png)

8. Előfordulhat, hogy az előző lépésben kiválasztott felhasználói csoportnak vannak olyan tagjai, akikre nem kívánja alkalmazni ezt a szabályzatot. Ilyen esetben e felhasználók csoportját adja hozzá a kivétel alá eső felhasználók listájához. Az **Exchange Online** panelen válassza a **Kivétel alá eső felhasználói csoportok** lehetőséget. A felhasználói csoportok listájának megnyitásához válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válassza ki azokat a csoportokat, amelyeket szeretné kivonni a szabályzat hatálya alól.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Felhasználói csoportok módosítása meglévő alkalmazásalapú feltételes hozzáférési szabályzatban vagy törlése abból

1. Nyissa meg a **Korlátozott felhasználói csoportok** panelt, majd jelölje ki a törölni kívánt felhasználói csoportot.
2. A három pontra kattintva megjelennek a törlési lehetőségek.
3. A felhasználói csoportnak a listáról való eltávolításához válassza a **Törlés** opciót.

## <a name="next-steps"></a>További lépések
[Modern hitelesítés nélküli alkalmazások blokkolása](app-modern-authentication-block.md)

### <a name="see-also"></a>További információ

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](app-protection-policies.md)

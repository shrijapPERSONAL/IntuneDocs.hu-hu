---
title: "Alkalmazás-hozzáférés az Exchange Online-hoz | Microsoft Docs"
description: "Ez a témakör ismerteti, hogy hogyan konfigurálhat feltételes hozzáférési szabályzatot MAM-alkalmazásokhoz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: ab6d1cf6a6b77be6aff6398ff99135674471ba35


---

# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a>Exchange Online feltételes hozzáférés konfigurálása kizárólag az MAM által támogatott alkalmazások engedélyezéséhez

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör lépésről lépésre végigvezeti azon, hogy miként tud feltételes hozzáférést beállítani az Exchange Online-hoz úgy, hogy csak az Intune alkalmazásvédelmi szabályzatokat támogató mobilalkalmazások legyenek engedélyezve.


## <a name="create-an-exchange-online-policy"></a>Exchange Online-szabályzat létrehozása
1.  Jelentkezzen be az alkalmazás-hozzáférési funkciót tartalmazó [Azure-portálon](https://portal.azure.com). Ha még csak most ismerkedik az Azure Portallal, olvassa el az [Alkalmazásvédelmi szabályzatok az Azure Portalon](azure-portal-for-microsoft-intune-mam-policies.md) című témakört.

2.  Válassza a **További szolgáltatások** lehetőséget, majd írja be az Intune kifejezést.

3.  Válassza az **Intune alkalmazásvédelem** lehetőséget.

4.  Az **Intune mobilalkalmazás-kezelés** panelen kattintson a **Minden beállítás** csempére.

5.  A **Feltételes hozzáférés** szakaszban válassza az **Exchange Online** elemet.

    ![Képernyőfelvétel a beállítások panel feltételes hozzáférés területéről, amelyen kiemelve látható az Exchange Online opció](../media/MAM-conditional-access-1.png)

6. Az **Engedélyezett alkalmazások** panelen válassza **Az Intune alkalmazásszabályzatait támogató alkalmazások engedélyezése** lehetőséget, hogy csak az Intune alkalmazásvédelmi szabályzatai által támogatott alkalmazások férhessenek hozzá az Exchange Online-hoz. Amikor kiválasztja ezt a beállítást, megjelenik a támogatott alkalmazások listája.

    >[!NOTE]
    >Ebben az esetben egyik Exchange Active Sync e-mail ügyfélprogram sem, így az iOS és az Android Exchange Online-hoz csatlakozó beépített e-mail ügyfélprogramjai sem küldhetnek vagy fogadhatnak leveleket. A felhasználók ehelyett egyetlen e-mail üzenetet kapnak, amely tájékoztatja őket, hogy az Outlook e-mail alkalmazást kell használniuk.

7. A szabályzatnak a felhasználókra való alkalmazásához nyissa meg a **Korlátozott felhasználói csoportok** panelt, és válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válasszon ki egy vagy több felhasználói csoportot, amelyre alkalmazni kívánja ezt a szabályzatot.

    ![A korlátozott felhasználói csoportok panel a felhasználói csoport hozzáadás opció kiemelésével – képernyőfelvétel](../media/mam-ca-add-user-group.png)

8. Előfordulhat, hogy az előző lépésben kiválasztott felhasználói csoportnak vannak olyan tagjai, akikre nem kívánja alkalmazni ezt a szabályzatot. Ilyen esetben e felhasználók csoportját adja hozzá a kivétel alá eső felhasználók listájához. Az **Exchange Online** panelen válassza a **Kivétel alá eső felhasználói csoportok** lehetőséget. A felhasználói csoportok listájának megnyitásához válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válassza ki azokat a csoportokat, amelyeket szeretné kivonni a szabályzat hatálya alól.  

## <a name="modify-an-existing-policy"></a>Meglévő szabályzat módosítása
### <a name="add-or-delete-user-groups"></a>Felhasználói csoportok hozzáadása vagy törlése

**Felhasználói csoport törléséhez** a **korlátozás alá eső felhasználói csoportok** listáról nyissa meg a **Korlátozás alá eső felhasználó csoportok** panelt, jelölje ki a törölni kívánt felhasználói csoportot és kattintson a **három pontra (...)** a **Törlés** opció megjelenítéséhez. A felhasználói csoportnak a listáról való eltávolításához válassza a **Törlés** opciót. Ugyanezzel az eljárással törölhet felhasználói csoportot a **kivétel alá eső felhasználói csoportok** listáról.


## <a name="next-steps"></a>További lépések
[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a>További információ
[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->



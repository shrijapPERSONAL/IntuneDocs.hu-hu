---
title: Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása a SharePoint Online-hoz
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 05/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 5848fc18e0c288f8806f1fc93427d96c48317d64
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a SharePoint Online-hoz

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Ez a témakör az alkalmazásalapú feltételes hozzáférési szabályzatok SharePoint Online-hoz való beállításához ad útmutatást. Az alkalmazásalapú feltételes hozzáféréssel a rendszergazdák engedélyezhetik csak olyan mobilalkalmazások használatát, melyekre az Intune alkalmazásvédelmi szabályzatai vonatkoznak.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása a SharePoint Online-hoz

1. Nyissa meg az [Azure Portal](https://portal.azure.com) webhelyet, és jelentkezzen be a hitelesítő adataival.

    > [!NOTE]
    > Ha még csak most ismerkedik az Azure Portal felületével, olvassa el az [Alkalmazásvédelmi szabályzatok az Azure Portalon](azure-portal-for-microsoft-intune-mam-policies.md) című témakört.

2. Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Válassza az **Intune App Protection** > **Intune mobilalkalmazás-kezelés** > **Minden beállítás** elemet.

4. Az Intune mobilalkalmazás-kezelés panelen kattintson a SharePoint Online csempére.

5. Az **Engedélyezett alkalmazások** panelen válassza **Az Intune alkalmazásszabályzatait támogató alkalmazások engedélyezése** lehetőséget, hogy csak az Intune alkalmazásvédelmi szabályzatai által támogatott alkalmazások legyenek engedélyezve.

    > [!NOTE] 
    > Amikor kiválasztja a csak az Intune alkalmazásvédelmi szabályzatai által támogatott alkalmazások engedélyezésének lehetőségét, megjelenik egy **kizárólag** a támogatott alkalmazásokat tartalmazó lista.

    ![Képernyőkép az engedélyezett alkalmazások panelről az alkalmazások listájával](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok hozzárendelése felhasználókhoz

1. Nyissa meg a **Korlátozott felhasználói csoportok** panelt, majd válassza a **Felhasználói csoport hozzáadása** lehetőséget.

2. Válasszon ki egy vagy több felhasználói csoportot, amelyre alkalmazni kívánja ezt a szabályzatot.

    ![A korlátozott felhasználói csoportok panel a felhasználói csoport hozzáadás opció kiemelésével – képernyőfelvétel](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Előfordulhat, hogy az előző lépésben kiválasztott felhasználói csoportnak vannak olyan tagjai, akikre nem kívánja alkalmazni ezt a szabályzatot. Ilyen esetben e felhasználók csoportját adja hozzá a kivétel alá eső felhasználók listájához. 

3. A **SharePoint Online** panelen válassza a **Kivétel alá eső felhasználói csoportok**, majd a **Felhasználói csoport hozzáadása** lehetőséget a felhasználói csoportok listájának megnyitásához.

4. Válassza ki azokat a csoportokat, amelyeket szeretné kivonni a szabályzat hatálya alól.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Felhasználói csoportok módosítása meglévő alkalmazásalapú feltételes hozzáférési szabályzatban vagy törlése abból

1. Nyissa meg a **Korlátozott felhasználói csoportok** panelt, majd jelölje ki a törölni kívánt felhasználói csoportot.
2. A három pontra kattintva megjelennek a törlési lehetőségek.
3. A felhasználói csoportnak a listáról való eltávolításához válassza a **Törlés** opciót.

> [!NOTE] 
> Ugyanezzel az eljárással törölhet felhasználói csoportot a **Kivétel alá eső felhasználói csoportok** listájáról is.

## <a name="next-steps"></a>További lépések

[Modern hitelesítés nélküli alkalmazások letiltása](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Lásd még:

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Alkalmazásalapú feltételes hozzáférés konfigurálása az Exchange Online-hoz](mam-ca-for-exchange-online.md)

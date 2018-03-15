---
title: "Alkalmazásalapú feltételes hozzáférési szabályzat beállítása az Intune-ban"
description: "Útmutató az alkalmazásalapú feltételes hozzáférési szabályzatok Intune-ban való létrehozásához."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89ee7c0df2fde740c18b84f1d9f028d59ba5d81d
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A cikk azt írja le, hogyan állíthatók be alkalmazásalapú feltételes hozzáférési szabályzatok a jóváhagyott alkalmazások listáján szereplő alkalmazásokhoz. A jóváhagyott alkalmazások listája a Microsoft által tesztelt alkalmazásokból áll.

> [!IMPORTANT]
> A cikk az alkalmazásalapú feltételes hozzáférési szabályzat Exchange Online-nal való felvételének lépésein vezeti végig, de ugyanezekkel a lépésekkel vehet fel olyan más alkalmazásokat is a jóváhagyott alkalmazások listájáról, mint például a SharePoint Online, a Microsoft Teams, stb.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása
1.  Nyissa meg az [Azure Portal](https://portal.azure.com) webhelyet, és jelentkezzen be a hitelesítő adataival.

2.  Válassza a **Minden szolgáltatás** lehetőséget, majd írja be az Intune kifejezést.

3.  Válassza az **Intune alkalmazásvédelem** lehetőséget.

4.  Az **Intune App Protection** panel **Feltételes hozzáférés** szakaszában válassza az **Exchange Online** lehetőséget.

    ![Képernyőkép a beállítások panel feltételes hozzáférés területéről, amelyen kiemelve látható az Exchange Online lehetőség](./media/MAM-conditional-access-1.png)

6. Az **Engedélyezett alkalmazások** panelen válassza **Az Intune alkalmazásszabályzatait támogató alkalmazások engedélyezése** lehetőséget, hogy csak az Intune alkalmazásvédelmi szabályzatai által támogatott alkalmazások férhessenek hozzá az Exchange Online-hoz. Amikor kiválasztja ezt a beállítást, megjelenik a támogatott alkalmazások listája.

    > [!NOTE]
    > Ebben az esetben egyik Exchange ActiveSync-levelezőprogram sem, így az iOS és az Android Exchange Online-hoz csatlakozó beépített levelezőprogramjai sem küldhetnek vagy fogadhatnak leveleket. A felhasználók ehelyett egyetlen e-mail üzenetet kapnak, amely tájékoztatja őket, hogy az Outlook e-mail alkalmazást kell használniuk.

7. A szabályzatnak a felhasználókra való alkalmazásához nyissa meg a **Korlátozott felhasználói csoportok** panelt, és válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válasszon ki egy vagy több felhasználói csoportot, amelyre alkalmazni kívánja ezt a szabályzatot.

    ![Képernyőkép a Korlátozott felhasználói csoportok panelről, a Felhasználói csoport hozzáadása lehetőség kiemelésével](./media/mam-ca-add-user-group.png)

8. Előfordulhat, hogy az előző lépésben kiválasztott felhasználói csoportnak vannak olyan tagjai, akikre nem kívánja alkalmazni ezt a szabályzatot. Ilyen esetben e felhasználók csoportját adja hozzá a kivétel alá eső felhasználók listájához. Az **Exchange Online** panelen válassza a **Kivétel alá eső felhasználói csoportok** lehetőséget. A felhasználói csoportok listájának megnyitásához válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válassza ki azokat a csoportokat, amelyeket szeretné kivonni a szabályzat hatálya alól.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Felhasználói csoportok módosítása meglévő alkalmazásalapú feltételes hozzáférési szabályzatban vagy törlése abból

1. Nyissa meg a **Korlátozott felhasználói csoportok** panelt, majd jelölje ki a törölni kívánt felhasználói csoportot.
2. A három pontra kattintva megjelennek a törlési lehetőségek.
3. A felhasználói csoportnak a listáról való eltávolításához válassza a **Törlés** opciót.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok Azure AD-munkafolyamatban való létrehozása

Az Intune 1708-as kiadásától kezdve a rendszergazdák alkalmazásalapú feltételes hozzáférési szabályzatokat hozhatnak létre az Azure AD-munkafolyamatból. E kényelmes megoldásnak köszönhetően nem kell váltania az Azure- és az Intune-munkafolyamatok között.

> [!IMPORTANT]
> Ahhoz, hogy Azure AD feltételes hozzáférési szabályzatokat hozhasson létre az Intune Azure Portal webhelyen, Azure AD Premium szintű előfizetésre van szükség.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása

> [!IMPORTANT]
> Az alkalmazásalapú feltételes hozzáférési szabályzatok használatakor már [Intune-beli alkalmazásvédelmi szabályzatokkal](app-protection-policies.md) kell rendelkeznie az alkalmazásokra vonatkozóan.

1. Az **Intune irányítópultján** válassza a **Feltételes hozzáférés** lehetőséget.

2. Az új alkalmazásalapú feltételes hozzáférési szabályzat létrehozásához a **Szabályzatok** panelen válassza az **Új szabályzat** lehetőséget.

4. A szabályzatnév megadása, valamint a **Hozzárendelések** szakaszban hozzáférhető beállítások konfigurálása után válassza a **Hozzáférés-szabályozás** szakaszban található **Engedélyezés** elemet.

5. Az új szabályzat mentéséhez válassza a **Jóváhagyott ügyfélalkalmazás megkövetelése**, majd a **Kijelölés**, végül pedig a **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések
[Modern hitelesítés nélküli alkalmazások blokkolása](app-modern-authentication-block.md)

### <a name="see-also"></a>Lásd még:

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](app-protection-policies.md)
[Feltételes hozzáférés az Azure Active Directory-ban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)

---
title: "Alkalmazás-hozzáférés konfigurálása a SharePoint Online-hoz"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>SharePoint Online feltételes hozzáférési szabályzat létrehozása kizárólag a MAM által támogatott alkalmazások engedélyezéséhez
Ez a témakör lépésről lépésre végigvezeti azon, hogy miként tud feltételes hozzáférést beállítani az Exchange Online-hoz úgy, hogy csak az Intune mobilalkalmazás-kezelési (MAM) szabályzatokat támogató mobilalkalmazások legyenek engedélyezettek.

## <a name="configure-a-sharepoint-online-policy"></a>SharePoint Online-szabályzat konfigurálása
**1. lépés:** Jelentkezzen be az alkalmazás-hozzáférési funkciót tartalmazó [Azure-portálon](https://portal.azure.com). Ha még csak most ismerkedik az Azure-portállal, olvassa el a [MAM-szabályzatok az Azure-portálon](azure-portal-for-microsoft-intune-mam-policies.md) témakört.

**2. lépés:** Válassza a **Tallózás > Intune > Intune mobilalkalmazás-felügyeleti panel > Beállítások** lehetőséget, és a **feltételes hozzáférés** területen válassza a **SharePoint Online-t**.

![A beállítások panel képernyőképe a feltételes hozzáférés szakasszal, a megnyitott SharePoint Online panellel](../media/mam-ca-settings-spo.png)

**3. lépés:** Az **Engedélyezett alkalmazások** panelen válassza az **Intune alkalmazás-szabályzatokat támogató alkalmazások engedélyezése** lehetőséget, hogy csak az Intune MAM-szabályzatai által támogatott alkalmazások férhessenek hozzá a SharePoint Online-hoz. Amikor kiválasztja a csak az Intune MAM-szabályzatokat támogató alkalmazások engedélyezését, megjelenik a támogatott alkalmazások listája.

![Képernyőkép az engedélyezett alkalmazások panelről az alkalmazások listájával](../media/mam-ca-spo-allowed-apps.png)

**4. lépés:** A szabályzatnak a felhasználókra való alkalmazásához nyissa meg a **Korlátozott felhasználói csoportok** panelt, és válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válasszon ki egy vagy több felhasználói csoportot, amelyre alkalmazni kívánja ezt a szabályzatot.

![A korlátozott felhasználói csoportok panel a felhasználói csoport hozzáadás opció kiemelésével – képernyőfelvétel](../media/mam-ca-spo-restricted-groups.png)


**5. lépés:** Előfordulhat, hogy az előző lépésben kiválasztott felhasználói csoportnak vannak olyan tagjai, akikre nem kívánja alkalmazni ezt a szabályzatot. Ilyen esetben e felhasználók csoportját adja hozzá a kivétel alá eső felhasználók listájához. A **SharePoint Online** panelen válassza a **Kivétel alá eső felhasználói csoportok** lehetőséget. A felhasználói csoportok listájának megnyitásához válassza a **Felhasználói csoport hozzáadása** lehetőséget. Válassza ki azokat a csoportokat, amelyeket szeretné kivonni a szabályzat hatálya alól.  

## <a name="modifying-an-existing-policy"></a>Meglévő szabályzat módosítása
### <a name="adding-or-deleting-user-groups"></a>Felhasználói csoportok hozzáadása vagy törlése
Ha **felhasználói csoportot szeretne törölni** a **korlátozás alá eső felhasználói csoportok** listáról, nyissa meg a Korlátozás alá eső felhasználói csoportok panelt, jelölje ki a törölni kívánt felhasználói csoportot, és kattintson a három pontra (...) a törlési opció megjelenítéséhez. A felhasználói csoportnak a listáról való eltávolításához válassza a **Törlés** opciót. Ugyanezzel az eljárással törölhet felhasználói csoportot a **kivétel alá eső felhasználói csoportok** listáról.


## <a name="next-steps"></a>További lépések
[Alkalmazás-hozzáférés konfigurálása Exchange Online-hoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>További információ

[Alkalmazásadatok védelme MAM-szabályzatok használatával](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)


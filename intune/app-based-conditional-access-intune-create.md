---
title: Alkalmazásalapú feltételes hozzáférési szabályzat beállítása az Intune-ban
description: Útmutató az alkalmazásalapú feltételes hozzáférési szabályzatok Intune-ban való létrehozásához.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c505e881fe06d6f4da217533d0507731ac22a29f
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk azt írja le, hogyan állíthatók be alkalmazásalapú feltételes hozzáférési szabályzatok a jóváhagyott alkalmazások listáján szereplő alkalmazásokhoz. A jóváhagyott alkalmazások listája a Microsoft által tesztelt alkalmazásokból áll.

> [!IMPORTANT]
> Ez a cikk végigvezeti az alkalmazásalapú feltételes hozzáférési szabályzatok hozzáadásának lépésein. Ne feledje, hogy ugyanezeket a lépéseket használhatja, ha alkalmazásokat ad hozzá, például SharePoint Online, Microsoft Teams és Microsoft Exchange Online, a jóváhagyott alkalmazások listájából.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok Azure AD-munkafolyamatban való létrehozása

A rendszergazdák alkalmazásalapú feltételes hozzáférési szabályzatokat hozhatnak létre az Azure AD-munkafolyamatból. E kényelmes megoldásnak köszönhetően nem kell váltania az Azure- és az Intune-munkafolyamatok között.

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

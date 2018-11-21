---
title: Alkalmazásalapú feltételes hozzáférési szabályzat beállítása az Intune-ban
description: Útmutató az alkalmazásalapú feltételes hozzáférési szabályzatok Intune-ban való létrehozásához.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 32044422943282d9cf813192405a335ee756e44e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52177931"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a jóváhagyott alkalmazások listáján szereplő alkalmazásokhoz. A jóváhagyott alkalmazások listája a Microsoft által tesztelt alkalmazásokból áll.

> [!IMPORTANT]
> Ez a cikk végigvezeti az alkalmazásalapú feltételes hozzáférési szabályzatok hozzáadásának lépésein. Ugyanezeket a lépéseket használhatja, ha alkalmazásokat ad hozzá, például SharePoint Online, Microsoft Teams és Microsoft Exchange Online, a jóváhagyott alkalmazások listájából.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok Azure AD-munkafolyamatban való létrehozása

A rendszergazdák alkalmazásalapú feltételes hozzáférési szabályzatokat hozhatnak létre az Azure AD-munkafolyamatból. Ennek a hozzáférésnek köszönhetően nem kell váltania az Azure- és az Intune-munkafolyamatok között.

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

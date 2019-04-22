---
title: Alkalmazásalapú feltételes hozzáférési szabályzat beállítása az Intune-ban
titleSuffix: Microsoft Intune
description: Útmutató az alkalmazásalapú feltételes hozzáférési szabályzatok Intune-ban való létrehozásához.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1514fe9dfcd09e2b77967b0fed8c36fb7a06634f
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896031"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a jóváhagyott alkalmazások listáján szereplő alkalmazásokhoz. A jóváhagyott alkalmazások listája a Microsoft által tesztelt alkalmazásokból áll.

> [!IMPORTANT]
> Ez a cikk végigvezeti az alkalmazásalapú feltételes hozzáférési szabályzatok hozzáadásának lépésein. Ugyanezeket a lépéseket használhatja, ha alkalmazásokat ad hozzá, például SharePoint Online, Microsoft Teams és Microsoft Exchange Online, a jóváhagyott alkalmazások listájából.

## <a name="create-app-based-conditional-access-policies"></a>Alkalmazásalapú feltételes hozzáférési szabályzatok létrehozása
A feltételes hozzáférés az Azure Active Directory (Azure AD) technológiája. Az *Intune-ból* elérhető feltételes hozzáférési csomópont ugyanaz a csomópont, amelyet az *Azure AD-ből* is el lehet érni. Ez azt jelenti, hogy nem kell váltani szabályzatok konfigurálása Intune-ban és az Azure AD között.

> [!IMPORTANT]
> Szüksége lesz egy Azure AD Premium-licencet hozhat létre feltételes hozzáférési szabályzatokat az Intune-portálon.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása

> [!IMPORTANT]
> Az alkalmazásalapú feltételes hozzáférési szabályzatok használatakor már [Intune-beli alkalmazásvédelmi szabályzatokkal](app-protection-policies.md) kell rendelkeznie az alkalmazásokra vonatkozóan.

1. Az a **Intune irányítópult**válassza **feltételes hozzáférési**.

2. Az új alkalmazásalapú feltételes hozzáférési szabályzat létrehozásához a **Szabályzatok** panelen válassza az **Új szabályzat** lehetőséget.

4. A szabályzatnév megadása, valamint a **Hozzárendelések** szakaszban hozzáférhető beállítások konfigurálása után válassza a **Hozzáférés-szabályozás** szakaszban található **Engedélyezés** elemet.

5. Az új szabályzat mentéséhez válassza a **Jóváhagyott ügyfélalkalmazás megkövetelése**, majd a **Kijelölés**, végül pedig a **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések
[Modern hitelesítés nélküli alkalmazások blokkolása](app-modern-authentication-block.md)

### <a name="see-also"></a>Lásd még:

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](app-protection-policies.md)
[Feltételes hozzáférés az Azure Active Directory-ban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)

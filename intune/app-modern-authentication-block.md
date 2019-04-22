---
title: Modern hitelesítés nélküli alkalmazások blokkolása az Intune-ban
titleSuffix: Microsoft Intune
description: Tudnivalók az alkalmazások és modern authentication (ADAL) a Microsoft Intune-nal.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897306"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Nem modern authentication (ADAL) használó alkalmazások letiltása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazásalapú feltételes hozzáférés az alkalmazásvédelmi szabályzatokkal védett alkalmazások használatával támaszkodjon [modern hitelesítést](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), azaz az OAuth2 implementációja. A legújabb Office asztali és mobil alkalmazások modern hitelesítést használnak. Előfordulhatnak azonban olyan harmadik féltől származó alkalmazások és régebbi Office-alkalmazások, hogy a felhasználó más hitelesítési módszerek, például alapszintű, vagy űrlap alapú hitelesítéssel.

## <a name="block-access-to-apps"></a>Alkalmazások elérésének blokkolása

Letiltja a nem modern hitelesítést használó alkalmazásokhoz való hozzáférés, használja az Intune alkalmazásvédelmi szabályzatai feltétel hozzáférés megvalósításához. További információkért lásd: [alkalmazásalapú feltételes hozzáférés Intune-nal](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>További információ

Azure AD feltételes hozzáférésével kapcsolatos további információkért lásd a következő témaköröket:
- [Mi az az Azure Active Directory feltételes hozzáférés?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Alkalmazásalapú feltételes hozzáférés működése](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Az Azure Active Directory feltételes hozzáférés beállítása a SharePoint Online és Exchange online-hoz](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>További lépések

- [Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)

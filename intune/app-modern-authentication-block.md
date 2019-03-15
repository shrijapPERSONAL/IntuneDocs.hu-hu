---
title: Modern hitelesítés nélküli alkalmazások blokkolása az Intune-ban
titleSuffix: Microsoft Intune
description: További információ a nem a Microsoft Intune-nal modern authentication (ADAL) használó alkalmazások blokkolása.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4af330f14b8622dd0ee977b2fa81a726845f4da
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57400160"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazásalapú feltételes hozzáférés az alkalmazásvédelmi szabályzatokkal védett alkalmazások használatával támaszkodjon [modern hitelesítést](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), azaz az OAuth2 implementációja. A legújabb Office asztali és mobil alkalmazások modern hitelesítést használnak. Előfordulhatnak azonban olyan harmadik féltől származó alkalmazások és régebbi Office-alkalmazások, hogy a felhasználó más hitelesítési módszerek, például alapszintű, vagy űrlap alapú hitelesítéssel.

## <a name="block-apps"></a>Alkalmazások letiltása

A nem modern hitelesítést használó alkalmazásokhoz való hozzáférés blokkolása, javasoljuk, hogy az alábbi módszerek:

- Állítsa be az ADFS-jogcímszabályokat a nem modern hitelesítési protokollok letiltására. Lépésenkénti útmutatás: 3. forgatókönyv – [Az O365-höz való hozzáférés teljes letiltása a böngészőalapú alkalmazások kivételével](https://technet.microsoft.com/library/dn592182.aspx).
- A **Exchange és SharePoint Online**, a feltételes hozzáférés használata, és a PowerShell-parancsmag segítségével Set-SPOTenant használata a SharePoint online. Részletes útmutatásért lásd: [A SharePoint Online és az Exchange Online beállítása az Azure Active Directoryhoz való feltételes hozzáféréshez](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Alkalmazásalapú feltételes hozzáférés nem használható az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítéssel. A fentiek közül csak az egyik lehet egyszerre konfigurálva.

## <a name="next-steps"></a>További lépések

- [Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)

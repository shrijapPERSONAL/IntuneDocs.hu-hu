---
title: "Modern hitelesítés nélküli alkalmazások blokkolása"
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
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0f192c0e41cf3b639cbfdac3f8c4fc3b8167266d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az alkalmazásvédelmi szabályzatokat használó alkalmazásalapú feltételes hozzáférés a [modern hitelesítést](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) használó alkalmazásokra épül, ami az OAuth2 implementációja. A legújabb asztali és mobil Office-alkalmazások már modern hitelesítést használnak, de vannak olyan külső gyártótól származó programok és régebbi Office-alkalmazások, amelyek másfajta hitelesítéssel működnek, például alapszintű vagy űrlap alapú hitelesítéssel.

Az ilyen típusú alkalmazásokat így blokkolhatja:

* Állítsa be az ADFS-jogcímszabályokat a nem modern hitelesítési protokollok letiltására. Lépésenkénti útmutatás: 3. forgatókönyv – [Az O365-höz való hozzáférés teljes letiltása a böngészőalapú alkalmazások kivételével](https://technet.microsoft.com/library/dn592182.aspx).
* A **SharePoint Online** esetén modern hitelesítés nélküli alkalmazások a SharePoint Online szolgáltatásban tilthatók le úgy, hogy a [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) PowerShell-parancsmaggal az örökölt hitelesítési protokollok értéket hamisra állítja:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>Az alkalmazásalapú feltételes hozzáférést tilos az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítésével használni. A fentiek közül csak az egyik lehet egyszerre konfigurálva.

### <a name="see-also"></a>További információ
[Csak az Intune által támogatott alkalmazások hozzáférésének engedélyezése az O365-szolgáltatásokhoz](allow-policy-managed-apps-access-to-o365.md)

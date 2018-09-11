---
title: Modern hitelesítés nélküli alkalmazások blokkolása az Intune-ban
titleSuffix: Microsoft Intune
description: Modern hitelesítés nélküli alkalmazások blokkolása (ADAL) – ismertető.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a4e4fbc4239941c662166f625de73858f1ef948a
ms.sourcegitcommit: d047a692c798e1fb61ee43a487d6332bce344610
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44058778"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alkalmazásvédelmi szabályzatokat használó alkalmazásalapú feltételes hozzáférés a [modern hitelesítést](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) használó alkalmazásokra épül, ami az OAuth2 implementációja. A legújabb asztali és mobil Office-alkalmazások már modern hitelesítést használnak, de vannak olyan külső gyártótól származó programok és régebbi Office-alkalmazások, amelyek másfajta hitelesítéssel működnek, például alapszintű vagy űrlap alapú hitelesítéssel.

Az ilyen típusú alkalmazásokat így blokkolhatja:

* Állítsa be az ADFS-jogcímszabályokat a nem modern hitelesítési protokollok letiltására. Lépésenkénti útmutatás: 3. forgatókönyv – [Az O365-höz való hozzáférés teljes letiltása a böngészőalapú alkalmazások kivételével](https://technet.microsoft.com/library/dn592182.aspx).
* Az **Exchange és a SharePoint Online** esetében használja az Azure Active Directory feltételes hozzáférést, a SharePoint Online esetében pedig használja a Set-SPOTenant PowerShell-parancsmagot. Részletes útmutatásért lásd: [A SharePoint Online és az Exchange Online beállítása az Azure Active Directoryhoz való feltételes hozzáféréshez](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Az alkalmazásalapú feltételes hozzáférést tilos az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítésével használni. A fentiek közül csak az egyik lehet egyszerre konfigurálva.

### <a name="see-also"></a>Lásd még:
[Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)

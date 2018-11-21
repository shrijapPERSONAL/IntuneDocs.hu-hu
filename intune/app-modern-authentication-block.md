---
title: Modern hitelesítés nélküli alkalmazások blokkolása az Intune-ban
titleSuffix: Microsoft Intune
description: Modern hitelesítés nélküli alkalmazások blokkolása (ADAL) – ismertető.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0b74559eb0914d87daabaaad52902547ae7c08ac
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182040"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazásalapú feltételes hozzáférés az alkalmazásvédelmi szabályzatokkal védett alkalmazások használatával támaszkodjon [modern hitelesítést](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), azaz az OAuth2 implementációja. A legújabb Office asztali és mobil alkalmazások modern hitelesítést használnak. Előfordulhatnak azonban olyan harmadik féltől származó alkalmazások és régebbi Office-alkalmazások, hogy a felhasználó más hitelesítési módszerek, például alapszintű, vagy űrlap alapú hitelesítéssel.

Ezekhez az alkalmazásokhoz való hozzáférés letiltását, javasoljuk, hogy az alábbi módszerek:

* Állítsa be az ADFS-jogcímszabályokat a nem modern hitelesítési protokollok letiltására. Lépésenkénti útmutatás: 3. forgatókönyv – [Az O365-höz való hozzáférés teljes letiltása a böngészőalapú alkalmazások kivételével](https://technet.microsoft.com/library/dn592182.aspx).
* Az **Exchange és a SharePoint Online** esetében használja az Azure Active Directory feltételes hozzáférést, a SharePoint Online esetében pedig használja a Set-SPOTenant PowerShell-parancsmagot. Részletes útmutatásért lásd: [A SharePoint Online és az Exchange Online beállítása az Azure Active Directoryhoz való feltételes hozzáféréshez](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Az alkalmazásalapú feltételes hozzáférést tilos az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítésével használni. A fentiek közül csak az egyik lehet egyszerre konfigurálva.

### <a name="see-also"></a>Lásd még:
[Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)

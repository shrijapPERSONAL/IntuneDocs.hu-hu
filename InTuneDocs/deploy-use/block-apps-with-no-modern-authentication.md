---
title: "Modern hitelesítés nélküli alkalmazások blokkolása | Microsoft Intune"
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
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 5c95cd8510faa437a33ac25d6602a2bcc57c05d5


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)
A Mobilalkalmazás-felügyeleti szabályzatot (MAM CA) használó alkalmazások feltételes hozzáférése a [modern hitelesítést](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) használó alkalmazásokra épül, ami az OAuth2 implementációja. A legújabb asztali és mobil Office-alkalmazások már modern hitelesítést használnak, de vannak olyan külső gyártótól származó programok és régebbi Office-alkalmazások, amelyek másfajta hitelesítéssel működnek, például alapszintű vagy űrlap alapú hitelesítéssel.

Az ilyen típusú alkalmazásokat így blokkolhatja:

* Állítsa be az ADFS-jogcímszabályokat a nem modern hitelesítési protokollok blokkolására. Lépésenkénti útmutatás: 3. forgatókönyv – [Az O365-höz való hozzáférés teljes letiltása a böngészőalapú alkalmazások kivételével](https://technet.microsoft.com/library/dn592182.aspx).

>[!IMPORTANT]
>A MAM feltételes hozzáférést tilos az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítéssel használni. A fentiek közül csak az egyik lehet egyszerre konfigurálva.



### <a name="see-also"></a>További információ
[Csak az Intune által támogatott alkalmazások hozzáférésének engedélyezése az O365-szolgáltatásokhoz](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Dec16_HO2-->



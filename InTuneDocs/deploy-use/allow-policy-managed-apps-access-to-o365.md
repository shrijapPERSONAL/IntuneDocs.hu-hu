---
title: "Alkalmazásalapú feltételes hozzáférés az O365-höz | Microsoft Docs"
description: "Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e55cf608c2e5157feeb40ba20d3988b5b35064db
ms.openlocfilehash: d53cded6670069f10bf645d23ff9a9102bd97539
ms.lasthandoff: 02/25/2017


---

# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Beállíthatja, hogy csak azok a mobilalkalmazások érhessék el az O365-szolgátasokat, amelyek támogatják az Intune-alkalmazásvédelmi szabályzatokat

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az [Intune alkalmazásvédelmi szabályzatainak](protect-apps-and-data-with-microsoft-intune.md) segítségével védheti vállalati adatait az Intune-ban regisztrált és felügyelt eszközökön. Az alkalmazásvédelmi szabályzatokat emellett olyan eszközökön is alkalmazhatja, amelyek **a munkatársak tulajdonában állnak, és amelyek nincsenek az Intune-ban felügyeletre regisztrálva**.  Jóllehet ebben az esetben nem felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védettek legyenek. A MAM és az alkalmazásalapú feltételes hozzáférés segítségével létrehozhat egy olyan szabályzatot, amely csak az Intune alkalmazásvédelmi szabályzatokat támogató mobilalkalmazásokat engedi hozzáférni az O365 szolgáltatásokhoz, például az Exchange Online-hoz.

Például ha csak a **Microsoft Outlook alkalmazást** engedélyezi hozzáférni az Exchange Online-hoz, **blokkolhatja azokat a beépített levelezőalkalmazásokat iOS-en és Androidon**, amelyek nem rendelkeznek az Intune MAM-szabályzatok adatvédelmével, hogy levelezést az **Exchange Online-on** folytathassa.

Az következő ábra azt a folyamatot mutatja be, amelynek alapján az alkalmazásalapú feltételes hozzáférési szabályzatok eldöntik, hogy mikor engedélyezik vagy tiltják le a hozzáférést: ![A hozzáférés megadásáról vagy letiltásáról hozott döntés különféle kritériumainak ábrája ](../media/mam-ca-decision-flow_simple.png).

Az ábrán használt rövidítések leírása:
* **CP**: a Munkahelyi portál alkalmazás
* **AA**: az Azure Authenticator alkalmazás
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Előfeltételek
**Mielőtt** létrehozna egy alkalmazásalapú feltételes hozzáférési szabályzatot, rendelkeznie kell **Enterprise Mobility + Security vagy Azure Active Directory Premium szintű előfizetéssel**, és a felhasználóknak licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/en-us/pricing/details/active-directory/) talál.


## <a name="supported-apps"></a>Támogatott alkalmazások
**Exchange Online**: **Microsoft Outlook** Android és iOS rendszerhez.

Azt, hogy mit tapasztalnak a felhasználók, ha alkalmazásalapú feltételes hozzáférési szabályzattal felügyelt alkalmazást használnak, a [Mire számítson, ha egy alkalmazást a MAM feltételes hozzáféréssel használ?](use-apps-with-mam-ca.md) című cikk nyújt tájékoztatást.


## <a name="next-steps"></a>További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>További információ

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)


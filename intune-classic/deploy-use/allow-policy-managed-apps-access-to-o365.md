---
title: Alkalmazásalapú feltételes hozzáférés az O365-höz
description: Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1f9446da0f553dca29bbfd96b99711c895cd8533
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Beállíthatja, hogy csak azok a mobilalkalmazások érhessék el az O365-szolgátasokat, amelyek támogatják az Intune-alkalmazásvédelmi szabályzatokat

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Az [Intune alkalmazásvédelmi szabályzatainak](protect-apps-and-data-with-microsoft-intune.md) segítségével védheti vállalati adatait az Intune-ban regisztrált és felügyelt eszközökön. Az alkalmazásvédelmi szabályzatokat emellett olyan eszközökön is alkalmazhatja, amelyek **a munkatársak tulajdonában állnak, és amelyek nincsenek az Intune-ban felügyeletre regisztrálva**.  Jóllehet ebben az esetben nem felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védettek legyenek. A MAM alkalmazásalapú feltételes hozzáférés segítségével létrehozhat egy olyan szabályzatot, amely csak az Intune alkalmazásvédelmi szabályzatokat támogató mobilalkalmazásokat engedi hozzáférni az O365 szolgáltatásokhoz, például az Exchange Online-hoz.

Például ha csak a **Microsoft Outlook alkalmazást** engedélyezi hozzáférni az Exchange Online-hoz, **blokkolhatja azokat a beépített levelezőalkalmazásokat iOS-en és Androidon**, amelyek nem rendelkeznek az Intune MAM-szabályzatok adatvédelmével, hogy levelezést az **Exchange Online-on** folytathassa. Azt is megteheti, hogy a **SharePoint Online** elérését blokkolja azon mobilalkalmazások számára, amelyekhez nincs Intune MAM-támogatásuk.

A következő ábra azt a folyamatot mutatja be, amelynek alapján az alkalmazásalapú feltételes hozzáférési szabályzatok eldöntik, hogy mikor engedélyezzék vagy tiltsák a hozzáférést: ![A hozzáférés megadásáról vagy letiltásáról hozott döntés különféle kritériumainak ábrája](../media/mam-ca-decision-flow_simple.png).

Az ábrán használt rövidítések leírása:
* **CP**: a Munkahelyi portál alkalmazás
* **AA**: az Azure Authenticator alkalmazás
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Előfeltételek
**Mielőtt** létrehozna egy alkalmazásalapú feltételes hozzáférési szabályzatot, rendelkeznie kell egy **Enterprise Mobility + Security vagy Azure Active Directory Premium szintű előfizetéssel**, a felhasználóknak pedig licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/pricing/details/active-directory/) talál.


## <a name="supported-apps"></a>Támogatott alkalmazások
**Exchange Online**:
* **Microsoft Outlook** Androidra és iOS-re

**SharePoint Online**
* Microsoft Word iOS-re és Androidra
* Microsoft Excel iOS-re és Androidra
* Microsoft PowerPoint iOS-re és Androidra
* Microsoft OneDrive Vállalati verzió iOS-re és Androidra
* Microsoft OneNote iOS-re

>[!IMPORTANT]
>Androidos eszközökön a kezdeti regisztrációt a OneDrive alkalmazásba vagy az Outlook alkalmazásba való bejelentkezéssel kell elvégezni. Az androidos OneNote alkalmazás még nem támogatja a regisztráció nélküli MAM-használatot.

Az alkalmazásalapú feltételes hozzáférési szabályzattal felügyelt alkalmazás használatához lásd: [Mire számítson, ha egy alkalmazást a MAM feltételes hozzáféréssel használ?](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[SharePoint Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-sharepoint-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Lásd még:

[Alkalmazásadatok védelme alkalmazásvédelmi szabályzatokkal](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

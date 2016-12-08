---
title: "Alkalmazás alapú feltételes hozzáférés az 0365-höz | Microsoft Intune"
description: "Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: e57280821168ddb043d093485ec74f042bbebfef


---

# Beállíthatja, hogy csak azoknak a mobilalkalmazások érhessék el az O365 szolgátasait, amelyek támogatják az Intune MAM-szabályzatokat
Az [Intune mobilalkalmazás-felügyeleti (MAM) szabályzatok](protect-apps-and-data-with-microsoft-intune.md) segítségével védheti vállalati adatait az Intune-ban regisztrált és felügyelt eszközökön. A MAM-szabályzatokat emellett olyan eszközökön is alkalmazhatja, amelyek **a munkatársak tulajdonában állnak, és amelyek nincsenek az Intune-ban felügyeletre regisztrálva**.  Jóllehet ebben az esetben nem felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védettek legyenek. A MAM feltételes hozzáférés (MAM CA) segítségével létrehozhat egy olyan szabályzatot, amely csak az Intune MAM-szabályzatokat támogató mobilalkalmazásokat engedi hozzáférni az O365 szolgáltatásokhoz, például az Exchange Online-hoz.

Például ha csak a **Microsoft Outlook alkalmazást** engedélyezi hozzáférni az Exchange Online-hoz, **blokkolhatja azokat a beépített levelezőalkalmazásokat iOS-en és Androidon**, amelyek nem rendelkeznek az Intune MAM-szabályzatok adatvédelmével, hogy levelezést az **Exchange Online-on** folytathassa.

Az következő ábra azt a folyamatot mutatja be, amelynek alapján a MAM feltételes hozzáférési szabályzatai eldöntik, hogy mikor engedélyezik vagy tiltják le a hozzáférést: ![A hozzáférés megadásáról vagy letiltásáról hozott döntés különféle kritériumainak ábrája ](../media/mam-ca-decision-flow_simple.png).

Az ábrán használt rövidítések leírása:
* **CP**: a Munkahelyi portál alkalmazás
* **AA**: az Azure Authenticator alkalmazás
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## Előfeltételek
**Mielőtt** konfigurálhatna egy MAM feltételes hozzáférés szabályzatot, rendelkeznie kell **Enterprise Mobility + Security vagy Azure Active Directory Premium szintű előfizetéssel**, és a felhasználóknak licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/en-us/pricing/details/active-directory/) talál.


## Támogatott alkalmazások
**Exchange Online**: **Microsoft Outlook** Android és iOS rendszerhez.

Azt, hogy mit tapasztalnak a felhasználók, ha a MAM feltételes hozzáférési szabályzataival felügyelt alkalmazást használnak, a [Mire számítson, ha egy alkalmazást a MAM feltételes hozzáféréssel használ?](use-apps-with-mam-ca.md) című cikk nyújt tájékoztatást.


## További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### További információ

[Alkalmazásadatok védelme MAM-szabályzatok használatával](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->



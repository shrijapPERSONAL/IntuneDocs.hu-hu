---
title: Az Egyesült Államok kormányzati központi telepítések – Microsoft Intune hálózati végpont
titleSuffix: ''
description: Tekintse át az USA kormányzati végpontok az Intune-hoz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a86069b7f4093fb437171d5699df2302fc6fd2a
ms.sourcegitcommit: df413d1786c9aa0f409424c1e9e102bf230bbe39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721696"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Egyesült Államok kormányzati végpontok a Microsoft Intune

Ezen a lapon találhatók az USA kormányzati végpontok az Intune-ban üzemelő szükséges.

Tűzfalak és proxykiszolgálók mögött található eszközök felügyeletére, engedélyeznie kell a kommunikációt az Intune-hoz.

- A proxykiszolgálónak támogatnia kell mind a **HTTP (80)** , mind a **HTTPS (443)** protokollt, mert az Intune-ügyfelek mindkét protokollt használják
- Bizonyos tevékenységek (például a szoftverfrissítések letöltése), az Intune hitelesített proxykiszolgálói hozzáférést igényel a manage.microsoft.com

Proxykiszolgáló beállításai az egyes ügyfélszámítógépeken módosíthatja. A csoportházirend-beállítások segítségével módosíthatja az összes, egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.

A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza:

|**Végpont**|**IP-cím**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Egyesült Államokbeli kormányzati ügyfelek végpontok kapja:
- Az Azure Portalon: https://portal.azure.us/ 
- Office 365: https://portal.office365.us/ 
- Az Intune céges portál: https://portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Partner Szolgáltatásvégpontok, amelyek az Intune-ban függ:
- AAD-szinkronizáló szolgáltatás: https://syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https://login.microsoftonline.us
- Címtár-Proxy: https://directoryproxy.microsoftazure.us/DirectoryProxy.svc
- Az AAD Graph: https://directory.microsoftazure.us és https://graph.microsoftazure.us
- Az MS Graph: https://graph.microsoft.us
- ADRS: https://enterpriseregistration.microsoftonline.us

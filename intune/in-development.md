---
title: A fejlesztés – Microsoft Intune
titleSuffix: ''
description: Fejlesztés a Microsoft Intune-funkciók
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3645d07fe9a703f182e05bc9a7f9fbb93c413ddc
ms.sourcegitcommit: dfcf80a91792715404dc021c8684866c8b0a27e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65816250"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Fejlesztés a Microsoft Intune - 2019. május

Segítség a készültségi és tervezési, ezen a lapon listák Intune felhasználói felület frissíti, és a szolgáltatásokat, fejlesztés alatt állnak, de még nem elérhető. Továbbá:

- Ha várhatóan tovább fogjuk, hogy intézkedjen módosítása előtt kell, tesszük közzé egy kiegészítő Office-Üzenetközpontban post.
- Ha egy szolgáltatás vagy előzetes elindul, éles környezetben, vagy általánosan elérhető, a szolgáltatás leírása áthelyezi ezt oldal ki, majd onnan az [Újdonságok oldalát](whats-new.md).
- Ezen a lapon, és a [Újdonságok oldalát](whats-new.md) rendszeresen frissül. További hírekért látogasson vissza.
- Tekintse meg a [M365 ütemterv](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratégiai le és ütemterveket.

> [!Note]
> Ezek az elemek tükrözik a Microsoft jelenlegi verziójával kapcsolatos elvárások hamarosan egy későbbi kiadásban az Intune funkcióival kapcsolatos. Dátumok és az egyes szolgáltatások változhatnak. Nem minden eleme fejlesztési rendelkeznie a szolgáltatás ezen az oldalon.

**RSS-hírcsatorna**: Értesítés küldése, amikor ezen a lapon frissül, másolása és beillesztése a következő URL-címet a hírcsatorna olvasóba szerint: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon


<!-- 1905 start-->


### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Keresési kulcsszó alapkonfiguráció támogatása  <!-- 3082036         -->
Hozza létre, és a egy biztonsági alapkonfigurációjának profilját szerkeszti, miközben Ön hamarosan, használandó *keresési* szűrése a beállításokat, amelyek jelenjen meg a konzolon.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Alaphelyzetbe állítása és törölni az eszközök tömeges a Graph API-val <!-- 3295288 -->
Láthatja, hogy alaphelyzetbe állítása és a Graph API használatával egyszerre legfeljebb 100 törölhetik.

<!-- 1904 start-->

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Eszköz felhasználók megtekinthetik a már telepített vagy telepíteni próbált minden felügyelt alkalmazás <!-- 2352913 -->
A Windows céges portál felsorolja az összes felügyelt alkalmazások&ndash; egyszerre kötelező és elérhető&ndash; telepített a felhasználó eszközén. Felhasználók tudják próbált nézet és a függőben lévő alkalmazások telepítésére, és azok aktuális állapotát. Ha a szervezet nem, hogy az alkalmazások, kötelező vagy elérhető legyen, a felhasználók látják egy üzenet tájékoztatja, hogy nem vállalati alkalmazások telepítve vannak-e. Felhasználók is elérhetik a rendezését vagy szűrését alkalmazások telepítési állapot szerint.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Ha használja a "alkalmazhatósági szabályok" konfigurációs profilok létrehozása a Windows 10 rendszerű eszköz <!-- 2549910 -->
Windows 10-es eszközkonfigurációs profilok létrehozása (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10-es** tartozó platform). Is elérheti, hozzon létre egy **alkalmazhatósági szabály** , a profil csak egy adott kiadását vagy egy adott verzió érvényes. Például hozzon létre egy profilt, amely lehetővé teszi egy BitLocker-beállítások. Miután hozzáadta a profil, használjon egy alkalmazhatósági szabályt, hogy a profil csak Windows 10 Enterprise rendszert futtató eszközökre vonatkozik.

Érintett kiadások: 
- Windows 10 és újabb



## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



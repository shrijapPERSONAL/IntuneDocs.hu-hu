---
title: A fejlesztés – Microsoft Intune
titleSuffix: ''
description: Fejlesztés a Microsoft Intune-funkciók
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
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
ms.openlocfilehash: 004ebad5276575fe9f5b580d13db188f297424fb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513674"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>A Microsoft Intune - április 2019 fejlesztés alatt

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

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Speciális beállítások a Windows Defender-tűzfal <!-- 1311949 -->
Hamarosan fogja tudni az ügyfeleken a Windows Defender az egyéni tűzfalszabályok kezelése az Intune-nal. Bejövő és kimenő viselkedés, alkalmazások hálózati címek és portok a szabályok határozzák meg. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Alkalmazások védelme feltételes hozzáférés megkövetelése  <!--1634317 -->
Fogja tudni használni *megkövetelése alkalmazásvédelmi szabályzatának*, ami megerősíti, hogy a házirend bejelentkezési meg, hogy a felhasználók hozzáférését az adatok védelme a feltételes hozzáférés befejezése előtt a felhasználó alkalmazása vonatkozik. Miközben házirend garancia lelassíthatják az első használata élményt, azt úgy segít védekezni hálózati problémák, a felügyeleti konfigurációs hibák vagy a szándékos erőfeszítéseket támadók alkalmazásvédelmi szabályzatokat. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Kernel-bővítmények beállítások konfigurálása a macOS-eszközökön <!-- 2043024 -->
MacOS-eszközökön, létrehozhat egy eszközkonfigurációs profilt (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > Válasszon **macOS** tartozó platform). Új beállítások csoportja, konfigurálhatja és az eszközök kernel-bővítmények használata lehetővé teszi.

A következőkre vonatkozik: macOS 10.13.2 és újabb verziók

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Eszköz felhasználók megtekinthetik a már telepített vagy telepíteni próbált minden felügyelt alkalmazás <!-- 2352913 -->
A Windows céges portál felsorolja az összes felügyelt alkalmazások&ndash; egyszerre kötelező és elérhető&ndash; telepített a felhasználó eszközén. Felhasználók tudják próbált nézet és a függőben lévő alkalmazások telepítésére, és azok aktuális állapotát. Ha a szervezet nem, hogy az alkalmazások, kötelező vagy elérhető legyen, a felhasználók látják egy üzenet tájékoztatja, hogy nem vállalati alkalmazások telepítve vannak-e. Felhasználók is elérhetik a rendezését vagy szűrését alkalmazások telepítési állapot szerint.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Ha használja a "alkalmazhatósági szabályok" konfigurációs profilok létrehozása a Windows 10 rendszerű eszköz <!-- 2549910 -->
Windows 10-es eszközkonfigurációs profilok létrehozása (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10-es** tartozó platform). Is elérheti, hozzon létre egy **alkalmazhatósági szabály** , a profil csak egy adott kiadását vagy egy adott verzió érvényes. Például hozzon létre egy profilt, amely lehetővé teszi egy BitLocker-beállítások. Miután hozzáadta a profil, használjon egy alkalmazhatósági szabályt, hogy a profil csak Windows 10 Enterprise rendszert futtató eszközökre vonatkozik.

Érintett kiadások: 
- Windows 10 és újabb

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune-ban biztonsági műveletek a Defender ATP-ben (a nyilvános előzetes verzió) <!-- 3208597 -->
Hamarosan elérhető nyilvános előzetes verzió, az Intune hamarosan új biztonsági tevékenységek a újonnan bejelentett Microsoft Defender fenyegetések és biztonsági rések kezelése.  Ez az integráció biztonsági műveleteket a rendszergazdák a Windows Defender ATP (WDATP) hatékonyabban kommunikálhatnak a javasolt szervizelés újonnan felbukkanó fenyegetésekkel szemben, hogy az Intune-rendszergazdák számára. Biztonsági feladatokat is hozzáadja a kockázatalapú megközelítés felderíteni, rangsorolására és végponti biztonsági rések és konfigurációs hibáinak javítása.

Az Intune-ban biztonsági feladatokkal kapcsolatos további információkért tekintse meg a következő blogbejegyzésben: kapcsolatos [Microsoft Defender ATP fenyegetések és biztonsági rések kezelése Intune-ban biztonsági műveletek segítségével](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>A Windows Defender komplex veszélyforrások elleni védelem alapkonfiguráció <!-- 3754134 -->
Fogunk hozzáadni az új alaptervet úgy, hogy a Windows Defender komplex veszélyforrások elleni védelem beállításainak konfigurálásához nyújtanak segítséget.


### <a name="ios-third-party-keyboards----4111843---"></a>iOS harmadik féltől származó billentyűzetek <!-- 4111843 -->
Az Intune alkalmazásvédelmi szabályzat (alkalmazás) támogatása a **harmadik féltől származó billentyűzetek** beállítás miatt az iOS platform megváltoztatására megszűnik. Nem tudnak konfigurálja ezt a beállítást az Intune felügyeleti konzolon, és nem kényszeríti az Intune App SDK az ügyfélen.

<!-- 1903 start-->

### <a name="windows-update-notifications----3316782---"></a>Windows-frissítési értesítések <!-- 3316782 -->
Azt adja hozzá támogatást a Windows Update kör konfigurációk úgy is elérheti a felhasználók a Windows Update-értesítések beállítása. Ez a beállítás nem lesz elérhető a portálon, de konfigurálható az Intune Graph API használatával.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Könnyebb elérhetőség érdekében a diagnosztikai beállítások <!-- 3804627 -->
Adunk hozzá egy új lehetőség a **Auditnaplók** minden napló számítási az Intune-konzolon, amellyel közvetlenül nyissa meg a panelen a *diagnosztikai beállítások* lap.

## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



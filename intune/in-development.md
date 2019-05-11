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
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910327"
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


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Törölhetne egy eszközt az Apple portálján megjelennek az Intune-portálon <!--2489996 -->
Ha egy eszközt az Apple Device Enrollment Program vagy az Apple üzleti Manager portálok törölnek, az eszköz automatikusan törölve lesz, az Intune-ból a következő szinkronizáláskor.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Keresési kulcsszó alapkonfiguráció támogatása  <!-- 3082036         -->
Hozza létre, és a egy biztonsági alapkonfigurációjának profilját szerkeszti, miközben Ön hamarosan, használandó *keresési* szűrése a beállításokat, amelyek jelenjen meg a konzolon.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Alaphelyzetbe állítása és törölni az eszközök tömeges a Graph API-val <!-- 3295288 -->
Láthatja, hogy alaphelyzetbe állítása és a Graph API használatával egyszerre legfeljebb 100 törölhetik.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>A Windows 10-es eszközök megfelelőségi szabályzatot a TPM lapkakészlet-ellenőrzés <!-- 3617671 -->
Számos Windows 10-es és újabb rendszerű eszközök kell a platformmegbízhatósági modul (TPM) chipkészletekkel. A frissítés egy új megfelelőségi beállítás, amely ellenőrzi a TPM lapka az eszközön lévő verziója tartalmazza. 

[Windows 10-es és újabb megfelelőségi szabályzat beállításai](compliance-policy-create-windows.md#device-security) ismerteti ezt a beállítást.

Érintett kiadások: Windows 10 és újabb

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Az Intune felügyeleti bővítmény PowerShell-parancsprogramok  <!-- 3734186    -->
Fogja tudni tartalomvédelemre konfigurálni PowerShell-parancsfájlok futtatásához a felhasználó rendszergazdai jogosultságokat az eszközön. További információkért lásd: [használja a Powershellt parancsfájlokat az Intune-ban Windows 10 rendszerű eszközökön](intune-management-extension.md).

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Megakadályozza, hogy a végfelhasználók számára a személyes elérési pont módosítása és a bejelentkezés iOS felügyelt eszközök Siri kiszolgáló letiltása <!-- 4097904  --> 
Létrehozhat egy eszközkorlátozási profilt az iOS-eszközön (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus). A frissítés konfigurálható új beállításokat tartalmazza:

- Személyes elérési pont
- Siri server naplózása

A jelenlegi beállítások megtekintéséhez lépjen a [IOS-es beállítások engedélyezett vagy korlátozott funkciók](device-restrictions-ios.md). 

A következőkre vonatkozik: iOS 12.2 és újabb

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Új tanterem alkalmazás eszközkorlátozásokra vonatkozó beállítások a DEP-ban regisztrált macOS-eszközök <!-- 4097905  --> 
Akkor is eszközkonfigurációs profilok létrehozása macOS-eszközök esetén (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **macOS** tartozó platform > **eszközkorlátozások** profiltípus). Ez a frissítés többek között a DEP által regisztrált eszközökre, és letilthatja az iCloud-Fotókönyvtár új osztályterem alkalmazás beállításait.

A jelenlegi beállítások megtekintéséhez lépjen a [engedélyezett vagy korlátozott funkciók az Intune-nal macOS beállításai](device-restrictions-macos.md).

A következőkre vonatkozik: macOS 10.14.4 és újabb

### <a name="android-enterprise-app-management----4459905-idready---"></a>Androidos vállalati Alkalmazáskezelés <!-- 4459905 idready -->
Hogy egyszerűbb legyen a rendszergazdák beállítása és használata az Android Enterprise management, az Intune automatikusan új négy gyakori Android Enterprise kapcsolódó alkalmazásokat az Intune felügyeleti konzolon. A négy Android Enterprise-alkalmazások a következők:

- **[A Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – teljes körűen felügyelt Android Enterprise-forgatókönyvek esetén használatos.
- **[A Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  -segít, jelentkezzen be a fiókok kétfaktoros ellenőrzési használatakor.
- **[Az Intune céges portál](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  – alkalmazás alkalmazásvédelmi szabályzatokat (alkalmazás) és az Android Enterprise munkahelyi profil helyzetekben használatos.
- [Kezdőlap képernyő felügyelt](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – Android Enterprise dedikált/kioszk esetekben használatos.

Korábban a rendszergazdáknak kell manuálisan található, és hagyja jóvá a ezeket az alkalmazásokat a [felügyelt Google Play áruház](https://play.google.com/store/apps) beállítása. Ez a változás eltávolítja azokat korábban manuális lépései könnyebben és gyorsabban az ügyfelek számára az Android Enterprise management használatához.

Rendszergazdák akkor láthatnak, ezeket az automatikusan hozzáadódik az Intune-alkalmazások listájában, hogy először csatlakoznak az Intune-bérlő a felügyelt Google Play időben négy alkalmazásokat. További információkért lásd: [Intune-fiókjához csatlakozhat a felügyelt Google Play fiókjához](connect-intune-android-enterprise.md). A bérlők számára, amely már csatlakoztatva van a bérlő vagy akik már használják Android Enterprise nincs teendője rendszergazdák tennie. Ezeket az alkalmazásokat négy automatikusan megjelenik a 2019. május szolgáltatás bevezetés befejezése után 7 napon belül.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Speciális beállítások a Windows Defender-tűzfal <!-- 1311949 -->
Hamarosan fogja tudni az ügyfeleken a Windows Defender az egyéni tűzfalszabályok kezelése az Intune-nal. Bejövő és kimenő viselkedés, alkalmazások hálózati címek és portok a szabályok határozzák meg. 


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



## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



---
title: Előzetes kiadása – Microsoft Intune
titlesuffix: ''
description: A Microsoft Intune előzetes kiadása
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 8cd32a7ec99064a36d58a5a714406659d9d16675
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55072439"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>A előzetes kiadása – január 2019 a Microsoft Intune

> [!Note]
> NDA-értesítés: A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az itt, nagyon szűk körben megosztott információkra titoktartási szerződés vonatkozik. Az információk egy részletét se tegye közzé közösségi médiában vagy nyilvános webhelyeken, például Twitteren, UserVoice-on, Redditen vagy hasonlón. 

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza, titoktartási szerződés hatálya alatt. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Az információkat ne tweetelje, ne tegye közzé a UserVoice-on, és más módon se ossza meg a vállalatán kívül. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1901 start -->


### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Online licenccel rendelkező Microsoft Store az üzleti alkalmazások telepítése <!-- 1672660  -->
Rendelje hozzá a szükséges online licenccel rendelkező Microsoft Store for Business-alkalmazások az eszköz a környezetben lehet. Központi telepítése a Microsoft Store for Business app így lehetővé teszi az alkalmazásnak, hogy az eszköz összes felhasználójához telepíthetők. Ez a tulajdonság csak a Windows 10 RS4 + asztali eszközökön alkalmazható. Az ügyfélalkalmazások hozzárendelés lapon találhat MSFB Online licencelt alkalmazások telepítésére, az eszköz a környezetben érhető el.


<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise-alkalmazás – hogy az alkalmazás üzembe helyezése <!-- 1171203 -->
Android-eszközökhöz a egy nem regisztrált alkalmazás alkalmazásvédelmi szabályzat regisztráció nélkül (alkalmazás-TUDJUK) a telepítési forgatókönyvben is elérheti, használja a felügyelt Google Play áruházbeli alkalmazások telepítése és ÜZLETÁGI alkalmazások a felhasználók számára. Pontosabban, az informatikai részleg már nem igényel a végfelhasználók számára, hogy lazábbá tehető az eszközeik biztonsági irányelvei, tiltják azáltal, hogy telepítések az ismeretlen forrásból származó alkalmazás katalógus és telepítési élményt nyújt a végfelhasználók számára. Emellett ebben a telepítési forgatókönyvben egy jobb végfelhasználói élményt biztosít.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Az Intune App SDK támogatni fogja a 256 bites titkosítási kulcsok <!-- 1832174 -->
Az Androidhoz készült Intune App SDK 256 bites titkosítási kulcsok fogja használni, ha az alkalmazásvédelmi szabályzatok engedélyezve van a titkosítási. Az SDK továbbra is támogatja a 128 bites kulcsok tartalmat és a régebbi SDK-t használó alkalmazások kompatibilitását.


### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-házirendek frissítése a hitelesítési módszert, és a vállalati portál alkalmazás telepítése  <!-- 1927359 -->
A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök, az Intune már nem támogatja a vállalati portál manuális telepítés a végfelhasználók az app store áruházból. Ez a változás csak akkor jelentősége, amikor Ön az Apple beállítási asszisztens regisztráció során hitelesítsék magukat. Ez a változás csak is hatással van a regisztrált iOS-eszközöket:  
* Az Apple configuratorral
* Apple üzleti vezető
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Ha a felhasználók a vállalati portál alkalmazást az App store áruházból telepítik, és próbálja meg, ezek eszközöket regisztrálni, akkor egy hibaüzenetet fog kapni. Ezek az eszközök csak céges portál használatához, amikor, a leküldött, automatikusan, az Intune-regisztráció során vár. Regisztrációs profilok az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Ha azt szeretné, hogy a DEP-eszközök felhasználói szeretné, hogy a vállalati portálon, szüksége lesz a beállítások megadása egy regisztrációs profilt. Emellett a **az eszköz azonosítására** a céges portál alkalmazás képernyőjén hamarosan elavulttá válnak.  
Is telepíthetik a vállalati portált a DEP-eszközökön már regisztrált, nyissa meg az Intune-nak frissítenie > ügyfélalkalmazások, és küldje le az alkalmazás-konfigurációs házirendek segítségével felügyelt alkalmazásként. A jövőbeli docs részletei elvégezheti ezeket a lépéseket ismerteti.


### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és átkerülnek a saját konfigurációs profil <!-- 3322847 -->
Az Intune-ban a felügyeleti sablonok (**eszközkonfiguráció** > **felügyeleti sablonok**) jelenleg privát előzetes verzióban érhető el. Ez a frissítés: Felügyeleti sablonok az Intune-ban kezelheti körülbelül 300 beállításokat tartalmaz. Korábban ezek a beállítások csak megtalálható a Helyicsoportházirend-szerkesztő.
Felügyeleti sablonok érhetők el a nyilvános előzetes verzióban felügyeleti sablonok helyez át a **eszközkonfiguráció** > **felügyeleti sablonok** való **eszköz konfigurációs** > **profilok** >**profil létrehozása** > a **Platform**, válassza a  **Windows 10 és újabb**, a **profiltípus**, válassza a **felügyeleti sablonok**.
Jelentéskészítés engedélyezve van a következőkre vonatkozik: Windows 10 és újabb

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune-ban macOS céges portálra sötét üzemmód <!-- 3300524 -->
Az Intune-ban macOS céges portálra sötét mód mostantól támogatja a macOS-hez. Sötét üzemmód engedélyezésével 10.14 + macOS-eszközön, a céges portál lehetőség a megjelenését, színek a tükrözés mód.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Az Alkalmazásvédelmi szabályzat (APP) beállításai webes adatokhoz <!-- 2662995 -->
A webes tartalmakra vonatkozó APP szabályzatok beállításait az Android- és iOS-eszközökön is frissítjük, hogy hatékonyabban kezelhetők legyenek a webes http- és https-hivatkozások, valamint az univerzális iOS-hivatkozásokon és Android-alkalmazáshivatkozásokon keresztüli adatátvitel.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Elavult eszközök az eszközmegfelelőségi irányítópulton <!-- 1981119 -->
Egy jövőbeli frissítés eltávolítja az elavult eszközöket az eszközmegfelelőségi irányítópultról. Ez módosítani fogja a megfelelőségi számokat.


## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).




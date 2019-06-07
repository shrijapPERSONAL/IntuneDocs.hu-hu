---
title: A fejlesztés – Microsoft Intune
titleSuffix: ''
description: Fejlesztés a Microsoft Intune-funkciók
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bc5ea7076e77e5071724168fab58fa78f59601c4
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744301"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>A Microsoft Intune-hoz – június 2019 fejlesztés alatt

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

<!-- ***********************************************-->
### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Eszköz felhasználók megtekinthetik a már telepített vagy telepíteni próbált minden felügyelt alkalmazás <!-- 2352913 -->
A Windows céges portál felsorolja az összes felügyelt alkalmazások (kötelező és elérhető), amely a felhasználó eszközén telepítve vannak. Felhasználók tudják próbált nézet és a függőben lévő alkalmazások telepítésére, és azok aktuális állapotát. Ha a szervezet nem, hogy az alkalmazások, kötelező vagy elérhető legyen, a felhasználók látják egy üzenet tájékoztatja, hogy nem vállalati alkalmazások telepítve vannak-e. Felhasználók is elérhetik a rendezését vagy szűrését alkalmazások telepítési állapot szerint.

#### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956---"></a>Az Androidos munkahelyi profil reporting elérhető Google Play alkalmazás <!-- 3041956 -->
Az Android munkahelyi profilos eszközök elérhető alkalmazástelepítések fogja megtekintheti az alkalmazás telepítési állapotát, valamint a felügyelt Google Play-alkalmazások telepített verzióját. További információkért lásd: [alkalmazásvédelmi szabályzatok figyelése](app-protection-policies-monitor.md), [kezelése Android munkahelyi profilos eszközök az Intune-nal](android-enterprise-overview.md) és [alkalmazástípus felügyelt Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Konfigurálhatja a böngésző összekapcsolása a szervezeti adatok használata engedélyezett. <!-- 3145939 -->
Az Intune App Protection házirendek (alkalmazás) Android és IOS rendszerű eszközökön lehetővé teszi, hogy a szervezeti webhivatkozások átvitele adott túl az Intune Managed Browser vagy a Microsoft Edge böngésző.  Alkalmazással kapcsolatos további információkért lásd: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md).

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Alkalmazások lap telepíthető a vállalati portál webhelye  <!-- 4224326 -->
A [céges portál webhely](https://portal.manage.microsoft.com/) felhasználók megjelenítése egy új lap tartalmazza az alkalmazások az eszközön telepített. Ez a lista tartalmazza az elérhető alkalmazások és a szervezet által megkövetelt ezeket az alkalmazásokat. Ezen az oldalon megtekintheti az alkalmazások telepítését és követelmény állapota az eszköz lesz a felhasználók. A céges portál webhely kapcsolatos további információkért lásd: [az Intune céges portál webhelyen](/intune-user-help/using-the-intune-company-portal-website.md) és [a Microsoft Intune vállalati portál alkalmazás konfigurálása](company-portal-app.md).

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Olvasási műveletek a felhasználói hitelesítő adatokat anélkül, hogy a Graph API meghívása <!-- 4655885 -->
Alkalmazásokat fogja tudni olvasási műveletek alkalmazás identitás felhasználói hitelesítő adatok nélkül az Intune Graph API meghívása. További tudnivalókért lásd: [felhasználó nélküli hozzáférést](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### <a name="device-configuration"></a>Eszközök konfigurálása


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Az IKEv2 VPN-profilok támogatása <!-- 1943438 -->
VPN-profilok létrehozása az IOS-es natív VPN-ügyfél az IKEv2 protokoll használatával képes lesz. IKEv2 rendszer az új kapcsolattípus **eszközkonfiguráció** > **profilok** > **profil létrehozása** > **iOS**  tartozó platform > **VPN** profiltípus > **beállítások**.

A VPN-profilok a natív VPN-ügyfél konfigurálásához. Így nem VPN ügyfél alkalmazások telepítésekor vagy leküldve a felügyelt eszközökre. A szolgáltatás használatához szükséges eszközök regisztrálhatók az Intune-ban (MDM-regisztráció).

Tekintse meg az aktuális VPN-beállításokat konfigurálhat, lépjen a [konfigurálása VPN-beállítások iOS-eszközökön a Microsoft Intune-ban](vpn-settings-ios.md).

A következőre vonatkozik: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>Kernel-bővítmények beállítások konfigurálása a macOS-eszközökön <!-- 20430240 -->
MacOS-eszközökön, létrehozhat egy eszközkonfigurációs profilt (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > Válasszon **macOS** tartozó platform). Egy következő frissítés egy új csoportot, amelyek segítségével konfigurálhatja, és a kernel-bővítmények használata az eszközök tartalmazza.

A következőkre vonatkozik: macOS 10.13.2 és újabb verziók

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Keresési kulcsszó alapkonfiguráció támogatása  <!-- 3082036         -->
Hozza létre, és a egy biztonsági alapkonfigurációjának profilját szerkeszti, miközben Ön hamarosan, használandó *keresési* szűrése a beállításokat, amelyek jelenjen meg a konzolon.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Ha használja a "alkalmazhatósági szabályok" konfigurációs profilok létrehozása a Windows 10 rendszerű eszköz <!-- 2549910 -->
Windows 10-es eszközkonfigurációs profilok létrehozása (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10-es** tartozó platform). Is elérheti, hozzon létre egy **alkalmazhatósági szabály** , a profil csak egy adott kiadását vagy egy adott verzió érvényes. Például hozzon létre egy profilt, amely lehetővé teszi egy BitLocker-beállítások. Miután hozzáadta a profil, használjon egy alkalmazhatósági szabályt, hogy a profil csak Windows 10 Enterprise rendszert futtató eszközökre vonatkozik.

Érintett kiadások: 
- Windows 10 és újabb

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Csak beállítás a Windows 10-eszközök áruházból származó alkalmazások további konfigurációs lehetőségeket tartalmazza <!-- 2697002  -->

Amikor létrehoz egy Windows-eszközök eszközkorlátozási profilt, használhatja a **csak áruházból származó alkalmazások** beállítást, így a felhasználók csak telepítik az alkalmazásokat a Windows App Store a (**eszközkonfiguráció**  >  **Profilok** > **profil létrehozása** > **Windows 10 és újabb** tartozó platform > **eszköz korlátozások** profiltípus). Ez a beállítás egy következő frissítés-támogatással kapcsolatos lehetőségekről további kibomlik. 

A jelenlegi beállítások megtekintéséhez lépjen a [Windows 10 (és újabb) eszközbeállítások engedélyezett vagy korlátozott funkciók az Intune-nal](device-restrictions-windows-10.md#app-store).

Érintett kiadások: Windows 10 és újabb

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Több Zebra mobilitási bővítmények eszköz profilok központi telepítése egy eszközön, ugyanazon felhasználói csoporthoz vagy ugyanazon csoporthoz. <!-- 4089955 -->
Az Intune-ban eszközkonfigurációs profil Zebra mobilitási extensions (MX) segítségével testre szabhatja a beállításokat, vagy nem beépített beállítások hozzáadása az Intune-hoz. Jelenleg egy profilt telepíthet egyetlen eszközt. Egy jövőbeli frissítéssel is elérheti a több profilok központi telepítése:

- Az ugyanazon felhasználói csoporthoz
- Az ugyanazon csoporthoz.
- Egy adott eszköz

[Használhatja és kezelheti a Zebra eszközök Microsoft Intune-ban Zebra mobilitási kiterjesztésű](android-zebra-mx-overview.md) bemutatja, hogyan MX használata az Intune-ban.

Érintett kiadások: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Egyes teljes képernyős beállítások iOS-eszközökön "Letiltás", és cserélje le a "Engedélyezése" állítsa be <!-- 4404075  -->
Amikor egy eszközkorlátozási profilt hoz létre az iOS-eszközökön (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus > **teljes képernyős**), beállíthatja a **automatikus zárolás**, **Hangjelzéskapcsoló**, **képernyő elforgatása**, **képernyőalvás gombja**, és **hangerőgombok**. 

Jelenleg ezek a beállítások használatával konfigurálhatók **engedélyezése** (letiltja a szolgáltatást), vagy **nincs konfigurálva** (lehetővé teszi, hogy a szolgáltatás). Egy jövőbeli frissítéssel, az értékek lesznek **blokk** (letiltja a szolgáltatást), vagy **nincs konfigurálva** (lehetővé teszi, hogy a szolgáltatás).

A jelenlegi beállítások megtekintéséhez lépjen a [IOS-es beállítások engedélyezett vagy korlátozott funkciók](device-restrictions-ios.md). 

A következőre vonatkozik: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>Face ID használata az iOS-eszközök jelszó-hitelesítés <!-- 4490704  -->
Amikor létrehoz egy iOS-eszközök eszközkorlátozási profilt, ujjlenyomattal jelszó is használhat. Egy következő frissítés az ujjlenyomat jelszó-beállításokat is lehetővé teszi arcfelismerési (**eszközkonfiguráció** > **profilok** > **profil létrehozása**   >  **iOS** tartozó platform > **eszközkorlátozások** profiltípus > **jelszó**). Ennek eredményeképpen az alábbi beállításokat módosítja:

- **Ujjlenyomattal történő Zárolásfeloldás** mostantól **Touch ID és a Face ID feloldásához**.
- **Ujjlenyomat módosítása (csak felügyelt)** mostantól **Touch ID és a Face ID módosítása (csak felügyelt)** .

Face ID az iOS 11.0-s és újabb verziói. A jelenlegi beállítások megtekintéséhez lépjen a [engedélyezett vagy korlátozott funkciók az Intune-nal IOS-es beállítások](device-restrictions-ios.md#password).

A következőre vonatkozik: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>Alkalmazások a szolgáltatás akkor minősítési régiótól függ, ha csoportkezelést játék és alkalmazás tárolja a funkciókat az iOS-eszközökön <!-- 4593948  -->
Az iOS-eszközökön engedélyezheti vagy korlátozhatja a játékok, az app Store áruházból és dokumentumok megtekintése kapcsolódó funkciókat (**eszközkonfiguráció** > **profilok**  >   **Profil létrehozása** > **iOS** tartozó platform > **eszközkorlátozások** profiltípus > **App Store, dokumentumok megtekintése, játékok**). Azt is beállíthatja a minősítési régiótól, például az Egyesült Államokban. Egy jövőbeli frissítéssel a **alkalmazások** funkció áthelyezi egy gyermeke lehet **minősítési régiótól**, és függ **minősítési régiótól**.

A jelenlegi beállítások megtekintéséhez lépjen a [engedélyezett vagy korlátozott funkciók az Intune-nal IOS-es beállítások](device-restrictions-ios.md#app-store-doc-viewing-gaming).

A következőre vonatkozik: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Csoportházirend-felügyeleti sablonok     <!--  3510695 -->
Felhőbeli eszközök biztonságának javítása érdekében, hogy felügyeleti sablonok, amely lehetővé teszi a Windows rendszerű számítógépekhez jelölje be a csoportházirend-beállítások konfigurálása az Intune-nal adunk ki.  Ezek a sablonok a szabályzat konfigurációs szolgáltató (CSP) használatával legfeljebb 2500 további beállításokat, az Office, a Windows és a onedrive vállalati verzió.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>A Windows biztonsági alapterv új beállításai  <!-- 3534649, 4217151          -->
Új beállításokkal bővítjük a Windows biztonsági alaptervhez. Az első érték a virtualizálás-alapú biztonság, amely a biztonságos rendszerindítás szükséges. A második beállítás lehetővé teszi hangaktiválás Windows-alkalmazások kezelését, ha a képernyő zárolva van.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Biztonsági alapterveket lesz általánosan elérhető  <!--  3785395       -->
A biztonsági előírások funkció hamarosan, előzetes és általánosan elérhető. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>A Windows biztonsági alapterv sablon lesz általánosan elérhető   <!--  3794072       -->
A Windows biztonsági alapterv sablon hamarosan, előzetes és általánosan elérhető. Előzetes verzióját, a sablon kivonjuk a forgalomból, és a egy új sablon elérhető lesz.

<!-- ***********************************************-->
### <a name="device-management"></a>Eszközkezelés

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Hatókörcímkék hozzárendelése egy biztonsági csoportot az összes felügyelt eszköz <!-- 3173810 -->
Jelenleg rendelhet egy hatókörcímkét eszköz minden egyes eszköz menübe **tulajdonságok** lapot, és válassza a hatókörcímkék. Egy következő frissítés is elérheti a hatókörcímkék hozzárendelése egy biztonsági csoportot, és a biztonsági csoportban található összes eszköz is ezeket hatókörcímkék társítva lesz. Ehhez válassza ki a **Intune** > **szerepkörök** > **hatókör (címkék)**  > **létrehozás**  >  **Hatókör (címkék)** > Válassza ki a csoportokat, amelyek a hatókörcímke a hozzárendelni kívánt. A megadott csoportokban szereplő összes eszközre is lesz hozzárendelve a hatókörcímkét. A hatókörcímkék állítsa ezzel a funkcióval, azzal felülírja a hatókörcímkék beállítása a jelenlegi eszköz hatókör címkék flow-val. (Egy jövőbeli frissítéssel, a jelenlegi folyamat hatókörcímkék hozzárendelése eszközökhöz lesz csak olvasható.)

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>A biztonsági javítási szint Android-eszközök esetén lásd: <!-- 4461911  -->
A biztonsági javítási szint az Android-eszközök megtekinthető lesz. Ehhez válassza ki a **Intune** > **eszközök** > **minden eszköz** > Válasszon egy eszközt > **figyelő**  >  **Hardver**.


<!-- ***********************************************-->
## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



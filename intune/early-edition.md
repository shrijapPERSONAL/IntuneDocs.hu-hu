---
title: "Előzetes kiadás"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9a2c104200518af31fd05e6b8abe853377767aa9
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>A Microsoft Intune előzetes kiadása – 2018. március

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Ne ossza meg ezeket az információkat cégen kívüli személyekkel. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
>A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) oldalát.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Több Exchange Connector támogatása <!-- 2070451 -->

Mostantól nem csak egy Microsoft Intune Exchange Connectort használhat bérlőnként. Az Intune hamarosan több Exchange Connector használatát is támogatni fogja, hogy több helyszíni Exchange-szervezetnél állíthassa be az Intune feltételes hozzáférést.

A helyszíni Intune Exchange Connector segítségével annak alapján kezelheti az eszközök helyszíni Exchange-postafiókokhoz történő hozzáférését, hogy az adott eszköz regisztrálva van-e az Intune-ban, és megfelel-e az Intune eszközmegfelelőségi szabályzatainak. Az összekötő beállításához töltse le a helyszíni Intune Exchange Connectort az Azure Portalról, és telepítse egy Exchange-szervezeten belüli kiszolgálón. A Microsoft Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget, majd a **Telepítés** területen kattintson az **Exchange ActiveSync Connector** lehetőségre. Töltse le a helyszíni Exchange Connectort, és telepítse egy Exchange-szervezeten belüli kiszolgálón. Most, hogy már nem csupán egy Exchange Connectort használhat bérlőnként, ugyanezekkel a lépésekkel letöltheti és telepítheti az összekötőt minden további Exchange-szervezethez, ha vannak ilyenek.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Új támogatás az iOS-hez készült Cisco AnyConnect-ügyfélhez<!-- 1333708 -->

Az iOS-hez készült Cisco AnyConnect új VPN-profiljai a Cisco AnyConnect 4.0.7x vagy újabb verzióival működnek. A meglévő iOS Cisco AnyConnect VPN-profiljai a **Cisco Legacy AnyConnect** (Cisco örökölt AnyConnect) nevet kapják, és továbbra is úgy működnek a Cisco AnyConnect 4.0.5x verziójával, mint eddig.

> [!NOTE]
> Ez a változás csak az iOS rendszerre érvényes, az Android, az Android for Work és a macOS rendszerekhez továbbra is csak egy Cisco AnyConnect-lehetőség érhető el. 

#### <a name="more-information"></a>További információ

Az új alkalmazás támogatásához új iOS Cisco AnyConnect VPN-profilt kell létrehoznia, mert az új Cisco AnyConnect és a Cisco Legacy AnyConnect két különböző alkalmazás. Ha saját környezetben kezeli az AnyConnect-ügyfelet, az új Cisco AnyConnect-alkalmazást is üzembe kell helyeznie. Frissítés végrehajtásához törölnie kell a Cisco Legacy AnyConnect VPN-profilt is, továbbá el kell távolítania a Cisco Legacy AnyConnect-alkalmazást. 

A hálózati hozzáférés-vezérlő (NAC) integrációja az eredeti kiadásban nem működik az új AnyConnect-ügyféllel. Jelenleg is dolgozunk a Cisco közreműködésével a NAC-integráció elérhetővé tételén egy későbbi kiadásban.

### <a name="enhanced-jailbreak-detection----846515---"></a>Függetlenítés (jailbreakelés) bővített észlelése <!-- 846515 -->

A függetlenítés (jailbreakelés) bővített észlelése egy új megfelelőségi beállítás, amelynek segítségével az Intune hatékonyabban értékelheti a feltört eszközöket. A beállítás révén az eszköznek gyakrabban, a helyalapú szolgáltatások és az akkumulátor fokozott használatával kell bejelentkeznie az Intune-ba.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Kötelező üzletági (LOB) alkalmazások üzembe helyezésének lehetősége az összes felhasználó számára Windows 10 rendszerű asztali eszközökön <!-- 1627835 RS4 -->
Az ügyfelek eszközkörnyezetben helyezhetik üzembe a kötelező üzletági Windows 10 rendszerű alkalmazásokat. Így az alkalmazások az eszköz összes felhasználója számára elérhetővé válnak. Ez csak Windows 10 rendszerű asztali eszközökre vonatkozik. 

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Lejáró üzletági (LOB) alkalmazások az Intune-ban <!-- 748789 -->
Az Intune az Azure Portalon keresztül értesítést küld a hamarosan lejáró üzletági alkalmazásokról. Az üzletági alkalmazás új verziójának letöltésekor az Intune eltávolítja a lejárati értesítést az alkalmazáslistáról.

### <a name="company-portal-enrollment-improved----1874230--"></a>A Céges portálra történő regisztráció továbbfejlesztése <!-- 1874230-->
A Céges portálon az 1703-as vagy annál újabb verziójú Windows 10 rendszerrel eszközt regisztráló ügyfelek az alkalmazás elhagyása nélkül hajthatják végre a regisztráció első lépését.

### <a name="new-management-name-column----1333586---"></a>Új oszlop Felügyeleti név elnevezéssel <!-- 1333586 -->
Az Eszközök panelen új oszlop jelenik meg, **Felügyeleti név** elnevezéssel. Ez egy automatikusan létrehozott, nem szerkeszthető név, amely az alábbi képlet alapján rendelődik hozzá az egyes eszközökhöz: 
- Az összes eszköz alapértelmezett neve: <username>_<devicetype>_<enrollmenttimestamp>
- Tömegesen hozzáadott eszközökhöz: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime> 
 
Ez egy választható oszlop az Eszközök panelen. Alapértelmezésben nem érhető el, csak az Oszlopválasztó használatával lehet hozzáférni. Az új oszlop nincs hatással az eszköz nevére.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Új beállítások a Windows Defender biztonsági központ értesítő eszközének konfigurációs profilján <!-- 1631906 -->

Három új beállítás jelenik meg a Windows Defender biztonsági központ (WDSC) értesítő eszközének konfigurációs profilján.

A rendszergazdák a következőket tehetik meg:

- Elrejthetik az Azonosítás oszlopot
- Elrejthetik a Hardver oszlopot és annak alárendelt beállításait
- Elrejthetik a Zsarolóvírus oszlopot (OneDrive Vállalati verzió, fájlvisszaállítás)

Ha a WDSC-alkalmazásban elrejtik ezeket az oszlopokat, a végfelhasználók nem tudják konfigurálni ezeket a beállításokat, és az elrejtett összetevőkre vonatkozóan egyetlen értesítés sem jön létre.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Felügyeleti állapoton alapuló, célzott MAM-szabályzatok <!-- 1665993 -->

Célzott MAM-szabályzatokat hozhat létre az eszköz felügyeleti állapota alapján:

- **iOS-eszközök** – nem felügyelt (csak MAM) vagy Intune által felügyelt eszközöket célozhat meg.
- **Android-eszközök** – nem felügyelt és Intune által felügyelt eszközöket, valamint Intune által felügyelt Android Enterprise- (korábban Android for Work-) profilokat célozhat meg.

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Gatekeeper konfigurálása a macOS rendszerű alkalmazásletöltés-források szabályozásához <!-- 1690459-->

Megvédheti eszközeit a kéretlen alkalmazásoktól a Gatekeeper konfigurálásával, amely szabályozza, hogy mely helyekről tölthetők le alkalmazások. A következő letöltésforrásokat konfigurálhatja: **Mac App Store**, **Mac App Store és azonosított fejlesztők**, vagy **Mindenhonnan**. Azt is beállíthatja, hogy a felhasználók telepíthetnek-e alkalmazásokat úgy. hogy a CTRL + kattintás segítségével felülírják a Gatekeeper szabályozásait.

Ezek a beállítások az **Eszközkonfiguráció** -> **Profil létrehozása** -> **macOS** -> **Endpoint protection** területen találhatók meg.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac-alkalmazástűzfal konfigurálása <!-- 1690461 -->

Lehetőség nyílik a Mac-alkalmazástűzfal konfigurálására. Ennek révén alkalmazásonként, és nem portonként szabályozhatja a kapcsolódásokat. Így könnyebb kihasználni a tűzfalvédelem előnyeit, és meggátolni, hogy kéretlen alkalmazások foglalják le az engedélyezett alkalmazások számára megnyitott hálózati portokat.
 
Ez a funkció az **Eszközkonfiguráció** -> **Profil létrehozása** -> **macOS** -> **Endpoint protection** területen található meg.

A Tűzfal beállítás engedélyezése után két stratégia szerint konfigurálhatja a tűzfalat:

- Minden bejövő kapcsolat letiltása

   A megcélzott eszközökön letilthat minden bejövő kapcsolatot. Ha emellett dönt, az összes alkalmazás számára le lesznek tiltva a bejövő kapcsolatok. 

- Egyes alkalmazások engedélyezése vagy letiltása

   A megadott alkalmazások számára engedélyezheti vagy tilthatja a bejövő kapcsolatok fogadását. A rejtett üzemmód engedélyezésével megakadályozhatja a válaszadást az ellenőrzési kérelmekre.
 
#### <a name="more-information"></a>További információ

- Minden bejövő kapcsolat letiltása

   Ez a beállítás megakadályozza, hogy a megosztási szolgáltatások (például a fájlmegosztás és a képernyőmegosztás) bejövő kapcsolatokat fogadjanak. A következő rendszerszolgáltatások továbbra is fogadhatnak bejövő kapcsolatokat:
   - configd – DHCP és más hálózati konfigurációs szolgáltatások megvalósítása
   - mDNSResponder – Bonjour megvalósítása
   - racoon – IPSec megvalósítása

   Megosztási szolgáltatások használata előtt gondoskodjon róla, hogy a **Bejövő kapcsolatok** lehetőség a **Nincs konfigurálva** (és ne a **Letiltás**) értékre legyen beállítva.

- Rejtett üzemmód

   Ha ezt az üzemmódot engedélyezi, a számítógép nem fog válaszolni az ellenőrzési kérelmekre. A számítógép továbbra is válaszol az engedélyezett alkalmazásokhoz tartozó kérelmekre. Az olyan váratlan kérelmeket, mint az ICMP (ping), a rendszer figyelmen kívül hagyja.
 

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciójának frissítése <!--1631531 -->

Az androidos alkalmazások ajánlott eljárásaihoz igazodva hamarosan frissülni fog az Androidhoz készült Céges portál alkalmazás Súgó és Visszajelzés funkciója. Az elkövetkező néhány hónapban az Androidhoz készült Céges portál alkalmazás frissülni fog a **Súgó és Visszajelzés** menüpont két különálló, **Súgó** és **Visszajelzés küldése** menüpontra osztásával. A **Súgó** oldalon egy **Gyakran ismételt kérdések** szakasz és egy **E-mail küldése az ügyfélszolgálatnak** gomb jelenik meg, amellyel a végfelhasználó naplókat tölthet fel a Microsoft részére, és e-mailben írhatja meg a problémát az ügyfélszolgálatnak. A **Visszajelzés küldése** oldal a Microsoft szabványos visszajelzési folyamatán vezeti végig a felhasználót, melynek során a rendszer a „Tetszik”, a „Nem tetszik”, és a „Javaslatom van” választ kínálja fel.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Mennyiségi vásárlási programon (VPP) belül beszerzett e-könyvekhez rendelhető egyéni könyvkategóriák <!-- 1488911 -->
Egyéni e-könyv-kategóriákat hozhat létre, majd hozzájuk rendelheti a mennyiségi vásárlási programon belüli e-könyveket. A végfelhasználók egyaránt látni fogják az újonnan létrehozott e-könyv-kategóriákat és a hozzájuk rendelt könyveket.

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Frissített vizualizációk az Androidhoz készült Céges portálhoz <!--976944 -->

Az Androidhoz készült Céges portál alkalmazás az Android [Material Design](https://material.io/) irányelveihez igazodva frissülni fog. Az új ikonokat az alkalmazás kiadásával egyidőben, az [Újdonságok az alkalmazások felhasználói felületén](whats-new-app-ui.md) című cikkben tesszük közzé. 


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Új regisztrációs hibákat ábrázoló trenddiagram és hibaokokat tartalmazó táblázat <!-- 1471783 -->

Az Enrollment Overview (Regisztráció áttekintése) lapon megtekintheti a regisztrációs hibák trendjét és az öt leggyakoribb hibaokot. A diagramra vagy a táblázatra kattintva hozzáférhet a részletesebb adatokhoz, valamint hibaelhárítási tanácsokat és szervizelési javaslatokat is találhat.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>A Céges portál témáinak testreszabása hexadecimális kódokkal <!--1049561 -->

Hexadecimális kódokkal testreszabhatja a témák színeit a Céges portál alkalmazásaiban. A hexadecimális kód megadásakor az Intune meghatározza a szövegszín és a háttérszín közötti legnagyobb kontrasztot eredményező szövegszínt a [WCAG 2.0 szabványok](http://www.w3.org/TR/WCAG20) alapján. A szöveg színéről és a céges emblémáról is megtekinthet egy-egy előnézeti képet a **Mobilalkalmazások** > **Céges portál** területen. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Új Windows Defender Credential Guard-beállítások az Endpoint Protection-beállításokban <!--1102252 --> 

Az új [Windows Defender Credential Guard] (https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] beállítások az **Eszközkonfiguráció** > **Profilok** > **Endpoint Protection** területén találhatók meg. A következő beállítások lesznek hozzáadva: 

- Platformbiztonsági szint: megadhatja, hogy engedélyezve legyen-e a platformbiztonsági szint a következő újraindításkor. A virtualizálás-alapú biztonsághoz biztonságos rendszerindítás szükséges. A virtualizálás-alapú biztonságot igény szerint a közvetlen memória-hozzáférés (DMA) védelmi funkcióinak használatakor is engedélyezheti. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.
- Virtualizálás-alapú biztonság: megadhatja, hogy engedélyezve legyen-e a virtualizálás-alapú biztonság a következő újraindításkor. 
- Windows Defender Credential Guard: a Credential Guard a virtualizálás-alapú biztonsággal történő együttes bekapcsolásával megvédheti a hitelesítő adatokat a következő újraindításnál, ha a platformszintű biztonság engedélyezve van a biztonságos újraindítás és a virtualizálás-alapú biztonság funkciókkal. Elérhető beállítások: **Letiltva**, **Engedélyezve UEFI-zárolással**, **Engedélyezve zárolás nélkül**, és **Nincs konfigurálva**. 
  - A „Letiltva” beállítás távolról kikapcsolja a Credential Guardot, ha azt korábban bekapcsolta az „Engedélyezve zárolás nélkül” funkcióval.

  - Az „Engedélyezve UEFI-zárolással” beállítással biztosíthatja, hogy a Credential Guard ne legyen letiltható egy beállításkulccsal vagy egy csoportházirenddel. A beállítás használata után a Credential Guard letiltásához a csoportházirendet „Letiltva” állapotra kell állítania, és el kell távolítania a biztonsági funkciókat a jelen lévő felhasználókkal rendelkező számítógépekről a UEFI-ben megőrzött konfigurációk törléséhez. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

  - Az „Engedélyezve zárolás nélkül” beállítással távolról letilthatja a Credential Guardot egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, legalább a Windows 10 1511-es verziójának kell futnia.

  - A „Nincs konfigurálva” beállítás nem definiálja a szabályzatbeállítást. A csoportházirend nem írja a szabályzatbeállítást a beállításjegyzékbe, így ez nincs hatással a számítógépekre vagy a felhasználókra. Ha már meg van adva egy beállítás a beállításjegyzékben, az nem módosul.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Jelszavak visszaállítása Android O-eszközökön <!-- 1238299 -->
A regisztrált Android O-eszközökön visszaállíthatja a jelszavakat. Amikor egy „Jelszó visszaállítása” kérelmet küld egy Android O-eszköznek, az egy új eszközfeloldó jelszót vagy egy kezelt profilra vonatkozó kérdést állít be az aktuális felhasználónak. A jelszó vagy a kérdés attól függ, hogy az eszköz rendelkezik-e profiltulajdonossal vagy eszköztulajdonossal, és azonnal életbe lép.

### <a name="local-device-security-option-settings----1251887---"></a>Helyi eszközbiztonsági beállítások <!-- 1251887 -->
A Windows 10-eszközökön az új Helyi eszközbiztonsági beállításokkal adhat meg biztonsági beállításokat. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Új nyomtatóbeállítások az oktatási profilokban <!-- 1308900 -->

Az oktatási profilok új beállításai a **Nyomtatók** kategória **Nyomtatók**, **Alapértelmezett nyomtató**, **Új nyomtatók hozzáadása** területén érhetők el. 

### <a name="ios-app-provisioning-configuration----1581650---"></a>iOS-es alkalmazáskiépítési konfiguráció <!-- 1581650 -->
iOS-es alkalmazáskiépítési profilok hozzárendelésével, illetve biztonsági csoportok alkalmazásával vagy kizárásával megelőzheti, hogy lejárjanak az alkalmazásai.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Új beállítások a Windows Defender – biztonsági rés kiaknázása elleni védelemhez <!-- 631893 -->

Hat új **Támadási felület csökkentése** beállítás és bővített **Mappahozzáférés felügyelete: Mappavédelem** funkciók érhetők el. Ezeket a beállításokat az alábbi helyen találhatja meg: Eszközkonfiguráció\Profilok\
Profil létrehozása\Endpoint Protection\Windows Defender - biztonsági rés kiaknázása elleni védelem.

#### <a name="attack-surface-reduction"></a>Támadási felület csökkentése

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Zsarolóprogramok elleni speciális védelem|Engedélyezve, Naplózás, Nincs konfigurálva|Zsarolóprogramok elleni agresszív védelem.|
|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése|Engedélyezve, Naplózás, Nincs konfigurálva|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése (lsass.exe).|
|Folyamatlétrehozás a PSExec- és WMI-parancsokból|Tiltás, Naplózás, Nincs konfigurálva|A PSEx-ec és WMI-parancsokból eredő folyamatlétrehozások letiltása.|
|Nem megbízható és aláíratlan, USB-ről futó folyamatok|Tiltás, Naplózás, Nincs konfigurálva|Nem megbízható és aláíratlan, USB-ről futó folyamatok letiltása.|
|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok|Tiltás, Naplózás, Nincs konfigurálva|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok letiltása.|

#### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Mappavédelem (már implementálva)|Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> **Új**<br>Lemezmódosítás letiltása, lemezmódosítás naplózása|
Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Új Windows Defender alkalmazásőr-beállítások <!-- 1631890 -->

- **Grafikus gyorsítás engedélyezése**

A rendszergazdák engedélyezhetik egy virtuális grafikai processzor használatát a Windows Defender alkalmazásőr számára. Ezzel a beállítással a CPU a vGPU-ra terhelheti a grafikai renderelést. Ez javíthatja a teljesítményt a magas grafikai igényű webhelyekkel történő munka, valamint a tárolón belüli videók megtekintése során.

- **SaveFilestoHost**

A rendszergazdák engedélyezhetik a tárolóban futó Microsoft Edge fájljainak a gazdafájlrendszerbe való áttérését. Ennek a beállításnak a bekapcsolásával a felhasználók letölthetik tárolóban futó Microsoft Edge-fájlokat a gazdafájlrendszerbe.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Alkalmazástársítás belefoglalása vagy kizárása Android Enterprise-csoportok alapján <!-- 1813081 -->
Az alkalmazás-hozzárendelések során és a hozzárendelés típusának kiválasztása után az Android Enterprise (korábbi nevén Android for Work) támogatja a kizárás funkciót.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Megfelelőségi szabályzatok alkalmazása eszközcsoportokban lévő eszközökre <!--1307012 -->

Alkalmazhatja majd a megfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználókra. Alkalmazhatja majd a megfelelőségi szabályzatokat eszközcsoportokban lévő eszközökre.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Alkalmazásvédelmi szabályzatok  <!-- 679615 -->
Az Intune alkalmazásvédelmi szabályzatai lehetőséget nyújtanak globális szintű alapértelmezett szabályzatok létrehozására, amelyekkel gyorsan beállítható a megfelelő védelem a teljes bérlő összes felhasználója számára.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS-alkalmazások PIN-kódjának konfigurálása <!-- 1586774 -->
Hamarosan kérhet PIN-kódot a kívánt iOS-alkalmazások használatához. A PIN-kód megkövetelését és napokban megadott lejárati idejét az Azure Portalon konfigurálhatja. Amikor szükséges, a felhasználóknak új PIN-kódot kell beállítaniuk, ha hozzá szeretnének férni egy iOS-alkalmazáshoz. Ezt a funkciót csak az Intune App SDK alkalmazásvédelmével ellátott iOS-alkalmazások támogatják.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->   
Az Azure Active Directory (Azure AD) használatával korlátozhatja majd a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>macOS-felhasználók átirányítása az új Céges portál alkalmazáshoz <!--1380728-->   
Ha egy végfelhasználó bejelentkezik a Céges portál webhelyre, hogy regisztrálja macOS-eszközét, átirányítjuk az új macOS-es Céges portál alkalmazás letöltési oldalára, hogy azzal fejezhesse be a folyamatot. Ez azoknál a macOS-eszközöknél történik meg, amelyek az OS X El Capitan 10.11-es vagy újabb verzióit futtatják. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
Az Android-eszközt használó végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”



## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.



### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



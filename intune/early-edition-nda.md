---
title: Előzetes kiadás
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f21df636ab429969429c6dbdf540daaa67a8f88
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576766"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>A Microsoft Intune előzetes kiadása – 2018. november

> [!Note]
> Titoktartási szerződés hatálya alá tartozó tájékoztatás: A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az itt, nagyon szűk körben megosztott információkra titoktartási szerződés vonatkozik. Az információk egy részletét se tegye közzé közösségi médiában vagy nyilvános webhelyeken, például Twitteren, UserVoice-on, Redditen vagy hasonlón. 

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza, titoktartási szerződés hatálya alatt. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Az információkat ne tweetelje, ne tegye közzé a UserVoice-on, és más módon se ossza meg a vállalatán kívül. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Alkalmazások eltávolítása a céges, felügyelt iOS-eszközökről <!-- 1281677 -->
Ön bármilyen alkalmazást el tud majd távolítani céges, felügyelt iOS-eszközökről. Ha az **Eltávolítás** hozzárendelési típussal megcélozza a felhasználó- vagy eszközcsoportokat, akkor bármilyen alkalmazást el tud távolítani. Személyes és nem felügyelt iOS-eszközök esetében a továbbiakban csak az Intune használatával telepített alkalmazásokat tudja majd eltávolítani.

### <a name="track-installation-of-office-proplus---2620217--"></a>Az Office ProPlus telepítésének nyomon követése <!--2620217-->
A [Beléptetési állapotlapon](windows-enrollment-status.md) nyomon tudja követni az [Office ProPlus](apps-add-office365.md) telepítési folyamatát.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>A macOS-készülékregisztrációs program által biztosított támogatás az Apple School Manager-fiókokhoz <!--3006133-->
Az Intune az Apple School Manager-fiókok esetében támogatást biztosít az készülékregisztrációs program macOS rendszerű eszközökön való használatához.

### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Kioszkmód ideiglenesen szüneteltetése Android-eszközökön a módosítások végrehajtásához <!-- 3041935 -->
Ha többalkalmazásos kioszkmódban használ Android-eszközöket, előfordulhat, hogy a rendszergazdáknak módosításokat kell végrehajtaniuk az eszközön. Új többalkalmazásos kioszkbeállítás, amely segítségével az informatikai rendszergazdák PIN-kód használatával ideiglenesen szüneteltethetik a kioszkmódot, és hozzáférést kaphatnak a teljes eszközhöz.
A jelenlegi kioszkbeállításokat az [Androidos kioszkbeállítások](android-kiosk-settings.md) között ellenőrizheti.

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Egyéni háttér beállítása a Managed Home Screen alkalmazásban  <!-- 3041945 -->
Új beállítás hozzáadásával lehetővé tesszük a Managed Home Screen alkalmazás háttérmegjelenítésének személyre szabását az Android Enterprise rendszerű, többalkalmazásos, kioszkmódú eszközökön.  **Egyéni URL-háttér** konfigurálásához nyissa meg az Azure portalon az Intune > Eszközkonfiguráció elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat a kioszkbeállításainak szerkesztéséhez.

### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Virtuális kezdőképernyő gomb bekapcsolása az Android Enterprise rendszerű kioszkeszközökön  <!-- 3042021 -->
Az új beállítás segítségével a felhasználók az eszközön lévő többfunkciós gombra való koppintással válthatnak a többalkalmazásos kioszkeszközökön található Managed Home Screen alkalmazás és az egyéb hozzárendelt alkalmazások között. Ez a beállítás igen hasznosnak bizonyul olyan esetekben, amikor a felhasználó kioszkalkalmazása nem reagál megfelelően a „vissza” gomb megnyomására. Ezt a beállítást Ön konfigurálni tudja majd az egyetlen célra használható céges Android-eszközökön. A **Virtuális kezdőképernyő gomb** be- és kikapcsolásához válassza az Azure portalon az Intune > Eszközök konfigurálása elemet. Jelöljön ki egy jelenlegi eszközkonfigurációs profilt, vagy hozzon létre újat kioszkbeállításainak szerkesztéséhez.

### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Alkalmazásvédelmi szabályzat-hozzárendelés mentése és alkalmazása <!-- 3104570 -->
Hatékonyabban felügyelheti majd az alkalmazásvédelmi szabályzat-hozzárendeléseket. Ha menti és alkalmazza az alkalmazásvédelmi szabályzat-hozzárendeléseket, kizárólag a kijelölt felhasználókra vonatkozik közvetlenül az adott alkalmazásvédelmi hozzárendelés-szabályzat.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>A Microsoft Edge böngészőhöz tartozó új beállítások Windows 10 és újabb rendszerek esetében <!-- 3174639 -->
Új beállítási lehetőséget vezetünk be, amellyel hatékonyan szabályozhatja és kezelheti a Microsoft Edge böngészőt az eszközein. A jelenlegi beállítások felsorolását az [Eszközkorlátozási beállítások Windows 10-hez (és újabb rendszerekhez)](device-restrictions-windows-10.md#microsoft-edge-browser) cikkben találja.

### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>A Regisztrációs állapotlapon nyomon követett alkalmazások kiválasztása<!-- 2531007 -->
Eldöntheti majd, hogy mely alkalmazások legyenek nyomon követve a Regisztrációs állapotlapon.

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Az Intune alkalmazásvédelmi szabályzataihoz tartozó kezelőfelületre vonatkozó frissítés <!-- 3251427 -->

Az Intune alkalmazásvédelmi szabályzatainak segítségével különböző adatvédelmi beállításokat konfigurálhat az Intune védett alkalmazásain (például a Microsoft Outlookban és Wordben). Az egyértelműség érdekében módosítjuk a beállítás- és gombcímkéket. Az **igen**/**nem** vezérlőket elsődlegesen **tilt**/**engedélyez** és **letilt**/**engedélyez** vezérlőkre módosítjuk majd, és az egyértelműség érdekében a címkéket is frissítjük. A beállításokat is újraformázzuk, így a beállítás és a hozzá tartozó címke egymás mellett szerepel a vezérlőben, hatékonyabbá téve a navigációt. Az alapértelmezett beállítások és a beállítások száma nem változik, azonban e módosításnak köszönhetően a felhasználók könnyebben érthetik meg és használhatják a beállításokat, valamint navigálhatnak közöttük, így segítve a kiválasztott alkalmazásvédelmi szabályzatok alkalmazását.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>A Microsoft által ajánlott beállítások használata a biztonsági előírásokhoz <!-- 2055484 -->
Az Intune integrálható más, biztonsági célú szolgáltatásokkal, például a Windows Defender ATP-vel és az Office 365 ATP-vel. Az ügyfelek a Microsoft 365-szolgáltatásokon átívelő közös stratégiát és összefüggő, teljes körű biztonsági munkafolyamatokat kérnek. Célunk a stratégiák összehangolása és ezáltal olyan megoldások létrehozása, amelyek hidat képeznek a biztonsági műveletek és a gyakori felügyeleti feladatok között. Az Intune-ban ezen cél elérésére a Microsoft által ajánlott „biztonsági előírások” közzétételével törekszünk (**Intune** > **Biztonsági előírások**).  A rendszergazdák így képesek arra, hogy közvetlenül ezekből az előírásokból hozzanak létre biztonsági szabályzatokat, és üzembe helyezzék őket a felhasználók számára. Emellett testreszabhatják az ajánlott eljárásokat a szervezet igényeihez igazítva. Az Intune biztosítja, hogy az eszközök megfeleljenek ezeknek az előírásoknak, és értesíti a rendszergazdákat, ha egy felhasználó vagy eszköz nem felel meg.

### <a name="scope-tags-for-apps---1081941---"></a>Hatókörcímkék alkalmazásokhoz <!--1081941 -->
Hatókörcímkék létrehozásával korlátozhatja a hozzáférést az Intune erőforrásaihoz. Adjon hozzá hatókörcímkét egy szerepkör-hozzárendeléshez, majd adja hozzá a hatókörcímkét egy konfigurációs profilhoz. A szerepkör csak a megfelelő hatókörcímkével rendelkező (vagy hatókörcímke nélküli) erőforrásokhoz férhet hozzá.
Hatókörcímke hozzáadásához válassza az **Intune-szerepkörök** > **Hatókör (Címkék)** > **Létrehozás** lehetőséget.
Hatókörcímke szerepkör-hozzárendeléshez való hozzáadásához válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** > **Hatókör (Címkék)** lehetőséget.
Hatókörcímke konfigurációs profilhoz való hozzáadásához válassza az **Eszközkonfiguráció** > **Profilok** > válasszon egy profilt > **Tulajdonságok** > **Hatókör (Címkék)** lehetőséget.

### <a name="tenant-health-dashboard----1124854---"></a>Bérlőállapot-figyelő irányítópult <!-- 1124854 -->
Az Intune Bérlő állapota oldala egyetlen helyen nyújt információkat a bérlő állapotát illetően. Az oldal 4 szakaszból áll:  
- **Bérlő adatai**: Olyan információkat tartalmaz, mint az MDM-szolgáltató, a bérlőn regisztrált eszközök teljes száma és a licencek száma. Ebben a szakaszban található a bérlő jelenlegi szolgáltatáskiadása is.
- **Összekötő állapota**: Információkat tartalmaz a konfigurált összekötőkről, például az Apple VPP-ről, a Vállalati Windows Store-ról és a tanúsítvány-összekötőkről. Az összekötők az aktuális állapotuk alapján *Kifogástalan*, *Figyelmeztetés* vagy *Nem kifogástalan* jelölést kapnak.
- **Intune-szolgáltatás állapota**: A bérlő aktív incidenseit vagy leállásait tartalmazza. Az ebben a szakaszban szereplő információk közvetlenül az Office Üzenetközpontból ([https://portal.office.com](https://portal.office.com)) származnak.
- **Intune-hírek**: A bérlő aktív üzeneteit tartalmazza, például az arról szóló értesítéseket, ha a bérlő megkapta a legújabb Intune-funkciókat. Az ebben a szakaszban szereplő információk közvetlenül az Office Üzenetközpontból ([https://portal.office.com](https://portal.office.com)) származnak.


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Felhasználói regisztráció nélkül telepített WIP-szabályzatok <!-- 1434452 -->
Windows Information Protection- (WIP-) szabályzatok telepíthetők anélkül is, hogy a felhasználóknak regisztrálniuk kellene Windows 10 rendszerű eszközüket. Ez a konfiguráció lehetővé teszi, hogy a vállalatok biztosítsák a vállalati dokumentumok védelmét a WIP-konfiguráció alapján, miközben a felhasználó saját maga felügyelheti Windows-eszközeit. Ha a dokumentumok védve vannak WIP-szabályzattal, a védett adatokat az Intune-rendszergazdák szelektív módon törölhetik. Ehhez ki kell választaniuk a felhasználót és az eszközt, majd el kell küldeniük egy adattörlési kérést, amelynek hatására WIP-szabályzat által védett összes adat használhatatlanná válik. Ehhez az Azure Portal Intune részén válassza a **Mobilalkalmazás** > **Alkalmazás szelektív törlése** lehetőséget.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Az Alkalmazásvédelmi szabályzat (APP) beállításai webes adatokhoz <!-- 2662995 -->
A webes tartalmakra vonatkozó APP szabályzatok beállításait az Android- és iOS-eszközökön is frissítjük, hogy hatékonyabban kezelhetők legyenek a webes http- és https-hivatkozások, valamint az univerzális iOS-hivatkozásokon és Android-alkalmazáshivatkozásokon keresztüli adatátvitel.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="ios-and-macos-version-numbers-and-build-numbers-are-available-in-compliance-policies----1892471---"></a>Az iOS- és macOS-verziószámok és -buildszámok megfelelőségi szabályzatokban érhetők el <!-- 1892471 -->
Az **Eszközmegfelelőség** > **Eszközmegfelelőség** megjeleníti az iOS és macOS operációs rendszerek verzióit, amelyek elérhetők a megfelelőségi szabályzatokkal. Egy jövőbeli frissítésben a buildszám is konfigurálható majd mindkét platformon.

A biztonsági frissítések megjelenésekor az Apple általában megtartja a verziószámot, de a buildszám változik. A megfelelőségi szabályzat buildszámának segítségével könnyen ellenőrizheti, hogy telepítve van-e a biztonsági frissítés.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Elavult eszközök az eszközmegfelelőségi irányítópulton <!-- 1981119 -->
Egy jövőbeli frissítés eltávolítja az elavult eszközöket az eszközmegfelelőségi irányítópultról. Ez módosítani fogja a megfelelőségi számokat.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Változás a helyszíni összekötők frissítési folyamatában <!-- 2277554 -->
Felhasználói visszajelzések alapján megváltozik a helyszíni összekötők frissítésének folyamata. Miután elvégezte a helyszíni összekötő kezdeti telepítését, a frissítések automatikusan lezajlanak. Ez a változás először a Microsoft Intune-hoz készült új PFX-tanúsítvány-összekötőnél jelenik meg, majd a soron következő további helyszíni összekötőknél is. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>A Configuration Manager megfelelőségének ellenőrzése <!-- 2192052 -->
Egy későbbi frissítés része lesz a System Center Configuration Manager új megfelelőségi beállítása (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Windows 10**). A Configuration Manager megfelelőségi jeleket küldi az Intune-nak. Az Intune beállításával megkövetelhető, hogy minden Configuration Manager-jelre „megfelelő” legyen a válasz.

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ha az eszközön bármelyik program ismeretlen állapotban van, akkor az eszköz nem megfelelőnek fog minősülni az Intune-ban.

A Windows 10 és újabb verziókra vonatkozik

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>VPP-jogkivonatok lejáratára vagy a Céges portál licenceinek alacsony számára vonatkozó riasztások <!-- 2237572 -->
Ha a Volume Purchase Program (VPP) igénybe vételével építi ki a Céges portált a DEP-regisztráció során, az Intune riasztást fog küldeni a VPP-jogkivonat közeli lejáratáról, és ha a Céges portál licencei hamarosan elfogynak.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).




---
title: "Újdonságok a Microsoft Intune-ban"
titleSuffix: Intune on Azure
description: "Az Azure-beli Intune-portál újdonságai"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/01/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c27ce82d10b927fdecec3ea2952376dc7b1f792e
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a [jövőbeni változtatásokról](#whats-coming), a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi verziókról](whats-new-archive.md) is.

> [!Note]
> Idővel ezeknek a funkcióknak egy jelentős része Configuration Managerrel végzett hibrid telepítések esetén is támogatott lesz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   

## <a name="week-of-july-31-2017"></a>2017. július 31-i hét

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 1-->
A [Céges portál webhely](https://portal.manage.microsoft.com) felhasználói felületén számos frissítést hajtottunk végre a végfelhasználói élmény javítása érdekében.

__Továbbfejlesztett alkalmazáscsempék__ A 79x79 pixelnél kisebb alkalmazásikonok mostantól az ikon meghatározó színe alapján automatikusan generált háttérrel jelennek meg. Ez felváltja a szürke kontúrt, amely eddig keretezte a kisméretű ikonokat az alkalmazáscsempén. A nagyobb ikonok mérete úgy módosul, hogy a képminőség megtartása mellett a lehető legjobban kitöltsék az alkalmazáscsempét.

Javasoljuk, hogy a rendszergazdák minimum 120x120 pixeles ikonokkal tegyék közzé az alkalmazásokat.

__Navigációs változások__ A navigációs sáv elemei a bal felső sarokban látható hamburger menübe kerültek át. A Kategóriák lap el lett távolítva. A felhasználók mostantól böngészés közben szűrhetik kategória szerint a tartalmat.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Jobb bejelentkezési élmény a Céges portál alkalmazásokhoz minden platformon <!--User Story 1132123-->

Egy olyan változást jelentünk most be, amely a következő néhány hónapban érkezik, és amellyel javulni fog a bejelentkezési élmény az Intune Céges portál Android, iOS és Windows rendszerű alkalmazásaiban. A Céges portál alkalmazásnál az új felhasználói élmény automatikusan megjelenik minden platformon, miután az Azure AD-ban megjelenik a változtatás. Ezen kívül a felhasználók egy másik eszközről is bejelentkezhetnek a Céges portálba egy egyszeri használtra generált kóddal. Ez különösen akkor hasznos, ha a felhasználónak hitelesítő adatok nélkül kell bejelentkeznie.

Az [Újdonságok az alkalmazás felhasználói felületén](/intune/whats-new-app-ui) témakörben képernyőképeket láthat a korábbi bejelentkezési módról, a hitelesítő adatokat használó új bejelentkezési élményről, és a másik eszközről történő bejelentkezési folyamatról.


## <a name="week-of-july-23rd-2017"></a>2017. július 23-i hét

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Világos és sötét üzemmód választható a Windows 10 rendszerre készült Céges portál alkalmazáshoz <!---676547--->
A végfelhasználók kiválaszthatják a Windows 10 rendszerre készült Céges portál alkalmazás színhasználatát. Ezt a felhasználó a Céges portál alkalmazás Beállítások szakaszában változtathatja meg. A változás az után jelenik meg, hogy a felhasználó újraindítja az alkalmazást. A Windows 10 1607-es és újabb verziói esetén az alkalmazás alapértelmezés szerint a rendszer beállításait használja. A Windows 10 1511-es és korábbi verziói esetén az alkalmazás alapértelmezés szerint a világos üzemmódot használja.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>A végfelhasználók megjelölhetik saját eszközcsoportjukat a Windows 10 rendszerre készült Céges portál alkalmazásban <!---807046-->
A végfelhasználók mostantól közvetlenül a Windows 10 rendszerhez készült Céges portál alkalmazásban címkézhetik meg az eszközt, hogy kiválasszák, melyik eszközcsoporthoz tartozik.

## <a name="week-of-june-26th-2017"></a>2017. június 26-i hét

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Új, szerepköralapú adminisztrációs hozzáférés Intune-rendszergazdáknak <!-- 1099990 -->  
Új, feltételes hozzáférésű rendszergazdai szerepkört vezetünk be az Azure AD feltételes hozzáférési szabályzatainak megtekintéséhez, létrehozásához, módosításához és törléséhez. Korábban csak a globális rendszergazdák és a biztonsági rendszergazdák rendelkeztek ilyen engedéllyel. Mostantól az Intune-rendszergazdák is megkaphatják ezt a szerepköri engedélyt, így ők is hozzáférhetnek a feltételes hozzáférési szabályzatokhoz.


### <a name="device-enrollment"></a>Eszközök beléptetése
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Céges tulajdonú eszközök címkézése sorozatszámmal <!-- 1215070 -->  
Az Intune már támogatja az iOS-, a macOS- és az Android-sorozatszámok feltöltését céges eszközazonosítókként. Jelenleg nem lehet a sorozatszámokat személyes eszközök regisztrálásból való kitiltására használni, mert a rendszer nem ellenőrzi a sorozatszámokat a regisztrálás során. A személyes eszközök sorozatszám alapján történő blokkolása a közeljövőben válik elérhetővé.


### <a name="device-management"></a>Eszközkezelés
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Új távoli műveletek iOS-eszközökhöz <!-- 854689 -->
Ebben a kiadásban két új műveletet tettünk elérhetővé az Apple Osztályterem alkalmazást kezelő megosztott iPad-eszközökkel kapcsolatban:

-   [Aktuális felhasználó kijelentkeztetése](device-logout-user.md) – Kijelentkezteti a kiválasztott iOS-eszköz aktuális felhasználóját.
-   [Felhasználó eltávolítása](device-remove-user.md) – Eltávolítja a kiválasztott felhasználót egy iOS-eszköz helyi gyorsítótárából.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>A megosztott iPadek támogatása az iOS-es Osztályterem alkalmazással <!-- 1044681 -->
Ebben a kiadásban kibővült az iOS-es Osztályterem alkalmazás felügyeletének támogatása, így olyan diákok felügyeletére is van lehetőség, akik a megosztott iPadekre saját felügyelt Apple ID-val jelentkeznek be.


### <a name="app-management"></a>Alkalmazáskezelés  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Beépített Intune-alkalmazásokkal kapcsolatos változások <!-- 1332306 -->

Korábban az Intune számos beépített alkalmazást tartalmazott, melyeket hamar hozzá lehetett rendelni egy kategóriához. A visszajelzések alapján azonban eltávolítottuk ezt a listát, és többé már nem jelennek meg beépített alkalmazások.
Ugyanakkor ha vannak olyan beépített alkalmazások, melyeket korábban már hozzárendelt valamelyik kategóriához, azok továbbra is meg fognak jelenni az alkalmazások listáján. Ezek az alkalmazások szükség szerint továbbra is hozzárendelhetők.
Terveink szerint egy későbbi kiadásban elérhetővé teszünk majd egy egyszerűbb módszert a beépített alkalmazások Intune-portálról történő kiválasztására és hozzárendelésére.

#### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365-alkalmazások egyszerűbb telepítése <!--- 1121362 --->
Az új **Office 365 ProPlus** alkalmazástípus megkönnyíti Office 365 ProPlus 2016-alkalmazásoknak a felügyelt, a Windows 10 legújabb verzióját futtató eszközökhöz rendelését. Emellett lehetőség nyílik a Microsoft Project és a Microsoft Visio telepítésére is, ha rendelkezik hozzájuk való saját licencekkel. A kívánt alkalmazásokat a rendszer összecsomagolja, és azok egyetlen alkalmazásként jelennek meg az Intune-konzol alkalmazáslistájában.
További információt a [Office 365-alkalmazások hozzáadása Windows 10 esetén](apps-add-office365.md) című témakörben talál.


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>A Vállalati Windows Áruházból származó offline alkalmazások támogatása <!--- 777044 --->
A Vállalati Windows Áruházban vásárolt offline alkalmazások mostantól szinkronizálhatók az Intune-portállal. Ezeket az alkalmazásokat eszközcsoportok vagy felhasználói csoportok számára telepítheti. Az offline alkalmazásokat az Intune, és nem az Áruház telepíti.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>A Microsoft Teams mostantól szerepel a jóváhagyott alkalmazások alkalmazásalapú feltételes hozzáférési listáján   <!-- 1257019 -->

Az iOS és Android rendszerű Microsoft Teams mostantól az Exchange és a SharePoint Online alkalmazásalapú feltételes szabályzataihoz tartozó jóváhagyott alkalmazások közé tartozik. Az alkalmazás az Intune App Protection panelen keresztül konfigurálható az Azure Portalon a jelenleg alkalmazásalapú feltételes hozzáférést használó összes bérlőre vonatkozóan.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser- (felügyelt böngésző) és alkalmazásproxy-integráció <!-- 1287310 -->
 Az Intune Managed Browser integrálható az Azure AD alkalmazásproxy szolgáltatásával így az éppen távolról dolgozó felhasználók is elérhetik a belső webhelyeket. A felhasználók a szokásos módon egyszerűen beírják a hely URL-címét a böngésző címsorába, a Managed Browser pedig átirányítja a kérést az alkalmazásproxy webátjárójára. További információ: [Az internet-hozzáférés kezelése felügyelt böngészőszabályzatokkal](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Új alkalmazáskonfigurációs beállítások az Intune Managed Browser alkalmazáshoz <!-- 682951 -->
Ebben a kiadásban további konfigurációs lehetőségekkel bővült az iOS és Android rendszerű Intune Managed Browser alkalmazás. A böngésző alapértelmezett kezdőlapjának és könyvjelzőinek beállítása alkalmazáskonfigurációs szabályzattal is lehetséges.
További információ: [Az internet-hozzáférés kezelése felügyelt böngészőszabályzatokkal](app-configuration-managed-browser.md)




### <a name="device-configuration"></a>Eszközök konfigurálása  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>BitLocker-beállítások a Windows 10-hez  <!-- 951707 -->
A Windows 10 rendszerű eszközök BitLocker-beállításai már új Intune-eszközprofillal is konfigurálhatók. Megkövetelheti például az eszközök titkosítását, és megadhat további, a BitLocker bekapcsolásakor alkalmazandó beállításokat is.
További információ: [Endpoint Protection-beállítások Windows 10 és újabb rendszerű eszközökön](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>A Windows 10-es eszközkorlátozási profil új beállításai <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

Ebben a kiadásban új beállítási lehetőségekkel bővült a Windows 10-es eszközkorlátozási profil, a következő kategóriákban:

-  Windows Defender
-  Mobilhálózati és egyéb kapcsolatok
-  Zárolási képernyő felülete
-  Személyes adatok védelme
-  Keresés
-  Windows Reflektorfény
-  Edge böngésző

További információ a Windows 10 beállításairól: [Windows 10 és újabb rendszerek eszközkorlátozási beállításai](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>2017. június 12-i hét

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Az Androidhoz készült Céges portál alkalmazás mostantól új felhasználói felületet nyújt az alkalmazásvédelmi szabályzatokhoz <!--1305217-->
A felhasználók visszajelzései alapján úgy módosítottuk az Androidhoz készült Céges portál alkalmazást, hogy egy **Céges tartalom elérése** gombot is hozzáadtunk. Ez mentesíti a végfelhasználót attól, hogy az egész regisztrációs folyamaton végig kelljen mennie, ha csak olyan alkalmazásokat kíván elérni, amelyek az Intune mobilalkalmazás-felügyelet egyik funkcióját, az alkalmazásvédelmi szabályzatokat támogatják. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Új menüművelet a Céges portál egyszerű eltávolításához <!--1164569-->
Felhasználói visszajelzések alapján az androidos Céges portál alkalmazásban új menüművelet jelent meg, amellyel a Céges portál eszközről való eltávolítása kezdeményezhető. A művelet megszünteti az eszköz Intune-felügyeletét, így a felhasználó az alkalmazást is eltávolíthatja az eszközről. Ezekről a változtatásokról bővebb információt talál az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) és [Az Android végfelhasználói dokumentációja](/intune-user-help/unenroll-your-device-from-intune-android) témakörökben.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>A Windows 10 alkotói frissítésével való alkalmazás-szinkronizálás fejlesztései <!--676505-->

A Windows 10-es Céges portál alkalmazás automatikusan kezdeményez szinkronizálást alkalmazástelepítési kérésekhez Windows 10 alkotói frissítést (1703-as verziót) futtató eszközök esetén. Ez csökkenti a függőben lévő szinkronizálás során feltorlódó alkalmazástelepítési műveletek számát. Emellett a felhasználók manuálisan is kezdeményezhetnek szinkronizálást az alkalmazásban. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Új interaktív felület a Windows 10-es Céges portálhoz<!---1058938--->

A Windows 10-es Céges portál alkalmazás tartalmazni fog egy interaktív Intune-útmutatót a nem azonosított vagy regisztrált eszközökhöz. Az új útmutató olyan részletes utasításokat tartalmaz, amelyek végigvezetik a felhasználókat a feltételes hozzáférési funkciók azonosításához szükséges Azure Active Directory-regisztrálás és az eszközkezelési funkciókhoz szükséges MDM-regisztrálás lépésein. Az útmutató a Céges portál kezdőlapján lesz elérhető. A felhasználók akkor is használhatják az alkalmazást, ha nem végezték el a regisztrálást és a beléptetést, de így korlátozottan használhatják csak a funkciókat.

Ez a frissítés csak a Windows 10 évfordulós frissítést (1607-es) vagy újabb verziókat futtató eszközökön látható. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

## <a name="week-of-june-5-2017"></a>2017. június 5-i hét

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Általánosan elérhető a Microsoft Intune-konzol és a feltételes hozzáférés rendszergazdai konzolja

Már általánosan elérhető az új Azure-beli Intune rendszergazdai konzolja, valamint a feltételes hozzáférés rendszergazdai konzolja is. Az Azure-beli Intune-nal most már egyetlen és egységes rendszergazdai felületen kezelhető az összes Intune-beli MAM- és MDM-funkció, és mindemellett az Azure AD csoportosítási és célzási képességei is kihasználhatók. Az Azure-beli feltételes hozzáférés az Azure AD és az Intune sokoldalú képességeit teszi elérhetővé egyetlen közös konzolon. Felügyeleti szempontból lényeges, hogy az Azure-platformra való váltásnak köszönhetően most már modern böngészők is használhatók.

A portal.azure.com webhelyen elérhető Azure-konzolon az Intune mostantól az **előzetes** címke nélkül jelenik meg.

Meglévő ügyfeleinknek jelenleg nincs ezzel kapcsolatos teendője, kivéve, ha olyan üzeneteket kaptak az üzenetközpontban, amelyek a csoportok migrálása érdekében bizonyos műveletek elvégzésére kérik őket. Előfordulhat, hogy az üzenetközpontban értesítés tájékoztatja arról, hogy a migrálás hosszabb időt vehet igénybe a mi oldalunkon jelentkező hibák miatt. Továbbra is intenzíven dolgozunk az érintett ügyfelek migrálásának befejezése érdekében.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Továbbfejlesztett alkalmazáscsempék az iOS-es Céges portál alkalmazásban
Frissítettük a kezdőlapon található alkalmazáscsempék megjelenését annak érdekében, hogy a Céges portálhoz beállított márkaszínek jelenjenek meg rajtuk. További információt az [alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) témakörben talál.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Az iOS-es Céges portál alkalmazásban elérhető a fiókválasztó
Akik iOS-es eszközt használnak, a Céges portálba való bejelentkezés után az új fiókválasztót is látni fogják, ha más Microsoft-alkalmazásokba is munkahelyi vagy iskolai fiókjukkal jelentkeznek be. További információt az [alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) témakörben talál.

## <a name="week-of-may-29-2017"></a>2017. május 29-i hét

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Az MDM-szolgáltató módosítása a felügyelt eszközök regisztrációjának törlése nélkül <!--1103950-->

Már anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. A Configuration Manager-konzolon [módosíthatja az MDM-szolgáltatót](/sccm/mdm/deploy-use/change-mdm-authority) a Configuration Manager (hibrid) beállításról Microsoft Intune (önálló) beállításra, vagy fordítva.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Továbbfejlesztett értesítés a Samsung KNOX indítási PIN-kódjaihoz <!--1087143-->
Amikor a végfelhasználóknak a titkosítási megfelelőség céljából be kell állítaniuk egy indítási PIN-kódot a Samsung KNOX rendszerű eszközeiken, a megjelenített értesítés átirányítja őket a Gépház alkalmazás megfelelő menüjébe az értesítésre való koppintáskor.  Korábban az értesítésre való koppintással a végfelhasználó a jelszómódosítási képernyőre került.


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Az Apple School Manager (ASM) támogatása megosztott iPadek esetén <!-- 748864, 770395-->

Az Apple készülékregisztrációs programja helyett az Intune az Apple School Manager (ASM) használatával támogatja az iOS-es eszközök alapértelmezett regisztrációját. ASM típusú beléptetésre van szükség a megosztott iPadek Osztályterem alkalmazásának használatához, valamint az adatok Microsoft School Data Sync (SDS) szolgáltatáson keresztüli szinkronizálásához az ASM és az Azure Active Directory között. További információ: [iOS-eszközök regisztrációjának engedélyezése az Apple School Manager-ben](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Ahhoz, hogy megosztott iPadeket konfigurálhasson az Osztályterem alkalmazáshoz, szükség van az iOS oktatási funkcióinak konfigurálására, ami jelenleg nem elérhető az Azure-ban.  Ezt a funkciót hamarosan elérhetővé tesszük.

### <a name="device-management"></a>Eszközkezelés

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Távsegítség Android-eszközökhöz a TeamViewerrel <!-- 675418 -->

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani az androidos eszközök felhasználóinak. További információt a [Távsegítség nyújtása az Intune által felügyelt Android-eszközökhöz](device-profile-android-teamviewer.md) témakörben talál.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>A MAM szolgáltatás alkalmazásvédelmi szabályzatainak új feltételei <!-- 679864 -->

A nem regisztrált felhasználókra vonatkozóan olyan követelményeket állíthat be a MAM szolgáltatásban, amely az alábbiakat írja elő:

- Az alkalmazás minimális verziószáma
- Az operációs rendszer minimális verziószáma
- A megcélzott alkalmazás minimális Intune App SDK-verziószáma (csak iOS)

A funkció Androidon és iOS-en egyaránt elérhető. Az Intune támogatja az operációs rendszerek, az alkalmazások és az Intune App SDK minimális verziószámának kényszerítését. Az integrált SDK-val rendelkező iOS-es alkalmazások az SDK szintjén állíthatják be a minimális verziószám kényszerítését. A felhasználó nem fog tudni hozzáférni a megcélzott alkalmazáshoz, ha az alkalmazásvédelmi szabályzat minimális követelményei a fenti három szinten nem teljesülnek. Ilyenkor a felhasználó eltávolíthatja a fiókját (többszörös identitást használó alkalmazások esetén), bezárhatja az alkalmazást, vagy frissítheti az operációs rendszert vagy az alkalmazást.

További beállítások konfigurálásával nem zavaró értesítésben lehet javasolni a felhasználóknak az operációs rendszer vagy az alkalmazás frissítését. Az ilyen értesítéseket be lehet zárni, és az alkalmazás a megszokott módon használható.

További információt [Az iOS-es alkalmazásfelügyeleti szabályzat beállításai](app-protection-policy-settings-ios.md) és [Alkalmazásvédelmi szabályzatok androidos beállításai](app-protection-policy-settings-android.md) témakörökben talál.

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Alkalmazáskonfigurációk beállítása az Android for Workhöz <!-- 621621 -->
Néhány áruházból származó androidos alkalmazás támogatja a felügyelt konfigurációs lehetőséget is, amellyel a rendszergazda meghatározhatja, hogyan fusson az alkalmazás a munkahelyi profilban. Az Intune most már lehetővé teszi, hogy megnézhesse az alkalmazás által támogatott konfigurációs lehetőségeket, amelyeket az Intune-portálon egy konfigurációtervezővel vagy JSON-szerkesztővel meg is változtathat. További információt az [Alkalmazáskonfigurációk használata Android for Workhöz](app-configuration-policies-use-android.md) témakörben talál.

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Új alkalmazáskonfigurációs lehetőség a regisztráció nélküli MAM-hoz <!-- 677969 -->

Mostantól a regisztráció nélküli MAM csatornáján keresztül is létrehozhat alkalmazáskonfigurációs szabályzatokat. Ez a funkció megegyezik a mobileszköz-kezelési (MDM) alkalmazáskonfigurációnál elérhető alkalmazáskonfigurációs szabályzatok funkciójával. A regisztráció nélküli MAM-ot használó alkalmazáskonfigurációra [Az internet-hozzáférés Managed Browser-szabályzatokkal való kezelése a Microsoft Intune-ban](app-configuration-managed-browser.md) című témakörben talál példát.

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Engedélyezett és letiltott URL-címek meghatározása a Managed Browser számára <!-- 682960 -->

Mostantól konfigurálható engedélyezett és letiltott alkalmazások URL-jeinek listája az Intune Managed Browser számára. Ehhez az Azure Portal alkalmazáskonfigurációs beállításait használhatja. Ezt a beállítást attól függetlenül lehet konfigurálni, hogy az felügyelt vagy nem felügyelt eszközön van-e használatban. További információkért lásd: [Az internet-hozzáférés kezelése Managed Browser-szabályzatokkal a Microsoft Intune-ban](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Alkalmazásvédelmi szabályzatok segélyszolgálati megtekintése <!-- 1069473 -->

Az informatikai segélyszolgálat felhasználói mostantól a Hibaelhárítás panelen ellenőrizhetik a felhasználói licencek állapotát és felhasználókhoz rendelt és alkalmazásvédelmi szabályzatokkal kezelt alkalmazások állapotát. További részleteket a [Hibaelhárítás](./help-desk-operators.md) témakörben talál.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Webhelylátogatások felügyelete iOS-eszközökön <!-- 723832 -->

Mostantól az alábbi két módszer valamelyikével szabályozhatja, hogy az iOS-es eszközök felhasználói mely webhelyeket nyithatják meg:

- Engedélyezett és letiltott URL-ek megadása az Apple beépített webtartalomszűrőjével

- Csak a megadott webhelyek elérésének engedélyezése a Safari böngészőnek. Minden megadott webhelyhez könyvjelző jön létre a Safariban.

További információt a [Webtartalomszűrő beállításai iOS-eszközökön](web-content-filter-settings-ios.md) témakörben talál.

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Az Android for Work-alkalmazások eszközengedélyeinek előzetes konfigurálása <!-- 621614 -->

Az Android for Work-eszközök munkahelyi profiljába telepített alkalmazások esetén konfigurálni lehet az egyes alkalmazások engedélyezési állapotát.  Alapértelmezés szerint az eszközengedélyeket (például hozzáférés a tartózkodási hely adataihoz vagy az eszköz kamerájához) megkövetelő androidos alkalmazások felszólítják a felhasználókat az engedélyek elfogadására vagy elutasítására.  Például ha egy alkalmazás az eszköz mikrofonját használja, a rendszer felszólítja a végfelhasználót, hogy adjon engedélyt az alkalmazásnak a mikrofon használatára. Ezzel a funkcióval engedélyeket határozhat meg a végfelhasználó nevében.  Az engedélyeket háromféleképpen konfigurálhatja: a) automatikus elutasítás a felhasználó értesítése nélkül, b) automatikus jóváhagyás a felhasználó értesítése nélkül, valamint c) a felhasználó elfogadásra vagy elutasításra való felszólítása. További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Alkalmazásspecifikus PIN-kód meghatározása Android for Work-eszközökön <!-- 728976, 1102534 -->

A munkahelyi profillal rendelkező, Android for Work-eszközként kezelt Android 7.0 vagy újabb rendszerű eszközök esetén a rendszergazda meghatározhat egy olyan PIN-kód-szabályzatot, amely csak a munkahelyi profilba telepített alkalmazásokra vonatkozik.  A lehetőségek a következők:

- Eszközre érvényes PIN-kód-szabályzat meghatározása – a felhasználónak ezt a PIN-kódot kell használnia az eszköz feloldására.
- Munkahelyi profilra érvényes PIN-kód-szabályzat meghatározása – a rendszer a PIN-kód megadását kéri a felhasználótól a munkahelyi profilban található bármely alkalmazás megnyitásakor.
- Eszközre és munkahelyi profilra egyaránt érvényes szabályzat meghatározása – a rendszergazdának lehetősége van eszközre és munkahelyi profilra egyaránt érvényes, különböző erősségű PIN-kód-szabályzat meghatározására (például 4 számjegyből álló PIN-kód az eszköz feloldásához, illetve 6 számjegyből álló PIN-kód a munkahelyi alkalmazások megnyitásához).

További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

> [!NOTE]
> Ez a funkció csak Android 7.0 vagy újabb rendszereken érhető el.  Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy dönthet úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használja.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Új beállítások Windows 10-es eszközök esetén <!-- 978585 -->

Újabb [windowsos eszközkorlátozási beállításokat](device-restrictions-windows-10.md) vezettünk be, amelyek a vezeték nélküli kijelzőkhöz, az eszközfelderítéshez, a feladatváltáshoz vagy a SIM-kártyák hibaüzeneteihez hasonló szolgáltatásokat szabályoznak.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Újdonságok a tanúsítványkonfigurációban <!-- 918991 and 823198 -->

SCEP-tanúsítványprofil létrehozásakor iOS, Android és Windows-eszközök esetén a **Tulajdonos nevének formátuma** beállításnál az**Egyéni** lehetőség is választható. A jelen frissítés előtt az **Egyéni** mező csak iOS-eszközök esetén volt elérhető. További információért lásd: [ SCEP-tanúsítványprofil létrehozása] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

PKCS-tanúsítványprofil létrehozásakor a **Tulajdonos alternatív neve** értékeként az **Egyéni Azure Ad-attribútum** lehetőség is választható. Az **Egyéni Azure Ad-attribútum** kiválasztásakor a **Részleg** lehetőség is megjelenik. További információért lásd: [PKCS-tanúsítványprofil létrehozása] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Több alkalmazás konfigurálásra teljes képernyős módban való futtatáshoz Android-eszközön <!-- 662059 -->

Korábban csak egy alkalmazást lehetett úgy konfigurálni, hogy az Android-eszközön teljes képernyős módban fusson. Mostantól több alkalmazás is konfigurálható így az alkalmazásazonosító vagy az áruházi URL-cím használatával, de kiválasztható egy már felügyelt Android-alkalmazás is. További információt [A teljes képernyős mód beállításai](device-restrictions-android.md#kiosk) témakörben talál.


## <a name="notices"></a>Értesítések

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Frissített IP-címek az Intune-hoz <!-- 1175274 -->

A tűzfal proxybeállításaihoz [DNS-nevek és IP-címek frissített listája](/intune/network-bandwidth-use) érhető el.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Feltételes hozzáféréshez használható az Azure Active Directory <!-- 967947 -->

Az Azure-konzol Azure Active Directory szakaszában elérhető a feltételes hozzáférés, amellyel hatékonyan és rugalmasan állíthatók be szabályzatok olyan felhőalkalmazásokhoz, mint az Office 365, az Exchange Online vagy a SharePoint Online.  A klasszikus Intune-konzol helyett most már az **Azure Active Directory feltételes hozzáférés** paneljén konfigurálhatja a szabályzatokat. A klasszikus Intune-konzolon meglévő szabályzatokat újra létre kell hozni az Azure-konzolon. További információt az [Azure AD feltételes hozzáférési szabályzatok létrehozása](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview) témakörben talál.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el az Azure Portal, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök

A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat az új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune/role-based-access-control).

## <a name="whats-coming"></a>Mi várható?

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 2-->

__Kiemelt alkalmazások frissítései__ A webhelyhez hozzáadtunk egy dedikált oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszán. A változásokat megtekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) oldalon.

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171127, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még október eleje előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Platformtámogatási emlékeztető: a Windows Phone 8.1 alapvető technikai támogatása 2017. július 11-én megszűnik
<!-- 1327781 -->

2017. július 11-én a Windows Phone 8.1 platform alapvető technikai támogatása lejár. A Windows 8.1 PC támogatását ez nem érinti.

Az Intune szolgáltatás által felügyelt Windows Phone 8.1-es eszközökre nézve ennek nincs közvetlen következménye. A regisztrált eszközök tovább használhatók, és minden szabályzat, konfiguráció és alkalmazás is az elvárt módon működik tovább. Fontos, hogy nincsenek az Intune szolgáltatás körébe tartozó Windows Phone 8.1 platformot és a Windows Phone 8.1 Vállalati portál alkalmazást érintő fejlesztések.

Javasolt az arra jogosult Windows Phone 8.1 eszközöket a lehető leghamarabb a Windows 10 mobil verziójára frissíteni. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Az Intune iOS-es Vállalati portál alkalmazás támogatásának változásai  <!-- 1164474  -->


A közeljövőben megjelenik az iOS-es Microsoft Intune Vállalati portál alkalmazás egy új verziója, amely csak az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. A Vállalati portál iOS 8-at támogató verziója nagyon rövid ideig még elérhető marad. Ugyanakkor vegye figyelembe, hogy ha MAM-használatot támogató iOS-alkalmazásokat is használ, akkor az iOS 9.0-s és újabb verzióit támogatjuk, ezért ajánlatos gondoskodni róla, hogy a végfelhasználók a legfrissebb operációs rendszert használják. 

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Mindezt azért tudatjuk előre a pontos dátumok ismerete nélkül, hogy legyen ideje tervet készíteni. Gondoskodjon róla, hogy a felhasználók frissítsenek legalább iOS 9.0 rendszerre, és követelje meg, hogy a Vállalati portál alkalmazást is frissítsék, amikor az megjelenik.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?

Javasolja a felhasználóinak, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 9.0 rendszerre.  Javasolja a felhasználóknak a Vállalati portál új verziójának telepítését, hogy kihasználhassák az általa kínált új funkciókat.

Nyissa meg az Intune-t az Azure Portalon, és az Eszközök -> Minden eszköz alatt az iOS verziójára szűrve gyűjtse ki az iOS 9-nél korábbi operációs rendszert futtató eszközöket.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Készüljön fel a változásra: megváltozik az Intune Partner Portal <!-- 1050016 -->

A 2017. május közepén esedékes szolgáltatásfrissítés keretében eltávolítjuk az Intune Partner lapot manage.microsoft.com-ról.  

Ha Ön partneradminisztrátor, akkor a továbbiakban nem lesz lehetősége az Intune Partner lapon megnézni partnereit és intézkedni a nevükben. Ehelyett a Microsoft két másik partnerportáljának valamelyikére kell majd bejelentkeznie.

A [Microsoft Partnerközpontban](https://partnercenter.microsoft.com/) és a [Microsoft Office 365 Felügyeleti partnerközpontban](https://portal.office.com/) egyaránt bejelentkezhet az Ön által felügyelt ügyfélfiókokba. A továbbiakban partnerként ezeken a webhelyeken felügyelheti ügyfeleit.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->

Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja.

Az új ATS-követelményeket érvényesítő Apple TestFlight alkalmazásban elérhetővé vált a Céges portál alkalmazás iOS rendszerű verziója. Ha szeretné kipróbálni az alkalmazást az ATS-megfelelőség tesztelése céljából, küldje el a kereszt- és vezetéknevét, az e-mail-címét és a munkahelye nevét a <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> e-mail-címre. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [A Céges portál felhasználói felületének újdonságai](whats-new-app-ui.md)
* [Korábbi hónapok újdonságai](whats-new-archive.md)

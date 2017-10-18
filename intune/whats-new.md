---
title: "Újdonságok a Microsoft Intune-ban"
titlesuffix: Azure portal
description: "Az Azure-beli Intune-portál újdonságai"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bc322567505506f63e2eb002fd330fc151bc70d
ms.sourcegitcommit: 6004fe51e3cee6fb34514ed0d56e20587ecafeb4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/17/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a [jövőbeni változtatásokról](#whats-coming), a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi verziókról](whats-new-archive.md) is.

> [!Note]
> Idővel ezeknek a funkcióknak egy jelentős része Configuration Managerrel végzett hibrid telepítések esetén is támogatott lesz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-2-2017"></a>2017. október 2-i hét

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>A Céges portál eszközbeállítási munkafolyamatával kapcsolatos újdonságok <!--1490692-->
Továbbfejlesztettük az androidos Céges portál alkalmazás eszközbeállítási munkafolyamatát. Nyelvezete felhasználóbarátabb, vállalatra szabottabb. Képernyőit – ahol lehetett – összevontuk. Az újításokat megtekintheti a [ felhasználói felület újdonságait](whats-new-app-ui.md#week-of-october-2-2017) bemutató oldalon.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Az androidos eszközök kapcsolati információk elérésére irányuló kéréseinek továbbfejlesztett támogatása <!--1484985-->

Gyakran előfordul, hogy a felhasználóknak engedélyt kell adniuk az androidos Céges portál alkalmazásnak a Kapcsolatok használatára. Ha ezt egy végfelhasználó elutasítja, mostantól egy alkalmazásbeli értesítés fogja figyelmeztetni feltételes hozzáférési engedély megadására. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Biztonságos indítást támogató kockázatcsökkentés Android-eszközökhöz<!--1490712-->

Az Android-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>További leküldéses értesítések az Android Oreo rendszert használó végfelhasználóknak a Céges portál alkalmazásban <!--1475932-->

A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy az Android Oreo Céges portál alkalmazása mikor végez háttérműveleteket (például szabályzatok lekérése az Intune szolgáltatástól). Ez átláthatóbbá teszi a végfelhasználók számára a Céges portál az eszközeiken végzett felügyeleti feladatait. Ez a [Céges portál felhasználói felülete optimalizálásának](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) része, amelyet az Android Oreo rendszeren futó Céges portál alkalmazáshoz végzünk. 

Az Android Oreóban engedélyezett új felhasználóifelület-elemekhez további optimalizálások tartoznak.  A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy a Céges portál mikor végez háttérműveleteket, például szabályzatok lekérését az Intune szolgáltatástól.  Ez átláthatóbbá teszi a végfelhasználók számára, hogy a Céges portál mikor hajt végre felügyeleti feladatokat az eszközön.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Munkahelyi profillal rendelkező Androidhoz készült Céges portál alkalmazás új működési módja <!---1485783--->

Android for Work-eszköz munkahelyi profillal történő regisztrálása után a munkahelyi profil Céges portál alkalmazása végzi el az eszközön a felügyeleti feladatokat. 

Hacsak nem használ MAM-használatot támogató alkalmazást a személyes profilban, az androidos Céges portál alkalmazásra már nincs szükség. Ezért a munkahelyi profil hatékony használhatósága érdekében a munkahelyi profil sikeres regisztrálása után az Intune elrejti a személyes Céges portál alkalmazást.

Az Androidhoz készült Céges portál alkalmazás a személyes profilban bármikor engedélyezhető. Ehhez keresse meg a [Céges portál alkalmazást a Play Áruházban](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal), és koppintson az **Engedélyezés** lehetőségre.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>A Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál fenntartási módba kerül <!--1428681-->

2017 októberétől a Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál alkalmazás fenntartási módba kerül. Ez azt jelenti, hogy ezeken a platformokon továbbra is jár támogatás az alkalmazásokhoz és a meglévő használati forgatókönyvekhez (például regisztrálás és megfelelőség). Az alkalmazások továbbra is letölthetők a meglévő kiadási csatornákon keresztül, például a Microsoft Áruházból. 

A fenntartási módban ezekhez az alkalmazásokhoz azonban már csak fontos biztonsági frissítések lesznek elérhetőek. Más típusú frissítések és új funkciók már nem jelennek meg ezekhez az alkalmazásokhoz. Ha az új funkciókat szeretné használni, azt javasoljuk, hogy frissítse az eszközt Windows 10 vagy Windows 10 Mobile rendszerre. 

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Nem támogatott Samsung Knox-eszközök regisztrációjának letiltása<!--- 1490695 --->

A Céges portál alkalmazás csak a támogatott Samsung Knox-eszközöket próbálja meg regisztrálni. Az MDM-regisztrációt megakadályozó KNOX-aktiválási hibák elkerülése érdekében az alkalmazás csak a [Samsung által közétett eszközlistán](https://www.samsungknox.com/knox-supported-devices/knox-workspace) szereplő eszközöket próbálja meg regisztrálni. Előfordulhat, hogy egy Samsung-eszköz bizonyos modelljei támogatják a KNOX platformot, míg más modelljei nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse a viszonteladóval, hogy az eszköz Knox-kompatibilis-e. Az ellenőrzött eszközök teljes listája megtalálható az [Android és Samsung KNOX Standard-eszközök konfigurációs szabályzatának beállításai](/intune-classic/android-policy-settings-in-microsoft-intune.md#supported-samsung-knox-standard-devices) témánál.

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171126, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Végfelhasználók tájékoztatása a regisztrált eszközök megtekinthető adatairól <!--1165314-->
A Céges portál alkalmazások Eszköz részletei képernyője kiegészül a **Tulajdonjog típusa** oldallal. Így a felhasználók közvetlenül a [Milyen adatok láthatók a cég számára?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) című cikkből fognak tudni tájékozódni az adatvédelmi kérdésekről. Ez terveink szerint az összes Céges portál alkalmazásban meg fog jelenni a közeljövőben. Az iOS kapcsán ezt a funkciót [szeptemberben](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) jelentettük be. 


## <a name="week-of-september-25-2017"></a>2017. szeptember 25-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="intune-supports-ios-11---1428975--"></a>Az Intune támogatja az iOS 11-et<!--1428975-->
Az Intune támogatja az iOS 11-et. Ezt korábban bejelentettük az [Intune támogatási blogjának](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) oldalán.

### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!---1164477--->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. 

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>A Windows 10-es Céges portál alkalmazásban elérhetővé válik a Frissítés művelet <!--1132468-->

A Windows 10-es céges portál alkalmazásban lehetőség lesz az adatok frissítésére. Ezt lefelé húzással, vagy asztali gépeken az F5 billentyű megnyomásával lehet majd elvégezni.

## <a name="week-of-september-11-2017"></a>2017. szeptember 11-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Végfelhasználóknak szóló információ az iOS-eszközök megtekinthető adatairól <!--739894-->

Az iOS-alapú Céges portál alkalmazásban található Eszköz részletei képernyőhöz hozzáadtuk a **Tulajdonjog típusa** oldalt. A felhasználók így közvetlenül az Intune végfelhasználói dokumentáció ezen oldaláról tájékozódhatnak az adatvédelemről. A tudnivalókat az About (Információk) képernyőről is elérhetik.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Az Android rendszerre készült Céges portál alkalmazás regisztráció nélküli elérésének engedélyezése végfelhasználók számára <!---1169910--->

A végfelhasználóknak rövidesen mát nem kell regisztrálniuk az eszközüket az Android rendszerre készült Céges portál alkalmazás eléréséhez. Az alkalmazásvédelmi szabályzatokat használó szervezetek végfelhasználói többé nem fognak az eszközük regisztrálására felszólító figyelmeztetést kapni a Céges portál alkalmazás megnyitásakor. A végfelhasználók alkalmazásokat is tudnak majd telepíteni a Céges portálról az eszköz regisztrálása nélkül. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Egyszerűbb megfogalmazás az Androidhoz készült Céges portál alkalmazáshoz <!---1396349--->  

Egyszerűsítettük az Androidhoz készült Céges portál alkalmazás regisztrálási folyamatának leírását, hogy a végfelhasználók könnyebben tudják elvégezni a regisztrálást. Ha egyéni regisztrációs dokumentációval rendelkezik, frissítse az új képernyők megjelenítéséhez. Mintaképeket a [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-app-ui.md#week-of-september-11-2017) című oldalon találhat.

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>A Windows Information Protection engedélyezési szabályzata a Windows 10-es Céges portál alkalmazással bővül <!-- 677129 -->

Frissítettük a Windows 10-es Céges portál alkalmazást, amely így támogatja a Windows Információvédelmet. Az alkalmazást hozzá lehet adni a WIP engedélyezési szabályzatához. A változásnak köszönhetően az alkalmazást a későbbiekben nem szükséges hozzáadni a **Kivételek** listához.


## <a name="week-of-august-21-2017"></a>2017. augusztus 21-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése
#### <a name="improvements-to-device-overview----1404453---"></a>Fejlesztések az eszközök áttekintésénél <!-- 1404453 -->  
A fejlesztéseknek köszönhetően az eszközök áttekintésében mostantól megjelennek a regisztrált eszközök, az Exchange ActiveSync által kezeltek viszont ki lesznek hagyva. Az Exchange ActiveSync által kezelt eszközök a regisztrált eszközökéitől eltérő felügyeleti beállításokkal rendelkeznek. A regisztrált eszközök számát összesítve és platform szerinti lebontásban is megtekintheti az Intune-ban az Azure Portal **Eszközök** > **Áttekintés** menüpontjában.

### <a name="device-management"></a>Eszközkezelés
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Az Intune által gyűjtött eszközleltár fejlesztései
<!-- 961134, 1104426, 1281327, 1333543 -->
Ebben a kiadásban a következő fejlesztések lettek végrehajtva a kezelt eszközök által gyűjtött leltáradatokkal kapcsolatban:
 
-   Mostantól Android-eszközök esetében hozzá lehet adni egy legutóbbi javítási szintet megjelenítő oszlopot az eszközleltárhoz. Ennek megtekintéséhez adja a **Security patch level** (Biztonsági javítási szint) oszlopot az eszközlistához.
-   Az eszközök szűrésénél most már az eszköz regisztrációjának dátuma alapján is szűrhet. Például megadhatja, hogy csak azok az eszközök jelenjenek meg, melyeket egy adott dátum után regisztráltak.
-   Fejlesztéseket hajtottunk végre a **Last Check-in Date** (Utolsó beadás dátuma) szűrőjén.
-   Az eszközlistában most már megjelenítheti a céges eszközök telefonszámát.
Továbbá, a szűrőablakban mostantól már telefonszám alapján is kereshet az eszközök között.
 
További információt az eszközleltárral kapcsolatban [Az Intune-eszközleltár megtekintése](device-inventory.md) című cikkben talál.

#### <a name="conditional-access-support-for-macos-devices"></a>Feltételes hozzáférés támogatása macOS-eszközöknél 
<!-- 720172 -->
Mostantól beállítható a Mac-eszközök Intune-ba való regisztrálását és az eszközmegfelelőségi szabályzatoknak való megfelelését megkövetelő feltételes hozzáférési szabályzat. A felhasználók megtehetik például, hogy letöltik a macOS-re készült Intune Céges portál alkalmazást és regisztrálják Mac-eszközeiket az Intune-ba. Az Intune kiértékeli, hogy a Mac-eszköz eleget tesz vagy sem többek között a PIN-kódra, a titkosításra, az operációs rendszer verziójára és a rendszerintegritásra vonatkozó követelményeknek.

- További információ a [feltételes hozzáférés támogatásáról macOS-eszközöknél](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Nyilvános előzetes verzióban elérhető a macOS-hez készült Céges portál alkalmazás <!---1484796--->
Az Enterprise Mobility + Security-beli feltételes hozzáférés nyilvános előzetesének részeként előzetes verzióban elérhető a macOS-es Céges portál alkalmazás. Ez a kiadás a macOS 10.11-es és későbbi verzióit támogatja. Letölthető a [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal) címről. 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Új Windows 10-es eszközkorlátozási beállítások    
<!--1063965, 1308850  -->
Ebben a kiadásban új beállítási lehetőségekkel bővült a [Windows 10-es eszközkorlátozási profil](/intune/device-restrictions-windows-10), a következő kategóriákban:

-   Windows Defender SmartScreen
-   Alkalmazás-áruház

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>A Windows 10-es Endpoint Protection-eszközprofil BitLocker-beállításainak frissítései
<!--1459533 -->    
Ebben a kiadásban a következő fejlesztéseket hajtottuk végre a Windows 10-es Endpoint Protection-eszközprofil BitLocker-beállításainak működésében:
 
Az **Operációsrendszer-meghajtók BitLocker-beállításaiban** a **BitLocker nem kompatibilis TPM-lapkával** beállításánál a **Letiltás** lehetőség választása korábban tévesen a BitLocker engedélyezését eredményezte. Javítottuk a beállítást, így kiválasztás esetén most már letiltja a BitLockert.
Az **Operációsrendszer-meghajtók BitLocker-beállításaiban** a **Tanúsítványalapú adat-helyreállítási ügynök** beállításnál mostantól letilthatja a tanúsítványalapú adat-helyreállítási ügynököt. Az ügynök ugyanakkor alapértelmezés szerint engedélyezve van.
A **Rögzített adatmeghajtók BitLocker-beállításai** között az **Adat-helyreállítási ügynök** beállításnál mostantól letilthatja az adat-helyreállítási ügynököt.
További információ: [Endpoint Protection-beállítások Windows 10 és újabb rendszerű eszközökön](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Új lehetőségek az Androidhoz készült Céges portál és az alkalmazásvédelmi szabályzat bejelentkezett felhasználóinak <!-- 621669 -->
A végfelhasználók az Androidhoz készült Céges portál használatával most már az Android rendszerű eszköz regisztrációja nélkül is böngészhetnek az alkalmazások között, felügyelhetnek eszközöket, valamint megtekinthetik az informatikai részleg elérhetőségeit. Ezenkívül ha egy végfelhasználó már egy, az Intune alkalmazásvédelmi szabályzata által védett alkalmazást használ, és elindítja az Androidhoz készült Céges portált, már nem kap felszólítást az eszköz regisztrációjára.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Új beállítás az akkumulátor-optimalizálás ki- és bekapcsolásához az Androidhoz készült Céges portál alkalmazásban<!--1405990-->
Az Androidhoz készült Céges portál alkalmazás **Beállítások** oldala új beállítással bővült, amellyel a felhasználók könnyen kikapcsolhatják az akkumulátor-optimalizálást a Céges portál és a Microsoft Authenticator alkalmazásokhoz. A beállításon látható alkalmazásnév attól függően változik, hogy melyik alkalmazás kezeli a munkahelyi fiókot. Az e-mailek és adatok szinkronizálását végző munkahelyi alkalmazások teljesítménynövelése érdekében az akkumulátor-optimalizálás kikapcsolását javasoljuk. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Többszörös identitás támogatása az iOS-hez készült OneNote-ban      <!-- 1234281 -->
A felhasználók mostantól több fiókot (munkahelyit és személyeset) is használhatnak az iOS-hez készült Microsoft OneNote-ban. Anélkül alkalmazhatók alkalmazásvédelmi szabályzatok a munkahelyi jegyzetfüzetekben található céges adatokra, hogy ez hatással lenne a személyes jegyzetfüzetekre. A szabályzat azt például lehetővé teszi, hogy a felhasználó adatokat kereshessen a céges jegyzetfüzetekben, azt viszont megakadályozza, hogy azokat kimásolja onnan, és beillessze egy személyes jegyzetfüzetbe.
 
- További információ azon alkalmazásokról, amelyek támogatják az [alkalmazásvédelmet és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Új beállítások alkalmazások engedélyezéséhez és letiltásához Samsung KNOX Standard-eszközökön
<!-- 1305423 822899-->  
Ebben a kiadásban új [eszközkorlátozási beállítások](device-restrictions-android.md) jelennek meg, amelyekkel megadhatók a következő alkalmazáslisták:
 
- Felhasználók által telepíthető alkalmazások
- Felhasználók által nem futtatható alkalmazások
- Az eszközön a felhasználó elől rejtett alkalmazások
 
Az alkalmazás megadható URL-cím vagy csomagnév alapján, vagy kiválasztható a felügyelt alkalmazások listájából.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Hivatkozás az új Azure AD alkalmazásalapú feltételes hozzáférési szabályzat felhasználói felületére az Intune-ból
<!-- 1016201 -->
Az Azure AD tevékenységprofiljában található új feltételes hozzáférési szabályzat felhasználói felületéről a rendszergazdák alkalmazásalapú feltételes szabályzatokat állíthatnak be. Az Azure Intune App Protection szakasz alkalmazásalapú feltételes hozzáférése egyelőre a helyén marad, és a kikényszerítése párhuzamosan zajlik le. Ezekhez adódik hozzá az a kényelmi hivatkozás, amely az Intune tevékenységprofilban található új feltételes hozzáférési szabályzat felhasználói felületére mutat.

- További tudnivalók az [Azure AD-beli alkalmazásalapú feltételes hozzáférésről](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Értesítések

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Frissített IP-címek az Intune-hoz <!-- 1175274 -->
A tűzfal proxybeállításaihoz [DNS-nevek és IP-címek frissített listája](/intune/network-bandwidth-use) érhető el.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Feltételes hozzáféréshez használható az Azure Active Directory <!-- 967947 -->
Az Azure Portal Azure Active Directory szakaszában elérhető a feltételes hozzáférés, amellyel hatékonyan és rugalmasan állíthatók be szabályzatok olyan felhőalkalmazásokhoz, mint az Office 365, az Exchange Online vagy a SharePoint Online.  Az Intune-konzol helyett most már az **Azure Active Directory feltételes hozzáférés** paneljén konfigurálhatja a szabályzatokat. Az Intune-konzolon meglévő szabályzatokat újra létre kell hozni az Azure Portalon. További információt az [Azure AD feltételes hozzáférési szabályzatok létrehozása](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview) című témakörben találhat.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el az Azure Portal, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök
A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat az új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune/role-based-access-control).



## <a name="whats-coming"></a>Mi várható?

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>Az iOS 11-ben a Mail alkalmazás támogatni fogja az OAuth-t<!---1196951--->
Az Intune-nal használt feltételes hozzáférés biztonságosabb hitelesítést tesz lehetővé iOS-eszközökön az OAuth használatával. Ennek a lehetőségnek a kihasználása érdekében az iOS-es Céges portál alkalmazásban egy új fajta folyamatot vezetünk be, amely lehetővé teszi a biztonságosabb hitelesítést. Ha a végfelhasználó a Mail alkalmazásban megpróbál bejelentkezni egy új Exchange-fiókba, a rendszer egy rákérdezést jelenít meg a webes nézethez. Az Intune-ban való regisztráláskor a rendszer egy kérdést jelenít meg, amelynél a felhasználó engedélyezheti, hogy a natív Mail alkalmazás hozzáférjen a tanúsítványhoz. A legtöbb végfelhasználó nem kap többé karanténba helyezett e-maileket. A már meglévő postafiókok továbbra is az alapszintű hitelesítési protokollt használják majd, és ilyen esetben a felhasználók továbbra is kaphatnak karanténba helyezett e-maileket. A végfelhasználói bejelentkezési folyamat hasonló az Office-mobilalkalmazásoknál tapasztalhatóhoz.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 2-->
__Frissítettük a Kiemelt alkalmazások szakaszt__  
A webhelyhez hozzáadtunk egy új oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszának felhasználói felületén. A változásokat megtekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) oldalon.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Platformtámogatási emlékeztető: a Windows Phone 8.1 alapvető technikai támogatása 2017. július 11-én megszűnt
<!-- 1327781 -->
A Windows Phone 8.1 platform alapvető technikai támogatása 2017. július 11-én lejárt. A Windows 8.1 PC támogatását ez nem érinti.

Az Intune szolgáltatás által felügyelt Windows Phone 8.1-es eszközökre nézve ennek nincs közvetlen következménye. A regisztrált eszközök tovább használhatók, és minden szabályzat, konfiguráció és alkalmazás is az elvárt módon működik tovább. Fontos, hogy nincsenek az Intune szolgáltatás körébe tartozó Windows Phone 8.1 platformot és a Windows Phone 8.1 Vállalati portál alkalmazást érintő fejlesztések.

Javasolt az arra jogosult Windows Phone 8.1 eszközöket a lehető leghamarabb a Windows 10 mobil verziójára frissíteni. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Az Intune iOS-es Vállalati portál alkalmazás támogatásának változásai  <!-- 1164474  -->
A közeljövőben megjelenik az iOS-es Microsoft Intune Vállalati portál alkalmazás egy új verziója, amely csak az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. A Vállalati portál iOS 8-at támogató verziója nagyon rövid ideig még elérhető marad. Ugyanakkor ha MAM-használatot támogató iOS-alkalmazásokat is használ, vegye figyelembe, hogy csak az iOS 9.0-s és újabb verzióit támogatjuk, ezért ajánlatos gondoskodni róla, hogy a végfelhasználók a legfrissebb operációs rendszert használják. 

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Mindezt azért tudatjuk előre a pontos dátumok ismerete nélkül, hogy legyen ideje tervet készíteni. Gondoskodjon róla, hogy a felhasználók frissítsenek legalább az iOS 9.0-s verziójára, és kérje meg őket, hogy a Céges portál alkalmazást is frissítsék, amikor az megjelenik.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Javasolja a felhasználóinak, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 9.0 rendszerre.  Javasolja a felhasználóknak a Vállalati portál új verziójának telepítését, hogy kihasználhassák az általa kínált új funkciókat.

Nyissa meg az Intune-t az Azure Portalon, és az Eszközök -> Minden eszköz alatt az iOS verziójára szűrve gyűjtse ki az iOS 9-nél korábbi operációs rendszert futtató eszközöket.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->
Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja.

Az új ATS-követelményeket érvényesítő Apple TestFlight alkalmazásban elérhetővé vált a Céges portál alkalmazás iOS rendszerű verziója. Ha szeretné kipróbálni az alkalmazást az ATS-megfelelőség tesztelése céljából, küldje el a kereszt- és vezetéknevét, az e-mail-címét és a munkahelye nevét a <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> e-mail-címre. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [A Céges portál felhasználói felületének újdonságai](whats-new-app-ui.md)
* [Korábbi hónapok újdonságai](whats-new-archive.md)

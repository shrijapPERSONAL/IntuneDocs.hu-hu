---
title: "Előzetes kiadás"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 8/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5861c999752bfef05b8a33161d0bf75a6d4daf59
ms.sourcegitcommit: 18cdbdc226f64368de892a8c5cff157c37986c57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="the-early-edition-for-microsoft-intune---august-2017"></a>A Microsoft Intune előzetes kiadása – 2017. augusztus

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Ne ossza meg ezeket az információkat cégen kívüli személyekkel. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
>A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune az Azure Portalon




### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Új eszközművelet az eszközök Intune-nal való szinkronizálásának kikényszerítésére <!-- 711369 -->    
Új eszközműveletet vezetünk be, amely a választott eszköz azonnali bejelentkezését kényszeríti ki az Intune-nál. Bejelentkezéskor az eszköz azonnal fogadja az összes hozzárendelt, függőben lévő műveletet vagy szabályzatot.  Ez a művelet segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.

### <a name="actions-for-non-compliance----730266--"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266-->     
A *Meg nem felelés esetén végrehajtandó műveletek* a megfelelési szabályzatok új funkciója, amelyekkel nem megfelelő eszközökön lehet műveleteket végrehajtani. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.


### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android- és iOS-eszköz regisztrálásának korlátozása operációsrendszer-verzió alapján <!--- 1333256,  1245463 --->  
Az Intune támogatja az iOS- és Android-eszközök regisztrálásának operációsrendszer-verziószám alapján történő korlátozását. Az **Intune** > **Regisztrációs korlátozások** > **Eszköztípus szerinti korlátozások** > **Alapértelmezés** > **Platformkorlátozások** szakaszban az adminisztrátor a platformkonfiguráció megadásával korlátozhatja a regisztrálást egy minimális és maximális operációsrendszer-verziószám között. Az Android operációsrendszer-verzióit főverzió.alverzió.build.javítás formában kell megadni, ahol a build és a javítás megadása nem kötelező. Az iOS-verziókat főverzió.alverzió.build formában kell megadni, ahol a build megadása nem kötelező.

>[!NOTE]
>Ez a beállítás nem korlátozza a regisztrációt az Apple regisztrációs programjaival, amilyen az Apple Készülékregisztrációs program, az Apple School Manager vagy az Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Személyes tulajdonban lévő Android, iOS és macOS rendszerű eszközök regisztrálásának korlátozása  <!--- 1333272,  1333275, 1245709 --->
Az Intune mostantól támogatja személyes tulajdonban lévő Android, iOS és macOS rendszerű eszközök regisztrálásának az eszköz sorozatszáma alapján történő korlátozását. Egyes eszközök nem adnak meg sorozatszámot. A részleteket egyeztesse az eszköz gyártójával. A sorozatszámot az Intune-ba feltöltve előre bejelenthető, hogy az eszköz vállalati tulajdonban van. A regisztrációs korlátozásokkal letilthatók a személyes tulajdonban lévő (BYOD) eszközök, így csak vállalati tulajdonú eszközök regisztrációja lesz engedélyezett.

Ha sorozatszámokat kíván importálni az Intune-portálra, keresse fel az **Eszközregisztráció** > **Céges készülékazonosítók** szakaszt, kattintson a **Hozzáadás** gombra, és töltsön fel egy .CSV fájlt. A fájlban nem lehet fejléc, és tartalmaznia kell két oszlopot, az egyiket a sorozatszámok, a másikat az olyan adatok számára, mint az IMEI-szám.  A személyes tulajdonban lévő eszközök letiltásához válassza az **Eszközregisztráció** > **Regisztrációs korlátozások** lehetőséget. Az **Eszköztípus-korlátozások** szakaszban válassza az **Alapértelmezés** majd a **Platformkonfigurációk** lehetőséget. **Engedélyezheti** vagy **Tilthatja** a személyes tulajdonban lévő iOS, Android, és macOS rendszerű eszközöket. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>A legújabb elérhető szoftverfrissítés automatikus telepítésének kikényszerítése felügyelt iOS-eszközöknél <!-- 777100 -->   
Új szabályzat jelenik meg a Szoftverfrissítések munkaterületen, amellyel kikényszeríthető a legújabb elérhető szoftverfrissítés automatikus telepítése a felügyelt iOS-eszközöknél. Megjeleníthet egy új jelentést is, amely tartalmazza a régebbi verziójú iOS-eszközök listáját és az elavulásuk tömör indoklását.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Új jelentés a régebbi iOS-verziójú iOS-eszközök listájával   <!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** munkaterületről lehet majd elérni. A jelentésben megtekintheti az iOS frissítési szabályzatok által megcélzott és elérhető frissítésekkel rendelkező felügyelt iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Új beállítások alkalmazások engedélyezéséhez és letiltásához Samsung Knox Standard-eszközökön  <!-- 822899,  1305423-->   
Megjelennek új [eszközkorlátozási beállítások](device-restrictions-android.md), amelyekkel megadhatók a következő alkalmazáslisták:
  - Felhasználók által telepíthető alkalmazások
  - Felhasználók által nem futtatható alkalmazások
  - Az eszközön a felhasználó elől rejtett alkalmazások  

Az alkalmazás megadható URL-cím vagy csomagnév alapján, vagy kiválasztható a felügyelt alkalmazások listájából.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>A Windows 10-es eszközkorlátozási profil új beállításai
<!--- 978575, 1308849, 1308850 -->
A Windows Defender SmartScreen kategóriában új beállításokat adunk a Windows 10-es eszközkorlátozási profilhoz.

A Windows 10-es eszközkorlátozási profillal kapcsolatban lásd: [Windows 10-es és újabb eszközkorlátozási beállítások]( device-restrictions-windows-10.md).

### <a name="new-device-restriction-settings-for-windows-10------1063965---"></a>A Windows 10-es eszközkorlátozási profil új beállításai   <!-- 1063965 -->
A [Windows 10-es eszközkorlátozási profilhoz](/intune/device-restrictions-windows-10) a következő kategóriákban adunk hozzá új beállításokat:
- Windows Defender SmartScreen
- Alkalmazás-áruház


### <a name="android-for-work-support-for-lookout----1087312---"></a>Az Android for Work Lookout-támogatása <!-- 1087312 -->   
A Lookouttal rendelkező Intune-összekötők támogatni fogják az Android for Work rendszerű eszközöket a Lookout for Work alkalmazás használatakor. A Lookout alkalmazást a tárolón kívül vagy belül egyaránt telepítheti.


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection és Citrix MDX fejlesztői eszközök <!-- 709185 -->
Az eszközöket és az alkalmazásokat a Citrix XenMobile MDX és a Microsoft Intune kombinációjával is kezelheti. Így az eszközök kezelésénél egyaránt igénybe veheti az Intune alkalmazásvédelmi szabályzatát és a Citrix mVPN-technológiáját.

Hozzáférhet egy kódtárhoz, amely a Citrix MDX mVPN-technológiával integráltan tartalmazza az Intune iOS és Android rendszerhez készült alkalmazásburkoló eszközét és az Intune App SDK-t.


### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Új mobileszköz-védelmi partner   <!-- 954681 -->
A Microsoft Intune-nal integrálható, Zimperium által irányított, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

#### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció?
A kockázatfelmérés a Zimperiumot futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Zimperium által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, amelyekkel az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Hivatkozás az új Azure AD feltételes hozzáférési szabályzat felhasználói felületére az Intune-ból <!-- 1016201 -->
Az Azure AD tevékenységprofiljában található új feltételes hozzáférési szabályzat felhasználói felületéről a rendszergazdák alkalmazásalapú feltételes szabályzatokat állíthatnak be. Az Azure Intune App Protection szakasz alkalmazásalapú feltételes hozzáférési szabályzatai egyelőre a helyükön maradnak, és a kikényszerítésük párhuzamosan zajlik le. Ezekhez adódik hozzá az a kényelmi hivatkozás, amely az Azure AD-ben található új feltételes hozzáférési szabályzat felhasználói felületére mutat.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása  <!-- 676614 -->   
A helyszíni Exchange Connector használatához több ügyfél-hozzáférési kiszolgálói (CAS) szerepkörrel is rendelkezhet. A fő CAS kiesése esetén például az Exchange Connector kap egy kérelmet, hogy térjen vissza más ügyfél-hozzáférési kiszolgálókhoz. Ez a funkció biztosítja, hogy a szolgáltatás ne szakadjon meg.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager felügyeleti csomag az Exchange Connectorhoz <!-- 885457 -->   
A System Center Operations Manager Exchange Connectorhoz készült felügyeleti csomagja segíteni fog az Exchange Connector naplófájljainak elemzésében. Ez a felügyeleti csomag számos megoldást nyújt az Intune monitorozására hibaelhárítás esetén.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Feltételes hozzáférés támogatása Mac-eszközöknél  <!-- 720172 -->   
Rövidesen beállítható lesz a Mac-eszközök Intune-ba való regisztrálását és az eszközmegfelelőségi szabályzatoknak való megfelelését megkövetelő feltételes hozzáférési szabályzat. A felhasználók megtehetik például, hogy letöltik a macOS-re készült Intune Céges portál alkalmazást és regisztrálják Mac-eszközeiket az Intune-ba. Az Intune kiértékeli, hogy a Mac-eszköz eleget tesz vagy sem többek között a PIN-kódra, a titkosításra, az operációs rendszer verziójára és a rendszerintegritásra vonatkozó követelményeknek.

### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!---1164477--->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes vállalati erőforráshoz, így az e-mailhez való hozzáférés is le lesz tiltva. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171127, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még október eleje előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Platformtámogatási emlékeztető: a Windows Phone 8.1 alapvető technikai támogatása 2017. július 11-én megszűnik <!-- 1327781 -->  
2017. július 11-én a Windows Phone 8.1 platform alapvető technikai támogatása lejár. A Windows 8.1 PC támogatását ez nem érinti.

Az Intune szolgáltatás által felügyelt Windows Phone 8.1-es eszközökre nézve ennek nincs közvetlen következménye. A regisztrált eszközök továbbra is használhatók, és minden szabályzat, konfiguráció és alkalmazás az elvárt módon működik tovább. Fontos, hogy nincsenek az Intune szolgáltatás körébe tartozó Windows Phone 8.1 platformot és a Windows Phone 8.1 Céges portál alkalmazást érintő fejlesztések.

Javasolt az arra jogosult Windows Phone 8.1 eszközöket a lehető leghamarabb a Windows 10 mobil verziójára frissíteni. 




## <a name="intune-apps"></a>Intune-alkalmazások

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Világos és sötét üzemmód választható a Windows 10 rendszerre készült Céges portál alkalmazáshoz <!---676547--->
A végfelhasználók kiválaszthatják a Windows 10 rendszerre készült Céges portál alkalmazás színhasználatát. Ezt a felhasználó a Céges portál alkalmazás Beállítások szakaszában változtathatja meg. A változás az után jelenik meg, hogy a felhasználó újraindítja az alkalmazást. A Windows 10 1607-es és újabb verziói esetén az alkalmazásmód alapértelmezés szerint a rendszer beállításait használja. A Windows 10 1511-es vagy korábbi verzióit futtató asztali számítógépeken az alkalmazás alapértelmezett üzemmódja a világos.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Az Android rendszerre készült Céges portál alkalmazás regisztráció nélküli elérésének engedélyezése végfelhasználók számára <!---1169910--->  
A végfelhasználóknak rövidesen mát nem kell regisztrálniuk az eszközüket az Android rendszerre készült Céges portál alkalmazás eléréséhez. Az alkalmazásvédelmi szabályzatokat használó szervezetek végfelhasználói többé nem fognak az eszközük regisztrálására felszólító figyelmeztetést kapni a Céges portál alkalmazás megnyitásakor. A végfelhasználók alkalmazásokat is tudnak majd telepíteni a Céges portálról az eszköz regisztrálása nélkül. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
A végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”

### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Új lehetőségek az Androidhoz készült Céges portál és az alkalmazásvédelmi szabályzat bejelentkezett felhasználóinak <!-- 621669 -->
A végfelhasználók az Androidhoz készült Céges portál használatával az Android-rendszerű eszköz regisztrációja nélkül is böngészhetnek az alkalmazások között, felügyelhetnek eszközöket, és megtekinthetnek informatikai kapcsolattartási adatokat. Továbbá ha egy végfelhasználó már egy, az Intune alkalmazásvédelmi szabályzat által védett alkalmazást használ, és elindítja az Androidhoz készült Céges portált, már nem kap felszólítást az eszköz regisztrációjára. 

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Végfelhasználóknak szóló információ az iOS-eszközök megtekinthető adatairól <!--739894-->
Az iOS-alapú Céges portál alkalmazásban található Eszköz részletei képernyőhöz hozzáadjuk a **Tulajdonjog típusa** oldalt. A felhasználók így közvetlenül az Intune végfelhasználói dokumentáció ezen oldaláról tájékozódhatnak az adatvédelemről. A tudnivalókat az About (Információk) képernyőről is elérhetik.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Androidos eszközökre vonatkozó új információk az Alkalmazások részletei lapon <!--1287476-->
Az Androidhoz készült Céges portál Alkalmazások részletei lapján meg fognak jelenni a rendszergazda által az alkalmazáshoz definiált alkalmazáskategóriák.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Modern felület az Intune mobilalkalmazás-felügyelet (MAM) párbeszédpanelein <!-- 1199015 -->
Az Intune mobilalkalmazás-felügyelet (MAM) frissített felületű párbeszédpanelei modern látványt és élményt nyújtanak. A párbeszédpanelek működése megegyezik az előző stíluséval.

A korszerű Android-rendszerű eszközökön az Intune által megjelenített, hibára vonatkozó vagy értesítési párbeszédpanelek megújult látványt és élményt nyújtanak.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Új beállítás az akkumulátor-optimalizálás ki- és bekapcsolásához az Androidhoz készült Céges portál alkalmazásban<!--1405990-->
Az Androidhoz készült Céges portál alkalmazás **Beállítások** oldala új beállítással bővül, amellyel a felhasználók könnyen kikapcsolhatják az akkumulátor-optimalizálást a Céges portál és a Microsoft Authenticator alkalmazásokhoz. A beállításon látható alkalmazásnév attól függően változik, hogy melyik alkalmazás kezeli a munkahelyi fiókot. Az e-mailek és adatok szinkronizálását végző munkahelyi alkalmazások teljesítménynövelése érdekében az akkumulátor-optimalizálás kikapcsolását javasoljuk. 




## <a name="notices"></a>Értesítések

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->   
Az Apple bejelentette, hogy 2017 tavaszától bizonyos követelményeket ír elő az Application Transport Security (ATS, alkalmazás átviteli biztonsága) esetében. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->   
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Készüljön fel a változásra: megváltozik az Intune Partner Portal <!-- 1050016 -->
A 2017. május közepén esedékes szolgáltatásfrissítés keretében eltávolítjuk az Intune Partner lapot manage.microsoft.com-ról.  

Ha Ön partneradminisztrátor, akkor a továbbiakban nem lesz lehetősége az Intune Partner lapon megnézni partnereit és intézkedni a nevükben. Ehelyett a Microsoft két másik partnerportáljának valamelyikére kell majd bejelentkeznie.

A [Microsoft Partnerközpontban](https://partnercenter.microsoft.com/) és a [Microsoft Office 365 Felügyeleti partnerközpontban](https://portal.office.com/) egyaránt bejelentkezhet az Ön által felügyelt ügyfélfiókokba. A továbbiakban partnerként ezeken a webhelyeken felügyelheti ügyfeleit.



### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).

---
title: "Előzetes kiadás"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ba953f1f471cc8bdbfdadad75c8f4eeb8acc2279
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2017
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

### <a name="actions-for-non-compliance----730266--"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266-->     
A *Meg nem felelés esetén végrehajtandó műveletek* a megfelelési szabályzatok új funkciója, amelyekkel nem megfelelő eszközökön lehet műveleteket végrehajtani. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Új jelentés a régebbi iOS-verziójú iOS-eszközök listájával   <!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** munkaterületről lehet majd elérni. A jelentésben megtekintheti az iOS frissítési szabályzatok által megcélzott és elérhető frissítésekkel rendelkező felügyelt iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Új beállítások alkalmazások engedélyezéséhez és letiltásához Samsung Knox Standard-eszközökön  <!-- 822899,  1305423-->   
Megjelennek új [eszközkorlátozási beállítások](device-restrictions-android.md), amelyekkel megadhatók a következő alkalmazáslisták:
  - Felhasználók által telepíthető alkalmazások
  - Felhasználók által nem futtatható alkalmazások
  - Az eszközön a felhasználó elől rejtett alkalmazások  

Az alkalmazás megadható URL-cím vagy csomagnév alapján, vagy kiválasztható a felügyelt alkalmazások listájából.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>A Windows 10-es eszközkorlátozási profil új beállításai
<!--- 978575, 1308849, -->
A Windows Defender SmartScreen kategóriában új beállításokat adunk a Windows 10-es eszközkorlátozási profilhoz.

A Windows 10-es eszközkorlátozási profillal kapcsolatban lásd: [Windows 10-es és újabb eszközkorlátozási beállítások]( device-restrictions-windows-10.md).




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

### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!---1164477--->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes vállalati erőforráshoz, így az e-mailhez való hozzáférés is le lesz tiltva. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171127, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még október eleje előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Platformtámogatási emlékeztető: a Windows Phone 8.1 alapvető technikai támogatása 2017. július 11-én megszűnik <!-- 1327781 -->  
2017. július 11-én a Windows Phone 8.1 platform alapvető technikai támogatása lejár. A Windows 8.1 PC támogatását ez nem érinti.

Az Intune szolgáltatás által felügyelt Windows Phone 8.1-es eszközökre nézve ennek nincs közvetlen következménye. A regisztrált eszközök továbbra is használhatók, és minden szabályzat, konfiguráció és alkalmazás az elvárt módon működik tovább. Fontos, hogy nincsenek az Intune szolgáltatás körébe tartozó Windows Phone 8.1 platformot és a Windows Phone 8.1 Céges portál alkalmazást érintő fejlesztések.

Javasolt az arra jogosult Windows Phone 8.1 eszközöket a lehető leghamarabb a Windows 10 mobil verziójára frissíteni. 

## <a name="intune-apps"></a>Intune-alkalmazások

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Intune Managed Browser-támogatás iOS és Android rendszerű eszközök számára <!---1374196--->

2017 októberétől az Intune Managed Browser alkalmazás Androidon kizárólag az Android 4.4 vagy újabb rendszerű eszközöket fogja támogatni. Az Intune Managed Browser alkalmazás iOS-en kizárólag az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Az Android rendszerre készült Céges portál alkalmazás regisztráció nélküli elérésének engedélyezése végfelhasználók számára <!---1169910--->  
A végfelhasználóknak rövidesen mát nem kell regisztrálniuk az eszközüket az Android rendszerre készült Céges portál alkalmazás eléréséhez. Az alkalmazásvédelmi szabályzatokat használó szervezetek végfelhasználói többé nem fognak az eszközük regisztrálására felszólító figyelmeztetést kapni a Céges portál alkalmazás megnyitásakor. A végfelhasználók alkalmazásokat is tudnak majd telepíteni a Céges portálról az eszköz regisztrálása nélkül. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
A végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”


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

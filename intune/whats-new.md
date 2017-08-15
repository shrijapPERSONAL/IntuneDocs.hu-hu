---
title: "Újdonságok a Microsoft Intune-ban"
titleSuffix: Intune on Azure
description: "Az Azure-beli Intune-portál újdonságai"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/10/2017
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
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>2017. július 31-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android- és iOS-eszköz regisztrálásának korlátozása operációsrendszer-verzió alapján <!--- 1333256,  1245463 --->
Az Intune támogatja az iOS- és Android-eszközök regisztrálásának operációsrendszer-verziószám alapján történő korlátozását. Az **Eszköztípuskorlát** szakaszban az adminisztrátor a platformkonfiguráció megadásával korlátozhatja a regisztrálást egy minimális és maximális operációsrendszer-verziószám között. Az Android operációsrendszer-verzióit főverzió.alverzió.build.javítás formában kell megadni, ahol az alverzió, a build és a javítás megadása nem kötelező. Az iOS-verziókat főverzió.alverzió.build formában kell megadni, ahol az alverzió és a build megadása nem kötelező. További információ [az eszköz regisztrációs korlátozásokról](enrollment-restrictions-set.md).

>[!NOTE]
>Nem korlátozza az Apple készülékregisztrációs programok vagy az Apple Configuratoron keresztül végzett regisztrációt.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Személyes tulajdonban lévő Android, iOS és macOS rendszerű eszközök regisztrálásának korlátozása  <!--- 1333272,  1333275, 1245709 --->
Az Intune korlátozhatja a személyes eszközök regisztrációját a céges eszközök IMEI-számait tartalmazó engedélyezési lista alapján. Ez a szolgáltatás most már iOS, Android, és macOS rendszereken is elérhető az Intune-ban az eszközök sorozatszámainak használatával. A sorozatszámot az Intune-ba feltöltve előre bejelenthető, hogy az eszköz vállalati tulajdonban van. A regisztrációs korlátozásokkal letilthatók a személyes tulajdonban lévő (BYOD) eszközök, így csak vállalati tulajdonú eszközök regisztrációja lesz engedélyezett. További információ [az eszköz regisztrációs korlátozásokról](enrollment-restrictions-set.md).

Sorozatszámok úgy tölthetők fel, hogy az **Eszközregisztráció** > **Céges készülékazonosítók** szakaszban a **Hozzáadás** gombra kattint, majd feltölt egy .CSV fájlt (fejléc nélkül, két oszloppal a sorozatszámoknak és más részleteknek, például az IMEI-számoknak).  A személyes tulajdonban lévő eszközök letiltásához válassza az **Eszközregisztráció** > **Regisztrációs korlátozások** lehetőséget. Az **Eszköztípus-korlátozások** szakaszban válassza az **Alapértelmezés** majd a **Platformkonfigurációk** lehetőséget. **Engedélyezheti** vagy **Tilthatja** a személyes tulajdonban lévő iOS, Android, és macOS rendszerű eszközöket. 


### <a name="device-management"></a>Eszközkezelés   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Új eszközművelet az eszközök Intune-nal való szinkronizálásának kikényszerítésére <!-- 711369 -->
Ebben a kiadásban új eszközműveletet vezettünk be, amely a választott eszköz azonnali bejelentkezését kényszeríti ki az Intune-nál. Amikor az eszköz bejelentkezik, azonnal megkap minden hozzá rendelt, függőben lévő műveletet vagy szabályzatot.  Ez a művelet segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.
További információkért lásd: [Eszköz szinkronizálása](device-sync.md)

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>A legújabb elérhető szoftverfrissítés automatikus telepítésének kikényszerítése felügyelt iOS-eszközöknél <!-- 777100 -->
Új szabályzat érhető el a Szoftverfrissítések munkaterületen, amellyel kikényszeríthető a legújabb elérhető szoftverfrissítés automatikus telepítése a felügyelt iOS-eszközöknél. További információt az [iOS-es frissítési szabályzatok konfigurálása](/intune/software-updates-ios) című cikkben talál.


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Új mobileszköz-védelmi partner  <!-- 954651, 1172027 -->
A Microsoft Intune-nal integrálható, Skycure nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

##### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció?
A kockázatfelmérés a Checkpoint SandBlast Mobile-t futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Checkpoint SandBlast Mobile által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. Az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.


### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Vállalati Microsoft Áruházbeli alkalmazások telepítése elérhető alkalmazásként <!-- 748101 -->
Ettől a kiadástól kezdve a rendszergazdák a Vállalati Microsoft Áruházat is beállíthatják elérhetőként. Ha ez elérhetőként van beállítva, a felhasználók az alkalmazást anélkül telepíthetik a Céges portál alkalmazásból vagy weboldalról, hogy átirányítanák őket a Microsoft Áruházba.


### <a name="intune-apps"></a>Intune-alkalmazások  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 1-->
A [Céges portál webhely](https://portal.manage.microsoft.com) felhasználói felületén számos frissítést hajtottunk végre a végfelhasználói élmény javítása érdekében.

- __Továbbfejlesztett alkalmazáscsempék__ Az alkalmazásikonok mostantól automatikusan generált háttérrel jelennek meg az ikon meghatározó színe alapján (amennyiben az érzékelhető). Amennyiben alkalmazható a funkció az ikonra, ez a háttér felváltja a szürke kontúrt, amely eddig keretezte az ikonokat az alkalmazáscsempén.

    Egy hamarosan megjelenő kiadástól kezdve a Céges portál webhely a nagyméretű ikonokat fogja megjeleníteni, amennyiben lehetséges. Javasoljuk, hogy a rendszergazdák minimum 120x120 pixeles, nagy felbontású ikonokkal tegyék közzé az alkalmazásokat. 

- __Navigációs változások__ A navigációs sáv elemei a bal felső sarokban látható hamburger menübe kerültek át. A Kategóriák lap el lett távolítva. A felhasználók mostantól böngészés közben szűrhetik kategória szerint a tartalmat.

- __Kiemelt alkalmazások frissítései__ A webhelyhez hozzáadtunk egy új oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszának felhasználói felületén.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>iBooks-támogatás a Céges portál webhelyén <!--1231841-->
Egy dedikált oldalt adtunk hozzá a Céges portál webhelyéhez, ahol a felhasználók böngészhetik és letölthetik az iBooks szolgáltatás e-könyveit. 

### <a name="reporting"></a>Jelentéskészítés

#### <a name="intune-data-warehouse-public-preview"></a>Intune-adattárház (nyilvános előzetes verzió)

Az Intune-adattárház napi adatgyűjtéssel dokumentálja a bérlő állapotelőzményeit. Az adatokat egy Power BI-fájl (PBIX), egy sok elemzőeszközzel kompatibilis OData-hivatkozás, vagy a REST API használatával is elérheti. További információt [Az Intune-adattárház használata](reports-nav-create-intune-reports.md) című témakörben talál.


## <a name="week-of-july-23rd-2017"></a>2017. július 23-i hét

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Világos és sötét üzemmód választható a Windows 10 rendszerre készült Céges portál alkalmazáshoz <!---676547--->
A végfelhasználók kiválaszthatják a Windows 10 rendszerre készült Céges portál alkalmazás színhasználatát. Ezt a felhasználó a Céges portál alkalmazás Beállítások szakaszában változtathatja meg. A változás az után jelenik meg, hogy a felhasználó újraindítja az alkalmazást. A Windows 10 1607-es és újabb verziói esetén az alkalmazás alapértelmezés szerint a rendszer beállításait használja. A Windows 10 1511-es és korábbi verziói esetén az alkalmazás alapértelmezés szerint a világos üzemmódot használja.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>A végfelhasználók megjelölhetik saját eszközcsoportjukat a Windows 10 rendszerre készült Céges portál alkalmazásban <!---807046-->
A végfelhasználók mostantól közvetlenül a Windows 10 rendszerhez készült Céges portál alkalmazásban címkézhetik meg az eszközt, hogy kiválasszák, melyik eszközcsoporthoz tartozik.




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

### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!---1164477--->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 2-->
__Frissítettük a Kiemelt alkalmazások szakaszt__  
A webhelyhez hozzáadtunk egy új oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszának felhasználói felületén. A változásokat megtekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) oldalon.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171127, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még október eleje előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Platformtámogatási emlékeztető: a Windows Phone 8.1 alapvető technikai támogatása 2017. július 11-én megszűnt
<!-- 1327781 -->
A Windows Phone 8.1 platform alapvető technikai támogatása 2017. július 11-én lejárt. A Windows 8.1 PC támogatását ez nem érinti.

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

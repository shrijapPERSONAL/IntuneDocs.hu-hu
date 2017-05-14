---
title: "Újdonságok | Microsoft Docs"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: ed51f7ff7b6fd5a3234eb699234c6ad5fb3bdbc2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/05/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Újdonságok a Microsoft Intune-ban – 2017. április
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

> [!Note]
> Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>A MyApps elérhető a Felügyelt böngészőhöz is <!--822308, 822303-->

A Microsoft MyApps mostantól jobban működik a Felügyelt böngészőben. A Felügyelt böngésző felügyeletre ki nem jelölt felhasználói közvetlenül a MyApps szolgáltatásba kerülnek, ahol elérhetik a rendszergazda által nekik kiosztott SaaS-alkalmazásokat. Az Intune-felügyeletre kijelölt felhasználók továbbra is a Felügyelt böngésző beépített könyvjelzőjével érhetik el a MyApps szolgáltatást.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Új ikonok a Felügyelt böngészőhöz és a Céges portálhoz <!--918433, 918431, 971473-->

A Managed Browser androidos és iOS-es verziója egyaránt megújult ikont kap. Ezen az Intune új jelvénye szerepel, így egységesebb lesz az Enterprise Mobility + Security (EM+S) programcsomag alkalmazásainak arculata. A Managed Browser új ikonját megnézheti az [Újdonságok az Intune-alkalmazás felhasználói felületén](whats-new-in-intune-app-ui.md) oldalon.

A Céges portál androidos, iOS-es és windowsos verziója is új ikont kap az EM+S többi alkalmazásával való összhang jegyében. Ezek az ikonok fokozatosan jelennek majd meg az egyes platformokon áprilistól május végéig.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Bejelentkezési folyamatjelző az androidos Céges portálhoz <!--953374-->

Az androidos Céges portál alkalmazás frissítésének köszönhetően bejelentkezési folyamatjelző jelenik meg, ha a felhasználó elindítja az alkalmazást vagy folytatja a használatát. A folyamatjelző új állapotokon halad végig, ezek időrendben a következők: „Csatlakozás...”, „Bejelentkezés...” és „Biztonsági követelmények keresése...” – a felhasználó ezt követően fér hozzá az alkalmazáshoz. Az Androidhoz készült Céges portál alkalmazás új képernyőképei az [Újdonságok az Intune-alkalmazás felhasználói felületén](whats-new-in-intune-app-ui.md) oldalon láthatók.

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Alkalmazások hozzáférésének letiltása a SharePoint Online-hoz <!-- 679339 -->

Most már lehetséges a [SharePoint Online-on](/InTune/deploy-use/mam-ca-for-sharepoint-online) keresztül létrehozni olyan alkalmazásalapú feltételes hozzáférési szabályzatokat olyan alkalmazások letiltásához, amelyekre nem vonatkozik alkalmazásvédelmi szabályzat. Az alkalmazásalapú feltételes hozzáférési forgatókönyv esetében az Azure Portal használatával meghatározhatja, hogy mely alkalmazásoknak legyen hozzáférése a SharePoint Online-hoz.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Egyszeri bejelentkezés az iOS-es Céges portál alkalmazásból az iOS-re készült Outlookba <!--834012-->
Az iOS-es Céges portál alkalmazásba bejelentkezett felhasználóknak már nem kell ugyanazon az eszközön, ugyanazzal a fiókkal bejelentkezniük az Outlook alkalmazásba is. Az Outlook indításakor kiválaszthatják a fiókjukat, és automatikusan bejelentkezhetnek. Ezt a funkciót igyekszünk további Microsoft-alkalmazásokba is beépíteni.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Jobb állapotjelentések az iOS-es Céges portál alkalmazásban <!--744866-->
Az iOS-es Céges portál alkalmazásban mostantól új, konkrétabb hibaüzenetek nyújtanak kézzelfoghatóbb információt arról, hogy mi történik az eszközökön. Ezek a hibaesetek korábban egy általános, „A Munkahelyi portál átmenetileg nem érhető el” című hibaüzenetet váltottak ki. Ha pedig valaki internetkapcsolat nélkül indítja el a Céges portál alkalmazást iOS-en, akkor a kezdőlapon tartósan látható marad a „Nincs internetkapcsolat” feliratú állapotsáv.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Jobb telepítésiállapot-megjelenítés a Windows 10-es Céges portál alkalmazásban <!--676495-->

A Windows 10-es Céges portál alkalmazásban elindított alkalmazástelepítések új fejlesztései az alábbiakat tartalmazzák:
-    Gyorsabb jelentéskészítés az MSI-csomagok folyamatban lévő telepítéséhez
-    Gyorsabb jelentéskészítés a Windows 10 évfordulós frissítését és újabb kiadásait futtató eszközök modern alkalmazásainak folyamatban lévő telepítéséhez
-    Új folyamatjelző sáv a Windows 10 évfordulós frissítését és újabb kiadásait futtató eszközök modern alkalmazásainak telepítéséhez

Az új folyamatjelző sávot megnézheti az [Újdonságok az Intune-alkalmazás felhasználói felületén](whats-new-in-intune-app-ui.md) oldalon.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-es eszközök tömeges regisztrálása <!-- 747607 -->

Mostantól a Windows Configuration Designer (WCD) használatával a Windows 10 alkotói frissítéssel rendelkező nagy számú eszközt csatlakoztathat az Azure Active Directoryhez és az Intune-hoz. Ha Azure AD-bérlőhöz be szeretné kapcsolni a [tömeges MDM-regisztrálást](/intune/deploy-use/bulk-enroll-windows), a Windows Configuration Designerrel hozzon létre olyan kiépítési csomagot, amely csatlakoztatja az eszközöket az Azure AD-bérlőhöz, majd alkalmazza a csomagot a csoportosan regisztrálni és felügyelni kívánt vállalati tulajdonú eszközökre. A csomagok alkalmazását követően az eszközök csatlakoznak az Azure AD-hez, regisztrálnak az Intune-ban, és készen állnak az Azure AD-felhasználók bejelentkezésére.  Az Azure AD-felhasználók általános jogú felhasználók ezeken az eszközökön, akik megkapják majd a kijelölt szabályzatokat és a kötelező alkalmazásokat. Az önkiszolgáló és a Céges portált használó módszer jelenleg nincs támogatva.

## <a name="notices"></a>Értesítések

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Appx-változások az Azure-beli Intune-ban <!-- 1000270 -->

Az Intune Azure-ra való migrálásának keretében három appx-változást vezetünk be:

1. Új, kizárólag MDM-be regisztrált eszközökre telepíthető appx-alkalmazástípus a klasszikus Intune-konzolon.
2. A korábbi appx-alkalmazástípussal mostantól csak a PC-s Intune-ügynökkel felügyelt PC-ket lehet célozni.
3. A migráció során az összes korábbi appx MDM-es appx-re konvertálódik.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

A változás nincs hatással a PC-s Intune-ügynökkel felügyelt eszközökön telepített példányokra. A migráció után azonban a migrált appx-eket nem lehet további, a PC-s Intune-ügynökkel felügyelt és korábban nem célzott eszközökre telepíteni.

#### <a name="what-action-do-i-need-to-take"></a>Mi a teendőm?

A migrálás után töltse fel újból az appx-et PC-s appx-ként, ha újabb PC-s telepítésekre készül. További tájékoztatást az Intune-ügyfélszolgálat blogján, az [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-változások az Azure-beli Intune-ban) című angol nyelvű bejegyzésben olvashat.  

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](/intune-azure/introduction/whats-new).

> [!Note]
> Az Azure Portal előzetes verziójának frissítései ebben a hónapban jelennek meg. Azonban az Intune szolgáltatás bevezetési módja miatt elképzelhető, hogy a változások nem azonnal érhetők el.  A Portal új funkcióinak megjelenése előtt a szolgáltatás többféle összetevőjének egymás utáni frissítésére van szükség. Az Azure Portal előzetes verziójának változásai fokozatosan jelennek meg ebben a hónapban. A változások teljes listáját a [Microsoft Intune előzetes verziójának újdonságai](/intune-azure/introduction/whats-new) című témakörben találja.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök

A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat ezen új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune-azure/access-control/role-based-access-control).

## <a name="whats-coming"></a>Mi várható?

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Jobb bejelentkezési élmény a Céges portál alkalmazásokhoz minden platformon <!--User Story 1132123-->

Egy olyan változást jelentünk most be, amely a következő néhány hónapban érkezik, és amellyel javulni fog a bejelentkezési élmény az Intune Céges portál Android, iOS és Windows rendszerű alkalmazásaiban. A Céges portál alkalmazásnál az új felhasználói élmény automatikusan megjelenik minden platformon, miután az Azure AD-ban megjelenik a változtatás. Ezen kívül a felhasználók egy másik eszközről is bejelentkezhetnek a Céges portálba egy egyszeri használtra generált kóddal. Ez különösen akkor hasznos, ha a felhasználónak hitelesítő adatok nélkül kell bejelentkeznie.

Az [Újdonságok az alkalmazás felhasználói felületén](whats-new-in-intune-app-ui.md) lapon képernyőképeket láthat a korábbi bejelentkezési módról, a hitelesítő adatokat használó új bejelentkezési élményről, és a másik eszközről történő bejelentkezési folyamatról.

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
* [Az Azure előzetes verziójának újdonságai](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [A Céges portál felhasználói felületének újdonságai](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Újdonságok – Archívum](whats-new-archive.md)


---
title: "Előzetes kiadás | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>A Microsoft Intune előzetes kiadása – 2017. február

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
> A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](./media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és -szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel. A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Új interaktív felület a Windows 10-es Céges portálhoz<!--713927-->
Márciustól a Windows 10-es Céges portál tartalmazni fog egy olyan eszközökhöz készült interaktív Intune-útmutató felületet, amelyek nincsenek azonosítva vagy regisztrálva. Az új útmutató felület olyan, az adott felhasználó Windows 10-buildjére szabott részletes utasításokat tartalmaz, amely végigvezeti a felhasználókat az AAD-regisztráció (mely a feltételes hozzáférési funkciók azonosításához szükséges) és az MDM-regisztráció (mely az eszközkezelési funkciókhoz szükséges) lépésein. Az interaktív felület a Céges portál kezdőlapjáról lesz elérhető és nem lesz kötelező; a felhasználók folytathatják az alkalmazás használatát a regisztráció befejezése nélkül, de ekkor a funkciók korlátozottak lehetnek.

###

## <a name="notices"></a>Értesítések

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A csoportmigráláshoz nem lesz szükség az iOS-eszközök csoportjainak vagy szabályzatainak frissítésére <!--898837-->
A vállalati eszközbeléptetési profil által előre hozzárendelt összes Intune-beli eszközcsoport esetében és az Azure Active Directory-eszközcsoportokba történő migrálás során a rendszer egy megfelelő dinamikus eszközcsoportot hoz létre az AAD-ben a vállalati eszközbeléptetési profil neve alapján. A rendszer ezzel biztosítja azt, hogy az eszközök a regisztráció során automatikusan bekerülnek a megfelelő csoportba, valamint ugyanazokat a szabályzatokat és alkalmazásokat kapják meg, mint amelyeket az eredeti Intune-csoport kapott.

Amint egy bérlő belép a csoportosítást és célcsoport-kezelést szolgáló migrálási folyamatba, az Intune automatikusan létrehoz egy dinamikus AAD-csoportot, amely igazodik a vállalati eszközbeléptetési profil által célzott Intune-csoporthoz. A célzott Intune-csoport Intune-rendszergazdai törlésével a megfelelő dinamikus AD-csoport törlése nem történik meg. A rendszer eltávolítja ugyan a csoporttagokat és a dinamikus lekérdezést, de maga a csoport addig megmarad, amíg a rendszergazda el nem távolítja azt az AAD portálon keresztül.

Hasonlóképpen, ha a rendszergazda módosítja a vállalati eszközbeléptetési profil által célzott Intune-csoportot, az Intune egy új dinamikus csoportot hoz létre az új profil-hozzárendelésnek megfelelően, de nem távolítja el a régi hozzárendeléshez létrehozott dinamikus csoportot.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows-eszközök új MDM-kiszolgálói címe <!--893007-->
Azok a Windows- és Windows Phone-felhasználók, akik megkísérelnek beléptetni egy eszközt, és a __manage.microsoft.com__ címet adják meg MDM-kiszolgálói címként (ha a rendszer kéri), hibaüzenetet kapnak. Az MDM-kiszolgálói cím __manage.microsoft.com__ címről __enrollment.manage.microsoft.com__ címre változik. Értesítse a felhasználókat, hogy ha a rendszer kéri, az __enrollment.manage.microsoft.com__ címet használják MDM-kiszolgálói címként egy Windows- vagy Windows Phone-eszköz regisztrációjakor. Amennyiben a DNS rendszerben található olyan CNAME rekord, amely átirányítja az __EnterpriseEnrollment.contoso.com__ címet a __manage.microsoft.com__ címre, ez a frissítés megköveteli annak cseréjét egy olyan CNAME rekordra, amely az __EnterpriseEnrollment-s.manage.microsoft.com__ címre irányítja át az __EnterpriseEnrollment.contoso.com__ címet. A fenti változásról további információt az [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) weboldalon kaphat.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->
Márciustól kezdve az Androidhoz készült Céges portál alkalmazásban a [material design irányelveinek](https://material.io/guidelines/material-design/introduction.html) követésével gondoskodunk a még modernebb megjelenésről és működésről. A jobb felhasználói élményt többek között az alábbiak alkotják:

* __Színek__: a lapfejlécek színét módosítani lehet az egyéni színpaletta alapján.
* __Felület__: az Alkalmazások lapon frissítettük a Kiemelt alkalmazások és a Minden alkalmazás gombokat. A Keresés gomb mostantól lebegő műveletgombként jelenik meg.
* __Navigáció__: a Minden alkalmazás gomb lapnézetben jeleníti meg a kiemelt alkalmazásokat, az összes alkalmazást és a kategóriákat, így a navigálás egyszerűbb.
* __Szolgáltatás__: a Saját eszközök és az IT-csoport elérhetősége lapok olvashatósága javult.

A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Több felügyeleti eszköz társítása a Vállalati Windows Áruházhoz <!--926135-->
Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel). A részleteket lásd: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>2017. február

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>A mobileszköz-regisztrálás korlátozásának képessége <!--747600, 795782-->
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.

* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.  
* Csak az iOS és az Android esetében van még egy lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Az összes művelet megtekintése a felügyelt eszközökön<!--677150-->
Az új __Eszközműveletek__ jelentés megmutatja, hogy mely felhasználó hajtott végre távoli műveleteket az eszközön (például gyári alaphelyzetbe állítás), valamint megjeleníti az adott művelet állapotát is.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->
A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

#### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Eszközkategóriák megjelenítése <!--814654-->
Mostantól az eszközkategória külön oszlopként jelenik meg az eszközlistában. A kategória módosítására szintén van lehetőség az Eszköztulajdonságok panel Tulajdonságok szakaszában.

### <a name="january-2017"></a>2017. január

#### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Üzletági alkalmazások kiosztása nem regisztrált eszközökre is <!--748803-->
Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Munkahelyi portál alkalmazás helyett a Munkahelyi portál webhelyen telepíthetik az alkalmazást.

### <a name="december-2016"></a>2016. december

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Feb17_HO2-->



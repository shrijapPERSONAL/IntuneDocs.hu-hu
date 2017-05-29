---
title: "Előzetes kiadás | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>A Microsoft Intune előzetes kiadása – 2017. május

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
> A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Egyszeri bejelentkezés az iOS-es Céges portál alkalmazásból az iOS-re készült Outlookba <!--834012-->

Az iOS-es Váll. portál alkalmazásba bejelentkezett felhasználóknak már nem kell ugyanazon az eszközön, ugyanazzal a fiókkal bejelentkezniük az Outlook alkalmazásba is. Az Outlook indításakor kiválaszthatják a fiókjukat, és automatikusan bejelentkezhetnek. Ezt a funkciót igyekszünk további Microsoft-alkalmazásokba is beépíteni.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Továbbfejlesztett értesítés a Samsung KNOX indítási PIN-kódjaihoz <!--1087143-->

Amikor a végfelhasználóknak a titkosítási megfelelőség céljából be kell állítaniuk egy indítási PIN-kódot a Samsung KNOX rendszerű eszközeiken, a megjelenített értesítés átirányítja őket a Gépház alkalmazás megfelelő menüjébe az értesítésre való koppintáskor.  Korábban az értesítésre való koppintással a végfelhasználó a jelszómódosítási képernyőre került.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Az androidos Intune váll. portál legújabb verziójának népszerűsítése <!--1098661-->

A végfelhasználók alkalmazásbeli értesítést láthatnak az alkalmazás értesítési képernyőjén, ha az androidos Intune váll. portál új, ajánlott verziója megjelenik. Az értesítésben a rendszer tájékoztatja a felhasználókat arról, hogy „Az Intune váll. portál frissítése rendelkezésre áll”. Az értesítésre való koppintással egy olyan weboldal nyílik meg, amely azokat a rendelkezésre álló alkalmazásáruházakat jeleníti meg, ahonnan a felhasználók letölthetik a frissített verziót. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>A Windows 10 alkotói frissítésével való alkalmazás-szinkronizálás fejlesztései <!-- 676505 -->

Alkalmazástelepítési kérések esetén a Windows 10-es Munkahelyi portál automatikusan kezdeményez szinkronizálást a Windows 10 alkotói frissítésével (1704) rendelkező eszközökön. Ez csökkenti a függőben lévő szinkronizálás során feltorlódó alkalmazástelepítési műveletek számát. Emellett a felhasználók manuálisan is kezdeményezhetnek szinkronizálást az alkalmazásban. 

A Windows 10-es Munkahelyi portál alkalmazásban egy frissítési gomb is látható, amellyel a felhasználó szükség szerint frissítheti az alkalmazásban megjelenő tartalmat. 

## <a name="notices"></a>Értesítések

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->

Az Apple bejelentette, hogy 2017 tavaszától bizonyos követelményeket ír elő az Application Transport Security (ATS, alkalmazás átviteli biztonsága) esetében. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Appx-változások az Azure-beli Intune-ban <!-- 1000270 -->

Az Intune Azure-ra való migrálásának keretében három appx-változást vezetünk be:

1. Új, kizárólag MDM-be regisztrált eszközökre telepíthető appx-alkalmazástípus a klasszikus Intune-konzolon.
2. A korábbi appx-alkalmazástípussal mostantól csak a PC-s Intune-ügynökkel felügyelt PC-ket lehet célozni.
3. A migráció során az összes korábbi appx MDM-es appx-re konvertálódik.

A változás nincs hatással a PC-s Intune-ügynökkel felügyelt eszközökön telepített példányokra. A migráció után azonban a migrált appx-eket nem lehet további, a PC-s Intune-ügynökkel felügyelt és korábban nem célzott eszközökre telepíteni.

A migrálás után töltse fel újból az appx-et PC-s appx-ként, ha újabb PC-s telepítésekre készül. További tájékoztatást az Intune-ügyfélszolgálat blogján, az [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-változások az Azure-beli Intune-ban) című angol nyelvű bejegyzésben olvashat.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/intune/what-is-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Felügyelt konfigurációs lehetőségek támogatása androidos alkalmazásokhoz <!-- 621621 -->

Konfigurálhatja a Play áruházban lévő, felügyelt konfigurációs lehetőségeket támogató androidos alkalmazásokat az Intune-nal.  Ezzel a funkcióval megnézheti az egyes alkalmazásokban használható konfigurációs értékek listáját, és útmutatással ellátott, egyszerű felhasználói felületen konfigurálhatja ezeket az értékeket.

### <a name="remote-assistance-for-android-devices----675418---"></a>Távsegítség androidos eszközökhöz <!-- 675418 -->

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani az androidos eszközök felhasználóinak.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Az Android for Work-alkalmazások eszközengedélyeinek előzetes konfigurálása <!-- 621614 -->

Az Android for Work-eszközök munkahelyi profiljába telepített alkalmazások esetén konfigurálni lehet az egyes alkalmazások engedélyezési állapotát. Alapértelmezés szerint az eszközengedélyeket (például hozzáférés a tartózkodási hely adataihoz vagy az eszköz kamerájához) megkövetelő androidos alkalmazások felszólítják a felhasználókat az engedélyek elfogadására vagy elutasítására.  Például ha egy alkalmazás az eszköz mikrofonját használja, a rendszer felszólítja a végfelhasználót, hogy adjon engedélyt az alkalmazásnak a mikrofon használatára. Ezzel a funkcióval engedélyeket határozhat meg a végfelhasználó nevében.  A rendszergazda az alábbi műveletekhez állíthat be engedélyeket

- Automatikus elutasítás a felhasználó értesítése nélkül
- Automatikus jóváhagyás a felhasználó értesítése nélkül
- A felhasználó elfogadásra vagy elutasításra való felszólítása.

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Alkalmazásspecifikus PIN-kód meghatározása Android for Work-eszközökön <!--728976-->

Meghatározhat egy olyan PIN-kód-szabályzatot, amely csak Android for Work-eszközként felügyelt, Android 7.0 vagy újabb rendszerű eszközök munkahelyi profiljába telepített alkalmazásokra vonatkozik.  A lehetőségek a következők:

- Eszközre érvényes PIN-kód-szabályzat meghatározása – a végfelhasználónak ezt a PIN-kódot kell használnia az eszköz feloldására
- Munkahelyi profilra érvényes PIN-kód-szabályzat meghatározása – a rendszer a PIN-kód megadását kéri a végfelhasználótól a munkahelyi profilban található bármely alkalmazás megnyitásakor.
- Eszközre és munkahelyi profilra egyaránt érvényes szabályzat meghatározása – az informatikai részlegnek lehetősége van eszközre és munkahelyi profilra egyaránt érvényes, különböző erősségű PIN-kód-szabályzat meghatározására (például 4 számjegyből álló PIN-kód az eszköz feloldásához, illetve 6 számjegyből álló PIN-kód a munkahelyi alkalmazások megnyitásához)

>[!NOTE]
> Ez a funkció csak Android 7.0 vagy újabb rendszereken érhető el.  Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy dönthet úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használja.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Jelszavak és egyéb Android for Work-beállítások kezelése <!--1102534-->

Az új Android for Work-eszközkorlátozási szabályzattal kezelhetők az Android for Work-eszközök jelszó- és munkahelyiprofil-beállításai.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Új webtartalomszűrői szabályzat iOS-eszközökhöz <!-- 723832 -->

Az alábbi két módszer valamelyikével szabályozhatja, hogy az iOS-es eszközök felhasználói mely webhelyeket nyithatják meg:

  - Engedélyezett és letiltott URL-ek megadása az Apple beépített webtartalomszűrőjével
  - Csak a megadott webhelyek elérésének engedélyezése a Safari böngészőnek. Minden megadott webhelyhez könyvjelző jön létre a Safariban.

### <a name="apple-school-manager-asm-support---748864--"></a>Az Apple School Manager (ASM) támogatása <!--748864-->

Az Apple készülékregisztrációs programja helyett az Intune az Apple School Manager (ASM) használatával fogja támogatni az iOS-es eszközök alapértelmezett regisztrációját. ASM típusú beléptetésre van szükség a megosztott iPadek Osztályterem alkalmazásának használatához, valamint az adatok Microsoft School Data Sync (SDS) szolgáltatáson keresztüli szinkronizálásához az ASM és az Azure Active Directory között.  

### <a name="shared-ipad-support---770395-1044681---"></a>Megosztott iPadek támogatása <!--770395, 1044681 -->

Az Intune támogatni fogja a megosztott iPadek üzemmódjának konfigurálását az Apple készülékregisztrációs programjához vagy az Apple School Manager szolgáltatáshoz tartozó regisztrációs profilokban. Ezzel a beállítással több felügyelt Apple ID jelentkezhet be ugyanarra az eszközre.

Ki fogjuk bővíteni az iOS-es Osztályterem alkalmazás felügyeletének támogatását, így olyan diákok felügyeletére is lesz lehetőség, akik a megosztott iPadekre saját felügyelt Apple ID-val jelentkeznek be.

### <a name="new-windows-device-restriction-settings---978585--"></a>Új windowsos eszközkorlátozási beállítások <!--978585-->

A windowsos eszközkorlátozási profilt olyan beállításokkal bővítjük ki, amelyek a vezeték nélküli kijelzőkhöz, az eszközfelderítéshez, a feladatváltáshoz vagy a SIM-kártyák hibaüzeneteihez hasonló szolgáltatásokat szabályoznak.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Az Office 365 ProPlus-alkalmazások elérhetők a Windows 10-es eszközökön <!--1121362-->

Bevezetjük az Office 365 ProPlus-alkalmazástípust, amellyel egyszerűen végezheti el az Office 365 ProPlus-alkalmazások Windows 10-es eszközökhöz való hozzárendelését. Emellett lehetőség nyílik a Microsoft Project és a Microsoft Visio telepítésére is, ha rendelkezik hozzájuk való saját licencekkel. A kívánt alkalmazásokat a rendszer összecsomagolja, és azok egyetlen alkalmazásként jelennek meg az Intune-konzol alkalmazáslistájában.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Új engedélyezési/tiltási lista a Managed Browser alkalmazáshoz <!--682960-->

Az Intune alkalmazáskonfigurációs beállításaival az Azure Portalon konfigurálhatja a Managed Browser alkalmazás tartományokra és URL-címekre vonatkozó engedélyezési/tiltási listáját. Ezt a funkciót attól függetlenül lehet konfigurálni, hogy a Managed Browser felügyelt vagy nem felügyelt eszközön van-e használatban.

### <a name="new-app-configuration-capabilities----677969---"></a>Új alkalmazáskonfigurációs képességek <!-- 677969 -->

Ez a funkció megegyezik a mobileszköz-kezelés (MDM) alkalmazáskonfigurációs funkciójával. Lehetővé teszi a rendszergazdáknak a regisztrációs csatorna nélküli mobilalkalmazás-kezelési szolgáltatásban elérhető alkalmazásvédelmi szabályzatok alkalmazáskonfigurációs értékein túli alkalmazáskonfigurációs értékek alkalmazását.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>A MAM szolgáltatás alkalmazásvédelmi szabályzatainak új feltételei <!--679864-->

A felügyeleti konzolon nem regisztrált felhasználókra vonatkozóan olyan követelményeket állíthat be a MAM szolgáltatásban, amely az alábbiakat írja elő:

- Az alkalmazás minimális verziószáma
- Az operációs rendszer minimális verziószáma
- A megcélzott alkalmazás minimális Intune App SDK-verziószáma (csak iOS)

Ez a funkció Androidon és iOS-en egyaránt rendelkezésre áll. Az Intune támogatja az operációs rendszerek, az alkalmazások és az Intune App SDK minimális verziószámának kényszerítését. Az integrált SDK-val rendelkező iOS-es alkalmazások az SDK szintjén állíthatják be a minimális verziószám kényszerítését.

A felhasználó nem fog tudni hozzáférni a megcélzott alkalmazáshoz, ha az alkalmazásvédelmi szabályzat minimális követelményei a fenti 3 szinten nem teljesülnek. Ilyenkor a felhasználó eltávolíthatja a fiókját (többszörös identitást használó alkalmazások esetén), bezárhatja az alkalmazást, és/vagy az operációs rendszer vagy az alkalmazás verziójának frissítésével teljesítheti a követelményt.

Ezen túlmenően a felügyeleti konzol további beállításainak konfigurálásával nem zavaró értesítésben lehet javasolni a felhasználóknak az operációs rendszer vagy az alkalmazás frissítését. Az ilyen értesítéseket be lehet zárni, és az alkalmazás a megszokott módon használható.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Az MDM-szolgáltató módosítása a felügyelt eszközök regisztrációjának törlése nélkül <!--1103950-->

Anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. A Configuration Manager-konzolon módosíthatja az MDM-szolgáltatót a Configuration Manager (hibrid) beállításról Microsoft Intune (önálló) beállításra, vagy fordítva.


### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).


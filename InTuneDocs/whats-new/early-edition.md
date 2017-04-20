---
title: "Előzetes kiadás | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f051d8366ba9c6ca2183b5661c64087eb4cce9f0
ms.openlocfilehash: 682545af10a7dc1f66158f95f871b889e9f85c4a
ms.lasthandoff: 04/06/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>A Microsoft Intune előzetes kiadása – 2017. április

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
> A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Jobb telepítésiállapot-megjelenítés a Windows 10-es Céges portál alkalmazásban <!--676495-->

A Windows 10-es Céges portál alkalmazásban mostantól folyamatjelző sávok jelzik a Céges portálról indított alkalmazástelepítések állapotát.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Jobb állapotjelentések az iOS-es Céges portál alkalmazásban <!--744866-->

Az iOS-es Céges portál alkalmazásban mostantól új, konkrétabb hibaüzenetek nyújtanak kézzelfoghatóbb információt arról, hogy mi történik az eszközökön. Ezek a hibaesetek korábban egy általános, „A Munkahelyi portál átmenetileg nem érhető el” című hibaüzenetet váltottak ki. Ha pedig valaki internetkapcsolat nélkül indítja el a Céges portál alkalmazást iOS-en, akkor a kezdőlapon tartósan látható marad a „Nincs internetkapcsolat” feliratú állapotsáv.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>A MyApps elérhető a Felügyelt böngészőhöz is <!--822308, 822303-->

A Microsoft MyApps mostantól jobban működik a Felügyelt böngészőben. A Felügyelt böngésző felügyeletre ki nem jelölt felhasználói közvetlenül a MyApps szolgáltatásba kerülnek, ahol elérhetik a rendszergazda által nekik kiosztott SaaS-alkalmazásokat. Az Intune-felügyeletre kijelölt felhasználók továbbra is a Felügyelt böngésző beépített könyvjelzőjével érhetik el a MyApps szolgáltatást.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Új ikonok a Felügyelt böngészőhöz és a Céges portálhoz <!--918433, 918431-->

A Felügyelt böngésző androidos és iOS-es verziója egyaránt megújult ikont kap. Ezen az Intune új jelvénye szerepel, így egységesebb lesz az Enterprise Mobility + Security (EM+S) programcsomag alkalmazásainak arculata.

A Céges portál androidos, iOS-es és windowsos verziója is új ikont kap az EM+S többi alkalmazásával való összhang jegyében. Ezek az ikonok fokozatosan jelennek majd meg az egyes platformokon áprilistól május végéig.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Egyszeri bejelentkezés az iOS-es Céges portál alkalmazásból az iOS-re készült Outlookba <!--834012-->

Az iOS-es Céges portál alkalmazásba bejelentkezett felhasználóknak már nem kell ugyanazon az eszközön, ugyanazzal a fiókkal bejelentkezniük az Outlook alkalmazásba is. Az Outlook indításakor kiválaszthatják a fiókjukat, és automatikusan bejelentkezhetnek. Ezt a funkciót igyekszünk további Microsoft-alkalmazásokba is beépíteni.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Bejelentkezési folyamatjelző az androidos Céges portálhoz <!--953374-->

Az androidos Céges portál alkalmazás frissítésének köszönhetően bejelentkezési folyamatjelző jelenik meg, ha a felhasználó elindítja az alkalmazást vagy folytatja a használatát. A folyamatjelző új állapotokon halad végig, ezek időrendben a következők: „Csatlakozás...”, „Bejelentkezés...” és „Biztonsági követelmények keresése...” – a felhasználó ezt követően fér hozzá az alkalmazáshoz.


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

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

A változás nincs hatással a PC-s Intune-ügynökkel felügyelt eszközökön telepített példányokra. A migráció után azonban a migrált appx-eket nem lehet további, a PC-s Intune-ügynökkel felügyelt és korábban nem célzott eszközökre telepíteni.

#### <a name="what-action-do-i-need-to-take"></a>Mi a teendőm?

A migrálás után töltse fel újból az appx-et PC-s appx-ként, ha újabb PC-s telepítésekre készül. További tájékoztatást az Intune-ügyfélszolgálat blogján, az [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-változások az Azure-beli Intune-ban) című angol nyelvű bejegyzésben olvashat.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Felügyelt konfigurációs lehetőségek támogatása androidos alkalmazásokhoz <!-- 621621 -->

A Play áruházban lévő, felügyelt konfigurációs lehetőségeket támogató androidos alkalmazásokat az Intune-nal is lehet konfigurálni.  Ezzel a funkcióval az IT-részleg megnézheti az egyes alkalmazásokban használható konfigurációs értékek listáját, és útmutatásokkal ellátott, kiváló felhasználói felületen konfigurálhatják ezeket az értékeket.

### <a name="remote-assistance-for-android-devices----675418---"></a>Távsegítség androidos eszközökhöz <!-- 675418 -->

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani az androidos eszközök felhasználóinak.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Új androidos szabályzat komplex PIN-kódokhoz <!-- 722069 -->

5.0-s vagy újabb Android rendszerű eszközökhöz tartozó androidos eszközprofilban meg lehet adni a Komplex numerikus értéket kötelező jelszótípusként.  Ezzel a beállítással lehet megakadályozni, hogy a felhasználók ismétlődő vagy egymást követő számokból álló PIN-kódot (például 1111 vagy 1234) válasszanak.

### <a name="additional-support-for-android-for-work-devices"></a>Kibővített támogatás Android for Work-eszközökhöz

- **Jelszó- és munkahelyiprofil-beállítások kezelése** <!-- 612808 -->

  Az új Android for Work-eszközkorlátozási szabályzattal kezelhetők a felügyelt Android for Work-eszközök jelszó- és munkahelyiprofil-beállításai.

- **A munkahelyi és a személyes profilok közötti adatmegosztás engedélyezése** <!-- 1045102 -->

  Az Android for Work-eszközkorlátozási szabályzataiban használható **Munkahelyi és személyes profilok közötti adatmegosztás** beállítás új lehetőségekkel segíti a kétféle profil közötti adatmegosztás konfigurálását.

- **A munkahelyi és a személyes profilok közötti másolás és beillesztés korlátozása** <!-- 1046094 -->

  Az Android for Work-eszközök Intune-beli felügyelete során engedélyezve van a munkahelyi és a személyes profilok közötti másolás és beillesztés. Mostantól egy Android for Work-eszközökhöz készült egyéni eszközprofillal megszabhatja, hogy engedélyezi-e a munkahelyi és a személyes profilok közötti másolást és beillesztést.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Üzletági alkalmazások hozzárendelése iOS-es és androidos eszközökhöz <!-- 1057568 -->

Az iOS-re (.ipa-fájlok) és Androidra (.apk-fájlok) készült üzletági alkalmazásokat felhasználókhoz vagy eszközökhöz rendelheti hozzá.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Új szabályzatok iOS-es eszközökhöz <!-- 723774, 723815, 723826, 723830, 723832 -->

- **A kezdőképernyőn látható alkalmazások** – eszközszabályzattal definiálhatja, mely alkalmazásokat láthatják a felhasználók iOS-es eszközeik kezdőképernyőjén. Ez a szabályzat módosítja a kezdőképernyő elrendezését, de nem telepíti a megadott, de nem telepített alkalmazásokat.

- **Kapcsolódás AirPrint-eszközökhöz** – Intune-os eszközszabályzatban szabhatja meg, hogy mely AirPrint-eszközökhöz (hálózati nyomtatókhoz) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Kapcsolódás AirPlay-eszközökhöz** – Intune-os eszközszabályzatban szabhatja meg, hogy mely AirPlay-eszközökhöz (például AppleTV készülékekhez) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Egyéni üzenet a zárolási képernyőn** – Az alapértelmezett helyett egyéni üzenetet állíthat be az iOS-es eszköz zárolási képernyőjére.

- **Webtartalomszűrő** – Az alábbi két módszer valamelyikével szabályozhatja, hogy az iOS-es eszközök felhasználói mely webhelyeket nyithatják meg:

  - Engedélyezett és letiltott URL-ek megadása az Apple beépített webtartalomszűrőjével
  - Csak a megadott webhelyek elérésének engedélyezése a Safari böngészőnek. Minden megadott webhelyhez könyvjelző jön létre a Safariban.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS-alkalmazások leküldéses értesítéseinek korlátozása <!-- 723767 -->

Az Intune-os eszközkorlátozási profilokban a következő értesítési beállításokat konfigurálhatja iOS-es eszközökhöz:

- Adott alkalmazás értesítéseinek teljes körű be- vagy kikapcsolása
- Adott alkalmazás értesítési központban megjelenő értesítéseinek be- vagy kikapcsolása
- Riasztástípus megadása (**None** – Nincs, **Banner** – Szalag vagy **Modal Alert** – Modális riasztás)
- Jelvények engedélyezése az alkalmazásnak
- Értesítési hangok engedélyezése az alkalmazásnak.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-alkalmazások konfigurálása autonóm egyalkalmazásos módhoz <!-- 737837 -->

Intune-eszközprofillal konfigurálhatja az iOS-es eszközöket megadott alkalmazások autonóm egyalkalmazásos módban való futtatására. Ha ez a mód konfigurálva van, és az alkalmazást elindítják, az eszközön nem lehet másik alkalmazást futtatni. Célszerű például így konfigurálni az olyan alkalmazásokat, amelyekkel a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Megbízható tartományok konfigurálása levelezéshez és böngészéshez iOS-es eszközökön <!-- 723765 -->

Az iOS-es eszközkorlátozási profilokban a következő tartománybeállításokat konfigurálhatja:

- **Jelöletlen levelezési tartományok** – a felhasználó által az itt megadottól különböző tartománnyal küldött vagy fogadott e-mailek meg lesznek jelölve nem megbízhatóként.

- **Felügyelt webtartományok** – az itt megadott URL-címekről letöltött dokumentumok felügyeltnek minősülnek (csak a Safari esetében).  

- **Jelszavak automatikus kitöltése a Safariban** – a felhasználók csak olyan URL-eken menthetik jelszavaikat a Safariban, amelyek egyeznek az itt megadott mintákkal. Ez a beállítás csak felügyelt módú, többfelhasználós konfigurációval nem rendelkező eszközön használható. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>A VPP-alkalmazások elérhetőek az iOS-es Céges portálon <!-- 748782 -->

A mennyiségi vásárlási program keretében vásárolt (VPP) iOS-es alkalmazásokat **Elérhető** telepítésként hozzárendelheti végfelhasználókhoz, akik Apple Store-fiókkal telepíthetik az alkalmazást.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>E-könyvek szinkronizálása az Apple VPP Store-ból <!-- 800878 -->

Az Apple mennyiségi vásárlásra szolgáló áruházából vásárolt könyvek szinkronizálhatók az Intune-nal, és kioszthatók felhasználóknak.

### <a name="shared-shift-worker-devices-for-samsung-knox-standard-devices----773753---"></a>Több műszakban, közösen használt Samsung KNOX Standard-eszközök <!-- 773753 -->

A Samsung KNOX Standard rendszerű eszközöket az Intune-portálon konfigurálhatja több műszakban, közösen használt eszközökként. A közös módba kerülő eszközön az alkalmazások, a szabályzatok és a levelezés a Céges portálra bejelentkező felhasználó identitásához kötődnek.
A felhasználók Azure Active Directory-beli hitelesítő adataikkal jelentkezhetnek be a Céges portál alkalmazásba. Alkalmazásaik, szabályzataik és e-mail-beállításaik automatikusan érvénybe lépnek az eszközön.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Többfelhasználós felügyelet a Samsung KNOX Standard-eszközökön <!-- 971988 -->

A Samsung KNOX Standard rendszerű eszközökön mostantól használható az Intune többfelhasználós felügyelete. Ilyenkor a felhasználók Azure Active Directory-beli hitelesítő adataikkal jelentkezhetnek be és ki az eszközön, de az központi felügyelet alatt marad, akár használatban van, akár nem.  A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

### <a name="additional-windows-device-restriction-settings----818566---"></a>További windowsos eszközkorlátozási beállítások <!-- 818566 -->

További windowsos eszközkorlátozási beállításokat tettünk elérhetővé, például bővült az Edge böngésző támogatása, testre szabható az eszközök zárolási képernyője és Start menüje, szabályozható a Windows Reflektorfény háttérképkészlete, illetve a proxybeállítások.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Többfelhasználós támogatás a Windows 10 alkotói frissítéséhez <!-- 822547 -->

A többfelhasználós felügyelet támogatását kiterjesztettük a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökre. Az eszközre minden egyes, AAD-s hitelesítő adataival bejelentkező felhasználó a saját felhasználónevéhez rendelt alkalmazásokat és szabályzatokat kapja meg.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Újrakezdés művelet Windows 10-es PC-khez<!-- 1004830 -->

Ebben a verzióban mutatkozik be a Windows 10-es PC-ken használható Újrakezdés eszközművelet,  amely eltávolítja a PC-re telepített alkalmazásokat, és automatikusan a Windows legújabb verziójára frissíti a gépet. Így egyszerűbben eltávolíthatók az új gépeken gyakran előtelepítve megtalálható számítógépgyártói (OEM) alkalmazások. A konfigurációval meg lehet adni, hogy a művelet a felhasználói adatokat is eltávolítsa-e.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>További Windows 10-es frissítési útvonalak <!-- 903672 -->

Mostantól olyan kiadásfrissítési szabályzatok is létrehozhatók, amelyekkel az alábbi Windows 10-kiadásokra frissíthetők az eszközök:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-es eszközök tömeges regisztrálása <!-- 747607 -->

IT-automatizálási eszközökkel nagy számú Windows 10-es eszközt lehet az Azure Active Directoryhoz és az Intune-hoz csatlakoztatni. Ha Azure AD-bérlőjéhez be szeretné kapcsolni az automatikus MDM-regisztrációt, a Windows Configuration Designerrel hozzon létre olyan kiépítési csomagot, amely csatlakoztatja az eszközt az Azure AD-bérlőhöz. A csomagot alkalmazza a regisztrálni és felügyelni kívánt, vállalati tulajdonú eszközökre.  Ezt követően az eszközök csatlakoznak az Azure AD-hez, regisztrálnak az Intune-ban, és készen állnak az Azure AD-felhasználók bejelentkezésére.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Új MAM-beállítások a PIN-kódhoz és a felügyelt tárolóhelyekhez <!-- 58112, 736644 -->

Két új alkalmazásbeállítás segíti a mobileszköz-felügyeletet (MAM):

- **Disable app PIN when device PIN is managed** (Alkalmazás PIN-kódjának letiltása felügyelt eszköz-PIN-kód esetén) – a rendszer észleli, hogy van-e eszköz-PIN-kód a regisztrált eszközön, és ha van, mentesíti a felhasználót az alkalmazásvédelmi szabályzatok által megkövetelt alkalmazás-PIN-kód megadása alól, ily módon kevesebbszer kell PIN-kódot megadni a regisztrált eszközökön a MAM-mal védett alkalmazások megnyitásakor. A funkció Androidon és iOS-en egyaránt elérhető.

- **A társzolgáltatások kijelölése, melyekbe menthetők a vállalati adatok** – itt lehet megadni, hogy mely tárolóhelyekre mentse a rendszer a vállalati adatokat. A felhasználók csak a kijelölt tárolóhelyekre menthetnek, a fel nem sorolt tárolóhelyek tehát le lesznek tiltva.

  A támogatott tárhelyszolgáltatások:

  - OneDrive
  - Vállalati SharePoint Online
  - Helyi tárhely


### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).


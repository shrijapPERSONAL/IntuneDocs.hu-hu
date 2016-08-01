---
title: "Korábbi kiadások | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b812a3124c330a9b45378c99ee77959c8d7bc537
ms.openlocfilehash: b30ab535ac7d8b10e3feef52ab01a68ba8572dba


---

# Az Intune korábbi kiadásai
## 2016. június
### Az Intune szolgáltatás állapota
Az Intune-ra vonatkozó szolgáltatásállapot-adatok átkerültek a központi, a többi Microsoft-szolgáltatásról is információt nyújtó helyre. Ezt az információt mostantól az Office 365 felügyeleti portál Szolgáltatás állapota menüjében találja meg. További információkat [ebben a blogban](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) talál.

### Alkalmazáskezelés
- **Továbbfejlesztett konfigurációs felület a Windows 10 vállalati adatkezelési házirendjéhez.** Továbbfejlesztettük a Windows 10 vállalati adatkezelési házirendjének konfigurációs felületét az alkalmazásszabályok létrehozása, a hálózathatár-definíciók megadása és más vállalati adatvédelmi beállítások tekintetében. További tudnivalók: [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Enterprise Data Protection-házirend létrehozása a Microsoft Intune-nal).


### Eszközkezelés
- **Windows Defender-házirendbeállítása a vélhetően nemkívánatos alkalmazások elleni védelem biztosításához.** A Windows Defender egy új, **Potentially Unwanted Application Detection** (Vélhetően nemkívánatos alkalmazás észlelése) nevű beállításával bővült a Windows 10 asztali és mobil verziójának általános konfigurációs házirendje. Ezzel a beállítással biztosíthatja a regisztrált Windows rendszerű asztali számítógépek védelmét a Windows Defender által a vélhetően nemkívánatos osztályba sorolt szoftverek futtatása ellen. Biztosíthatja a védelmet ezen alkalmazások futtatása ellen, vagy a vizsgálati üzemmóddal jelentést készíthet a vélhetően nemkívánatos alkalmazások telepítéséről. További információ: [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) (A Windows 10 házirendbeállításai a Microsoft Intune-ban).
<!---TFS 1244478--->

### Feltételes hozzáférés
- **Cisco ISE-hálózati hozzáférés-vezérlési szabályzat az Intune-hoz.**  Azok az ügyfelek, akik a Cisco Identity Service Engine (ISE) 2.1 szolgáltatást, illetve a Microsoft Intune-t is használják, a hálózati hozzáférés-vezérlési szabályzatot beállíthatják az ISE szolgáltatásban.

    Ezen szabályzat használatakor azoknak az eszközöknek, melyeknek Wi-Fi vagy VPN használatával kell kapcsolódniuk a hálózathoz, meg kell felelniük a következő feltételeknek a hozzáférésük engedélyezéséhez:

    * Az Intune által felügyeltnek kell lenniük
    * Meg kell felelniük az Intune összes telepített megfelelőségi szabályzatának

 A nem megfelelő eszközökkel rendelkező végfelhasználókat kérni fogja a rendszer, hogy regisztráljanak, és hárítsák el a megfelelőségi problémákat, hogy hozzáférést kapjanak.
- **Feltételes hozzáférés böngészőhöz.** Feltételes hozzáférési házirendet állíthat be az [Exchange Online-hoz](restrict-access-to-exchange-online-with-microsoft-intune.md) és a [SharePoint Online-hoz](restrict-access-to-sharepoint-online-with-microsoft-intune.md), így azok csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök támogatott webböngészőiről érhetők majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **A Dynamics CRM Online támogatja a feltételes hozzáférést.** Feltételes hozzáférési házirendet állíthat be a [Dynamics CRM Online-hoz](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md), hogy csak a felügyelt és a szabályozásnak megfelelő iOS- és Android-eszközök érhessék el. A Dynamics CRM mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés végrehajtása előtt a rendszer kérni fogja a regisztrálást az Intune-ba, valamint a meg nem felelést okozó problémák megszüntetését.
<!---TFS1295358--->

##A Vállalati portál újdonságai

#### Androidos Munkahelyi portál alkalmazás

- Ha a rendszergazdák az új „Az eszközök tiltsák le az ismeretlen forrásból származó alkalmazások telepítését (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az ismeretlen forrásokból származó alkalmazások telepítését le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Biztonság** menüben ki kell kapcsolniuk az **Ismeretlen források** lehetőséget. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Futtasson biztonsági fenyegetés elleni keresést az eszközön” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Google** > **Biztonság** menüben be kell kapcsolniuk a **Biztonsági fenyegetések keresése az eszközön** beállítást. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak az üzenetről és a beállítás bekapcsolásának okáról.

- Ha a rendszergazdák az új „Az USB-hibakeresés letiltásának megkövetelése (Android 4.2+)” házirendet alkalmazzák, az Android 4.2-vel és későbbi verziókkal rendelkező végfelhasználók számára „Az USB-hibakeresést le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Fejlesztői beállítások** menüben ki kell kapcsolniuk az **USB-hibakeresést**. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0+)” házirendet alkalmazzák, az Android 6.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az eszköz nem éri el a minimális Android biztonsági javítási szintet” üzenet jelenik meg. A felhasználóknak ekkor telepíteniük kell a szükséges biztonsági javítási szintet. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak a biztonsági javítás telepítéséről és arról, hogy jelenleg melyik biztonsági javítási verzióval rendelkeznek.

#### iOS rendszerű Vállalati portál alkalmazás

- A végfelhasználó számára az üzleti alkalmazások telepítésekor egy továbbfejlesztett környezet jelenik meg. Ha az alkalmazás telepítése hosszú ideig tart, a felhasználók manuálisan szinkronizálhatják az eszközt a szinkronizálási folyamat kényszerített folytatásához. A végfelhasználói lépéseket [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Az iOS-eszköz manuális szinkronizálása) című szakaszban tekintheti meg.

- Az iOS rendszerhez készült Microsoft Intune Vállalati portál alkalmazás frissült, így már támogatja az iOS 8.0-s és újabb verzióit. A frissítés eredményeként a végfelhasználók csak akkor tudják telepíteni a Vállalati portál alkalmazást, és regisztrálni új eszközöket az Intune-ban, ha az eszközön az iOS 8.0-s vagy újabb verziója fut. Az iOS nem támogatott verzióját futtató eszközöket korábban regisztrált felhasználók továbbra is használhatják az eszközükön lévő Vállalati portál alkalmazást.


## 2016. május

Mindezek a funkciók hibrid telepítések esetén is támogatottak (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok](https://technet.microsoft.com/en-us/library/mt718155.aspx) oldalát.

### Dokumentáció
A [docs.microsoft.com](https://docs.microsoft.com/en-us/intune) előzetes kiadása üdvözli Önt!
Ez a teljesen új, modern tartalomplatform azért jött létre, hogy Ön, ügyfelünk egyszerűbben megismerje és hatékonyabban használhassa az Intune-t.
Ha szeretne tájékozódni az összes új funkcióról, keresse fel az [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (A docs.microsoft.com bemutatása) című weblapot.

### Az Intune szolgáltatás állapota
Az Intune-ra vonatkozó szolgáltatásállapot-adatok átkerültek a központi, a többi Microsoft-szolgáltatásról is információt nyújtó helyre. Ezt az információt mostantól az [Office 365 felügyeleti portál](https://portal.office.com/Admin/Default.aspx) **Szolgáltatás állapota** menüjében találja meg.
További információkat [ebben a blogban](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) talál.


### Alkalmazáskezelés
- **MAM SDK: PIN-kód hosszának konfigurálása.** A mobilalkalmazás-felügyeleti (MAM-) alkalmazásoknál az eszközök PIN-kódjához hasonlóan meghatározható lesz a PIN-kód hossza. Ebben az esetben a végfelhasználóknak meg kell felelniük a beállított új korlátozásoknak. A felhasználók számára kissé más képernyő jelenik meg a hosszabb PIN-kód beviteléhez. Részletekért lásd: [Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban](/intune/deploy-use/android-mam-policy-settings) és [iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása](/intune/deploy-use/ios-mam-policy-settings).

- **Skype Vállalati verzió Androidra és iOS-re.** Mostantól a Skype Vállalati verziót is beállíthatja [mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási szabályzatok nélkül](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-szabályzatokat.

- **MAM-szabályzatokkal való felügyeletre alkalmas új alkalmazások.** Az androidos Microsoft Word, Excel és PowerPoint alkalmazáshoz mostantól az Intune-ban nem regisztrált eszközökön is MAM-szabályzatok társíthatók. A támogatott alkalmazások teljes listájának megtekintéséhez keresse fel a Microsoft Intune mobilalkalmazás-galériát a [Microsoft Intune alkalmazáspartnerek](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) oldalán.


### A Vállalati portál újdonságai

#### Androidos Munkahelyi portál alkalmazás
- **Végfelhasználói bejelentési értesítések**: a végfelhasználók mostantól bejelentési értesítést kapnak az androidos Vállalati portál alkalmazástól, amikor regisztrálják eszközüket a Vállalati portálon, illetve, amikor eltávolítják eszközüket a portálról.

- **Változások a készülékregisztráció-kezelői fiókokban az androidos Vállalati portál alkalmazásban.** A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM-) eszközt az androidos Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.

#### Munkahelyi portál webhely
- **Vállalati portál webhely: az eszközazonosító sáv több információt nyújt a végfelhasználók számára.** A végfelhasználók mostantól könnyebben azonosíthatják a választott eszközt a Vállalati portál webhelyen. Ha nem jól választottak, a kezdőlapi sávon a **Koppintson ide** hivatkozással kijelölhetik a megfelelő eszközt.

## Mi várható?
- **Az üzenetközpont felhasználói felület bevezetése**. Az Intune-nak az [Office 365 felügyeleti portálra](https://portal.office.com/) való áttelepítése keretében az Office 365 üzenetközpontját fogjuk használni az új funkciókkal kapcsolatos és egyéb típusú értesítések küldéséhez. Emellett az Office 365 Admin felügyeleti társalkalmazás telepítésével mobiltelefonos értesítéseket kaphat, és egyszerűen továbbíthat bármilyen üzenetet a felhasználóknak vagy egy terjesztési célú aliasra.
Az üzenetközpontot a májusi kiadással kezdjük el használni, és a továbbiakban itt értesítjük a felhasználókat a frissítések elkészültéről, valamint az Intune új és továbbfejlesztett funkcióiról. Az üzenetközpont megtekintéséhez jelentkezzen be az [Office 365 felügyeleti portálra](https://portal.office.com/), és a bal oldali navigációs ablakból válassza az ÜZENETKÖZPONT elemet.

- **A készülékregisztráció-kezelő (DEM-) fiókok változásai**. A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az **összes** készülékregisztráció-kezelő (DEM-) eszközt az iOS-es Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre. Emellett az Intune-ból kivezettük a DEM-fiókoknak az Apple Device Enrollment Programmal és az Apple Configurator eszközzel való használatát. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását. Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.

### A felhőplatform ütemterve
Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával.

### Szolgáltatások érvénytelenítése
- **Intune Viewer-alkalmazások** Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer Android-eszközökre a Google Play Áruházból

  Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. További információk az RMS-megosztó alkalmazásról (a dokumentációra mutató hivatkozással).

- **Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.**
Az Intune értesítési szabályai határozzák meg, hogy kinek küld értesítő e-mailt az Intune. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016. június 1-jétől fogva a felhasználó által létrehozott csoportok megcélzása nem lesz megvalósítható.

    Ma a következő lépések szükségesek ahhoz, hogy egy értesítési szabállyal egy Ön által létrehozott csoportot célozzon meg a Microsoft Intune felügyeleti konzoljában:

    A **Felügyelet** munkaterületen kattintson az **Értesítési szabályok** > **Új szabály létrehozása** elemre.

    Az Értesítési szabály létrehozása varázsló második lépésében válassza ki a szabály által megcélzott eszközcsoportokat. Ez az eszközcsoportok kiválasztására szolgáló lépés a jövőben nem lesz elérhető az Intune-konzolon.

    A módosítás előzetes ütemterve a következő:
    - 2016 júniusától az új bérlők számára nem fog megjelenni az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
    - 2016 augusztusától kezdve egyes meglévő bérlők számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.
    - 2016 októberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.


- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**. Néhány hónapon belül meg fog jelenni egy frissítés az iOS-es Microsoft Intune Vállalati portál alkalmazáshoz, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az iOS 8.0-s verziójánál régebbi rendszerű új eszközöket ettől kezdve nem lehet majd regisztrálni. Az iOS 8.0-s verziójánál régebbi rendszerű, de korábban már regisztrált eszközök korlátozott ideig még felügyelhetők, és használhatják a Vállalati portál alkalmazást. A Vállalati portál alkalmazás legújabb verzióját azonban csak az iOS 8.0-s vagy újabb rendszerű eszközök fogják tudni elérni. Javasoljuk, hogy értesítse a felhasználókat, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0 rendszerre.  


## 2016. április
Mindezeket a funkciókat a hibrid ügyfelek is támogatják (tehát az Intune-nal integrált Configuration Manager is).
### Alkalmazáskezelés
- **A felhasználók mobilalkalmazás-felügyeleti megfelelősége.**
Már az Azure Active Directory- (AAD-) bérlőben szereplő bármely felhasználónál megtekintheti az alkalmazásfelügyeleti házirendek [állapotát](monitor-mobile-app-management-policies-with-Microsoft-Intune.md). Ez a következő teendőket foglalja magában:
   - Eszközök
   - Alkalmazások az eszközön

   Az állapot a következő értékeket veheti fel:

   **Beadva**: azt jelzi, hogy a házirend telepítve van a felhasználónál, az alkalmazást pedig használták munkahelyi környezetben, és sikeresen megkapta a házirendet.

    **Nincs beadva:** azt jelzi, hogy a házirend telepítve van a felhasználónál, de az alkalmazást egyszer sem használták a munkahelyi környezetben.


- **Az Outlook-névjegyek szinkronizálásának megakadályozása mobilalkalmazás-felügyelettel (Android).**
Új beállítás érhető el a [mobilalkalmazások eszközregisztráció nélküli felügyeletéhez](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md). Ezzel a beállítással megakadályozhatja, hogy az alkalmazás szinkronizálja a névjegyeket a natív címjegyzékbe az Android-eszközökön. Ha a beállítás engedélyezve van, a megcélzott alkalmazások nem menthetnek névjegyeket a natív címjegyzékbe. Ha a beállítás nincs engedélyezve, a megcélzott alkalmazások menthetik a névjegyeket a natív címjegyzékbe. Amikor [távolról törli egy eszköz vagy alkalmazás tartalmát](wipe-managed-company-app-data-with-Microsoft-Intune.md), a natív címjegyzék mentett összes névjegy törlődni fog. Ezt az új beállítást már az Android-eszközökön elérhető Outlook alkalmazás is támogatja.

### Eszközkezelés
- **A céges eszközök telefonszámos azonosítása.** A „Céges” eszközként besorolt telefonokat a rendszer már a teljes telefonszámukkal azonosítja, például amikor jelentést készít a mobileszközkészletről. A BYOD-eszközök telefonszámai továbbra is **** karakterekkel maszkolva, csak az utolsó 4 számjegyükkel jelennek meg.


### A Vállalati portál újdonságai
**Androidos Vállalati portál alkalmazás** Azok a felhasználók, akik nem regisztrálták az eszközüket az Intune-ban, és akiknél nincs telepítve a megfelelő tanúsítvány, nem jelentkezhetnek be az androidos Vállalati portál alkalmazásba. Náluk a következő üzenet jelenik meg: „Nem tud bejelentkezni, mert az eszközön hiányzik egy szükséges tanúsítvány.” Az üzenettel együtt megjelenő „Útmutató a probléma megoldásához” hivatkozással a felhasználó megtekintheti a tanúsítvány telepítési lépéseit. A probléma megoldásának lépéseit [Az eszközhöz hiányzik egy szükséges tanúsítvány](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) című cikkben találhatja.

**iOS Vállalati portál alkalmazás**A kezdőképernyőn szereplő tartalmak, például a felsorolt alkalmazások, eszközök és az informatikusok elérhetőségi adatai már lefelé húzással is frissíthetők. A lehúzásos frissítési művelet a megfelelőséggel és házirenddel kapcsolatos adatokat nem ellenőrzi – ez az aktuális eszköz csempéjének kijelölésével és a **Szinkronizálás** gombbal végezhető el.

**Windows 10 Mobile és Windows Phone 8.1 Vállalati portál alkalmazás** A végfelhasználó számára az üzleti alkalmazások telepítésekor egy továbbfejlesztett környezet jelenik meg. Ha az alkalmazás telepítése hosszú ideig tart, a felhasználók manuálisan szinkronizálhatják az eszközt a szinkronizálási folyamat kényszerített folytatásához. A végfelhasználói lépések az [Eszköz manuális szinkronizálása a lassú alkalmazástelepítések felgyorsítása érdekében](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) című cikkben találhatók.

**Vállalati portál webhelye** A Windows 10 Mobile- és a Windows Phone 8.1 -felhasználók az üzleti alkalmazások telepítésekor a következő új állapotokat láthatják, amelyek több részlettel szolgálnak számukra a telepítés előrehaladásáról:

* **Várakozás az eszköz szinkronizálására** – A felhasználó a „Telepítés” gombra kattintott, az eszköz pedig most megpróbál szinkronizálni az Intune-infrastruktúrával. A szinkronizálás szükséges a telepítés folytatásához. A „Várakozás az eszköz szinkronizálására” üzenet egyben hivatkozás is, amellyel a felhasználó megtekinthet egy [útmutatást](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) arról, hogyan szinkronizálhatja manuálisan az eszközét az Intune-nal, ha a szinkronizálási folyamat túl sokáig tart vagy elakad.
* **Letöltés** – A felhasználó letöltési kérelme feldolgozás alatt áll, az eszközön pedig folyamatban van az alkalmazás letöltése és telepítése.

A fenti állapotok megjelenése előtt a felhasználónál zavart okozhatott, ha egy alkalmazás telepítése hosszú ideig tartott, ugyanis csak a „Telepítés” állapotot láthatta, amely akár órákig is a képernyőn maradhatott. Az új állapotok bevezetésével a felhasználó a támogatási szolgálat felkeresése helyett a „Várakozás az eszköz szinkronizálására” hivatkozásra kattinthat, és az útmutatást követve folytatásra kényszerítheti a szinkronizálási folyamatot.


## 2016. március
### Újdonságok 2016. március 29-én
A Windows 10-hez tartozó általános konfigurációs házirend frissítésének kivételével a 2016. március 29-én kiadott összes szolgáltatás a hibrid ügyfelek (Intune-nal integrált Configuration Manager) esetében is támogatott. A Windows 10 általános konfigurációs házirendjének hibrid támogatása hamarosan elérhető lesz. Vegye figyelembe, hogy a felsorolt szolgáltatások némelyikéhez a Configuration Manager legújabb verziójára lehet szükség.

### Alkalmazáskezelés
- **A MAM felügyeletével elkerülhető az Outlook-névjegyek szinkronizálása (iOS).** Új beállítás érhető el az eszközregisztráció nélküli mobilalkalmazás-kezeléshez. Ezzel a beállítással megakadályozhatja, hogy az alkalmazás szinkronizálja a névjegyeket a natív címjegyzékbe az iOS-eszközökön. Ha a beállítás engedélyezve van, az alkalmazás nem tudja menteni a névjegyeket a natív címjegyzékbe. Ha a beállítás nincs engedélyezve, az alkalmazás menteni tudja a névjegyeket a natív címjegyzékbe. Amikor szelektív módon törli egy eszköz tartalmát, a natív címjegyzékbe mentett összes névjegy törlődni fog. Ez az új beállítást az Outlook alkalmazás támogatja az iOS-eszközökön. Az új beállítással és az egyéb beállításokkal kapcsolatban további információt a [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése](https://technet.microsoft.com/en-us/library/dn292747.aspx) című témakörben találhat.

### Hozzáférés-vezérlés
- **A Skype Vállalati online verzió támogatja a feltételes hozzáférést.** Beállíthat feltételes hozzáférési házirendet a Skype Vállalati online verzióhoz, hogy csak a felügyelt és megfelelő iOS- és Android-eszközök férhessenek hozzá. A Skype Vállalati online verzió mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés végrehajtása előtt a rendszer kérni fogja a regisztrálást az Intune-nal, valamint a nem megfelelést okozó problémák megszüntetését. Részletes leírás: [A Skype Vállalati online verzióhoz való hozzáférés kezelése](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Eszközkezelés
- **Intune-támogatás az iOS 9.3-as verzióhoz.** Az Apple március 21-én, hétfőn jelentette be az iOS 9.3 megjelenését. Komoly erőfeszítéseket tettünk azért, hogy a Microsoft Intune kompatibilis legyen az Apple mobil operációs rendszerének legújabb verziójával, és [örömmel jelenthetjük be, hogy az Intune már támogatja az iOS 9.3-as verzióval működő eszközöket](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  A jelenleg rendelkezésre álló iOS-eszközökhöz elérhető összes meglévő Intune-szolgáltatás továbbra is problémamentesen fog működni, amikor a felhasználók az iOS 9.3-as verzióra frissítik az eszközeiket. Ezenkívül az iOS 9.3-as verziót már a hibrid ügyfelek (Intune-nal integrált Configuration Manager) is támogatják.

- **A Windows 10 általános konfigurációs házirendje már tartalmazza a Windows Defendernek a Windows 10 rendszerrel működő regisztrált számítógépeken történő kezeléséhez szükséges beállításokat.** Részletes leírás: [A Windows 10 konfigurációs házirendjének beállításai a Microsoft Intune-ban](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Vállalati portál

- **A Windows-alkalmazáscsomagok közvetlenül elérhetők a Vállalati portál webhelyén.** A Windows 8, a Windows 8.1 és a Windows RT rendszerű számítógépek felhasználói most már közvetlenül a Vállalati portál webhelyéről telepíthetik a Windows-alkalmazáscsomagokat (.appx kiterjesztés). Korábban az alkalmazások telepítéséhez Önnek kellett központilag telepítenie, vagy a felhasználóknak az eszközeikre kell telepíteniük a Vállalati portál alkalmazást.

- **A felhasználók a Vállalati portál webhelyén távolról zárolhatják az eszközeiket.** Egy új távoli zárolási beállítás lett elérhető a Vállalati portál webhelyen, amellyel a felhasználók a portálon távolról zárolhatják az eszközeiket azok elvesztése vagy ellopása esetén. Lásd a [végfelhasználóknak szóló utasításokat](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). A következő táblázat a távoli zárolás platformtámogatását sorolja fel a különálló Intune és a Configuration Managerrel együtt használt Intune esetében.

|Platform | Támogatás részletei|
|---------|----------------|
|Android |Támogatott|
|iOS |Támogatott|
|Windows 10 mobil verzió |Csak beállított jelszóval rendelkező telefonok esetén támogatott|
|Windows 10 asztali verzió |Nem támogatott|
|Windows Phone 8.1 |Csak beállított jelszóval rendelkező telefonok esetén támogatott|
|Windows Phone 8.0 |Nem támogatott|
|PC (Windows 8.0 és korábbi verziók) |Nem támogatott|
|PC (Windows 8.1) |Nem támogatott|

### Újdonságok 2016. március 10-én

### Alkalmazáskezelés

- **Éljen az iOS harmadik fél által nyújtott, MDM-megoldásokban regisztrált eszközök „Megnyitás ezzel” típusú kezelésének előnyével** A harmadik felek által nyújtott mobileszköz-kezelési forgalmazójával kihasználhatja az iOS „Megnyitás ezzel” típusú kezelését. Korlátozásokat állíthat be a konfigurációs profil beállításaiban, és az [iOS-alkalmazások közti adatátvitel kezelésével](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) telepítheti az alkalmazást.

     Ez a módszer két fő előnnyel jár:

     1. A felhasználóknak be kell jelentkezniük a munkahelyi fiókjukkal, mielőtt hozzáférhetnének a szervezeti adatokhoz a Cloud Services szolgáltatásokból vagy más alkalmazásokból. Ez biztosítja, hogy mobilalkalmazás-kezelési (MAM-) házirendek legyenek érvényben az adatok elérésekor.

     2. A külső MDM-megoldással telepített felügyelt e-mail-profilok és más felügyelt alkalmazások fájlokat és adatokat oszthatnak meg az Intune MAM-szabályzatokkal rendelkező alkalmazásokkal.

- **A Microsoft Outlook alkalmazás kezelése MAM-szabályzatokkal az Intune-ban nem regisztrált eszközökön** Mostantól az Intune mobilalkalmazás-kezelési szabályzatával kezelheti a Microsoft Outlook alkalmazást az Intune-ban nem regisztrált eszközökön. A frissített Microsoft Outlook alkalmazás a MAM-képességekkel az [iOS-](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) és [Android-](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)eszközökhöz is elérhető. A [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése](https://technet.microsoft.com/library/mt627829.aspx) témakörben található utasításokkal hozzon létre egy MAM-házirendet.  


- **A mobilalkalmazások konfigurációs szabályzataival rugalmasabban szabhatja meg az iOS-alkalmazások felhasználói adatait** Megadhat olyan felhasználói beállításokat, amelyekre az iOS-alkalmazásoknak szükségük lehet a megnyitásukkor. Megadhat például egy hálózati portot vagy egy felhasználónevet. Részletes leírás: [iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Az Adobe Reader for Microsoft Intune telepítése a vállalata Intune-ban kezelt iOS-eszközeire ** Az Adobe Reader iOS-alkalmazás már regisztrált eszközökön is kezelhető az Intune mobilealkalmazás-kezelési házirendjével.

- **A telepített webklipeknek a felügyelt böngészőben való megnyitása** Célzott webklipeket telepíthet, amelyek csak a felügyelt böngészővel nyithatók meg az iOS- és Android-eszközökön. Vállalati erőforrásokra mutató hivatkozásokat telepíthet például a Vállalati portálon keresztül, és amikor a felhasználók megnyitják a hivatkozásokat, azok közvetlenül a felügyelt böngészőben nyílnak meg, ahol a MAM-házirend védi őket. Részletes leírás: [Alkalmazások telepítése](deploy-apps.md).


- **Windows 10-eszközökre készült Vállalati Windows Áruház alkalmazásainak keresése, kezelése és elosztása az Intune rendszergazdai konzolból** Az Intune támogatást nyújt a Vállalati Windows Áruházhoz, így könnyebben kereshet, kezelhet és oszthat el alkalmazásokat a kezelt Windows 10-eszközei között. A Vállalati Windows Áruházzal kezelheti ezen alkalmazások telepítését és megfigyelését az Intune felügyeleti konzoljáról – ugyanarról a konzolról, amellyel a többi alkalmazást is kezeli. A Vállalati Windows Áruház az „online licencelt alkalmazások” tartalmát és licencelését felügyeli. Részletes leírás: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Eszközkezelés
- **PFX-tanúsítványok elosztása iOS-eszközökön** Az Intune-rendszergazdák iOS PFX-tanúsítványokat hozhatnak létre és telepíthetnek a Wi-Fi-, e-mail- és VPN-hitelesítéshez az iOS-eszközökön. Ez a funkció már elérhető az Android- és Windows 10-es eszközökhöz. Részletes leírás: [Vállalati erőforrások elérésének lehetővé tétele tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md).


- **Alkalmazások és házirendek alkalmazása különböző eszközcsoportokra a felhasználói kategóriák alapján** Az Intune-rendszergazdák mostantól egyéni eszközkategóriákat határozhatnak meg, amelyekből a felhasználók válogathatnak a regisztrálás során. A rendszergazdák például azt kívánhatják, hogy a felhasználóik adják meg, hogy a „Pénztárhoz”, „Szállítójárműhöz” vagy „Leltárhoz” használt eszközt regisztrálnak-e. A kiválasztott kategória miatt az eszköz egy Intune-eszközcsoport tagjává válik, amely különböző alkalmazások és házirendek a regisztrált eszközre való telepítéséhez használható. Részletes leírás: [Eszközök kategorizálása eszközcsoport-leképezéssel](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### A Microsoft Munkahelyi portál szolgáltatásának módosításai és frissítései
Ebben a kiadásban a következő módosításokat vezettük be a Munkahelyi portál szolgáltatásban.

**Androidos Munkahelyi portál alkalmazás**

* Amikor a felhasználók mobilalkalmazás-kezeléssel felügyelt alkalmazást indítanak, egy üzenetet látnak, amely értesíti őket, hogy az alkalmazást a vállalatuk felügyeli. A felhasználók mostantól a „További információk” hivatkozásra koppintva [további információhoz](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) juthatnak arról, mit jelent a „felügyelt alkalmazás”. Vagy ha a „Ne jelenjen meg ismét” lehetőségre koppintanak, az üzenet többé nem jelenik meg az alkalmazás elindításakor.
* Új képernyők vezetik végig a felhasználókat a regisztrálási folyamaton és nyújtanak további információt arról, hogy a felhasználóknak miért érdemes regisztrálniuk, valamint hogy az informatikai rendszergazdák mit láthatnak és mit nem láthatnak a regisztrált eszközökön. A részleteket lásd: [Regisztrációs utasítások](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* A regisztrációs hibaüzenetek mostantól megjelennek a Munkahelyi portál alkalmazásban. Korábban ezek az üzenetek a Munkahelyi portál webhelyen jelentek meg. Ez a módosítás azt jelenti, hogy mostantól az összes hibaüzenet egy helyen jelenik meg ahelyett, hogy két különböző helyen jelenne meg.


**iOS rendszerű Vállalati portál alkalmazás**
* Amikor a felhasználók mobilalkalmazás-kezeléssel felügyelt alkalmazást indítanak, egy üzenetet látnak, amely értesíti őket, hogy az alkalmazást a vállalatuk felügyeli. A felhasználók mostantól a „További információk” hivatkozásra koppintva [további információhoz](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) juthatnak arról, mit jelent a „felügyelt alkalmazás”. Vagy ha a „Ne jelenjen meg ismét” lehetőségre koppintanak, az üzenet többé nem jelenik meg az alkalmazás elindításakor.
* Új képernyők vezetik végig a felhasználókat a regisztrálási folyamaton és nyújtanak további információt arról, hogy a felhasználóknak miért érdemes regisztrálniuk, valamint hogy az informatikai rendszergazdák mit láthatnak és mit nem láthatnak a regisztrált eszközökön. A részleteket lásd: [Regisztrációs utasítások](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* A regisztrációs hibaüzenetek mostantól megjelennek a Munkahelyi portál alkalmazásban. Korábban ezek az üzenetek a Munkahelyi portál webhelyen jelentek meg. Ez a módosítás azt jelenti, hogy mostantól az összes hibaüzenet egy helyen jelenik meg ahelyett, hogy két különböző helyen jelenne meg.




## 2016. február
### A Microsoft Munkahelyi portál szolgáltatásának módosításai és frissítései

Ebben a kiadásban a következő módosításokat vezettük be a Munkahelyi portál szolgáltatásban.

#### Androidos Munkahelyi portál alkalmazás
- Új képernyők vezetik végig a felhasználókat a regisztrálási folyamaton és nyújtanak további információt arról, hogy a felhasználóknak miért érdemes regisztrálniuk, valamint hogy az informatikai rendszergazdák mit láthatnak és mit nem láthatnak a regisztrált eszközökön. A részleteket lásd: [Regisztrációs utasítások](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- A regisztrációs hibaüzenetek mostantól megjelennek a Munkahelyi portál alkalmazásban. Korábban ezek az üzenetek a Munkahelyi portál webhelyen jelentek meg. Ez a módosítás azt jelenti, hogy mostantól az összes hibaüzenet egy helyen jelenik meg ahelyett, hogy két különböző helyen jelenne meg.

#### iOS rendszerű Vállalati portál alkalmazás
 - Új képernyők vezetik végig a felhasználókat a regisztrálási folyamaton és nyújtanak további információt arról, hogy a felhasználóknak miért érdemes regisztrálniuk, valamint hogy az informatikai rendszergazdák mit láthatnak és mit nem láthatnak a regisztrált eszközökön. A részleteket lásd: [Regisztrációs utasítások](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - A regisztrációs hibaüzenetek mostantól megjelennek a Munkahelyi portál alkalmazásban. Korábban ezek az üzenetek a Munkahelyi portál webhelyen jelentek meg. Ez a módosítás azt jelenti, hogy mostantól az összes hibaüzenet egy helyen jelenik meg ahelyett, hogy két különböző helyen jelenne meg.


## 2016. január

### A Windows 10 szolgáltatásainak kihasználása
* **Feltételes hozzáférés az állapotigazolási szolgáltatással** Az Intune-rendszergazdák mostantól megtekinthetik a Windows 10 eszközállapot-igazolási állapotát az Intune felügyeleti konzoljában. Az eszközállapot-igazolással a rendszergazdák gondoskodhatnak arról, hogy az ügyfélszámítógépek BIOS-, TPM- és rendszerindítószoftver-konfigurációja megbízható legyen. Az eszközállapot-igazolás támogatásához az ügyféleszközökön a Windows 10-nek kell futnia, és engedélyezni kell a TPM 2-t. Az eszközállapot-igazolás megjeleníti az eszközök számát, melyeken engedélyezve vannak az egyes alábbi funkciók:
    * Korai indítás kártevőirtó
    * BitLocker
    * Biztonságos rendszerindítás
    * Kódintegritás

    Az eszközállapot beállításával, az összegyűjtött adatpontokkal és az eszközállapot-jelentéssel kapcsolatos részleteket lásd: [Bevezetés a Microsoft Intune eszközmegfelelőségi házirendjeinek kezelésébe](introduction-to-device-compliance-policies-in-microsoft-intune.md). A [HAS szolgáltatás részletei](https://msdn.microsoft.com/en-us/library/dn934876.aspx) című témakör részletesen leírja a szolgáltatást.

* **Windows 10 Passport for Work házirend- és tanúsítványkezelés** Az Intune lehetővé teszi az [integrációt a Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) nevű Windows 10-es alternatív bejelentkezési módszerrel, amely Active Directoryt vagy egy Azure Active Directory-fiókot használ jelszó, intelligens kártya vagy virtuális intelligens kártya helyett. A Passport lehetővé teszi jelszó helyett felhasználói kézmozdulatok használatát a bejelentkezéshez. A felhasználói hitelesítési mód lehet egy egyszerű PIN-kód, biometrikus hitelesítés, mint például a Windows Hello, vagy egy külső eszköz, például egy ujjlenyomat-olvasó.

* **VPN-csatlakozás választott alkalmazásokban** Kiválaszthat olyan alkalmazásokat, amelyek automatikusan csatlakoznak a vállalati hálózathoz VPN-kapcsolaton keresztül. A VPN-profil beállításakor létrehozhatja az alkalmazások listáját a Segítség a felhasználóknak a munkájukhoz való csatlakozásban VPN-profilok használatával a Microsoft Intune-nal című részben leírtak alapján.

* **Windows 10 – teljes törlés támogatása** Mostantól az Intune-nal regisztrált Windows 10-es asztali eszközök teljes távoli törlését is elrendelheti az Intune felügyeleti konzoljáról. A Windows 10 teljes törlési funkciója az eszköz gyári beállításainak visszaállítását végzi el.


### Az Apple Volume Purchase program (VPP) frissítése
Az Intune most segít [az Apple Volume Purchase Program (VPP) for Business programon keresztül vásárolt alkalmazások felügyeletében](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Ebbe beletartozik a licencinformációk az Apple és az Intune közötti szinkronizálása és annak nyomon követése, hogy az egyes alkalmazások hány példánya van telepítve.

### Vállalati tulajdonú eszközök azonosítása IMEI számokkal
[Nemzetközi mobilkészülék-azonosító (IMEI) számokat importálhat](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) IMEI-számokkal rendelkező mobileszköz-platformok esetén, hogy könnyebben azonosítsa a vállalati tulajdonban lévő mobileszközöket. Az Intune-ban történő regisztráció után az importált IMEI-számokkal rendelkező eszközök Vállalati címkével rendelkeznek, amellyel a személyes eszközökre alkalmazott házirendektől eltérő házirendek alkalmazhatók.

### Mostantól több alkalmazás kompatibilis az Intune MAM-házirendekkel
Mostantól a Microsoft partnereinek további alkalmazásai kompatibilisek az Intune mobilalkalmazás-kezelési (MAM-) házirendjeivel (az Intune által felügyelt eszközökhöz):
* Box for EMM (a Box Inc vállalattól) – csak iOS esetén
* Adobe Reader (az Adobe vállalattól) – csak Android esetén
* Foxit PDF Reader (a Foxit Corporation vállalattól) – iOS és Android esetén


### Az IE9 támogatása januárban megszűnik
2016 februárjától többé nem támogatjuk az Internet Explorer 9-et mint a Microsoft Intune Vállalati portál webhelyének, az Intune-fiókportálnak és az Intune felügyeleti konzoljának eléréséhez használható hivatalos böngészőt. Ezért át kell térnie az Internet Explorer 10 vagy a böngésző újabb verziójának használatára.


>[!div class="step-by-step"]

>[&larr; **Az Intune újdonságai**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Jul16_HO3-->



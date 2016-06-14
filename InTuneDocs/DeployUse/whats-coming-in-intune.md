---
# required metadata

title: Várható újdonságok | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Várható újdonságok a Microsoft Intune-ban
Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. A várható újdonságokkal kapcsolatban friss hírekért látogasson vissza.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Mindezeket a funkciókat a hibrid ügyfélkörnyezetek is támogatni fogják (tehát az Intune-nal integrált Configuration Manager is). Az új hibrid funkciókkal kapcsolatos további információkért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Intune-kommunikáció
- **Az Intune-ra vonatkozó szolgáltatásállapot-adatok** átkerültek a központi, a többi Microsoft-szolgáltatásról is információt nyújtó helyre. Ezt az információt mostantól az [Office 365 felügyeleti portál](https://portal.office.com/Admin/Default.aspx) Szolgáltatás állapota menüjében találja meg. További információkat [ebben a blogposztban](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) talál.

- **Az üzenetközpont felhasználói felület bevezetése.** Az Intune-nak az [Office 365 felügyeleti portálra](https://portal.office.com/) való áttelepítése keretében az Office 365 üzenetközpontját fogjuk használni az új funkciókkal kapcsolatos és egyéb típusú értesítések küldéséhez. Emellett az Office 365 Admin felügyeleti társalkalmazás telepítésével mobiltelefonos értesítéseket kaphat, és egyszerűen továbbíthat bármilyen üzenetet a felhasználóknak vagy egy terjesztési célú aliasra.
Az üzenetközpontot a májusi kiadással kezdjük el használni, és a továbbiakban itt értesítjük a felhasználókat a frissítések elkészültéről, valamint az Intune új és továbbfejlesztett funkcióiról. Az üzenetközpont megtekintéséhez jelentkezzen be az [Office 365 felügyeleti portálra](https://portal.office.com/), és a bal oldali navigációs ablakból válassza az **Üzenetközpont** elemet.

## Alkalmazáskezelés
- **MAM-szabályzatokkal való felügyeletre alkalmas új alkalmazások.** Az androidos Microsoft Word, Excel és PowerPoint alkalmazásokhoz mostantól az Intune-ban nem regisztrált eszközökön is MAM-szabályzatok társíthatók. A támogatott alkalmazások teljes listájának megtekintéséhez keresse fel a Microsoft Intune mobilalkalmazás-galériát a [Microsoft Intune alkalmazáspartnerek oldalán](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


- **Feltételes hozzáférés böngészőhöz.** Lehetősége nyílik majd, hogy feltételes hozzáférési házirendet állítson be az Exchange Online-hoz és a SharePoint Online-hoz, így azokat csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök érhetik majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **MAM SDK: PIN-kód hosszának konfigurálása.** A mobilalkalmazás-felügyeleti (MAM-) alkalmazásoknál az eszközök PIN-kódjához hasonlóan meghatározható lesz a PIN-kód hossza. Ebben az esetben a végfelhasználóknak meg kell felelniük a beállított új korlátozásoknak. A felhasználók számára kissé más képernyő jelenik meg a hosszabb PIN-kód beviteléhez.
<!--- TFS 1104753--->

- **Skype Vállalati verzió Androidra.** Az Intune-rendszergazdák már a Skype Vállalati verziót is beállíthatják mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási házirendek nélkül.  A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-házirendeket.
<!--- TFS item 1248444 --->

- **Skype Vállalati verzió iOS-re.** Az Intune-rendszergazdák már a Skype Vállalati verziót is beállíthatják mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási házirendek nélkül.  A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-házirendeket.
<!--- TFS item 1248443 --->

### Xamarin-támogatás
A Microsoft Intune App SDK már támogatja a Xamarin-alkalmazásokat a következő használati helyzetekben:

- Új alkalmazások írása vagy a meglévő üzleti alkalmazások kódjának módosítása az Intune SDK-val. A bővítmény letölthető a [Microsoft Intune Github-oldalról](https://github.com/msintuneappsdk).
- A mobilalkalmazás-felügyelet támogatásának kiterjesztése a meglévő üzleti alkalmazásokra az Intune alkalmazásburkoló eszközével.

Ha segítségre van szüksége a megfelelő módszer kiválasztásához, lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Eszközkezelés
- **Távsegítségi munkamenetek Windows-számítógépekhez.** A Windows asztali ügynökprogrammal felügyelt számítógépek TeamViewer-integrációja révén távsegítségi munkameneteket kezdeményezhet a Windows asztali ügynökprogrammal felügyelt számítógépekkel, ami a végfelhasználói támogatási szolgálatok munkájához nyújt segítséget. Ez a lehetőség a Windows 7, 8, 8.1 és Windows 10 rendszerekre egyaránt kiterjed.
<!--- TFS 1284856--->



## Vállalati portál

- **Végfelhasználói bejelentési értesítések:** A végfelhasználók mostantól bejelentési értesítést kapnak az androidos Vállalati portál alkalmazástól, amikor regisztrálják eszközüket a Vállalati portálon, illetve amikor eltávolítják eszközüket a portálról.
- **Az eszközazonosító sáv több információt nyújt a végfelhasználók számára.** A végfelhasználók könnyebben azonosíthatják a választott eszközt a Vállalati portál webhelyen. Ha nem jól választottak, a kezdőlapi sávon a „Koppintson ide” hivatkozással kijelölhetik a megfelelő eszközt.
<!--- TFS 1231157--->

- **Változások a készülékregisztráció-kezelői fiókokban az androidos Vállalati portál alkalmazásban.** A jobb teljesítmény és méretezés érdekében az Intune a jövőben nem fogja megjeleníteni az összes készülékregisztráció-kezelő (DEM-) eszközt az androidos Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz jelenik meg, és az is csak abban az esetben, ha korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.

- **Változások a készülékregisztráció-kezelői fiókokban az iOS-es Vállalati portál alkalmazásban.** A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM-) eszközt az iOS-es Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.  Emellett az Intune-ból kivezettük a DEM-fiókok használati lehetőségét az Apple Device Enrollment Programmal és az Apple Configurator eszközzel. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.  Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.



## Szolgáltatások érvénytelenítése
**Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.**
Az Intune értesítési szabályai határozzák meg, hogy kinek küld e-mail-értesítést az Intune. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016. június 1-jétől fogva a felhasználó által létrehozott csoportok megcélzása nem lesz megvalósítható.

Ma a következő lépések szükségesek ahhoz, hogy egy értesítési szabállyal egy Ön által létrehozott csoportot célozzon meg a Microsoft Intune felügyeleti konzoljában:

A **Felügyelet** munkaterületen kattintson az **Értesítési szabályok** > **Új szabály létrehozása** elemre.

Az Értesítési szabály létrehozása varázsló második lépésében válassza ki a szabály által megcélzott eszközcsoportokat. Ez az eszközcsoportok kiválasztására szolgáló lépés a jövőben nem lesz elérhető az Intune-konzolon.

A módosítás előzetes ütemterve a következő:
- 2016 júniusától az új bérlők számára nem fog megjelenni az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
- 2016 augusztusától kezdve egyes meglévő bérlők számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.
- 2016 októberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.

<!---   TFS 1278864--->
**Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások.**
Néhány hónapon belül meg fog jelenni egy frissítés az iOS-es Microsoft Intune Vállalati portál alkalmazáshoz, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az iOS 8.0-s verziójánál régebbi rendszerrel futó új eszközöket ettől kezdve nem lehet majd regisztrálni. Az iOS 8.0-s verziójánál régebbi rendszerrel futó, de korábban már regisztrált eszközök korlátozott ideig még felügyelhetők, és használhatják a Vállalati portál alkalmazást. A Vállalati portál alkalmazás legújabb verzióját azonban csak az iOS 8.0-s vagy újabb rendszerrel futó eszközök fogják tudni elérni. Javasoljuk, hogy értesítse a felhasználókat, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0 rendszerre.  

- **Intune Viewer-alkalmazások.** Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer Android-eszközökre a Google Play Áruházból

  Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. További információk az RMS-megosztó alkalmazásról (a dokumentációra mutató hivatkozással).






### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).


<!--HONumber=Jun16_HO1-->



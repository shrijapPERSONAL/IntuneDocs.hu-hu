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

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Mindezeket a funkciókat a hibrid ügyfélkörnyezetek is támogatni fogják (tehát az Intune-nal integrált Configuration Manager is). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Alkalmazáskezelés
- **A Windows 10 Enterprise adatházirendjének változásai.** A Windows 10 Enterprise adatházirendjéhez tartozó alkalmazásházirend javítása miatt, ha alkalmazásszabályokkal konfigurált házirendet ment (korábbi nevén védett alkalmazások), minden eddig konfigurált szabály el fog veszni. A folytatáshoz újra kell konfigurálnia ezeket az alkalmazásszabályokat.

- **Feltételes hozzáférés böngészőhöz.** Lehetősége nyílik majd, hogy feltételes hozzáférési házirendet állítson be az Exchange Online-hoz és a SharePoint Online-hoz, így azokat csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök érhetik majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **A Dynamics CRM Online támogatja a feltételes hozzáférést.** Az ügyfelek feltételes hozzáférési házirendet állíthatnak be a Dynamics CRM Online-hoz, hogy csak a felügyelt és a szabályozásnak megfelelő iOS- és Android-eszközök érhessék el. A Dynamics CRM mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés végrehajtása előtt a rendszer kérni fogja a regisztrálást az Intune-ba, valamint a meg nem felelést okozó problémák megszüntetését.
<!---TFS1295358--->

### Xamarin-támogatás
A Microsoft Intune App SDK már támogatja a Xamarin-alkalmazásokat a következő használati helyzetekben:

- Új alkalmazások írása vagy a meglévő üzleti alkalmazások kódjának módosítása az Intune SDK-val. A bővítmény letölthető a [Microsoft Intune Github-oldalról](https://github.com/msintuneappsdk).
- A mobilalkalmazás-felügyelet támogatásának kiterjesztése a meglévő üzleti alkalmazásokra az Intune alkalmazásburkoló eszközével.

Ha segítségre van szüksége a megfelelő módszer kiválasztásához, lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Vállalati portál
**Változások a készülékregisztráció-kezelői fiókokban az iOS-es Vállalati portál alkalmazásban.** A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM-) eszközt az iOS-es Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.  Emellett az Intune-ból kivezettük a DEM-fiókok használati lehetőségét az Apple Device Enrollment Programmal és az Apple Configurator eszközzel. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.  Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.
<!---TFS 1233681--->

## Szolgáltatások érvénytelenítése
**A Windows 8 és a Windows Phone 8 vállalati portál alkalmazásai 2016. szeptembertől elavulttá válnak.** 2016. szeptembertől a Microsoft Intune már nem fogja támogatni a Microsoft Intune vállalati portál alkalmazásait Windows Phone 8 és Windows 8 platformokon. Frissítése az eszközöket a Windows 8.1 és a Windows Phone 8.1 rendszerekre, és használja a megfelelő Windows 8.1 és Windows Phone 8.1 vállalati portál alkalmazásokat az alkalmazásoknak ezekre az eszközökre történő további terjesztésére.
<!---TFS 1255391--->

**Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.**
Az e-mail-riasztások címzettjeit Intune értesítési szabályok határozzák meg. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016. június 1-jétől fogva a felhasználó által létrehozott csoportok megcélzása nem lesz megvalósítható.

A módosítás előzetes ütemterve a következő:
- 2016 júniusától az új bérlők számára nem fog megjelenni az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
- 2016 augusztusától kezdve egyes meglévő bérlők számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.
- 2016 októberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.

<!---   TFS 1278864--->
**Az iOS rendszerű vállalati portál alkalmazás támogatására vonatkozó módosítások.**
A felhasználóknak frissíteniük kell a legújabb iOS rendszerű vállalati portál alkalmazásra. Az elkövetkező hónapokban az iOS rendszerhez készült Microsoft Intune vállalati portál alkalmazás minden felhasználójának az alkalmazás legújabb verzióját kell majd használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

**Intune Viewer-alkalmazások.** Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. További információk az RMS-megosztó alkalmazásról (a dokumentációra mutató hivatkozással).


### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).


<!--HONumber=Jun16_HO2-->



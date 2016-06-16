---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Újdonságok | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Újdonságok a Microsoft Intune-ban
## 2016. június

### A Vállalati portál újdonságai

#### iOS rendszerű Vállalati portál alkalmazás

- A végfelhasználó számára az üzleti alkalmazások telepítésekor egy továbbfejlesztett környezet jelenik meg. Ha az alkalmazás telepítése hosszú ideig tart, a felhasználók manuálisan szinkronizálhatják az eszközt a szinkronizálási folyamat kényszerített folytatásához. A végfelhasználói lépéseket lásd [Az iOS-eszköz manuális szinkronizálása](/Intune/EndUser/sync-your-device-manually-ios.md) című szakaszban.

- Az iOS rendszerhez készült Microsoft Intune Vállalati portál alkalmazás frissült, így már támogatja az iOS 8.0-s és újabb verzióit. A frissítés eredményeként a végfelhasználók csak akkor tudják telepíteni a Vállalati portál alkalmazást, és regisztrálni új eszközöket az Intune-ban, ha az eszközön az iOS 8.0-s vagy újabb verziója fut. Az iOS nem támogatott verzióját futtató eszközöket korábban regisztrált felhasználók továbbra is használhatják az eszközükön lévő Vállalati portál alkalmazást.

## 2016. május


Mindezek a funkciók hibrid telepítések esetén is támogatottak (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok](https://technet.microsoft.com/en-us/library/mt718155.aspx) oldalát.

### Dokumentáció

A [docs.microsoft.com](https://docs.microsoft.com/en-us/intune) előzetes kiadása üdvözli Önt!
Ez a teljesen új, modern tartalomplatform azért jött létre, hogy Ön, ügyfelünk egyszerűbben megismerje és hatékonyabban használhassa az Intune-t.
Ha szeretne tájékozódni az összes új funkcióról, keresse fel [A docs.microsoft.com bemutatása](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) oldalt.

### Az Intune szolgáltatás állapota
Az Intune-ra vonatkozó szolgáltatásállapot-adatok átkerültek a központi, a többi Microsoft-szolgáltatásról is információt nyújtó helyre. Ezt az információt mostantól az [Office 365 felügyeleti portál](https://portal.office.com/Admin/Default.aspx) **Szolgáltatás állapota** menüjében találja meg.
További információkat [ebben a blogposztban](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) talál.


### Alkalmazáskezelés

- **MAM SDK: PIN-kód hosszának konfigurálása.** A mobilalkalmazás-felügyeleti (MAM-) alkalmazásoknál az eszközök PIN-kódjához hasonlóan meghatározható lesz a PIN-kód hossza. Ebben az esetben a végfelhasználóknak meg kell felelniük a beállított új korlátozásoknak. A felhasználók számára kissé más képernyő jelenik meg a hosszabb PIN-kód beviteléhez. Részletekért lásd: [Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban](/intune/deploy-use/android-mam-policy-settings) és [iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása](/intune/deploy-use/ios-mam-policy-settings).

- **Skype Vállalati verzió Androidra és iOS-re.** Mostantól a Skype Vállalati verziót is beállíthatja [mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási szabályzatok nélkül](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-szabályzatokat.

- **MAM-szabályzatokkal való felügyeletre alkalmas új alkalmazások.** Az androidos Microsoft Word, Excel és PowerPoint alkalmazásokhoz mostantól az Intune-ban nem regisztrált eszközökön is MAM-szabályzatok társíthatók. A támogatott alkalmazások teljes listájának megtekintéséhez keresse fel a Microsoft Intune mobilalkalmazás-galériát a [Microsoft Intune alkalmazáspartnerek](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) oldalán.



### A Vállalati portál újdonságai

#### Androidos Vállalati portál alkalmazás

- **Végfelhasználói bejelentési értesítések**: a végfelhasználók mostantól bejelentési értesítést kapnak az androidos Vállalati portál alkalmazástól, amikor regisztrálják eszközüket a Vállalati portálon, illetve, amikor eltávolítják eszközüket a portálról.

- **Változások a készülékregisztráció-kezelői fiókokban az androidos Vállalati portál alkalmazásban.** A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM-) eszközt az androidos Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre.
-
#### Munkahelyi portál webhely

**Vállalati portál webhely: az eszközazonosító sáv több információt nyújt a végfelhasználók számára.** A végfelhasználók mostantól könnyebben azonosíthatják a választott eszközt a Vállalati portál webhelyen. Ha nem jól választottak, a kezdőlapi sávon a **Koppintson ide** hivatkozással kijelölhetik a megfelelő eszközt.


## Mi várható?

- **Az üzenetközpont felhasználói felület bevezetése**. Az Intune-nak az [Office 365 felügyeleti portálra](https://portal.office.com/) való áttelepítése keretében az Office 365 üzenetközpontját fogjuk használni az új funkciókkal kapcsolatos és egyéb típusú értesítések küldéséhez. Emellett az Office 365 Admin felügyeleti társalkalmazás telepítésével mobiltelefonos értesítéseket kaphat, és egyszerűen továbbíthat bármilyen üzenetet a felhasználóknak vagy egy terjesztési célú aliasra.
Az üzenetközpontot a májusi kiadással kezdjük el használni, és a továbbiakban itt értesítjük a felhasználókat a frissítések elkészültéről, valamint az Intune új és továbbfejlesztett funkcióiról. Az üzenetközpont megtekintéséhez jelentkezzen be az [Office 365 felügyeleti portálra](https://portal.office.com/), és a bal oldali navigációs ablakból válassza az ÜZENETKÖZPONT elemet.

- **A készülékregisztráció-kezelő (DEM-) fiókok változásai**. A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az **összes** készülékregisztráció-kezelő (DEM-) eszközt az iOS-es Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre. Emellett az Intune-ból kivezettük a DEM-fiókok használati lehetőségét az Apple Device Enrollment Programmal és az Apple Configurator eszközzel. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását. Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.

### A Cloud platform ütemterve
Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával.

### Szolgáltatások érvénytelenítése
- **Intune Viewer-alkalmazások.** Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer Android-eszközökre a Google Play Áruházból

  Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. További információk az RMS-megosztó alkalmazásról (a dokumentációra mutató hivatkozással).

- **Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.**
Az e-mail-riasztások címzettjeit Intune értesítési szabályok határozzák meg. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016. június 1-jétől fogva a felhasználó által létrehozott csoportok megcélzása nem lesz megvalósítható.

    Ma a következő lépések szükségesek ahhoz, hogy egy értesítési szabállyal egy Ön által létrehozott csoportot célozzon meg a Microsoft Intune felügyeleti konzoljában:

    A **Felügyelet** munkaterületen kattintson az **Értesítési szabályok** > **Új szabály létrehozása** elemre.

    Az Értesítési szabály létrehozása varázsló második lépésében válassza ki a szabály által megcélzott eszközcsoportokat. Ez az eszközcsoportok kiválasztására szolgáló lépés a jövőben nem lesz elérhető az Intune-konzolon.

    A módosítás előzetes ütemterve a következő:
    - 2016 júniusától az új bérlők számára nem fog megjelenni az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
    - 2016 augusztusától kezdve egyes meglévő bérlők számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.
    - 2016 októberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.


- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**. Néhány hónapon belül meg fog jelenni egy frissítés az iOS-es Microsoft Intune Vállalati portál alkalmazáshoz, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az iOS 8.0-s verziójánál régebbi rendszerrel futó új eszközöket ettől kezdve nem lehet majd regisztrálni. Az iOS 8.0-s verziójánál régebbi rendszerrel futó, de korábban már regisztrált eszközök korlátozott ideig még felügyelhetők, és használhatják a Vállalati portál alkalmazást. A Vállalati portál alkalmazás legújabb verzióját azonban csak az iOS 8.0-s vagy újabb rendszerrel futó eszközök fogják tudni elérni. Javasoljuk, hogy értesítse a felhasználókat, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0 rendszerre.



## Az Intune korábbi kiadásai
Az Intune-ban az elmúlt hat hónapban bevezetett újdonságok listája [Az Intune korábbi kiadásai](previous-intune-releases.md) című cikkben olvasható.
> [!div class="op_single_selector"]
- [2016. április](previous-intune-releases.md)
- [2016. március](previous-intune-releases.md)
- [2016. február](previous-intune-releases.md)
- [2016. január](previous-intune-releases.md)
- [2015. december](previous-intune-releases.md)
- [2015. november](previous-intune-releases.md)




### További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A Cloud Platform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO2-->



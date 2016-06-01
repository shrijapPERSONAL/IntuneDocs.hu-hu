---
# required metadata

title: Várható újdonságok | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
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

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Mindezeket a funkciókat a hibrid ügyfélkörnyezetek is támogatni fogják (tehát az Intune-nal integrált Configuration Manager is). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx)..

## Az üzenetközpont bevezetése
Az Intune-nak az [Office 365 felügyeleti portálra](https://portal.office.com/) való áttelepítése keretében az Office 365 üzenetközpontját fogjuk használni az új funkciókkal kapcsolatos és egyéb típusú értesítések küldéséhez.  Emellett az Office 365 Admin felügyeleti társalkalmazás telepítésével mobiltelefonos értesítéseket kaphat, és egyszerűen továbbíthat bármilyen üzenetet a felhasználóknak vagy egy terjesztési célú aliasra.<br>  
Az üzenetközpontot a májusi kiadással kezdjük el használni, és a továbbiakban itt értesítjük a felhasználókat a frissítések elkészültéről, valamint az Intune új és továbbfejlesztett funkcióiról.  Az üzenetközpont megtekintéséhez jelentkezzen be az [Office 365 felügyeleti portálra](https://portal.office.com/), és a bal oldali navigációs ablakból válassza az **ÜZENETKÖZPONT** elemet.
<!---TFS 1242782--->


## Alkalmazáskezelés
- **Feltételes hozzáférés böngészőhöz.** Lehetősége nyílik majd, hogy feltételes hozzáférési házirendet állítson be az Exchange Online-hoz és a SharePoint Online-hoz, így azokat csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök érhetik majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **MAM SDK: PIN-kód hosszának konfigurálása.** A mobilalkalmazás-felügyeleti (MAM-) alkalmazásoknál az eszközök PIN-kódjához hasonlóan meghatározható lesz a PIN-kód hossza. Ebben az esetben a végfelhasználóknak meg kell felelniük a beállított új korlátozásoknak. A felhasználók számára kissé más képernyő jelenik meg a hosszabb PIN-kód beviteléhez.
<!--- TFS 1104753--->

- **A MAM felügyeletével elkerülhető az Outlook-névjegyek szinkronizálása (iOS).** Új beállítás érhető el a mobilalkalmazások eszközregisztráció nélküli felügyeletéhez. Ezzel a beállítással az Intune-rendszergazda megakadályozhatja, hogy az alkalmazás szinkronizálja a névjegyeket a natív címjegyzékbe az iOS-eszközökön. Ha a beállítás engedélyezve van, az alkalmazás nem tudja menteni a névjegyeket a natív címjegyzékbe. Ha a beállítás nincs engedélyezve, az alkalmazás menteni tudja a névjegyeket a natív címjegyzékbe. Amikor az Intune-rendszergazda szelektív módon törli egy eszköz tartalmát, a natív címjegyzékben mentett összes névjegy törlődni fog. Ezt az új beállítást már az iOS-eszközökön elérhető Outlook alkalmazás is támogatja.
<!---TFS item 1276166--->

- **Skype Vállalati verzió Androidra.** Az Intune-rendszergazdák már a Skype Vállalati verziót is beállíthatják mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási házirendek nélkül.  A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-házirendeket.
<!--- TFS item 1248444 --->

- **Skype Vállalati verzió iOS-re.** Az Intune-rendszergazdák már a Skype Vállalati verziót is beállíthatják mobilalkalmazás-felügyeleti (MAM-) célként, regisztrálási házirendek nélkül.  A felhasználók bejelentkezését követően a rendszer érvénybe lépteti a MAM-házirendeket.
<!--- TFS item 1248443 --->

### Xamarin-támogatás
A Microsoft Intune App SDK már támogatja a Xamarin-alkalmazásokat a következő használati helyzetekben:

- Új alkalmazások írása vagy a meglévő üzleti alkalmazások kódjának módosítása az Intune SDK-val. A bővítmény letölthető a [Microsoft Intune Github-oldalról](https://github.com/msintuneappsdk).
- A mobilalkalmazás-felügyelet támogatásának kiterjesztése a meglévő üzleti alkalmazásokra az Intune alkalmazásburkoló eszközével.

Ha segítségre van szüksége a megfelelő módszer kiválasztásához, lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)..
<!--- TFS 1061478 & TFS 1152340--->


## Eszközkezelés
- **Távsegítségi munkamenetek Windows-számítógépekhez.** A Windows asztali ügynökprogrammal felügyelt számítógépek TeamViewer-integrációja révén távsegítségi munkameneteket kezdeményezhet a Windows asztali ügynökprogrammal felügyelt számítógépekkel, ami a végfelhasználói támogatási szolgálatok munkájához nyújt segítséget. Ez a lehetőség a Windows 7, 8, 8.1 és Windows 10 rendszerekre egyaránt kiterjed.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Hozzáférés-vezérlés
* **A Skype Vállalati online verzió támogatja a feltételes hozzáférést.** Az Intune-rendszergazdák feltételes hozzáférési házirendet is beállíthatnak a Skype Vállalati online verzióhoz, így azok csak a felügyelt és a szabályozásnak megfelelő iOS- és Android-eszközök által lesznek elérhetők. A Skype Vállalati verzió mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés előtt a rendszer kérni fogja a regisztrálást az Intune-ban, valamint a szabályozási problémák megszüntetését.
<!---TFS item 1254499--->

## Vállalati portál
* **Az eszközazonosító sáv több információt nyújt a végfelhasználók számára.** A végfelhasználók könnyebben azonosíthatják a választott eszközt a Vállalati portál webhelyen. Ha nem jól választottak, a kezdőlapi sávon a „Koppintson ide” hivatkozással kijelölhetik a megfelelő eszközt.
<!--- TFS 1231157--->

* **Közvetlenül a Vállalati portálon elérhető Windows-alkalmazáscsomagok**: A Windows 8, a Windows 8.1 és a Windows RT rendszerű számítógépek felhasználói most már közvetlenül a Vállalati portál webhelyéről telepíthetik a Windows-alkalmazáscsomagokat (.appx kiterjesztés). Ahhoz, hogy az alkalmazások telepítése lehetővé váljon, korábban az Intune-rendszergazdáknak kellett központilag telepíteniük a Vállalati portál alkalmazást, vagy a felhasználóknak kellett telepíteniük azt saját eszközükön.
<!--- TFS item 1082481 --->

* **A felhasználók a Vállalati portálon távolról zárolhatják eszközüket**: Egy új távoli zárolási beállítás lett elérhető a Vállalati portál webhelyen, amellyel a felhasználók a portálon távolról zárolhatják az eszközeiket azok elvesztése vagy ellopása esetén. A következő táblázat a távoli zárolási szolgáltatás platformtámogatását sorolja fel a különálló Intune és a Configuration Managerrel együtt használt Intune esetében.
<!--- TFS item 1195661 --->

|Platform  |Támogatás részletei|
|---------|---------|
|iOS | Támogatott|
|Android | Támogatott|
|Windows Phone 8.1 | Támogatott|
|Windows 10 mobil verzió | Csak beállított jelszóval rendelkező telefonok esetén támogatott|
|PC (Windows 8.0 és korábbi verziók) | Nem támogatott|
|PC (Windows 8.1) | Nem támogatott|
|Windows Phone 8.0 | Nem támogatott|
|Windows 10 asztali verzió | Nem támogatott|

## Szolgáltatások érvénytelenítése
* **Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.** 2016 júniusának elejétől kezdve az Értesítési szabály létrehozása varázslóval már nem célozhatók meg egyéni felhasználói csoportok értesítési szabályokkal.

    Jelenleg ha felhasználói által létrehozott csoportot szeretne megcélozni a Microsoft Intune felügyeleti konzolon, a **Felügyelet** > **Értesítési szabályok** > **Új szabály létrehozása** elemet kell választania. Az Értesítési szabály létrehozása varázsló második lépésében ki kell választania a szabály által megcélzott eszközcsoportokat. Ez az **Eszközcsoportok kiválasztása** lépés a jövőben nem lesz elérhető az Intune-konzolon.

    Az **Eszközcsoportok kiválasztása** funkció az Intune 2016. júniusi (1606) kiadása után már nem lesz támogatott. A beállítás ugyanakkor 2016 augusztusáig továbbra is látható marad. Augusztus után elkezdjük áttelepíteni a bérlőinket az új felületre. Ez a folyamat két hónapig fog tartani. 2016 októberéig az új felületre való áttérés az összes meglévő ügyfelünknél lezajlik. Az új felület bevezetését követően az értesítési szabályok adott csoportokra való célzására szolgáló beállítás többé nem fog megjelenni.
<!---   TFS 1278864--->







### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->



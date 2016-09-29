---
title: "Újdonságok | Microsoft Intune"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 03a5dd14b854fedf7e2cb5b949580960a0eab9de
ms.openlocfilehash: 1d09e5a0adb3ecfa8f2d64f668ea7ff16bdf31fa


---

# Újdonságok a Microsoft Intune-ban – szeptember
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Blogbejegyzés ‒ Ensuring mobile devices are up to date using Microsoft Intune (A mobileszközök naprakészségének biztosítása a Microsoft Intune segítségével)<br>
>A nemrégiben a Trident nevű kártevő által az iOS eszközök ellen indított támadások nyomán közzétettünk egy új blogbejegyzést [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (A mobileszközök naprakészségének biztosítása a Microsoft Intune segítségével) címen, amely ismerteti az Intune által kínált különböző lehetőségeket a mobileszközök biztonságának és naprakészségének fenntartására.

## iOS 10-támogatás
A meglévő Intune MDM- és MAM-forgatókönyvek kompatibilisek az iOS 10 rendszerrel. Az [Intune támogatási csapatának blogjában](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/) tippeket olvashat.

## Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken
Az Intune alkalmazásburkoló eszköz egy parancssori eszköz, amellyel az Intune MAM üzleti (LOB) alkalmazások esetében is használható iOS és Android rendszereken. Ez a legegyszerűbb módja annak, hogy az Intune MAM SDK-t az alkalmazásba integrálja, így az alkalmazás kikényszerítheti az Intune-ban üzembe helyezett MAM-szabályzatokat. A MAM-szabályzatokkal lehetősége van:

1. Alkalmazásadatok titkosítására.
2. Megkövetelni, hogy az infómunkás PIN-kódot adjon meg az alkalmazás indításához.
3. Előírni, hogy az alkalmazás csak felügyelt alkalmazások számára továbbíthasson adatokat.
4. Letiltani, hogy az alkalmazás adatokat mentsen az Android, iTunes vagy iCloud rendszerekbe.
5. Előírni, hogy a kivágás, másolás és beillesztés műveleteket csak felügyelt alkalmazások között lehessen végrehajtani.

A frissített Intune alkalmazásburkoló eszköz nyilvános előzetes verziója már eszközregisztráció nélküli MAM-támogatást is nyújt az iOS és Android rendszereken futó belső üzleti alkalmazásokhoz. Ez azt jelenti, hogy a felhasználóknak nem szükséges regisztrálni az eszközeiket az Intune-ban a MAM által kezelt üzleti alkalmazások használatához.

A szoftver nyilvános előzetes verzióját bárki tesztelheti, és a GitHub msintuneappsdk oldalain hasznos dokumentáció is található hozzá:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

A Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásának telepítése előtt:

* Tekintse át a Microsoft licencfeltételeit a Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásához
* Nyomtassa ki és őrizze meg a licencfeltételeket. A Microsoft licencfeltételeit a Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásának letöltésével és használatával Ön elfogadja ezeket a licencfeltételeket. Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.
<!---TFS 1235607--->

## Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba
Egyes új Intune-fiókok az Intune felhasználói csoportok helyett Azure Active Directory-alapú biztonsági csoportokat fognak használni. Azt, hogy biztonsági csoportokkal dolgozik-e, onnan lehet tudni, hogy az Intune-portál csoportok lapján egy hivatkozás irányítja majd át az Azure felügyeli portáljára.

## Lookout-integráció Android-eszközök védelméhez
A Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az Androidos mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást az Android-eszközön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a hozzáférés biztosításához. További információ: [Hozzáférés korlátozása eszközök, hálózat és alkalmazáskockázat alapján](restrict-access-based-on-device-network-app-risk.md).


## A Vállalati portál újdonságai

### Android

**„Értesítések” bevezetése a Munkahelyi portál androidos verziójában**<br/>
A Munkahelyi portál androidos verziójában a kezdőlapon az „Értesítéseknek” új ikonja van. Az ikonra koppintva megnyílik az Értesítések lap, amely megjeleníti a végfelhasználók számára az összes figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Az iOS-alapú Munkahelyi portál alkalmazásban már elérhető ez az értesítési funkció. Az új Értesítések lap eredményeképpen, ha az eszköz már regisztrálva van, a Munkahelyi hozzáférés beállítása képernyő nem jelenik meg a Munkahelyi portál androidos verziójának minden egyes elindításakor vagy használatának folytatásakor. Ha létrehozza saját végfelhasználói útmutatóját, frissítse dokumentációját ezen változásnak megfelelően. A frissített képernyőképeket [itt](https://aka.ms/androidcpupdate) találja.  
<!---TFS 1095560--->


### iOS
**Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
Az iOS rendszerhez készült Microsoft Intune vállalati portál alkalmazás minden felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók már csak a legújabb verziót tudják letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem tudják használni a vállalati portált, és regisztrálni sem tudnak, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is frissíteniük kell a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.
<!---TFS 1283165--->

**Fejlesztések azzal kapcsolatban, hogy az iOS-végfelhasználók hogyan kapják meg az alkalmazásaikat**<br/>
A következő változásokra került sor az iOS-es Vállalati portál alkalmazás alkalmazáscsempéivel kapcsolatban annak érdekében, hogy a felhasználók valamennyi alkalmazásukat egyetlen helyen, a Vállalati portál webhelyen láthassák különböző nézetekben. Az Apple korlátozásai tiltják az üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban; ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk.

- A **Vállalati alkalmazások** csempe korábban az összes alkalmazás listájára mutatott a Vállalati portál webhely ÖSSZES lapján, és ez a jövőben is így marad. A csempe neve **Minden alkalmazás**-ra változott.
- Az **Egyéb alkalmazások** csempe korábban a Vállalati portál alkalmazás azon alkalmazásokat listázó nézetére mutatott, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. A csempe neve **Kiemelt alkalmazások**-ra változott, és rákoppintás esetén a felhasználót a Vállalati portál webhely KIEMELT lapjára irányítja.
-  A **Kategóriák** csempe korábban egy olyan nézetre mutatott a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza. A csempe neve nem változott, most azonban a Vállalati portál webhely KATEGÓRIÁK nézetére mutat.
[Itt](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) talál frissített képernyőképeket.
<!---TFS 1317133--->

**Felszólítás az iOS-es Managed Browser alkalmazás telepítésére, ha az informatikai részleg beállította ezt a követelményt az alkalmazás számára**<br/>
Ha egy webklipet úgy konfigurált, hogy csak a felügyelt böngészőben nyíljon meg, de a felügyelt böngésző nincs telepítve az eszközön, akkor az eszközön futó Vállalati portál alkalmazás felszólítja a felhasználót, hogy a webklip telepítése előtt telepítse a felügyelt böngészőt. 
<!---TFS 1228570--->

### Windows
**A Windows Phone 8.1-es Munkahelyi portál alkalmazás visszajelzési gombbal egészült ki**<br/>
A Windows Phone 8.1-es Munkahelyi portál alkalmazás lehetővé teszi, hogy a végfelhasználók az új „visszajelzés küldése” gombbal visszajelzést küldjenek az alkalmazásról. A gomb megtalálásához koppintson a Munkahelyi portál alkalmazás képernyőjén alul jobbra látható „három pont” menüre, majd koppintson a **visszajelzés küldése** lehetőségre. Az anonimizált formában összegyűjtött visszajelzéseket a Microsoft a Munkahelyi portál alkalmazás nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!---TFS 1317806--->


## Mi várható?

### Az Intune-csoportok Azure Active Directory-csoportokká alakulnak
Az Intune egy új csoportkezelési megoldást vezet be, amely Azure Active Directory- (AAD-) biztonsági csoportokat használ felhasználói és eszközcsoportokként az Intune-ban. **Az új, Azure-alapú Intune felügyeleti portál bemutatása után** e csoportok használatával történik majd minden csoportfelügyeleti, valamint szabályzat- és profillétesítési művelet.

Az új felhasználói élmény kiküszöböli a csoportok szolgáltatások közti duplikálásának szükségességét, **hozzáférést nyújt néhány új Prémium szintű Azure Active Directory- (AADP-) csoportszolgáltatáshoz**, és bővíthetőséget tesz lehetővé a PowerShell és a Graph használatával. Emellett vállalati mobileszköz-felügyeleti szinten egyesíteni fogja a csoportfelügyeleti élményt.

A biztonsági csoportokra való áttérés lehetővé tételének érdekében a **jelenlegi felügyeleti konzol** felhasználói élménye is változni fog. **Az ezt érintő változtatások, valamint az AAD-biztonságicsoportok használata az Intune-dokumentációban lesznek rögzítve**.

Az Intune új felhasználói **a biztonsági csoportokat érintő egyes változásokkal előbb szembesülnek majd, mint a jelenlegi bérlők**.

A csoportfelügyelettel kapcsolatos változtatások mellett **a következő funkciók megszűnnek**:
- Tagok vagy csoportok kihagyása egy új csoport létrehozásakor
- **Nem csoportosított felhasználók** és **Nem csoportosított eszközök** csoportjai
- **Csoportok kezelése** a szolgáltatásadminisztrátori szerepkörben
- Egyéni, csoportalapú riasztások az értesítési szabályokkal kapcsolatban
- Pivotálás csoportokkal a jelentésekben
<!--- TFS 1295329--->

### Új feltételes hozzáférési szabályzatok az Exchange Online-hoz és a SharePoint Online-hoz
Lehetősége nyílik arra, hogy korlátozza a hozzáférést az Exchange Online-hoz és a SharePoint Online-hoz, hogy a hozzáférés csak az Office mobilalkalmazások – például Outlook, Word, Excel vagy OneDrive – számára legyen lehetséges. Ez az új funkció kiválóan együtt használható az Intune mobilalkalmazás-kezelési (MAM) szabályzatokkal, mivel letilthatja a hozzáférést a beépített e-mail ügyfélprogramokhoz vagy más alkalmazásokhoz, amelyek nincsenek még konfigurálva Intune MAM-szabályzatokkal. Ezzel biztosítható, hogy a felhasználók csak olyan alkalmazásokkal férhessenek hozzá a vállalati adatokhoz, amelyeket az Intune MAM használatával védenek. Az Intune mobilalkalmazás-felügyelettel az Azure-portálon ismerkedhet meg. Ehhez keresse a „Beállítások” panelen az új Feltételes hozzáférés szakaszt.



### Szolgáltatások érvénytelenítése

- **A Windows 8 és a Windows Phone 8 Vállalati portál alkalmazásai elavulttá válnak** <br/>
2016 októberétől a Microsoft Intune kivezeti a Windows 8 és Windows Phone 8 Vállalati portál alkalmazások támogatását. A Microsoft Intune egyúttal a Windows Phone 8 platform támogatását is kivezeti. Ennek következményeképpen ekkortól nem tud majd Windows Phone 8 rendszerű eszközöket regisztrálni vagy frissíteni. A már regisztrált Windows Phone 8 és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.



### A felhőplatform ütemterve
Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával.


## Az Intune korábbi kiadásai
Az Intune-ban az elmúlt hat hónapban bevezetett újdonságok listája [Az Intune korábbi kiadásai](previous-intune-releases.md) című cikkben olvasható.

### További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO3-->



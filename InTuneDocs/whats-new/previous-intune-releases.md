---
title: "Korábbi kiadások | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1360a23647d6e66ba682548ad2b158bb9047265d
ms.openlocfilehash: ec1b118b2c7681f351d83f469b8c32e95f8fa71f


---

# Az Intune korábbi kiadásai

## 2016. szeptember
### Új funkciók, bejelentések és információk
* [Windows feltételes hozzáférés](#windows-conditional-access)
* [iOS 10-támogatás](#ios-10-support)
* [Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integráció Android-eszközök védelméhez](#lookout-integration-to-protect-android-devices)
* [A Vállalati portál frissítései Android, iOS és Windows rendszeren](#company-portal-updates)
* [Intune-szószedet](#intune-glossary)
* [Mi várható?](#whats-coming)

### Windows feltételes hozzáférés
Mostantól feltételes hozzáférési szabályzatokat hozhat létre az Intune felügyeleti konzollal. Ezekkel megakadályozhatja, hogy a Windows rendszerű számítógépek elérjék az Exchange Online-t és a SharePoint Online-t. Olyan feltételes hozzáférési szabályzatokat is létrehozhat, amelyekkel az Office asztali és univerzális alkalmazásainak elérését gátolhatja meg.

### iOS 10-támogatás
A meglévő Intune MDM- és MAM-forgatókönyvek kompatibilisek az iOS 10 rendszerrel. Az [Intune támogatási csapatának blogjában](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/) tippeket olvashat.

### Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken
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

### Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba
Egyes új Intune-fiókok az Intune felhasználói csoportok helyett Azure Active Directory-alapú biztonsági csoportokat fognak használni. Azt, hogy biztonsági csoportokkal dolgozik-e, onnan lehet tudni, hogy az Intune-portál csoportok lapján egy hivatkozás irányítja majd át az Azure felügyeli portáljára.

### Lookout-integráció Android-eszközök védelméhez
A Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az Androidos mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást az Android-eszközön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a hozzáférés biztosításához. További információ: [Hozzáférés korlátozása eszközök, hálózat és alkalmazáskockázat alapján](restrict-access-based-on-device-network-app-risk.md).


### A Vállalati portál újdonságai

### Android
**„Értesítések” bevezetése a Munkahelyi portál androidos verziójában**<br/>
A Munkahelyi portál androidos verziójában a kezdőlapon az „Értesítéseknek” új ikonja van. Az ikonra koppintva megnyílik az Értesítések lap, amely megjeleníti a végfelhasználók számára az összes figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Az iOS-alapú Munkahelyi portál alkalmazásban már elérhető ez az értesítési funkció. Az új Értesítések lap eredményeképpen, ha az eszköz már regisztrálva van, a Munkahelyi hozzáférés beállítása képernyő nem jelenik meg a Munkahelyi portál androidos verziójának minden egyes elindításakor vagy használatának folytatásakor. Ha létrehozza saját végfelhasználói útmutatóját, frissítse dokumentációját ezen változásnak megfelelően. A frissített képernyőképeket [itt](https://aka.ms/androidcpupdate) találja.  
<!---TFS 1095560--->

**Visszajelzés küldése az Androidhoz készült Vállalati portálon**</br>
Az Androidhoz készült Vállalati portál menüjében egy új elem jelent meg. Ha a **Help & Feedback** (Súgó és visszajelzés) elemre koppint, az alábbi három művelet közül választhat:
* Válassza a **Get Help** (Segítség kérése) lehetőséget, ha egy Vállalati portállal kapcsolatos problémát szeretne jelenteni az informatikai részlegnek. Az informatikai részleg az Ön e-mail ügyfélprogramját használva elkészít egy e-mail üzenetet, amelyhez csatolja a Vállalati portál naplóadatait. A **Get Help** (Segítség kérése) a **Send Data** (Adatküldés) elemet váltja fel a **Settings** (Beállítások) lapon.
* A **Give Feedback** (Visszajelzés küldése) használatával visszajelzést küldhet a Vállalati portál csapatának.
* Az **Rate our App** (Alkalmazás értékelése) arra ad lehetőséget, hogy értékelje a Vállalati portál alkalmazást a Google Play áruházban.

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

### Intune-szószedet</br>
A könyvtárban elhelyeztünk egy új, a [szószedetet tartalmazó témakört](https://docs.microsoft.com/intune/understand-explore/intune-glossary), hogy segítsünk megérteni az Intune termékben használat fogalmakat.


## 2016. augusztus
### Alkalmazáskezelés
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Rejtett és megjelenített alkalmazások iOS 9.3 alatt__ Az iOS 9.3-at vagy annál újabb verziójú operációs rendszert futtató felügyelt eszközök esetében az iOS-es általános konfigurációs szabályzat rejtett és megjelenített alkalmazásokat tartalmazó listája segítségével:
- Megadhatja a felhasználók elől elrejtett alkalmazások listáját. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
- Megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

Az így megadott alkalmazások egyaránt lehetnek Ön által telepített, illetve olyan beépített iOS-alkalmazások, mint az Üzenetek és a Megjegyzések. Részletekért lásd: [iOS-szabályzatbeállítások a Microsoft Intune-ban]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
__Engedélyezett és letiltott alkalmazások házirendje Samsung KNOX-eszközökhöz__ Mostantól egyedi szabályzatot konfigurálhat Samsung KNOX-eszközökhöz, amely lehetővé teszi az alábbiak egyikének létrehozását:
- Az eszközön nem futtatható alkalmazások listája. A tiltólistán szereplő alkalmazások nem aktiválhatók az eszközön, még ha telepítve is vannak.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung KNOX-ot futtató eszközökön használhatók.
Részletekért lásd: [Egyéni szabályzat használata alkalmazások engedélyezéséhez és tiltásához Samsung KNOX-eszközökön](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->
__A mobilalkalmazás-kezelési (MAM) szabályzatokkal kompatibilis új alkalmazások__ [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) és [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) operációs rendszer alatt a Yammer-alkalmazás már kompatibilis az [Intune mobilalkalmazás-kezelési (MAM) szabályzatokkal](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), függetlenül attól, hogy az eszköz regisztrálva van-e vagy sem.

A MAM-kompatibilis alkalmazások teljes listáját lásd a [Microsoft Intune-alkalmazáspartnerek](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) webhelyén.
<!--- TFS 1252335 & 1252336 checked--->

<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune Viewer-alkalmazások__ Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos [Rights Management alkalmazás (RMS-megosztó alkalmazás)](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. Onnantól kezdve, hogy az Intune Viewer alkalmazás már nem lesz támogatott, eltávolítjuk a Google Store áruházból, és nem lesz elérhető további használatra.

### Eszközkezelés
__Android 7.0-támogatás__ Az Intune azonnali támogatást nyújt a hamarosan megjelenő Android 7.0 operációs rendszerhez mobileszközökön.
<!---TFS 1262053--->

__A jelszó távoli alaphelyzetbe állításának Google általi megszüntetése Android 7.0 rendszerű eszközökön__ A Google megszünteti azt a lehetőséget, hogy a rendszergazdák és a végfelhasználók távolról új jelszót kérhessenek Android 7.0 rendszerű eszközükhöz. Korábban a rendszergazdák távolról új jelszót állíthattak be a felhasználók számára, a felhasználók pedig a Vállalati portálról tehették meg ugyanezt.

### A Vállalati portál újdonságai
__Munkahelyi portál webhely__
- **Visszajelzési hivatkozás a Vállalati portálról a Microsofthoz** <br/>
A Vállalati portál webhelyen az oldal alján található új „Visszajelzés” hivatkozásra koppintva a felhasználók visszajelzést küldhetnek a Microsoftnak a webhellyel kapcsolatos tapasztalataikról. A névtelenített formában összegyűjtött visszajelzéseket a Microsoft a Vállalati portál nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!--- TFS 1313657 checked--->

__iOS__
- **A felügyelt böngésző iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
A Microsoft Intune Managed Browser alkalmazás iOS-verziója frissítve lett, és már támogatja az iOS 8.0-s vagy újabb rendszerű eszközöket. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható a jelenlegi Managed Browser alkalmazás, kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253 checked--->

### Mi várható?

__iOS 10-támogatás__ Az Intune teljes körűen támogatja az iOS 10-et. További információ az iOS 10 nyilvános bemutatását követően lesz elérhető.

__Az Intune-csoportok 2016 szeptemberétől Azure Active Directory-csoportokká alakulnak__ Az Intune egy új csoportkezelési megoldást vezet be, amely Azure Active Directory- (AAD-) biztonsági csoportokat használ felhasználói és eszközcsoportokként az Intune-ban. **Az új, Azure-alapú Intune felügyeleti portál bemutatása után** e csoportok használatával történik majd minden csoportfelügyeleti, valamint szabályzat- és profillétesítési művelet.

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

__„Értesítések” bevezetése a Vállalati portál Android-verziójában__ Szeptemberben egy frissítést adunk ki a Vállalati portál Android-verziójához, amely bevezet egy új **Értesítések** ikont a kezdőlapon. Az ikonra koppintva megnyílik az **Értesítések** oldal, amely megjeleníti a végfelhasználó számára az összes, figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Ha az iOS rendszerű Vállalati portál alkalmazást is használja, akkor már ismerheti az Értesítések nyújtotta felhasználói élményt. Az **Értesítések** lap bevezetésével nem fog a Vállalati portál Android-verziójának minden egyes elindításakor vagy folytatásakor megjelenni a **Vállalati hozzáférés beállítása** képernyő, ha az eszköz már regisztrálva van. Tisztában vagyunk azzal, hogy sokan hoztak létre végfelhasználói útmutatókat, és nagy hasznát veszik az előzetes értesítéseknek, amikor az útmutatók vagy a képernyőképek frissítésére lehet szükség. Kérjük, frissítsék a dokumentációkat, hogy azok tükrözzék a felhasználói élménnyel kapcsolatos közelgő változásokat. A frissített képernyőképek itt találhatók: https://aka.ms/androidcpupdate.  

__Fejlesztések azzal kapcsolatban, hogy az iOS-végfelhasználók hogyan kapják meg az alkalmazásaikat__ Szeptemberben a következő változásokra kerül sor az iOS-es Vállalati portál alkalmazás alkalmazáscsempéivel kapcsolatban annak érdekében, hogy a felhasználók valamennyi alkalmazásukat egyetlen helyen, a Vállalati portál webhelyen láthassák különböző nézetekben. Jelenleg az Apple korlátozásai tiltják az üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban; ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk.

- A **Vállalati alkalmazások** csempe jelenleg az összes alkalmazás listájára mutat a Vállalati portál webhely ÖSSZES lapján, és ez a jövőben is így marad. A csempe új neve **Minden alkalmazás**.
- Az **Egyéb alkalmazások** csempe jelenleg a Vállalati portál alkalmazás azokat az alkalmazásokat listázó nézetére mutat, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. A csempe új neve **Kiemelt alkalmazások** lesz, és rákoppintás esetén a felhasználót a Vállalati portál webhely KIEMELT lapjára irányítja.
-  A **Kategóriák** csempe jelenleg egy olyan nézetre mutat a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza. A csempe neve nem változik, azonban ezentúl a Vállalati portál webhely KATEGÓRIÁK nézetére mutat majd. [Itt](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) talál frissített képernyőképeket.
<!---TFS 1317133--->

### A felhőplatform ütemterve
Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával.

### Szolgáltatások érvénytelenítése
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
Szeptembertől iOS operációs rendszer alatt a Microsoft Intune Vállalati portál alkalmazás valamennyi felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

- **A felügyelt böngésző iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
Augusztusban az Intune egy olyan frissítést ad ki a Microsoft Intune Managed Browser alkalmazás iOS-verziójához, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket támogatja. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható lesz a jelenlegi Managed Browser alkalmazás, de kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253--->

- **A Windows 8 és a Windows Phone 8 Vállalati portál alkalmazásai elavulttá válnak** <br/>
2016 októberétől a Microsoft Intune kivezeti a Windows 8 és Windows Phone 8 Vállalati portál alkalmazások támogatását. A Microsoft Intune egyúttal a Windows Phone 8 platform támogatását is kivezeti. Ennek következményeképpen ekkortól nem tud majd Windows Phone 8 rendszerű eszközöket regisztrálni vagy frissíteni. A már regisztrált Windows Phone 8 és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## 2016. július
### Alkalmazáskezelés

__Az alkalmazáslétesítési profilok frissítéseivel kapcsolatos felhasználói élmény javítása__ Az Apple iOS üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.

Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában 3 évig érvényes. A létesítési profil viszont 1 év után lejár. Ettől a frissítéstől kezdve az Intune biztosítja azokat az eszközöket, amelyekkel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak. További információk: [iOS mobil létesítésiprofil-házirendek használata az üzletági alkalmazások naprakészen tartására](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Az Intune-hoz készült Xamarin SDK már elérhető__ Az Intune App SDK Xamarin összetevőjével engedélyezheti az Intune mobilalkalmazás-felügyeleti funkciókat a Xamarinnal készült, iOS vagy Android rendszerű alkalmazásokban. Az összetevőt a [Xamarin áruházban](https://components.xamarin.com/view/Microsoft.Intune.MAM) vagy a [Microsoft Intune GitHub-oldalon](https://github.com/msintuneappsdk) érheti el.
<!--- TFS 1061478 --->

### Eszközkezelés
__Megnövelt eszközregisztrációs limit__ Az Intune a konfigurálható eszközök regisztrációs korlátját felhasználónként 5 eszközről 15-re növelte.
<!---TFS 1289896 --->

__Az Intune ügyfélszoftvert futtató Windows-számítógépeken érvénybe léptethető__
[TeamViewer](https://www.teamviewer.com)-integráció segítségével távsegítség-munkameneteket indíthat más Windows-számítógépekkel, ami jelentős előnyt jelent a végfelhasználói ügyfélszolgálat számára. Ez a lehetőség a Windows 7, 8, 8.1 és Windows 10 rendszerekre egyaránt kiterjed. Részletekért lásd: [A Windows rendszerű számítógépek a Microsoft Intune számítógépügyféllel való felügyeletének általános feladatai](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### A Vállalati portál újdonságai

__Munkahelyi portál webhely__
- **Továbbfejlesztett végfelhasználói élmény Windows-eszközök regisztrálásakor**<br/>
Egyértelműbbek lettek a feltételes hozzáféréses regisztráció lépései a Windows 8.1, valamint a Windows 10 asztali verzió és Windows 10 Mobile rendszerekhez készült Vállalati portálon. A felhasználók mostantól különálló „Eszközök regisztrációja” és „Munkahelyi csatlakoztatás” lépéseket látnak majd, ami megkönnyíti számukra az eszköz állapotának megállapítását, és a folyamat befejezését a Munkahelyi csatlakoztatás esetleges meghiúsulása után. A különálló lépések várhatóan a rendszergazdák számára is megkönnyítik majd a hibák felderítését és elhárítását. Korábban, ha a végfelhasználó regisztrációt és Munkahelyi csatlakozást próbált végezni, és a regisztráció sikeres volt, de a Munkahelyi csatlakoztatás meghiúsult, akkor a regisztrált eszköz nem jelent meg a felhasználók által azonosítható eszközök listáján, ami problémákat eredményezhetett.

__Android__
- **Androidos Munkahelyi portál alkalmazás**<br/>
Ha Android-végfelhasználók egy hibaüzenetet kapnak arról, hogy az eszközről hiányzik egy szükséges tanúsítvány, a „Probléma megoldása” gombra koppintva megtudhatják, milyen [lépésekkel](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) végezhetik el a hiányzó tanúsítvány telepítését. Ha a felhasználók elvégezték a lépéseket, de továbbra is egy „hiányzó tanúsítvány” hibaüzenetet kapnak, a rendszer megkéri őket, hogy adják meg a rendszergazdájuknak ezt a [hivatkozást](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), amely leírja azokat a lépéseket, amelyekkel a rendszergazda elháríthatja a tanúsítvánnyal kapcsolatos problémát.

- **Az alkalmazások közvetlen telepíthetőségének korlátozása regisztrált eszközökön**<br/>
Az Android rendszerű eszközökre mostantól nem lehet a Vállalati portál webhelyen keresztül alkalmazásokat telepíteni, ha az eszközök nincsenek regisztrálva az Intune-ban az Intune Vállalati portál alkalmazás Android-verziójával.
<!---TFS 1299082--->

__iOS__
- **Változások a készülékregisztráció-kezelői fiókokban az iOS-es Vállalati portál alkalmazásban**<br/>
A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM) eszközt az iOS-es Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon.

A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre. Emellett az Intune-ból kivezettük a DEM-fiókoknak az Apple Device Enrollment Programmal és az Apple Configurator eszközzel való használatát. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.

Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges. További információ: [Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Windows-szolgáltatások névváltozásai
- A [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) mostantól **Windows Hello for Business** néven érhető el.
- A [Vállalati adatvédelem](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) mostantól **Windows információvédelem** ismert.

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
- **Feltételes hozzáférés böngészőhöz.** Feltételes hozzáférési házirendet állíthat be az [Exchange Online-hoz](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) és a [SharePoint Online-hoz](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), így azok csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök támogatott webböngészőiről érhetők majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **A Dynamics CRM Online támogatja a feltételes hozzáférést.** Feltételes hozzáférési házirendet állíthat be a [Dynamics CRM Online-hoz](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), hogy csak a felügyelt és a szabályozásnak megfelelő iOS- és Android-eszközök érhessék el. A Dynamics CRM mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés végrehajtása előtt a rendszer kérni fogja a regisztrálást az Intune-ba, valamint a meg nem felelést okozó problémák megszüntetését.
<!---TFS1295358--->

### Az Intune Munkahelyi portál újdonságai

__Androidos Munkahelyi portál alkalmazás__

- Ha a rendszergazdák az új „Az eszközök tiltsák le az ismeretlen forrásból származó alkalmazások telepítését (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az ismeretlen forrásokból származó alkalmazások telepítését le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Biztonság** menüben ki kell kapcsolniuk az **Ismeretlen források** lehetőséget. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Futtasson biztonsági fenyegetés elleni keresést az eszközön” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Google** > **Biztonság** menüben be kell kapcsolniuk a **Biztonsági fenyegetések keresése az eszközön** beállítást. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak az üzenetről és a beállítás bekapcsolásának okáról.

- Ha a rendszergazdák az új „Az USB-hibakeresés letiltásának megkövetelése (Android 4.2+)” házirendet alkalmazzák, az Android 4.2-vel és későbbi verziókkal rendelkező végfelhasználók számára „Az USB-hibakeresést le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Fejlesztői beállítások** menüben ki kell kapcsolniuk az **USB-hibakeresést**. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0+)” házirendet alkalmazzák, az Android 6.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az eszköz nem éri el a minimális Android biztonsági javítási szintet” üzenet jelenik meg. A felhasználóknak ekkor telepíteniük kell a szükséges biztonsági javítási szintet. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak a biztonsági javítás telepítéséről és arról, hogy jelenleg melyik biztonsági javítási verzióval rendelkeznek.

__iOS rendszerű Vállalati portál alkalmazás__

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
Már az Azure Active Directory- (AAD-) bérlőben szereplő bármely felhasználónál megtekintheti az alkalmazásfelügyeleti házirendek [állapotát](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune). Ez a következő teendőket foglalja magában:
   - Eszközök
   - Alkalmazások az eszközön

   Az állapot a következő értékeket veheti fel:

   **Beadva**: azt jelzi, hogy a házirend telepítve van a felhasználónál, az alkalmazást pedig használták munkahelyi környezetben, és sikeresen megkapta a házirendet.

    **Nincs beadva:** azt jelzi, hogy a házirend telepítve van a felhasználónál, de az alkalmazást egyszer sem használták a munkahelyi környezetben.


- **Az Outlook-névjegyek szinkronizálásának megakadályozása mobilalkalmazás-felügyelettel (Android).**
Új beállítás érhető el a [mobilalkalmazások eszközregisztráció nélküli felügyeletéhez](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune). Ezzel a beállítással megakadályozhatja, hogy az alkalmazás szinkronizálja a névjegyeket a natív címjegyzékbe az Android-eszközökön. Ha a beállítás engedélyezve van, a megcélzott alkalmazások nem menthetnek névjegyeket a natív címjegyzékbe. Ha a beállítás nincs engedélyezve, a megcélzott alkalmazások menthetik a névjegyeket a natív címjegyzékbe. Amikor [távolról törli egy eszköz vagy alkalmazás tartalmát](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), a natív címjegyzék mentett összes névjegy törlődni fog. Ezt az új beállítást már az Android-eszközökön elérhető Outlook alkalmazás is támogatja.

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

>[!div class="step-by-step"]

>[&larr; **Az Intune újdonságai**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO3-->



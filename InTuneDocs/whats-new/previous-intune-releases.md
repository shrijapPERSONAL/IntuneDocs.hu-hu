---
title: "Korábbi kiadások | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ffbb26f30c7801789a47d57ffed00696f5e6d81a
ms.openlocfilehash: 11e90ce994d17d9dcc62edba775dd0ab8110414e


---

# Az Intune korábbi kiadásai
## 2016. augusztus
## 2016. augusztus
## Alkalmazáskezelés
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Rejtett és megjelenített alkalmazások iOS 9.3 alatt
Az iOS 9.3-at vagy annál újabb verziójú operációs rendszert futtató eszközök esetében az iOS-es általános konfigurációs szabályzat rejtett és megjelenített alkalmazásokat tartalmazó listája segítségével:
- Megadhatja a felhasználók elől elrejtett alkalmazások listáját. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
- Megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

Az így megadott alkalmazások egyaránt lehetnek Ön által telepített, illetve olyan beépített iOS-alkalmazások, mint az Üzenetek és a Megjegyzések. Részletekért lásd: [iOS-szabályzatbeállítások a Microsoft Intune-ban]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
### Engedélyezett és letiltott alkalmazások házirendje Samsung KNOX-eszközökhöz
Mostantól egyedi szabályzatot konfigurálhat Samsung KNOX-eszközökhöz, amely lehetővé teszi az alábbiak egyikének létrehozását:
- Az eszközön nem futtatható alkalmazások listája. A tiltólistán szereplő alkalmazások nem aktiválhatók az eszközön, még ha telepítve is vannak.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung KNOX-ot futtató eszközökön használhatók.
Részletekért lásd: [Egyéni szabályzat használata alkalmazások engedélyezéséhez és tiltásához Samsung KNOX-eszközökön](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->
### A mobilalkalmazás-kezelési (MAM) szabályzatokkal kompatibilis új alkalmazások
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) és [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) operációs rendszer alatt a Yammer-alkalmazás már kompatibilis az [Intune mobilalkalmazás-kezelési (MAM) szabályzatokkal](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), függetlenül attól, hogy az eszköz regisztrált-e vagy sem.

A MAM-kompatibilis alkalmazások teljes listáját lásd a [Microsoft Intune-alkalmazáspartnerek](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) webhelyén.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune Viewer-alkalmazások
Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos [Rights Management alkalmazás (RMS-megosztó alkalmazás)](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. Onnantól kezdve, hogy az Intune Viewer alkalmazás már nem lesz támogatott, eltávolítjuk a Google Store áruházból, és nem lesz elérhető további használatra.

## Eszközkezelés
### Android 7.0-támogatás
Az Intune azonnali támogatást nyújt az Android 7.0 operációs rendszerhez mobileszközökön.
<!---TFS 1262053--->
### Az új jelszó távolról történő kérésének Google általi megszüntetése Android 7.0 rendszerű eszközökön
A Google megszünteti azt a lehetőséget, hogy a rendszergazdák és a végfelhasználók távolról új jelszót kérhessenek Android 7.0 rendszerű eszközükhöz. Korábban a rendszergazdák távolról új jelszót állíthattak be a felhasználók számára, a felhasználók pedig a Vállalati portálról tehették meg ugyanezt.



## A Vállalati portál újdonságai
### Munkahelyi portál webhely
- **Visszajelzési hivatkozás a Vállalati portálról a Microsofthoz** <br/>
A Vállalati portál webhelyen az oldal alján található új „Visszajelzés” hivatkozásra koppintva a felhasználók visszajelzést küldhetnek a Microsoftnak a webhellyel kapcsolatos tapasztalataikról. A névtelenített formában összegyűjtött visszajelzéseket a Microsoft a Vállalati portál nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!--- TFS 1313657 checked--->

### iOS
- **A felügyelt böngésző iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
A Microsoft Intune Managed Browser alkalmazás iOS-verziója frissítve lett, és már támogatja az iOS 8.0-s vagy újabb rendszerű eszközöket. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható a jelenlegi Managed Browser alkalmazás, kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253 checked--->

## Mi várható?

### iOS 10-támogatás
Az Intune teljes körűen támogatja az iOS 10-et. További információ az iOS 10 nyilvános bemutatását követően lesz elérhető.

### Az Intune-csoportok 2016 szeptemberétől Azure Active Directory-csoportokká alakulnak
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

### „Értesítések” bevezetése a Vállalati portál Android-verziójában
Szeptemberben egy frissítést adunk ki a Vállalati portál Android-verziójához, amely bevezet egy új **Értesítések** ikont a kezdőlapon. Az ikonra koppintva megnyílik az **Értesítések** oldal, amely megjeleníti a végfelhasználó számára az összes, figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Ha az iOS rendszerű Vállalati portál alkalmazást is használja, akkor már ismerheti az Értesítések nyújtotta felhasználói élményt. Az **Értesítések** lap bevezetésével nem fog a Vállalati portál Android-verziójának minden egyes elindításakor vagy folytatásakor megjelenni a **Vállalati hozzáférés beállítása** képernyő, ha az eszköz már regisztrálva van. Tisztában vagyunk azzal, hogy sokan hoztak létre végfelhasználói útmutatókat, és nagy hasznát veszik az előzetes értesítéseknek, amikor az útmutatók vagy a képernyőképek frissítésére lehet szükség. Kérjük, frissítsék a dokumentációkat, hogy azok tükrözzék a felhasználói élménnyel kapcsolatos közelgő változásokat. A frissített képernyőképek itt találhatók: https://aka.ms/androidcpupdate.  

### Fejlesztések azzal kapcsolatban, hogy az iOS-végfelhasználók hogyan kapják meg az alkalmazásaikat
Szeptemberben a következő változásokra kerül sor az iOS-es Vállalati portál alkalmazás alkalmazáscsempéivel kapcsolatban annak érdekében, hogy a felhasználók valamennyi alkalmazásukat egyetlen helyen, a Vállalati portál webhelyen láthassák különböző nézetekben. Jelenleg az Apple korlátozásai tiltják az üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban; ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk.

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
#### Az alkalmazáslétesítési profilok frissítéseivel kapcsolatos felhasználói élmény javítása
Az Apple iOS üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.

Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában 3 évig érvényes. A létesítési profil viszont 1 év után lejár. Ettől a frissítéstől kezdve az Intune biztosítja azokat az eszközöket, amelyekkel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak. További információk: [iOS mobil létesítésiprofil-házirendek használata az üzletági alkalmazások naprakészen tartására](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
#### Az Intune-hoz készült Xamarin SDK már elérhető
Az Intune App SDK Xamarin összetevőjével engedélyezheti az Intune mobilalkalmazás-felügyeleti funkciókat a Xamarinnal készült, iOS vagy Android rendszerű alkalmazásokban. Az összetevőt a [Xamarin áruházban](https://components.xamarin.com/view/Microsoft.Intune.MAM) vagy a [Microsoft Intune GitHub-oldalon](https://github.com/msintuneappsdk) érheti el.
<!--- TFS 1061478 --->

### Eszközkezelés
#### Megnövelt eszközregisztrációs limit
Az Intune a konfigurálható eszközök regisztrációs korlátját felhasználónként 5 eszközről 15-re növelte.
<!---TFS 1289896 --->

#### Az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek TeamViewer-integrációja
Az Intune ügyfélszoftvert futtató Windows-számítógépeken érvénybe léptethető [TeamViewer](https://www.teamviewer.com)-integráció segítségével távsegítség-munkameneteket indíthat más Windows-számítógépekkel, ami jelentős előnyt jelent a végfelhasználói ügyfélszolgálat számára. Ez a lehetőség a Windows 7, 8, 8.1 és Windows 10 rendszerekre egyaránt kiterjed. Részletekért lásd: [A Windows rendszerű számítógépek a Microsoft Intune számítógépügyféllel való felügyeletének általános feladatai](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### A Vállalati portál újdonságai
#### Munkahelyi portál webhely
- **Továbbfejlesztett végfelhasználói élmény Windows-eszközök regisztrálásakor**<br/>
Egyértelműbbek lettek a feltételes hozzáféréses regisztráció lépései a Windows 8.1, valamint a Windows 10 asztali verzió és Windows 10 Mobile rendszerekhez készült Vállalati portálon. A felhasználók mostantól különálló „Eszközök regisztrációja” és „Munkahelyi csatlakoztatás” lépéseket látnak majd, ami megkönnyíti számukra az eszköz állapotának megállapítását, és a folyamat befejezését a Munkahelyi csatlakoztatás esetleges meghiúsulása után. A különálló lépések várhatóan a rendszergazdák számára is megkönnyítik majd a hibák felderítését és elhárítását. Korábban, ha a végfelhasználó regisztrációt és Munkahelyi csatlakozást próbált végezni, és a regisztráció sikeres volt, de a Munkahelyi csatlakoztatás meghiúsult, akkor a regisztrált eszköz nem jelent meg a felhasználók által azonosítható eszközök listáján, ami problémákat eredményezhetett.

#### Android
- **Androidos Munkahelyi portál alkalmazás**<br/>
Ha Android-végfelhasználók egy hibaüzenetet kapnak arról, hogy az eszközről hiányzik egy szükséges tanúsítvány, a „Probléma megoldása” gombra koppintva megtudhatják, milyen [lépésekkel](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) végezhetik el a hiányzó tanúsítvány telepítését. Ha a felhasználók elvégezték a lépéseket, de továbbra is egy „hiányzó tanúsítvány” hibaüzenetet kapnak, a rendszer megkéri őket, hogy adják meg a rendszergazdájuknak ezt a [hivatkozást](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), amely leírja azokat a lépéseket, amelyekkel a rendszergazda elháríthatja a tanúsítvánnyal kapcsolatos problémát.

- **Az alkalmazások közvetlen telepíthetőségének korlátozása regisztrált eszközökön**<br/>
Az Android rendszerű eszközökre mostantól nem lehet a Vállalati portál webhelyen keresztül alkalmazásokat telepíteni, ha az eszközök nincsenek regisztrálva az Intune-ban az Intune Vállalati portál alkalmazás Android-verziójával.
<!---TFS 1299082--->

#### iOS
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

- **Éljen az iOS harmadik fél által nyújtott, MDM-megoldásokban regisztrált eszközök „Megnyitás ezzel” típusú kezelésének előnyével** A harmadik felek által nyújtott mobileszköz-kezelési forgalmazójával kihasználhatja az iOS „Megnyitás ezzel” típusú kezelését. Korlátozásokat állíthat be a konfigurációs profil beállításaiban, és az [iOS-alkalmazások közti adatátvitel kezelésével](/intune/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune) telepítheti az alkalmazást.

     Ez a módszer két fő előnnyel jár:

     1. A felhasználóknak be kell jelentkezniük a munkahelyi fiókjukkal, mielőtt hozzáférhetnének a szervezeti adatokhoz a Cloud Services szolgáltatásokból vagy más alkalmazásokból. Ez biztosítja, hogy mobilalkalmazás-kezelési (MAM-) házirendek legyenek érvényben az adatok elérésekor.

     2. A külső MDM-megoldással telepített felügyelt e-mail-profilok és más felügyelt alkalmazások fájlokat és adatokat oszthatnak meg az Intune MAM-szabályzatokkal rendelkező alkalmazásokkal.

- **A Microsoft Outlook alkalmazás kezelése MAM-szabályzatokkal az Intune-ban nem regisztrált eszközökön** Mostantól az Intune mobilalkalmazás-kezelési szabályzatával kezelheti a Microsoft Outlook alkalmazást az Intune-ban nem regisztrált eszközökön. A frissített Microsoft Outlook alkalmazás a MAM-képességekkel az [iOS-](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) és [Android-](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)eszközökhöz is elérhető. A [Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése](https://technet.microsoft.com/library/mt627829.aspx) témakörben található utasításokkal hozzon létre egy MAM-házirendet.  


- **A mobilalkalmazások konfigurációs szabályzataival rugalmasabban szabhatja meg az iOS-alkalmazások felhasználói adatait** Megadhat olyan felhasználói beállításokat, amelyekre az iOS-alkalmazásoknak szükségük lehet a megnyitásukkor. Megadhat például egy hálózati portot vagy egy felhasználónevet. Részletes leírás: [iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).


- **Az Adobe Reader for Microsoft Intune telepítése a vállalata Intune-ban kezelt iOS-eszközeire ** Az Adobe Reader iOS-alkalmazás már regisztrált eszközökön is kezelhető az Intune mobilealkalmazás-kezelési házirendjével.

- **A telepített webklipeknek a felügyelt böngészőben való megnyitása** Célzott webklipeket telepíthet, amelyek csak a felügyelt böngészővel nyithatók meg az iOS- és Android-eszközökön. Vállalati erőforrásokra mutató hivatkozásokat telepíthet például a Vállalati portálon keresztül, és amikor a felhasználók megnyitják a hivatkozásokat, azok közvetlenül a felügyelt böngészőben nyílnak meg, ahol a MAM-házirend védi őket. Részletes leírás: [Alkalmazások telepítése](/intune/deploy-use/deploy-apps).


- **Windows 10-eszközökre készült Vállalati Windows Áruház alkalmazásainak keresése, kezelése és elosztása az Intune rendszergazdai konzolból** Az Intune támogatást nyújt a Vállalati Windows Áruházhoz, így könnyebben kereshet, kezelhet és oszthat el alkalmazásokat a kezelt Windows 10-eszközei között. A Vállalati Windows Áruházzal kezelheti ezen alkalmazások telepítését és megfigyelését az Intune felügyeleti konzoljáról – ugyanarról a konzolról, amellyel a többi alkalmazást is kezeli. A Vállalati Windows Áruház az „online licencelt alkalmazások” tartalmát és licencelését felügyeli. Részletes leírás: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).


### Eszközkezelés
- **PFX-tanúsítványok elosztása iOS-eszközökön** Az Intune-rendszergazdák iOS PFX-tanúsítványokat hozhatnak létre és telepíthetnek a Wi-Fi-, e-mail- és VPN-hitelesítéshez az iOS-eszközökön. Ez a funkció már elérhető az Android- és Windows 10-es eszközökhöz. Részletes leírás: [Vállalati erőforrások elérésének lehetővé tétele tanúsítványprofilokkal](/intune/deploy-use/secure-resource-access-with-certificate-profiles).


- **Alkalmazások és házirendek alkalmazása különböző eszközcsoportokra a felhasználói kategóriák alapján** Az Intune-rendszergazdák mostantól egyéni eszközkategóriákat határozhatnak meg, amelyekből a felhasználók válogathatnak a regisztrálás során. A rendszergazdák például azt kívánhatják, hogy a felhasználóik adják meg, hogy a „Pénztárhoz”, „Szállítójárműhöz” vagy „Leltárhoz” használt eszközt regisztrálnak-e. A kiválasztott kategória miatt az eszköz egy Intune-eszközcsoport tagjává válik, amely különböző alkalmazások és házirendek a regisztrált eszközre való telepítéséhez használható. Részletes leírás: [Eszközök kategorizálása eszközcsoport-leképezéssel](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

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

    Az eszközállapot beállításával, az összegyűjtött adatpontokkal és az eszközállapot-jelentéssel kapcsolatos részleteket lásd: [Bevezetés a Microsoft Intune eszközmegfelelőségi házirendjeinek kezelésébe](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). A [HAS szolgáltatás részletei](https://msdn.microsoft.com/en-us/library/dn934876.aspx) című témakör részletesen leírja a szolgáltatást.

* **Windows 10 Passport for Work házirend- és tanúsítványkezelés** Az Intune lehetővé teszi az [integrációt a Microsoft Passport for Work](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) nevű Windows 10-es alternatív bejelentkezési módszerrel, amely Active Directoryt vagy egy Azure Active Directory-fiókot használ jelszó, intelligens kártya vagy virtuális intelligens kártya helyett. A Passport lehetővé teszi jelszó helyett felhasználói kézmozdulatok használatát a bejelentkezéshez. A felhasználói hitelesítési mód lehet egy egyszerű PIN-kód, biometrikus hitelesítés, mint például a Windows Hello, vagy egy külső eszköz, például egy ujjlenyomat-olvasó.

* **VPN-csatlakozás választott alkalmazásokban** Kiválaszthat olyan alkalmazásokat, amelyek automatikusan csatlakoznak a vállalati hálózathoz VPN-kapcsolaton keresztül. A VPN-profil beállításakor létrehozhatja az alkalmazások listáját a Segítség a felhasználóknak a munkájukhoz való csatlakozásban VPN-profilok használatával a Microsoft Intune-nal című részben leírtak alapján.

* **Windows 10 – teljes törlés támogatása** Mostantól az Intune-nal regisztrált Windows 10-es asztali eszközök teljes távoli törlését is elrendelheti az Intune felügyeleti konzoljáról. A Windows 10 teljes törlési funkciója az eszköz gyári beállításainak visszaállítását végzi el.


### Az Apple Volume Purchase program (VPP) frissítése
Az Intune most segít [az Apple Volume Purchase Program (VPP) for Business programon keresztül vásárolt alkalmazások felügyeletében](/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Ebbe beletartozik a licencinformációk az Apple és az Intune közötti szinkronizálása és annak nyomon követése, hogy az egyes alkalmazások hány példánya van telepítve.

### Vállalati tulajdonú eszközök azonosítása IMEI számokkal
[Nemzetközi mobilkészülék-azonosító (IMEI) számokat importálhat](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) IMEI-számokkal rendelkező mobileszköz-platformok esetén, hogy könnyebben azonosítsa a vállalati tulajdonban lévő mobileszközöket. Az Intune-ban történő regisztráció után az importált IMEI-számokkal rendelkező eszközök Vállalati címkével rendelkeznek, amellyel a személyes eszközökre alkalmazott házirendektől eltérő házirendek alkalmazhatók.

### Mostantól több alkalmazás kompatibilis az Intune MAM-házirendekkel
Mostantól a Microsoft partnereinek további alkalmazásai kompatibilisek az Intune mobilalkalmazás-kezelési (MAM-) házirendjeivel (az Intune által felügyelt eszközökhöz):
* Box for EMM (a Box Inc vállalattól) – csak iOS esetén
* Adobe Reader (az Adobe vállalattól) – csak Android esetén
* Foxit PDF Reader (a Foxit Corporation vállalattól) – iOS és Android esetén


### Az IE9 támogatása januárban megszűnik
2016 februárjától többé nem támogatjuk az Internet Explorer 9-et mint a Microsoft Intune Vállalati portál webhelyének, az Intune-fiókportálnak és az Intune felügyeleti konzoljának eléréséhez használható hivatalos böngészőt. Ezért át kell térnie az Internet Explorer 10 vagy a böngésző újabb verziójának használatára.


>[!div class="step-by-step"]

>[&larr; **Az Intune újdonságai**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO1-->



---
title: "Újdonságok | Microsoft Intune"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8bff8951c8ced7656f007787d614fd277401fd0
ms.openlocfilehash: 35612b07cf18d8038af51cdfac5146b9e8a876fc


---

# Újdonságok a Microsoft Intune-ban
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## 2016. július
## Alkalmazáskezelés
### Az alkalmazáslétesítési profilok frissítéseivel kapcsolatos felhasználói élmény javítása
Az Apple iOS üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.

Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában 3 évig érvényes. A létesítési profil viszont 1 év után lejár. Ettől a frissítéstől kezdve az Intune biztosítja azokat az eszközöket, amelyekkel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak. További információk: [iOS mobil létesítésiprofil-házirendek használata az üzletági alkalmazások naprakészen tartására](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
### Az Intune-hoz készült Xamarin SDK már elérhető
Az Intune App SDK Xamarin összetevőjével engedélyezheti az Intune mobilalkalmazás-felügyeleti funkciókat a Xamarinnal készült, iOS vagy Android rendszerű alkalmazásokban. Az összetevőt a [Xamarin áruházban](https://components.xamarin.com/view/Microsoft.Intune.MAM) vagy a [Microsoft Intune GitHub-oldalon](https://github.com/msintuneappsdk) érheti el.
<!--- TFS 1061478 --->

## Eszközkezelés
### Megnövelt eszközregisztrációs limit
Az Intune a konfigurálható eszközök regisztrációs korlátját felhasználónként 5 eszközről 15-re növelte.
<!---TFS 1289896 --->



## A Vállalati portál újdonságai
### Munkahelyi portál webhely
- **Továbbfejlesztett végfelhasználói élmény Windows-eszközök regisztrálásakor**<br/>
Egyértelműbbek lettek a feltételes hozzáféréses regisztráció lépései a Windows 8.1, valamint a Windows 10 asztali verzió és Windows 10 Mobile rendszerekhez készült Vállalati portálon. A felhasználók mostantól különálló „Eszközök regisztrációja” és „Munkahelyi csatlakoztatás” lépéseket látnak majd, ami megkönnyíti számukra az eszköz állapotának megállapítását, és a folyamat befejezését a Munkahelyi csatlakoztatás esetleges meghiúsulása után. A különálló lépések várhatóan a rendszergazdák számára is megkönnyítik majd a hibák felderítését és elhárítását. Korábban, ha a végfelhasználó regisztrációt és Munkahelyi csatlakozást próbált végezni, és a regisztráció sikeres volt, de a Munkahelyi csatlakoztatás meghiúsult, akkor a regisztrált eszköz nem jelent meg a felhasználók által azonosítható eszközök listáján, ami problémákat eredményezhetett.

### Android
- **Androidos Munkahelyi portál alkalmazás**<br/>
Ha Android-végfelhasználók egy hibaüzenetet kapnak arról, hogy az eszközről hiányzik egy szükséges tanúsítvány, a „Probléma megoldása” gombra koppintva megtudhatják, milyen [lépésekkel](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) végezhetik el a hiányzó tanúsítvány telepítését. Ha a felhasználók elvégezték a lépéseket, de továbbra is egy „hiányzó tanúsítvány” hibaüzenetet kapnak, a rendszer megkéri őket, hogy adják meg a rendszergazdájuknak ezt a [hivatkozást](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), amely leírja azokat a lépéseket, amelyekkel a rendszergazda elháríthatja a tanúsítvánnyal kapcsolatos problémát.

- **Az alkalmazások közvetlen telepíthetőségének korlátozása regisztrált eszközökön**<br/>
Az Android rendszerű eszközökre mostantól nem lehet a Vállalati portál webhelyen keresztül alkalmazásokat telepíteni, ha az eszközök nincsenek regisztrálva az Intune-ban az Intune Vállalati portál alkalmazás Android-verziójával.
<!---TFS 1299082--->

### iOS
- **Változások a készülékregisztráció-kezelői fiókokban az iOS-es Vállalati portál alkalmazásban**<br/>
A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM) eszközt az iOS-es Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon.

    A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre. Emellett az Intune-ból kivezettük a DEM-fiókoknak az Apple Device Enrollment Programmal és az Apple Configurator eszközzel való használatát. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.

    Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges. További információ: [Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Windows-szolgáltatások névváltozásai
- A [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) mostantól **Windows Hello for Business** néven érhető el.
- A [Vállalati adatvédelem](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) mostantól **Windows információvédelem** ismert.

## Mi várható?
### Az Intune-csoportok 2016 augusztusától Azure Active Directory-csoportoká alakulnak
Az Intune egy új csoportkezelési megoldást vezet be, amely Azure Active Directory- (AAD-) biztonsági csoportokat használ az Intune-ban. Ezek az Azure AD-alapú biztonsági csoportok felhasználókat és eszközöket egyaránt tartalmazhatnak, és az új, Azure-alapú Intune felügyeleti portál bemutatása után e csoportok használatával történik majd minden csoportfelügyeleti, valamint szabályzat- és profillétesítési művelet.

Az új felhasználói élmény a következő előnyöket hordozza magában:
- Megszünteti a csoportok szolgáltatások közti duplikálásának szükségességét.
- Hozzáférést nyújt néhány új Prémium szintű Azure Active Directory- (AADP-) csoportszolgáltatáshoz.
- Bővíthetőséget tesz lehetővé a PowerShell és a Graph használatával.
- Vállalati mobileszköz-felügyeleti szinten egyesíti a csoportfelügyeleti élményt.

A biztonsági csoportokra való áttérés lehetővé tételének érdekében a jelenlegi felügyeleti konzol felhasználói élménye is változni fog. Az ezt érintő változtatások, valamint az Azure AD-biztonságicsoportok használata az Intune-dokumentációban lesznek rögzítve.

Az Intune új felhasználói a biztonsági csoportokat érintő egyes változásokkal előbb szembesülnek majd, mint a jelenlegi bérlők.

A csoportfelügyelettel kapcsolatos változtatások mellett a következő funkciók megszűnnek:
- Tagok vagy csoportok kihagyása egy új csoport létrehozásakor
- **Nem csoportosított felhasználók** és **Nem csoportosított eszközök** csoportjai
- **Csoportok kezelése** a szolgáltatásadminisztrátori szerepkörben
- Egyéni, csoportalapú riasztások az értesítési szabályokkal kapcsolatban
- Pivotálás csoportokkal a jelentésekben

A megszűnő funkciók kiváltásával kapcsolatos bővebb információkat augusztusban hozzuk nyilvánosságra.

### „Értesítések” bevezetése a Vállalati portál Android-verziójában
Augusztusban egy frissítést adunk ki a Vállalati portál Android-verziójához, amely bevezet egy új **Értesítések** ikont a kezdőlapon. Az ikonra koppintva megnyílik az **Értesítések** oldal, amely megjeleníti a végfelhasználó számára az összes, figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Ha az iOS rendszerű Vállalati portál alkalmazást is használja, akkor már ismerheti az Értesítések nyújtotta felhasználói élményt. Az **Értesítések** lap bevezetésével nem fog a Vállalati portál Android-verziójának minden egyes elindításakor vagy folytatásakor megjelenni a **Vállalati hozzáférés beállítása** képernyő, ha az eszköz már regisztrálva van. Tisztában vagyunk azzal, hogy sokan hoztak létre végfelhasználói útmutatókat, és nagy hasznát veszik az előzetes értesítéseknek, amikor az útmutatók vagy a képernyőképek frissítésére lehet szükség. Kérjük, frissítsék a dokumentációkat, hogy azok tükrözzék a felhasználói élménnyel kapcsolatos közelgő változásokat. A frissített képernyőképek itt találhatók: https://aka.ms/androidcpupdate.  



### A felhőplatform ütemterve
Maradjon naprakész az Intune jövőbeli fejlesztéseiről a [Cloud Platform ütemterv](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) használatával.

### Szolgáltatások érvénytelenítése
- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
Júliustól az iOS rendszerhez készült Microsoft Intune vállalati portál alkalmazás minden felhasználójának az alkalmazás legújabb verzióját kell majd használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

- **A felügyelt böngésző iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
Augusztusban az Intune egy olyan frissítést ad ki a Microsoft Intune Managed Browser alkalmazás iOS-verziójához, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket támogatja. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható lesz a jelenlegi Managed Browser alkalmazás, de kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253--->

- **A Windows 8 és a Windows Phone 8 vállalati portál alkalmazásai 2016. szeptembertől elavulttá válnak** <br/>
2016. szeptembertől a Microsoft Intune már nem fogja támogatni a Microsoft Intune vállalati portál alkalmazásait Windows Phone 8 és Windows 8 platformokon. Frissítése az eszközöket a Windows 8.1 és a Windows Phone 8.1 rendszerekre, és használja a megfelelő Windows 8.1 és Windows Phone 8.1 vállalati portál alkalmazásokat az alkalmazásoknak ezekre az eszközökre történő további terjesztésére.
<!---TFS 1255391--->

- **Intune Viewer-alkalmazások** <br/>
Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer Android-eszközökre a Google Play Áruházból

  Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos [Rights Management alkalmazás (RMS-megosztó alkalmazás)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. Onnantól kezdve, hogy az Intune Viewer alkalmazás már nem lesz támogatott, eltávolítjuk a Google Store áruházból, és nem lesz elérhető további használatra.

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



## Az Intune korábbi kiadásai
Az Intune-ban az elmúlt hat hónapban bevezetett újdonságok listája [Az Intune korábbi kiadásai](previous-intune-releases.md) című cikkben olvasható.

### További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO3-->



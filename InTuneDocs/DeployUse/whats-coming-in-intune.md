---
title: "Várható újdonságok | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35ee5d0c8898c95898c0527a623cf13c454387f2
ms.openlocfilehash: 831cec6cd0e02a94c1a3f67d4adf5a5dcbb01449


---

# A Microsoft Intune várható újdonságai – július
Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. A várható újdonságokkal kapcsolatban friss hírekért látogasson vissza.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Alkalmazáskezelés
### Az alkalmazáslétesítési profilok frissítéseivel kapcsolatos felhasználói élmény javítása
Az Apple iOS üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.

Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában 3 évig érvényes. A létesítési profil viszont 1 év után lejár. Ettől a frissítéstől kezdve az Intune biztosítja azokat az eszközöket, amelyekkel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak.
<!--- TFS 1280247--->

### Xamarin-támogatás
A Microsoft Intune App SDK a következő használati helyzetekben fogja támogatni a Xamarin-alkalmazásokat:

- Új alkalmazások írása vagy a meglévő üzleti alkalmazások kódjának módosítása az Intune SDK-val. A bővítmény a [Microsoft Intune Github-oldalról](https://github.com/msintuneappsdk) lesz letölthető.
- A mobilalkalmazás-felügyelet támogatásának kiterjesztése a meglévő üzleti alkalmazásokra az Intune alkalmazásburkoló eszközével.

Ha segítségre van szüksége a megfelelő módszer kiválasztásához, lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Eszközkezelés
### Megnövelt eszközregisztrációs limit
Az Intune a konfigurálható eszközök regisztrációs korlátját felhasználónként 5 eszközről 15-re növeli.
<!---TFS 1289896 --->

## Csoportfelügyelet
### Az Intune-csoportok 2016 augusztusától Azure Active Directory-csoportoká alakulnak
Az Intune egy új csoportkezelési megoldást vezet be, amely Azure Active Directory- (AAD-) biztonsági csoportokat használ felhasználói és eszközcsoportokként az Intune-ban. **Az új, Azure-alapú Intune felügyeleti portál bemutatása után** e csoportok használatával történik majd minden csoportfelügyeleti, valamint szabályzat- és profillétesítési művelet.

Az új felhasználói élmény kiküszöböli a csoportok szolgáltatások közti duplikálásának szükségességét, **hozzáférést nyújt néhány új Prémium szintű Azure Active Directory- (AADP-) csoportszolgáltatáshoz**, és bővíthetőséget tesz lehetővé a PowerShell és a Graph használatával. Emellett vállalati mobileszköz-felügyeleti szinten egyesíteni fogja a csoportfelügyeleti élményt.

A biztonsági csoportokra való áttérés lehetővé tételének érdekében a **jelenlegi felügyeleti konzol** felhasználói élménye is változni fog. **Az ezt érintő változtatások, valamint az AAD-biztonságicsoportok használata az Intune-dokumentációban lesznek rögzítve**.

Az Intune új felhasználói **a biztonsági csoportokat érintő egyes változásokkal előbb szembesülnek majd, mint a jelenlegi bérlők**.

A csoportfelügyelettel kapcsolatos változtatások mellett **a következő funkciók megszűnnek**:
- Tagok vagy csoportok kihagyása egy új csoport létrehozásakor
- „Csoportok kezelése” a szolgáltatásadminisztrátori szerepkörben
- Egyéni, csoportalapú riasztások az értesítési szabályokkal kapcsolatban
- Pivotálás csoportokkal a jelentésekben


## Vállalati portál

### „Értesítések” bevezetése a Vállalati portál Android-verziójában
Augusztusban egy frissítést adunk ki a Vállalati portál Android-verziójához, amely bevezet egy új **Értesítések** ikont a kezdőlapon. Az ikonra koppintva megnyílik az **Értesítések** oldal, amely megjeleníti a végfelhasználó számára az összes, figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Ha az iOS rendszerű Vállalati portál alkalmazást is használja, akkor már ismerheti az Értesítések nyújtotta felhasználói élményt. Az **Értesítések** lap bevezetésével nem fog a Vállalati portál Android-verziójának minden egyes elindításakor vagy folytatásakor megjelenni a **Vállalati hozzáférés beállítása** képernyő, ha az eszköz már regisztrálva van. Tisztában vagyunk azzal, hogy sokan hoztak létre végfelhasználói útmutatókat, és nagy hasznát veszik az előzetes értesítéseknek, amikor az útmutatók vagy a képernyőképek frissítésére lehet szükség. Kérjük, frissítsék a dokumentációkat, hogy azok tükrözzék a felhasználói élménnyel kapcsolatos közelgő változásokat. A frissített képernyőképek itt érhetők el: https://aka.ms/androidcpupdate  

### Segíthet a felhasználóknak megoldani a regisztrációval kapcsolatos problémákat, amikor a Munkahelyi csatlakoztatás meghiúsul
Leegyszerűsödtek a feltételes hozzáféréses regisztráció lépései a Windows 8.1, valamint a Windows 10 asztali verzió és Windows 10 Mobile rendszerekhez készült Vállalati portálon az olyan esetekben, amikor a végfelhasználó által indított Munkahelyi csatlakoztatás meghiúsul. Korábban, ha a végfelhasználó regisztrációt és Munkahelyi csatlakozást próbált kezdeményezni, és a regisztráció sikeres volt, de a Munkahelyi csatlakoztatás meghiúsult, akkor a regisztrált eszköz nem jelent meg a felhasználók által azonosítható eszközök listáján, ami problémákat eredményezhetett. A felhasználók mostantól különálló „Eszközök regisztrációja” és „Munkahelyi csatlakoztatás” lépéseket látnak majd, ami megkönnyíti számukra az eszköz állapotának megállapítását, és a folyamat befejezését a Munkahelyi csatlakoztatás esetleges meghiúsulása után. A különálló lépések várhatóan a rendszergazdák számára is megkönnyítik majd a hibák felderítését és elhárítását.

### Változások a készülékregisztráció-kezelői fiókokban az iOS-es Vállalati portál alkalmazásban
A jobb teljesítmény és méretezés érdekében az Intune a jövőben nem fogja megjeleníteni az összes készülékregisztráció-kezelő (DEM-) eszközt az iOS rendszerhez készült Vállalati portál alkalmazás Saját eszközök panelén. Csak az alkalmazást futtató helyi eszköz jelenik meg, és az is csak abban az esetben, ha korábban már regisztrálták a Vállalati portálon. A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon lesznek majd végrehajthatók.  Emellett az Intune-ból kivezettük a DEM-fiókoknak az Apple Device Enrollment Programmal és az Apple Configurator eszközzel való használatát. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását. Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges.
<!---TFS 1233681--->
### Az alkalmazások közvetlen telepíthetőségének korlátozása regisztrált Android-eszközökön
Az Android rendszerű eszközökre mostantól nem lehet a Vállalati portál webhelyen keresztül alkalmazásokat telepíteni, ha az eszközök nincsenek regisztrálva az Intune-ban az Intune Vállalati portál alkalmazás Android-verziójával. 
<!---TFS 1299082--->

## Szolgáltatások érvénytelenítése
**A Windows 8 és a Windows Phone 8 vállalati portál alkalmazásai 2016. szeptembertől elavulttá válnak.** 2016. szeptembertől a Microsoft Intune már nem fogja támogatni a Microsoft Intune vállalati portál alkalmazásait Windows Phone 8 és Windows 8 platformokon. Frissítése az eszközöket a Windows 8.1 és a Windows Phone 8.1 rendszerekre, és használja a megfelelő Windows 8.1 és Windows Phone 8.1 vállalati portál alkalmazásokat az alkalmazásoknak ezekre az eszközökre történő további terjesztésére.
<!---TFS 1255391--->

**Az értesítési szabályok egyéni csoportcélzási lehetősége megszűnik.**
Az Intune értesítési szabályai határozzák meg, hogy kinek küld értesítő e-mailt az Intune. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016. június 1-jétől fogva a felhasználó által létrehozott csoportok megcélzása nem lesz megvalósítható.

A módosítás előzetes ütemterve a következő:
- 2016 augusztusától az új bérlők számára nem fog megjelenni az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
- 2016 szeptemberétől kezdve egyes meglévő bérlők számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.
- 2016 novemberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az eszközcsoportok kiválasztására szolgáló lépés a varázslóban.

<!---   TFS 1278864--->

**Az iOS rendszerű vállalati portál alkalmazás támogatására vonatkozó módosítások.**
Júliustól az iOS rendszerhez készült Microsoft Intune vállalati portál alkalmazás minden felhasználójának az alkalmazás legújabb verzióját kell majd használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

**Intune Viewer-alkalmazások.** Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. További információk az RMS-megosztó alkalmazásról (a dokumentációra mutató hivatkozással).



### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->



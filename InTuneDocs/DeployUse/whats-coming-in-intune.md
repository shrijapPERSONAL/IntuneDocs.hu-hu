---
title: "Várható újdonságok | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b0653af30aa6e75888dd72c5b3a4afa0b2b1d596
ms.openlocfilehash: a3cc5ea639c31e3fec08e86f27f118e193b8f4b3


---

# A Microsoft Intune várható újdonságai – június
Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. A várható újdonságokkal kapcsolatban friss hírekért látogasson vissza.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Alkalmazáskezelés
### Rejtett és megjelenített alkalmazások iOS 9.3 alatt
Az iOS 9.3-at vagy annál újabb verziójú operációs rendszert futtató felügyelt eszközök esetében az iOS általános konfigurációs szabályzat rejtett és megjelenített alkalmazások listája segítségével:
- Megadhatja a felhasználók elől elrejtett alkalmazások listáját. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
- Megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

Az így megadott alkalmazások egyaránt lehetnek Ön által telepített, illetve olyan beépített iOS-alkalmazások, mint az Üzenetek és a Megjegyzések.
<!---TFS 1279009--->

### Engedélyezett és letiltott alkalmazások házirendje Samsung KNOX-eszközökhöz

Mostantól egyedi szabályzatot konfigurálhat Samsung KNOX-eszközökhöz, amely lehetővé teszi az alábbiak egyikének létrehozását:
- Az eszközön nem futtatható alkalmazások listája. A tiltólistán szereplő alkalmazások nem aktiválhatók az eszközön, még ha telepítve is vannak.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung KNOX-ot futtató eszközökön használhatók.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### A mobilalkalmazás-kezelési (MAM) szabályzatokkal kompatibilis új alkalmazások
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) és [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) operációs rendszer alatt a Yammer-alkalmazás kompatibilis lesz az [Intune mobilalkalmazás-kezelési (MAM) szabályzatokkal](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), függetlenül attól, hogy az eszköz regisztrált-e vagy sem.

A MAM-kompatibilis alkalmazások teljes listáját lásd a [Microsoft Intune-alkalmazáspartnerek](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) webhelyén.
<!--- TFS 1252335 & 1252336--->

## Eszközkezelés
### Android 7.0-támogatás
Augusztustól az Intune azonnali támogatást nyújt az Android 7.0 operációs rendszerhez mobileszközökön.
<!---TFS 1262053--->
### Az új jelszó távolról történő kérésének Google általi megszüntetése Android 7.0 rendszerű eszközökön
A Google megszünteti azt a lehetőséget, hogy a rendszergazdák és a végfelhasználók távolról új jelszót kérhessenek Android 7.0 rendszerű eszközükhöz. Korábban a rendszergazdák távolról új jelszót állíthattak be a felhasználók számára, a felhasználók pedig a Vállalati portálról tehették meg ugyanezt.

## Csoportfelügyelet
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

## Vállalati portál

### Visszajelzési hivatkozás a Vállalati portálról a Microsofthoz
A Vállalati portál webhelyen az oldal alján található új „Visszajelzés” hivatkozásra koppintva visszajelzést küldhetnek a Microsoftnak a webhelyen szerzett tapasztalataikról. A névtelenített formában összegyűjtött visszajelzéseket a Microsoft a Vállalati portál nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!--- TFS 1313657--->

### Fejlesztések azzal kapcsolatban, hogy az iOS-végfelhasználók hogyan kapják meg az alkalmazásaikat
Szeptemberben a következő változásokra kerül sor az iOS-es Vállalati portál alkalmazás alkalmazáscsempéivel kapcsolatban annak érdekében, hogy a felhasználók valamennyi alkalmazásukat egyetlen helyen, a Vállalati portál webhelyen láthassák különböző nézetekben. Jelenleg az Apple korlátozásai tiltják az üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban; ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk.

- A **Vállalati alkalmazások** csempe jelenleg az összes alkalmazás listájára mutat a Vállalati portál webhely ÖSSZES lapján, és ez a jövőben is így marad. A csempe új neve **Minden alkalmazás**.
- Az **Egyéb alkalmazások** csempe jelenleg a Vállalati portál alkalmazás azokat az alkalmazásokat listázó nézetére mutat, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. A csempe új neve **Kiemelt alkalmazások** lesz, és rákoppintás esetén a felhasználót a Vállalati portál webhely KIEMELT lapjára irányítja.
-  A **Kategóriák** csempe jelenleg egy olyan nézetre mutat a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza. A csempe neve nem változik, azonban ezentúl a Vállalati portál webhely KATEGÓRIÁK nézetére mutat majd.
[Itt](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) talál frissített képernyőképeket.
<!---TFS 1317133--->

### Felszólítás az iOS-es Managed Browser alkalmazás telepítésére, ha az informatikai részleg beállította ezt a követelményt az alkalmazás számára
Ha az iOS-es Vállalati portál alkalmazás szeptemberi kiadásában egy webklipet úgy konfigurált, hogy csak a felügyelt böngészőben nyíljon meg, de a felügyelt böngésző nincs telepítve az eszközön, akkor az eszközön futó Vállalati portál alkalmazás felszólítja a felhasználót, hogy a webklip telepítése előtt telepítse a felügyelt böngészőt. 
<!---TFS 1228570--->

## Szolgáltatások érvénytelenítése
### A vállalati portál Windows 8 és a Windows Phone 8 rendszerhez készült alkalmazásai 2016 szeptemberétől elavulttá válnak
2016 októberétől a Microsoft Intune kivezeti a Windows 8 és Windows Phone 8 Vállalati portál alkalmazások támogatását. A Microsoft Intune egyúttal a Windows Phone 8 platform támogatását is kivezeti. Ennek következményeképpen ekkortól nem tud majd Windows Phone 8 rendszerű eszközöket regisztrálni vagy frissíteni. A már regisztrált Windows Phone 8 és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.
<!---TFS 1255391--->

### Az értesítési szabályok egyedi csoportcélzási lehetősége megszűnik
Az Intune értesítési szabályai határozzák meg, hogy kinek küld értesítő e-mailt az Intune. Jelenleg úgy is beállíthatja az értesítési szabályokat, hogy a rendszer a létrehozott Intune-eszközcsoportokhoz tartozó eszközök összes felhasználójának elküldje az e-maileket. 2016 júniusától megszűnik az egyéni csoportcélzás lehetősége.

A módosítás előzetes ütemterve a következő:
- 2016 augusztusától az új bérlők számára nem jelenik meg az Értesítési szabály létrehozása varázsló második lépése. A meglévő bérlőkre ekkor még nem lesz érvényes a változás.
- 2016 szeptemberétől kezdve egyes meglévő bérlők számára nem jelenik meg a varázsló „Eszközcsoportok kiválasztása” lépése.
- 2016 novemberétől kezdve terveink szerint már egyetlen bérlő számára sem fog megjelenni az „Eszközcsoportok kiválasztása” lépés a varázslóban.

<!---   TFS 1278864--->
### Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások
Szeptembertől iOS operációs rendszer alatt a Microsoft Intune Vállalati portál alkalmazás valamennyi felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.

<!---TFS 1283165--->


### Intune Viewer-alkalmazások
Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusában megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos Rights Management alkalmazás (RMS-megosztó alkalmazás) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. Bővebben az [RMS-megosztó alkalmazásról](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).
<!--- goes in 1608 What's New--->


### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Sep16_HO2-->



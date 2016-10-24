---
title: "Újdonságok archívuma | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## 2016. szeptember
## Új funkciók, bejelentések és információk
* [Windows feltételes hozzáférés](#windows-conditional-access)
* [iOS 10-támogatás](#ios-10-support)
* [Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integráció Android-eszközök védelméhez](#lookout-integration-to-protect-android-devices)
* [A Vállalati portál frissítései Android, iOS és Windows rendszeren](#company-portal-updates)
* [Intune-szószedet](#intune-glossary)
* [Mi várható?](#whats-coming)

## Windows feltételes hozzáférés
Mostantól feltételes hozzáférési szabályzatokat hozhat létre az Intune felügyeleti konzollal. Ezekkel megakadályozhatja, hogy a Windows rendszerű számítógépek elérjék az Exchange Online-t és a SharePoint Online-t. Olyan feltételes hozzáférési szabályzatokat is létrehozhat, amelyekkel az Office asztali és univerzális alkalmazásainak elérését gátolhatja meg.

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

## Intune-szószedet</br>
A könyvtárban elhelyeztünk egy új, a [szószedetet tartalmazó témakört](https://docs.microsoft.com/intune/understand-explore/intune-glossary), hogy segítsünk megérteni az Intune termékben használat fogalmakat.



<!--HONumber=Oct16_HO2-->



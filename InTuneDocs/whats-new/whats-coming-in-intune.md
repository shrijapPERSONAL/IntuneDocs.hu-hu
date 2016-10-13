---
title: "Előzetes kiadás | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# A Microsoft Intune várható újdonságai – október
Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. A várható újdonságokkal kapcsolatban friss hírekért látogasson vissza.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### A MAM-szabályzatokat használó felügyelt alkalmazásokból történő nyomtatás kezelése
Immár megakadályozhatja a vállalati adatok kinyomtatását a MAM-szabályzatokkal rendelkező alkalmazásokból. Ez a beállítás az [Azure-portálon](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) érhető el, és [iOS](..deployuse/ios-mam-policy-settings) [Android](..deployuse/android-mam-policy-settings) operációs rendszereket futtató eszközön egyaránt támogatott.
<!--TFS 1014328-->

### Az új Munkahelyi Microsoft Intune-portál elérhető a Windows 10-es eszközökhöz
A Microsoft új Munkahelyi Microsoft Intune-portált ad ki Windows 10-es eszközökhöz. Az új univerzális Windows 10 formátumot használó alkalmazás frissített, egységes felhasználói felületet nyújt az alkalmazáson belül és az összes Windows 10-es eszközön, számítógépen, illetve mobileszközön, miközben a jelenlegi funkcionalitása is megmarad.

Az új alkalmazással a felhasználók további platformszolgáltatásokat érhetnek majd el, mint például az egyszeri bejelentkezést (SSO) és tanúsítványalapú hitelesítést Windows 10-es eszközökön. Az alkalmazás a meglévő Windows 8.1 Vállalati portál frissítéseként lesz elérhető , amelyet a Windows Phone 8.1-es Vállalati portál telepít a Windows Áruházból.
<!--TFS 1016502-->

### Android for Work-támogatás

Az Intune immár az [Android for Work program](https://enterprise.google.com/android/partners/) része. Az Android for Work funkcióinak támogatása ebben a hónapban kezdődik.

[Olvassa el a Microsoft közleményét az Intune Android for Work-támogatásáról](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Android Samsung KNOX-kompatibilitás az Intune-nal

Egyes Samsung Galaxy Ace-modelleket az Intune nem képes Samsung KNOX-eszközként kezelni. Amikor belépteti ezeket az eszközöket Intune-ba, azok csak szabványos Android-eszközként kezelhetők.
Az alábbi modellek érintettek:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Önnek és végfelhasználóinak ezzel kapcsolatban nincs semmilyen teendője.
További információért látogasson el a [Samsung KNOX](https://www.samsungknox.com) webhelyre.

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### A Windows 8-hoz készült Vállalati portál alkalmazás elavult; a Windows Phone 8 és a Windows RT platformok támogatását kivezetjük
2016 októberétől kivezetjük a Windows 8 Vállalati portál támogatását a Microsoft Intune-ban. Egyúttal a Windows Phone 8 és Windows RT platform Microsoft Intune-beli támogatását is kivezetjük. Ennek következményeképpen nem fog tudni Windows Phone 8 vagy Windows RT rendszerű eszközöket regisztrálni vagy frissíteni.

A már regisztrált Windows Phone 8, Windows RT és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.

2016 novemberétől megszüntetjük a Windows Phone 8 Vállalati portál támogatását.
<!--TFS 1255391-->

### Feltételes hozzáférés a mobilalkalmazás-kezeléshez
Mostantól feltételes hozzáférési szabályzatokat hozhat létre, hogy letiltsa a nem felügyelt mobilalkalmazások hozzáférését az [Exchange Online-hoz](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) és a [SharePoint Online-hoz](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Zárolhatja a beépített e-mail ügyfélprogramját és azokat az alkalmazásokat, amik nem támogatják a MAM használatát az Intune App SDK-val.  Ezt feltételes hozzáférési szabályzat létrehozásával és azon alkalmazások megadásával hajtható végre, amelyek az Azure Portal használatával férnek hozzá az Exchange Online-hoz és a SharePoint Online-hoz.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Lookout-integráció iOS-eszközök védelméhez
Októbertől a Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az iOS- mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő iOS-eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást eszközükön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a vállalati adatokhoz való hozzáféréshez.
<!--TFS 1319493-->

### Intune App SDK és alkalmazásburkoló Android rendszerhez
Az Intune alkalmazásburkoló eszközével vagy az Intune App SDK-val engedélyezheti, hogy az alkalmazások Intune mobilalkalmazás-felügyeleti (MAM) szabályzatokat használjanak. Az alkalmazásburkoló és az SDK új frissítései magukba foglalják az alábbiakat:

* Az Android N támogatása
* Az Intune mobilalkalmazás-felügyeleti szabályzatainak támogatása az eszköz beléptetése nélkül
* A Xamarin-alapú Android-alkalmazások támogatása

Az Androidos alkalmazásburkoló nyilvános előzetesében kipróbálhatja a mobilalkalmazás-kezelést az eszköz beléptetése nélkül, illetve a Xamarin-támogatást: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Oct16_HO1-->



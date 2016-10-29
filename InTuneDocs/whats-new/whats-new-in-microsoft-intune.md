---
title: "Újdonságok | Microsoft Intune"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Újdonságok a Microsoft Intune-ban – 2016. október
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Újdonságok

### Feltételes hozzáférés a mobilalkalmazás-kezeléshez
Lehetősége nyílik az Exchange Online-hoz való hozzáférés korlátozására, hogy az csak az Intune mobilalkalmazás-felügyeleti szabályzatokat támogató alkalmazások, például Outlook számára legyen elérhető. [Ez az új funkció](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) kiválóan együtt használható az Intune mobilalkalmazás-felügyeleti (MAM-) szabályzataival, mivel letilthatja vele a hozzáférést a beépített e-mail-ügyfélprogramokhoz vagy más alkalmazásokhoz, amelyek nincsenek még konfigurálva Intune MAM-szabályzatokkal. Ezzel biztosítható, hogy a felhasználók csak olyan alkalmazásokkal férhessenek hozzá a vállalati adatokhoz, amelyeket az Intune MAM használatával védenek. Az Intune mobilalkalmazás-felügyelettel az Azure-portálon ismerkedhet meg. Ehhez keresse a „Beállítások” panelen az új Feltételes hozzáférés szakaszt.

### Feltételes hozzáférés Windows rendszerű számítógépeken
Mostantól feltételes hozzáférési szabályzatokat hozhat létre az Intune felügyeleti konzoljával. Ezekkel megakadályozhatja, hogy a Windows rendszerű számítógépek elérjék az [Exchange Online-t](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) és a [SharePoint Online-t](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Olyan feltételes hozzáférési szabályzatokat is létrehozhat, amelyekkel az Office asztali és univerzális alkalmazásainak elérését gátolhatja meg.

### Android for Work-támogatás
Az Intune immár az Android for Work program része. Az Android for Work funkcióinak támogatása ebben a hónapban kezdődik.
[Olvassa el a Microsoft közleményét az Intune Android for Work-támogatásáról](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

A következő Intune témakörök új, vagy az Android for Workre vonatkozó, frissített információkat tartalmaznak:

Informatikai szakemberek számára:
- [Az Android for Work beállítása](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Az Exchange Online-hoz és az új dedikált Exchange Online-hoz való e-mail hozzáférés korlátozása](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [A helyszíni Exchange-hez és az örökölt dedikált Exchange Online-hoz való e-mail-hozzáférés korlátozása](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work-alapú megfelelőségi szabályzatok beállításai](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work-alkalmazások telepítése](/intune/deploy-use/android-for-work-apps)
- [Android for Work-alkalmazások konfigurálása mobilalkalmazás-konfigurációs szabályzatok segítségével](/intune/deploy-use/afw-app-configuration-policy)
- [Az Android for Work szabályzatbeállításai](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Végfelhasználók számára:
- [Mi történik munkahelyi profil létrehozásakor](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Munkahelyi profil létrehozása és eszköz regisztrálása az Intune-ban](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Lookout-integráció iOS-eszközök védelméhez
Októbertől a Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az iOS- mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő iOS-eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást eszközükön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a vállalati adatokhoz való hozzáféréshez. Olvassa el a [Lookout for Work alkalmazások konfigurálása és telepítése](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) című témakört.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Intune-alkalmazásburkoló Android rendszerhez
Az Intune alkalmazásburkoló eszközével engedélyezheti, hogy az alkalmazások Intune-alapú mobilalkalmazás-felügyeleti (MAM-) szabályzatokat használjanak. Az Intune mobilalkalmazás-felügyeleti szabályzatai már az eszköz regisztrálása nélkül is támogatottak.

### A MAM-szabályzatokat használó felügyelt alkalmazásokból történő nyomtatás kezelése
Immár megakadályozhatja a vállalati adatok kinyomtatását a MAM-szabályzatokkal rendelkező alkalmazásokból. Ez a beállítás az [Azure-portálon](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) érhető el, és [iOS](/Intune/deploy-use/ios-mam-policy-settings) [Android](/Intune/deploy-use/android-mam-policy-settings) operációs rendszereket futtató eszközön egyaránt támogatott.
<!--TFS 1014328-->

## Értesítések

### Android Samsung KNOX-kompatibilitás az Intune-nal
Egyes Samsung Galaxy Ace-modelleket az Intune nem képes Samsung KNOX-eszközként kezelni. Amikor belépteti ezeket az eszközöket Intune-ba, azok csak szabványos Android-eszközként kezelhetők.

Az alábbi modellek érintettek:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Önnek és végfelhasználóinak ezzel kapcsolatban nincs semmilyen teendője. További információért látogasson el a [Samsung KNOX](https://www.samsungknox.com) webhelyre.

### A Windows 8-hoz készült Vállalati portál alkalmazás elavult; a Windows Phone 8 és a Windows RT platformok támogatását kivezetjük
2016 októberétől kivezetjük a Windows 8 Vállalati portál támogatását a Microsoft Intune-ban. Egyúttal a Windows Phone 8 és Windows RT platform Microsoft Intune-beli támogatását is kivezetjük. Ennek következményeképpen nem fog tudni Windows Phone 8 vagy Windows RT rendszerű eszközöket regisztrálni vagy frissíteni.

A már regisztrált Windows Phone 8, Windows RT és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.

2016 novemberétől megszüntetjük a Windows Phone 8 Vállalati portál támogatását.
<!--TFS 1255391-->

## Mi várható?

### Az új Munkahelyi Microsoft Intune-portál elérhető a Windows 10-es eszközökhöz
A Microsoft új Munkahelyi Microsoft Intune-portált ad ki Windows 10-es eszközökhöz. Az új univerzális Windows 10 formátumot használó alkalmazás frissített, egységes felhasználói felületet nyújt az alkalmazáson belül és az összes Windows 10-es eszközön, számítógépen, illetve mobileszközön, miközben a jelenlegi funkcionalitása is megmarad.

Az új alkalmazással a felhasználók további platformszolgáltatásokat érhetnek majd el, mint például az egyszeri bejelentkezést (SSO) és tanúsítványalapú hitelesítést Windows 10-es eszközökön. Az alkalmazás a meglévő Windows 8.1 Vállalati portál frissítéseként lesz elérhető , amelyet a Windows Phone 8.1-es Vállalati portál telepít a Windows Áruházból. További részletekért látogasson el az [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) oldalra.
<!--TFS 1016502-->

### További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Intune korábbi kiadásai](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->



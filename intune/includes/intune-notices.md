---
title: fájl belefoglalása
description: fájl belefoglalása
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fab8f2be48a30f6ad058b3eeb6874a44ff04e6ac
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744322"
---
Ezek a megjegyzések meg fontos információkat, amelyek segítségével előkészítése az Intune jövőbeli változtatásokat és szolgáltatásokat. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Az androidhoz készült céges portál alkalmazás frissítése a legújabb verzióra <!--4536963-->
Az Intune rendszeres időközönként frissítéseket ad ki, az Androidos vállalati portál alkalmazás. 2018. November kiadtunk egy vállalati portál frissítése, amely tartalmaz egy háttér-kapcsolót a Google módosítsa a meglévő értesítési platform, a Google Firebase Cloud Messaging (FCM) előkészítése. Ha Google kivonja a meglévő értesítési platform és a lépés a FCM, frissítette a vállalati portál alkalmazást, legalább a 2018. November a felhasználóknak kell teljes kiadási folytatja, a Google play áruházban való kommunikáció során.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A telemetriai adatok azt jelzi, hogy az eszközt a vállalati portál verziónál régebbi verziójú 5.0.4269.0. Ha ez a verzió vagy újabb, a vállalati portál alkalmazás nincs telepítve, IT pro kezdeményezett eszközök műveletei, például törlés, jelszó alaphelyzetbe állítása szükséges és elérhető alkalmazást telepít és tanúsítványigénylés nem működnek megfelelően. Ha az eszközök MDM-regisztrálása az Intune-ban, majd megjelenik a céges portál-verzió és a felhasználók a ügyfélalkalmazások – detektált alkalmazások. Korábbi verziók a céges portál kiválasztása lehetővé teszi, hogy mely felhasználók helyezte-e az eszközöket, amelyek nem frissítette a céges portál.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Kérje meg a végfelhasználók számára az Android-eszközök, amelyek még nem frissített frissíteni a vállalati portálon keresztül a Google play. Tájékoztassa a segélyszolgálatot, abban az esetben, ha a felhasználó nem tartott automatikus frissítése, a vállalati portál alkalmazást. További információ található további a Google FCM platform hivatkozásra, és módosítsa.

#### <a name="additional-information"></a>További információ
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Az Intune-bA érkező új nA celou obrazovku – felhasználói élmény <!--4593669-->
Bevezetjük frissített létrehozásához és szerkesztéséhez a felhasználói felületi élmény az Intune-bA az Azure Portalon. Az új felületet egy varázsló stílus formátumban, egy panelen sűrített leegyszerűsíti a meglévő munkafolyamatokba. Ez a frissítés azonnal mindenre "panel bővítéseket", vagy minden létrehozási, és a folyamatok, amelyek megkövetelik a részletes panel Journey részleteinek szerkesztése. A létrehozás munkafolyamatok hozzárendelések tartalmazza (kivéve az alkalmazás-hozzárendelés) is frissülni fog.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A teljes képernyős élmény fog történni az Intune-hoz is portal.azure.com és devicemanagement.microsoft.com a következő néhány hónapban. Ez a frissítés felhasználói felületén nem érinti a meglévő szabályzatokat és a profilok, de egy kis mértékben módosított munkafolyamatot láthatja. Új szabályzatokat hozhat létre, ha például Ön lesz állíthat be néhány hozzárendelés helyett ezzel a házirend létrehozása után ez a folyamat részeként. Tekintse meg a következő blogbejegyzést: további információk a képernyőképek, az új felület fog kinézni a konzolon.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Nem kell semmit sem, de az is, fontolja meg az IT pro útmutatást frissítése, ha szükséges. Dokumentációnkat frissítjük, ahogy ez a tapasztalat bevezeti a különböző paneleket az Intune-ban az Azure Portalon.

#### <a name="additional-information"></a>További információ 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Tervezett módosítás: Az Intune támogatja az iOS 11 vagy újabb szeptembertől áthelyezése <!-- 4665342-->
Szeptembertől iOS az Apple kell megjelenteti 13 várhatóan. Az Intune-regisztrációt, a céges portál és a Managed Browser támogatja az iOS 11 vagy újabb, az IOS-es 13 kiadás után rövid idővel áthelyezi.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Feltéve, hogy az Office 365 mobilalkalmazások iOS 11.0-s és újabb rendszeren támogatott, ez hatással lehet a nem Ön; már valószínűleg már telepítette az operációs rendszer vagy eszköz. Azonban az alábbi eszközök egyikét sem, vagy úgy dönt, hogy regisztrálják az alább felsorolt eszközöket, ha tudja, hogy az alábbi eszközök nem támogatják az operációs rendszer iOS 10-nél nagyobb. Ezek az eszközök kell frissíteni, hogy egy eszköz, amely támogatja az iOS 11 vagy újabb verziója:

- iPhone 5
- iPhone 5c
- iPad (4. generáció)

Július kezdődően az MDM-ben regisztrált eszközökön az iOS 10-es és a vállalati portál rendszer felkéri, hogy az operációs rendszer vagy eszköz frissítése. Alkalmazás alkalmazásvédelmi szabályzatokat (alkalmazás) használatakor a "Megkövetelése (csak figyelmeztetési) minimális iOS operációs rendszer" hozzáférési beállítás is beállíthat.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ellenőrizze az Intune, tekintse meg a felhasználók vagy eszközök milyen hatással lehet a jelentéskészítés. Lépjen a **eszközök** > **minden eszköz** operációs rendszer alatt. Meghatározásához, hogy a vállalatnál ki van-e az iOS 10-es eszközök további oszlopokat is hozzáadhat. A kérés, hogy a végfelhasználók számára az eszközök frissítése egy operációs rendszer támogatott verziója szeptember előtt.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Tervezett módosítás: 8.1.1-es verzió támogatása és az iOS-hez készült Intune App SDK újabb <!-- 3586942-->
Szeptember 2019 az Intune fogja át támogatásához az iOS-alkalmazások az Intune App SDK-val 8.1.1-es és újabb verzióit. Kisebb, mint 8.1.1-es SDK-verziókra létrehozott alkalmazások többé nem lesz támogatott. Ez a változás lépnek életbe várhatóan származnak, körül. szeptember 13 iOS az Apple kiadásával és szintén bejelentettük a MC181399.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Az Intune App SDK-val vagy az App Wrapping-integrációnak köszönhetően a vállalati adatok védelme is a jóvá nem hagyott alkalmazások és adatok titkosítása felhasználókat. Az Intune App SDK IOS rendszerhez készült fogja használni 256 bites titkosítási kulcsok alapértelmezés szerint, ha a titkosítás engedélyezve van az Intune App Protection házirendek (alkalmazás). A módosítás után bármely SDK korábbi verziók 8.1.1-es, amely 128 bites titkosítási kulcsok használatához az iOS-alkalmazások többé nem lesz képes alkalmazások 8.1.1-es SDK-val integrált vagy 256 bites kulcsokkal megoszthatják az adatokat. Minden iOS-alkalmazás-SDK verziója 8.1.1-es rendelkeznie kell, vagy magasabb, hogy védett adatok megosztásához.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ellenőrizze a Microsoft, külső és az üzletági (LOB) alkalmazások. Győződjön meg arról, hogy az alkalmazások védelme az Intune APP SDK 8.1.1-es verziót használ, vagy később.

- A LOB-alkalmazások: Szükség lehet való ismételt közzétételéhez az alkalmazások integrálva van az SDK-verzió 8.1.1-es vagy újabb verziója. Azt javasoljuk, hogy az SDK legújabb verzióját. A témakörben találhat további információt az útmutató az ÜZLETÁGI alkalmazások előkészítése alkalmazásvédelmi szabályzatokkal, lásd: [– üzletági alkalmazások előkészítése alkalmazásvédelmi szabályzatok](../apps-prepare-mobile-application-management.md).
- A Microsoft és külső alkalmazások: Győződjön meg arról, hogy ezek az alkalmazások legújabb verzióját a felhasználók számára telepít.

Ha van ilyen, a módosítás tartalmazza az SDK támogatást, is frissítenie kell a dokumentációban vagy a fejlesztői útmutató.

#### <a name="additional-information"></a>További információ
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

---
title: fájl belefoglalása
description: fájl belefoglalása
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: c4a17abdb518daba30fbdf339090f7e24c8c26d5
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412154"
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

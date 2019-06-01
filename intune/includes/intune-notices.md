---
title: fájl belefoglalása
description: fájl belefoglalása
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 1073a38da8a5b2467b1ff8c97b32b93f92e34e4c
ms.sourcegitcommit: f90cba0b2c2672ea733052269bcc372a80772945
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66454117"
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

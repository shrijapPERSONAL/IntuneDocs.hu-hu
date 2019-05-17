---
title: fájl belefoglalása
description: fájl belefoglalása
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732605"
---
Ezek a megjegyzések meg fontos információkat, amelyek segítségével előkészítése az Intune jövőbeli változtatásokat és szolgáltatásokat. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>A vállalati iOS-eszközök beállítási Asszisztenssel való hitelesítés közben az Intune vállalati portálon a regisztrációs folyamat módosítása <!-- 1927359 -->
Az iOS-eszközök Apple vállalati tulajdonú eszközök regisztrálási módszerei – az Apple Configurator, Apple üzleti vezető, az Apple School Manager vagy az Apple eszköz beléptetési Program (DEP) keresztül munkafolyamata egy közelgő változásokat használata esetén a telepítő Segéd a hitelesítéshez. Ez a változás csak a felhasználói affinitással rendelkező regisztrált eszközökre vonatkozik.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ez a változás bevezetési, amikor regisztrációs profilokat az Intune-ban az Azure Portalon, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást fog frissülni. Továbbfejlesztett munkafolyamatot az iOS-eszközök regisztrálása a fenti módszerek keresztül lesz. 

- Amikor új eszközök regisztrációja és hitelesítése a beállítási asszisztens, képes lesz-e automatikusan telepíthető a vállalati portál alkalmazás kiválasztása. A végfelhasználók már nem jelenik meg a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban.  
- A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök lépéseket kell tennie, ha azt szeretné, a feltételes hozzáférés engedélyezéséhez. Kell [alkalmazáskonfigurációs szabályzat konfigurálása](https://aka.ms/enrollment_setup_assistant) az egy adott xml leküldéses le ezeket az eszközöket a vállalati portálon.  Ha elküldi a vállalati portál ezen a módon kikapcsolja, végfelhasználók számára már nem jelennek meg, a "Az eszköz azonosítása" képernyő és a "Az eszköz megerősítése" képernyő a regisztráció folyamatban. 
- Után ez a változás az egyik tagján jelennek meg, ha még nem telepítette a vállalati portál alkalmazás konfigurációs profil a fent említett, és ha a vállalati portál alkalmazást az App Store áruházból, figyelemmel felhasználóknak a bejelentkezéshez, a végfelhasználók letöltése, de fog hibaüzenetet kap. Nem tudják használni az alkalmazást a feltételes hozzáférés. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha a módosított munkafolyamat használatát tervezi, szeretné frissíteni a végfelhasználói útmutatót, amely szerint:

- Végfelhasználók számára már nem jelennek meg a fent említett a regisztrációs folyamat két képernyő. 
- Jelentkezzen be a vállalati portálon, hogy telepítésekor automatikusan, és ne töltse le az app store lesz szükséges. 

Ha szeretné, hozzon létre egy alkalmazáskonfigurálási szabályzat most szükség esetén ez a változás előkészítéséhez. Amikor az új munkafolyamatot vezet be, látni fogja a frissített beléptetési profilok a konzolon. Azt fogjuk is értesíti a felhasználókat a Bevezetés az üzenet központon keresztül. Ezt követően kell, hogy a végfelhasználók beléptethetik az DEP Programon keresztül és a beállítási Asszisztenssel hitelesítéséhez és a feltételes hozzáférés is használhatja a vállalati portál, hajtsa végre a műveletet.

#### <a name="additional-information"></a>További információ 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Az androidhoz készült céges portál alkalmazás frissítése a legújabb verzióra <!--4536963-->
Az Intune rendszeres időközönként frissítéseket ad ki, az Androidos vállalati portál alkalmazás. 2018. November kiadtunk egy vállalati portál frissítése, amely tartalmaz egy háttér-kapcsolót a Google módosítsa a meglévő értesítési platform, a Google Firebase Cloud Messaging (FCM) előkészítése. Ha Google kivonja a meglévő értesítési platform és a lépés a FCM, frissítette a vállalati portál alkalmazást, legalább a 2018. November a felhasználóknak kell teljes kiadási folytatja, a Google play áruházban való kommunikáció során.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
A telemetriai adatok azt jelzi, hogy az eszközt a vállalati portál verziónál régebbi verziójú 5.0.4269.0. Ha ez a verzió vagy újabb, a vállalati portál alkalmazás nincs telepítve, IT pro kezdeményezett eszközök műveletei, például törlés, jelszó alaphelyzetbe állítása szükséges és elérhető alkalmazást telepít és tanúsítványigénylés nem működnek megfelelően. Ha az eszközök MDM-regisztrálása az Intune-ban, majd megjelenik a céges portál-verzió és a felhasználók a ügyfélalkalmazások – detektált alkalmazások. Korábbi verziók a céges portál kiválasztása lehetővé teszi, hogy mely felhasználók helyezte-e az eszközöket, amelyek nem frissítette a céges portál.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Kérje meg a végfelhasználók számára az Android-eszközök, amelyek még nem frissített frissíteni a vállalati portálon keresztül a Google play. Tájékoztassa a segélyszolgálatot, abban az esetben, ha a felhasználó nem tartott automatikus frissítése, a vállalati portál alkalmazást. További információ található további a Google FCM platform hivatkozásra, és módosítsa.

#### <a name="additional-information"></a>További információ
https://firebase.google.com/docs/cloud-messaging/
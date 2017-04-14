---
title: "A végfelhasználók felkészítése a Microsoft Intune használatára | Microsoft Intune"
description: "Tájékoztassa a végfelhasználókat, hogy sikeres legyen az Intune bevezetése."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 48914533-f138-4dc0-8b93-4cea3ac61f7b
ms.reviewer: robstack
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bed28fc91271c12377f45662aa00fc9616d16fe8
ms.openlocfilehash: 3d3f35f38a4d6f09f8fdc3e1bbc1c6ca5af6bbe7
ms.lasthandoff: 04/11/2017


---

# <a name="how-to-educate-your-end-users-about-microsoft-intune"></a>A végfelhasználók felkészítése a Microsoft Intune használatára

A Microsoft Intune segít a munkatársak mobileszközökkel való ellátásában, miközben gondoskodik a vállalati adatok védelméről. A rendszer sikeres bevezetése több lépésből áll, beleértve az Intune [ingyenes próbaverzión keresztüli](/Intune/Understand/mobile-device-management-trial-guide-microsoft-intune.md) kiértékelését, [az e-mailek védelmét](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices), valamint az [alkalmazások beágyazását az Intune SDK segítségével](/intune/develop/intune-app-sdk.md).

Azonban semmilyen technológia nem garantálja azt, hogy a felhasználók fel is ismerik az eszközfelügyelet fontosságát. Sőt, számos végfelhasználó gondolhatja úgy, hogy Ön hozzáfér a személyes adataikhoz – különösen ha az Intune bevezetése [saját eszközök használatával](/enterprise-mobility-security/solutions/byod-design-considerations-guide.md) történik.

> [!Important]
> A végfelhasználók vállalati eszközfelügyelettel kapcsolatos kétségeinek megismerése és ezek proaktív kezelése a rendszer sikeres bevezetésének kritikus fontosságú része.

A bevezetés nem csak a technológia beüzemeléséről és az eszközök szétosztásáról szól, hanem a megfelelő tájékoztatásról is, mivel a végfelhasználók csak így értékelhetik igazán az Intune által nyújtott biztonságos hozzáférést. A felhasználók idegenkedhetnek a nagyvállalati mobilitástól, ha nem magyarázza el számukra, hogy a rendszer pontosan mire jó, illetve mire képes (vagy nem képes).

## <a name="things-to-consider-about-your-end-users"></a>Amire érdemes figyelni a végfelhasználókkal kapcsolatban

__Milyen szintű tapasztalattal rendelkeznek a végfelhasználók?__ A végfelhasználók a különböző technológiák használata során különböző tapasztalatokra tesznek szert. Ezek a tapasztalatok lehetnek pozitívak (például olyan emlékezetes fényképek, amelyeket a végfelhasználó készített a gyermekeiről) vagy lehetnek negatívak (például amikor a végfelhasználó beleejti a mobilkészülékét a lefolyóba, és minden olyan adatot elveszít róla, amelyről nincs biztonsági mentés). Az ilyen tapasztalatok határozzák meg azt, hogy a végfelhasználók miként viszonyulnak a technológiához, és mit gondolnak az eszközök személyes és üzleti célú felhasználásáról.

__Mit jelent számomra a mobileszköz-kezelés?__ Elképzelhető, hogy a felhasználók nincsenek teljesen tisztában azzal, hogy Ön milyen hozzáféréssel rendelkezik (vagy nem rendelkezik) a felhasználók eszközeihez és adataihoz. A felhasználókat aggaszthatja, hogy az informatikai osztály és a vezetőség esetlegesen nyomon követi minden lépésüket. Ez különösen azokat a kevésbé tapasztalt felhasználókat zavarhatja, akik úgy vélik, hogy az eszközeiken végzett minden tevékenység személyes jellegű. A tapasztaltabb felhasználók konkrét félelmei pedig olyan feltételezésekből származhatnak, amely szerint a Nagy Testvér figyeli őket az eszközeiken, és még az is előfordulhat, hogy a felhasználók terjesztik ezeket a nézeteiket a munkatársak körében.

__Milyen kényelmetlenségek érhetik a végfelhasználókat?__ Az alkalmazások telepítése, az eszközök regisztrálása, valamint a megfelelőség biztosítása időigényes feladat. Az Intune kiemelt prioritása a vállalati adatok biztonságának garantálása, de egy PIN-kód használatának indokolatlan megkövetelése feldühítheti a felhasználókat a személyes eszközeik vállalati felügyeletével kapcsolatban. Ha kötelező alkalmazásfrissítéseket küld egy üzleti szempontból fontos konferenciahívás közepén, csökkentheti a felhasználók termelékenységét. Ez pedig épp ellenkezője annak, amiért eredetileg ellátta őket mobileszközökkel.

## <a name="things-you-should-do"></a>Tennivalók

Ha eloszlatja a felhasználók aggodalmait, a rendszer bevezetése simább lehet. Az alábbi listában több olyan módszert talál, amelyekkel elősegítheti az eszközfelügyelet végfelhasználói elfogadását.

* __Legyen segítőkész.__ Az Intune dokumentációja különböző tartalmakkal segíti a végfelhasználókat a feladataik végrehajtásában, ideértve például az eszközök regisztrációját vagy a hibaelhárítást. A tartalmak között találhatók olyan cikkek, amelyeket a rendszer a Céges portálról küld a felhasználóknak. A cikkek különböző szakaszokra oszlanak: a Céges portál alkalmazás telepítése és az Intune-regisztráció; a felhasználók által az eszközökön végrehajtható általános műveletek, valamint a hibaelhárítás. A dokumentáció a [Felügyelt eszközök használata a munkavégzéshez](/Intune/EndUser/use-managed-devices-to-get-work-done) című témakörben található.

* __Legyen elérhető.__ A végfelhasználóknak tudniuk kell, hogy hol kérhetnek segítséget az eszközeikkel kapcsolatban. Ne felejtse el megadni a rendszergazda kapcsolattartási adatait a [Vállalati portál testreszabásakor](/Intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-7), hogy a felhasználók szükség esetén tudjanak segítséget kérni.

* __Legyen személyes.__ A bevezetett rendszer szempontjából nem elég konkrét útmutatók azt éreztethetik a felhasználókkal, hogy Ön nem veszi figyelembe a felhasználók tapasztalatait. Ezzel a [rendszergazdáknak készült, testreszabható, végfelhasználói Intune-regisztrációs sablonnal](https://gallery.technet.microsoft.com/office/Intune-End-User-Enrollment-3a0c9b0c) saját regisztrációs útmutatót készíthet a végfelhasználóknak.

* __Keresse a különböző kommunikációs lehetőségeket.__ A [különböző tanulási stílusokhoz](http://www.umassd.edu/dss/resources/facultystaff/howtoteachandaccommodate/howtoaccommodatedifferentlearningstyles/) hasonlóan a felhasználók különböző módon fogyasztanak információkat. Azoknak a felhasználóknak, akik a szövegalapú dokumentációk helyett inkább a videókat kedvelik, [különböző eszköztípusok regisztrációjához készült videotartalmakat](https://channel9.msdn.com/Series/IntuneEnrollment) és sok minden mást kínálunk a 9-es csatornán. A videókat közvetlenül be lehet ágyazni saját [SharePoint-webhelyekre](https://support.office.com/article/Embed-a-video-from-Office-365-Video-59e19984-c34e-4be8-889b-f6fa93910581), vagy le lehet tölteni őket helyi példányként – akár csak hanggal vagy képpel.

* __Legyen figyelmes.__ A végfelhasználói tapasztalatok hatással vannak a termelékenységre, ezért ezek megértése egyszerűsíti az aktuálisan felmerülő problémák megoldását. Ha tisztában van azzal, hogy a végfelhasználók miként töltenek le alkalmazásokat, egyszerűbbé teheti a felhasználók által tapasztalt problémák diagnosztizálását, és elősegítheti a problémák gyorsabb megoldását.

* **Android**
  * [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/Intune/EndUser/using-your-android-device-with-intune)
  * [Android-felhasználói alkalmazások letöltése](how-your-android-users-get-their-apps.md)

* **iOS**
  * [iOS-eszköz használata az Intune-nal](https://docs.microsoft.com/Intune/EndUser/using-your-ios-device-with-intune)
  * [iOS-felhasználói alkalmazások letöltése](how-your-ios-users-get-their-apps.md)

* **Windows**
  * [Windows-eszköz használata az Intune-nal](https://docs.microsoft.com/Intune/EndUser/using-your-windows-device-with-intune)
  * [Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)

* __Legyen előrelátó.__ Egyértelműen mondja el a felhasználóknak, hogy pontosan milyen adatokat felügyel az eszközeiken. Mondja el nekik, hogy milyen típusú adatokat gyűjt, és miért gyűjti azokat. Tájékoztassa őket arról, hogy miként tervezi az eszközadatok felhasználását. [A Microsoft hisz abban, hogy felhasználóknak joga van a lehető legrészletesebben megismerni az ügyféladatok felhőben történő kezelésének módját](https://www.microsoft.com/trustcenter/about/transparency), és hiszünk abban, hogy ez a filozófia jelentősen növelheti a végfelhasználók Intune-nal való elégedettségét.

>[!Note]
> Amikor csak lehetséges, az átláthatóság központi elemét képezi a rendszer sikeres bevezetésének.

A bizalomnak és a gondosan megfogalmazott megfelelőségi szabályzatoknak köszönhetően a végfelhasználók tisztában lehetnek azzal, hogy bár Ön *képes* betekinteni bizonyos személyes adatokba, ez *nincsen szándékában*, és vállalja a felelősséget a felhasználók személyes adatainak megsértéséért. Ha a jogi és a HR-részleggel közösen fogalmaz meg egy nyilatkozatot, a különösen nehezen kezelhető alkalmazottak aggodalmait is eloszlathatja.


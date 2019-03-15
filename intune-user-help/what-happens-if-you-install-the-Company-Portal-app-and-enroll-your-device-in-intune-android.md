---
title: Mi történik az Androidos Céges portál alkalmazás telepítésekor?
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d22f5aea-7be4-419b-b51b-a522ca037b69
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d8af8b01de3b9782f487e29a9f993ceaf32aac6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "55838155"
---
# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-android-device-in-intune"></a>Mi történik a Vállalati portál alkalmazás telepítésekor és az Android-eszköz Intune-beli regisztrálásakor?

Ha a szervezetében kötelező telepítenie az Intune Céges portál alkalmazást Android-eszközén, megfordulhat a fejében a kérdés, hogy miért. Ez a cikk az alkalmazás&mdash;célját és funkcióit ismerteti, valamint azt, hogy hogyan védi meg az eszközzel elért és azon tárolt munkahelyi és iskolai adatokat.

## <a name="gets-your-device-managed"></a>Eszköz felügyelet alá vonása
A Céges portál alkalmazással felügyelet alá vonhatja eszközét (más szóval *regisztrálhatja*) a szervezet eszközkezelési rendszerében. Mielőtt a szervezeti hálózatoz csatlakozik, az iskolája vagy munkahelye meggyőződik arról, hogy Ön biztonságos és megbízható eszközzel rendelkezik. Munkahelyi vagy iskolai erőforrások eléréséhez az eszköznek a szervezet eszközökre vonatkozó szabályzatait kell követnie. 

Ezeket a szabályzatokat a cége ügyfélszolgálata vagy informatikai rendszergazdája konfigurálja a céges szintű eszközkezelési rendszerben. Az eszköz regisztrálása után Ön is megkapja ezeket a szabályzatokat. 

Példák a szervezet által megkövetelhető szabályzatokra:
* Jelszó vagy PIN-kód beállítása
* Hozzáférés korlátozása adott számú bejelentkezési kísérlet után
* Jailbreakelt vagy rootolt eszköz használatának kizárása
* A munkahelyen kötelező alkalmazások telepítése

A Céges portál alkalmazás a regisztráció minden lépésén végigkíséri Önt, az eszköz beállításait pedig a szervezet követelményei szerint konfigurálja. Bizonyos esetekben az alkalmazás módosításokat kérhet Öntől.

## <a name="gives-you-access-to-work-and-school-apps-work-files-and-email"></a>Hozzáférést nyújt munkahelyi és iskolai alkalmazásaihoz, fájljaihoz és levelezéséhez
A regisztráció során a Céges portál alkalmazás megköveteli a munkahelyi vagy iskolai fiókhoz való csatlakozást. A hitelesítés után hozzáférhet munkahelyi levelezéséhez, valamint a szervezete hálózatához, fájljaihoz és alkalmazásaihoz. 

Egyes szervezetek munkahelyi vagy biztonsági alkalmazások – például a Microsoft Office vagy a Mobile Threat Defense – telepítését követelhetik meg. Ha ezek az alkalmazások kötelezőek vagy elérhetővé tették őket Önnek, a Céges portál alkalmazásban találhatja meg őket.

## <a name="lets-you-remotely-reset-a-lost-or-stolen-device-if-device-supports-it"></a>Távolról alaphelyzetbe állíthatja elveszett vagy ellopott eszközét (ha az eszköz ezt támogatja)
Ha az eszköz elveszett vagy ellopták, a Céges portál alkalmazásba vagy annak webhelyére egy másik eszközről bejelentkezve visszaállíthatja a telefont a gyári beállításokra. Ez a funkció jól jöhet, ha az eszköz olyan jogvédett munkahelyi adatokat tartalmaz, amelyeket nem szeretne mások számára elérhetővé tenni. Mivel az eszköz regisztrálva van felügyeletre, a céges ügyfélszolgálat vagy rendszergazda is segíthet alaphelyzetbe állítani.  

## <a name="notifies-you-of-policy-updates-and-requirements"></a>Értesítést küld a szabályzatfrissítésekről és a követelményekről
A Céges portál alkalmazás nyolcóránként szinkronizál a szervezet mobileszköz-kezelési szolgáltatójával. Ha gyakoribb szinkronizálást szeretne, Ön vagy a cége manuális frissítést kezdeményezhet. A szinkronizálás során az alkalmazás a következőket végzi el:  
* A cég informatikai támogatási szolgálata által elérhetővé tett szabályzatok és alkalmazásfrissítések letöltése.  
* A hardverleltár változásainak elküldése. Ezek a frissítések nem tartalmaznak személyes adatokat.  
* A vállalati alkalmazások leltárában bekövetkezett változások elküldése. Ezek a frissítések nem tartalmaznak személyes adatokat.  

Ha az eszköz nincs a szervezeti követelményeknek megfelelően szinkronizálva, a Céges portál erről értesíti Önt. Az alkalmazás tájékoztatást küld a problémáról, és megjeleníti a javításhoz szükséges lépéseket. Amíg az eszköz nem felel meg újra a követelményeknek, megvonható az Ön munkahelyi vagy iskolai erőforrásokhoz való hozzáférése. A Céges portál alkalmazásban ezt az állapotot *nem megfelelőnek* nevezzük. 

## <a name="permits-company-support-access-to-your-device"></a>Lehetővé teszi a céges ügyfélszolgálat hozzáférését az eszközhöz
Ha regisztrálja az eszközt a Céges portál alkalmazásban, a céges ügyfélszolgálat vagy informatikai rendszergazda hozzáférést kap az eszközhöz néhány korlátozott, ám fontos okból. Ezek a következők:  

* Az eszköz visszaállítása a gyári beállításokra. A fent említetteknek megfelelően Ön is alaphelyzetbe állíthatja az eszközt. Azonban ha nem fér hozzá a Céges portál alkalmazáshoz, ezt a cége is megteheti.  

* Az összes céges adat eltávolítása. A szervezete eltávolíthat céges adatokat az eszközről, ha Ön elhagyja a céget vagy az eszköz kezelése megszűnik. A személyes adatai és beállításai továbbra is megmaradnak.  

* Követelményeket határozhat meg az eszközön, például a jelszó vagy PIN-kód használatát. Ebben az esetben alkalmazáson belüli értesítést kap arról, ha az eszköz nem megfelelő. A cég támogatási szolgálata korlátozhatja, hogy hányszor lehet helytelen jelszót megadni az eszközön. Túl sok sikertelen kísérlet után az eszközt lezárhatják.  

* Ehhez el kell fogadnia a használati feltételeket.  

* A kamera letiltása. A szabályzat célja, hogy meggátolja a jogvédett adatok fotózását, valamint kevesebb figyelemelterelő funkciót nyújtson iskolai környezetekben. Az iskolák letilthatják a kamerákat a tantermi eszközökön, a tanulók így nem oszthatnak meg egymással vizsgaanyagokat.  

* Az eszközön található adatok titkosításának megkövetelése. Ez a szabályzat hozzájárul az adatok védelméhez az eszköz elvesztésekor és ellopásakor. Emellett az eszközökkel vagy alkalmazásokkal megosztott adatok számára is védelmet nyújt.  

Segítség Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble installing the Company Portal app on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.

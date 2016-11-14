---
experiment_id: kgremban_images_080416
title: "A Microsoft Intune bemutatása | Microsoft Intune"
description: "Ismerkedjen meg az Intune-nal, a nagyvállalati mobilitási és biztonsági megoldás mobileszköz-kezelési összetevőjével."
keywords: 
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 11e471cb71a14056433e756938bc202dae08416f


---

# Az Intune bemutatása
A Microsoft Intune a Microsoft Enterprise Mobility + Security (EMS, korábban Nagyvállalati mobilitási csomag) „felügyeleti ága”. A nagyvállalati mobilitás lényege, hogy az alkalmazottak minden eszközükön hatékonyan dolgozhatnak, miközben a szervezeti adatok védelme is biztosított.  

Az EMS a nagyvállalati mobilitás teljes, integrált csomagja, amelynek részét alkotják az irodai alkalmazások, az identitáskezelés, a hozzáférés-vezérlés, a felügyelet és az adatvédelem. Hatékony módot biztosít egy mobilitási megoldás üzembe helyezéséhez és üzemeltetéséhez a szervezetében.  

Az Intune segítségével felügyelheti a mobileszközeit és a mobilalkalmazásait. Az identitáskezelés és a hozzáférés-vezérlés tekintetében az Intune szorosan együttműködik az Azure Active Directoryval (Azure AD), valamint adatvédelmi téren az Azure Rights Managementtel.  

Néhány, az Intune segítségével megoldható általános üzleti probléma:

* A meglévő helyszíni e-mail- és együttműködési infrastruktúra védelmének biztosítása úgy, hogy a rendszer az interneten keresztül elérhető legyen a mobileszközök és az alkalmazások számára.
* A meglévő Office 365-infrastruktúra védelmének biztosítása úgy, hogy a rendszer az interneten keresztül elérhető legyen a mobileszközök és az alkalmazások számára.
* Annak lehetővé tétele, hogy a szervezet mobiltelefonokkal láthassa el az alkalmazottait.
* Annak lehetővé tétele, hogy a szervezet korlátozottan alkalmazható „megosztott eszközöket” biztosíthasson az adminisztratív munkatársak számára.
* Annak lehetővé tétele, hogy a szervezet biztonságos stratégiát vezessen be a „saját eszközök használatára” (BYOD) a személyes eszközökre vonatkozóan.
* Annak lehetővé tétele, hogy a szervezet megteremtse az alkalmazottak számára az Office 365 olyan eszközökkel és alkalmazásokkal történő elérésének feltételeit, amelyek nem állnak a vállalat ellenőrzése alatt, például egy szakvásár előcsarnokában elhelyezett kioszkkal.

![A nagyvállalati mobilitást átfogóan bemutató kép](..\media\em-vision.png)

Néhány Intune által ajánlott elsődleges eszköz:
* **Mobileszköz-felügyeleti (MDM)**: Lehetőség az eszközöknek az Intune-ban történő regisztrálására, így az adott eszközök kiépíthetők, konfigurálhatók, megfigyelhetők, illetve műveletek is végezhetők rajtuk, például törölhető a tartalmuk.
* **Mobilalkalmazás-kezelés (MAM)**: Lehetőség a felhasználók mobilalkalmazásainak közzétételére, leküldésére, konfigurálására, védelmére, figyelésére és frissítésére.
* **Mobilalkalmazás-biztonság**: A mobilalkalmazások felügyeletének részeként a személyes adatoknak a vállalati adatokról történő leválasztásának és a vállalati adatok szelektív törlésének lehetőségével támogatja a mobiladatok védelmét.

Ezek az eszközök különböző kombinációkban használhatók az elterjedt üzleti forgatókönyvek megvalósításához. Például a megosztott eszközzel kapcsolatos helyzetek erősen támaszkodnak az MDM használatára. A BYOD-helyzetek általában a MAM használatára támaszkodnak. A vállalati telefonos helyzetek pedig mindkettőre építenek. Szinte minden helyzet támaszkodik a mobilalkalmazás-biztonságra.

Ebben a dokumentációban elmagyarázzuk, hogy az Intune által biztosított eszközök hogyan használhatók az üzleti helyzetek feltételeinek megteremtésére.  Azt is ismertetjük, hogy ezek az eszközök hogyan használhatók az Office 365-tel, az Azure AD-vel, az Azure RMS-sel és a Microsoft mobilitási csomag többi részével. Általános áttekintést nyújtunk a technológia legelterjedtebb alkalmazásairól és lehetséges kedvező hatásairól az Ön környezetében, valamint a megvalósításához szükséges eljárásokról. Maga a technológia rugalmas, és alkalmazható az itt leírtakon kívüli bármilyen típusú forgatókönyvben is.

### További lépések
* Tájékozódjon az [Intune gyakori használati módjairól](common-ways-to-use-intune.md).
* Ismerkedjen meg a termékkel egy [30 napos Intune-próbaverzió](get-started-with-a-30-day-trial-of-microsoft-intune.md) révén.
* Mélyedjen el az Intune [műszaki követelményeiben és képességeiben](/intune/get-started/what-to-know-before-you-start-microsoft-intune).



<!--HONumber=Oct16_HO4-->



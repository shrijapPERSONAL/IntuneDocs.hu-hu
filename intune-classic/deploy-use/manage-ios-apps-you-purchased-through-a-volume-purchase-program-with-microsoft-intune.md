---
title: "Mennyiségi programban vásárolt iOS-alkalmazások felügyelete | Microsoft Docs"
description: "Az Intune segít az Apple-től mennyiségi program keretében vásárolt alkalmazások felügyeletében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt használjon, mint amennyit vásárolt."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c05c9cb1a0de468f1a6663a7870631af159d9b04
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az iOS App Store áruháza lehetővé teszi, hogy több licencet is vásároljon a vállalatnál használni kívánt alkalmazásokhoz. Ezzel a megoldással csökkenthetők az alkalmazások különböző megvásárolt példányainak nyilvántartásával járó adminisztratív terhek.

A Microsoft Intune segít az e program keretében vásárolt alkalmazások felügyeletében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt használjon, mint amennyit vásárolt.

> [!Important]
> Az iOS Volume Purchase Program for Business (VPP) programon keresztül vásárolt alkalmazások licenceit az Intune jelenleg a felhasználókhoz, és nem az eszközökhöz rendeli. Emiatt az alkalmazás telepítéséhez a végfelhasználóknak meg kell adniuk Apple ID azonosítójukhoz tartozó jelszavukat.
> Az Apple Volume Purchase Program for Education ebben a kiadásban nem támogatott.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Nagy mennyiségben vásárolt alkalmazások felügyelete iOS-eszközökön
Az [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) programon keresztül egyszerre több licencet vásárolhat az iOS-alkalmazásokhoz. Ehhez Apple VPP-fiókot kell beállítani az Apple webhelyén, és az Apple VPP-tokent fel kell tölteni az Intune-ba.  Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

## <a name="before-you-start"></a>Előkészületek
Mielőtt hozzálát, be kell szereznie a VPP-tokent az Apple-től, és fel kell töltenie azt az Intune-fiókjába. Ezenkívül tisztában kell lennie a következőkkel:

* Az Intune legfeljebb 256 VPP-token hozzáadását támogatja.
* Ha korábban VPP-tokent használt egy másik termékkel, egy újat kell létrehoznia az Intune használatához.
* A tokenek egy évig érvényesek.
* Alapértelmezés szerint az Intune naponta kétszer szinkronizál az Apple VPP szolgáltatással. Manuális szinkronizálás bármikor kezdeményezhető.
* Miután a VPP-tokent az Intune-ba importálta, ne importálja ugyanezt a tokent egy másik eszközfelügyeleti megoldásba. Ez a licenc-hozzárendelések és a felhasználói rekordok elvesztését eredményezheti.
* Mielőtt az iOS VPP-t az Intune-nal kezdené használni, távolítsa el a más mobileszköz-felügyeleti (MDM) megoldás használatával létrehozott összes meglévő VPP-felhasználói fiókot. Az Intune biztonsági okokból nem szinkronizálja ezeket a felhasználói fiókokat az Intune-ba. Az Intune csak az Intune által létrehozott adatokat szinkronizálja Apple VPP szolgáltatásból.
* Csak akkor telepíthet iOS VPP-alkalmazásokat a felhasználók olyan eszközeire, amelyeket az eszközregisztrációs protokollal (DEP) regisztráltak, ha az eszközhöz konfigurálva van a felhasználói affinitás.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP-token beszerzése és feltöltése

1.  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Felügyelet** &gt; **iOS és Mac OS X** &gt; **Volume Purchase Program** (Mennyiségi vásárlási program) elemet.

2.  Kattintson az **Apple VPP-fiók** hivatkozásra. Ha még nem tette meg, regisztráljon a Volume Purchase Program for Business programba. A regisztrációt követően töltse le a fiókjához tartozó Apple VPP-tokent.

3.  Az Intune-konzolon **Az Apple Volume Purchase Program (VPP) kezelése** oldalon válassza **A VPP-token feltöltése** lehetőséget.

4.  A **VPP-token feltöltése** párbeszédpanelen írja be vagy a vágólapról illessze be a VPP-token nevét és az Ön Apple ID-ját, majd válassza a **Feltöltés** elemet.

5.  A figyelmeztető párbeszédpanelen a jelölőnégyzet bejelölésével jelezze, hogy tudomásul veszi, hogy később nem válthat másik VPP-fiókra, majd válassza az **Igen** lehetőséget.

A **Volume Purchase Program** lapon megtekintheti az Apple VPP-token információit, beleértve az utolsó frissítés idejét, a lejárat idejét, valamint hogy mikor volt utoljára szinkronizálva az Intune-nal.

Az Apple által tárolt adatok bármikor szinkronizálhatók az Intune-nal a **Szinkronizálás** lehetőség kiválasztásával.

## <a name="to-deploy-a-volume-purchased-app"></a>Mennyiségi programban vásárolt alkalmazás telepítése

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza az **Alkalmazások** &gt; **Alkalmazások** &gt; **Mennyiségi licencszerződés keretében vásárolt alkalmazások** elemet. Ebben a listában az összes, az Apple VPP-szolgáltatásából szinkronizált alkalmazás szerepel.

2.  Válassza ki a telepíteni kívánt alkalmazást, válassza a **Központi telepítés kezelése** elemet, majd az [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md) című témakörben található utasítások segítségével végezze el az alkalmazás feltöltését, létrehozását és telepítését.

> [!TIP]
> Válassza a **Szükséges** telepítési műveletet. A rendelkezésre álló telepítések jelenleg nem támogatottak. Ezenkívül telepítheti az alkalmazást felhasználói csoportok számára is.

Ha az alkalmazást **Szükséges** telepítésként telepíti, az alkalmazást telepítő összes felhasználó felhasznál egy licencet.

A licencek visszanyeréséhez módosítania kell a központi telepítési műveletet az **Eltávolítás** műveletre. A licenc az alkalmazás eltávolítása után felszabadul.

Amikor egy jogosult eszközzel rendelkező felhasználó először próbál VPP-alkalmazást telepíteni, a rendszer megkéri, hogy csatlakozzon az Apple Volume Purchase programhoz. Ezt a lépést az alkalmazás telepítésének folytatása előtt kell megtennie.

Ha nincsenek további elérhető licencek, a telepítés meghiúsul.

## <a name="to-monitor-apple-vpp-apps"></a>Apple VPP-alkalmazások figyelése
Az **Alkalmazások** munkaterületen a **Mennyiségi licencszerződés keretében vásárolt alkalmazások** csomópontban követheti nyomon, hogy mely VPP-alkalmazásokat telepítették, és hány licencet használtak fel.

> [!TIP]
> Az alkalmazás **szűrőivel** megvizsgálhatja az egyes alkalmazástelepítések állapotát.

### <a name="see-also"></a>További információ
[Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md)


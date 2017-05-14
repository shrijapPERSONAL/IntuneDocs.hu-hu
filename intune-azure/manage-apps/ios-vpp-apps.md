---
title: "Mennyiségi programban vásárolt iOS-alkalmazások felügyelete | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure előzetes verzió: Az iOS áruházból mennyiségi programban vásárolt alkalmazások szinkronizálása az Intune-nal, majd használatuk felügyelete és nyomon követése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: 1909549b321f51069bb6ad83f2f245afbf60b7dd
ms.contentlocale: hu-hu
ms.lasthandoff: 05/03/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az iOS App Store áruháza lehetővé teszi, hogy több licencet is vásároljon a vállalatnál használni kívánt alkalmazásokhoz. Ezzel a megoldással csökkenthetők az alkalmazások különböző megvásárolt példányainak nyilvántartásával járó adminisztratív terhek.

A Microsoft Intune segít az e program keretében vásárolt alkalmazások felügyeletében. Ehhez importálja a licencadatokat az App Store áruházból, figyelemmel kíséri, hogy hány licencet használt fel, és meggátolja, hogy több alkalmazáspéldányt használjon, mint amennyit vásárolt.

Ezen kívül az Apple mennyiségi vásárlásra szolgáló áruházából vásárolt könyvek szinkronizálhatók, felügyelhetők és hozzárendelhetők az Intune-nal, és felhasználókhoz rendelhetők. Könyvek felügyeletéhez használja az Intune-portál **Könyvek** funkcióját. A könyvek felügyelete ugyanúgy történik, ahogy az alkalmazásoké.
Mielőtt felügyelhetné a könyveket, fel kell töltenie egy Apple mennyiségi vásárlási program-tokent. Jelenleg csak **Kötelező** telepítésként rendelhet hozzá könyveket.
Csak olyan eszközhöz rendelhet hozzá könyvet, amelyen telepítve van a beépített iBooks alkalmazás. Ha az alkalmazás nincs telepítve, a felhasználó csak az alkalmazás újratelepítése után olvashatja a könyvet. Az Intune jelenleg nem használható eltávolított beépített alkalmazások újratelepítésére.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Nagy mennyiségben vásárolt alkalmazások felügyelete iOS-eszközökön
Az [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/) vagy az [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store) programon keresztül vásárolhat egyszerre több licencet az iOS-alkalmazásokhoz. Ehhez Apple VPP-fiókot kell beállítani az Apple webhelyén, és az Apple VPP-tokent fel kell tölteni az Intune-ba.  Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

## <a name="before-you-start"></a>Előkészületek
Mielőtt hozzálát, be kell szereznie a VPP-tokent az Apple-től, és fel kell töltenie azt az Intune-fiókjába. Ezenkívül tisztában kell lennie a következőkkel:

* Több mennyiségi vásárlási program tokenjeit társíthatja az Intune-fiókhoz.
* Ha korábban VPP-tokent használt egy másik termékkel, egy újat kell létrehoznia az Intune használatához.
* A tokenek egy évig érvényesek.
* Alapértelmezés szerint az Intune naponta kétszer szinkronizál az Apple VPP szolgáltatással. Manuális szinkronizálás bármikor kezdeményezhető.
* Miután a VPP-tokent az Intune-ba importálta, ne importálja ugyanezt a tokent egy másik eszközfelügyeleti megoldásba. Ez a licenc-hozzárendelések és a felhasználói rekordok elvesztését eredményezheti.
* Mielőtt az iOS VPP-t az Intune-nal kezdené használni, távolítsa el a más mobileszköz-felügyeleti (MDM) megoldás használatával létrehozott összes meglévő VPP-felhasználói fiókot. Az Intune biztonsági okokból nem szinkronizálja ezeket a felhasználói fiókokat az Intune-ba. Az Intune csak az Intune által létrehozott adatokat szinkronizálja Apple VPP szolgáltatásból.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP-token beszerzése és feltöltése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1.  A **Mobilalkalmazások** munkafolyamatban válassza a **Telepítés** > **iOS VPP-jogkivonatok** elemet.
2.  A VPP-tokenek panel listájában kattintson a **Hozzáadás** elemre.
3.  Az Új VPP-token panelen adja meg az alábbi adatokat:
    - **VPP-jogkivonatfájl** – Ha még nem tette meg, iratkozzon fel a Volume Purchase Program vagy a Volume Purchase Program programra. A regisztrációt követően töltse le a fiókjához tartozó Apple VPP-tokent, és itt jelölje ki.
    - **Apple ID** – Adja meg a mennyiségi vásárlási programhoz kapcsolódó fiók Apple ID-ját.
    - **VPP-fiók típusa** –A következő lehetőségek közül választhat: **Üzlet** és **Oktatás**.
4. Amikor elkészült, kattintson a **Feltöltés** gombra.

A token a jogkivonatok panel listájában jelenik meg.


Az Apple által tárolt adatok bármikor szinkronizálhatók az Intune-nal a **Szinkronizálás** lehetőség kiválasztásával.

## <a name="to-assign-a-volume-purchased-app"></a>Mennyiségi programban vásárolt alkalmazás hozzárendelése

1. A **Mobilalkalmazások** munkafolyamatban válassza a **Felügyelet** > **Licencelt alkalmazások** elemet.
2. Az alkalmazáslista panelen válassza ki azt az alkalmazást, amelyet szeretne hozzárendelni, és válassza a '**...**' > **Csoportok hozzárendelése**.
3. Az *Alkalmazás neve*>- **Hozzárendelt csoportok** panelen válassza a **Felügyelet** > **Hozzárendelt csoportok** elemet.
4. Válassza az **Assign Groups** (Csoportok hozzárendelése), majd a **Select groups** (Csoportok kijelölése) panelen jelölje ki azon Azure AD-beli felhasználói vagy eszközcsoportokat, amelyekhez hozzá szeretné rendelni az alkalmazást.
Válassza a **Szükséges** hozzárendelési műveletet. az eszközcsoportokhoz való hozzárendelés pedig csak a 2017 januárja után létrehozott új bérlők esetében érhető el. Ha az Ön bérlője korábban jött létre, és nincs lehetősége a VPP-alkalmazásokat eszközcsoportokhoz rendelni, forduljon az Intune ügyfélszolgálatához.
5. Ha elkészült, válassza a **Mentés** elemet.

Lásd [az alkalmazások figyelésével](monitor-apps.md) foglalkozó útmutatót, amely az alkalmazás-hozzárendelések figyeléséhez nyújt segítséget.

## <a name="further-information"></a>További információ

Ha az alkalmazást **Szükséges** telepítésként rendeli hozzá, az alkalmazást telepítő összes felhasználó felhasznál egy licencet.

A licencek visszanyeréséhez módosítania kell a hozzárendelési műveletet az **Eltávolítás** műveletre. A licenc az alkalmazás eltávolítása után felszabadul.

Amikor egy jogosult eszközzel rendelkező felhasználó először próbál VPP-alkalmazást telepíteni, a rendszer megkéri, hogy csatlakozzon az Apple Volume Purchase programhoz. Ezt a lépést az alkalmazás telepítésének folytatása előtt kell megtennie.

Ha VPP-alkalmazás elérhetőként való hozzárendelését végzi, az alkalmazás tartalmának és licencének hozzárendelése közvetlenül az alkalmazás-áruházból történik.


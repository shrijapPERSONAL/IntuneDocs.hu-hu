---
title: "Mennyiségi programban vásárolt iOS-alkalmazások felügyelete"
titleSuffix: Intune on Azure
description: "Az iOS áruházból mennyiségi programban vásárolt alkalmazások szinkronizálása az Intune-nal, majd használatuk felügyelete és nyomon követése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az iOS App Store áruháza lehetővé teszi, hogy több licencet is vásároljon a vállalatnál használni kívánt alkalmazásokhoz. Az alkalmazás több példányának megvásárlásával csökkenthetők az alkalmazások különböző megvásárolt példányainak nyilvántartásával járó adminisztratív terhek.

A Microsoft Intune segítséget nyújt az ilyen program keretében vásárolt alkalmazások kezelésében a következő módon:

- A licencinformáció importálása az App Store-ból
- A felhasznált licencek számának nyilvántartása
- Annak megakadályozása, hogy több példányt telepítsen az alkalmazásból, mint amennyit vásárolt

Ezen kívül az Apple mennyiségi vásárlásra szolgáló áruházából vásárolt könyvek szinkronizálhatók, felügyelhetők és hozzárendelhetők az Intune-nal. Könyvek felügyeletéhez használja az Intune-portál **Könyvek** funkcióját. A könyvek felügyelete ugyanúgy történik, ahogy az alkalmazásoké.
Mielőtt nekikezdhetne, fel kell töltenie egy Apple mennyiségi vásárlási program-tokent. Jelenleg csak **Kötelező** telepítésként rendelhet hozzá könyveket.
Csak olyan eszközhöz rendelhet hozzá könyvet, amelyen telepítve van a beépített iBooks alkalmazás. Ha az alkalmazás nincs telepítve, a felhasználó csak az alkalmazás újratelepítése után olvashatja a könyvet. Az Intune jelenleg nem használható eltávolított beépített alkalmazások újratelepítésére.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Nagy mennyiségben vásárolt alkalmazások felügyelete iOS-eszközökön
Az [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/) vagy az [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store) programon keresztül vásárolhat egyszerre több licencet az iOS-alkalmazásokhoz. Ez az eljárás magában fogalja Apple VPP-fiók beállítását az Apple webhelyén, és az Apple VPP-token feltöltését az Intune-ba.  Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

## <a name="before-you-start"></a>Előkészületek
Mielőtt hozzálát, be kell szereznie a VPP-tokent az Apple-től, és fel kell töltenie azt az Intune-fiókjába. Ezenkívül tisztában kell lennie a következő feltételekkel:

* Több mennyiségi vásárlási program tokenjeit társíthatja az Intune-fiókhoz.
* Ha korábban VPP-tokent használt egy másik termékkel, egy újat kell létrehoznia az Intune használatához.
* A tokenek egy évig érvényesek.
* Alapértelmezés szerint az Intune naponta kétszer szinkronizál az Apple VPP szolgáltatással. Manuális szinkronizálás bármikor kezdeményezhető.
* Miután a VPP-tokent az Intune-ba importálta, ne importálja ugyanezt a tokent egy másik eszközfelügyeleti megoldásba. Ez a licenc-hozzárendelések és a felhasználói rekordok elvesztését eredményezheti.
* Mielőtt az iOS VPP-t az Intune-nal kezdené használni, távolítsa el a más mobileszköz-felügyeleti (MDM) megoldás használatával létrehozott összes meglévő VPP-felhasználói fiókot. Az Intune biztonsági okokból nem szinkronizálja ezeket a felhasználói fiókokat az Intune-ba. Az Intune csak az Intune által létrehozott adatokat szinkronizálja az Apple VPP szolgáltatásból.
* Az Intune legfeljebb 256 VPP-token hozzáadását támogatja.
* Ha egy Eszközregisztrációs profillal vagy az Apple Configuratorban regisztrált eszközhöz rendel hozzá mennyiségi programban vásárolt alkalmazást, akkor csak az eszközökre célzott alkalmazások fognak működni. Nem célozhatja meg mennyiségi programban vásárolt alkalmazásokkal az olyan DEP-eszköz felhasználóit, amely nem rendelkezik felhasználói affinitással.
* A VPP-token használata egyszerre csak egy Intune-fiókban támogatott. Nem használja újra ugyanazt a VPP-tokent több Intune-bérlőhöz.
* Ha felhasználólicencelési modellel rendel hozzá VPP-alkalmazásokat a felhasználókhoz vagy eszközökhöz (felhasználói affinitással), minden egyes Intune-felhasználót társítani kell egy egyedi Apple ID-vel vagy egy e-mail-címmel, amikor az eszközükön elfogadják az Apple használati feltételeit.
Amikor beállít egy eszközt egy új Intune-felhasználó számára, konfigurálja azt a felhasználó egyedi Apple ID-jével vagy e-mail-címével. Az Apple ID vagy e-mail-cím és az Intune-felhasználó egyedi párosítást alkot, amely akár 5 eszközön használható.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP-token beszerzése és feltöltése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1.  A **Mobilalkalmazások** munkafolyamatban válassza a **Telepítés** > **iOS VPP-jogkivonatok** elemet.
2.  A VPP-tokenek panel listájában kattintson a **Hozzáadás** elemre.
3.  Az **Új VPP-token** panelen adja meg az alábbi adatokat:
    - **VPP-jogkivonatfájl** – Ha még nem tette meg, iratkozzon fel a vállalati Volume Purchase Programra vagy az oktatási programra. A regisztrációt követően töltse le a fiókjához tartozó Apple VPP-tokent, és itt jelölje ki.
    - **Apple ID** – Adja meg a mennyiségi vásárlási programhoz kapcsolódó fiók Apple ID-ját.
    - **VPP-fiók típusa** –A következő lehetőségek közül választhat: **Üzlet** és **Oktatás**.
4. Amikor elkészült, kattintson a **Feltöltés** gombra.

A token a jogkivonatok panel listájában jelenik meg.


Az Apple által tárolt adatok bármikor szinkronizálhatók az Intune-nal a **Szinkronizálás** lehetőség kiválasztásával.

> [!NOTE]
> A Microsoft Intune csak azoknak az alkalmazásoknak az adatait szinkronizálja, amelyek nyilvánosan elérhetők a iTunes Store-ban. **Az iOS-re készült egyéni B2B-alkalmazások** még nem támogatottak. Ha a használati esete ilyen alkalmazásokra vonatkozik, az alkalmazásadatok nem szinkronizálódnak.

## <a name="to-assign-a-volume-purchased-app"></a>Mennyiségi programban vásárolt alkalmazás hozzárendelése

1. A **Mobilalkalmazások** munkafolyamatban válassza a **Felügyelet** > **Licencelt alkalmazások** elemet.
2. Az alkalmazáslista panelen válassza ki azt az alkalmazást, amelyet szeretne hozzárendelni, és válassza a '**...**' > **Csoportok hozzárendelése**.
3. Az *Alkalmazás neve*>- **Hozzárendelt csoportok** panelen válassza a **Felügyelet** > **Hozzárendelt csoportok** elemet.
4. Válassza az **Assign Groups** (Csoportok hozzárendelése), majd a **Select groups** (Csoportok kijelölése) panelen jelölje ki azon Azure AD-beli felhasználói vagy eszközcsoportokat, amelyekhez hozzá szeretné rendelni az alkalmazást.
Válassza a **Szükséges** hozzárendelési műveletet. az eszközcsoportokhoz való hozzárendelés pedig csak a 2017 januárja után létrehozott új bérlők esetében érhető el. Ha az Ön bérlője ennél a dátumnál korábban jött létre, és nincs lehetősége a VPP-alkalmazásokat eszközcsoportokhoz rendelni, forduljon az Intune ügyfélszolgálatához.
5. Ha elkészült, válassza a **Mentés** elemet.

>[!NOTE]
>A megjelenített alkalmazások listája egy tokenhez van társítva. Ha van egy olyan alkalmazása, amely több VPP-tokenhez is társítva van, akkor ugyanaz az alkalmazás többször is megjelenik; minden tokenhez egyszer.

Az alkalmazás-hozzárendelések figyeléséhez a [How to monitor apps](apps-monitor.md) (Alkalmazások figyelése) című témakörben találhat segítséget.

## <a name="further-information"></a>További információ

Ha az alkalmazást **Szükséges** telepítésként rendeli hozzá, az alkalmazást telepítő összes felhasználó felhasznál egy licencet.

A licencek visszanyeréséhez módosítania kell a hozzárendelési műveletet az **Eltávolítás** műveletre. A licenc az alkalmazás eltávolítása után felszabadul.

Amikor egy jogosult eszközzel rendelkező felhasználó először próbál VPP-alkalmazást telepíteni, a rendszer megkéri, hogy csatlakozzon az Apple Volume Purchase programhoz. Még az alkalmazás telepítésének folytatása előtt csatlakozniuk kell. Az Apple Volume Purchase programhoz való csatlakozás meghívójához az szükséges, hogy a felhasználó tudja használni az iTunes alkalmazást az iOS-eszközön. Ha szabályzatot állított be az iTunes Store alkalmazás letiltásához, a VPP-alkalmazások felhasználói alapú licencelése nem fog működni. A megoldás az, hogy vagy engedélyezi az iTunes alkalmazást a szabályzat eltávolításával, vagy eszközalapú licencelést használ.

Ha VPP-alkalmazás elérhetőként való hozzárendelését végzi, az alkalmazás tartalmának és licencének hozzárendelése közvetlenül az alkalmazás-áruházból történik.

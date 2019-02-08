---
title: Mennyiségi programban vásárolt iOS-alkalmazások felügyelete a Microsoft Intune-ban
titlesuffix: ''
description: Az iOS áruházból mennyiségi programban vásárolt alkalmazások szinkronizálása a Microsoft Intune-nal, majd használatuk felügyelete és nyomon követése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e8af65738e51d7c1a5d0b1a0779c210b09bc044
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835435"
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az iOS App Store áruháza lehetővé teszi, hogy több licencet is vásároljon a vállalatnál használni kívánt alkalmazásokhoz. Több licenc vásárlásával hatékonyabban kezelhetők a vállalaton belüli alkalmazások.

A Microsoft Intune segítséget nyújt az ilyen program keretében vásárolt alkalmazások több példányának kezelésében a következő módon:

- Licencinformációk jelentése az App Store-ból.
- A felhasznált licencek számának nyilvántartása.
- Annak megakadályozása, hogy több példányt telepítsen az alkalmazásból, mint amennyit vásárolt.

A mennyiségi programban vásárolt alkalmazásokat kétféle módszerrel lehet hozzárendelni:

### <a name="device-licensing"></a>Eszközlicencelés

Ha eszközhöz rendeli az alkalmazást, egyetlen alkalmazáslicenc lesz használatban, továbbra is ahhoz az eszközhöz társítva, amelyhez hozzárendelte.

Ha mennyiségi programban vásárolt alkalmazásokat rendel az eszközhöz, a végfelhasználónak nem kell Apple ID azonosítót megadnia az áruházhoz való hozzáféréshez.

### <a name="user-licensing"></a>Felhasználói licencelés

Ha felhasználóhoz rendeli az alkalmazást, egyetlen alkalmazáslicenc lesz használatban, a felhasználóhoz társítva. Az alkalmazás több, a felhasználó tulajdonában lévő eszközön is futhat (ennek a korlátját az Apple határozza meg).

Ha mennyiségi programban vásárolt alkalmazásokat rendel felhasználókhoz, minden végfelhasználónak érvényes, egyedi Apple ID azonosítóval kell rendelkeznie az App Store-hoz való hozzáféréshez.

Ezen kívül az Apple mennyiségi vásárlásra (VPP) szolgáló áruházából vásárolt könyvek szinkronizálhatók, felügyelhetők és hozzárendelhetők az Intune-nal. További információkat a [Mennyiségi vásárlási program keretében vásárolt iOS-es e-könyvek kezelése](vpp-ebooks-ios.md) című cikkben talál.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Nagy mennyiségben vásárolt alkalmazások felügyelete iOS-eszközökön

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Az Apple Volume Purchase Program keretében vásárolt iOS-alkalmazások támogatása

Az [Apple Volume Purchase Program for Business (VPP)](https://www.apple.com/business/vpp/) vagy az [Apple Volume Purchase Program for Education](https://volume.itunes.apple.com/us/store) programon keresztül vásárolhat egyszerre több licencet az iOS-alkalmazásokhoz. Ez az eljárás magában fogalja Apple VPP-fiók beállítását az Apple webhelyén, és az Apple VPP-token feltöltését az Intune-ba.  Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Vállalatok közötti mennyiségi vásárlás keretében vásárolt iOS-alkalmazások támogatása

Ezenkívül, az iTunes Connectben megadott, megfelelő jogosultságokkal rendelkező Volume Purchase Program for Business-tagoknak külsős fejlesztők is terjeszthetik alkalmazásaikat. Ezek a VPP for Business-tagok be tudnak jelentkezni a Volume Purchase Program App Store áruházba, és ott meg tudják venni azokat az alkalmazásokat, amelyekre szükségük van. A végfelhasználók által a VPP for Business keretében megvásárolt alkalmazások Intune-bérlőikkel szinkronizálják magukat.

## <a name="before-you-start"></a>Előkészületek
Mielőtt hozzálát, be kell szereznie a VPP-tokent az Apple-től, és fel kell töltenie azt az Intune-fiókjába. Ezenkívül tisztában kell lennie a következő feltételekkel:

* Intune-fiókjához több VPP-tokent is társíthat.
* Ha korábban VPP-tokent használt egy másik termékkel, egy újat kell létrehoznia az Intune használatához.
* A tokenek egy évig érvényesek.
* Alapértelmezés szerint az Intune naponta kétszer szinkronizál az Apple VPP szolgáltatással. Manuális szinkronizálás bármikor kezdeményezhető.
* Mielőtt az Apple VPP-t az Intune-nal kezdené használni, távolítsa el a más mobileszköz-felügyeleti (MDM) megoldás használatával létrehozott összes meglévő VPP-felhasználói fiókot. Az Intune biztonsági okokból nem szinkronizálja ezeket a felhasználói fiókokat az Intune-ba. Az Intune csak az Intune által létrehozott adatokat szinkronizálja az Apple VPP szolgáltatásból.
* Az Intune legfeljebb 256 VPP-token hozzáadását támogatja.
* Az Apple készülékregisztrációs profil (DEP) program automatizálja a mobileszközök felügyeleti célú regisztrációját (MDM regisztrációját). A készülékregisztrációs profilt használva a vállalati eszközöket kézbevétel nélkül is be tudja állítani. A DEP programba ugyanazzal a programügynök-fiókkal tud regisztrálni, mint amit az Apple VPP-hez használt. Az [Apple Központi Telepítési Program](https://deploy.apple.com) oldalon felsorolt valamennyi program egyedi azonosítóval rendelkezik, amellyel nem lehet bejelentkezni az olyan Apple-szolgáltatásokba, mint amilyen például az iTunes áruház.
* Ha felhasználólicencelési modellel rendel hozzá VPP-alkalmazásokat a felhasználókhoz vagy eszközökhöz (felhasználói affinitással), minden egyes Intune-felhasználót társítani kell egy egyedi Apple ID-vel vagy egy e-mail-címmel, amikor az eszközükön elfogadják az Apple használati feltételeit.
* Amikor beállít egy eszközt egy új Intune-felhasználó számára, konfigurálja azt a felhasználó egyedi Apple ID-jével vagy e-mail-címével. Az Apple ID vagy e-mail-cím és az Intune-felhasználó egyedi párt alkot, amely akár öt eszközön használható.
* A VPP-token használata egyszerre csak egy Intune-fiókban támogatott. Nem használja újra ugyanazt a VPP-tokent több Intune-bérlőhöz.

>[!IMPORTANT]
>Miután a VPP-tokent az Intune-ba importálta, ne importálja ugyanezt a tokent egy másik eszközfelügyeleti megoldásba. Ez a licenc-hozzárendelések és a felhasználói rekordok elvesztését eredményezheti.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP-token beszerzése és feltöltése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3.  Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** > **iOS-es VPP-tokenek** elemet a **Beállítás** lehetőség alatt.
4.  A VPP-tokenek panel listájában válassza a **Létrehozás** elemet.
5. Az **VPP-token Létrehozása** panelen adja meg az alábbi adatokat:
    - **VPP-jogkivonatfájl** – Ha még nem tette meg, iratkozzon fel a vállalati Volume Purchase Programra vagy az oktatási programra. A regisztrációt követően töltse le a fiókjához tartozó Apple VPP-tokent, és itt jelölje ki.
    - **Apple ID** – Adja meg a mennyiségi vásárlási programhoz kapcsolódó fiók Apple ID-ját.
    - **Ország/régió** – Válassza ki a VPP országkódját.  Az Intune a megadott VPP-ország áruházából az összes területi beállításhoz tartozó VPP-alkalmazást szinkronizálja.
        > [!WARNING]  
        > Az ország módosításakor az ezzel a tokennel létrehozott alkalmazásoknál az Apple-szolgáltatással való legközelebbi szinkronizálás alkalmával frissülni fognak az alkalmazás metaadatai és az áruházi URL-cím. Az alkalmazás nem fog frissülni, ha az nem található meg az új országhoz tartozó áruházában.

    - **VPP-fiók típusa** –A következő lehetőségek közül választhat: **Üzlet** és **Oktatás**.
    - **Alkalmazások automatikus frissítése** – Az automatikus frissítés engedélyezéséhez válasszon a **Be** és **Ki** érték közül. Engedélyezés esetén az Intune észleli, ha az alkalmazás-áruházban az adott VPP-alkalmazáshoz frissítés érhető el, és az eszköz legközelebbi bejelentkezésekor automatikusan leküldi a frissítéseket az eszközre. Az Apple VPP automatikus alkalmazásfrissítései csak a **Kötelező** telepítési szándékkal üzembe helyezett alkalmazásokat frissítik automatikusan. A **Rendelkezésre áll** telepítési szándékkal üzembe helyezett alkalmazásoknál az automatikus frissítés létrehoz egy értesítést a rendszergazda számára, amely tájékoztatja, hogy rendelkezésre áll az alkalmazás új verziója. A felhasználónak rá kell kattintania a Telepítés gombra az alkalmazás újabb verziójának telepítéséhez. Emellett a felhasználó a Céges portálon nem telepítettként látja az alkalmazást, annak ellenére, hogy annak régebbi verziója telepítve van. Ebben az esetben a felhasználó újratelepítheti az alkalmazást.
    
        > [!NOTE]
        > Az automatikus alkalmazásfrissítések eszköz- és felhasználói licencelésű alkalmazások esetén is működnek az iOS 11.0 és újabb verzióin.
6. Amikor elkészült, válassza a **Létrehozás** gombot.

A token a jogkivonatok panel listájában jelenik meg.

Az Apple által tárolt adatok bármikor szinkronizálhatók az Intune-nal a **Szinkronizálás** lehetőség kiválasztásával.

## <a name="to-assign-a-volume-purchased-app"></a>Mennyiségi programban vásárolt alkalmazás hozzárendelése

1.  Az **Intune** ablaktáblán válassza az **Eszközalkalmazások** > **Alkalmazások** elemet a **Kezelés** lehetőség alatt.
2.  Az alkalmazáslista paneljén válassza ki a hozzárendelni kívánt alkalmazást, és válassza a **Hozzárendelés** lehetőséget.
3.  Az ***Alkalmazás neve*** - **Hozzárendelések** panelen kattintson a **Csoport hozzáadása** elemre, majd a **Csoport hozzáadása** panelen válasszon egy **hozzárendelés-típust** és azokat az Azure AD-beli felhasználói vagy eszközcsoportokat, amelyekhez hozzá kívánja rendelni az alkalmazást.
5.  Minden kijelölt csoporthoz válassza ki az alábbi beállításokat:
    - **Típus** – Határozza meg, hogy az alkalmazás **Elérhető**, azaz a végfelhasználók telepíthetik a Céges portálról, vagy **Kötelező**, azaz a végfelhasználók automatikusan megkapják az telepített alkalmazást.
    - **Licenc típusa** – Válassza a **Felhasználói licencelés** vagy az **Eszközlicencelés** lehetőséget.
6.  Ha elkészült, válassza a **Mentés** elemet.


>[!NOTE]
>A megjelenített alkalmazások listája egy tokenhez van társítva. Ha van egy olyan alkalmazása, amely több VPP-tokenhez is társítva van, akkor ugyanaz az alkalmazás többször is megjelenik; minden tokenhez egyszer.

## <a name="end-user-prompts-for-vpp"></a>VPP-figyelmeztetés a végfelhasználónak

A végfelhasználó különféle helyzetekben figyelmeztetést fog kapni VPP-alkalmazások telepítésére. A különféle feltételek az alábbi táblázatban láthatók:

| # | Forgatókönyv                                | Meghívás az Apple VPP-programba                              | Figyelmeztetés alkalmazástelepítésre | Apple ID bekérése |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | BYOD – licenccel rendelkező felhasználó                             | I                                                                                               | I                                           | I                                 |
| 2 | Corp (Vállalat) – licenccel rendelkező felhasználó (nem felügyelt eszköz)     | I                                                                                               | I                                           | I                                 |
| 3 | Corp (Vállalat) – licenccel rendelkező felhasználó (felügyelt eszköz)         | I                                                                                               | N                                           | I                                 |
| 4 | BYOD – licenccel rendelkező eszköz                           | N                                                                                               | I                                           | N                                 |
| 5 | CORP (Vállalat) – licenccel rendelkező eszköz (nem felügyelt eszköz)                           | N                                                                                               | I                                           | N                                 |
| 6 | CORP (Vállalat) – licenccel rendelkező eszköz (felügyelt eszköz)                           | N                                                                                               | N                                           | N                                 |
| 7 | Teljes képernyős mód (felügyelt eszköz) – licenccel rendelkező eszköz | N                                                                                               | N                                           | N                                 |
| 8 | Teljes képernyős mód (felügyelt eszköz) – licenccel rendelkező felhasználó   | --- | ---                                          | ---                                |

> [!Note]  
> VPP-alkalmazásokat nem ajánlott teljes képernyős eszközökhöz rendelni VPP-felhasználói licenceléssel.

## <a name="revoking-app-licenses-and-deleting-tokens"></a>Alkalmazásengedélyek visszavonása és tokenek törlése 

Visszavonhatja az iOS-es mennyiségi licencprogramban (VPP) részt vevő összes társított alkalmazáslicencet az adott eszköz, felhasználó vagy alkalmazás alapján. A felhasználókat értesítheti, amikor megszűnik az alkalmazás hozzájuk rendelése. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás eltávolításához és a felhasználóhoz vagy eszközhöz társított alkalmazáslicenc visszaszerzéséhez a hozzárendelési műveletet meg kell változtatnia **Eltávolítás** műveletre. Ha egy felhasználóhoz hozzárendelt alkalmazást eltávolít, az Intune visszaigényli a felhasználó vagy az eszköz licencét, és eltávolítja az alkalmazást az eszközről. A visszavont licencek száma látható lesz az Intune **Alkalmazások** tevékenységcsoportján belüli **Licencelt alkalmazások** csomóponton. Miután eltávolított egy VPP-alkalmazást és visszavonta az alkalmazás licencét, választhatja, hogy hozzárendeli az alkalmazás licencét egy másik felhasználóhoz vagy eszközhöz. 

>[!NOTE]
>Ha egy alkalmazott távozik a cégtől, és nem tagja már AAD-csoportoknak, az Intune visszaszerez minden olyan alkalmazáslicencet, amely felhasználó által licencelt iOS VPP-alkalmazáshoz tartozik.

<!-- 820879 -->  
A konzol segítségével törölheti az iOS Volume Purchasing Program (VPP) tokenjét. Ez akkor lehet szükséges, ha egy VPP-token több példányban van meg. A token törlésével a kapcsolódó alkalmazásokat és hozzárendelést is törli. A token törlésével azonban nem vonja vissza az alkalmazáslicenceket, és nem töröl alkalmazásokat. 

>[!NOTE]
>Az Intune a token törlése után már nem tudja visszavonni az alkalmazáslicenceket. 

<!-- 820870 -->  
Ha egy VPP-token összes VPP-alkalmazásának licenceit törölni szeretné, először vissza kell vonnia a tokenhez társított összes alkalmazáslicencet, majd törölnie kell a tokent.

## <a name="renewing-app-licenses"></a>Alkalmazáslicencek megújítása

Az Apple VPP-jogkivonat megújításához töltsön le egy új jogkivonatot az Apple mennyiségi vásárlási programjának portáljáról, és frissítse az Intune-ban a meglévő jogkivonatot.

## <a name="deleting-an-ios-vpp-app"></a>iOS VPP-alkalmazás törlése

Jelenleg az iOS VPP-alkalmazások nem törölhetők a Microsoft Intune-ból.

## <a name="additional-information"></a>További információ

Amikor egy jogosult eszközzel rendelkező felhasználó először próbál VPP-alkalmazást telepíteni egy eszközön, a rendszer megkéri, hogy csatlakozzon az Apple Volume Purchase Programhoz. Még az alkalmazás telepítésének folytatása előtt csatlakozniuk kell. Az Apple Volume Purchase programhoz való csatlakozás meghívójához az szükséges, hogy a felhasználó tudja használni az iTunes alkalmazást az iOS-eszközön. Ha szabályzatot állított be az iTunes Store alkalmazás letiltásához, a VPP-alkalmazások felhasználói alapú licencelése nem fog működni. A megoldás az, hogy vagy engedélyezi az iTunes alkalmazást a szabályzat eltávolításával, vagy eszközalapú licencelést használ.

Az Apple közvetlen segítséget biztosít a VPP-tokenek létrehozásához és megújításához. További információkért lásd a [Tartalomterjesztés a felhasználók felé a Mennyiségi vásárlási program (VPP) segítségével](https://go.microsoft.com/fwlink/?linkid=2014661) című részt az Apple dokumentációjában. 

Ha az Intune portálján a **Külső MDM-hez rendelve** beállítás látható, a VPP-token Intune-beli használata előtt a rendszergazdának el kell távolítania a VPP-tokent a harmadik félhez tartozó MDM-ről.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

#### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Mennyi ideig tart, mire a portál frissíti a licencszámot egy alkalmazás telepítése vagy az eszközről való eltávolítása után?
A licenc néhány órával az alkalmazások telepítése vagy eltávolítása után frissül. Megjegyzés: Ha a végfelhasználó eltávolítja az alkalmazást, a licenc továbbra is a felhasználóhoz vagy az eszközhöz lesz rendelve.

#### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Túlléphető egy alkalmazáselőfizetés? Ha igen, milyen körülmények között?
Igen. Az Intune rendszergazdája túllépheti az alkalmazáselőfizetéseket. Ha például a rendszergazda 100 licencet vásárol XYZ alkalmazáshoz, majd egy 500 tagú csoporthoz rendeli azt. Az első 100 tag (felhasználó vagy eszköz) megkapja a licencet, a többi taghoz azonban nem lesz hozzárendelve licenc.

#### <a name="i-understand-intune-automatically-syncs-app-licenses-each-day-with-apple-is-that-correct"></a>Jól tudom, hogy az Intune naponta automatikusan szinkronizálja az alkalmazáslicenceket az Apple-lel?
Az Intune naponta kétszer szinkronizálja az Apple-lel az alkalmazáslicenceket.

## <a name="next-steps"></a>További lépések

Az alkalmazás-hozzárendelések figyeléséhez a [How to monitor apps](apps-monitor.md) (Alkalmazások figyelése) című témakörben találhat segítséget.

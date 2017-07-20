---
title: "Mennyiségi programban vásárolt iOS-es e-könyvek kezelése"
titleSuffix: Intune on Azure
description: "Az iOS-áruházból mennyiségi programban vásárolt könyvek szinkronizálása az Intune-nal, majd használatuk felügyelete és nyomon követése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e23c40eb4c13fd0d2593742c72086fc943fe2b54
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Mennyiségi vásárlási program keretében vásárolt iOS-es e-könyvek kezelése a Microsoft Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Apple Volume Purchase Program (VPP) keretében a vállalat felhasználói közt elosztani kívánt könyvekhez több licencet is vásárolhat. Az üzleti és az oktatási áruházakból vásárolt könyveket oszthatja el.

A Microsoft Intune segít a program keretében vásárolt könyvek szinkronizálásában, kezelésében és hozzárendelésében. Importálhatja az áruházból a licencadatokat, és nyomon követheti a felhasznált licencek számát.

A könyvek kezelésének eljárásai hasonlók a [VPP-alkalmazások kezeléséhez](vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Mennyiségi programban vásárolt könyvek kezelése iOS-eszközökön
Az [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/) vagy az [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store) programon keresztül vásárolhat egyszerre több licencet az iOS-könyvekhez. Ez az eljárás magában fogalja Apple VPP-fiók beállítását az Apple webhelyén, és az Apple VPP-token feltöltését az Intune-ba.  Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt könyvek használatát.

## <a name="before-you-start"></a>Előkészületek
Mielőtt hozzálát, szerezzen be VPP-tokent az Apple-től, és töltse fel az Intune-fiókjába. Egyéb rendelkezések:

* Intune-fiókjához akár 256 VPP-tokent is társíthat.
* Ha korábban VPP-tokent használt egy másik termékkel, egy újat kell létrehoznia az Intune használatához.
* A tokenek egy évig érvényesek.
* Alapértelmezés szerint az Intune naponta kétszer szinkronizál az Apple VPP szolgáltatással. Manuális szinkronizálás bármikor kezdeményezhető.
* Miután a VPP-tokent az Intune-ba importálta, ne importálja ugyanezt a tokent egy másik eszközfelügyeleti megoldásba. Ez a licenc-hozzárendelések és a felhasználói rekordok elvesztését eredményezheti.
* Mielőtt az iOS-könyveket az Intune-nal kezdené használni, távolítsa el a más mobileszköz-felügyeleti (MDM) megoldás használatával létrehozott összes meglévő VPP-felhasználói fiókot. Az Intune biztonsági okokból nem szinkronizálja ezeket a felhasználói fiókokat az Intune-ba. Az Intune csak az Intune által létrehozott adatokat szinkronizálja az Apple VPP szolgáltatásból.
* Jelenleg csak **Kötelező** telepítésként rendelhet hozzá könyveket. Ha a könyvet **Szükséges** telepítésként rendeli hozzá, a könyvet telepítő összes felhasználó felhasznál egy licencet.
* Csak olyan eszközhöz rendelhet hozzá könyvet, amelyen telepítve van a beépített iBooks alkalmazás. Ha nincs, akkor a felhasználónak újra kell telepítenie az alkalmazást, hogy el tudják olvasni a könyvet. Az Intune jelenleg nem használható eltávolított beépített alkalmazások újratelepítésére.
* Csak az Apple Volume Purchase Program webhelyéről rendelhet hozzá könyveket. A házon belül létrehozott könyveket nem töltheti fel és rendelheti hozzá.
* Jelenleg nem rendelhet hozzá könyveket a felhasználói kategóriákhoz ugyanúgy, ahogyan az alkalmazásokat.
* A könyv hozzárendelése után nem igényelhet vissza licencet.
* Amikor egy arra jogosult eszközzel rendelkező felhasználó először próbál VPP-könyvet telepíteni, először csatlakoznia kell az Apple Volume Purchase programhoz. A felügyelt Apple-azonosítókkal rendelkező biztonsági csoportokhoz is hozzárendelhet licenceket. Ha ezt teszi, akkor a könyvek telepítésekor a rendszer nem kéri a felhasználóktól az Apple-azonosítót.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP-token beszerzése és feltöltése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1.  A **Mobilalkalmazások** munkafolyamatban válassza a **Telepítés** > **iOS VPP-jogkivonatok** elemet.
2.  A VPP-tokenek panel listájában kattintson a **Hozzáadás** elemre.
3.  Az **Új VPP-token** panelen adja meg az alábbi adatokat:
    - **VPP-jogkivonatfájl** – Ha még nem tette meg, iratkozzon fel a Volume Purchase Program for Business vagy a Volume Purchase Program for Education programra. Ezután töltse le a fiókjához tartozó Apple VPP-tokent, és itt jelölje ki.
    - **Apple ID** – Adja meg a mennyiségi vásárlási programhoz kapcsolódó fiók Apple ID-ját.
    - **VPP-fiók típusa** –A következő lehetőségek közül választhat: **Üzlet** és **Oktatás**.
4. Amikor elkészült, kattintson a **Feltöltés** gombra.

A token a jogkivonatok panel listájában jelenik meg.


Az Apple által tárolt adatok bármikor szinkronizálhatók az Intune-nal a **Szinkronizálás** lehetőség kiválasztásával.

## <a name="to-assign-a-volume-purchased-app"></a>Mennyiségi programban vásárolt alkalmazás hozzárendelése

1. Az **e-könyvek** munkaterhelésben válassza a **Felügyelet** > **Összes e-könyv** lehetőséget.
2. A könyvlista panelen válassza ki azt a könyvet, amelyet szeretne hozzárendelni, és válassza a „**...**” elemet. > **Csoportok hozzárendelése**.
3. A <*könyv neve*> – **Hozzárendelt csoportok** panelen válassza a **Felügyelet** > **Hozzárendelt csoportok** lehetőséget.
4. Válassza a **Hozzárendelt csoportok**, majd a **Csoportok kiválasztása** panelt, és jelölje ki azon Azure AD felhasználói csoportokat, amelyekhez hozzá szeretné rendelni a könyvet. Az eszközcsoportok jelenleg nem támogatottak.
Válassza a **Szükséges** hozzárendelési műveletet. 
5. Ha elkészült, válassza a **Mentés** elemet.

## <a name="next-steps"></a>További lépések

Lásd [az alkalmazások figyelésével](apps-monitor.md) foglalkozó útmutatót, amely segítséget nyújt a könyvhozzárendelések figyeléséhez.






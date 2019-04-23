---
title: A Microsoft Intune bérlői állapota lap
titleSuffix: Microsoft Intune
description: Az Intune-bérlő állapotát lap segítségével fontos bérlői adatainak megtekintése az Intune-portál elhagyása nélkül
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/23/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0cde1977b0c126f478abae06860110acc2f10444
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514174"
---
# <a name="intune-tenant-status-page"></a>Az Intune bérlői állapota lap
A bérlő állapotának lap egy információs központ, ahol megtekinthetik az aktuális és fontos részleteket a bérlő kapcsolatban. Licenc rendelkezésre állási és használata, összekötő állapotát és az Intune szolgáltatással kapcsolatos fontos kommunikációs szerepel.  

Az irányítópult megtekintése az Azure Portalon, lépjen az **Intune > Bérlőállapot**.  Bérlői állapota megjelenik a **Súgó és támogatási csoport**.  

A lap négy területet oszlik:

## <a name="tenant-details"></a>Bérlő részletei
Bérlő részletei a bérlő egy pillantással adatainak megadása. Részletek megtekintése, például a bérlő nevét és helyét, az MDM-szolgáltató és a bérlők szolgáltatási kiadás száma. A kiadási száma egy hivatkozás, amely megnyitja a *Újdonságok az Intune-ban* a cikk a Microsoft docs webhelyén. A *Újdonságok*, itt olvashat a legújabb funkciókat és frissítéseket az Intune szolgáltatáshoz.  

Ez a szakasz is a rendelkezésre álló licencek és hány rendelkező felhasználókhoz rendelt alapvető információkat biztosít. Licencek eszközök nem jelennek meg.

## <a name="connector-status"></a>Összekötő állapota
Összekötő állapota egyablakos helyét az összes elérhető összekötő állapotának áttekintése az Intune-hoz.  

Az összekötők a következők:
- **Külső szolgáltatások úgy konfigurálhatók kapcsolatok**. Ha például a *Apple Volume Purchase Program* szolgáltatás vagy a *Windows Autopilot* szolgáltatás.  Az ilyen típusú összekötő állapota a legutóbbi sikeres szinkronizálásának időpontját alapul.
- **Tanúsítványok vagy egy külső nem felügyelt szolgáltatáshoz való csatlakozáshoz szükséges hitelesítő adatokat**, pl. *Apple leküldéses értesítési szolgáltatások* (APNS) tanúsítványokat. Az ilyen típusú összekötő állapota a lejárat időbélyeg a tanúsítvány vagy hitelesítő adatok alapján történik.  

Alapértelmezés szerint a megjelenített legfeljebb öt összekötők jeleníti meg. Választhat **tekintse meg az összes összekötő** bontsa ki a lista az összes elérhető összekötők, többek között még nem konfigurálta használható összekötők megtekintéséhez.  

Nem megfelelő állapotú összekötők mindig a lista tetején jelennek meg. Ezután olyan összekötőket figyelmeztetéseket, majd a megfelelő összekötők listája. Még nem konfigurálta összekötőket utolsó.

Ha több mint egy típustól egy összekötőt, az állapota az összes azonos összekötőket összegzését. A csoport egyetlen összekötőket legalább kifogástalan állapotát az egészségügyi lesz.  

**Összekötő állapota:**
- **Nem megfelelő állapotú:**
    - A tanúsítvány vagy hitelesítő adatok érvényessége lejárt
    - A legutóbbi szinkronizálás legalább három nappal ezelőtt volt
- **Figyelmeztetés:**
    - A tanúsítvány vagy hitelesítő adatok hét napon belül lejár
    - A legutóbbi szinkronizálás több mint egy nappal ezelőtt volt
- **Kifogástalan állapotú:**
    - A tanúsítvány vagy hitelesítő adatok nem jár le a hét napon belül
    - A legutóbbi szinkronizálás kevesebb, mint egy nappal ezelőtt volt  

Amikor kiválaszt egy összekötőt a listából, a portál megjelenít a portálon, amely fontos létrehozásáról és konfigurálásáról az összekötőt.  Például, ha kiválasztja a **VPP lejárati dátuma** összekötőt, a **Program-tokenek mennyiségi licencszerződés keretében vásárolt iOS** lap megnyitásakor, ahol megtekintheti, hogy az összekötő további információt. Ezután hozzon létre egy új konfigurációt vagy szerkesztheti és problémáinak elhárítása egy már meglévőt.  

## <a name="intune-service-health"></a>Az Intune szolgáltatás állapota  
Keresse meg a Microsoft 365 üzemállapot-jelző pult vagy az üzenetközpont nélkül megtekintheti az aktív incidensek által érintett, és a tanácsadók adatait, is található a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com). Csak a ahol hatás lett tudomásul vette a bérlő érintő incidensek jelennek meg.  

Amikor kiválaszt egy incidenst, a támogatási kérelem részletek közvetlenül a bérlő állapotának oldalán jelennek meg. Tanácsok és incidensek korábbi megtekintéséhez jelölje ki **korábbi incidensek/tanácsadók**. A Microsoft 365 felügyeleti központ megnyílik, és ezután megtekintheti tanácsok és incidensek az elmúlt 30 nap-bérlője számára.  

Információk megtekintéséhez *az Intune szolgáltatás állapota*, a fióknak rendelkeznie kell a **globális rendszergazdai** vagy **szolgáltatás-rendszergazda** szerepkört az Azure Active Directoryban vagy a A Microsoft 365 felügyeleti központban. Szeretné hozzárendelni ezeket az engedélyeket, jelentkezzen be a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com) globális rendszergazdai jogosultságokkal rendelkező. Válassza ki **felhasználók > aktív felhasználók**, és válassza ki azt a fiókot, amelyhez hozzáférés szükséges. Válassza ki **szerkesztése** szerepkörhöz, válassza ki a *szolgáltatás-rendszergazda* vagy *globális rendszergazdai*, majd **mentése** hozzárendelése a módosításokat a engedélyek.  

A kommunikációs beállítások az Intune szolgáltatás állapotát a Microsoft 365 felügyeleti központban csak beállítása.

## <a name="intune-news"></a>Az Intune-hírek  
Tájékoztató kommunikáció az Intune szolgáltatás csapat megtekintéséhez nyissa meg az Office Üzenetközpontjában nélkül. Kommunikációs üzeneteket, amelyek nemrég történt az Intune szolgáltatásba, vagy az a bérlőhöz tartozó von a változásokat tartalmazza.  

Alapértelmezés szerint a legutóbbi 10 aktív üzenetek jelennek meg. Régebbi üzeneteket megtekintéséhez jelölje ki **lásd a régebbi üzeneteket** megnyitásához a *üzenetközpont* a Microsoft 365 felügyeleti központban.  

Információk az Intune hírek megtekintéséhez, a fióknak rendelkeznie kell a **globális rendszergazdai** vagy **szolgáltatás-rendszergazda** szerepkörhöz az Azure Active Directoryban, vagy a **üzenetközpont olvasó** szerepkört a Microsoft 365 felügyeleti központban.  Rendelje hozzá ezt az engedélyt, jelentkezzen be a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com) rendszergazdai jogosultságokkal. Válassza ki **felhasználók > aktív felhasználók**, és válassza ki azt a fiókot, amelyhez hozzáférés szükséges. Válassza ki **szerkesztése** a *szerepkörök*, jelölje be *csapatok kommunikáció rendszergazda*, majd **mentése** az engedélyek hozzárendelése a szerkesztése.  

A kommunikációs beállítások az Intune hírek a Microsoft 365 felügyeleti központban csak beállítása.

---
title: Eszközprofilok hibaelhárítása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Gyakori kérdések és válaszok a szabályzatok és profilok, beleértve a profilmódosítások nem alkalmazza a felhasználókhoz vagy eszközökhöz, mennyi ideig tart az új házirendeket lehet leküldeni az eszközre, mely beállítások több szabályzatok érvényesek, mi történik, amikor egy profil a törölt vagy eltávolított, és több Microsoft Intune-nal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12ac2b93126f271bf4918c6a914dedc7a22c1010
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461005"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Gyakori kérdések, problémák és megoldások a szabályzatok és profilok a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Válaszok a gyakori kérdésekre eszközprofilokat és szabályzatokat az Intune-ban való munka során. Ez a bejelentkezési időintervallumok listák is cikkre, biztosít több lefoglalja az ütközések és egyéb.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Miért nem kap a felhasználó új profilt, amikor megváltoztatja a jelszót vagy a hozzáférési kódot egy létező Wi-Fi-profilban?

Ön létrehoz egy vállalati Wi-Fi-profilt, hozzárendeli egy csoporthoz, megváltoztatja a jelszót, és menti a profilt. A profil megváltoztatásakor egyes felhasználók esetleg nem kapják meg az új profilt.

A probléma következményei vendég Wi-Fi beállításával mérsékelhetők. A vállalati Wi-Fi kiesése esetén a felhasználók a vendég Wi-Fi-hez kapcsolódhatnak. Gondoskodjon az automatikus csatlakozás beállításáról. A vendég Wi-Fi profilt rendelje hozzá minden felhasználóhoz.

Néhány további javaslat:  

- Ha a Wi-Fi-hálózathoz csatlakozik, jelszót vagy hozzáférési kódot használ, győződjön meg arról, hogy közvetlenül tud kapcsolódni a Wi-Fi-útválasztóhoz. Ezt kipróbálhatja egy iOS-eszközzel.
- A Wi-Fi-végponthoz (Wi-Fi-útválasztóhoz) való sikeres kapcsolódás után jegyezze fel az SSID-t és a használt hitelesítő adatokat (ez a jelszó vagy a hitelesítő kód).
- Adja meg az SSID-t és a hitelesítő adatokat (jelszót vagy hitelesítő kódot) az Előmegosztott kulcs mezőben. 
- Alkalmazza egy tesztcsoportra, amelynek csak néhány tagja van, lehetőleg a rendszergazdák közül. 
- Szinkronizálja az iOS-eszközt az Intune-nal. Regisztráljon, ha ezt még nem tette meg. 
- Próbáljon meg újból kapcsolódni ugyanahhoz a Wi-Fi-végponthoz (az első lépésben leírtak szerint).
- Bővítse ki a kört nagyobb csoportokra és végül mindenkire, aki a szervezetben várhatóan felhasználó lesz. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Mennyi időt vesz igénybe, hogy a mobileszközök megkapják a szabályzatot vagy az alkalmazásokat, amelyeket hozzájuk rendeltek?

Szabályzat vagy alkalmazás hozzárendelésekor az Intune azonnal értesíti az eszközt arról, hogy be kell jelentkeznie az Intune szolgáltatásba. Az értesítés általában öt percnél kevesebb időt vesz igénybe.

Ha egy eszköz nem jelentkezik be, hogy lekérje a házirendet az első értesítés után, az Intune három további kísérletet tesz. Egy kapcsolat nélküli eszköz, például ki van kapcsolva, vagy nem kapcsolódik hálózathoz, előfordulhat, hogy nem kapja meg az értesítéseket. Ebben az esetben az eszköz a következő ütemezett bejelentkezéskor szerzi és az Intune szolgáltatás, amely lekérdezi a szabályzat:

| Platform | A frissítés|
| --- | --- |
| iOS | 6 óránként |
| macOS | 6 óránként |
| Android | 8 óránként |
| Eszközként regisztrált Windows 10 számítógépek | 8 óránként |
| Windows Phone | 8 óránként |
| Windows 8.1 | 8 óránként |

Ha az eszköz nemrég lett regisztrálva, a bejelentkezés gyakrabban fusson:

| Platform | Gyakoriság |
| --- | --- |
| iOS | 6 órán át 15 perceként, majd 6 óránként |  
| Mac OS X | 6 órán át 15 perceként, majd 6 óránként | 
| Android | 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Windows Phone | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Eszközként regisztrált Windows-számítógépek | 30 percen át 3 percenként, majd 8 óránként | 

Bármikor a felhasználók nyissa meg a céges portál alkalmazást, és az eszköz szinkronizálása érdekében az profil frissítések azonnali ellenőrzésére.

Felhasználói affinitás nélküli eszközök esetén a utáni szinkronizálás gyakorisága regisztrációs is órától napi egy vagy több. Intune az eszköznek, hogy jelentkezzen be az Intune különböző időközönként kéréseket küld. Ezt azonban magának az eszköznek kell van. Az első regisztráció után az idő, mennyi időbe telik a bejelentkezés befejezéséhez az előre nem látható. Attól is függ az eszköz regisztrálása és a házirendek és a egy eszközhöz hozzárendelt profillal típusát. Miután regisztrálja az eszközt, és az összes kezdeti szabályzat alkalmazása, az eszköz általában keres új szabályzatokat 6-8 óránként.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Milyen műveletek hatására küld az Intune azonnal értesítést egy eszközre?

Eszközök Intune-ban jelentkeznek, amikor a bejelentkezésre, vagy az ütemezett bejelentkezéskor során értesítést kapnak. Ha egy eszközre vagy felhasználóra vonatkozik egy művelet, például a zárolás, PIN-kód alaphelyzetbe állítása, alkalmazás-hozzárendelés, profilt és a szabályzat-hozzárendelés, majd az Intune azonnal értesítést küld az eszköznek kell a frissítések fogadásához.

Az egyéb módosítások – például a kapcsolattartási adatok módosítása a céges portálon – nem indítják el az azonnali értesítések küldését az eszközök felé.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Ha ugyanazon felhasználóhoz vagy eszközhöz több szabályzat is hozzá van rendelve, honnan tudható, hogy mely beállítások lesznek alkalmazva?

Ha két vagy több szabályzatot rendel hozzá ugyanazon felhasználóhoz vagy eszközhöz, majd a beállítást, amely érvényes történik az egyes beállítások szintjén:

- Megfelelőségi házirend-beállítások mindig prioritást élveznek beállítások az eszközkonfigurációs profilban.

- Ha egy másik megfelelőségi szabályzatban egy beállítás a kiértékeli a megfelelőségi szabályzatot, majd a szigorúbb megfelelőségi beállítás lesz érvényes.

- Ha egy konfigurációs szabályzatbeállítás ütközik egy másik konfigurációs szabályzatbeállítással, az ütközés az Intune-ban jelenik meg. Ezeket az ütközéseket manuálisan kell feloldani.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Mi történik, ha ütközés van két alkalmazásvédelmi szabályzat között? Melyik érvényes az alkalmazásra?

Ütköző értékek az alkalmazásvédelmi szabályzat legkorlátozóbb beállításai *kivételével* a számbeviteli mezők, például a PIN-kódmegadási próbálkozások alaphelyzetbe állítása előtt. A számbeviteli mezők vannak beállítva azonos értékei létrehozható – MAM-szabályzatoknak a javasolt beállításokkal.

Ütközések fordulhat elő, ha két profil beállításai megegyeznek. Például előfordulhat, hogy a másolás/beillesztés beállításra két megegyező MAM-házirendet konfigurált. Ebben az esetben a másolás/beillesztés a legszigorúbb értékre lesz beállítva, a többi beállítás pedig a konfiguráltak szerint lesz alkalmazva.

A szabályzatot az alkalmazáshoz és érvénybe lép. Egy második érvénybe léptetett szabályzat. Ebben a forgatókönyvben az első házirend élvez elsőbbséget, és érvényben marad. A második szabályzatot jeleníti meg az ütközést. Ha mindkettő egyszerre is vonatkozik, ami azt jelenti, hogy nincs első szabályzat, majd mindkettő ütközést jelez. Minden ütközésnél a legszigorúbb beállítás lesz érvényes.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Mi történik, ha az egyéni iOS-házirendek ütköznek?

Az Intune nem értékeli a konfigurációs Apple-fájlok vagy az Open Mobile Alliance egységes erőforrás-azonosítóra (OMA-URI) vonatkozó egyéni szabályzatainak tartalmát. Csak kézbesítési mechanizmusként funkcionál.

Egyéni szabályzat hozzárendelése esetén győződjön meg arról, hogy a konfigurált beállítások nem ütköznek megfelelőségi, konfigurációs vagy más egyéni szabályzatokkal. Ha egyéni szabályzatot és annak beállításai ütköznek, majd a beállítások véletlenszerűen érvényesülnek.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Mi történik, ha egy profilt törölnek, vagy az már nem érvényes?

Amikor töröl egy profilt, vagy egy eszköz eltávolítása a csoportból, amelyen a profil, a profil és a beállítások törlődnek az eszközről leírtak szerint:

- Wi-Fi, VPN, tanúsítvány és e-mail-profilok: Ezek a profilok az összes támogatott regisztrált eszközről el lesznek távolítva.
- Minden más profiltípus esetén:  

  - **Windows és Android-eszközök**: Beállítások nem törlődnek az eszközről
  - **Windows Phone 8.1 rendszerű eszközök**: A következő beállítások törlődnek:  
  
    - Jelszó szükséges a mobileszközök feloldásához
    - Egyszerű jelszavak engedélyezése
    - Jelszó minimális hossza
    - Kötelező jelszótípus
    - Jelszó lejárata (nap)
    - Jelszóelőzmények megjegyzése
    - Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt
    - Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót
    - Kötelező jelszótípus – megadandó karakterek minimális száma
    - Kamera használatának engedélyezése
    - Mobileszköz titkosításának kötelezővé tétele
    - Cserélhető tároló használatának engedélyezése
    - Webböngésző használatának engedélyezése
    - Alkalmazástároló használatának engedélyezése
    - Képernyőfelvétel-készítés használatának engedélyezése
    - Földrajzi hely meghatározásának engedélyezése
    - Microsoft-fiók használatának engedélyezése
    - Másolás és beillesztés használatának engedélyezése
    - Wi-Fi alapú internetmegosztás használatának engedélyezése
    - Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése
    - Wi-Fi elérési pontok jelentéskészítésének engedélyezése
    - Összes adat törlésének engedélyezése
    - Bluetooth használatának engedélyezése
    - NFC használatának engedélyezése
    - Wi-Fi használatának engedélyezése

  - **iOS**: Az összes beállítás törlődik, kivéve:
  
    - Hangroaming engedélyezése
    - Adatroaming engedélyezése
    - Automatikus szinkronizálás engedélyezése roaming közben

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Módosítottam egy eszközkorlátozási profilt, de a módosítások még nem léptek érvénybe

Beállítása után, Windows Phone-eszközök nem engedélyezett biztonsági szabályzatok beállítása, hogy a beállításukat MDM vagy az EAS használatával. Például, ha beállítja egy **legalább hány karakterből álló jelszót** 8-ra. Próbálja meg 4-re csökkenteni. A szigorúbb profil már alkalmazva van az eszközön.

Ha módosítani szeretné a profil egy kevésbé biztonságos értékre, alaphelyzetbe kell állítania a biztonsági szabályzatok. Ha például a Windows 8.1, az asztalon, pöccintsen jobbról > Válasszon **beállítások** > **Vezérlőpult**. Válassza a **Felhasználói fiókok** kisalkalmazást. A bal oldali navigációs menü van egy **biztonsági házirendek mellőzése** (irányába alsó) hivatkozásra. Válassza ki ezt, majd a **Szabályzatok alaphelyzetbe állítása** lehetőséget.

Előfordulhat, hogy egyéb MDM-eszközöket, például Android, Windows Phone 8.1 és újabb verziók, iOS és Windows 10-es kell kell vonni, majd az Intune-ba való egy kevésbé korlátozó profil.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Egyes beállítások Windows 10-profilban adja vissza "Nem alkalmazható"

Egyes beállítások Windows 10 rendszerű eszközökön is állapotúként "Nem alkalmazható". Ha ez történik, beállítását, hogy a verzió vagy az eszközön futó Windows-kiadás nem támogatott. Ez az üzenet a következő okok miatt fordulhat elő:

- A beállítás csak a Windows újabb verziói, és nem a jelenlegi operációs rendszer (OS) az eszközön lévő verziója érhető el.
- A beállítás csak az adott Windows-kiadások és az adott esetében, például a kezdőlap, Professional, Enterprise és Education érhető el.

A verzió és a Termékváltozat vonatkozó követelményeket a különböző beállításokkal kapcsolatos további információkért tekintse meg a [konfigurációs szolgáltató (CSP) hivatkozás](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>További lépések

További segítségre van szüksége? Ismerje meg, [hogyan kérhet támogatást az Intune-hoz](get-support.md).

---
title: Eszközprofilok hibaelhárítása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: 'Eszközprofilokkal kapcsolatos gyakori problémák, például: A profilmódosítások nem jutnak érvényre egyes felhasználók vagy eszközök esetén. Mennyi ideig tart egy új szabályzatnak az eszközökre való leküldése? Mely szabályok érvényesülnek több szabályzat esetén? Mi történik egy profil törlésekor vagy eltávolításakor? Mindez és még sok más a Microsoft Intune-ról az Azure Portalon.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 32281ae37b7b36dfbf49503275a8a1e6c35d8f6d
ms.sourcegitcommit: 513c59a23ca5dfa80a3ba6fc84068503a4158757
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54210788"
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Eszközprofilokkal kapcsolatos gyakori problémák a Microsoft Intune-ban és azok megoldása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune-eszközprofilok használatával kapcsolatos gyakori hibák elhárítása.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Miért nem kap a felhasználó új profilt, amikor megváltoztatja a jelszót vagy a hozzáférési kódot egy létező Wi-Fi-profilban? 
Ön létrehoz egy vállalati Wi-Fi-profilt, hozzárendeli egy csoporthoz, megváltoztatja a jelszót, és menti a profilt. A profil megváltoztatásakor egyes felhasználók esetleg nem kapják meg az új profilt.

A probléma következményei vendég Wi-Fi beállításával mérsékelhetők. A vállalati Wi-Fi kiesése esetén a felhasználók a vendég Wi-Fi-hez kapcsolódhatnak. Gondoskodjon az automatikus csatlakozás beállításáról. A vendég Wi-Fi profilt rendelje hozzá minden felhasználóhoz.

Néhány további javaslat:  

- Mivel a Wi-Fi-hálózat, amelyhez csatlakozik, jelszót vagy hozzáférési kódot használ, gondoskodjon arról, hogy közvetlenül tud kapcsolódni a Wi-Fi-útválasztóhoz. Ezt kipróbálhatja egy iOS-eszközzel.
- A Wi-Fi-végponthoz (Wi-Fi-útválasztóhoz) való sikeres kapcsolódás után jegyezze fel az SSID-t és a használt hitelesítő adatokat (ez a jelszó vagy a hitelesítő kód).
- Adja meg az SSID-t és a hitelesítő adatokat (jelszót vagy hitelesítő kódot) az Előmegosztott kulcs mezőben. 
- Alkalmazza egy tesztcsoportra, amelynek csak néhány tagja van, lehetőleg a rendszergazdák közül. 
- Szinkronizálja az iOS-eszközt az Intune-nal. Regisztráljon, ha ezt még nem tette meg. 
- Próbáljon meg újból kapcsolódni ugyanahhoz a Wi-Fi-végponthoz (az első lépésben leírtak szerint).
- Bővítse ki a kört nagyobb csoportokra és végül mindenkire, aki a szervezetben várhatóan felhasználó lesz. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Mennyi időt vesz igénybe, hogy a mobileszközök megkapják a szabályzatot vagy az alkalmazásokat, amelyeket hozzájuk rendeltek?
Szabályzat vagy alkalmazás hozzárendelésekor az Intune azonnal értesíti az eszközt arról, hogy be kell jelentkeznie az Intune szolgáltatásba. Az értesítés általában öt percnél kevesebb időt vesz igénybe.

Ha az eszköz az első értesítés után nem jelentkezik be, hogy beszerezze a szabályzatot, az Intune három további kísérletet tesz. Ha az eszköz kapcsolat nélküli állapotban van (például ki van kapcsolva vagy nem kapcsolódik hálózathoz), előfordulhat, hogy nem kapja meg az értesítéseket. Ebben az esetben az eszköz az Intune szolgáltatásba való következő ütemezett bejelentkezéskor szerzi be a szabályzatot a következő módon:

- iOS és MacOS rendszeren: 6 óránként
- Android:: 8 óránként
- Windows Phone: 8 óránként
- Eszközként regisztrált Windows 8.1 és Windows 10-számítógépek: 8 óránként

Ha az eszköz nemrég lett regisztrálva, a bejelentkezés gyakoribb lesz, a következőképpen:

- iOS és MacOS rendszeren: 15 percenként az hat óra, majd 6 óránként
- Android:: 15 percen át 3 percenként, majd két órán át 15 percenként, majd 8 óránként
- Windows Phone: 15 percen át 5 percenként, majd két órán át 15 percenként, majd 8 óránként
- Eszközként regisztrált Windows-számítógépek: A 30 percesnek, majd 8 óránként percen át 3 percenként

A felhasználók a Céges portál alkalmazás megnyitásával bármikor jelentkezhetnek a szabályzat beszerzéséhez.

A felhasználói affinitás nélküli eszközök esetén a regisztráció utáni szinkronizálás gyakorisága néhány órától egy vagy több napig terjedhet. Az Intune különböző időközönként kéréseket küld az eszköznek, hogy jelentkezzen be a szolgáltatásba. Bejelentkeznie azonban magának az eszköznek kell. Az első regisztráció után az eszközregisztráció típusától és az eszközhöz rendelt szabályzatoktól és profiloktól függően változhat, hogy mennyi időbe telik a bejelentkezés elvégzése. Azonban az eszközregisztráció és az összes kezdeti szabályzat alkalmazása után az eszköz általában körülbelül 6 óránként keres új szabályzatokat.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Milyen műveletek hatására küld az Intune azonnal értesítést egy eszközre?
Az eszközök akkor jelentkeznek be az Intune-ba, amikor értesítést kapnak a bejelentkezésre, vagy a rendszeresen ütemezett alkalmakkor. Ha egy művelet, például a törlés, a zárolás, a jelszó alaphelyzetbe állítása, illetve az alkalmazás-, profil- vagy szabályzat-hozzárendelés egy eszközre vagy felhasználóra vonatkozik, az Intune azonnal értesíti az eszközt arról, hogy be kell jelentkeznie az Intune szolgáltatásba a frissítések fogadásához.

Az egyéb módosítások – például a kapcsolattartási adatok módosítása a céges portálon – nem indítják el az azonnali értesítések küldését az eszközök felé.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Ha ugyanazon felhasználóhoz vagy eszközhöz több szabályzat is hozzá van rendelve, honnan tudható, hogy mely beállítások lesznek alkalmazva?
Ha több szabályzatot rendel hozzá ugyanazon felhasználóhoz vagy eszközhöz, akkor az egyes beállítások szintjén dől el, hogy mely beállítások jutnak érvényre:

- A megfelelőségi házirend-beállítások mindig prioritást élveznek a konfigurációs házirend-beállításokkal szemben

- Ha egy beállítás több megfelelőségi szabályzatban is szerepel, akkor a legszigorúbb megfelelőségi beállítás lesz érvényes.

- Ha egy konfigurációs szabályzatbeállítás ütközik egy másik konfigurációs szabályzatbeállítással, az ütközés az Azure Portalon is megjelenik. Ebben a helyzetben az ütközést manuálisan kell feloldani.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Mi történik, ha ütközés van két alkalmazásvédelmi szabályzat között? Melyik érvényes az alkalmazásra?
Az ütközési értékek az alkalmazásvédelmi szabályzatok leginkább korlátozó beállításai, a számbeviteli mezők kivételével (ilyen például a PIN-kódmegadási próbálkozások száma az alaphelyzetbe állítás előtt). A számbeviteli mezők értékei megegyeznek a – javasolt beállításokkal a konzolban létrehozható – MAM-szabályzatok értékeivel.

Akkor történik ütközés, ha két profilbeállítás megegyezik. Például előfordulhat, hogy a másolás/beillesztés beállításra két megegyező MAM-házirendet konfigurált. Ebben az esetben a másolás/beillesztés beállítás a legszigorúbb értékre lesz állítva, a többi beállítás pedig a konfiguráltak szerint lesz megadva.

Ha az alkalmazáshoz hozzárendel egy profilt, és az érvénybe lép, majd egy másikat is hozzárendel, akkor az első elsőbbséget élvez és érvényben marad, a második pedig ütközést jelez. Ha egyszerre történik a hozzárendelésük, tehát nincsen korábbi profil, akkor mindkettő ütközést fog jelezni. Minden ütközésnél a legszigorúbb beállítás lesz érvényes.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Mi történik, ha az egyéni iOS-házirendek ütköznek?
Az Intune nem értékeli ki a konfigurációs Apple-fájlok vagy az Open Mobile Alliance egységes erőforrás-azonosítóra (OMA-URI) vonatkozó egyéni profilok tartalmát. Csak kézbesítési mechanizmusként funkcionál.

Egyéni profil hozzárendelésekor ellenőrizze, hogy a konfigurált beállítások nem ütköznek-e megfelelőségi, konfigurációs vagy más egyéni szabályzatokkal. Ha egy egyéni profilt és annak beállításai ütköznek, majd a beállítások véletlenszerűen érvényesülnek.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Mi történik, ha egy profilt törölnek, vagy az már nem érvényes?
Amikor töröl egy profilt, vagy eltávolít egy olyan eszközt a csoportból, amely a profilhoz tartozik, akkor a profil és a beállítások a következő listákban leírtaknak megfelelően lesznek eltávolítva az adott eszközről:

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

  - **iOS-es**: Az összes beállítás törlődik, kivéve:
  
    - Hangroaming engedélyezése
    - Adatroaming engedélyezése
    - Automatikus szinkronizálás engedélyezése roaming közben

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Módosítottam egy eszközkorlátozási profilt, de a módosítások még nem léptek érvénybe
A Windows Phone-telefonok nem teszik lehetővé, hogy a beállításukat követően a felhasználó alacsonyabb biztonsági értékeket konfiguráljon az MDM vagy az EAS használatával megadott biztonsági szabályzatokhoz. Ilyen eset például, ha beállítja a **jelszó minimális karakterszámát** 8-ra, majd megpróbálja 4-re csökkenteni. Az eszközhöz már a szigorúbb profil van hozzárendelve.

Ha egy kevésbé biztonságos értékre szeretné módosítani a profilt, alaphelyzetbe kell állítania a biztonsági szabályzatokat. Windows 8.1 rendszerben például pöccintsen jobbról, majd válassza a **Beállítások** > **Vezérlőpult** elemet. Válassza a **Felhasználói fiókok** kisalkalmazást. A bal oldali navigációs menü alján található egy **Biztonsági szabályzatok mellőzése** hivatkozás. Válassza ki ezt, majd a **Szabályzatok alaphelyzetbe állítása** lehetőséget.

Előfordulhat, hogy az egyéb, például Android, Windows Phone 8.1 vagy újabb, iOS és Windows 10 rendszerű MDM-eszközöket ki kell vonni, majd újból regisztrálni kell a szolgáltatásba egy kevésbé korlátozó profil hozzárendeléséhez.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Egyes beállítások Windows 10-profilban adja vissza "Nem alkalmazható"
Egyes beállítások Windows 10 rendszerű eszközökön is állapotúként "Nem alkalmazható". Ha ez történik, beállítását, hogy a verzió vagy az eszközön futó Windows-kiadás nem támogatott. Ez az üzenet a következő okok miatt fordulhat elő:

- A beállítás csak a Windows újabb verziói, és nem a jelenlegi operációs rendszer (OS) az eszközön lévő verziója érhető el.
- A beállítás csak az adott Windows-kiadások és az adott esetében, például a kezdőlap, Professional, Enterprise és Education érhető el.

A verzió és a Termékváltozat vonatkozó követelményeket a különböző beállításokkal kapcsolatos további információkért tekintse meg a [konfigurációs szolgáltató (CSP) hivatkozás](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>További lépések
További segítségre van szüksége? Ismerje meg, [hogyan kérhet támogatást az Intune-hoz](get-support.md).

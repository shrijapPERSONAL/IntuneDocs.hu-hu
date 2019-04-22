---
title: macOS beállításai a Microsoft Intune – Azure |} A Microsoft Docs
titleSuffix: ''
description: Adja hozzá, adja meg, vagy létrehozása beállítások macOS-eszközökre korlátozhatja a funkciókat, beleértve a jelszókövetelmények beállítása, szabályozhatja a zárolási képernyő, használja a beépített alkalmazások, korlátozott vagy jóváhagyott alkalmazások hozzáadása, bluetooth-eszközök kezeléséhez, csatlakoztatása a felhőhöz, a biztonsági mentéshez és a tárolási, teljes képernyős mód engedélyezése, tartományokkal és vezérelheti a felhasználók hogyan használják a Safari böngészővel a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5feec66e791da4038bd069cdad69a7ba573f27f3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897051"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>engedélyezi, vagy korlátozhatja a funkciókat az Intune-nal macOS beállításai

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és macOS-eszközökön vezérelheti a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használatával ezek a beállítások lehetővé teszik vagy szolgáltatásokat tilthat le, jelszószabályok beállítása, engedélyezése vagy korlátozása egyedi alkalmazások és más.

Ezek a beállítások hozzá egy eszközkonfigurációs profilt az Intune-ban, és ezután hozzárendelt vagy a macOS-eszközökre telepített.

## <a name="before-you-begin"></a>Előkészületek

[Hozzon létre egy eszközkorlátozási profilt konfigurációs](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Általános

- **Keresésének letiltása**: **Blokk** megakadályozza, hogy a felhasználó általi kiemelve egy szót, és ezután keresése az eszközön a meghatározását. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a definíció keresési szolgáltatáshoz való hozzáférést.
- **Diktálás letiltása**: **Blokk** megakadályozza a felhasználó szóbeli bemeneti szöveg beírásához. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a felhasználó diktálással történő bevitel használja.
- **Letiltja a tartalom gyorsítótárazása**: Válasszon **nincs konfigurálva** tartalom gyorsítótárazásának engedélyezése (alapértelmezett). Tartalom gyorsítótárazása az alkalmazásadatok, webes böngésző adatokat, letöltések és további helyileg, az eszközön tárolja. Válassza ki **blokk** megakadályozza, hogy ezek az adatok tárolása a gyorsítótárban.

  A tartalom gyorsítótárazása macOS rendszeren további információkért lásd: [kezelni a tartalom gyorsítótárazása Mac gépen](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (megnyílik egy másik webhely).

  Ez a funkció az alábbiakra vonatkozik:  
  - macOS 10.13 és újabb verziók

- **Késlelteti a szoftverfrissítéseket**: Ha a beállítása **nincs konfigurálva** (alapértelmezett), szoftverfrissítések jelennek meg az eszközön, az Apple által kiadott. Például ha egy macOS-frissítést lekérdezi elérhető az Apple által egy adott dátumon, majd a frissítési természetes módon megjelenik-e az eszközön a Megjelenés dátumához körül. Kezdőérték build frissítések engedélyezettek késedelem nélkül.

  **Engedélyezése** lehetővé teszi, hogy amikor a szoftverfrissítések jelennek meg az eszközökön, a 0 – 90 nappal késleltetés. Ez a beállítás nem szabályozza, amikor a frissítések vannak, vagy nincsenek telepítve. 

  - **Látható-e szoftverfrissítéseket késleltetés**: Adjon meg egy 0-90 nap közötti értéket. Amikor a késleltetés lejár, a felhasználók frissíteni az operációs rendszer legkorábbi verziójára, ha a késleltetés lett elindítva értesítést kaphat.

    Például, ha egy macOS-frissítés érhető el **január 1-től**, és **látható-e késleltetni** értékre van állítva **5 nap**, majd a frissítés nem eszközökön elérhető frissítésként jelenik meg. Az a **hatodik nap** , hogy a frissítés érhető el, és a végfelhasználók telepíthetik a kiadásban a következő.

    Ez a funkció az alábbiakra vonatkozik:  
    - macOS 10.13.4 és újabb verziók

## <a name="password"></a>Windows 10

- **Jelszó**: **Szükséges** a végfelhasználó számára adjon meg egy jelszót az eszköz elérésére. **Nincs konfigurálva** (alapértelmezett) nincs szükség a jelszó, és nem kényszerített korlátozásokat, például az egyszerű jelszavak blokkolása vagy beállítás minimális hosszát.
  - **Kötelező jelszótípus**: Adja meg, hogy a jelszó is csak numerikus lehet, vagy hogy Alfanumerikusnak kell lennie (betűket és számokat tartalmazhat). Ezt a beállítást csak a Mac OS X 10.10.3-as és újabb verziói támogatják.
  - **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg a jelszóban használandó speciális karakterek minimális számát (**0** - **4**).<br>A speciális karakterek olyan szimbólumok, mint például a „**?**”.
  - **Jelszó minimális hossza**: Adja meg a felhasználó beállítandó jelszó minimális hosszát (közötti **4** és **16** karakter).
  - **Egyszerű jelszavak**: Az egyszerű jelszavak (például a **0000**vagy az**1234**) használatának engedélyezése.
  - **Jelszó kérése ennyi képernyőzárolás után legfeljebb ennyi perc**: Adja meg, hogy mennyi ideig legyen a számítógép inaktív ahhoz, hogy bekapcsoljon a jelszavas zárolás.
  - **Ennyi perc inaktivitás képernyőzárolás**: Adja meg az, hogy mennyi ideig legyen a számítógép üresjáratban a képernyő zárolása előtt.
  - **Jelszó érvényessége (napokban)**: Adja meg, hogy hány nap telhet el a kötelező jelszómódosításig (**1** **255** nap).
  - **Korábbi jelszavak újbóli használatának tiltása**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható fel újra, a **1** való **24**.

- **Megakadályozza a felhasználó PIN-kód módosítása**: Válasszon **blokk** a PIN-kód módosításának, hozzáadva vagy eltávolítva billentyűkombinációt. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a PIN-kódok hozzáadni, módosítani vagy eltávolítani.
- **Ujjlenyomattal történő Zárolásfeloldás letiltása**: Válasszon **blokk** az eszközzárolás ujjlenyomattal történő elkerülése érdekében. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a felhasználó számára az eszközzárolás ujjlenyomattal történő használatával.

- **Automatikus kitöltés letiltása jelszó**: Válasszon **blokk** , hogy az automatikus kitöltés jelszavak funkció használatával a MacOS-gépeken. Választás **blokk** is az az alábbi hatással van:

  - Felhasználók sem kapnak felszólítást a mentett jelszó használata a Safari vagy az alkalmazások.
  - Automatikus erős jelszavak le vannak tiltva, és erős jelszavakat nem javasolt a felhasználók számára.

  **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy ezeket a funkciókat.

- **Jelszó közelségi-kérések blokkolása**: Válasszon **blokk** , a felhasználó-eszköz nem jelszavakat kérhet közelben lévő eszközökhöz. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a jelszó forrásától.

- **Jelszó adatmegosztás blokkolására**: **Blokk** megakadályozza, hogy a jelszavak használatával AirDrop eszközök közötti megosztását. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a jelszavak megoszthatók.

## <a name="built-in-apps"></a>Beépített alkalmazások

- **Safari böngésző automatikus kitöltés letiltása**: **Blokk** letiltja az automatikus kitöltés funkciót az eszközön a Safariban. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.
- **Kamera letiltása**: Válasszon **blokk** kívánja tagadni a hozzáférést az eszközön a kamera. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy az eszköz kamerájához való hozzáférést.
- **Az Apple Music letiltása**: **Blokk** klasszikus módra a Music alkalmazás visszaáll, és letiltja a Music szolgáltatást. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy az Apple Music alkalmazás használatával.
- **Letiltása a Spotlight internetes keresési eredmények**: **Blokk** reflektorfény leállítja az eredményt visszatérésre egy internetes keresés. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, hogy adja meg a keresési eredmények.
- **Blokk fájlátviteli iTunes használatával**: **Blokk** letiltja az alkalmazás fájlmegosztási szolgáltatásokat. Elérhető a macOS 10.13 és újabb verziók. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy az alkalmazás fájlmegosztási szolgáltatásokat.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

- A **tiltott alkalmazások** lista: Az Intune-ban, hogy a felhasználók nem telepíthetnek és futtathatnak által nem kezelt alkalmazások listája. Felhasználók tiltott alkalmazásokat telepítsenek nem akadályozza meg, de ilyen esetben a rendszergazda jelentett.
- Egy **jóváhagyott alkalmazások** lista: Azokat az alkalmazásokat listázza, amelyek telepítése engedélyezett a felhasználók számára. Felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem jelennek meg. Az Intune által kezelt alkalmazások automatikusan engedélyezettek. Felhasználó egy alkalmazást, amely nem szerepel az engedélyezési listán nem akadályozza. De ha igen, a rendszergazda számára jelentett.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet, igény szerint az alkalmazás kiadóját, valamint az alkalmazás csomagazonosítóját (például *com.apple.calculator*).

## <a name="connected-devices"></a>Csatlakoztatott eszközök

- **AirDrop tiltása**: **Blokk** megakadályozza, hogy az eszközön található AirDrop használatával. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a közeli eszközökkel az AirDrop funkció használatával.
- **Apple Watch automatikus letiltása feloldásához**: **Blokk** megakadályozza, hogy a felhasználók macOS-eszközeiket az Apple Watch-zárolás feloldásához. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a macOS-eszközeiket az Apple Watch-feloldását a felhasználóknak.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Icloud-alapú kulcslánc-szinkronizálás letiltása**: Válasszon **blokk** tárolt meg a Kulcsláncban Icloudba történő szinkronizálása folyamatban hitelesítő letiltása. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a felhasználók ezeket a hitelesítő adatokat szinkronizálni.
- **Dokumentumok icloudba szinkronizálásának letiltása**: **Blokk** megakadályozza, hogy a iCloud dokumentumok és adatok szinkronizálását. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére.
- **ICloud biztonsági másolata letiltása**: **Blokk** icloud-alapú megakadályozza, hogy a macOS-Mail alkalmazásban történő szinkronizálásának engedélyezése. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a Mail szinkronizálási az icloud szolgáltatásba.
- **Icloud-alapú ügyfél biztonsági mentés letiltása**: **Blokk** icloud-alapú megakadályozza, hogy az eszközök névjegyek szinkronizálása. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy az adatokat az iCloud segítségével névjegy-szinkronizálás.
- **Icloud-alapú naptár biztonsági mentés letiltása**: **Blokk** icloud-alapú megakadályozza, hogy a macOS-naptár app történő szinkronizálásának engedélyezése. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a naptár szinkronizálását az icloud szolgáltatásba.
- **Icloud-alapú emlékeztető biztonsági mentés letiltása**: **Blokk** icloud-alapú megakadályozza, hogy a macOS emlékeztetők app történő szinkronizálásának engedélyezése. **Nincs konfigurálva** (alapértelmezett) emlékeztetők szinkronizálásának Icloudba történő szinkronizálásának engedélyezése.
- **Icloud-alapú könyvjelző biztonsági mentés letiltása**: **Blokk** icloud-alapú megakadályozza, hogy az eszközök a könyvjelzők szinkronizálása. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a könyvjelző szinkronizálási az icloud szolgáltatásba.
- **Icloud-alapú megjegyzések biztonsági mentés letiltása**: **Blokk** icloud-alapú megakadályozza, hogy az eszközök Megjegyzések szinkronizálása. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a feljegyzések szinkronizálását az icloud szolgáltatásba.

## <a name="domains"></a>Tartományok

- **E-mail-tartomány URL-címe**: Egy vagy több URL-címek hozzáadása a listához. Ha a felhasználó nem a konfigurált tartományok egyikéből kap e-mailt, a MacOS-es Mail alkalmazásban ez az e-mail nem megbízhatóként jelenik meg.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Korlátozhatja is eszközök funkcióinak és beállításainak a [iOS](device-restrictions-ios.md) eszközök.

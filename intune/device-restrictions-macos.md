---
title: macOS beállításai a Microsoft Intune – Azure |} A Microsoft Docs
titlesuffix: ''
description: Hozzáadása, konfigurálása és létrehozása a beállítások macOS-eszközökre korlátozhatja a funkciókat, beleértve a jelszókövetelmények beállítása, szabályozhatja a zárolási képernyő, használja a beépített alkalmazások, korlátozott vagy jóváhagyott alkalmazások hozzáadása, a Bluetooth-eszközök kezeléséhez, csatlakoztatása a felhőhöz, biztonsági mentése és tárolási, teljes képernyős mód engedélyezése, tartományokkal és vezérelheti a felhasználók hogyan használják a Safari böngészővel a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 190facae36127a15f6df9f5fecfec9332ca06670
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742312"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>engedélyezi, vagy korlátozhatja a funkciókat az Intune-nal macOS beállításai

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és macOS-eszközökön vezérelheti a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használatával ezek a beállítások lehetővé teszik vagy szolgáltatásokat tilthat le, jelszószabályok beállítása, engedélyezése vagy korlátozása egyedi alkalmazások és más.

Ezek a beállítások hozzá egy eszközkonfigurációs profilt az Intune-ban, és ezután hozzárendelt vagy a macOS-eszközökre telepített.

## <a name="before-you-begin"></a>Előkészületek

[Hozzon létre egy eszközkorlátozási profilt konfigurációs](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Általános

- **Letiltja a tartalom gyorsítótárazása**: Válasszon **nincs konfigurálva** tartalom gyorsítótárazásának engedélyezése (alapértelmezett). Tartalom gyorsítótárazása az alkalmazásadatok, webes böngésző adatokat, letöltések és további helyileg, az eszközön tárolja. Válassza ki **blokk** megakadályozza, hogy ezek az adatok tárolása a gyorsítótárban.

  A tartalom gyorsítótárazása macOS rendszeren további információkért lásd: [kezelni a tartalom gyorsítótárazása Mac gépen](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (megnyílik egy másik webhely).

  Ez a funkció az alábbiakra vonatkozik:  
  - macOS 10.13 és újabb verziók

- **Késlelteti a szoftverfrissítéseket (csak felügyelt)**: Ha a beállítása **nincs konfigurálva** (alapértelmezett), szoftverfrissítések jelennek meg az eszközön, az Apple által kiadott. Például ha egy macOS-frissítést lekérdezi elérhető az Apple által egy adott dátumon, majd a frissítési természetes módon megjelenik-e az eszközön a Megjelenés dátumához körül.

  **Engedélyezése** lehetővé teszi, hogy amikor a szoftverfrissítések jelennek meg az eszközökön, a 0 – 90 nappal késleltetés. Ez a beállítás nem szabályozza, amikor a frissítések vannak, vagy nincsenek telepítve. 

  - **Látható-e szoftverfrissítéseket késleltetés**: Adjon meg egy 0-90 nap közötti értéket. Amikor a késleltetés lejár, a felhasználók frissíteni az operációs rendszer legkorábbi verziójára, ha a késleltetés lett elindítva értesítést kaphat.

    Például, ha egy macOS-frissítés érhető el **január 1-től**, és **látható-e késleltetni** értékre van állítva **5 nap**, majd a frissítés nem eszközökön elérhető frissítésként jelenik meg. Az a **hatodik nap** , hogy a frissítés érhető el, és a végfelhasználók telepíthetik a kiadásban a következő.

    Ez a funkció az alábbiakra vonatkozik:  
    - macOS 10.13.4 és újabb verziók

## <a name="password"></a>Windows 10

- **Jelszó**: Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
  - **Kötelező jelszótípus**: Adja meg, hogy a jelszó is csak numerikus lehet, vagy hogy Alfanumerikusnak kell lennie (betűket és számokat tartalmazhat). Ezt a beállítást csak a Mac OS X 10.10.3-as és újabb verziói támogatják.
  - **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg a jelszóban használandó speciális karakterek minimális számát (**0** - **4**).<br>A speciális karakterek olyan szimbólumok, mint például a „**?**”.
  - **Jelszó minimális hossza**: Adja meg a felhasználó beállítandó jelszó minimális hosszát (közötti **4** és **16** karakter).
  - **Egyszerű jelszavak**: Az egyszerű jelszavak (például a **0000**vagy az**1234**) használatának engedélyezése.
  - **Jelszó kérése ennyi képernyőzárolás után legfeljebb ennyi perc**: Adja meg, hogy mennyi ideig legyen a számítógép inaktív ahhoz, hogy bekapcsoljon a jelszavas zárolás.
  - **Ennyi perc inaktivitás képernyőzárolás**: Adja meg az, hogy mennyi ideig legyen a számítógép üresjáratban a képernyő zárolása előtt.
  - **Jelszó érvényessége (napokban)**: Adja meg, hogy hány nap telhet el a kötelező jelszómódosításig (**1** **255** nap).
  - **Korábbi jelszavak újbóli használatának tiltása**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható fel újra, a **1** való **24**.

- **Automatikus kitöltés letiltása jelszó**: Válasszon **blokk** , hogy az automatikus kitöltés jelszavak funkció használatával a MacOS-gépeken. Választás **blokk** is az az alábbi hatással van:

  - Felhasználók sem kapnak felszólítást a mentett jelszó használata a Safari vagy az alkalmazások.
  - Automatikus erős jelszavak le vannak tiltva, és erős jelszavakat nem javasolt a felhasználók számára.

  **Nincs konfigurálva** lehetővé teszi, hogy ezeket a funkciókat.

- **Jelszó közelségi-kérések blokkolása**: Válasszon **blokk** , a felhasználó-eszköz nem jelszavakat kérhet közelben lévő eszközökhöz. **Nincs konfigurálva** lehetővé teszi, hogy a jelszó forrásától.

- **Jelszó adatmegosztás blokkolására**: **Blokk** megakadályozza, hogy a jelszavak használatával AirDrop eszközök közötti megosztását. **Nincs konfigurálva** lehetővé teszi a jelszavak megoszthatók.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

- A **tiltott alkalmazások** lista: Az Intune-ban, hogy a felhasználók nem telepíthetnek és futtathatnak által nem kezelt alkalmazások listája. Felhasználók tiltott alkalmazásokat telepítsenek nem akadályozza meg, de ilyen esetben a rendszergazda jelentett.
- Egy **jóváhagyott alkalmazások** lista: Azokat az alkalmazásokat listázza, amelyek telepítése engedélyezett a felhasználók számára. Felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem jelennek meg. Az Intune által kezelt alkalmazások automatikusan engedélyezettek. Felhasználó egy alkalmazást, amely nem szerepel az engedélyezési listán nem akadályozza. De ha igen, a rendszergazda számára jelentett.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet, igény szerint az alkalmazás kiadóját, valamint az alkalmazás csomagazonosítóját (például *com.apple.calculator*).

## <a name="domains"></a>Tartományok

### <a name="unmarked-email-domains"></a>Jelöletlen e-mail-tartományok

Az **E-mail-tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. Ha a felhasználó nem a konfigurált tartományok egyikéből kap e-mailt, a MacOS-es Mail alkalmazásban ez az e-mail nem megbízhatóként jelenik meg.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Korlátozhatja is eszközök funkcióinak és beállításainak a [iOS](device-restrictions-ios.md) eszközök.
---
title: Adja hozzá az iOS eszközkorlátozásokra vonatkozó beállításait a Microsoft Intune – Azure |} A Microsoft Docs
titleSuffix: ''
description: Adja hozzá, konfigurálása, vagy az iOS-eszközök jelszó állíthatnak be, szabályozhatja a zárolási képernyő, használja a beépített alkalmazások, korlátozott vagy jóváhagyott alkalmazások hozzáadása, bluetooth-eszközök kezeléséhez, csatlakoztatása a felhőhöz, biztonsági mentése és a storage-beállítások létrehozása, teljes képernyős mód engedélyezése, adja hozzá a tartományok, és szabályozhatja, hogy a felhasználók hogyan használják a Safari böngészővel a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a677742c5d2f876c0714f13c4f62d059ced98584
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728973"
---
# <a name="ios-device-restrictions-settings-list-in-microsoft-intune"></a>iOS-es eszközök korlátozások beállítások listája a Microsoft Intune-ban

Ez a cikk és az összes a eszközkorlátozásokra vonatkozó beállítások iOS-eszközökön konfigurálható ismerteti. Ezek a beállítások hozzá eszközkonfigurációs profil, és ezután hozzárendelt vagy telepített iOS-eszközök Microsoft Intune-nal.

## <a name="general"></a>Általános

- **Használati adatok megosztása**: válasszon **blokk** megakadályozza, hogy az eszköz diagnosztikai és használati adatok küldése az Apple-nek. **Nincs konfigurálva** lehetővé teszi, hogy ezeket az adatokat küldeni.
  - **Diagnosztikai adatok küldésének**: **blokk** e funkció felhasználó általi a diagnosztikai adatküldési és alkalmazáselemzési beállítások módosításának **diagnosztikai és használati** (eszköz beállításai). Használja ezt a beállítást, az eszköz felügyelt módban (IOS-es 9.3.2+) kell lennie. **Nincs konfigurálva** lehetővé teszi a felhasználó ezen eszköz beállításainak módosítására.
- **Képernyőfelvétel**: válasszon **blokk** képernyőképek megelőzése, illetve a képernyőfelvétel-készítés, az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
  - **Távoli képernyőfigyelés az osztályterem alkalmazással (csak felügyelt)**: válasszon **blokk** , hogy az osztályterem alkalmazás képernyőjét távolról az eszközön. Használja ezt a beállítást, az eszköz felügyelt módban (iOS 9.3 és újabb) kell lennie. **Nincs konfigurálva** lehetővé teszi, hogy az Apple osztályterem alkalmazás megtekintése a képernyő.
  - **Rákérdezés nélküli képernyőfigyelés az osztályterem alkalmazással (csak felügyelt)**: Ha beállítása **engedélyezése**, az oktatók csendes figyelheti a diákok tudta nélkül az osztályterem alkalmazás használatával a diákok iOS-eszközök a képernyő. Tanulói eszközökhöz regisztráltak egy az osztályterem alkalmazás használatával automatikusan engedélyezik a tanfolyam oktatójának, engedélyt. **Nincs konfigurálva** megakadályozza, hogy ez a funkció.
- **Nem megbízható TLS-tanúsítványok**: válasszon **blokk** , hogy a nem megbízható Transport Layer Security (TLS) tanúsítványok, az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a TLS-tanúsítványokkal.
- **Megbízható nagyvállalati alkalmazás**: válasszon **blokk** eltávolítása a **megbízható nagyvállalati fejlesztő** gombot a beállítások > Általános > profilok és Eszközfelügyelet az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó dönt, hogy megbízható alkalmazásokat, amelyeket nem az alkalmazásáruházból letöltött.
- **Fiókmódosítás (csak felügyelt)**: Ha a beállítása **blokk**, a felhasználó nem tudja frissíteni az iOS beállításkezelő alkalmazását az eszközre vonatkozó beállításokat. Például a felhasználó nem lehet új eszközfiókok létrehozása, vagy módosítsa a felhasználónév vagy jelszó. **Nincs konfigurálva** lehetővé teszi a felhasználók a beállítások módosításához.
  Ez a funkció is, például a levelezés, névjegyek, naptár, Twitter és egyéb az iOS beállításkezelő alkalmazásából elérhető beállítások vonatkozik. Ez a funkció nem vonatkozik a fiók beállításait, amelyek nem konfigurálhatók, például a Microsoft Outlook alkalmazást az iOS beállításkezelő alkalmazásából származó alkalmazásokat.
- **Korlátozások engedélyezése az eszköz között (csak felügyelt)**: válasszon **blokk** megakadályozza, hogy a felhasználók korlátozások engedélyezése az eszköz között. **Nincs konfigurálva** lehetővé teszi a felhasználó eszközkorlátozásokat (szülői felügyeletet) mint például az eszköz konfigurálásához.
- **Az eszközön (csak felügyelt eszköz esetén) az összes tartalmat és beállítást beállítás törlésére szolgáló funkció használata**: válassza a **letiltása** így a felhasználók nem használhatják a törlése minden tartalmat és a beállítás az eszközön (csak felügyelt eszköz esetén). **Nincs konfigurálva** ezeket a beállításokat felhasználók számára hozzáférést biztosít.
- **Eszköz nevének módosítása (csak felügyelt)**: válasszon **blokk** , az eszköz neve nem lehet módosítani. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó megváltoztassa az eszköz nevét.
- **Értesítési beállítások módosítása (csak felügyelt)**: válasszon **blokk** , az értesítési beállítások nem módosíthatók. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó megváltoztassa az eszköz értesítési beállításait.
- **Háttérkép módosítása (csak felügyelt)**: **blokk** megakadályozza, hogy a háttérkép módosításának. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó módosíthatja az az eszköz háttérképét.
- **Vállalati alkalmazások megbízhatósági beállításai módosításának (csak felügyelt)**: **blokk** e funkció felhasználó általi módosításának a felügyelt eszközökön a vállalati alkalmazások megbízhatósági beállításai. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználót, hogy megbízható alkalmazásokat, amelyeket nem az alkalmazásáruházból letöltött.
- **Konfigurációs profil módosítása (csak felügyelt)**: **blokk** megakadályozza, hogy a konfigurációs profil módosítása az eszközön. **Nincs konfigurálva** lehetővé teszi a felhasználó számára a konfigurációs profilok telepítését.
- **Az aktiválási zár (csak felügyelt)**: válasszon **engedélyezése** az aktiválási zár engedélyezése felügyelt iOS-eszközökön. Az aktiválási zár megnehezíti az elveszett vagy ellopott eszközök újraaktiválását.
- **Letiltása (csak felügyelt) alkalmazás eltávolítása**: válasszon **blokk** megakadályozza, hogy a felhasználók alkalmazások eltávolítása. **Nincs konfigurálva** lehetővé teszi a felhasználóknak alkalmazások eltávolítása az eszközről.
- **Blokkok USB korlátozott módban (csak felügyelt)**: válasszon **blokk** letiltása USB korlátozott módban a felügyelt eszközökön. USB korlátozott módban blokkolja USB Kellékek származó adatok cseréje a olyan eszköz, amely egy óráig zárolva van. **Nincs konfigurálva** USB korlátozott mód lehetővé teszi.
- **Az automatikus dátum és idő (csak felügyelt) kényszerítése**: **megkövetelése** kényszeríti a felügyelt eszközök számára, hogy a dátum és idő beállítása automatikusan. Az eszköz időzónája szerint frissül, amikor az eszköz mobilhálózati kapcsolattal rendelkezik, vagy engedélyezve van a Wi-Fi, a helyalapú szolgáltatásokat.
- **Diákok háromnapos helyszíni tanfolyam (csak felügyelt eszköz esetén), hogy kérjen engedélyt igényel**: **megkövetelése** arra kényszeríti az oktatói kérjen engedélyt az osztályterem alkalmazás használatával, hogy egy nem felügyelt tanfolyam-ban regisztrált tanulók a tanfolyam. Csak az iOS 11.3 + érhető el. **Nincs konfigurálva** nem kényszeríti a kérjen engedélyt a tanulói.
- **Lehetővé teszi a nyilvános kulcsokra épülő infrastruktúra vezeték nélküli frissítések**: **engedélyezése** lehetővé teszi, hogy a felhasználók számára, anélkül, hogy egy számítógép csatlakozna az eszközeik szoftverfrissítéseket fogadni.
- **Követési korlát ad**: válasszon **korlát** letiltása az eszköz hirdetési azonosító. **Nincs konfigurálva** tartja azt engedélyezve van.
- **Blokk VPN létrehozása (csak felügyelt)**: **blokk** megakadályozza, hogy a felhasználók létrehozása a VPN-konfigurációs beállítások. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók használhassanak VPN-eket az eszközön.

## <a name="configurations-requiring-supervision"></a>Felügyeletet igénylő konfigurációk

Az iOS Supervised (Felügyelt) módja csak a kezdeti eszközbeállítás során, az Apple Készülékregisztrációs programján keresztül vagy az Apple Configuratorral engedélyezhető. A Supervised (Felügyelt) mód engedélyezése után az Intune az alábbi funkciókkal konfigurálhatja az eszközöket:

- App Lock (Egyetlen alkalmazás mód) 
- Globális HTTP-Proxy 
- Aktiválási zár megkerülése 
- Önálló egyetlen alkalmazás mód 
- Webtartalomszűrő 
- Háttér és zárolási képernyő beállítása 
- Felhasználói beavatkozás nélküli alkalmazástelepítés 
- Mindig bekapcsolt VPN 
- Kizárólag felügyelt alkalmazások telepítésének engedélyezése 
- iBookstore 
- iMessages 
- Game Center 
- Airdrop 
- AirPlay 
- Párosítás gazdagéppel 
- Felhőalapú szinkronizálás 
- Spotlight-keresés 
- Handoff 
- Eszköz törlése 
- Korlátozások felhasználói felülete 
- Konfigurációs profilok telepítése a felhasználói felület használatával 
- Hírek 
- Billentyűparancsok 
- PIN-kód módosítása 
- Eszköznév módosítása 
- Alkalmazások automatikus letöltése 
- Vállalati alkalmazások megbízhatóságának módosítása 
- Apple Music 
- Mail Drop 
- Párosítás Apple Watch órával 

> [!NOTE]
> Az Apple megerősítette, hogy bizonyos beállítások 2019-ben át fognak kerülni a kizárólag felügyelt módban használhatók közé. Mérlegelje ezt, ha az alábbi beállításokat azelőtt használja, mielőtt a kapcsolódó funkciókat az Apple áthelyezi a kizárólag felügyelt módban használhatók közé:
> - Végfelhasználók által végzett alkalmazástelepítés
> - Alkalmazás eltávolítása
> - FaceTime
> - Safari
> - iTunes
> - Durva tartalom
> - iCloud dokumentumok és adatok
> - Több résztvevős játék
> - Game Centerbeli barátok hozzáadása
> - Siri

## <a name="password"></a>Jelszó

- **Jelszó**: megköveteli a végfelhasználótól, adjon meg egy jelszót az eszköz elérésére. Nincs konfigurálva lehetővé teszi a felhasználóknak az eszköz elérésére anélkül, hogy jelszót írna be.
  - **Egyszerű jelszavak**: válasszon **blokk** , amelyek összetett jelszót. **Nincs konfigurálva** lehetővé teszi egyszerű jelszavak, mint `0000` és `1234`.
  - **Kötelező jelszótípus**: válassza ki a jelszó megkövetelése a szervezet. A választható lehetőségek:
    - **Eszköz alapértelmezése**
    - **numerikus**
    - **Alfanumerikus karakterek**
  - **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg, hány szimbólumnak, például `#` vagy `@`, kell szerepelnie a jelszóban.
  - **Jelszó minimális hossza**: írja be a minimális hosszát, a felhasználónak meg kell adnia, (4 és 14 karakter között).
  - **Bejelentkezési hibák eszköz törlése előtt**: Itt adhatja meg, mielőtt a rendszer törölné az eszközt (között 1 – 11.) a sikertelen bejelentkezéseket.
  - **Jelszó kérése ennyi képernyőzárolás után legfeljebb ennyi perc**<sup>1</sup>: Adja meg, mennyi ideig az eszköz marad tétlen, mielőtt a felhasználónak újra meg kell adnia a jelszavát. Ha az idő hossza meghaladja a beállított az eszközön, majd az eszköz figyelmen kívül hagyja a az idő. Az iOS 8.0 és újabb eszközökön támogatott.
  - **Ennyi perc inaktivitás képernyőzárolás**<sup>1</sup>: ennyi perc inaktivitás az eszközön a képernyőzárolás engedélyezett maximális számát adja meg. Ha az idő hossza meghaladja a beállított az eszközön, majd az eszköz figyelmen kívül hagyja a az idő.
  - **Jelszó érvényessége (napokban)**: Adja meg, hány nap elteltével kell megváltoztatni az eszköz jelszavát.
  - **Korábbi jelszavak újbóli használatának tiltása**: Adja meg az új jelszót kell lennie egy lehessen.
  - **Ujjlenyomattal történő Zárolásfeloldás**: válasszon **blokk** az eszközzárolás ujjlenyomattal történő elkerülése érdekében. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó számára az eszközzárolás ujjlenyomattal történő használatával.
- **PIN-kód módosítása (csak felügyelt)**: válasszon **blokk** a PIN-kód módosításának, hozzáadva vagy eltávolítva billentyűkombinációt. PIN-kód korlátozások módosításai figyelmen kívül hagyja a felügyelt eszközökön ez a funkció letiltása után. **Nincs konfigurálva** lehetővé teszi, hogy a PIN-kódok hozzáadni, módosítani vagy eltávolítani.
  - **Ujjlenyomat módosítása (csak felügyelt)**: **blokk** megakadályozza a felhasználó módosítja, hozzáadja vagy eltávolítsa a TouchID-ujjlenyomatokat. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó frissítése a TouchID-ujjlenyomatokat az eszközön.
- **Blokk jelszó automatikus kitöltés (csak felügyelt)**: válasszon **blokk** , hogy az automatikus kitöltés jelszavak funkció használatával iOS rendszeren. Választás **blokk** is a következőket:
  - Felhasználók sem kapnak felszólítást a mentett jelszó használata a Safari vagy az alkalmazások.
  - Automatikus erős jelszavak le vannak tiltva, és erős jelszavakat nem javasolt a felhasználók számára.

  **Nincs konfigurálva** lehetővé teszi, hogy ezeket a funkciókat.

- **(Csak felügyelt) jelszó közelségi-kérések blokkolása**: válasszon **letiltása** , a felhasználó-eszköz nem jelszavakat kérhet közelben lévő eszközökhöz. **Nincs konfigurálva** lehetővé teszi, hogy a jelszó forrásától.
- **Jelszó megosztása (csak felügyelt) letiltása**: **letiltása** megakadályozza, hogy a jelszavak használatával AirDrop eszközök közötti megosztását. **Nincs konfigurálva** lehetővé teszi a jelszavak megoszthatók.

<sup>1</sup>konfigurálása során a **legfeljebb ennyi perc inaktivitás képernyőzárolás** és **maximális jelszó kérése ennyi perc után képernyőzár** beállításokat, azok van alkalmazva. Ha például mindkét beállítást az értéket állítja be **5** perc, a képernyő kikapcsolja az öt perc után automatikusan és az eszköz zárolva van után további öt perc alatt. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában Miután a felhasználó kikapcsolta a képernyőt, az eszköz zárolja az öt perc múlva.

## <a name="locked-screen-experience"></a>Zárolási képernyő felülete

- **Vezérlőközpont elérése az eszköz zárolt**: válasszon **blokk** kívánja tagadni a hozzáférést a vezérlőközpont-alkalmazáshoz, amíg az eszköz zárolva van. **Nincs konfigurálva** lehetővé teszi a felhasználóknak hozzáférést a vezérlőközpont-alkalmazáshoz, amikor az eszköz zárolva van.
- **Értesítések az eszköz zárolt**: **blokk** megakadályozza a hozzáférést az értesítésekre, amikor az eszköz zárolva van. **Nincs konfigurálva** lehetővé teszi a felhasználó az eszköz zárolásának feloldása nélkül férhetnek hozzá a az értesítéseket.
- **Eszköz zárolva van Wallet értesítések**: **blokk** megakadályozza a Wallet app való hozzáférést, ha az eszköz zárolva van. **Nincs konfigurálva** lehetővé teszi a felhasználó a Wallet alkalmazás eléréséhez, amíg az eszköz zárolva van.
- **Ma nézet, amíg az eszköz zárolva**: **blokk** megakadályozza a ma nézet való hozzáférést, ha az eszköz zárolva van. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó számára a ma nézet, ha az eszköz zárolva van.

## <a name="app-store-doc-viewing-gaming"></a>Alkalmazás-áruház, dokumentumok megtekintése, játékok

- **Alkalmazás-áruház**: **blokk** megakadályozza a hozzáférést az app Store-ban felügyelt eszközökön. **Nincs konfigurálva** lehetővé teszi a hozzáférést.
  - **Alkalmazások telepítése az App Store (csak felügyelt)**: válasszon **blokk** blokkolja az app Store áruházból, az eszköz kezdőképernyőjén. A végfelhasználók továbbra is használhatják az iTunest vagy az Apple Configurator eszközt alkalmazások telepítésére. **Nincs konfigurálva** lehetővé teszi, hogy az app Store áruházból, a kezdőképernyőn.
  - **Automatikus alkalmazásletöltések (csak felügyelt)**: válasszon **blokk** más eszközökön megvásárolt alkalmazások automatikus letöltésének elkerülése érdekében. Ez a meglévő alkalmazások frissítéseire nincs hatással. **Nincs konfigurálva** lehetővé teszi, hogy az eszköz letöltéséhez más iOS-eszközökön megvásárolt alkalmazások.
- **Alkalmazásáruház elérésére szolgáló jelszó**: **megkövetelése** a felhasználó a végfelhasználót egy jelszó beírására kötelezi az alkalmazás-áruházból. **Nincs konfigurálva** lehetővé teszi a hozzáférést az app Store-ba, anélkül, hogy jelszót írna be.
- **Alkalmazáson belüli vásárlások**: válasszon **blokk** alkalmazáson belüli vásárlás az áruházból elkerülése érdekében. **Nincs konfigurálva** lehetővé teszi, hogy a futó alkalmazásokból áruházból történt vásárlások.
- **Zene, podcast vagy hírek (csak felügyelt) tartalom explicit iTunes**: válasszon **blokk** explicit iTunes zene, podcast vagy hírek tartalom elkerülése érdekében. **Nincs konfigurálva** lehetővé teszi, hogy a tároló felnőttnek tartalom elérését az eszköz számára.
- **Tartalmat letölteni az iBook áruházban "erotika"**: válasszon **blokk** meg, hogy a felhasználók leállítja az Ibooks áruházban erotikus van megjelölve, a media letöltését. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó számára "az erotikus tartalom" kategóriába könyvek letöltésének.
- **Céges dokumentumok megtekintése a nem felügyelt alkalmazások**: **blokk** megakadályozza, hogy a nem céges dokumentumok megtekintése a nem felügyelt alkalmazásokban. **Nincs konfigurálva** lehetővé teszi, hogy a vállalati dokumentumok bármely alkalmazásban megtekintését. Például azt szeretné, hogy a felhasználók fájlokat mentsenek a OneDrive alkalmazásból a dropbox alkalmazásba. Ezt a beállítást a konfigurálása **blokk**. Miután az eszköz megkapja a házirendet (például újraindítás után), már nem így mentése folyamatban van.
- **Nem céges dokumentumok megtekintése a céges alkalmazásokban**: **blokk** megakadályozza, hogy a nem céges dokumentumok megtekintése a céges alkalmazásokban. **Nincs konfigurálva** engedélyezi bármilyen dokumentum megtekintését a felügyelt céges alkalmazásokban.
- **AirDrop kezelése nem felügyelt célként**: **megkövetelése** figyelembe kell venni egy nem felügyelt áthúzási célként AirDrop kényszerítése. Leállítja az Airdrop segítségével adatokat küldjön a felügyelt alkalmazások. 
- **Game Centerbeli ismerősök felvételének engedélyezése (csak felügyelt)**: **blokk** megakadályozza, hogy a felhasználók Game Centerbeli ismerősök felvételének engedélyezése. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználót, hogy felvegyen ismerősöket a Game Center.
- **Game Center (csak felügyelt)**: **blokk** a Game Center alkalmazás használatát. **Nincs konfigurálva** lehetővé teszi, hogy az eszközön a Game Center alkalmazás használatával.
- **Többrésztvevős játékok (csak felügyelt)**: válasszon **blokk** több résztvevős játék elkerülése érdekében. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználót, hogy többszereplős játékokat játsszon az eszközön.
- **Minősítési régió**: válassza ki az engedélyezett letöltéseket használni kívánt besorolási régióra. Majd válassza a besorolású **filmek** és **TV-műsorok**.
- **Alkalmazások**: válassza ki a korhatár-besorolású alkalmazásokat, amelyek a felhasználók letölthetik, vagy dönthet **minden alkalmazás engedélyezése**.

## <a name="built-in-apps"></a>Beépített alkalmazások

- **Kamera**: válasszon **blokk** kívánja tagadni a hozzáférést az eszközön a kamera. **Nincs konfigurálva** engedélyezi a hozzáférést az eszköz kamerájának használatát.
  - **FaceTime**: **blokk** kívánja tagadni a hozzáférést a FaceTime alkalmazás használatát. **Nincs konfigurálva** engedélyezi a hozzáférést a FaceTime alkalmazás használatát az eszközön.
- **Siri**: **blokk** Siri megakadályozza a hozzáférést. **Nincs konfigurálva** lehetővé teszi, hogy a Siri beszédfelismerési asszisztens használata az eszközön.
  - **Siri zárolt eszközön**: válasszon **blokk** való hozzáférés letiltása Siri, ha az eszköz zárolva van. **Nincs konfigurálva** lehetővé teszi, hogy a Siri beszédfelismerési asszisztens használatát az eszközön, amikor zárolva van.
  - **Siri profanitásszűrője (csak felügyelt)**: **megkövetelése** megakadályozza, hogy a Siri durva kifejezéseket mondjon ki, vagy diktálását.
  - **Felhasználó által létrehozott tartalom lekérdezése az internetről (csak felügyelt) Siri**: **blokk** megakadályozza, hogy a Siri kérdések megválaszolása céljából webhelyek hozzáférjenek. **Nincs konfigurálva** lehetővé teszi, hogy a Siri számára az internetről érkező felhasználók által létrehozott tartalom eléréséhez.
- **Apple hírek (csak felügyelt)**: válasszon **blokk** , hogy megakadályozza a hozzáférést az Apple hírek alkalmazás az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy az Apple hírek alkalmazás használatával.
- **iBooks store (csak felügyelt)**: **blokk** megakadályozza, hogy a hozzáférés az iBooks Store-bA. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók böngészhetik és vásároljon az iBook áruházban könyvek.
- **Üzenetek alkalmazás az eszközön (csak felügyelt)**: válasszon **blokk** így a felhasználók nem használhatnak az üzenetek alkalmazás az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy az üzenetek alkalmazás használatával küldi, és a szöveges üzenetek olvasásához.
- **Podcastok (csak felügyelt)**: **blokk** megakadályozza, hogy a felhasználók a podcastok alkalmazás használatával. **Nincs konfigurálva** lehetővé teszi, hogy a podcastok alkalmazás használatával.
- **Music szolgáltatás (csak felügyelt)**: **blokk** klasszikus módra a Music alkalmazás visszaáll, és letiltja a Music szolgáltatást. **Nincs konfigurálva** lehetővé teszi, hogy az Apple Music alkalmazás használatával.
- **iTunes Radio szolgáltatás (csak felügyelt)**: **blokk** megakadályozza, hogy a felhasználók az iTunes Radio alkalmazás használatával. **Nincs konfigurálva** lehetővé teszi, hogy az iTunes Radio alkalmazás használatával.
- **A barátok alkalmazás beállításai (csak felügyelt) változik**: **blokk** megakadályozza a módosítását a barátok alkalmazás beállításai. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó megváltoztassa a barátok alkalmazás beállításait.
- **Spotlight-keresés (csak felügyelt) internetes eredmények visszaadásának**: **blokk** reflektorfény leállítja az eredményt visszatérésre egy internetes keresés. **Nincs konfigurálva** lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, hogy adja meg a keresési eredmények.
- **Rendszer-alkalmazások (csak felügyelt) eszközről eltávolításának letiltása**: kiválasztása **blokk** letiltja a rendszer alkalmazások eltávolítása az eszközről. **Nincs konfigurálva** lehetővé teszi a felhasználóknak a rendszer alkalmazások eltávolítása.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

- **Tiltott alkalmazások**: nincs telepítve az eszközön, amelyet szeretne Intune által kezelt alkalmazások listáját. Ha a felhasználó telepít egy alkalmazást a listából, értesítést kap az Intune által.
- **Jóváhagyott alkalmazások**: alkalmazásokat, amelyek telepítése engedélyezett a felhasználók számára. Maradni megfelelő, a felhasználók nem telepíthetnek egyéb alkalmazásokat. Az Intune által kezelt alkalmazások automatikusan engedélyezettek. Ha a felhasználó telepít egy alkalmazást a listából, értesítést kap az Intune által.

Alkalmazások hozzáadása az ezek a listák, a következőket teheti:

- **Adjon hozzá** alkalmazás iTunes áruházbeli URL-címét a kívánt alkalmazást. Írja be például a Microsoft Work Folders alkalmazás hozzáadásához `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Az alkalmazás URL-cím megkereséséhez nyissa meg az iTunes App Store, és keresse meg az alkalmazást. Például keresse meg `Microsoft Remote Desktop` vagy `Microsoft Word`. Válassza ki az alkalmazást, és másolja az URL-címet.

  ITunes segítségével is megkeresheti az alkalmazást, és használja a **hivatkozás másolása** feladat az alkalmazás URL-Címének lekéréséhez.

- Az alkalmazást, beleértve az URL-cím adatait tartalmazó CSV-fájl importálása. Használja a <app url>, <app name>, <app publisher> formátumban. Vagy egy meglévő lista, amely tartalmazza a korlátozott alkalmazások listáját az ugyanebben a formátumban exportálja.

> [!IMPORTANT]
> Eszközprofilok a tiltott alkalmazások beállításait használó felhasználói csoportok hozzá kell rendelni.

## <a name="show-or-hide-apps-supervised-only"></a>Alkalmazások megjelenítése vagy elrejtése (csak felügyelt)

A Megjelenítés vagy elrejtés alkalmazások listájában konfigurálhatja az alábbi listák egyikét iOS 9.3-at vagy újabb rendszert futtató felügyelt eszközökön.

- **Rejtett alkalmazások**: a felhasználók adja meg a rejtett alkalmazások listáját. Felhasználók nem lehet megtekinteni, vagy nyissa meg ezeket az alkalmazásokat.
- **Megjelenített alkalmazások**: Adja meg, amelyeket a felhasználók megtekinthetnek alkalmazásokat, és indítsa el listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

Alkalmazások hozzáadása az ezek a listák, a következőket teheti:

- **Adjon hozzá** alkalmazás iTunes áruházbeli URL-címét a kívánt alkalmazást. Írja be például a Microsoft Work Folders alkalmazás hozzáadásához `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Az alkalmazás URL-cím megkereséséhez nyissa meg az iTunes App Store, és keresse meg az alkalmazást. Például keresse meg `Microsoft Remote Desktop` vagy `Microsoft Word`. Válassza ki az alkalmazást, és másolja az URL-címet.

  ITunes segítségével is megkeresheti az alkalmazást, és használja a **hivatkozás másolása** feladat az alkalmazás URL-Címének lekéréséhez.

- Az alkalmazást, beleértve az URL-cím adatait tartalmazó CSV-fájl importálása. Használja a <app url>, <app name>, <app publisher> formátumban. Vagy egy meglévő lista, amely tartalmazza a korlátozott alkalmazások listáját az ugyanebben a formátumban exportálja.

## <a name="wireless"></a>Vezeték nélküli

- **Alkalmazásadat-barangolás**: válasszon **blokk** a mobilhálózati adatroaming elkerülése érdekében. **Nincs konfigurálva** engedélyezi az adatroaming használatát, ha az eszköz mobilhálózati.
- **Roamingolás közbeni globális háttérbeli adatbeolvasás**: **blokk** megakadályozza, hogy a globális, háttérbeli adatbeolvasás funkció használatával a mobilhálózati roaming esetén. **Nincs konfigurálva** lehetővé teszi az eszköz adatlehívást, például az e-mailben mobilhálózati roaming esetén.
- **Hangtárcsázás**: válasszon **blokk** megakadályozza, hogy a felhasználók a hangtárcsázás funkciót az eszközön található használatával. **Nincs konfigurálva** lehetővé teszi, hogy a hangtárcsázási az eszközön.
- **Hangroaming**: válasszon **blokk** a mobilhálózati hangroaming elkerülése érdekében. **Nincs konfigurálva** engedélyezi a hangroaming használatát, ha az eszköz mobilhálózati.
- **Alkalmazás mobiladatátvitel-használati beállításai (csak felügyelt) változik**: válasszon **blokk** való az alkalmazás mobiladatátvitel-használati beállításai módosításának megakadályozása. **Nincs konfigurálva** lehetővé teszi a felhasználó szabályozza, hogy mely alkalmazások bonyolíthassanak le mobilhálózati adatforgalmat.
- **Személyes elérési pont**: **blokk** megakadályozza, hogy az eszköz elérési pontként használják. Előfordulhat, hogy egyes hálózatüzemeltető szolgáltatók esetében ez a beállítás nem érvényesül. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **Csatlakozás Wi-Fi hálózatokhoz csak konfigurációs profillal (csak felügyelt)**: **megkövetelése** arra kényszeríti az eszköz csak Intune eszközkonfigurációs profilok keresztül beállított Wi-Fi hálózatokhoz. **Nincs konfigurálva** lehetővé teszi az eszköz más Wi-Fi-hálózatokkal.
- **Mobilhálózati használati szabályok (csak felügyelt alkalmazások)**: típusok felügyelt alkalmazások által mobilhálózatokon használható az adatok meghatározásához. A választható lehetőségek:
  - **Mobiladatok használatának letiltása**: blokkolja a mobiladatok használatával **minden kezelt alkalmazások** vagy **adott alkalmazások**.
  - **Mobiladatok használatának letiltása barangolás esetén**: letiltani mobiladatok barangolás esetén **minden kezelt alkalmazások** vagy **adott alkalmazások**.

## <a name="connected-devices"></a>Csatlakoztatott eszközök

- **AirDrop (csak felügyelt)**: **blokk** megakadályozza, hogy az eszközön található AirDrop használatával. **Nincs konfigurálva** lehetővé teszi a közeli eszközökkel az AirDrop funkció használatával.
- **Apple Watch-párosítás (csak felügyelt)**: **blokk** megakadályozza, hogy az Apple Watch-párosítás. **Nincs konfigurálva** lehetővé teszi az eszköz egy Apple Watch-párosítás.
- **Párosított Apple Watch órák csuklóérzékelése**: **megkövetelése** kényszeríti a párosított Apple Watch csuklóérzékelés használatára. Ha szükséges, az Apple Watch nem jelenít meg értesítéseket, amikor nem viselik. 
- **Bluetooth módosítása (csak felügyelt)**: **blokk** leállítja a végfelhasználó megváltoztassa az eszköz Bluetooth-beállításokat. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó módosíthatja ezeket a beállításokat.
- **Párosítás szabályozhatja az iOS-eszközök párosítható eszközök (csak felügyelt) üzemeltetésére**: **nincs konfigurálva** lehetővé teszi, hogy a gazdapárosítás annak érdekében, hogy a rendszergazda szabályozhatja az iOS-eszközzel párosítható eszközök. **Blokk** megakadályozza, hogy a gazdapárosítási.
- **Kimenő AirPlay-kérelmekhez párosítási jelszó megkövetelése**: **megkövetelése** párosítási jelszót, amikor a felhasználó az airplay segítségével tartalmat kíván streamelni egyéb Apple-eszközökre. **Nincs konfigurálva** a felhasználó az AirPlay segítségével anélkül, hogy jelszót írna be tartalomátvitelre.
- **(Csak felügyelt) letiltása AirPrint**: válasszon **letiltása** , hogy az AirPrint-funkció használatát az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó AirPrint használja.
  - **(Csak felügyelt) Keychain AirPrint hitelesítőadat-tárolók letiltása**: **blokk** megakadályozza, hogy a kulcslánc-tárolók használata felhasználónevet és jelszót az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy az AirPrint-felhasználónév és jelszó tárolja a Keychain alkalmazást.
  - **Szükséges megbízható TLS-tanúsítvány (csak felügyelt) AirPrint**: **megkövetelése** arra kényszeríti az eszközön a megbízható tanúsítványokat használ a nyomtatási kommunikációhoz a TLS.
  - **AirPrint-nyomtatókra (csak felügyelt) iBeacon észlelésének letiltása**: **blokk** megakadályozza, hogy a hálózati forgalom adathalászat elleni rosszindulatú AirPrint Bluetooth jeleket. **Nincs konfigurálva** lehetővé teszi a hirdetési AirPrint-nyomtatókra az eszközön.

## <a name="keyboard-and-dictionary"></a>Billentyűzet és szótár

- **Szómeghatározások keresése (csak felügyelt)**: **blokk** megakadályozza, hogy a felhasználó általi kiemelve egy szót, és ezután keresése az eszközön a meghatározását. **Nincs konfigurálva** lehetővé teszi, hogy a definíció keresési szolgáltatáshoz való hozzáférést.
- **Prediktív billentyűzetek (csak felügyelt)**: **nincs konfigurálva** lehetővé teszi, hogy a felhasználó segítségével prediktív billentyűzetek szavakra, érdemes lehet. **Blokk** megakadályozza, hogy ez a funkció.
- **Automatikus javítás (csak felügyelt)**: **nincs konfigurálva** lehetővé teszi, hogy az eszköz automatikusan kijavítsa a hibásan leírt szavakat megoldására. **Blokk** megakadályozza az automatikus javítás használatával.
- **Billentyűzet helyesírás-ellenőrzése (csak felügyelt)**: **nincs konfigurálva** lehetővé teszi, hogy az eszköz helyesírás-ellenőrző használatával. **Blokk** lehetővé teszi, hogy a helyesírás-ellenőrzőjének használatát.
- **Billentyűparancsok (csak felügyelt)**: **nincs konfigurálva** engedélyezi a billentyűparancsok használata az eszközön. **Blokk** leállítja a felhasználónak a billentyűparancsok használatát.
- **Diktálás (csak felügyelt)**: **blokk** megakadályozza a felhasználó szóbeli bemeneti szöveg beírásához. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó diktálással történő bevitel használja.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Icloudba történő biztonsági mentés**: **nincs konfigurálva** lehetővé teszi a felhasználó biztonsági mentése az eszközre az icloud szolgáltatásba. **Blokk** megakadályozza a felhasználó biztonsági mentése az eszközre az icloud szolgáltatásba.
- **Dokumentum icloudba szinkronizálásának (csak felügyelt)**: **nincs konfigurálva** lehetővé teszi, hogy a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére. **Blokk** megakadályozza, hogy a iCloud dokumentumok és adatok szinkronizálását.
- **Fényképadatfolyamok Icloudba történő szinkronizálása**: **nincs konfigurálva** lehetővé teszi, hogy a felhasználók engedélyezhetik **saját fénykép Stream** az Iclouddal való szinkronizálását, és rendelkezik a fényképek elérhető a felhasználói eszközökön az eszközön. **Blokk** megakadályozza, hogy a fényképadatfolyamok Icloudba történő szinkronizálása.
- **Biztonsági másolatok titkosításának**: **megkövetelése** , eszköz biztonsági titkosítva kell lennie.
- **iCloud-Fotókönyvtár**: állítsa **blokk** fényképek és videók tárolása a felhőben használatával iCloud-fotókönyvtár letiltása. Fényképek az eszközre az iCloud-Fotókönyvtár nincs teljes egészében letöltve az eszközről törlődnek. **Nincs konfigurálva** lehetővé teszi, hogy az iCloud-fotókönyvtár használatával.
- **Felügyelt alkalmazások szinkronizálása a felhővel**: **nincs konfigurálva** lehetővé teszi, hogy az Intune felügyeli alkalmazásokat szinkronizálja az adatokat szinkronizáljanak a felhasználó iCloud-fiókjával. **Blokk** megakadályozza, hogy az adatok szinkronizálása az icloud szolgáltatásba.
- **Megosztott fotóstream**: válasszon **blokk** letiltása **fényképek Icloudban való megosztásának** az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy megosztott fotóstreamelés.
- **Tevékenység folytatása**: **nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára az iOS-eszközökön, egy másik iOS vagy MacOS rendszerű eszköz (átadás) elkezdett munkát. **Blokk** megakadályozza, hogy a handoff számára.
- **Icloud-alapú kulcslánc-szinkronizálás letiltása**: válasszon **blokk** tárolt meg a Kulcsláncban Icloudba történő szinkronizálása folyamatban hitelesítő letiltása. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók szinkronizálhatják ezeket a hitelesítő adatokat.
- **Letiltása vállalati könyv biztonsági mentés**: válasszon **letiltása** megakadályozza, hogy a felhasználók vállalati könyvek biztonsági mentésével. **Nincs konfigurálva** lehetővé teszi, hogy a biztonsági mentést a könyvet.
- **Vállalati könyv metaadatainak szinkronizálása (megjegyzések és kiemelések) letiltása**: **blokk** megakadályozza, hogy szinkronizálja megjegyzések, és kiemeli a vállalati könyvekben. **Nincs konfigurálva** lehetővé teszi, hogy a szinkronizálás.

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonóm egyalkalmazásos mód (csak felügyelt)

Ezek a beállítások segítségével konfigurálhatja az iOS-eszközöket megadott alkalmazások autonóm Egyalkalmazásos módban futtatásához. Ez a mód konfigurálva van, és az alkalmazás fut, amikor az eszköz zárolva van. Csak akkor futtathatja az alkalmazást. Például hozzáadhat egy alkalmazást, amely lehetővé teszi, hogy a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

Alkalmazások hozzáadása a következőket teheti:

- Adja meg a **alkalmazásnév** és **Alkalmazásköteg-azonosító**, és válassza ki **Hozzáadás**. [Csomagazonosító-referencia beépített iOS-alkalmazások](#bundle-id-reference-for-built-in-ios-apps) (a jelen cikkben) tartalmazza az egyes alkalmazások, a hozzájuk tartozó azonosítóik.
- **Importálás** alkalmazásnevek és azok csomagazonosító listáját tartalmazó CSV-fájl. Másik lehetőségként **exportálása** egy meglévő lista, amely tartalmazza az alkalmazások.

## <a name="kiosk-supervised-only"></a>Kioszkmód (csak felügyelt)

- **Alkalmazás teljes képernyős módban való futásra**: válassza ki a kioszk módban futtatni kívánt alkalmazásokhoz. A választható lehetőségek: 
  - **App Store**: írja be az URL-cím egy alkalmazás az iTunes App Store-ban
  - **Felügyelt alkalmazás**: Válasszon egy alkalmazást az Intune-hoz hozzáadott
  - **Beépített alkalmazás**: Adja meg a [csomagazonosítója](#bundle-id-reference-for-built-in-ios-apps) a beépített alkalmazás

- **Az assistivetouch**: **megkövetelése** a kisegítő érintés kisegítő beállítást kell az eszközön. Ez a funkció segít az képernyőn megjelenő kézmozdulatok, amely lehet nehézségekbe ütközik az. **Nincs konfigurálva** nem futtatni, vagy engedélyezze ezt a funkciót a teljes képernyős módban.
- **Színek invertálása**: **megkövetelése** a Színek invertálása kisegítő beállítást, a megjelenített képernyőt a látásukban felhasználók módosíthatják. **Nincs konfigurálva** nem futtatni, vagy engedélyezze ezt a funkciót a teljes képernyős módban.
- **Monó hang**: **megkövetelése** a monó hang kisegítő beállítást kell az eszközön. **Nincs konfigurálva** nem futtatni, vagy engedélyezze ezt a funkciót a teljes képernyős módban.
- **VoiceOver**: **megkövetelése** a VoiceOver kisegítő beállítást kell az eszközön a hangos olvassa el a képernyőn megjelenő szöveget. **Nincs konfigurálva** nem futtatni, vagy engedélyezze ezt a funkciót a teljes képernyős módban.
- **Nagyítás**: **megkövetelése** nagyítási beállítását az eszközön, hogy a felhasználók a képernyő nagyítása touch használatával lehet. **Nincs konfigurálva** nem futtatni, vagy engedélyezze ezt a funkciót a teljes képernyős módban.
- **Automatikus zárolás**: **engedélyezése** az eszköz automatikus zárolását. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Csengés kapcsolója**: **engedélyezése** a csengető-(némító-) kapcsoló az eszközön. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Képernyő elforgatása**: **engedélyezése** a képernyő tájolásának módosítását az eszköz elforgatásakor. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Képernyőalvás gombja**: válasszon **engedélyezése** letiltása a képernyőt felébresztő gomb az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **Touch**: **blokk** letiltja az érintőképernyő használatát az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó használja az érintőképernyő használatát.
- **Hangerőgombok**: **engedélyezése** használatával a Hangerőszabályzó gombok használatát az eszközön. **Nincs konfigurálva** letiltja a Hangerőszabályzó gombok használatát.
- **Assistivetouch-vezérlés**: **engedélyezése** megadásakor a felhasználók a kisegítő érintés funkció használata. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Színinvertálás vezérlője**: **engedélyezése** színek invertálásának beállításai, hogy a felhasználók a funkció. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Kijelölt szöveg felolvasása**: **engedélyezése** a kijelölés felolvasása kisegítő beállítást kell az eszközön. Ez a funkció a szöveg, amely a felhasználó kiválasztja hangos olvassa be. **Nincs konfigurálva** letiltja ezt a funkciót.
- **VoiceOver vezérlője**: **engedélyezése** voiceover módosításokat, hogy a felhasználók a VoiceOver funkció, például milyen gyors képernyőn látható szöveg olvasható hangos frissítése. **Nincs konfigurálva** megakadályozza a voiceover módosítását.
- **Nagyítás vezérlője**: **engedélyezése** nagyítás módosításait a felhasználó által. **Nincs konfigurálva** megakadályozza a Nagyítás módosítását.

> [!NOTE]
> Az iOS-eszközök Kioszk módra való konfigurálása előtt felügyelt módba kell állítania az eszközt az Apple Configurator eszközzel vagy az Apple Device Enrollment Program készülékregisztráció-kezelővel. Útmutató az Apple az Apple Configurator eszközzel jelenik meg.
> Ha az iOS-alkalmazást, adja meg a profil hozzárendelése után települ, majd az eszköz nem lép kioszk módba az eszköz újraindításáig.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Csomagazonosító-referencia beépített iOS-alkalmazásokhoz

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, lépjen kapcsolatba a szoftver gyártójával.

| Csomagazonosító                   | Alkalmazásnév     | Kiadó |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Alkalmazásáruház    | Apple     |
| com.apple.calculator        | Számológép   | Apple     |
| com.apple.mobilecal         | Naptár     | Apple     |
| com.apple.camera            | Fényképezőgép       | Apple     |
| com.apple.mobiletimer       | Óra        | Apple     |
| com.apple.compass           | Iránytű      | Apple     |
| com.apple.MobileAddressBook | Névjegyek     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Barátok keresése | Apple     |
| com.apple.mobileme.fmip1    | iPhone keresése  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Állapot       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Térképek         | Apple     |
| com.apple.MobileSMS         | Üzenetek     | Apple     |
| com.apple.Music             | Zene        | Apple     |
| com.apple.news              | Hírek         | Apple     |
| com.apple.mobilenotes       | Megjegyzések        | Apple     |
| com.apple.Numbers           | Számok      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotók       | Apple     |
| com.apple.podcasts          | Podcastok     | Apple     |
| com.apple.reminders         | Emlékeztetők    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Beállítások     | Apple     |
| com.apple.stocks            | Részvények       | Apple     |
| com.apple.tips              | Tippek         | Apple     |
| com.apple.videos            | Videók       | Apple     |
| com.apple.VoiceMemos        | Hangjegyzetek   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Időjárás      | Apple     |

## <a name="safari"></a>Safari

- **Safari (csak felügyelt)**: **blokk** a Safari böngésző használata az eszközön. **Nincs konfigurálva** lehetővé teszi a felhasználóknak a Safari böngésző használata.
- **Automatikus kitöltés**: **blokk** letiltja az automatikus kitöltés funkciót az eszközön a Safariban. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.
- **A cookie-k**: válassza ki, hogyan kezelje a cookie-k az eszközön. A választható lehetőségek:
  - Engedélyezés
  - Az összes cookie blokkolása
  - A felkeresett webhelyek cookie-k engedélyezése
  - A jelenlegi webhely cookie-k engedélyezése
- **A JavaScript**: **blokk** Java-parancsfájlok böngészőben megakadályozza, hogy az eszközön. **Nincs konfigurálva** lehetővé teszi a Java-parancsfájlok.
- **Csalással kapcsolatos figyelmeztetések**: **megkövetelése** csalással kapcsolatos figyelmeztetések jelennek meg a böngésző az eszközön. **Nincs konfigurálva** letiltja ezt a funkciót.
- **Előugró ablakok**: **blokk** letiltja a böngésző előugróablak-blokkolóját. **Nincs konfigurálva** lehetővé teszi, hogy a előugróablak-blokkolóját.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Jelöletlen e-mail-tartományok

A **E-mail tartomány URL-címe**, egy vagy több URL-címek hozzáadása a listához. Amikor a végfelhasználók számára a tartományok, adjon meg eltérő tartományban van, egy e-mailt kap, az e-mailben van megjelölve megbízhatóként a IOS-es Mail alkalmazásban.

### <a name="managed-web-domains"></a>Felügyelt webtartományok

A **webes tartomány URL-címe**, egy vagy több URL-címek hozzáadása a listához. Ad meg, a tartományokból letöltött dokumentumok azokat a rendszer kezeli. Ez a beállítás csak a Safari böngészővel letöltött dokumentumokra vonatkozik.

### <a name="safari-password-autofill-domains"></a>Jelszavak automatikus kitöltése a Safariban

A **tartomány URL-címe**, egy vagy több URL-címek hozzáadása a listához. A felhasználók csak a listában szereplő URL-címekhez tartozó webes jelszavakat menthetnek. Ez a beállítás csak a Safari böngészőre és az iOS 9.3 vagy későbbi verzióit futtató eszközökre vonatkozik felügyelt módban. Ha egyetlen URL-címet sem ad meg, jelszavakat minden webhelyhez lehetséges menteni.

## <a name="next-steps"></a>További lépések

[A profil hozzárendelése](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md) annak állapotát.

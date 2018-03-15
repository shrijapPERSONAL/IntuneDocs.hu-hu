---
title: "Eszközkorlátozásokra vonatkozó beállítások a Microsoft Intune-ban iOS-hez"
titleSuffix: 
description: "A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az iOS rendszerű eszközökön."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc53a7a6a4c961a649d01f23f30c59ff4dc90fe2
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2018
---
# <a name="microsoft-intune-ios-device-restriction-settings"></a>A Microsoft Intune iOS-eszközkorlátozásokra vonatkozó beállításai
A cikk bemutatja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók iOS rendszerű eszközökhöz.

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Általános

-   **Diagnosztikai adatok küldése** – Engedélyezi vagy letiltja, hogy az eszköz diagnosztikai adatokat küldjön az Apple számára.
-   **Képernyőfelvétel** – Engedélyezi a felhasználó számára, hogy képként rögzítse a képernyő tartalmát.
    - **Távoli képernyőfigyelés az Osztályterem alkalmazással (csak felügyelt)** – Letiltja vagy engedélyezi, hogy az Apple Osztályterem alkalmazása figyelje az iOS-eszközök képernyőjét.
    - **Az Osztályterem alkalmazás értesítés nélküli képernyőfigyelése (csak felügyelt)** – Ha engedélyezi, az oktatók csendes módban, a diákok tudta nélkül figyelhetik a diákok iOS-eszközeinek képernyőjét az Osztályterem alkalmazás használatával.
-   **Nem megbízható TLS-tanúsítványok** – Engedélyezi nem megbízható TLS-tanúsítványok használatát az eszközön.
-   **Megbízható nagyvállalati alkalmazás** – Engedélyezi a felhasználó számára, hogy megbízhatónak tekintsen olyan alkalmazásokat, amelyeket nem az alkalmazás-áruházból töltött le.
- **Fiókmódosítás (csak felügyelt)** – Ha a beállítás ki van kapcsolva, a felhasználó nem módosíthat eszközspecifikus beállításokat (például új eszközfiókok létrehozása, felhasználónév vagy jelszó módosítása) az iOS beállításkezelő alkalmazásából.
Ez az iOS beállításkezelő alkalmazásából elérhető, más alkalmazásokra (például Mail, Contacts, Calendar, Facebook és Twitter) vonatkozó beállításokat is érinti, nem vonatkozik azonban azokra az alkalmazásokra, amelyeknek nincsenek az iOS beállításkezelő alkalmazásából konfigurálható fiókbeállításaik (például a Microsoft Outlook alkalmazás).
- **Korlátozások engedélyezése az eszközbeállítások között (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó eszközkorlátozásokat (szülői felügyeletet) állítson be az eszközön.
- **Az eszköz teljes tartalmának és összes beállításának törlésére szolgáló beállítás használata (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó törölje az összes tartalmat és beállítást az eszközről.
- **Eszköz nevének módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy módosítsa az eszköz nevét.
- **Értesítési beállítások módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy módosítsa az eszköz értesítési beállításait.
- **Háttérkép módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy megváltoztassa az eszköz háttérképét.
- **Vállalati alkalmazások megbízhatósági beállításainak módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy megbízhatónak tekintsen olyan alkalmazásokat, amelyeket nem az alkalmazás-áruházból töltött le.
- **Konfigurációs profil módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára a konfigurációs profilok telepítését.
- **Aktiválási zár (csak felügyelt)** – Engedélyezi az aktiválási zárat a felügyelt iOS-eszközökön.

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
- Háttérkép módosítása 
- Alkalmazások automatikus letöltése 
- Vállalati alkalmazások megbízhatóságának módosítása 
- Apple Music 
- Mail Drop 
- Párosítás Apple Watch órával 

> [!NOTE]
> Az Apple megerősítette, hogy bizonyos beállítások 2018-ban át fognak kerülni a kizárólag felügyelt módban használhatók közé. Mérlegelje ezt, ha az alábbi beállításokat azelőtt használja, mielőtt a kapcsolódó funkciókat az Apple áthelyezi a kizárólag felügyelt módban használhatók közé:
> - Végfelhasználók által végzett alkalmazástelepítés
> - Alkalmazás eltávolítása
> - FaceTime
> - Safari
> - iTunes
> - Durva tartalom
> - iCloud dokumentumok és adatok
> - Több résztvevős játék
> - Barátok hozzáadása a Game Centerben

## <a name="password"></a>Jelszó
-   **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -   **Egyszerű jelszavak** – Engedélyezi az egyszerű jelszavak (például a 0000 és az 1234) használatát.
    -   **Kért jelszótípus** – A kért jelszó típusát határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.
    -   **Nem alfanumerikus karakterek száma a jelszóban** – Adja meg, hogy hány szimbólumkarakternek (például **#** vagy **@**) kell szerepelnie a jelszóban.
    -   **Jelszó minimális hossza** – Meghatározza, hogy legalább hány karakterből álljon a jelszó.
    -   **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Meghatározza, hogy hány sikertelen bejelentkezési kísérlet után törlődnek az eszközön lévő adatok.
    -   **Jelszó kérése ennyi perccel a képernyőzárolás után**<sup>1</sup> – Azt határozza meg, hogy az eszköz mennyi időt tölthet üresjáratban, mielőtt a felhasználónak újra meg kellene adnia a jelszavát.
    -   **Képernyőzárolás legfeljebb ennyi perc inaktivitás után**<sup>1</sup> – Ennyi perc elteltével kapcsol ki a kijelző.
    -   **Jelszó érvényessége (nap)** – Meghatározza, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát.
    -   **Korábbi jelszavak újbóli használatának tiltása** – Azt határozza meg, hogy az eszköz hány korábban használt jelszót jegyezzen meg.
    -   **Ujjlenyomattal történő zárolásfeloldás engedélyezése** – Engedélyezi az erre alkalmas eszközök zárolásának ujjlenyomattal történő feloldását.
- **PIN-kód módosítása (csak felügyelt)** – Megakadályozza a jelszó hozzáadását, módosítását és eltávolítását.
    - **Ujjlenyomat módosítása (csak felügyelt)** – Megakadályozza, hogy a felhasználó módosítsa, hozzáadja vagy eltávolítsa a TouchID-beállításokat.

<sup>1</sup>Ha a **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** és a **Jelszó kérése legfeljebb ennyi perccel a képernyőzárolás után** beállítást is konfigurálja, akkor a rendszer egymást követően alkalmazza őket. Ha például mindkét beállítást az **5** perc értékre állítja be, a képernyő öt perc után automatikusan ki fog kapcsolni, és az eszköz további öt perc után lesz zárolva. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában az eszköz öt perccel azután lesz zárolva, hogy a felhasználó kikapcsolta a képernyőt.

## <a name="locked-screen-experience"></a>Zárolási képernyő felülete

-   **Vezérlőközpont elérése az eszköz zárolt állapotában** – Engedélyezi a felhasználó számára a hozzáférést a vezérlőközpont-alkalmazáshoz olyankor is, amikor az eszköz zárolva van.
-   **Értesítések, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára, hogy az eszköz zárolásának feloldása nélkül is hozzáférhessen az értesítések nézetéhez.
-   **Passbook, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára a Passbook alkalmazás elérését olyankor is, amikor az eszköz zárolva van.
-   **Ma nézet, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára a Ma nézet használatát, ha az eszköz zárolva van.

## <a name="app-store-doc-viewing-gaming"></a>Alkalmazás-áruház, dokumentumok megtekintése, játékok


-   **Alkalmazás-áruház** – Letiltja az alkalmazás-áruház elérését a felügyelt eszközökön.
    - **Alkalmazások telepítése az App Store-ból (csak felügyelt)** – Letiltja az alkalmazás-áruház elérését az eszköz kezdőképernyőjén. A végfelhasználók továbbra is használhatják az iTunest vagy az Apple Configurator eszközt alkalmazások telepítésére.
    - **Automatikus alkalmazásletöltések (csak felügyelt)** – Letiltja a más iOS-eszközökön megvásárolt alkalmazások letöltését erre az eszközre.
-   **Alkalmazás-áruház elérésére szolgáló jelszó** – A felhasználóktól jelszót kér, mielőtt hozzáférhetnének az alkalmazás-áruházhoz.
-   **Alkalmazáson belüli vásárlás** – Engedélyezi a futó alkalmazásokból történő áruházi vásárlást.
-   **Felnőtteknek szánt iTunes-tartalom (zene, podcast vagy hírek)** – Engedélyezi a felnőttnek minősített áruházi tartalom elérését az eszköz számára.
-   **Az iBook áruházban „Erotika” címkével megjelölt tartalmak letöltése** – Engedélyezi a felhasználó számára az iBooks áruházban erotikus tartalomként megjelölt tartalom letöltését.
-   **Céges dokumentumok megtekintése a nem felügyelt alkalmazásokban** – Engedélyezi a vállalati dokumentumok tetszőleges alkalmazásban való megtekintését.<br>**Példa:** Szeretné megakadályozni, hogy a felhasználók fájlokat mentsenek a OneDrive alkalmazásból a Dropbox alkalmazásba. Állítsa be ezt a beállítást „Nem” értékre. Miután az eszköz megkapja a házirendet (például újraindítás után), a továbbiakban nem engedélyezi a mentést.
-   **Nem céges dokumentumok megtekintése a céges alkalmazásokban** – Engedélyezi bármilyen dokumentum megtekintését a felügyelt céges alkalmazásokban.
-   **AirDrop kezelése nem felügyelt célként** – Letiltja a felügyelt alkalmazásokból az AirDrop segítségével történő adatküldést. az Airdrop szolgáltatással való adatküldés lehetőségét.
-   **Game Center-beli ismerősök hozzáadása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy felvegyen ismerősöket a Game Centerben.
-   **Game Center (csak felügyelt)** – Engedélyezi vagy letiltja a Game Center alkalmazás használatát.
-   **Több résztvevős játékok (csak felügyelt eszköz esetén)** – Engedélyezi a felhasználó számára, hogy több résztvevős játékokat játsszon az eszközön.
-   **Besorolási régió** – Válassza ki, hogy melyik besorolási régióra vonatkozóan kívánja konfigurálni az engedélyezett letöltéseket, majd adja meg, hogy milyen besorolású **Filmek** és **Tévéműsorok** letöltését engedélyezi.
-   **Alkalmazások** – Válassza ki, hogy milyen korhatár-besorolású alkalmazásokat tölthessenek le a felhasználók (a **Minden alkalmazás engedélyezése** lehetőséget is választhatja).

## <a name="built-in-apps"></a>Beépített alkalmazások

-   **Kamera** – A beállítás meghatározza, hogy használható-e az eszközön a kamera.
    -   **FaceTime** – Engedélyezi a FaceTime alkalmazás használatát az eszközön.
-   **Siri** – Engedélyezi az eszközön a Siri beszédfelismerési asszisztens használatát.
    -   **Siri, ha az eszköz zárolva van** – Engedélyezi a Siri beszédfelismerési asszisztens eszközzárolás alatti használatát az eszközön.
    -   **Siri profanitásszűrője (csak felügyelt)** – Megakadályozza, hogy a Siri durva kifejezéseket mondjon ki, vagy elfogadja ilyenek diktálását.
    -   **Felhasználó által létrehozott tartalom Siri általi lekérdezése az internetről (csak felügyelt)** – Engedélyezi, hogy a Siri kérdések megválaszolása céljából hozzáférjen webhelyekhez.
- **Apple Hírek (csak felügyelt)** – Engedélyezi az Apple Hírek alkalmazás használatát.
- **iBooks Store (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó könyveket böngésszen és vásároljon az iBook áruházban.
- **Üzenetek alkalmazás az eszközön (csak felügyelt)** – Engedélyezi az Üzenetek alkalmazás használatát SMS-ek küldésére és fogadására.
- **Podcasts (csak felügyelt)** – Engedélyezi a Podcastok alkalmazás használatát.
- **Music szolgáltatás (csak felügyelt)** – Engedélyezi az Apple Music alkalmazás használatát.
- **iTunes Radio szolgáltatás (csak felügyelt)** – Engedélyezi az iTunes Radio alkalmazás használatát.
- **Barátok keresése alkalmazás beállításainak módosítása (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó megváltoztassa a Barátok alkalmazás beállításait.
- **Spotlight-keresés internetes eredményeinek visszaadása (csak felügyelt)** – Lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, és további találatokat adjon vissza.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

- A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára. A rendszer nem akadályozza meg, hogy a felhasználók tiltott alkalmazásokat telepítsenek, de ilyen esetben értesítést küld Önnek.
- A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek. A rendszer nem akadályozza meg, hogy a felhasználók az engedélyezési listán nem szereplő alkalmazásokat telepítsenek, de ilyen esetben értesítést küld Önnek.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet. Tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazásnak az alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha meg szeretné adni egy alkalmazás URL-címét alkalmazások listájában, használja a következő formátumot:

Keresőmotor segítségével keresse meg az iTunes alkalmazás-áruházban használni kívánt alkalmazást, és nyissa meg az alkalmazás lapját.
Másolja a vágólapra a lap URL-címét, és használja ezt az URL-címet az engedélyezett és a letiltott alkalmazások listájának, illetve a kioszkmódban futtatni kívánt alkalmazásoknak a konfigurálásához.
A tiltott alkalmazások beállításait tartalmazó eszközprofilokat hozzá kell rendelni a kívánt felhasználócsoportokhoz.

Példa: Keressen rá az iPad Microsoft Word alkalmazásra. Ebben az esetben a következő URL-címet használja: https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Az iTunes segítségével is megkeresheti az alkalmazást, majd a **Hivatkozás másolása** parancs használatával beszerezheti az alkalmazás URL-címét.

### <a name="additional-options"></a>További beállítások

Az **Importálás** gombra kattintva feltöltheti a listát egy CSV-fájlból, mely a következő formátumú: <*alkalmazás URL-címe*>, <*alkalmazás neve*>, <*alkalmazás kiadója*>. Az **Exportálás** gombra kattintva pedig létrehozhat egy CSV-fájlt, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.

## <a name="show-or-hide-apps-supervised-only"></a>Alkalmazások megjelenítése vagy elrejtése (csak felügyelt)

A megjelenített és az elrejtett alkalmazások listáján konfigurálhatja valamelyiket a következő listák közül (ennek feltétele, hogy a felügyelt eszközökön az iOS 9.3-as vagy újabb verziója fusson).

A **Rejtett alkalmazások** listája – Itt felsorolhatja azokat az alkalmazásokat, amelyek rejtve vannak a felhasználók számára. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
A **Megjelenített alkalmazások** listája – Itt felsorolhatja a felhasználók által látható és elindítható alkalmazásokat. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, és adja meg a kívánt nevet. Tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazásnak az alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha meg szeretné adni egy alkalmazás URL-címét alkalmazások listájában, használja a következő formátumot:

Keresőmotor segítségével keresse meg az iTunes alkalmazás-áruházban használni kívánt alkalmazást, és nyissa meg az alkalmazás lapját.
Másolja a vágólapra a lap URL-címét, és használja ezt az URL-címet az engedélyezett és a letiltott alkalmazások listájának, illetve a kioszkmódban futtatni kívánt alkalmazásoknak a konfigurálásához.

Példa: Keressen rá az iPad Microsoft Word alkalmazásra. Ebben az esetben a következő URL-címet használja: https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Az iTunes szoftverrel is megkeresheti az alkalmazást, majd a **Hivatkozás másolása** parancs használatával beszerezheti az alkalmazás URL-címét.

### <a name="additional-options"></a>További beállítások

Az **Importálás** gombra kattintva egy CSV formátumú fájlt is beolvashat. Ennek a következő formátumúnak kell lennie: <*az alkalmazás URL-címe*>, <*az alkalmazás neve*>, <*az alkalmazás kiadója*>. Az **Exportálás** gombra kattintva egy olyan CSV-fájlt hozhat létre, amely ugyanebben a formátumban tartalmazza a rejtett vagy a megjelenített alkalmazások listáját.


## <a name="wireless"></a>Vezeték nélküli
-   **Adatroaming** – Engedélyezi adatroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik.
-   **Barangolás közbeni globális háttérbeli adatbeolvasás** – Engedélyezi az eszköz számára a mobilhálózati roaming közben történő adatlehívást, például az e-mailek lekérését.
-   **Hangtárcsázás** – Engedélyezi a hangtárcsázási funkciót az eszközön.
-   **Hangroaming** – Engedélyezi a hangroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik.
-   **Alkalmazások mobil adatforgalmi beállításainak módosítása (csak felügyelt)** – Engedélyezi, hogy a felhasználó szabályozza, mely alkalmazások bonyolíthassanak le mobilhálózati adatforgalmat.
-   **Személyes elérési pont** – Letiltja az eszköz elérési pontként való használatát. Előfordulhat, hogy egyes hálózatüzemeltető szolgáltatók esetében ez a beállítás nem érvényesül.
-   **Wi-Fi-hálózatokhoz való csatlakozás csak konfigurációs profilokkal (csak felügyelt)** – Az eszköz csak olyan Wi-Fi-hálózatokhoz csatlakozhat, amelyeket Intune-beli Wi-Fi-profillal konfiguráltak.

- **Mobilhálózati használati szabályok (csak felügyelt)** – A beállítással a felügyelt alkalmazások által mobilhálózatokon használható adattípusokat határozhatja meg. A következő lehetőségek közül választhat:
    - **Mobiladatok használatának letiltása**
    - **Mobiladatok használatának letiltása barangolás esetén**

## <a name="connected-devices"></a>Csatlakoztatott eszközök

-   **AirDrop (csak felügyelt)** – Engedélyezi az AirDrop funkciónak a közeli eszközökkel való tartalomcserére történő használatát.
-   **Apple Watch párosítása (csak felügyelt)** – Engedélyezi az eszköz Apple Watch órával való párosítását.
-   **Párosított Apple Watch órák csuklóérzékelése** – Ha ez a beállítás engedélyezve van, az Apple Watch nem jelenít meg értesítéseket, amikor nem viselik.
-   **Bluetooth módosítása (csak felügyelt)** – Letiltja, hogy a felhasználó módosítsa az eszközön a Bluetooth-beállításokat.
-   **Gazdapárosítás annak szabályozására, hogy az iOS-készülék milyen eszközökkel legyen párosítható (csak felügyelt)** – Engedélyezi a gazdapárosítási funkció számára, hogy lehetővé tegye az iOS-alapú eszközzel párosítható eszközök szabályozását a rendszergazda számára.
-   **Párosítási jelszó megkövetelése a kimenő AirPlay-kérelmekhez** – A rendszer kéri a párosítási jelszót, ha a felhasználó az AirPlay segítségével tartalmat kíván streamelni egyéb Apple-eszközökre.

## <a name="keyboard-and-dictionary"></a>Billentyűzet és szótár

-   **Szómeghatározások keresése (csak felügyelt)** – Engedélyezi azt az iOS-funkciót, amellyel kijelölhet egy szót, és megkeresheti a meghatározását.
-   **Prediktív billentyűzetek (csak felügyelt)** – Engedélyezi a prediktív billentyűzetek használatát; ezek javaslatokat tesznek a felhasználó által leírni kívánt szavakra.
-   **Automatikus javítás (csak felügyelt)** – Engedélyezi, hogy az eszköz automatikusan kijavítsa a hibásan leírt szavakat.
-   **Billentyűzet helyesírás-ellenőrzése (csak felügyelt)** – Engedélyezi az eszköz helyesírás-ellenőrzőjének használatát.
-   **Billentyűparancsok (csak felügyelt)** – Engedélyezi a billentyűparancsok használatát.
-   **Diktálás (csak felügyelt)** – Megakadályozza, hogy a felhasználó hangbemenet használatával írjon be szöveget.

## <a name="cloud-and-storage"></a>Felhő és tárolás
-   **Biztonsági mentés az iCloudba** – Engedélyezi, hogy a felhasználó biztonsági mentést készítsen az iCloudba az eszközről.
-   **Dokumentumok iCloudba történő szinkronizálása (csak felügyelt eszköz esetén)** – Engedélyezi a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére.
-   **Fényképadatfolyamok iCloudba történő szinkronizálása** – A felhasználók engedélyezhetik a **Saját fotóstreamet** az eszközeiken, amely lehetővé teszi a fényképeknek az iClouddal való szinkronizálását, így a fényképek elérhetővé válnak a felhasználó összes eszközén.
-   **Biztonsági másolatok titkosítása** – Megköveteli az eszköz minden biztonsági másolatának titkosítását.
-   **iCloud-fotókönyvtár** – A **Nem** értékre állítva letilthatja a felhasználói fényképek és videók felhőben való tárolását lehetővé tevő iCloud-fotókönyvtár használatát.   Ha a beállítás a **Nem** értékre van állítva, a rendszer minden olyan fényképet eltávolít az eszközről, amely nincs teljes egészében letöltve az eszközre az iCloud-fotókönyvtárból.
-   **Felügyelt alkalmazások szinkronizálása a felhővel** – Engedélyezi, hogy az Intune-nal felügyelt alkalmazások adatokat szinkronizáljanak a felhasználó iCloud-fiókjával.
-   **Megosztott fotóstream** – A **Nem** értékre állítva letilthatja az **iCloud-fotómegosztást** az eszközön.
-   **Tevékenység folytatása** – Lehetővé teszi, hogy a felhasználó folytassa az iOS-eszközön vagy egy másik macOS rendszerű gépen elkezdett munkát (átadás).

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonóm egyalkalmazásos mód (csak felügyelt)

Ezekkel a beállításokkal konfigurálhatja az iOS-es eszközöket megadott alkalmazások autonóm egyalkalmazásos módban való futtatására. Ha ez a mód konfigurálva van, és az alkalmazást elindítják, az eszközön nem lehet másik alkalmazást futtatni. Célszerű például így konfigurálni az olyan alkalmazásokat, amelyekkel a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

### <a name="settings"></a>Beállítások

- **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak az ezen a panelen található alkalmazáslistában megjelenő nevét.
- **Alkalmazás csomagazonosítója** – Itt adhatja meg az alkalmazás csomagazonosítóját. Segítséget a jelen témakörben alább található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.

Az alkalmazásnevek és a csomagazonosítók megadása után az alkalmazást a **Hozzáadás** lehetőség választásával adhatja hozzá a listához.

- **Importálás** – Importálhat egy vesszővel tagolt (.csv kiterjesztésű) fájlt, amely az alkalmazások nevét és a hozzájuk tartozó csomagazonosítókat tartalmazza.
- **Exportálás** – Az alkalmazásneveket és a hozzájuk tartozó csomagazonosítókat egy vesszővel tagolt (.csv kiterjesztésű) fájlba exportálhatja.

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Csomagazonosító-referencia beépített iOS-alkalmazásokhoz

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, lépjen kapcsolatba a szoftver gyártójával.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.MobileSafari,Safari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


## <a name="kiosk-supervised-only"></a>Kioszkmód (csak felügyelt)
-   **Kioszkmódban futó alkalmazás** – A **Felügyelt alkalmazás** lehetőséget választva egy az Intune-ba már felvett alkalmazást adhat meg, az **Áruházbeli alkalmazás** lehetőséget választva egy áruházbeli alkalmazás URL-címét. Az itt megadotton kívül más alkalmazás nem futtatható az eszközön. További segítségért olvassa el a jelen témakörben alább található „Alkalmazásáruházak URL-címének megadása” című részt.
    -   **AssistiveTouch** – Engedélyezi vagy letiltja az **AssistiveTouch** kisegítő beállítást, amely segít a nehézségekkel küzdő felhasználóknak a képernyőn elvégezhető kézmozdulatok végrehajtásában.
    -   **Színinvertálás** – Engedélyezi vagy letiltja a Színinvertálás kisegítő beállítást, amellyel módosíthatja a képernyőt a látásukban korlátozott felhasználók számára.
    -   **Monó hang** – Engedélyezi vagy letiltja a Monó hang kisegítő beállítást.
    -   **VoiceOver** – Engedélyezi vagy letiltja a **VoiceOver** kisegítő beállítást, amely hangosan felolvassa az eszköz képernyőjén megjelenő szöveget.
    -   **Nagyítás** – Engedélyezi vagy letiltja a **Nagyítás** kisegítő beállítást, amellyel a felhasználó érintéssel nagyíthatja az eszköz képernyőjén megjelenő tartalmat.
    -   **Automatikus zárolás** – Engedélyezi vagy letiltja az eszköz automatikus zárolását.
    -   **Csengés kapcsolója** – Engedélyezheti vagy letilthatja a csengő kapcsolóját (az elnémítót) az eszközön.
    -   **Képernyő elforgatása** – Engedélyezi vagy letiltja a képernyő tájolásának módosítását az eszköz elforgatásakor.
    -   **Képernyőalvás gombja** – Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.
    -   **Érintésvezérlés** – Engedélyezi vagy letiltja az érintőképernyő használatát az eszközön.
    -   **Hangerőgombok** – Engedélyezi vagy letiltja a hangerőszabályzó gombok használatát az eszközön.
    -   **AssistiveTouch-vezérlés** – Engedélyezi vagy letiltja az AssistiveTouch funkció beállításának módosítását.
    -   **Színinvertálás vezérlője** – Engedélyezi vagy letiltja a színinvertálási funkció beállításainak módosítását.
    -   **Kijelölt szöveg felolvasása** – Engedélyezi vagy letiltja a Kijelölés felolvasása kisegítő beállítást, amellyel felolvastatható a felhasználó által kijelölt szöveg.
    -   **VoiceOver vezérlője** – Engedélyezi vagy letiltja a VoiceOver funkció beállítását (például hogy milyen gyorsan történjen a képernyőn látható szöveg felolvasása).
    -   **Nagyítás vezérlője** – Engedélyezi vagy letiltja a nagyítási funkció működésének felhasználó általi beállítását.

>[!NOTE]
> Az iOS-eszközök Kioszk módra való konfigurálása előtt felügyelt módba kell állítania az eszközt az Apple Configurator eszközzel vagy az Apple Device Enrollment Program készülékregisztráció-kezelővel. Az Apple Configurator eszközzel kapcsolatos további információkat az Apple dokumentációjában talál.
>Ha a megadott iOS-alkalmazás a profil hozzárendelése után települ, az eszköz mindaddig nem lép kioszkmódba, amíg újra nem indítják.

## <a name="safari"></a>Safari
-   **Safari (csak felügyelt eszköz esetén)** – Ez a beállítás azt határozza meg, hogy használható-e a Safari böngésző az eszközön.
-   **Automatikus kitöltés** – Engedélyezi a felhasználó számára, hogy módosítsa a böngésző automatikus kiegészítési funkciójának beállításait.
-   **Cookie-k** – Engedélyezi a cookie-k használatát a böngésző számára.
-   **JavaScript** – Engedélyezi a Java-parancsfájlok futtatását a böngészőben.
-   **Csalás elleni figyelmeztetés** – Engedélyezi a csalás elleni figyelmeztetéseket a böngészőben.
-   **Előugró ablakok** – Engedélyezi vagy letiltja a böngésző előugróablak-blokkolóját.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Jelöletlen e-mail-tartományok

Az **E-mail-tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. Ha a végfelhasználó nem a konfigurált tartományok egyikéből kap e-mailt, az iOS-es Mail alkalmazásban ez az e-mail nem megbízhatóként jelenik meg.


### <a name="managed-web-domains"></a>Felügyelt webtartományok

A **Webtartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. A megadott tartományokból letöltött dokumentumok felügyeltnek minősülnek. Ez a beállítás csak a Safari böngészővel letöltött dokumentumokra vonatkozik.


### <a name="safari-password-autofill-domains"></a>Jelszavak automatikus kitöltése a Safariban

A **Tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. A felhasználók csak a listában szereplő URL-címekhez tartozó webes jelszavakat menthetnek. Ez a beállítás csak a Safari böngészőre és az iOS 9.3 vagy későbbi verzióit futtató eszközökre vonatkozik felügyelt módban. Ha egyetlen URL-címet sem ad meg, jelszavakat minden webhelyhez lehetséges menteni.

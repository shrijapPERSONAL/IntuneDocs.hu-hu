---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban iOS esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az iOS-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e860c99154f4695e5f4ad0122def8221e583c483
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Az iOS eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Általános
-     **Kamera** – A beállítás meghatározza, hogy használható-e az eszközön a kamera.     
-     **Diagnosztikai adatok küldése** – Engedélyezi vagy letiltja, hogy az eszköz diagnosztikai adatokat küldjön az Apple számára.
-     **FaceTime** – Engedélyezi a FaceTime alkalmazás használatát az eszközön.
-     **Képernyőfelvétel** – Engedélyezi a felhasználó számára, hogy képként rögzítse a képernyő tartalmát.
-     **Siri** – Engedélyezi az eszközön a Siri beszédfelismerési asszisztens használatát.
    -     **Siri, ha az eszköz zárolva van** – Engedélyezi a Siri beszédfelismerési asszisztens eszközzárolás alatti használatát az eszközön.
    -     **Siri profanitásszűrője (csak felügyelt)** – Megakadályozza, hogy a Siri durva kifejezéseket mondjon ki, vagy elfogadja ilyenek diktálását.
    -     **Felhasználó által létrehozott tartalom Siri általi lekérdezése az internetről (csak felügyelt)** – Engedélyezi, hogy a Siri kérdések megválaszolása céljából hozzáférjen webhelyekhez.
-     **Nem megbízható TLS-tanúsítványok** – Engedélyezi nem megbízható TLS-tanúsítványok használatát az eszközön.
-     **Vezérlőközpont elérése az eszköz zárolt állapotában** – Engedélyezi a felhasználó számára a hozzáférést a vezérlőközpont-alkalmazáshoz olyankor is, amikor az eszköz zárolva van.
-     **Értesítések, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára, hogy az eszköz zárolásának feloldása nélkül is hozzáférhessen az értesítések nézetéhez.
-     **Passbook, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára a Passbook alkalmazás elérését olyankor is, amikor az eszköz zárolva van.
-     **Ma nézet, ha az eszköz zárolva van** – Engedélyezi a felhasználó számára a Ma nézet használatát, ha az eszköz zárolva van.
-     **Megbízható nagyvállalati alkalmazás** – Engedélyezi a felhasználó számára, hogy megbízhatónak tekintsen olyan alkalmazásokat, amelyeket nem az alkalmazás-áruházból töltött le.
-     **AirDrop (csak felügyelt)** – Engedélyezi az AirDrop funkciónak a közeli eszközökkel való tartalomcserére történő használatát.
-     **Spotlight-keresés internetes eredményeinek visszaadása (csak felügyelt)** – Lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, és további találatokat adjon vissza.
-     **Szómeghatározások keresése (csak felügyelt)** – Engedélyezi azt az iOS-funkciót, amellyel kijelölhet egy szót, és megkeresheti a meghatározását.
-     **Prediktív billentyűzetek (csak felügyelt)** – Engedélyezi a prediktív billentyűzetek használatát; ezek javaslatokat tesznek a felhasználó által leírni kívánt szavakra.
-     **Automatikus javítás (csak felügyelt)** – Engedélyezi, hogy az eszköz automatikusan kijavítsa a hibásan leírt szavakat.
-     **Billentyűzet helyesírás-ellenőrzése (csak felügyelt)** – Engedélyezi az eszköz helyesírás-ellenőrzőjének használatát.
-     **Billentyűparancsok (csak felügyelt)** – Engedélyezi a billentyűparancsok használatát.
-     **Párosított Apple Watch órák csuklóérzékelése** – Ha ez a beállítás engedélyezve van, az Apple Watch nem jelenít meg értesítéseket, amikor nem viselik.
- **Párosítási jelszó megkövetelése a kimenő AirPlay-kérelmekhez** – A rendszer kéri a párosítási jelszót, ha a felhasználó az AirPlay segítségével tartalmat kíván streamelni egyéb Apple-eszközökre.
- **Fiókmódosítás (csak felügyelt)** – Ha a beállítás ki van kapcsolva, a felhasználó nem módosíthat eszközspecifikus beállításokat (például új eszközfiókok létrehozása, felhasználónév vagy jelszó módosítása) az iOS beállításkezelő alkalmazásából.
Ez az iOS beállításkezelő alkalmazásából elérhető, más alkalmazásokra (például Mail, Contacts, Calendar, Facebook és Twitter) vonatkozó beállításokat is érinti, nem vonatkozik azonban azokra az alkalmazásokra, amelyeknek nincsenek az iOS beállításkezelő alkalmazásából konfigurálható fiókbeállításaik (például a Microsoft Outlook alkalmazás).
- **Apple Watch párosítása (csak felügyelt)** – Engedélyezi az eszköz Apple Watch órával való párosítását.
- **Bluetooth módosítása (csak felügyelt)** – Letiltja, hogy a felhasználó módosítsa az eszközön a Bluetooth-beállításokat.
- **Távoli képernyőfigyelés az Osztályterem alkalmazással (csak felügyelt)** – Letiltja vagy engedélyezi, hogy az Osztályterem alkalmazás figyelje a távoli eszközök képernyőjét.
- **Korlátozások engedélyezése az eszközbeállítások között (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó eszközkorlátozásokat (szülői felügyeletet) állítson be az eszközön.
- **Az eszköz teljes tartalmának és összes beállításának törlésére szolgáló beállítás használata (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó törölje az összes tartalmat és beállítást az eszközről.
- **Eszköz nevének módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy módosítsa az eszköz nevét.
- **Diagnosztikai adatok küldésére vonatkozó beállítások módosítása (csak felügyelt)** – Engedélyezi vagy letiltja, hogy az eszköz diagnosztikai adatokat küldjön az Apple számára.
- **Gazdapárosítás annak szabályozására, hogy az iOS-készülék milyen eszközökkel legyen párosítható (csak felügyelt)** – Engedélyezi a gazdapárosítási funkció számára, hogy lehetővé tegye az iOS-alapú eszközzel párosítható eszközök szabályozását a rendszergazda számára.
- **Értesítési beállítások módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy módosítsa az eszköz értesítési beállításait.
- **PIN-kód módosítása (csak felügyelt)** – Engedélyezi az eszközjelszó hozzáadását, módosítását és eltávolítását.
- **Háttérkép módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy megváltoztassa az eszköz háttérképét.
- **Vállalati alkalmazások megbízhatósági beállításainak módosítása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy megbízhatónak tekintsen olyan alkalmazásokat, amelyeket nem az alkalmazás-áruházból töltött le.
- **Alkalmazások telepítése az App Store-ból (csak felügyelt)** – Engedélyezi az eszköz számára az alkalmazás-áruház elérését és alkalmazások telepítését.
- **Barátok keresése alkalmazás beállításainak módosítása (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó megváltoztassa a Barátok alkalmazás beállításait.
- **iBooks Store (csak felügyelt)** – Lehetővé teszi, hogy a felhasználó könyveket böngésszen és vásároljon az iBook áruházban.
- **Üzenetek alkalmazás az eszközön (csak felügyelt)** – Engedélyezi az Üzenetek alkalmazás használatát SMS-ek küldésére és fogadására.
- **Podcasts (csak felügyelt)** – Engedélyezi a Podcastok alkalmazás használatát.
- **Music szolgáltatás (csak felügyelt)** – Engedélyezi az Apple Music alkalmazás használatát.
- **iTunes Radio szolgáltatás (csak felügyelt)** – Engedélyezi az iTunes Radio alkalmazás használatát.
- **Apple Hírek (csak felügyelt)** – Engedélyezi az Apple Hírek alkalmazás használatát.
- **Konfigurációs profil módosítása** – Engedélyezi a felhasználó számára a konfigurációs profilok telepítését.

## <a name="password"></a>Jelszó
-     **Jelszó megkövetelése** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
-     **Egyszerű jelszavak** – Engedélyezi az egyszerű jelszavak (például a 0000 és az 1234) használatát.
-     **Kért jelszótípus** – A kért jelszó típusát határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.
-     **Nem alfanumerikus karakterek száma a jelszóban** – Adja meg, hogy hány szimbólumkarakternek (például **#** vagy **@**) kell szerepelnie a jelszóban.
-     **Jelszó minimális hossza** – Meghatározza, hogy legalább hány karakterből álljon a jelszó.
-     **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Meghatározza, hogy hány sikertelen bejelentkezési kísérlet után törlődnek az eszközön lévő adatok.
-     **Jelszó kérése ennyi perccel a képernyőzárolás után**<sup>1</sup> – Azt határozza meg, hogy az eszköz mennyi időt tölthet üresjáratban, mielőtt a felhasználónak újra meg kellene adnia a jelszavát.
-     **Képernyőzárolás legfeljebb ennyi perc inaktivitás után**<sup>1</sup> – Ennyi perc elteltével kapcsol ki a kijelző.
-     **Jelszó érvényessége (nap)** – Meghatározza, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát.
-     **Korábbi jelszavak újbóli használatának tiltása** – Azt határozza meg, hogy az eszköz hány korábban használt jelszót jegyezzen meg.
-     **Ujjlenyomattal történő zárolásfeloldás engedélyezése** – Engedélyezi az erre alkalmas eszközök zárolásának ujjlenyomattal történő feloldását.

<sup>1</sup>Ha a **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** és a **Jelszó kérése legfeljebb ennyi perccel a képernyőzárolás után** beállítást is konfigurálja, akkor a rendszer egymást követően alkalmazza őket. Ha például mindkét beállítást az **5** perc értékre állítja be, a képernyő 5 perc után automatikusan ki fog kapcsolni, és az eszköz további 5 perc után lesz zárolva. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában az eszköz 5 perccel azután lesz zárolva, hogy a felhasználó kikapcsolta a képernyőt.

## <a name="app-store-doc-viewing-gaming"></a>Alkalmazás-áruház, dokumentumok megtekintése, játékok


-   **Alkalmazás-áruház (csak felügyelt eszköz esetén)** – Letiltja az alkalmazás-áruház elérését a felügyelt eszközökön.
-     **Alkalmazás-áruház elérésére szolgáló jelszó** – A felhasználóktól jelszót kér, mielőtt hozzáférhetnének az alkalmazás-áruházhoz.
-     **Alkalmazáson belüli vásárlás** – Engedélyezi a futó alkalmazásokból történő áruházi vásárlást.
-     **Automatikus alkalmazásletöltések (csak felügyelt)** -
-     **Felnőtteknek szánt iTunes-tartalom (zene, podcast vagy hírek)** – Engedélyezi a felnőttnek minősített áruházi tartalom elérését az eszköz számára.
-     **Az iBook áruházban „Erotika” címkével megjelölt tartalmak letöltése** – Engedélyezi a felhasználó számára az iBooks áruházban erotikus tartalomként megjelölt tartalom letöltését.
-     **Céges dokumentumok megtekintése a nem felügyelt alkalmazásokban** – Engedélyezi a vállalati dokumentumok tetszőleges alkalmazásban való megtekintését.<br>**Példa:** Szeretné megakadályozni, hogy a felhasználók fájlokat mentsenek a OneDrive alkalmazásból a Dropbox alkalmazásba. Állítsa be ezt a beállítást „Nem” értékre. Miután az eszköz megkapja a házirendet (például újraindítás után), a továbbiakban nem engedélyezi a mentést.
-     **Nem céges dokumentumok megtekintése a céges alkalmazásokban** – Engedélyezi bármilyen dokumentum megtekintését a felügyelt céges alkalmazásokban.
-     **AirDrop kezelése nem felügyelt célként** – Letiltja a felügyelt alkalmazásokból az AirDrop segítségével történő adatküldést. az Airdrop szolgáltatással való adatküldés lehetőségét.
-     **Game Center-beli ismerősök hozzáadása (csak felügyelt)** – Engedélyezi a felhasználó számára, hogy felvegyen ismerősöket a Game Centerben.
-     **Game Center (csak felügyelt)** – Engedélyezi vagy letiltja a Game Center alkalmazás használatát.
-     **Több résztvevős játékok (csak felügyelt eszköz esetén)** – Engedélyezi a felhasználó számára, hogy több résztvevős játékokat játsszon az eszközön.
-     **Besorolási régió** – Válassza ki, hogy melyik besorolási régióra vonatkozóan kívánja konfigurálni az engedélyezett letöltéseket, majd adja meg, hogy milyen besorolású **Filmek** és **Tévéműsorok** letöltését engedélyezi.
-     **Alkalmazások** – Válassza ki, hogy milyen korhatár-besorolású alkalmazásokat tölthessenek le a felhasználók (a **Minden alkalmazás engedélyezése** lehetőséget is választhatja).

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára.
A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet, igény szerint az alkalmazás kiadóját, valamint az alkalmazás alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha meg szeretné adni egy alkalmazás URL-címét alkalmazások listájában, használja a következő formátumot:

Keresőmotor segítségével keresse meg az iTunes alkalmazás-áruházban használni kívánt alkalmazást, és nyissa meg az alkalmazás lapját.
Másolja a vágólapra a lap URL-címét, és használja ezt az URL-címet az engedélyezett és a letiltott alkalmazások listájának, illetve a kioszkmódban futtatni kívánt alkalmazásoknak a konfigurálásához.
A tiltott alkalmazások beállításait tartalmazó eszközprofilokat hozzá kell rendelni a kívánt felhasználócsoportokhoz.

Példa: Keressen rá az iPad Microsoft Word alkalmazásra. Ebben az esetben a következő URL-címet használja: https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Az iTunes szoftverrel is megkeresheti az alkalmazást, majd a **Hivatkozás másolása** parancs használatával beszerezheti az alkalmazás URL-címét.



### <a name="additional-options"></a>További beállítások

Az **Importálás** gombra kattintva egy CSV formátumú fájlt is beolvashat. Ennek a következő formátumúnak kell lennie: <*az alkalmazás URL-címe*>, <*az alkalmazás neve*>, <*az alkalmazás kiadója*>. Az **Exportálás** gombra kattintva egy olyan CSV-fájlt hozhat létre, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.

## <a name="show-or-hide-apps"></a>Alkalmazások megjelenítése vagy elrejtése

A megjelenített és az elrejtett alkalmazások listáján konfigurálhatja valamelyiket a következő listák közül (ennek feltétele, hogy a felügyelt eszközökön az iOS 9.3-as vagy újabb verziója fusson).

A **Rejtett alkalmazások** listája – Itt felsorolhatja azokat az alkalmazásokat, amelyek rejtve lesznek a felhasználók számára. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
A **Megjelenített alkalmazások** listája – Ebben megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

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


## <a name="cellular"></a>Mobil
-     **Adatroaming** – Engedélyezi adatroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik.
-     **Barangolás közbeni globális háttérbeli adatbeolvasás** – Engedélyezi az eszköz számára a mobilhálózati roaming közben történő adatlehívást, például az e-mailek lekérését.
-     **Hangtárcsázás** – Engedélyezi a hangtárcsázási funkciót az eszközön.
-     **Hangroaming** – Engedélyezi a hangroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik.
-     **Alkalmazások mobil adatforgalmi beállításainak módosítása (csak felügyelt)** – Engedélyezi, hogy a felhasználó szabályozza, mely alkalmazások bonyolíthassanak le mobilhálózati adatforgalmat.

## <a name="cloud-and-storage"></a>Felhő és tárolás
-     **Biztonsági mentés az iCloudba** – Engedélyezi, hogy a felhasználó biztonsági mentést készítsen az iCloudba az eszközről.
-     **Dokumentumok iCloudba történő szinkronizálása (csak felügyelt eszköz esetén)** – Engedélyezi a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére.
-     **Fényképadatfolyamok iCloudba történő szinkronizálása** – A felhasználók engedélyezhetik a **Saját fotóstreamet** az eszközeiken, amely lehetővé teszi a fényképeknek az iClouddal való szinkronizálását, így a fényképek elérhetővé válnak a felhasználó összes eszközén.
-     **Biztonsági másolatok titkosítása** – Megköveteli az eszköz minden biztonsági másolatának titkosítását.
-     **iCloud-fotókönyvtár** – A **Nem** értékre állítva letilthatja a felhasználói fényképek és videók felhőben való tárolását lehetővé tevő iCloud-fotókönyvtár használatát.    Minden olyan fénykép, amely nincs teljes egészében letöltve az eszközre az iCloud-fotókönyvtárból, el lesz távolítva az eszközről, ha a beállítás a **Nem** értékre van állítva.
-     **Felügyelt alkalmazások szinkronizálása a felhővel** – Engedélyezi, hogy az Intune-nal felügyelt alkalmazások adatokat szinkronizáljanak a felhasználó iCloud-fiókjával.
-     **Megosztott fotóstream** – A **Nem** értékre állítva letilthatja az **iCloud-fotómegosztást** az eszközön.
-     **Tevékenység folytatása** – Lehetővé teszi, hogy a felhasználó folytassa az iOS-eszközön vagy egy másik macOS rendszerű gépen elkezdett munkát (átadás).

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonóm egyalkalmazásos mód (csak felügyelt)

Ezekkel a beállításokkal konfigurálhatja az iOS-es eszközöket megadott alkalmazások autonóm egyalkalmazásos módban való futtatására. Ha ez a mód konfigurálva van, és az alkalmazást elindítják, az eszközön nem lehet másik alkalmazást futtatni. Célszerű például így konfigurálni az olyan alkalmazásokat, amelyekkel a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

### <a name="settings"></a>Beállítások

- **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak az ezen a lapon található alkalmazáslistában megjelenő nevét.
- **Alkalmazás csomagazonosítója** – Itt adhatja meg az alkalmazás csomagazonosítóját. Segítséget a jelen témakörben alább található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.

Az alkalmazásnevek és a csomagazonosítók megadása után az alkalmazást a **Hozzáadás** lehetőség választásával adhatja hozzá a listához.

- **Importálás** – Importálhat egy vesszővel tagolt (.csv kiterjesztésű) fájlt, amely az alkalmazások nevét és a hozzájuk tartozó csomagazonosítókat tartalmazza.
- **Exportálás** – Az alkalmazásneveket és a hozzájuk tartozó csomagazonosítókat egy vesszővel tagolt (.csv kiterjesztésű) fájlba exportálhatja.

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Csomagazonosító-referencia beépített iOS-alkalmazásokhoz

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, lépjen kapcsolatba a szoftver gyártójával.

|||
|-|-|
|Alkalmazás neve|Csomagazonosító|
|Alkalmazásáruház|com.apple.AppStore|
|Számológép|com.apple.calculator|
|Naptár|com.apple.mobilecal|
|Fényképezőgép|com.apple.camera|
|Óra|com.apple.mobiletimer|
|Iránytű|com.apple.compass|
|Névjegyek|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Barátok keresése|com.apple.mobileme.fmf1|
|iPhone keresése|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Állapot|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Térképek|com.apple.Maps|
|Üzenetek|com.apple.MobileSMS|
|Zene|com.apple.Music|
|Hírek|com.apple.news|
|Megjegyzések|com.apple.mobilenotes|
|Számok|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotók|com.apple.mobileslideshow|
|Podcastok|com.apple.podcasts|
|Emlékeztetők|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Beállítások|com.apple.Preferences|
|Részvények|com.apple.stocks|
|Tippek|com.apple.tips|
|Videók|com.apple.videos|
|Hangjegyzetek|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Időjárás|com.apple.weather|


## <a name="kiosk"></a>Kioszkmód
-     **Aktiválási zár** – Engedélyezi az aktiválási zárat a felügyelt iOS-eszközökön.
-     **Kioszkmódban futó alkalmazás** – A **Felügyelt alkalmazás** lehetőséget választva egy az Intune-ba már felvett alkalmazást adhat meg, az **Áruházbeli alkalmazás** lehetőséget választva egy áruházbeli alkalmazás URL-címét. Az itt megadotton kívül más alkalmazás nem futtatható az eszközön. További segítségért olvassa el a jelen témakörben alább található „Alkalmazásáruházak URL-címének megadása” című részt.
-     **AssistiveTouch** – Engedélyezi vagy letiltja az **AssistiveTouch** kisegítő beállítást, amely segít a nehézségekkel küzdő felhasználóknak a képernyőn elvégezhető kézmozdulatok végrehajtásában.
-     **Színinvertálás** – Engedélyezi vagy letiltja a Színinvertálás kisegítő beállítást, amellyel módosíthatja a képernyőt a látásukban korlátozott felhasználók számára.
-     **Monó hang** – Engedélyezi vagy letiltja a Monó hang kisegítő beállítást.
-     **VoiceOver** – Engedélyezi vagy letiltja a **VoiceOver** kisegítő beállítást, amely hangosan felolvassa az eszköz képernyőjén megjelenő szöveget.
-     **Nagyítás** – Engedélyezi vagy letiltja a **Nagyítás** kisegítő beállítást, amellyel a felhasználó érintéssel nagyíthatja az eszköz képernyőjén megjelenő tartalmat.
-     **Automatikus zárolás** – Engedélyezi vagy letiltja az eszköz automatikus zárolását.
-     **Csengés kapcsolója** – Engedélyezheti vagy letilthatja a csengő kapcsolóját (az elnémítót) az eszközön.
-     **Képernyő elforgatása** – Engedélyezi vagy letiltja a képernyő tájolásának módosítását az eszköz elforgatásakor.
-     **Képernyőalvás gombja** – Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.
-     **Érintésvezérlés** – Engedélyezi vagy letiltja az érintőképernyő használatát az eszközön.
-     **Hangerőgombok** – Engedélyezi vagy letiltja a hangerőszabályzó gombok használatát az eszközön.
-     **AssistiveTouch-vezérlés** – Engedélyezi vagy letiltja az AssistiveTouch funkció beállításának módosítását.
-     **Színinvertálás vezérlője** – Engedélyezi vagy letiltja a színinvertálási funkció beállításainak módosítását.
-     **Kijelölt szöveg felolvasása** – Engedélyezi vagy letiltja a Kijelölés felolvasása kisegítő beállítást, amellyel felolvastatható a felhasználó által kijelölt szöveg.
-     **VoiceOver vezérlője** – Engedélyezi vagy letiltja a VoiceOver funkció beállítását (például hogy milyen gyorsan történjen a képernyőn látható szöveg felolvasása).
-     **Nagyítás vezérlője** – Engedélyezi vagy letiltja a nagyítási funkció működésének felhasználó általi beállítását.

>[!NOTE]
> Az iOS-eszközök Kioszk módra való konfigurálása előtt felügyelt módba kell állítania az eszközt az Apple Configurator eszközzel vagy az Apple Device Enrollment Program készülékregisztráció-kezelővel. Az Apple Configurator eszközzel kapcsolatos további információkat az Apple dokumentációjában talál.
>Ha a megadott iOS-alkalmazás a profil hozzárendelése után települ, az eszköz mindaddig nem lép kioszkmódba, amíg újra nem indítják.

## <a name="safari"></a>Safari
-     **Safari (csak felügyelt eszköz esetén)** – Ez a beállítás azt határozza meg, hogy használható-e a Safari böngésző az eszközön.
-     **Automatikus kitöltés** – Engedélyezi a felhasználó számára, hogy módosítsa a böngésző automatikus kiegészítési funkciójának beállításait.
-     **Cookie-k** – Engedélyezi a cookie-k használatát a böngésző számára.
-     **JavaScript** – Engedélyezi a Java-parancsfájlok futtatását a böngészőben.
-     **Csalás elleni figyelmeztetés** – Engedélyezi a csalás elleni figyelmeztetéseket a böngészőben.
-     **Előugró ablakok** – Engedélyezi vagy letiltja a böngésző előugróablak-blokkolóját.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Jelöletlen e-mail-tartományok

Az **E-mail-tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. Ha a végfelhasználó a listában nem szereplő tartományból kap e-mailt, az iOS-es Mail alkalmazásban az nem megbízhatóként lesz megjelölve.


### <a name="managed-web-domains"></a>Felügyelt webtartományok

A **Webtartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. A megadott tartományokból letöltött dokumentumok felügyeltnek minősülnek. Ez a beállítás csak a Safari böngészővel letöltött dokumentumokra vonatkozik.


### <a name="safari-password-auto-fill-domains"></a>Jelszavak automatikus kitöltése a Safariban

A **Tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. A felhasználók csak a listában szereplő URL-címekhez tartozó webes jelszavakat menthetnek. Ez a beállítás csak a Safari böngészőre és az iOS 9.3 vagy későbbi verzióit futtató eszközökre vonatkozik felügyelt módban. Ha egyetlen URL-címet sem ad meg, jelszavakat minden webhelyhez lehetséges menteni.


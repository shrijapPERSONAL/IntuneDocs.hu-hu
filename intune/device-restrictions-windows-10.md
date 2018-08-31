---
title: Eszközkorlátozási beállítások Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A cikk tájékoztatást nyújt a Microsoft Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a Windows 10 rendszerű eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 42e0798b0c2941d9ea45e75b367b69bc7dab548f
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321220"
---
# <a name="device-restriction-for-windows-10-and-newer-settings-in-intune"></a>Eszközkorlátozási beállítások Windows 10-hez (és újabb rendszerekhez) az Intune-ban
A cikk bemutatja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók Windows 10 rendszerű eszközökhöz.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Általános
- **Képernyőfelvétel (csak mobileszköz)** – A felhasználó képként rögzítheti a képernyőn látható tartalmat.
- **Másolás és beillesztés (csak mobileszköz)** – Engedélyezi az alkalmazások közötti másolási és beillesztési műveletet az eszközön.
- **Regisztráció manuális törlése** – Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
   - A rendszer nem alkalmazza ezt a szabályzatbeállítást, ha a számítógép az Azure Active Directoryhoz van csatlakoztatva, és engedélyezve van az automatikus regisztráció. 
   - A szabályzatbeállítás a Windows 10 Home rendszerű számítógépekre nem vonatkozik.
- **Főtanúsítvány manuális telepítése (csak mobileszköz)** – Letiltja a felhasználó számára a főtanúsítványok és a köztes szolgáltatói tanúsítványok manuális telepítését.

- **Kamera** – Engedélyezi vagy letiltja az eszköz kamerájának használatát.
- **OneDrive-fájlszinkronizálás** – Letiltja az eszköz fájljainak OneDrive-ba való szinkronizálását.
- **Cserélhető tároló** – Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.
- **Földrajzi hely** – Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.
- **Internetkapcsolat megosztása** – Engedélyezi az internetkapcsolat megosztását az eszközön.
- **Telefon alaphelyzetbe állítása** – Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait.
- **USB-kapcsolat (csak mobileszköz)** – Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.
- **Lopásgátló üzemmód (csak mobileszköz)** – Itt az állítható be, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.
- **Cortana** – Engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztenst.
- **Hangrögzítés (csak mobileszköz)** – Engedélyezi vagy letiltja az eszköz hangrögzítőjét.
- **Az eszköz nevének módosítása** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz nevét (csak Windows 10 mobil verzió esetén)
- **Kiépítési csomagok hozzáadása** – Megakadályozza, hogy a konfigurációs ügynök kiépítési csomagokat telepítsen.
- **Kiépítési csomagok eltávolítása** – Megakadályozza, hogy a konfigurációs ügynök kiépítési csomagokat távolítson el.
- **Eszközfelderítés** – Letiltja az eszköz más eszközök általi felderíthetőségét.
- **Feladatváltó (csak mobileszköz)** – Letiltja a feladatváltót az eszközön.
- **SIM-kártyahibát jelző párbeszédpanel (csak mobileszköz)** – Letiltja a hibaüzenetet, amely akkor jelenne meg, amikor a rendszer nem észlel SIM-kártyát az eszközön.
- **Szabadkézi munkaterület** – Megakadályozza, hogy a felhasználók hozzáférjenek a szabadkézi munkaterülethez. Ha ez a beállítás nincs konfigurálva, a szabadkézi munkaterület engedélyezve lesz (a funkció elérhető), így a felhasználók a zárolási képernyőn is elérhetik azt.
- **Automatikus újbóli üzembe helyezés** – Lehetővé teszi a rendszergazdai jogosultságokkal rendelkező felhasználóknak, hogy az eszköz zárolási képernyőjén a **CTRL + Win + R** billentyűkombinációval törölhessék az összes felhasználói adatot és beállítást. Ennek hatására automatikusan megtörténik az eszköz újbóli konfigurálása és regisztrálása felügyeletre.

## <a name="password"></a>Jelszó
-   **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -   **Kért jelszótípus** – Azt határozza meg, hogy a jelszó csak számokból vagy számokból és betűkből állhat.
    -   **Jelszó minimális hossza** – Csak a Windows 10 Mobile verzióra vonatkozik.
    -   **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Windows 10 rendszerű eszközök esetében: ha a BitLocker engedélyezve van az eszközön, akkor az a megadott számú sikertelen bejelentkezési kísérlet után a BitLocker helyreállítási módjába kerül. Ha az eszközön nincs engedélyezve a BitLocker, akkor ez a beállítás nem alkalmazható.
Windows 10 Mobile-eszközök esetében: a megadott számú sikertelen bejelentkezési kísérlet után az eszköz tartalma törlődik.
    -   **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.
    -   **Jelszó érvényessége (nap)** – Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót.
    -   **Korábbi jelszavak újbóli használatának tiltása** – Azt határozza meg, hogy az eszköz hány korábban használt jelszót jegyezzen meg.
    -   **Jelszó kérése, ha az eszköz visszatér az inaktív állapotból (csak mobil verzióban)** – Azt adja meg, hogy köteles-e a felhasználó jelszót megadni az eszköz feloldásához (csak Windows 10 Mobile esetén).
    -   **Egyszerű jelszavak** – Lehetővé teszi egyszerű jelszavak használatát, például 1111 vagy 1234. Ez a beállítás a Windows-képjelszavak használatát is engedélyezi vagy letiltja.
-   **Titkosítás** – Titkosítás engedélyezése a megcélzott eszközökön.

## <a name="personalization"></a>Személyre szabás

- **Az asztal háttérképének URL-címe (csak asztali verzió)** – A Windows asztali háttérképeként használandó JPEG formátumú kép URL-címének megadása. A felhasználók ezt nem tudják módosítani.

## <a name="privacy"></a>Személyes adatok védelme

-   **Bemenet személyre szabása** – Letiltja a felhőalapú beszédszolgáltatások használatát a Cortanához, a diktáláshoz vagy a Microsoft Áruház alkalmazásaihoz. Ha engedélyezi ezeket a szolgáltatásokat, a Microsoft hangadatokat gyűjthet a szolgáltatás fejlesztéséhez.
-   **A társításra és adatvédelemre vonatkozó felhasználói beleegyezést kérő üzenetek automatikusa elfogadása** – Lehetővé teszi a Windowsnak, hogy automatikusan elfogadja a társítási és adatvédelmi beleegyezést kérő üzeneteket az alkalmazások futtatása közben.
- **Felhasználói tevékenységek közzététele**: A megosztott élmények és a feladatváltóban nemrég használt erőforrások megelőzéséhez ezt a beállítást **tiltsa le**.
- **Csak a helyi tevékenységek**: A csak a helyi tevékenységek alapján megosztott használat és a feladatváltóban nemrég használt erőforrások felderítésének megelőzéséhez ezt a beállítást **tiltsa le**.

Meghatározhatja azon adatok körét, amelyeket az eszközön futó összes alkalmazás elérhet. Definiálhat kivételeket alkalmazásonként az **Alkalmazásonkénti adatvédelmi kivételek** segítségével.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok** – Megadhatja, hogy az alkalmazás hozzáférhet-e a felhasználó nevéhez, képéhez és kapcsolati adataihoz.
- **Háttérben futó alkalmazások** – Megadhatja, hogy az alkalmazás futhat-e a háttérben.
- **Naptár** – Megadhatja, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista** – Megadhatja, hogy az alkalmazás hozzáférhet-e a híváslistához.
- **Kamera** – Megadhatja, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek** – Megadhatja, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **E-mail** – Megadhatja, hogy az alkalmazás hozzáférhet-e az e-mailekhez, és küldhet-e e-mailt.
- **Tartózkodási hely** – Megadhatja, hogy az alkalmazás hozzáférhet-e a tartózkodási hellyel kapcsolatos adatokhoz.
- **Üzenetkezelés** – Megadhatja, hogy az alkalmazás olvashat és küldhet-e SMS- és MMS-üzeneteket.
- **Mikrofon** – Megadhatja, hogy az alkalmazás használhatja-e a mikrofont.
- **Mozgásérzékelő** – Megadhatja, hogy az alkalmazás hozzáférhet-e az eszköz mozgásérzékelőjének adataihoz.
- **Értesítések** – Megadhatja, hogy az alkalmazás hozzáférhet-e az értesítésekhez.
- **Telefon** – Megadhatja, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennák** – Egyes alkalmazások adatokat küldenek és fogadnak az eszközben lévő antennákkal (például Bluetooth-antennával). Az ilyen alkalmazásoknak szüksége lehet az antennák be- és kikapcsolására. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok** – Megadhatja, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök** – Megadhatja, hogy az alkalmazás használhat-e megbízható eszközöket (már csatlakoztatott, illetve a PC-hez, táblagéphez vagy telefonhoz gyárilag tartozó hardvereket). Például: televíziók és kivetítők.
- **Visszajelzés és diagnosztika** – Megadhatja, hogy az alkalmazás hozzáférhet-e a diagnosztikai adatokhoz.
- **Szinkronizálás eszközökkel** – Megadhatja, hogy az alkalmazás oszthat-e meg és szinkronizálhat-e adatokat automatikusan olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az adott PC-vel, táblagéppel vagy telefonnal.

## <a name="per-app-privacy-exceptions"></a>Alkalmazásonkénti adatvédelmi kivételek

Az egyes alkalmazásokhoz beállíthat az alapértelmezett adatvédelmi beállításoktól eltérő adatvédelmi működést.

- **Csomag neve** – Az alkalmazás csomagcsaládjának neve.
- **Alkalmazás neve** – Az alkalmazás neve.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok** – Megadhatja, hogy az alkalmazás hozzáférhet-e a felhasználó nevéhez, képéhez és kapcsolati adataihoz.
- **Háttérben futó alkalmazások** – Megadhatja, hogy az alkalmazás futhat-e a háttérben.
- **Naptár** – Megadhatja, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista** – Megadhatja, hogy az alkalmazás hozzáférhet-e a híváslistához.
- **Kamera** – Megadhatja, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek** – Megadhatja, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **E-mail** – Megadhatja, hogy az alkalmazás hozzáférhet-e az e-mailekhez, és küldhet-e e-mailt.
- **Tartózkodási hely** – Megadhatja, hogy az alkalmazás hozzáférhet-e a tartózkodási hellyel kapcsolatos adatokhoz.
- **Üzenetkezelés** – Megadhatja, hogy az alkalmazás olvashat és küldhet-e SMS- és MMS-üzeneteket.
- **Mikrofon** – Megadhatja, hogy az alkalmazás használhatja-e a mikrofont.
- **Mozgásérzékelő** – Megadhatja, hogy az alkalmazás hozzáférhet-e az eszköz mozgásérzékelőjének adataihoz.
- **Értesítések** – Megadhatja, hogy az alkalmazás hozzáférhet-e az értesítésekhez.
- **Telefon** – Megadhatja, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennák** – Egyes alkalmazások adatokat küldenek és fogadnak az eszközben lévő antennákkal (például Bluetooth-antennával). Az ilyen alkalmazásoknak szüksége lehet az antennák be- és kikapcsolására. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok** – Megadhatja, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök** – Megadhatja, hogy az alkalmazás használhat-e megbízható eszközöket (már csatlakoztatott, illetve a PC-hez, táblagéphez vagy telefonhoz gyárilag tartozó hardvereket). Például: televíziók és kivetítők.
- **Visszajelzés és diagnosztika** – Megadhatja, hogy az alkalmazás hozzáférhet-e a diagnosztikai adatokhoz.
- **Szinkronizálás eszközökkel** – Megadhatja, hogy az alkalmazás oszthat-e meg és szinkronizálhat-e adatokat automatikusan olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az adott PC-vel, táblagéppel vagy telefonnal.

## <a name="locked-screen-experience"></a>Zárolási képernyő felülete

- **Műveletközpont értesítései (csak mobileszköz)** – Engedélyezi a Műveletközpont értesítéseinek megjelenését az eszköz zárolási képernyőjén (csak Windows 10 Mobile esetén).
- **Zárolási képernyő URL-címe (csak asztali verzióban)** – A Windows zárolási képernyőjének háttérképeként használandó JPEG formátumú kép URL-címét adja meg. A felhasználók ezt nem tudják módosítani.
-   **Felhasználó által konfigurálható képernyő-időkorlát (csak mobilon)** – Engedélyezi a felhasználóknak az időtartam konfigurálását 
-   **Cortana zárolt képernyőn (csak asztali verzió)** – Nem engedélyezi, hogy a felhasználó interakcióba lépjen a Cortanával, ha a képernyő zárolva van (csak Windows 10 asztali verziónál).
-   **Bejelentési értesítések zárolt képernyőn** – Riasztások megjelenítésének letiltása az eszköz zárolási képernyőjén.
-   **Képernyő időkorlátja (csak mobilon)** – A képernyő zárolási idejének megadása másodpercben, aminek elteltével kikapcsol.

## <a name="app-store"></a>Alkalmazásáruház

-   **Alkalmazás-áruház (csak mobileszköz)** – Engedélyezi vagy letiltja az alkalmazásáruházat a Windows 10 Mobile rendszerű eszközökön.
-   **Áruházból származó alkalmazások automatikus frissítése** – Engedélyezi a Microsoft Áruházból származó alkalmazások automatikus frissítését.
-   **Megbízható alkalmazás telepítése** – Engedélyezi a megbízható tanúsítvánnyal aláírt alkalmazások közvetlen telepítését.
-   **Fejlesztői zárolás feloldása** – Engedélyezi, hogy a Windows fejlesztői beállításait (például alkalmazások közvetlen telepítését) a végfelhasználók megváltoztassák.
-   **Megosztott felhasználói alkalmazásadatok** – Engedélyezi, hogy ugyanazon az eszközön a felhasználók megoszthassák egymás között az alkalmazásadatokat.
-   **Csak privát áruház használata** – Ennek a beállításnak az engedélyezésével a felhasználók csak a privát áruházból származó alkalmazásokat tölthetik le.
-   **Áruházból származó alkalmazások indítása** – Letiltja az összes előre telepített vagy Microsoft Áruházból letöltött alkalmazást az eszközön.
-   **Alkalmazásadatok telepítése a rendszerköteten** – Megakadályozza, hogy az alkalmazások adatokat tároljanak az eszköz rendszerkötetén.
-   **Alkalmazások telepítése a rendszermeghajtón** – Megakadályozza, hogy az alkalmazások adatokat tároljanak az eszköz rendszermeghajtóján.
-   **Játékvideó-rögzítő (csak asztali verzióban)** – Meghatározza, hogy engedélyezett-e játékok rögzítése és közvetítése.
-   **Csak áruházból származó alkalmazások** – Meghatározza, hogy a felhasználók telepíthetnek-e alkalmazásokat az alkalmazás-áruháztól eltérő forrásokból.

## <a name="edge-browser"></a>Microsoft Edge böngésző

-   **Microsoft Edge böngésző (csak mobil)** – Engedélyezi az Edge böngésző használatát az eszközön.
-   **Címsor legördülő funkciója (csak asztali gép)** – Ezzel akadályozhatja meg, hogy a Microsoft Edge megjelenítse a javaslatok listáját egy legördülő menüben gépelés közben. Ezzel minimalizálhatja a hálózati sávszélességnek a Microsoft Edge és a Microsoft szolgáltatásai közötti használatát.
-   **Kedvencek szinkronizálása a Microsoft-böngészők között (csak asztali gépek)** – Lehetővé teszi, hogy a Windows szinkronizálja a kedvenceket az Internet Explorer és a Microsoft Edge között.
-   **„Do Not Track” fejlécek küldése** – Arra konfigurálja a Microsoft Edge böngészőt, hogy Do Not Track (Követés letiltása) fejléceket küldhessen a felhasználók által meglátogatott webhelyeknek.
-   **Cookie-k** – Engedélyezi a böngészőnek, hogy mentse az internetről érkező cookie-kat az eszközre.
-   **JavaScript** – Engedélyezi a szkriptek (például a JavaScript) futtatását a Microsoft Edge böngészőben.
-   **Előugró ablakok** – Blokkolja az előugró ablakokat a böngészőben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Keresési javaslatok** – Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
-   **Intranetes forgalom átirányítása az Internet Explorerbe** – Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Automatikus kitöltés** – Engedélyezi a felhasználók számára, hogy módosítsák a böngésző automatikus kiegészítési funkciójának beállításait (csak a Windows 10 asztali verzióra vonatkozik).
-   **Jelszókezelő** – Engedélyezi vagy letiltja a Microsoft Edge böngésző Jelszókezelő szolgáltatását.
-   **Vállalati üzemmód webhelylistájának helye** – Megadja, hogy hol található a Vállalati üzemmódban megnyíló webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.<br>(Csak a Windows 10 asztali verzió.)
-   **Fejlesztői eszközök** – Megakadályozza, hogy a végfelhasználók megnyithassák a Microsoft Edge fejlesztői eszközeit.
-   **Bővítmények** – Engedélyezi, hogy a végfelhasználók Microsoft Edge-bővítményeket telepítsenek az eszközön.
-   **InPrivate-böngészés** – Megakadályozza, hogy a végfelhasználók InPrivate-böngészési munkamenetet nyissanak meg.
-   **Első futtatáskori oldal megjelenítése** – Megakadályozza a bemutató lap megjelenítését a Microsoft Edge első futtatásakor.
    -   **Első futtatás URL-címe** – Megadhatja annak a lapnak az URL-címét, amely akkor jelenik meg, amikor a felhasználó első alkalommal futtatja a Microsoft Edge böngészőt (csak Windows 10 mobil verziónál).
-   **Kezdőlapok** – Azoknak a webhelyeknek a listája, amelyek kezdőlapokként szeretne megjeleníteni a Microsoft Edge böngészőben (csak asztali verzióban).
-   **Kezdőlap módosítása** – Engedélyezheti a felhasználóknak, hogy megváltoztassák a Microsoft Edge megnyitásakor megjelenő kezdőlapokat. A Kezdőlapok beállítással hozhatja létre a Microsoft Edge indításakor megjelenő lapot vagy lapok listáját.
-   **Az about:flags laphoz való hozzáférés letiltása** – Megakadályozza, hogy a végfelhasználó hozzáférhessen a Microsoft Edge about:flags lapjához, amely a fejlesztői és kísérleti beállításokat tartalmazza.
-   **WebRTC LocalHost IP-címe** – Letiltja a felhasználó localhost IP-címének megjelenítését a WebRTC protokollal történő telefonhívások esetén.
-   **Alapértelmezett keresőmotor** – Meghatározza az alapértelmezetten használandó keresőmotort. A végfelhasználók ezt az értéket bármikor módosíthatják.
-   **Böngészési adatok törlése kilépéskor** – Előzmények és böngészési adatok törlése, amikor a felhasználó bezárja a Microsoft Edge böngészőt.
-   **Adatgyűjtés élő csempéhez** – Leállítja a Windows élő csempéből történő adatgyűjtését, amikor a felhasználók kitűznek az Microsoft Edge böngészőből egy webhelyet a Start menübe.
-  **Kedvencek lista** – A kedvencek fájl elérési útját adja meg. Például: http://contoso.com/favorites.html.
-  **A kedvencek módosításának korlátozása** – Ha ezt **Letiltva** értékre állítja, a felhasználók nem használhatják a Kedvencek listában a hozzáadás, importálás, rendezés és szerkesztés funkciókat. 

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **SmartScreen a Microsoft Edge böngészőhöz** – Az Edge SmartScreen webhely- és fájlletöltésekhez való hozzáférésének engedélyezése.
- **Rosszindulatú webhelyelérés** - Meggátolja a felhasználókat abban, hogy figyelmen kívül hagyják a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja a webhely elérését.
- **Ellenőrizetlen fájlletöltés** - Meggátolja a felhasználókat abban, hogy figyelmen kívül hagyják a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja az ellenőrizetlen fájlok letöltését.

## <a name="search"></a>Keresés
- **Biztonságos keresés (csak mobileszközökön)** – Meghatározza, hogy a Cortana hogyan szűrje a felnőtt tartalmat a keresési eredményekben. A megadható értékek a **Szigorú** és a **Közepes**, vagy engedélyezhető, hogy a végfelhasználó állítsa be az értékét.
- **Internetes keresési találatok megjelenítése** – Letiltja vagy engedélyezi az internetes találatok megjelenítését az eszközön való kereséskor.

## <a name="cloud-and-storage"></a>Felhő és tárolás
-   **Microsoft-fiók** – Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.
-   **Nem Microsoft-fiók** – Lehetővé teszi, hogy a felhasználó olyan e-mail-fiókokat vegyen fel az eszközön, amelyek nincsenek Microsoft-fiókhoz társítva.
-   **Microsoft-fiók beállításszinkronizálása** – Lehetővé teszi a Microsoft-fiókhoz kapcsolódó eszköz- és alkalmazásbeállítások szinkronizálását az eszközök között.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

-   **Mobilhálózati adatcsatorna** – Megakadályozza a felhasználók adathasználatát, például a webböngészést, amikor mobilhálózathoz vannak kapcsolódva. 
-   **Adatroaming** – Engedélyezi a hálózatok közötti roamingot adatok elérése közben.
-   **Mobilhálózati VPN** – Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.
-   **Mobilhálózati VPN-barangolás** – Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming közben.
-   **Bluetooth** – Azt szabályozza, hogy a felhasználó engedélyezheti és konfigurálhatja-e a Bluetooth-t az eszközön.
-   **Bluetooth-észlelhetőség** – Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök számára.
-   **Előzetes Bluetooth-párosítás** – Lehetővé teszi meghatározott Bluetooth-eszközök konfigurálását, hogy automatikus legyen a gazdaeszközzel való párosításuk.
-   **Bluetooth-hirdetés** – Lehetővé teszi az eszköz számára, hogy hirdetéseket fogadjon a Bluetooth-kapcsolaton.
-   **Csatlakoztatott eszközök szolgáltatás** – Kiválaszthatja, hogy engedélyezi-e a csatlakoztatott eszközök szolgáltatást, amely lehetővé teszi más Bluetooth-eszközök észlelését és a hozzájuk való kapcsolódást.
-   **NFC** – Lehetővé teszi a felhasználó számára az eszköz NFC funkciójának engedélyezését és konfigurálását.
-   **Wi-Fi** – Lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja a Wi-Fi funkciót az eszközön (csak Windows 10 Mobile esetén).
-   **Automatikus csatlakozás Wi-Fi-elérési pontokhoz** – Engedélyezi az eszközön az ingyenes Wi-Fi-elérési pontokhoz történő automatikus csatlakozást és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadását.
-   **Wi-Fi manuális konfigurálása** – Azt szabályozza, hogy a felhasználó konfigurálhat-e saját Wi-Fi-kapcsolatokat, vagy csak a Wi-Fi-profillal konfigurált kapcsolatokat használhatja (csak Windows 10 Mobile esetén).
-   **Wi-Fi-ellenőrzési időköz** – Meghatározza, hogy az eszközök milyen gyakorisággal keressenek Wi-Fi-hálózatokat. Adjon meg egy 1 (leggyakoribb) és 500 (legritkább) közötti értéket.
-   **Bluetooth-engedélyezett szolgáltatások** – Az engedélyezett Bluetooth-szolgáltatások és -profilok meghatározása hexadecimális sztringekként.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

-   **Gépház alkalmazás** – Letiltja a hozzáférést a Windows Gépház alkalmazásához.
    -   **Rendszer** – Letiltja a hozzáférést a Gépház alkalmazás Rendszer területéhez.
        -   **Energiagazdálkodási és alvási beállítások módosítása (csak asztali verzióban)** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz energiagazdálkodási és alvási beállításait.
    -   **Eszközök** – Letiltja a hozzáférést a Gépház alkalmazás Eszközök területéhez.
    -   **Hálózat és internet** – Letiltja a hozzáférést a Gépház alkalmazás Hálózat és internet területéhez.
    -   **Személyre szabás** – Letiltja a hozzáférést a Gépház alkalmazás Személyre szabás területéhez.
    -   **Fiókok** – Letiltja a hozzáférést a Gépház alkalmazás Fiókok területéhez.
    -   **Idő és nyelv** – Letiltja a hozzáférést a Gépház alkalmazás Idő és nyelv területéhez.
        -   **Rendszeridő módosítása** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz rendszeridejét.
        -   **Területi beállítások módosítása (csak asztali verzióban)** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz területi beállításait.
        -   **Nyelvi beállítások módosítása (csak asztali verzióban)** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz nyelvi beállításait.
    -   **Játékok** – Letiltja a hozzáférést a hozzáférést a Gépház alkalmazás Játékok területéhez.
    -   **Könnyű kezelés** – Letiltja a hozzáférést a Gépház alkalmazás Könnyű kezelés területéhez.
    -   **Adatvédelem** – Letiltja a hozzáférést a Gépház alkalmazás Adatvédelem területéhez.
    -   **Frissítés és biztonság** – Letiltja a hozzáférést a Gépház alkalmazás Frissítés és biztonság területéhez.

## <a name="start"></a>Indítás

- **Alkalmazások levétele a tálcáról** – Megakadályozza, hogy a felhasználó alkalmazásokat távolítson el a Start menüből.
- **Dokumentumok a Start menüben** – A Windows Start menü Dokumentumok mappájának megjelenítése vagy elrejtése.
- **Letöltések a Start menüben** – A Windows Start menü Letöltések mappájának megjelenítése vagy elrejtése.
- **Fájlkezelő a Start menüben** – A Fájlkezelő alkalmazás megjelenítése vagy elrejtése a Windows Start menüjében.
- **Otthoni csoport a Start menüben** – A Windows Start menü Otthoni csoport mappájának megjelenítése vagy elrejtése.
- **Zene a Start menüben** – A Windows Start menü Zene mappájának megjelenítése vagy elrejtése.
- **Hálózat a Start menüben** – A Windows Start menü Hálózat mappájának megjelenítése vagy elrejtése.
- **Személyes mappa a Start menüben** – A Windows Start menü Személyes mappájának megjelenítése vagy elrejtése.
- **Képek a Start menüben** – A Windows Start menü képeket tartalmazó mappájának megjelenítése vagy elrejtése.
- **Gépház a Start menüben** – A Gépház alkalmazás elrejtése vagy megjelenítése a Windows Start menüben.
- **Videók a Start menüben** – A Windows Start menü videókat tartalmazó mappájának megjelenítése vagy elrejtése.

## <a name="display"></a>Megjelenítés

- **GDI-méretezés bekapcsolása az alkalmazásoknál**
- **GDI-méretezés kikapcsolása az alkalmazásoknál**

  A GDI DPI-méretezés lehetővé teszi, hogy a nem DPI-figyelő alkalmazások monitoronként DPI-figyelővé váljanak. Megadhatja az örökölt alkalmazásokat, melyek esetében a GDI DPI-méretezés be van kapcsolva. Ha a GDI DPI-méretezés bekapcsolása és kikapcsolása egyaránt konfigurálva van egy alkalmazás esetében, akkor a méretezés ehhez az alkalmazáshoz ki lesz kapcsolva.

## <a name="kiosk-preview---obsolete"></a>Kioszk (Előzetes) – Elavult

Ezek a beállítások csak olvashatók, és nem módosíthatók. A kioszkmód a [Kioszkbeállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával konfigurálható.

A kioszkeszközök jellemzően egyetlen alkalmazást futtatnak, vagy az alkalmazások egy előre meghatározott készletét. A rendszer a felhasználóknak csak ezekhez a kioszkalkalmazásokhoz ad hozzáférést, és meggátolja az eszköz más funkcióinak és szolgáltatásainak elérését.

- **Kioszkmód** – Azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezés) – A szabályzat nem engedélyezi a teljes képernyős módot. 
  - **Egyalkalmazásos kioszk** – A profil csak egyetlen alkalmazás futtatását engedélyezi az eszköznek. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk** – A profil engedélyezi több alkalmazás futtatását az eszköznek. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amely csak a szükséges alkalmazások elérését engedélyezi, a többi alkalmazást pedig elrejti a felhasználó elől.

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk
Adja meg a következő beállításokat:

- **Felhasználói fiók** – Adja meg a kioszkalkalmazáshoz társított helyi (eszközön létező) felhasználói fiókot, egy AD-tartományi fiókot vagy az Azure AD-fiókot.
  - Helyi fiók: Adja meg így: `devicename\accountname`, `.\accountname` vagy `accountname`
  - Tartományi fiók: Adja meg így: `domain\accountname`
  - Azure AD-fiók: Adja meg így: `AzureAD\emailaddress`. Ügyeljen rá, hogy „AzureAD”-ként adja meg, mivel ez egy rögzített tartománynév. Ezt követően adja meg az Azure AD e-mail-címét. Például írja be a következőt: `AzureAD\user@contoso.onmicrosoft.com`.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha kioszk módhoz Azure AD-fiókot használ, ügyeljen rá, hogy ezt írja be: `AzureAD\user@yourorganization.com`.

- **Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)** – Adja meg a kioszkalkalmazás alkalmazásfelhasználói modellben használt azonosítóját. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk
A [többalkalmazásos kioszkeszközök](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) olyan kioszkkonfigurációt használnak, amely más beállítások mellett tartalmazza az engedélyezett alkalmazások listáját. 

Hozzon létre egy kioszkkonfigurációt a **Hozzáadás** gomb használatával (vagy válasszon egy meglévőt). Ezután adja meg a következő beállításokat:

- **Kioszkkonfiguráció neve** – Írja be a konfiguráció azonosítására szolgáló felhasználóbarát nevet.

- **Kioszkalkalmazások** – Adja meg a Start menüben elérhető alkalmazásokat. A felhasználó kizárólag a megadott alkalmazásokat fogja tudni elérni.

  - **Alkalmazástípus** – Adja meg a kioszkalkalmazás típusát:
    - **Win32-alkalmazás** – Hagyományos asztali alkalmazás. A futtatható fájlnak az eszközön érvényes teljes elérési útja szükséges.
    - **UWP-alkalmazás** - Egy univerzális Windows-alkalmazás. [Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) szükséges.

  - **Azonosító** – Adja meg a futtatható fájlnak az eszközön érvényes teljes elérési útját (Win32-alkalmazás esetén) vagy [az alkalmazás alkalmazásfelhasználói modellben használt azonosítóját (AUMID)](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (univerzális Windows-alkalmazás esetén).

- **Tálca** – Válassza az **Engedélyezés** beállítást a tálca megjelenítéséhez, vagy hagyja meg az alapértelmezett **Nincs konfigurálva** beállítást a tálca kioszkeszközön való elrejtéséhez.

- **Start menü elrendezése** – Adjon meg egy XML-fájlt, amely meghatározza, hogyan jelenjenek meg az alkalmazások a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.


  Az XML-fájlok használatáról és létrehozásáról bővebb információt a [Több alkalmazást futtató Windows 10 rendszerű kioszk létrehozása](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) című cikkben találhat.

- **Hozzárendelt felhasználók** – Adjon meg egy vagy több olyan felhasználói fiókot, amely jogosult a társított alkalmazások használatára. A fiókkal való bejelentkezéskor csak a konfigurációban meghatározott alkalmazások érhetők el. Ez lehet egy helyi fiók az eszközön, vagy egy Azure AD-fiók, amely a teljes képernyős alkalmazáshoz van társítva.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `domain\user@tenant.com` formátumot.

## <a name="windows-defender-antivirus"></a>Windows Defender víruskereső

-   **Valós idejű figyelés engedélyezése** – Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű keresését.
-   **Viselkedésfigyelés engedélyezése** – Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.
-   **Hálózatvizsgáló rendszer (NIS)** – Az NIS segít megvédeni az eszközöket a hálózatalapú támadásoktól. A Microsoft Endpoint Protection-központból származó ismert sebezhető pontok mintázatai alapján segít észlelni és blokkolni a rosszindulatú hálózati forgalmat.
-   **Minden letöltött fájl vizsgálata** – Meghatározza, hogy a Defender megvizsgálja-e az internetről letöltött összes fájlt.
-   **Microsoft-webböngészőkben betöltött szkriptek vizsgálata** – Engedélyezi a Defender számára az Internet Explorer által használt szkriptek vizsgálatát.
-   **Végfelhasználói hozzáférés a Defenderhez** – Azt szabályozza, hogy a Windows Defender kezelőfelülete el legyen-e rejtve a végfelhasználók elől.
Módosítás esetén a beállítás a felhasználó számítógépének következő újraindításakor lép érvénybe.
-   **Aláírás-frissítési időköz (óra)** – Meghatározza, hogy a Defender milyen időközönként keressen új aláírásfájlokat.
-   **Fájl- és programtevékenység figyelése** – Engedélyezi a Defender számára az eszközökön zajló a fájl- és programtevékenység figyelését.
-   **A karanténba zárt kártevők ennyi nap után törlődjenek** – A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok számát **0**-ra állítja, a kártevő a karanténban marad, és a rendszer nem távolítja el automatikusan.
-   **CPU-használati korlát ellenőrzés közben** – Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**-től **100**-ig).
-   **Archív fájlok vizsgálata** – Engedélyezi a Defender számára az archív fájlok – például .zip- vagy .cab-fájlok – vizsgálatát.
-   **Bejövő e-mailek vizsgálata** – Engedélyezi a Defender számára az eszközre érkező e-mailek azonnali vizsgálatát.
-   **A teljes vizsgálat a cserélhető meghajtókra is terjedjen ki** – Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát.
-   **Csatlakoztatott hálózati meghajtók vizsgálata** – Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon lévő fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem tudja eltávolítani a bennük talált kártevőket.
-   **Hálózati mappákból megnyitott fájlok vizsgálata** – Engedélyezi a Defender számára a megosztott hálózati meghajtókon lévő (például UNC elérési úton található) fájlok vizsgálatát.
Ha a meghajtón található fájlok írásvédettek, a Defender nem tudja eltávolítani a bennük talált kártevőket.
-   **Felhővédelem** – Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.
-   **Rákérdezés a mintaküldés előtt** – Azt szabályozza, hogy a rendszer automatikusan elküldje-e a Microsoftnak azokat a vélhetően kártevő fájlokat, amelyeknek további vizsgálata szükséges.
-   **Napi gyorsvizsgálat időpontja** – Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé.
-   **Rendszervizsgálat típusa** – Megadható, hogy milyen szintű vizsgálatra kerüljön sor az ütemezett rendszervizsgálatok alkalmával.
-   **Vélhetően nemkívánatos alkalmazások észlelése** – A védelmi szint kiválasztása arra az esetre, ha a Windows vélhetően nem kívánatos alkalmazásokat észlel:
        - **Tiltás**
        - **Naplózás** A vélhetően nem kívánatos alkalmazásokról bővebben [ebben a témakörben](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus) olvashat.
-   **Kártevők észlelése esetén végrehajtandó műveletek** – Ennek a beállításnak az engedélyezésével adhatja meg, hogy a Defender milyen műveleteket hajtson végre az észlelt fenyegetési szinteken (alacsony, közepes, magas és súlyos). Az elvégezhető műveletek a következők:
    -   **Tisztítás**
    -   **Karantén**
    -   **Eltávolítás**
    -   **Engedélyezés**
    -   **Felhasználó által definiált**
    -   **Tiltás**

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender víruskereső – kizárások

-   **A vizsgálatokból és a valós idejű védelemből kizárandó fájlok és mappák** – Felvesz egy vagy több fájlt vagy mappát (például **C:\Elérési út** vagy **%ProgramFiles%\Elérési út\fájlnév.exe**) a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.
-   **A vizsgálatokból és a valós idejű védelemből kizárandó fájlkiterjesztések** – Ezzel a beállítással egy vagy több fájlnév-kiterjesztés (például **jpg** vagy **txt**) vehető fel a kivételek listájára. A rendszer nem vizsgálja az ilyen kiterjesztésű fájlokat a valós idejű és a ütemezett vizsgálatok során.
-   **A vizsgálatokból és a valós idejű védelemből kizárandó folyamatok** – Ezzel a beállítással egy vagy több **.exe**, **.com** vagy **.scr** típusú folyamat vehető fel a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.

## <a name="network-proxy"></a>Hálózati proxy

-   **Proxybeállítások automatikus észlelése** – Ha a beállítás engedélyezve van, az eszköz megpróbálja megkeresni egy PAC-szkript elérési útját.
-   **Proxyparancsfájl használata** – A beállítás engedélyezésével megadhatja a PAC-szkript elérési útját a proxykiszolgáló konfigurálásához.
    -   **Beállítási parancsfájl URL-címe** – A proxykiszolgáló konfigurálásához használni kívánt PAC-szkript URL-címét adhatja meg.
-   **Manuális proxykiszolgáló használata** – Engedélyezze ezt a beállítást, ha manuálisan szeretné megadni a proxykiszolgáló beállításait.
    -   **Cím** – Adja meg a proxykiszolgáló nevét vagy IP-címét.
    -   **Portszám** – Adja meg a proxykiszolgáló portszámát.
    -   **Proxyhasználat alóli kivételek** – Adja meg azokat az URL-címeket, amelyeknél nem kell proxykiszolgálót használni. Az egyes címeket pontosvesszővel választhatja el egymástól.
    -   **Proxykiszolgáló kihagyása helyi cím esetén** – Engedélyezze ezt a beállítást, ha az intranet helyi címeinél nem szeretné használni a proxykiszolgálót.

## <a name="windows-spotlight"></a>Windows Reflektorfény

- **Windows Reflektorfény** – Ezzel a beállítással tilthatja le az összes Windows Reflektorfény-funkciót a Windows 10-es eszközökön. Ha letiltja ezt a beállítást, a következő beállítások nem lesznek elérhetők.
    - **Windows Reflektorfény a zárolási képernyőn** – Megakadályozza, hogy a Windows Reflektorfény információt jelenítsen meg az eszköz zárolási képernyőjén.
    - **Külső féltől származó javaslatok a Windows Reflektorfényben** – Megakadályozza, hogy a Windows Reflektorfény nem a Microsoft által közzétett javaslatokat jelenítsen meg.
    - **Fogyasztói funkciók** – Letilthatja az olyan fogyasztói funkciókat, mint a Start menü javaslatai vagy a tagsági értesítések.
    - **Windows-tippek** – A beállítással letilthatja az előugró Windows-tippek megjelenítését.
    - **Windows Reflektorfény a műveletközpontban** – A Windows Reflektorfény-javaslatok, például az új alkalmazásról vagy biztonsági tartalomról szólók, Windows Műveletközpontban való megjelenítésének letiltása.
    - **Windows Reflektorfény személyre szabása** – Megakadályozza, hogy a Windows Reflektorfény személyre szabja az eredményeket az eszköz használata alapján.
    - **Windows-újdonságok az üdvözlőképernyőn** – A felhasználó számára új vagy frissített funkciókra vonatkozó információkat megjelenítő Windows-újdonságok az üdvözlőképernyőn letiltása.

## <a name="projection"></a>Kivetítés

- **Felhasználói bevitel vezeték nélküli kijelzők vevőegységeiről** – Letiltja a felhasználói bevitelt a vezeték nélküli kijelzők vevőegységeiről.
- **Kivetítés erre a számítógépre** – Megakadályozza, hogy más eszközök felderíthessék a számítógépet kivetítéshez.
- **PIN-kód kérése párosításhoz** – PIN-kód kérésének megkövetelése vetítőeszközhöz való csatlakozáskor.

## <a name="cloud-printer"></a>Felhőbeli nyomtató

- **Nyomtatófelderítési URL-cím** – A felhőbeli nyomtatók felderítéséhez használt végpont.
- **Nyomtatóelérési szolgáltató URL-címe** – Az OAuth-jogkivonatok beszerzésének hitelesítési végpontja.
- **Azure-beli natív ügyfélalkalmazás GUID-azonosítója** – Az OAuth-szolgáltatótól OAuth-jogkivonatok letöltésére jogosult ügyfélalkalmazás GUID-azonosítója.
- **Nyomtatási szolgáltatás erőforrás-URI-ja** – A nyomtatási szolgáltatás Azure Portal webhelyen konfigurált OAuth-erőforrás-URI-ja.
- **Lekérdezendő nyomtatók maximális száma (csak mobil)** – Az egyes felderítési végpontokból lekérdezendő nyomtatók maximális száma.
- **Nyomtatófelderítési szolgáltatás erőforrás-URI-ja** – A nyomtatófelderítési szolgáltatás Azure Portal webhelyen konfigurált OAuth-erőforrás-URI-ja.

## <a name="local-printer"></a>Helyi nyomtató
- **Nyomtatók** – A hozzáadott helyi nyomtatók listája.
- **Alapértelmezett nyomtató** – Az alapértelmezett nyomtató beállítása.
- **Felhasználói hozzáférés új nyomtatók hozzáadásához** – Helyi nyomtatók használatának engedélyezése vagy tiltása.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása** – Itt adhatja meg a diagnosztikai adatok küldésének szintjét.
- **Telemetria proxykiszolgálója**

  Adja meg az „Összekapcsolt felhasználói élmények és telemetria” szolgáltatásnak küldött kéréseket SSL-kapcsolaton keresztül továbbító proxykiszolgáló teljes tartománynevét (FQDN) vagy IP-címét a következő formátumban: *kiszolgáló*:*port*. Ha a megadott proxy nem érhető el, vagy ha e szabályzat engedélyezésekor nincs megadva proxy, az „Összekapcsolt felhasználói élmények és telemetria” szolgáltatás adatai nem lesznek továbbítva a helyi eszközről.

   Példák a formátumra:

   IPv4: 192.246.246.106:100<br>
 IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100<br> FQDN: www.contoso.com:345

## <a name="messaging"></a>Üzenetküldés

- **Üzenetszinkronizálás (csak mobilon)** – Az Üzenetek mindenhol és a szöveges üzenetek funkció biztonsági mentésének és visszaállításának letiltása.
- **MMS (csak mobilon)** – Az MMS küldése/fogadása funkció letiltása az eszközön.
- **RCS (csak mobilon)** – A gazdag kommunikációs szolgáltatások (RCS) küldése/fogadása funkció letiltása az eszközön.

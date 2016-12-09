---
title: "iOS-alkalmazások burkolása az Intune Alkalmazásburkoló eszközzel | Microsoft Intune"
description: "Ebből a témakörből megtudhatja, hogyan burkolhatja az iOS-alkalmazásait anélkül, hogy módosítaná magának az alkalmazásnak a programkódját. Előkészítheti az alkalmazásokat a mobilalkalmazás-felügyeleti szabályzatok alkalmazására."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ee7e0491c0635c45cbc0377a5de01d5eba851132
ms.openlocfilehash: 0eee40c3c3c6bdfc3da2e715ef7b46e8408ba319


---

# <a name="prepare-ios-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel

A Microsoft Intune App Wrapping Tool for iOS nevű alkalmazásburkoló eszközzel megváltoztathatja a saját fejlesztésű IOS-alkalmazások viselkedését a kódjuk módosítása nélkül, azáltal, hogy lehetővé teszi az Intune alkalmazásvédelmi funkcióinak működését.

Az eszköz egy macOS parancssori alkalmazás, amely „burkolót” hoz létre az alkalmazások körül. Az alkalmazások feldolgozását követően a rendszergazda által beállított Intune [mobilalkalmazás-kezelési szabályzattal](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) módosíthatja a működésüket.

Az eszköz letöltéséhez keresse fel a [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) weblapot a GitHubon.



## <a name="fulfill-the-prerequisites-for-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz előfeltételeinek teljesítése
[Ebből a blogcikkből részletesebben tájékozódhat arról, hogy miképpen teremtheti meg az Intune alkalmazásburkoló eszköz működésének előfeltételeit](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

|Követelmény|További információ|
|---------------|--------------------------------|
|Támogatott operációs rendszer és eszközkészlet | Az alkalmazásburkoló eszközt olyan OS X 10.8.5 vagy újabb rendszerű macOS-számítógépen kell futtatni, amelyre telepítve van az XCode eszközkészlet 5-ös vagy újabb verziója.|
|Aláíró tanúsítvány és létesítési profil | Rendelkeznie kell egy Apple aláíró tanúsítvánnyal és létesítési profillal. Lásd az [Apple fejlesztői dokumentációját](https://developer.apple.com/).|
|Alkalmazás feldolgozása az alkalmazásburkoló eszközzel  |Az alkalmazást vállalatának vagy egy független szoftverszállítónak kell létrehoznia és aláírnia. Az eszköz nem használható az Apple Store áruházból származó alkalmazások feldolgozásához. Az alkalmazásoknak az iOS 8.0-s vagy újabb verziójához kellett készülnie. Az alkalmazásoknak a Position Independent Executable (PIE) formátumot kell használniuk. A PIE formátumról az Apple fejlesztői dokumentációjában talál további tájékoztatást. Végül az alkalmazásoknak **.app** vagy **.ipa** kiterjesztésűeknek kell lenniük.|
|Az eszközzel fel nem dolgozható alkalmazások | Titkosított alkalmazások, aláíratlan alkalmazások, kiterjesztett fájlattribútumokkal rendelkező alkalmazások.|
|Jogosultságok beállítása az alkalmazáshoz|Az alkalmazás burkolása előtt jogosultságokat kell megadnia, amelyek az általában megadottak mellett további engedélyekkel és képességekkel ruházzák fel az alkalmazást. További utasításokért lásd az [Alkalmazásjogosultságok beállítása](#setting-app-entitlements) című részt.|

## <a name="install-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz telepítése

1.  Töltse le az alkalmazásburkoló eszköz fájljait a [GitHubról](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) egy macOS-számítógépre.

2.  Kattintson duplán a **Microsoft Intune App Wrapping Tool for iOS.dmg** fájlra. Megjelenik a végfelhasználói licencszerződés (EULA) ablaka. Figyelmesen olvassa el a dokumentumot.

3. A licencszerződés elfogadásához válassza az **Elfogadom** lehetőséget, amivel a csomagot az adott számítógéphez rendeli.

4.  Nyissa meg a **IntuneMAMPackager** csomagot, és mentse a tartalmát a macOS-számítógépre. Most már készen áll az alkalmazásburkoló eszköz futtatására.

## <a name="run-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz futtatása

### <a name="use-terminal"></a>Terminál használata

Indítsa el a macOS Terminal programját, és keresse meg azt a mappát, ahová az alkalmazásburkoló eszköz fájljait mentette. A végrehajtható eszköz neve IntuneMAMPackager, és az IntuneMAMPackager/Contents/MacOS könyvtárban található. A következőképpen futtassa a parancsot:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Egyes paraméterek megadása nem kötelező, amint az az alábbi táblázatban látható.

**Példa:** A következő példaparancs a MyApp.ipa nevű alkalmazáson futtatja az alkalmazásburkoló eszközt. Meg van adva benne egy létesítési profil és az aláíró tanúsítvány SHA-1 kivonata. Ezzel írja alá az eszköz a beburkolt alkalmazást. A kimeneti alkalmazás (MyApp_Wrapped.ipa) elkészül, és a felhasználó Asztal mappájába kerül.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
```

### <a name="command-line-parameters"></a>Parancssori paraméterek
Az alkalmazásburkoló eszközzel a következő parancssori paraméterek használhatók:

|Tulajdonság|Használat|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. A fájlnév végződése .app vagy .ipa legyen. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Részletes használati információkat jelenít meg az alkalmazásburkoló eszközben elérhető parancssori tulajdonságokról.|
|**-v**|(Nem kötelező) Részletes üzeneteket jelenít meg a konzolon.|
|**-e**| (Nem kötelező) Ezzel a kapcsolóval utasíthatja az alkalmazásburkoló eszközt a hiányzó jogosultságok törlésére alkalmazásfeldolgozás közben. További részletek az Alkalmazásjogosultságok beállítása című részben olvashatók.|
|**-xe**| (Nem kötelező) Információkat jelenít meg az alkalmazás iOS-bővítményeiről, továbbá arról, hogy ezek milyen jogosultságokkal használhatók. További részletek az Alkalmazásjogosultságok beállítása című részben olvashatók. |
|**-x**| (Nem kötelező) `<An array of paths to extension provisioning profiles>`. Akkor használja, ha az alkalmazáshoz bővítménylétesítési profil szükséges.|
|**-f**|(Nem kötelező) `<Path to a plist file specifying arguments.>` Ez a kapcsoló a [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-fájl neve előtt használandó, ha az IntuneMAMPackager többi tulajdonságát (például -i, -o és -p) a plist-sablonban adja meg. Lásd a plist használata argumentumok megadásához című részt. |
|**-b**|(Nem kötelező) A -b argumentumok nélküli használatával a burkolt kimeneti alkalmazás csomagverziója ugyanaz lesz, mint a bementi alkalmazásé (nem ajánlott). <br/><br/> A `-b <custom bundle version>` használatával a burkolt alkalmazás egyéni CFBundleVersion-számmal fog rendelkezni. Ha egyéni CFBundleVersion-számot szeretne megadni, célszerű a natív alkalmazás CFBundleVersion-számában a legalacsonyabb értékű tagot megnövelni, például 1.0.0 -> 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Plist használata argumentumok megadásához
Az App Wrapping Tool egyszerűen futtatható úgy is, ha minden parancssori argumentumot egy [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-fájlban ad meg. A plist az XML-hez hasonló fájlformátum, amelyben űrlapon lehet megadni a parancssori argumentumokat.

Az IntuneMAMPackager/Contents/MacOS mappában nyissa meg a `Parameters.plist` nevű üres plist-sablont egy szövegszerkesztő alkalmazással vagy az Xcode-dal. Írja be az alábbi kulcsokhoz tartozó argumentumokat:

| Plist-kulcs |  Alapértelmezett érték| Megjegyzések |
|------------------|--------------|-----|
| Bemeneti alkalmazáscsomag elérési útja  |üres| Ugyanaz, mint az -i|
| Kimeneti alkalmazáscsomag elérési útja |üres| Ugyanaz, mint az -o|
| Létesítési profil elérési útja |üres| Ugyanaz, mint a -p|
| SHA-1 tanúsítvány kivonata |üres| Ugyanaz, mint a -c|
| Részletes üzenetek engedélyezve |hamis| Ugyanaz, mint a -v|
| Hiányzó jogosultságok eltávolítása | hamis| Ugyanaz, mint a -c|
| Alapértelmezett build tiltása |hamis | Ugyanaz, mint a -b argumentumok nélkül|
|Build karakterláncának felülbírálása | üres| A burkolt kimeneti alkalmazás egyéni CFBundleVersion-száma |
|Bővítménylétesítési profilok elérési útjai | üres| Az alkalmazás bővítménylétesítési profiljainak tömbje.


Futtassa az IntuneMAMPackager parancsot, egyetlen argumentumként a plist-fájlt megadva:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>A burkolás után

A beburkolási folyamat befejezése után megjelenik egy üzenet tájékoztat a burkolás sikerességéről. Hiba esetén további segítségért lásd: [Hibaüzenetek](#error-messages-and-log-files) .

A burkolt alkalmazást a korábban megadott kimeneti mappába menti a rendszer. Most már feltöltheti az alkalmazást az Intune felügyeleti konzolra, és társíthatja egy mobilalkalmazás-felügyeleti szabályzathoz.

> [!IMPORTANT]
> A burkolt alkalmazás feltöltésénél megpróbálhat egy régebbi verziót frissíteni, ha az alkalmazás egy régebbi (burkolt vagy natív) verziója már korábban üzembe lett helyezve az Intune-ban. Hiba esetén az alkalmazást új alkalmazásként töltse fel, és törölje a korábbi verziót.

Mostantól telepítheti az alkalmazást a felhasználócsoportok számára, és alkalmazásvédelmi szabályzatokat léptethet érvénybe az alkalmazásra vonatkozóan. Az alkalmazás ezt követően a megadott alkalmazásvédelmi szabályzatoknak megfelelően fut az eszközön.

## <a name="error-messages-and-log-files"></a>Hibaüzenetek és naplófájlok
Az alábbi információkat használva háríthatja el az alkalmazásburkoló eszközzel kapcsolatos hibákat.

### <a name="error-messages"></a>Hibaüzenetek
Ha az alkalmazásburkoló eszköz nem jár sikerrel, az alábbi hibaüzenetek valamelyike jelenik meg a konzolon:

|Hibaüzenet|További információ|
|-----------------|--------------------|
|Adjon meg egy érvényes iOS-létesítési profilt.|Előfordulhat, hogy a létesítési profil nem érvényes. Ellenőrizze, hogy rendelkezik-e megfelelő engedélyekkel az eszközökhöz, és hogy a profilja megfelelően be van-e állítva fejlesztéshez vagy terjesztéshez. A létesítési profilja esetleg le is járhatott.|
|Adjon meg egy érvényes bemeneti alkalmazásnevet.|Győződjön meg arról, hogy helyesen adta meg a bemeneti alkalmazás nevét.|
|Adjon meg érvényes elérési utat a kimeneti alkalmazáshoz.|Győződjön meg arról, hogy a kimeneti alkalmazás megadott elérési útja létezik és helyes.|
|Adjon meg egy érvényes bemeneti létesítési profilt.|Győződjön meg arról, hogy érvényes létesítésiprofil-nevet és -kiterjesztést adott meg. Előfordulhat, hogy hiányoznak jogosultságok a létesítési profiljából, vagy nem vette fel a –p parancssori kapcsolót.|
|A megadott bemeneti alkalmazás nem található. Adjon meg egy érvényes nevet és elérési utat a bemeneti alkalmazáshoz.|Győződjön meg arról, hogy a bemeneti alkalmazás elérési útja érvényes és létezik. Ellenőrizze, hogy a bemeneti alkalmazás az adott helyen található-e.|
|A megadott bemeneti létesítési profilfájl nem található. Adjon meg egy érvényes bemeneti létesítési profilfájlt.|Győződjön meg arról, hogy a bemeneti létesítési fájl elérési útja érvényes és a megadott fájl létezik.|
|A megadott kimeneti alkalmazásmappa nem található. Adjon meg érvényes elérési utat a kimeneti alkalmazáshoz.|Győződjön meg arról, hogy a megadott kimeneti elérési út érvényes és létezik.|
|A kimeneti alkalmazásnak nem **.ipa** a kiterjesztése.|Az alkalmazásburkoló eszköz csak az **.app** és az **.ipa** kiterjesztést fogadja el. Ellenőrizze, hogy a kimeneti fájl kiterjesztése érvényes-e.|
|Érvénytelen aláíró tanúsítványt adott meg. Adjon meg egy érvényes Apple aláíró tanúsítványt.|Ellenőrizze, hogy a helyes aláíró tanúsítványt töltötte-e le az Apple fejlesztői portáljáról. Lehetséges, hogy a tanúsítvány lejárt, vagy hiányzik egy publikus vagy titkos kulcs. Ha Apple-tanúsítványa és létesítési profilja használható az alkalmazások megfelelő aláírásához az Xcode-on belül, akkor érvényes az alkalmazásburkoló eszközhöz.|
|A megadott bemeneti alkalmazás érvénytelen. Adjon meg egy érvényes alkalmazást.|Győződjön meg arról, hogy .app vagy .ipa fájlként összeállított, érvényes iOS-alkalmazással rendelkezik.|
|A megadott bemeneti alkalmazás titkosítva van. Adjon meg egy érvényes titkosítatlan alkalmazást.|Az alkalmazásburkoló eszköz nem támogatja a titkosított alkalmazásokat. Adjon meg egy titkosítatlan alkalmazást.|
|A megadott bemeneti alkalmazás nem Position Independent Executable (PIE) formátumú. Adjon meg egy érvényes alkalmazást PIE formátumban.|A Position Independent Executable (PIE) formátumú alkalmazások egy véletlenszerű memóriacímre tölthetők be futtatás közben. Ez biztonsági előnyökkel járhat. A biztonsági előnyökről az Apple fejlesztői dokumentációjában talál további tájékoztatást.|
|A megadott bemeneti alkalmazás már be van burkolva. Adjon meg egy érvényes burkolatlan alkalmazást.|Az eszköz által már feldolgozott alkalmazás nem dolgozható fel. Ha ismét fel szeretne dolgozni egy alkalmazást, az alkalmazás eredeti verzióját használva futtassa az eszközt.|
|A megadott bemeneti alkalmazás nincs aláírva. Adjon meg egy érvényes aláírt alkalmazást.|Az alkalmazásburkoló eszköz megköveteli az alkalmazások aláírását. A fejlesztői dokumentációból megtudhatja, hogy miként írhat alá burkolt alkalmazásokat.|
|A megadott bemeneti alkalmazásnak .ipa vagy .app formátumúnak kell lennie.|Az alkalmazásburkoló eszköz csak .app és .ipa kiterjesztést fogad el. Ellenőrizze, hogy a bemeneti fájl érvényes kiterjesztéssel rendelkezik-e, és .app vagy .ipa fájlként lett-e összeállítva.|
|A megadott bemeneti alkalmazás már burkolt, és a házirendsablon legújabb verziójában van.|Az alkalmazásburkoló eszköz nem burkol újra egy már meglévő burkolt alkalmazást a szabályzatsablon legújabb verziójával.|
|Figyelmeztetés: Nem adta meg az SHA1 tanúsítvány kivonatát. Ellenőrizze, hogy a burkolt alkalmazás alá van-e írva a telepítés előtt.|Adjon meg egy érvényes SHA1 kivonatot a –c parancssori kapcsoló után. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz naplófájljai
Az alkalmazásburkoló eszközzel burkolt alkalmazások az iOS-ügyféleszköz konzoljára írt naplófájlokat hoznak létre. Ezek az adatok akkor hasznosak, ha problémát tapasztal az alkalmazással kapcsolatban, és meg kell állapítania, hogy a hiba az alkalmazásburkoló eszközzel kapcsolatos-e. Az adatokat az alábbi lépéseket követve olvashatja be:

1.  Az alkalmazást futtatva reprodukálja a hibát.

2.  Gyűjtse össze a konzol kimenetét az Apple [telepített iOS-alkalmazások hibakeresésére](https://developer.apple.com/library/ios/qa/qa1747/_index.html)vonatkozó utasításait követve.

3.  A következő szkriptet a konzolon megadva szűrje a mentett naplókat az alkalmazáskorlátozások kimenetre:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    A szűrt naplót elküldheti a Microsoftnak.

    > [!NOTE]
    > A naplófájlban a „buildszám” az Xcode buildszámának felel meg.

    A burkolt alkalmazások lehetőséget biztosítanak a felhasználóknak, hogy az alkalmazás összeomlása után közvetlenül az eszközről küldjenek e-mailt. A felhasználók elküldhetik Önnek a naplót, hogy megvizsgálja, és szükség esetén továbbítsa azt a Microsoftnak.


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Tanúsítvány, létesítési profil és hitelesítési követelmények

Az alkalmazásburkoló eszköz iOS-verziójának optimális működéséhez bizonyos követelményeknek teljesülniük kell.

|Követelmény|Részletek|
|---------------|-----------|
|iOS-beli létesítési profil|Használat előtt ellenőrizze a létesítési profil érvényességét. iOS-alkalmazások feldolgozásakor az alkalmazásburkoló eszköz nem ellenőrzi a létesítési profil érvényességét. Ha lejárt létesítési profil van megadva, az alkalmazásburkoló eszköz tartalmazza a lejárt létesítési profilt, és addig nem szerez tudomást a problémáról, amíg az alkalmazás telepítése meg nem hiúsul egy iOS-eszközön.|
|iOS-beli aláíró tanúsítvány|Mielőtt megadja az aláíró tanúsítványt, ellenőrizze, hogy érvényes-e. iOS-alkalmazások feldolgozásánál az alkalmazásburkoló eszköz nem ellenőrzi a tanúsítvány érvényességét. Ha lejárt tanúsítvány kivonatát adja meg, az eszköz feldolgozza és aláírja az alkalmazást, de nem tudja telepíteni az eszközökre.<br /><br />Ügyeljen rá, hogy a beburkolt alkalmazás aláírására használt tanúsítvány megtalálható legyen a létesítési profilban. Az eszköz nem ellenőrzi, hogy a létesítési profil rendelkezik-e egyezéssel a burkolt alkalmazás aláírásához megadott tanúsítványhoz.|
|Hitelesítés|A titkosítás működéséhez az eszközöknek PIN-kóddal kell rendelkezniük. Olyan eszközökön, amelyekre telepít egy beburkolt alkalmazást, az eszköz állapotsávjának megérintése esetén a felhasználónak újra be kell jelentkezni a munkahelyi vagy iskolai fiókjával. A burkolt alkalmazások alapértelmezett szabályzata a *hitelesítés újraindításkor*. Az iOS minden külső értesítést (például telefonhívást) az alkalmazásból való kilépésként és az alkalmazás újraindításaként kezel.


## <a name="setting-app-entitlements"></a>Alkalmazásjogosultságok beállítása
Az alkalmazást a burkolása előtt *jogosultságok* megadásával további engedélyekkel és képességekkel láthatja el. Ezek segítségével tovább bővítheti az alkalmazás által elvégezhető tevékenységek körét. A kódaláírás során a rendszer *jogosultságot tartalmazó fájlt* használ a speciális engedélyek (például megosztott kulcslánchoz való hozzáférés) megadásához az alkalmazáson belül. Az alkalmazás *képességek* néven ismert konkrét szolgáltatásai az alkalmazásfejlesztés során az Xcode-on belül engedélyezhetők. Miután engedélyezte őket, a képességek megjelennek a jogosultságokat tartalmazó fájlban. A jogosultságokról és képességekről az iOS Developer Library [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Képességek hozzáadása) című témakörében olvashat bővebben. A támogatott képességek teljes listáját a [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Támogatott képességek) című témakörben találja.

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Az iOS rendszerhez készült alkalmazásburkoló eszköz támogatott képességei

|Képesség|Leírás|Ajánlott útmutatás|
|--------------|---------------|------------------------|
|Alkalmazáscsoportok|Alkalmazáscsoportok használatával biztosíthatja több alkalmazás hozzáférését a megosztott tárolókhoz, és engedélyezheti a folyamatközi kommunikációt az alkalmazások között.<br /><br />Az alkalmazáscsoportok engedélyezéséhez nyissa meg a **Capabilities** (Képességek) panelt, és kattintson az **On** (Bekapcsolás) lehetőségre az **App Groups** (Alkalmazáscsoportok) beállításnál. Felvehet alkalmazáscsoportokat, illetve kijelölhet meglévőket.|Alkalmazáscsoportok használatakor használjon címfeloldási DNS-t:<br /><br />*csoport.com.cégnév.Alkalmazáscsoport*|
|Háttérbeli üzemmódok|A háttérbeli üzemmódok engedélyezése esetén az iOS-alkalmazás tovább futhat a háttérben is.||
|Adatvédelem|Az adatvédelem biztosítja az iOS-alkalmazás által a lemezen tárolt fájlok védelmét. Az adatvédelem az adott eszközökön megtalálható beépített titkosítási hardvert használja a fájlok titkosított formában történő tárolásához a lemezen. Az alkalmazást úgy kell létrehozni, hogy használjon adatvédelmet.||
|Alkalmazáson belüli vásárlás|Az alkalmazáson belüli vásárlás beépít egy áruházat magába az alkalmazásba azáltal, hogy engedélyezi az áruházhoz való csatlakozást és a felhasználó fizetéseinek biztonságos feldolgozását. Az alkalmazáson belüli vásárlás segítségével szedheti be a továbbfejlesztett funkciókért vagy az alkalmazása által használható további tartalomért járó díjakat.||
|Kulcslánc megosztása|A kulcslánc megosztása lehetővé teszi, hogy az alkalmazása jelszavakat osszon meg a kulcsláncban a csapata által fejlesztett egyéb alkalmazásokkal.|Kulcslánc megosztásakor fordított DNS jelölésmódot használjon:<br /><br />*com.cégnév.Kulcslánccsoport*|
|Személyes VPN|A személyes VPN engedélyezésével lehetővé teszi az alkalmazásnak, hogy egyéni VPN-rendszerkonfigurációt hozzon létre és szabályozzon a Hálózati bővítmény keretrendszer használatával.||
|Leküldéses értesítések|Az Apple Push Notification szolgáltatás (APNs) lehetővé teszi, hogy a nem az előtérben futó alkalmazások értesítsék a felhasználót arról, hogy információi vannak a számára.|A leküldéses értesítések működéséhez alkalmazásspecifikus létesítési profilt kell használnia.<br /><br />Kövesse az [Apple fejlesztői dokumentációjában](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) megadott lépéseket.|
|Vezeték nélküli tartozék konfigurációja|A vezeték nélküli tartozék konfigurációja felveszi a külsőtartozék-támogatási keretrendszert a projektjébe, és lehetővé teszi az alkalmazásnak az MFi Wi-Fi tartozékok beállítását.||

### <a name="steps-to-enable-entitlements"></a>A jogosultságok engedélyezésének lépései

1.  Képességek engedélyezése az alkalmazásban:

    a.  Az Xcode-ban keresse meg az alkalmazás célját, és kattintson a **Capabilities** (Képességek) elemre.

    b.  Kapcsolja be a megfelelő képességeket. Az egyes képességekről és a megfelelő értékek meghatározásáról az iOS Developer Library [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Képességek hozzáadása) című témakörében olvashat bővebben.

    c.  Jegyezze fel a folyamat során létrehozott azonosítókat.

    d.  Készítse el és írja alá a burkolandó alkalmazást.

2.  Jogosultságok engedélyezése a létesítési profiljában:

    a.  Jelentkezzen be az Apple Developer Member Center webhelyre.

    b.  Hozzon létre egy létesítési profilt az alkalmazásához. Utasításokért lásd: [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Az Intune App Wrapping Tool for iOS előfeltételeinek megteremtése).

    c.  A létesítési profiljában engedélyezze ugyanazokat a jogosultságokat, amelyekkel az alkalmazásában rendelkezik. Adja meg ugyanazokat az azonosítókat, amelyeket az alkalmazása fejlesztése során adott meg.

    d.  Fejezze be a létesítési profil varázslót, és töltse le a fájlt.

3.  Ellenőrizze, hogy minden előfeltétel teljesült-e, majd burkolja az alkalmazást.

### <a name="troubleshoot-common-errors-with-entitlements"></a>A jogosultságokkal kapcsolatos gyakori hibák elhárítása
Ha az iOS-hez készült alkalmazásburkoló eszköz jogosultsággal kapcsolatos hibát jelenít meg, próbálkozzon az alábbi hibaelhárítási lépésekkel.

|Probléma|Ok|Megoldás|
|---------|---------|--------------|
|Nem sikerült a bemeneti alkalmazás által létrehozott jogosultságok elemzése.|Az alkalmazásburkoló eszköz nem tudja olvasni az alkalmazásból kinyert jogosultságfájlt. Előfordulhat, hogy a jogosultságfájl helytelenül formázott.|Vizsgálja meg az alkalmazásához tartozó jogosultságfájlt. A következő útmutatás elmagyarázza ennek módját. A jogosultságfájl vizsgálatakor ellenőrizze, hogy nem tartalmaz-e hibás szintaxist. A fájlnak XML formátumúnak kell lennie.|
|A létesítési profilban jogosultságok hiányoznak (a hiányzó jogosultságok listában láthatók). Csomagolja újra az alkalmazást egy olyan létesítési profillal, amely tartalmazza ezeket a jogosultságokat.|A létesítési profilban engedélyezett jogosultságok és az alkalmazásban engedélyezett képességek között eltérés tapasztalható. Ez az eltérés érvényes az adott képességekhez (vagyis az alkalmazáscsoportokhoz, kulcslánc-hozzáféréshez stb.) társított azonosítókra is.|Általában létrehozhat egy új létesítési profilt, amely ugyanazokat a képességeket engedélyezi, mint az alkalmazás. Ha nem egyeznek meg a profil és az alkalmazás között az azonosítók, az alkalmazásburkoló eszköz lecseréli őket (ha tudja). Ha az új létesítési profil létrehozását követően továbbra is megjelenik a hibaüzenet, próbálja meg eltávolítani a jogosultságokat az alkalmazásból az –e paraméter használatával (lásd a „Jogosultságok eltávolítása az alkalmazásból az –e paraméter használatával” című részt).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>Aláírt alkalmazás meglévő jogosultságainak megkeresése
Aláírt alkalmazás és létesítési profil meglévő jogosultságainak ellenőrzése:

1.  Keresse meg az .ipa fájlt, és módosítsa .zip kiterjesztésűre.

2.  Bontsa ki a .zip fájlt. Ez a művelet létrehoz egy Payload nevű mappát, amely tartalmazza az .app csomagot.

3.  A codesign eszközzel ellenőrizze a jogosultságokat az .app csomagon (a `YourApp.app` helyére adott .app csomag nevét kell beírni):

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  A security eszközzel ellenőrizze a jogosultságokat az .app beépített létesítési profilján (a `YourApp.app` helyére adott .app csomag nevét kell beírni).

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Jogosultságok eltávolítása az alkalmazásból az –e paraméterrel
Ezzel a paranccsal eltávolítja az alkalmazásból azon engedélyezett képességeket, amelyek nem szerepelnek a jogosultságokat tartalmazó fájlban. Ha olyan képességeket távolít el, amelyeket az alkalmazás használ, az az alkalmazás meghibásodásához vezethet. Hiányzó képességeket például abban az esetben érdemes eltávolítani, ha egy partner által fejlesztett alkalmazásnak alapértelmezés szerint minden képessége megvan.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszközzel kapcsolatos biztonsági és adatvédelmi szempontok
Az alkalmazásburkoló eszköz használata során kövesse az alábbi biztonsági és adatvédelmi gyakorlati tanácsokat.

-   Az aláíró tanúsítványnak, a létesítési profilnak és a megadott üzletági alkalmazásnak ugyanazon a macOS-számítógépen kell lennie, mint amelyet az alkalmazásburkoló eszköz futtatásához használ. Ha a fájlok egy UNC elérési úton vannak, ellenőrizze, hogy elérhetők-e a macOS -számítógépről. Az elérési utat IPsec- vagy SMB-aláírással védeni kell.

    A felügyeleti konzolra importált beburkolt alkalmazásnak ugyanazon a számítógépen kell lennie, mint amelyen az eszközt futtatja. Ha a fájl egy UNC elérési úton van, győződjön meg róla, hogy a mappa elérhető a felügyeleti konzolt futtató számítógépről. Az elérési utat IPsec- vagy SMB-aláírással védeni kell.

-   IPsec- vagy SMB-aláírással kell védeni azt a környezetet, ahová az alkalmazásburkoló eszközt a GitHub-tárházból letölti.

-   A feldolgozott alkalmazásnak megbízható forrásból kell származnia ahhoz, hogy a támadások elleni védelmét biztosítani lehessen.

-   Gondoskodjon az alkalmazásburkoló eszközben megadott kimeneti mappa védelméről, különösen ha távoli mappáról van szó.

-   A fájlfeltöltési párbeszédpanelt tartalmazó iOS-alkalmazások lehetővé tehetik a felhasználóknak, hogy megkerüljék az alkalmazáshoz megadott kivágási, másolási és beillesztési korlátozásokat. A felhasználók a fájlfeltöltési párbeszédpanelt használhatják például az alkalmazásadatok képernyőfelvételének feltöltéséhez.

-   Amikor egy burkolt alkalmazásból figyeli az eszközükön lévő dokumentummappát, láthatja az .msftintuneapplauncher nevű mappát. Ha módosítja vagy törli ezt a mappát, az hatással lehet a korlátozott alkalmazások megfelelő működésére.

### <a name="see-also"></a>További információ
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Dec16_HO2-->



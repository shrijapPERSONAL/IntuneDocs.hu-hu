---
title: "iOS-alkalmazások burkolása az Alkalmazásburkoló eszközzel | Microsoft Intune"
description: "Ebből a témakörből megtudhatja, hogyan burkolhatja az iOS-alkalmazásait anélkül, hogy módosítaná az alkalmazás programkódját. Előkészítheti az alkalmazásokat a mobilalkalmazás-felügyeleti szabályzatok alkalmazására."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: c67a5042fd177a4c5bd897092e84281db0977f5e
ms.openlocfilehash: 2c187b61b8fe25b2870d0cbc62f8352494583fc2


---

# iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel
A **Microsoft Intune App Wrapping Tool for iOS** nevű alkalmazásburkoló eszközzel módosíthatja a belső fejlesztésű IOS-alkalmazások viselkedését, így az alkalmazások kódjának módosítása nélkül korlátozhatja az alkalmazások funkcióit.

Az eszköz egy Mac OS parancssori alkalmazás, amely „burkolót” hoz létre az alkalmazások körül. Az alkalmazások feldolgozását követően az Ön által beállított Intune [mobilalkalmazás-kezelési szabályzat](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) használatával módosíthatja az alkalmazások működését.

Az eszköz letöltéséhez keresse fel a [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) weblapot.



## 1. lépés Az alkalmazásburkoló eszköz használatára vonatkozó előfeltételek teljesítése
[Ebben a blogbejegyzésben](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) további információkat talál az előfeltételekről, és hogy hogyan kell őket beállítani.

|Követelmény|További információ|
|---------------|--------------------------------|
|Támogatott operációs rendszer és eszközkészlet|Az alkalmazásburkoló eszközt OS X 10.8.5 vagy újabb rendszerű macOS számítógépen kell futtatni, amelyen telepítve van az XCode eszközkészlet 5-ös vagy újabb verziója.|
|Aláíró tanúsítvány és létesítési profil|Rendelkeznie kell egy Apple aláíró tanúsítvánnyal és létesítési profillal. Lásd az [Apple fejlesztői dokumentációját](https://developer.apple.com/).|
|Alkalmazás feldolgozása az alkalmazásburkoló eszközzel|Az alkalmazást vállalatának vagy egy független szoftverszállítónak kell létrehoznia és aláírnia. Az eszköz nem használható az Apple Store áruházból származó alkalmazások feldolgozásához. Az alkalmazásoknak az iOS 8.0-s vagy újabb verziójához kellett készülnie. Az alkalmazásoknak a Position Independent Executable (PIE) formátumot kell használniuk. A PIE formátumról az Apple fejlesztői dokumentációjában talál további információkat. Végül az alkalmazásoknak **.app** vagy **.ipa** kiterjesztésűeknek kell lenniük.|
|Az alkalmazásburkoló eszköz által nem feldolgozható alkalmazások|Titkosított alkalmazások, aláíratlan alkalmazások, kiterjesztett fájlattribútumokkal rendelkező alkalmazások.|
|Jogosultságok beállítása az alkalmazáshoz|Az alkalmazás burkolása előtt jogosultságokat kell megadnia, amelyek az általában megadottak mellett további engedélyekkel és képességekkel ruházzák fel az alkalmazást. További utasításokért lásd az [Alkalmazásjogosultságok beállítása](#setting-app-entitlements) című részt.|

## 2. lépés Az alkalmazásburkoló eszköz telepítése

1.  A **Microsoft Intune App Wrapping Tool for iOS** nevű [GitHub-tárházból](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) töltse le az alkalmazásburkoló eszköz fájljait egy helyi macOS számítógépre.

2.  Kattintson duplán a **Microsoft Intune App Wrapping Tool for iOS.dmg** telepítőfájlra. Megjelenik a végfelhasználói licencszerződés (EULA) ablaka. Figyelmesen olvassa el a dokumentumot.

3. A licencszerződés elfogadásához válassza az **Elfogadom** lehetőséget, amivel a csomagot az adott számítógéphez rendeli.

4.  Nyissa meg a **IntuneMAMPackager** csomagot, és mentse a fájlokat a macOS számítógép egy helyi könyvtárába. Most már készen áll az alkalmazásburkoló eszköz futtatására.

## 3. lépés. Az alkalmazásburkoló eszköz futtatása
* A macOS számítógépen nyissa meg a terminálablakot, és keresse meg azt a mappát, ahová az alkalmazásburkoló eszköz fájljait mentette. A végrehajtható eszköz neve **IntuneMAMPackager**, és az **IntuneMAMPackager/Contents/MacOS** könyvtárban található. A parancsot az alábbi módon kell futtatni:

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > Egyes paraméterek megadása nem kötelező, az alábbi táblázatban látható módon.

    **Példa:** A következő példaparancs egy **MyApp.ipa**nevű alkalmazáson futtatja az alkalmazásburkoló eszközt. Meg van adva egy létesítési profil és SHA-1 kivonat. A feldolgozott alkalmazás **MyApp_Wrapped.ipa** névvel elkészül, és a felhasználó Asztal mappájába kerül.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    Az alkalmazásburkoló eszközzel a következő parancssori tulajdonságok használhatók:

    |Tulajdonság|Használat|
  |------------|--------------------|
  |**-i**|`<Path of the input native iOS application file>`. A fájl végződése .app vagy .ipa legyen. |
  |**-o**|`<Path of the wrapped output application>` |
  |**-p**|`<Path of your provisioning profile for iOS apps>`|
  |**-c**|`<SHA1 hash of the signing certificate>`|
    |-h|Részletes használati információt jelenít meg az alkalmazásburkoló eszköz elérhető parancssori tulajdonságairól.|
  |-v|(Nem kötelező, de hasznos) Részletes üzeneteket jelenít meg a konzolon.|
  |-e | (Nem kötelező) Ezzel a kapcsolóval utasíthatja az alkalmazásburkoló eszközt a hiányzó jogosultságok törlésére alkalmazásfeldolgozás közben. További információk az „alkalmazásjogosultságok beállítása” című részben.|
  |-xe| (Nem kötelező) Információt jelenít meg az alkalmazás iOS-bővítményeiről, továbbá hogy azok milyen jogosultságokkal használhatók. További információk az „alkalmazásjogosultságok beállítása” című részben. |
  |-x| (Nem kötelező) `<An array of paths to extension provisioning profiles>`. Akkor használja, ha az alkalmazáshoz bővítménylétesítési profil szükséges.|
  |-f |(Nem kötelező) `<Path to a plist file specifying arguments.>` Ez a kapcsoló a [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-fájl neve előtt használandó, ha az IntuneMAMPackager többi tulajdonságát ( -i, -o, -p stb.) a plist-sablonban adja meg. További információkat a „Plist használata argumentumok megadásához” című részben talál. |
  |-b|(Nem kötelező) A -b argumentumok nélküli használatával a burkolt kimeneti alkalmazás csomagverziója ugyanaz lesz, mint a bementi alkalmazásé (nem ajánlott). <br/><br/> A `-b <custom bundle version>` használatával a burkolt alkalmazás egyéni CFBundleVersion-számmal fog rendelkezni. Ha egyéni CFBundleVersion-számot szeretne megadni, javasoljuk, hogy a natív alkalmazás CFBundleVersion-számában a legalacsonyabb értékű komponenst növelje, például 1.0.0 -> 1.0.1. |


###Plist használata argumentumok megadásához
Az App Wrapping Tool egyszerűen futtatható úgy is, ha minden parancssori argumentumot egy [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-fájlban ad meg. A plist az XML-hez hasonló fájlformátum, amelyben – egy űrlap felület használatával – parancssori argumentumok adhatók meg.

Az **IntuneMAMPackager/Contents/MacOS** mappában nyissa meg a `Parameters.plist` nevű üres plist-sablont egy szövegszerkesztő alkalmazással vagy az Xcode-dal. Írja be az alábbi kulcsokhoz tartozó argumentumokat:

| Plist-kulcs |  Alapértelmezett érték| Megjegyzések |
|------------------|--------------|-----|
| Bemeneti alkalmazáscsomag elérési útja  |üres| Ugyanaz, mint az -i. |
| Kimeneti alkalmazáscsomag elérési útja |üres| Ugyanaz, mint az -o.|
| Létesítési profil elérési útja |üres| Ugyanaz, mint a -p. |
| SHA-1 tanúsítvány kivonata |üres| Ugyanaz, mint a -c. |
| Részletes üzenetek engedélyezve |hamis| Ugyanaz, mint a -v. |
| Hiányzó jogosultságok eltávolítása | hamis| Ugyanaz, mint a -c.|
| Alapértelmezett build tiltása |hamis | Ugyanaz, mint a -b argumentumok nélkül. |
|Build karakterláncának felülbírálása | üres| A burkolt kimeneti alkalmazás egyéni CFBundleVersion-száma |
|Bővítménylétesítési profilok elérési útjai | üres| Az alkalmazás bővítménylétesítési profiljainak tömbje.
  

Végül futtassa az IntuneMAMPackager parancsot, egyetlen argumentumként a plist-fájlt megadva:

```
./IntuneMAMPackager –f Parameters.plist
```

* A feldolgozás befejezése után megjelenik „**Az alkalmazás burkolása sikerült**” üzenet.

    Hiba esetén további segítségért lásd: [Hibaüzenetek](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) .

*   A burkolt alkalmazást a korábban megadott kimeneti mappába menti a rendszer. Most már feltöltheti az alkalmazást az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-ba, és társíthatja egy mobilalkalmazás-felügyeleti házirenddel.

    > [!IMPORTANT]
    > A burkolt alkalmazás feltöltésénél megpróbálhat egy régebbi verziót frissíteni, ha az alkalmazás egy régebbi (burkolt vagy natív) verziója már korábban üzembe lett helyezve az Intune-ban. Hiba esetén az alkalmazást új alkalmazásként töltse fel, és törölje a korábbi verziót.

    Most már telepítheti az alkalmazást az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-csoportokba, és az alkalmazás már futni fog a megadott alkalmazáskorlátozásokat használó eszközön.

## Hibaüzenetek és naplófájlok
Az alábbi információkat használva háríthatja el az alkalmazásburkoló eszközzel kapcsolatos hibákat.

### Hibaüzenetek
Ha az alkalmazásburkoló eszköz befejezése sikertelen, az alábbi hibaüzenetek valamelyike jelenik meg a konzolon:

|Hibaüzenet|További információ|
|-----------------|--------------------|
|Adjon meg egy érvényes iOS-létesítési profilt.|Előfordulhat, hogy a létesítési profil nem érvényes. Ellenőrizze, hogy rendelkezik-e megfelelő engedélyekkel az eszközökhöz, és hogy a profilja megfelelően be van-e állítva fejlesztéshez vagy terjesztéshez. A létesítési profilja esetleg le is járhatott.|
|Adjon meg egy érvényes bemeneti alkalmazásnevet.|Győződjön meg arról, hogy helyesen adta meg a bemeneti alkalmazás nevét.|
|Adjon meg érvényes elérési utat a kimeneti alkalmazáshoz.|Győződjön meg arról, hogy a kimeneti alkalmazás megadott elérési útja létezik és helyes.|
|Adjon meg egy érvényes bemeneti létesítési profilt.|Győződjön meg arról, hogy érvényes létesítésiprofil-nevet és -kiterjesztést adott meg. Előfordulhat, hogy hiányoznak jogosultságok a létesítési profiljához, vagy nem vette fel a **–p** parancssori kapcsolót.|
|A megadott bemeneti alkalmazás nem található. Adjon meg egy érvényes nevet és elérési utat a bemeneti alkalmazáshoz.|Győződjön meg arról, hogy a bemeneti alkalmazás elérési útja érvényes és létezik. Ellenőrizze, hogy a bemeneti alkalmazás az adott helyen található-e.|
|A megadott bemeneti létesítési profilfájl nem található. Adjon meg egy érvényes bemeneti létesítési profilfájlt.|Győződjön meg arról, hogy a bemeneti létesítési fájl elérési útja érvényes és a megadott fájl létezik.|
|A megadott kimeneti alkalmazásmappa nem található. Adjon meg érvényes elérési utat a kimeneti alkalmazáshoz.|Győződjön meg arról, hogy a megadott kimeneti elérési út érvényes és létezik.|
|A kimeneti alkalmazás kiterjesztése nem .ipa.|Az alkalmazásburkoló eszköz csak **.app** és **.ipa** kiterjesztést fogad el. Ellenőrizze, hogy a kimeneti fájl kiterjesztése érvényes-e.|
|Érvénytelen aláíró tanúsítványt adott meg. Adjon meg egy érvényes Apple aláíró tanúsítványt.|Ellenőrizze, hogy a helyes aláíró tanúsítványt töltötte-e le az Apple fejlesztői portáljáról. Lehetséges, hogy a tanúsítvány lejárt, vagy hiányzik egy publikus vagy titkos kulcs. Ha Apple-tanúsítványa és létesítési profilja használható az alkalmazások megfelelő aláírásához az Xcode-on belül, akkor érvényesek az alkalmazásburkoló eszközhöz.|
|A megadott bemeneti alkalmazás érvénytelen. Adjon meg egy érvényes alkalmazást.|Győződjön meg arról, hogy .app vagy .ipa fájlként összeállított, érvényes iOS-alkalmazással rendelkezik.|
|A megadott bemeneti alkalmazás titkosítva van. Adjon meg egy érvényes titkosítatlan alkalmazást.|Az alkalmazásburkoló eszköz nem támogatja a titkosított alkalmazásokat. Adjon meg egy titkosítatlan alkalmazást.|
|A megadott bemeneti alkalmazás nem Position Independent Executable (PIE) formátumú. Adjon meg egy érvényes alkalmazást PIE formátumban.|A Position Independent Executable (PIE) formátumú alkalmazások egy véletlenszerű memóriacímre tölthetők be futtatás közben, ami biztonsági szempontból előnyökkel járhat. További tudnivalókért tanulmányozza az Apple fejlesztői dokumentációját.|
|A megadott bemeneti alkalmazás már be van burkolva. Adjon meg egy érvényes burkolatlan alkalmazást.|Az eszköz által már feldolgozott alkalmazás nem dolgozható fel. Ha ismét fel szeretne dolgozni egy alkalmazást, az alkalmazás eredeti verzióját használva futtassa az eszközt.|
|A megadott bemeneti alkalmazás nincs aláírva. Adjon meg egy érvényes aláírt alkalmazást.|Az alkalmazásburkoló eszköz megköveteli az alkalmazások aláírását. A fejlesztői dokumentációból megtudhatja, hogy miként írhat alá burkolt alkalmazásokat.|
|A megadott bemeneti alkalmazásnak .ipa vagy .app formátumúnak kell lennie.|Az alkalmazásburkoló eszköz csak .app és .ipa kiterjesztést fogad el. Ellenőrizze, hogy a bemeneti fájl érvényes kiterjesztéssel rendelkezik-e, és .app vagy .ipa fájlként lett-e összeállítva.|
|A megadott bemeneti alkalmazás már burkolt, és a házirendsablon legújabb verziójában van.|Az alkalmazásburkoló eszköz nem fog újraburkolni egy már meglévő burkolt alkalmazást a házirendsablon legújabb verziójával.|
|Figyelmeztetés: Nem adta meg az SHA1 tanúsítvány kivonatát. Ellenőrizze, hogy a burkolt alkalmazás alá van-e írva a telepítés előtt.|Adjon meg egy érvényes SHA1 kivonatot a **–c** parancssori kapcsoló után. |

### Az alkalmazásburkoló eszköz naplófájljai
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


### Tanúsítvány, létesítési profil és hitelesítési követelmények

Az alkalmazásburkoló eszköz optimális működéséhez bizonyos követelményeknek teljesülnie kell.

|Követelmény|Részletek|
|---------------|-----------|
|Létesítési profil|**Használat előtt ellenőrizze a létesítési profil érvényességét**. iOS-alkalmazások feldolgozásánál az alkalmazásburkoló eszköz nem ellenőrzi a létesítési profil érvényességét. Ha lejárt létesítési profil van megadva, az alkalmazásburkoló eszköz tartalmazza a lejárt létesítési profilt, és addig nem szerez tudomást a problémáról, amíg az alkalmazás telepítése meg nem hiúsul egy iOS-eszközön.|
|Tanúsítvány|**Használat előtt ellenőrizze a tanúsítvány érvényességét**. iOS-alkalmazások feldolgozásánál az alkalmazásburkoló eszköz nem ellenőrzi a tanúsítvány érvényességét. Ha lejárt tanúsítvány kivonatát adja meg, az eszköz feldolgozza és aláírja az alkalmazást, de nem tudja telepíteni az eszközökre.<br /><br />**Ellenőrizze, hogy a burkolt alkalmazás aláírásához megadott tanúsítvány rendelkezik-e egyezéssel a létesítési profilban**. Az eszköz nem ellenőrzi, hogy a létesítési profil rendelkezik-e egyezéssel a burkolt alkalmazás aláírásához megadott tanúsítványhoz.|
|Hitelesítés|A titkosítás működéséhez az eszközöknek PIN-kóddal kell rendelkezniük. Azokon az eszközökön, amelyekhez burkolt alkalmazást telepített, az eszközön lévő állapotjelző sáv megérintése esetén a felhasználónak újra hitelesíteni kell az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-nal. A burkolt alkalmazások alapértelmezett szabályzata a *hitelesítés újraindításkor*. Az iOS minden külső értesítést (például egy telefonhívást) az alkalmazásból való kilépéssel és annak újraindításával kezel.


## Alkalmazásjogosultságok beállítása
Az alkalmazást a burkolása előtt **jogosultságok** megadásával további engedélyekkel és képességekkel láthatja el. Ezek segítségével tovább bővítheti az alkalmazás által elvégezhető tevékenységek körét.  A kódaláírás során a rendszer **jogosultságot tartalmazó fájlt** használ a speciális engedélyek (például megosztott kulcslánchoz való hozzáférés) megadásához az alkalmazáson belül. Az alkalmazás **képességek** néven ismert specifikus szolgáltatások az alkalmazásfejlesztés során az Xcode-on belül engedélyezhetők. Miután engedélyezte őket, a képességek megjelennek a jogosultságokat tartalmazó fájlban. A jogosultságokról és képességekről az iOS Developer Library [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Képességek hozzáadása) című témakörében olvashat bővebben. A támogatott képességek teljes listáját a [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Támogatott képességek) című témakörben találja.

### Az iOS rendszerhez készült alkalmazásburkoló eszköz támogatott képességei

|Képesség|Leírás|Ajánlott útmutatás|
|--------------|---------------|------------------------|
|Alkalmazáscsoportok|Alkalmazáscsoportok használatával biztosíthatja több alkalmazás hozzáférését a megosztott tárolókhoz, és engedélyezheti a folyamatközi kommunikációt az alkalmazások között.<br /><br />Az alkalmazáscsoportok engedélyezéséhez nyissa meg a **Képességek** panelt, és az **Alkalmazáscsoportok** részen kattintson a **BE** kapcsolóra. Felvehet alkalmazáscsoportokat, illetve kijelölhet meglévőket.|Alkalmazáscsoportok használatakor használjon címfeloldási DNS-t:<br /><br />*csoport.com.cégnév.Alkalmazáscsoport*|
|Háttérmódok|A háttérmódok engedélyezése lehetővé teszi az iOS-alkalmazás futtatását a háttérben.||
|Adatvédelem|Az adatvédelem biztosítja az iOS-alkalmazás által a lemezen tárolt fájlok védelmét. Az adatvédelem az adott eszközökön megtalálható beépített titkosítási hardvert használja a fájlok titkosított formában történő tárolásához a lemezen. Az alkalmazást úgy kell létrehozni, hogy használjon adatvédelmet.||
|Alkalmazáson belüli vásárlás|Az alkalmazáson belüli vásárlás közvetlenül az alkalmazásba beépít egy áruházat azáltal, hogy engedélyezi az áruházhoz csatlakozást és a felhasználó fizetéseinek biztonságos feldolgozását. Az alkalmazáson belüli vásárlás segítségével szedheti be a továbbfejlesztett funkciókért vagy az alkalmazása által használható további tartalomért járó díjakat.||
|Kulcslánc megosztása|A kulcslánc megosztása lehetővé teszi, hogy az alkalmazása jelszavakat osszon meg a kulcsláncban a csapata által fejlesztett egyéb alkalmazásokkal.|Kulcslánc megosztásakor használjon címfeloldási DNS-t:<br /><br />*com.cégnév.Kulcslánccsoport*|
|Személyes VPN|A személyes VPN engedélyezésével lehetővé teszi az alkalmazásnak, hogy egyéni VPN-rendszerkonfigurációt hozzon létre és szabályozzon a Hálózati bővítmény keretrendszer használatával.||
|Leküldéses értesítések|Az Apple Push Notification szolgáltatás (APNs) lehetővé teszi, hogy a nem az előtérben futó alkalmazások értesítsék a felhasználót arról, hogy információi vannak a számára.|A leküldéses értesítések működéséhez alkalmazásspecifikus létesítési profilt kell használnia.<br /><br />Kövesse az [Apple fejlesztői dokumentációjában](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) megadott lépéseket.|
|Vezeték nélküli tartozék konfigurációja|A vezeték nélküli tartozék konfigurációja felveszi a külsőtartozék-támogatási keretrendszert a projektjébe, és lehetővé teszi az alkalmazásnak az MFi Wi-Fi tartozékok konfigurálását.||

### A jogosultságok engedélyezésének lépései

1.  Képességek engedélyezése az alkalmazásban:

    1.  Az Xcode-ban keresse meg az alkalmazás célját, és kattintson a **Képességek** panelre.

    2.  Kapcsolja be a megfelelő képességeket. Az egyes képességekről és a megfelelő értékek meghatározásáról az iOS Developer Library [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Képességek hozzáadása) című témakörében olvashat bővebben.

    3.  Jegyezze fel a folyamat során létrehozott azonosítókat.

    4.  Készítse el és írja alá a burkolandó alkalmazást.

2.  Jogosultságok engedélyezése a létesítési profiljában:

    1.  Jelentkezzen be az Apple Developer Member Center webhelyre.

    2.  Hozzon létre egy létesítési profilt az alkalmazásához. Utasításokért lásd: [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Az Intune App Wrapping Tool for iOS előfeltételeinek megteremtése).

    3.  A létesítési profiljában engedélyezze ugyanazokat a jogosultságokat, amelyekkel az alkalmazásában rendelkezik. Adja meg ugyanazokat az azonosítókat, amelyeket az alkalmazása fejlesztése során adott meg.

    4.  Fejezze be a létesítési profil varázslót, és töltse le a fájlt.

3.  Ellenőrizze, hogy minden előfeltétel teljesült-e, majd burkolja az alkalmazást.

### A jogosultságokkal kapcsolatos gyakori hibák elhárítása
Ha az iOS rendszerhez készült alkalmazásburkoló eszköz jogosultsággal kapcsolatos hibát jelenít meg, próbálkozzon meg az alábbi hibaelhárítási lépésekkel.

|Probléma|Ok|Megoldás|
|---------|---------|--------------|
|Nem sikerült a bemeneti alkalmazás által létrehozott jogosultságok elemzése.|Az alkalmazásburkoló eszköz nem tudja olvasni az alkalmazásból kinyert jogosultságfájlt. Előfordulhat, hogy a jogosultságfájl helytelenül formázott.|Vizsgálja meg az alkalmazásához tartozó jogosultságfájlt. Ehhez kövesse az alábbi utasításokat. A jogosultságfájl vizsgálatakor ellenőrizze, hogy nem tartalmaz-e hibás szintaxist. A fájlnak XML formátumúnak kell lennie.|
|A létesítési profilban jogosultságok hiányoznak (a hiányzó jogosultságok listában láthatók). Csomagolja újra az alkalmazást egy olyan létesítési profillal, amely tartalmazza ezeket a jogosultságokat.|A létesítési profilban engedélyezett jogosultságok és az alkalmazásban engedélyezett képességek között eltérés tapasztalható. Ez az eltérés érvényes az adott képességekhez (vagyis az alkalmazáscsoportokhoz, kulcslánc-hozzáféréshez stb.) társított azonosítókra is.|Általában létrehozhat egy új létesítési profilt, amely ugyanazokat a képességeket engedélyezi, mint az alkalmazás. Ha nem egyeznek meg a profil és az alkalmazás között az azonosítók, az alkalmazásburkoló eszköz lecseréli őket (ha tudja). Ha az új létesítési profil létrehozását követően továbbra is megjelenik a hibaüzenet, próbálja meg eltávolítani a jogosultságokat az alkalmazásból az **–e** paraméter használatával (lásd az alábbi „Jogosultságok eltávolítása az alkalmazásból az –e paraméter használatával” című részt).|

### Aláírt alkalmazás meglévő jogosultságainak megkeresése
Aláírt alkalmazás és létesítési profil meglévő jogosultságainak ellenőrzése:

1.  Keresse meg az .ipa fájlt, és módosítsa .zip kiterjesztésűre.

2.  Bontsa ki a .zip fájlt. Ez a művelet létrehoz egy Payload nevű mappát, amely tartalmazza az .app csomagot.

3.  A codesign eszközzel ellenőrizze a jogosultságokat az .app csomagon az alábbi módon:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    ahol a `YourApp.app` a .app csomag tényleges neve.

4.  A security eszközzel ellenőrizze az alkalmazás beágyazott létesítési profiljának jogosultságait:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    ahol a `YourApp.app` a .app csomag tényleges neve.

### Jogosultságok eltávolítása az alkalmazásból az –e paraméter használatával
Ezzel a paranccsal eltávolítja az alkalmazásból azon engedélyezett képességeket, amelyek nem szerepelnek a jogosultságokat tartalmazó fájlban. Ha olyan képességeket távolít el, amelyeket az alkalmazás használ, az az alkalmazás meghibásodásához vezethet. Hiányzó képességeket például abban az esetben érdemes eltávolítani, ha egy partner által fejlesztett alkalmazás alapértelmezés szerint rendelkezik az összes képességgel.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Biztonság és adatvédelem az alkalmazásburkoló eszköz esetén
Az alkalmazásburkoló eszköz használatakor kövesse az alábbi biztonsági és adatvédelmi gyakorlati tanácsokat.

-   Az aláíró tanúsítványnak, a létesítési profilnak és a megadott üzletági alkalmazásnak ugyanazon a macOS számítógépen kell lennie, amelyet az alkalmazásburkoló eszköz futtatásához használ. Ha a fájlok egy UNC elérési úton vannak, ellenőrizze, hogy elérhetők-e a macOS számítógépről. Az elérési utat IPsec- vagy SMB-aláírással védeni kell.

    Az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konzolra importált burkolt alkalmazásnak ugyanazon a számítógépen kell lennie, mint amelyen az eszközt futtatja. Ha a fájl egy UNC elérési úton van, győződjön meg arról, hogy az elérhető az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konzolt futtató számítógépen. Az elérési utat IPsec- vagy SMB-aláírással védeni kell.

-   IPsec- vagy SMB-aláírással kell védeni azt a környezetet, ahová az alkalmazásburkoló eszközt a GitHub-tárházból letölti.

-   A feldolgozott alkalmazásnak megbízható forrásból kell származnia ahhoz, hogy a támadások elleni védelmét biztosítani lehessen.

-   Győződjön meg arról, hogy az alkalmazásburkoló eszközben megadott kimeneti mappa (különösen ha az egy távoli mappa) védett.

-   A fájlfeltöltési párbeszédpanelt tartalmazó iOS-alkalmazások lehetővé tehetik a felhasználóknak, hogy megkerüljék az alkalmazáshoz megadott kivágási, másolási és beillesztési korlátozásokat. A felhasználók a fájlfeltöltési párbeszédpanelt használhatják például az alkalmazásadatok képernyőfelvételének feltöltéséhez.

-   Amikor a felhasználók egy burkolt alkalmazásból figyelik az eszközükön lévő dokumentummappát, egy **.msftintuneapplauncher**nevű mappát láthatnak. Ha ez a mappa megváltozott vagy törölték, az hatással lehet a korlátozott alkalmazások megfelelő működésére.

### További információ
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->



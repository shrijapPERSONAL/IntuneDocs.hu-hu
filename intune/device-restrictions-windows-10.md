---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Windows 10 esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a Windows 10-es eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b49c227e3cae6c5dca8655362cfbfa6fd3f94807
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>A Windows 10-es és újabb verzióinak eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Általános
-   **Képernyőfelvétel (csak mobileszköz)** – A felhasználó képként rögzítheti a képernyőn látható tartalmat.
-   **Másolás és beillesztés (csak mobileszköz)** – Engedélyezi az alkalmazások közötti másolási és beillesztési műveletet az eszközön.
-   **Regisztráció manuális törlése** – Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
-   **Főtanúsítvány manuális telepítése (csak mobileszköz)** – Letiltja a felhasználó számára a főtanúsítványok és a köztes szolgáltatói tanúsítványok manuális telepítését.
-   **Diagnosztikai adatok küldése** – A lehetséges értékek a következők:
    -       **Nincs** – Az eszköz nem küld adatokat a Microsoftnak.
    -       **Alapszintű** – Az eszköz korlátozott információkat küld a Microsoftnak
    -       **Bővített** – Az eszköz bővebb diagnosztikai adatokat küld a Microsoftnak
    -       **Teljes** – A Bővített beállítással küldött adatok mellett az eszköz állapotával kapcsolatos információkat is küld.
-   **Kamera** – Engedélyezi vagy letiltja az eszköz kamerájának használatát.
-   **OneDrive-fájlszinkronizálás** – Letiltja az eszköz fájljainak OneDrive-ba való szinkronizálását.
-   **Cserélhető tároló** – Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.
-   **Földrajzi hely** – Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.
-   **Internetkapcsolat megosztása** – Engedélyezi az internetkapcsolat megosztását az eszközön.
-   **Telefon alaphelyzetbe állítása** – Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait.
-   **USB-kapcsolat (csak mobileszköz)** – Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.
-   **Lopásgátló üzemmód (csak mobileszköz)** – Itt az állítható be, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.
-   **Cortana** – Engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztenst.
-   **Hangrögzítés (csak mobileszköz)** – Engedélyezi vagy letiltja az eszköz hangrögzítőjét.
-   **Az eszköz nevének módosítása** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz nevét (csak Windows 10 mobil verzió esetén)
-   **Kiépítési csomagok hozzáadása** – Megakadályozza, hogy a konfigurációs ügynök kiépítési csomagokat telepítsen.
-   **Kiépítési csomagok eltávolítása** – Megakadályozza, hogy a konfigurációs ügynök kiépítési csomagokat távolítson el.
-   **Eszközfelderítés** – Letiltja az eszköz más eszközök általi felderíthetőségét.
-   **Feladatváltó (csak mobileszköz)** – Letiltja a feladatváltót az eszközön.
-   **SIM-kártyahibát jelző párbeszédpanel (csak mobileszköz)** – Letiltja a hibaüzenetet, amely akkor jelenne meg, amikor a rendszer nem észlel SIM-kártyát az eszközön.


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
-   **Titkosítás** – Engedélyezi a célzott eszközök titkosítását (csak Windows 10 Mobile esetén).

## <a name="personalization"></a>Személyre szabás

-   **Asztali háttérkép URL-címe (csak asztali verzióban)** – A Windows asztali háttérképeként használandó PNG, JPG vagy JPEG formátumú kép URL-címének megadása. A felhasználók ezt a beállítást nem változtathatják meg.

## <a name="privacy"></a>Személyes adatok védelme

-   **Bemenet személyre szabása** – Ne engedélyezze a felhőalapú beszédszolgáltatások használata a Cortanához, diktáláshoz vagy a Windows Áruház alkalmazásaihoz. Ha engedélyezi ezeket a szolgáltatásokat, a Microsoft hangadatokat gyűjthet a szolgáltatás fejlesztéséhez.
-   **A társításra és adatvédelemre vonatkozó felhasználói beleegyezést kérő üzenetek automatikusa elfogadása** – Lehetővé teszi a Windowsnak, hogy automatikusan elfogadja a társítási és adatvédelmi beleegyezést kérő üzeneteket az alkalmazások futtatása közben.


## <a name="locked-screen-experience"></a>Zárolási képernyő felülete


-   **Műveletközpont értesítései (csak mobileszköz)** – Engedélyezi a Műveletközpont értesítéseinek megjelenését az eszköz zárolási képernyőjén (csak Windows 10 Mobile esetén).
-   **Zárolási képernyő URL-címe (csak asztali verzióban)** – A Windows zárolási képernyőjének háttérképeként használandó PNG, JPG vagy JPEG formátumú kép URL-címét adja meg. A felhasználók ezt a beállítást nem változtathatják meg.
-   **Felhasználó által konfigurálható képernyő-időkorlát (csak mobilon)** – Engedélyezi a felhasználóknak az időtartam konfigurálását 
-   **Cortana zárolt képernyőn (csak asztali verzió)** – Nem engedélyezi, hogy a felhasználó interakcióba lépjen a Cortanával, ha a képernyő zárolva van (csak Windows 10 asztali verziónál).
-   **Bejelentési értesítések zárolt képernyőn** – Riasztások megjelenítésének letiltása az eszköz zárolási képernyőjén.
-   **Képernyő időkorlátja (csak mobilon)** – A képernyő zárolási idejének megadása másodpercben, aminek elteltével kikapcsol.



## <a name="app-store"></a>Alkalmazásáruház

-   **Alkalmazás-áruház (csak mobileszköz)** – Engedélyezi vagy letiltja az alkalmazásáruházat a Windows 10 Mobile rendszerű eszközökön.
-   **Áruházból származó alkalmazások automatikus frissítése** – Engedélyezi a Windows Áruházból származó alkalmazások automatikus frissítését.
-   **Megbízható alkalmazás telepítése** – Engedélyezi a megbízható tanúsítvánnyal aláírt alkalmazások közvetlen telepítését.
-   **Fejlesztői zárolás feloldása** – Engedélyezi, hogy a Windows fejlesztői beállításait (például alkalmazások közvetlen telepítését) a végfelhasználók megváltoztassák.
-   **Megosztott felhasználói alkalmazásadatok** – Engedélyezi, hogy ugyanazon az eszközön a felhasználók megoszthassák egymás között az alkalmazásadatokat.
-   **Csak privát áruház használata** – Ennek a beállításnak az engedélyezésével a felhasználók csak a privát áruházból származó alkalmazásokat tölthetik le.
-   **Áruházból származó alkalmazások indítása** – Letiltja az összes előre telepített és a Windows Áruházból letöltött alkalmazást az eszközön.
-   **Alkalmazásadatok telepítése a rendszerköteten** – Megakadályozza, hogy az alkalmazások adatokat tároljanak az eszköz rendszerkötetén.
-   **Alkalmazások telepítése a rendszermeghajtón** – Megakadályozza, hogy az alkalmazások adatokat tároljanak az eszköz rendszermeghajtóján.
-   **Játékvideó-rögzítő (csak asztali verzióban)** – Meghatározza, hogy engedélyezett-e játékok rögzítése és közvetítése.
-   **Csak áruházból származó alkalmazások** – Meghatározza, hogy a felhasználók telepíthetnek-e alkalmazásokat az alkalmazás-áruháztól különböző forrásokból.



## <a name="edge-browser"></a>Edge böngésző
-   **Microsoft Edge böngésző (csak mobil)** – Engedélyezi az Edge böngésző használatát az eszközön.
-   **Címsor legördülő funkciója (csak asztali gép)** – Ezzel akadályozhatja meg, hogy az Edge megjelenítse a javaslatok listáját egy legördülő menüben gépelés közben. Ezzel minimalizálhatja a hálózati sávszélességnek az Edge és a Microsoft szolgáltatásai közötti használatát.
-   **Kedvencek szinkronizálása a Microsoft-böngészők között (csak asztali gépek)** – Lehetővé teszi, hogy a Windows szinkronizálja a kedvenceket az Internet Explorer és az Edge között.
-   **„Do Not Track” fejlécek küldése** – Arra konfigurálja az Edge böngészőt, hogy Do Not Track (Követés letiltása) fejléceket küldhessen a felhasználók által meglátogatott webhelyeknek.
-   **Cookie-k** – Engedélyezi a böngészőnek, hogy mentse az internetről érkező cookie-kat az eszközre.
-   **JavaScript** – Engedélyezi a szkriptek (például a JavaScript) futtatását az Edge böngészőben.
-   **Előugró ablakok** – Blokkolja az előugró ablakokat a böngészőben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Keresési javaslatok** – Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
-   **Intranetes forgalom átirányítása az Internet Explorerbe** – Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Automatikus kitöltés** – Engedélyezi a felhasználók számára, hogy módosítsák a böngésző automatikus kiegészítési funkciójának beállításait (csak a Windows 10 asztali verzióra vonatkozik).
-   **Jelszókezelő** – Engedélyezi vagy letiltja az Edge böngésző Jelszókezelő szolgáltatását.
-   **Vállalati üzemmód webhelylistájának helye** – Megadja, hogy hol található a Vállalati üzemmódban megnyíló webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.<br>(Csak a Windows 10 asztali verzió.)
-   **Fejlesztői eszközök** – Megakadályozza, hogy a végfelhasználók megnyithassák az Edge fejlesztői eszközeit.
-   **Bővítmények** – Engedélyezi, hogy a végfelhasználók Edge-bővítményeket telepítsenek az eszközön.
-   **InPrivate-böngészés** – Megakadályozza, hogy a végfelhasználók InPrivate-böngészési munkamenetet nyissanak meg.
-   **Első futtatáskori oldal megjelenítése** – Megakadályozza a bemutató lap megjelenítését az Edge első futtatásakor.
    -   **Első futtatás URL-címe** – Megadhatja annak a lapnak az URL-címét, amely akkor jelenik meg, amikor a felhasználó első alkalommal futtatja az Edge böngészőt (csak Windows 10 mobil verziónál).
-   **Kezdőlapok** – Azoknak a webhelyeknek a listája, amelyek kezdőlapokként szeretne megjeleníteni az Edge böngészőben (csak asztali verzióban).
-   **Kezdőlap módosítása** – Engedélyezheti a felhasználóknak, hogy megváltoztassák az Edge megnyitásakor megjelenő kezdőlapokat. A Kezdőlapok beállítással hozhatja létre az Edge indításakor megjelenő lapot vagy lapok listáját.
-   **Az about:flags laphoz való hozzáférés letiltása** – Megakadályozza, hogy a végfelhasználó hozzáférhessen az Edge about:flags lapjához, amely a fejlesztői és kísérleti beállításokat tartalmazza.
-   **WebRTC LocalHost IP-címe** – Letiltja a felhasználó localhost IP-címének megjelenítését a WebRTC protokollal történő telefonhívások esetén.
-   **Alapértelmezett keresőmotor** – Meghatározza az alapértelmezetten használandó keresőmotort. A végfelhasználók ezt az értéket bármikor módosíthatják.
-   **Böngészési adatok törlése kilépéskor** – Előzmények és böngészési adatok törlése, amikor a felhasználó bezárja az Edge böngészőt.
-   **Adatgyűjtés élő csempéhez** – Leállítja a Windows élő csempéből történő adatgyűjtését, amikor a felhasználók kitűznek az Edge böngészőből egy webhelyet a Start menübe.

## <a name="edge-browser-smartscreen"></a>Az Edge böngésző SmartScreen funkciója

-   **SmartScreen** – Engedélyezi vagy letiltja a rosszindulatú webhelyeket blokkoló SmartScreen funkciót.
-   **SmartScreen-üzenetek felülbírálása** – Engedélyezi, hogy a végfelhasználó letilthassa a SmartScreen szűrő által megjelenített, az esetlegesen rosszindulatú webhelyekre figyelmeztető üzeneteket.
-   **SmartScreen-üzenetek felülbírálása fájlok esetén** – Engedélyezi, hogy a végfelhasználó letilthassa a SmartScreen szűrő által megjelenített, az esetlegesen rosszindulatú fájlok letöltésére figyelmeztető üzeneteket.

## <a name="search"></a>Keresés
- **Biztonságos keresés (csak mobileszközökön)** – Meghatározza, hogy a Cortana hogyan szűrje a felnőtt tartalmat a keresési eredményekben. A megadható értékek a **Szigorú** és a **Közepes**, vagy engedélyezhető, hogy a végfelhasználó állítsa be az értékét.

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
-   **Bluetooth-engedélyezett szolgáltatások** – Az engedélyezett Bluetooth-szolgáltatások és -profilok meghatározása hexadecimális karakterláncokként.


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

## <a name="defender"></a>Defender

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



## <a name="defender-exclusions"></a>A Defender vizsgálata alóli kivételek

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
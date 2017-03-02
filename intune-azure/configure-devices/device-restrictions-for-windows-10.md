---
title: "Az Intune eszközkorlátozásokra vonatkozó beállításai Windows 10-hez | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a Windows 10-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 208312eea9df0b6330e6eac9334bd63bb13624c5
ms.lasthandoff: 02/16/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>A Windows 10-es és újabb verzióinak eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Általános
-     **Képernyőfelvétel** – Engedélyezése esetén a felhasználó rögzítheti képként a képernyőn látható tartalmat. (csak a Windows 10 Mobile)
-     **Másolás és beillesztés (csak mobileszköz)** – Engedélyezi az alkalmazások közötti másolási és beillesztési műveletet az eszközön.
-     **Regisztráció manuális törlése** – Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
-     **Főtanúsítvány manuális telepítése** -     
-     **Diagnosztikai adatok küldése** – A lehetséges értékek a következők:
    -         **Nincs** – Az eszköz nem küld adatokat a Microsoftnak.
    -         **Alapszintű** – Az eszköz korlátozott információkat küld a Microsoftnak
    -         **Bővített** – Az eszköz bővebb diagnosztikai adatokat küld a Microsoftnak
    -         **Teljes** – A Bővített beállítással küldött adatok mellett az eszköz állapotával kapcsolatos információkat is küld.
-     **Kamera** – Engedélyezi vagy letiltja az eszköz kamerájának használatát.
-     **Cserélhető tároló** – Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.
-     **Földrajzi hely** – Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.
-     **Internetkapcsolat megosztása** – Engedélyezi az internetkapcsolat megosztását az eszközön.
-     **Telefon alaphelyzetbe állítása** – Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait.
-     **USB-kapcsolat** – Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.
-     **Lopásgátló üzemmód** – Itt az állítható be, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.
-     **Műveletközpont értesítései** – Engedélyezi vagy letiltja a Műveletközpont értesítéseinek megjelenését az eszköz zárolási képernyőjén (csak Windows 10 Mobile).
-     **Cortana** – Engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztenst.
-     **Hangrögzítés** – Engedélyezi vagy letiltja az eszköz hangrögzítőjét.

## <a name="password"></a>Jelszó
-     **Jelszó megkövetelése** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
-     **Kért jelszótípus** – Azt határozza meg, hogy a jelszó csak számokból vagy számokból és betűkből állhat.
-     **Jelszó minimális hossza** – Csak a Windows 10 Mobile verzióra vonatkozik.
-     **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Windows 10-es eszközök esetében: ha a BitLocker engedélyezve van az eszközön, akkor az a megadott számú sikertelen bejelentkezési kísérlet után a BitLocker helyreállítási módjába kerül. Ha az eszközön nincs engedélyezve a BitLocker, akkor ez a beállítás nem alkalmazható.
Windows 10 Mobile-eszközök esetében: a megadott számú sikertelen bejelentkezési kísérlet után az eszköz tartalma törlődik.
-     **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.
-     **Jelszó érvényessége (nap)** – Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót.
-     **Korábbi jelszavak újbóli használatának tiltása** – Azt határozza meg, hogy az eszköz hány korábban használt jelszót jegyezzen meg.
-     **Jelszó kérése, ha az eszköz visszatér az inaktív állapotból** – Azt adja meg, hogy köteles-e a felhasználó jelszót megadni az eszköz feloldásához (csak Windows 10 Mobile esetén).
-     **Titkosítás** – Engedélyezi a célzott eszközök titkosítását (csak Windows 10 Mobile esetén).
## <a name="app-store"></a>Alkalmazás-áruház

-     **Alkalmazás-áruház (csak mobileszköz)** – Engedélyezi vagy letiltja az alkalmazásáruházat a Windows 10 Mobile rendszerű eszközökön.
## <a name="edge-browser"></a>Edge böngésző
-     **Microsoft Edge böngésző (csak mobil)** – Engedélyezi az Edge böngésző használatát az eszközön.
-     **SmartScreen** – Engedélyezi vagy letiltja a csalárd webhelyeket blokkoló SmartScreen funkciót.
-     **„Do Not Track” fejlécek küldése** – Arra konfigurálja az Edge böngészőt, hogy Do Not Track (Követés letiltása) fejléceket küldhessen a felhasználók által meglátogatott webhelyeknek.
-     **Cookie-k** – Engedélyezi a böngészőnek, hogy mentse az internetről érkező cookie-kat az eszközre.
-     **JavaScript** – Engedélyezi a szkriptek (például a JavaScript) futtatását az Edge böngészőben.
-     **Előugró ablakok** – Blokkolja az előugró ablakokat a böngészőben.<br>(Csak a Windows 10 asztali verzióra vonatkozik.)
-     **Keresési javaslatok** – Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
-     **Intranetes forgalom átirányítása az Internet Explorerbe** – Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben. <br>(Csak a Windows 10 asztali verzió.)
-     **Automatikus kitöltés** – Engedélyezi a felhasználók számára, hogy módosítsák a böngésző automatikus kiegészítési funkciójának beállításait.<br>(csak a Windows 10 asztali verzió)
-     **Jelszókezelő** – Engedélyezi vagy letiltja az Edge böngésző Jelszókezelő szolgáltatását.
-     **Vállalati üzemmód webhelylistájának helye** – Megadja, hogy hol található a Vállalati üzemmódban megnyíló webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.<br>(Csak a Windows 10 asztali verzió.)
## <a name="cloud-and-storage"></a>Felhő és tárolás
-     **Microsoft-fiók** – Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.
-     **Nem Microsoft-fiók** – Lehetővé teszi, hogy a felhasználó olyan e-mail-fiókokat vegyen fel az eszközön, amelyek nincsenek Microsoft-fiókhoz társítva.
-     **Microsoft-fiók beállításszinkronizálása** – Lehetővé teszi a Microsoft-fiókhoz kapcsolódó eszköz- és alkalmazásbeállítások szinkronizálását az eszközök között.
## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok
-     **Adatroaming** – Engedélyezi a hálózatok közötti roamingot adatok elérése közben.
-     **Mobilhálózati VPN** – Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.
-     **Mobilhálózati VPN-barangolás** – Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming közben.
-     **Bluetooth** – Azt szabályozza, hogy a felhasználó engedélyezheti és konfigurálhatja-e a Bluetooth-t az eszközön.
-     **Bluetooth-észlelhetőség** – Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök számára.
-     **Bluetooth-hirdetés** – Lehetővé teszi az eszköz számára, hogy hirdetéseket fogadjon a Bluetooth-kapcsolaton.
-     **NFC** – Lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja az NFC funkciót az eszközön.
-     **Wi-Fi** – Lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja a Wi-Fi funkciót az eszközön (csak Windows 10 Mobile esetén).
-     **Automatikus csatlakozás Wi-Fi-elérési pontokhoz** – Engedélyezi az eszközön az ingyenes Wi-Fi-elérési pontokhoz történő automatikus csatlakozást és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadását.
-     **Wi-Fi manuális konfigurálása** – Azt szabályozza, hogy a felhasználó konfigurálhat-e saját Wi-Fi-kapcsolatokat, vagy csak a Wi-Fi-profillal konfigurált kapcsolatokat használhatja (csak Windows 10 Mobile esetén).
## <a name="defender"></a>Defender

-     **Valós idejű figyelés engedélyezése** – Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű keresését.
-     **Viselkedésfigyelés engedélyezése** – Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.
-     **Hálózatvizsgáló rendszer (NIS)** – A hálózatvizsgáló rendszer (NIS) az ismert biztonsági réseknek a Microsoft Endpoint Protection-központtól származó aláírásai alapján észleli és blokkolja a kártékony hálózati forgalmat, ezáltal segíti az eszközök védelmét a hálózati támadásokkal szemben.
-     **Minden letöltött fájl vizsgálata** – Meghatározza, hogy a Defender megvizsgálja-e az internetről letöltött összes fájlt.
-     **Microsoft-webböngészőkben betöltött szkriptek vizsgálata** – Engedélyezi a Defender számára az Internet Explorer által használt szkriptek vizsgálatát.
-     **Végfelhasználói hozzáférés a Defenderhez** – Azt szabályozza, hogy a Windows Defender kezelőfelülete el legyen-e rejtve a végfelhasználók elől.
Módosítás esetén a beállítás a végfelhasználó számítógépének következő újraindításakor lép érvénybe.
-     **Aláírás-frissítési időköz (óra)** – Meghatározza, hogy a Defender milyen időközönként keressen új aláírásfájlokat.
-     **Fájl- és programtevékenység figyelése** – Engedélyezi a Defender számára az eszközökön zajló a fájl- és programtevékenység figyelését.
-     **A karanténba zárt kártevők ennyi nap után törlődjenek** – A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok számát **0**-ra állítja, a kártevő a karanténban marad, és a rendszer nem távolítja el automatikusan.
-     **CPU-használati korlát ellenőrzés közben** – Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**-től **100**-ig).
-     **Archív fájlok vizsgálata** – Engedélyezi a Defender számára az archív fájlok – például .zip- vagy .cab-fájlok – vizsgálatát.
-     **Bejövő e-mailek vizsgálata** – Engedélyezi a Defender számára az eszközre érkező e-mailek azonnali vizsgálatát.
-     **A teljes vizsgálat a cserélhető meghajtókra is terjedjen ki** – Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát.
-     **Csatlakoztatott hálózati meghajtók vizsgálata** – Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon lévő fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.
-     **Hálózati mappákból megnyitott fájlok vizsgálata** – Engedélyezi a Defender számára a megosztott hálózati meghajtókon lévő (például UNC elérési úton található) fájlok vizsgálatát.
Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.
-     **Felhővédelem** – Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.
-     **Rákérdezés a mintaküldés előtt** – Azt szabályozza, hogy a rendszer automatikusan elküldje a Microsoftnak azokat a fájlokat, amelyeken további vizsgálat szükséges annak megállapításához, hogy kártékonyak-e.
-     **Napi gyorsvizsgálat időpontja** – Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé.
-     **Rendszervizsgálat típusa** – Az adható meg vele, hogy milyen szintű vizsgálatra kerüljön sor az ütemezett rendszervizsgálatok alkalmával.
## <a name="defender-exclusions"></a>A Defender vizsgálata alóli kivételek

-     **A vizsgálatokból és a valós idejű védelemből kizárandó fájlok és mappák** – Felvesz egy vagy több fájlt vagy mappát (például **C:\Elérési út** vagy **%ProgramFiles%\Elérési út\fájlnév.exe**) a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.
-     **A vizsgálatokból és a valós idejű védelemből kizárandó fájlkiterjesztések** – Ezzel a beállítással egy vagy több fájlnév-kiterjesztés (például **jpg** vagy **txt**) vehető fel a kivételek listájára. A rendszer nem vizsgálja az ilyen kiterjesztésű fájlokat a valós idejű és a ütemezett vizsgálatok során.
-     **A vizsgálatokból és a valós idejű védelemből kizárandó folyamatok** – Ezzel a beállítással egy vagy több **.exe**, **.com** vagy **.scr** típusú folyamat vehető fel a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.


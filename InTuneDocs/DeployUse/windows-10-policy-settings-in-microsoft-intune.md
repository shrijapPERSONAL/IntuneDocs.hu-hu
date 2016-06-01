---
# required metadata

title: Windows 10-es házirend-beállítások a Microsoft Intune-ban | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 10-es házirend-beállítások a Microsoft Intune-ban

A jelen témakörben felsorolt házirend-beállításokkal konfigurálhatja a Windows 10 asztali verziót vagy Windows 10 Mobile-t használó regisztrált eszközökön.

## Az általános konfigurációs szabályzat beállításai

A Microsoft Windows 10-eszközökhöz készült **általános konfigurációs szabályzatát** regisztrált asztali Windows 10- és Windows 10 Mobile-eszközökhöz használhatja:


### Jelszó

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Jelszó kérése az eszközzárolás feloldásához**|Jelszó kérése a támogatott eszközökön.|Igen|Igen|
|**Kötelező jelszótípus**|Meghatározza a megkövetelt jelszótípust, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat|Igen|Igen|
|**Kötelező jelszótípus** - **Karakterkészletek minimális száma**|A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. Ez a beállítás azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban.|Igen|Igen|
|**Jelszó minimális hossza**|Az eszközjelszóban használandó karakterek minimális számát határozza meg.|Nem|Igen|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|A megadott számú sikertelen bejelentkezési kísérlet után törli az eszközt.|Igen|Igen|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.|Igen|Igen|
|**Jelszó lejárata (nap)**|Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót.|Igen|Igen|
|**Jelszóelőzmények megjegyzése**|Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.|Igen|Igen|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás a eszköz által megjegyzett korábbi jelszavak számát határozza meg.|Igen|Igen|
|**Képjelszó és PIN-kód engedélyezése**|Lehetővé teszi egy képen egyszerű kézmozdulatok, vagy egy egyszerű PIN-kód használatát a bejelentkezéshez.|Igen|Nem|
|**Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**|Engedélyezése esetén a felhasználónak meg kell adnia egy jelszót, ha szeretné feloldani az inaktív állapotú eszköz zárolását.|Nem|Igen|

### Titkosítás

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Mobileszköz titkosításának kötelezővé tétele**|Aktiválja a titkosítást a megcélzott eszközökön.|Nem|Igen|

### Rendszer

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Képernyőfelvétel-készítés használatának engedélyezése**|Engedélyezése esetén a felhasználó rögzítheti képként a képernyőn látható tartalmat.|Nem|Igen|
|**Regisztráció manuális törlésének engedélyezése**|Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.|Igen|Igen|
|**Főtanúsítvány manuális telepítésének engedélyezése**|Meghatározza, hogy a felhasználó telepíthet-e manuálisan főtanúsítványokat|Nem|Igen|
|**Diagnosztikai és használati adatok küldésének engedélyezése a Microsoft felé**|Meghatározza, hogy az eszközök mennyi diagnosztikai és használati adatot küldjenek a Microsoftnak.<br>**Nem** – Az eszköz nem küld adatokat a Microsoftnak.<br>**Alapszintű** – Az eszköz csak korlátozott mennyiségű információt küld a Microsoftnak.<br>**Bővített** – Az eszköz bővebb diagnosztikai adatokat küld a Microsoftnak.<br>**Teljes (ajánlott)** – A **Bővített** beállítással küldött adatok mellett az eszköz állapotával kapcsolatos információkat is küld.|Igen|Igen|


### Fiók és szinkronizálás

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Microsoft-fiók használatának engedélyezése**|Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.|Igen|Igen|
|**Nem Microsoft-fiókok manuális felvételének engedélyezése**|Lehetővé teszi, hogy a felhasználó olyan e-mail fiókokat vegyen fel az eszközön, amelyek nincsenek Microsoft-fiókhoz társítva.|Igen|Igen|
|**Beállítások szinkronizálásának engedélyezése Microsoft-fiók esetén**|Lehetővé teszi a Microsoft-fiókhoz kapcsolódó eszköz- és alkalmazásbeállítások szinkronizálását az eszközök között.|Igen|Igen|

### E-mail beállítások

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**A Microsoft-fiók opcionálissá tétele a Windows Mail alkalmazásban**|A beállítás engedélyezése esetén nem kötelező Microsoft-fiókot használni a Windows Posta alkalmazásban.|Igen|Nem|



### Microsoft Edge

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Webböngésző használatának engedélyezése**|Engedélyezi az Edge webböngésző használatát az eszközön.|Nem|Igen|
|**Keresési javaslatok engedélyezése a címsorban**|Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.|Igen|Igen|
|**Intranetes adatforgalom küldésének engedélyezése az Internet Explorerbe**|Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben.|Igen|Nem|
|**Követés letiltásának engedélyezése**|Lehetővé teszi az Edge böngésző számára a Do Not Track (Követés letiltása) fejlécek küldését a felhasználók által meglátogatott webhelyeknek.|Igen|Igen|
|**SmartScreen engedélyezése**|Aktiválja a SmartScreen böngészőbeállítást az eszközökön.|Igen|Igen|
|**Active Scripting engedélyezése**|A parancsprogramok, például a JavaScriptek futtatásának engedélyezése az Edge böngészőben.|Igen|Igen|
|**Előugró ablakok engedélyezése**|A böngésző előugróablak-blokkolójának engedélyezése vagy letiltása.|Igen|Nem|
|**Cookie-k engedélyezése**|A cookie-k engedélyezésére vagy letiltására szolgál.|Igen|Igen|
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.|Igen|Nem|
|**Jelszókezelő engedélyezése**|Az Edge böngésző Jelszókezelő szolgáltatásának engedélyezése vagy letiltása.|Igen|Igen|
|**Vállalati üzemmód webhelylistájának helye**|Megadja, hogy hol található a Vállalati üzemmódban megnyitott webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.|Igen|Nem|

### Alkalmazások

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Alkalmazástároló használatának engedélyezése**|Az alkalmazás-áruház használatának engedélyezése az eszközön.|Nem|Igen|



### Mobil

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Adatroaming használatának engedélyezése**|Hálózatok közötti barangolás engedélyezése adatok elérése közben.|Igen|Igen|
|**VPN engedélyezése mobilhálózaton**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.|Igen|Igen|
|**VPN engedélyezése mobilhálózati roaming esetén**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming esetén.|Igen|Igen|

### Hardver

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Kamera használatának engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a kamera.|Igen|Igen|
|**Cserélhető tároló használatának engedélyezése**|Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.|Igen|Igen|
|**Wi-Fi használatának engedélyezése**|Az eszköz Wi-Fi funkciójának engedélyezése.|Nem|Igen|
|**Internetmegosztás engedélyezése**|Az internetmegosztás engedélyezése az eszközön.|Igen|Igen|
|**Manuális Wi-Fi konfiguráció engedélyezése**|Azt szabályozza, hogy a felhasználó konfigurálhat-e saját Wi-Fi kapcsolatokat, vagy csak a Wi-Fi profillal konfigurált kapcsolatokat használhatja.|Nem|Igen|
|**Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése**|Az ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadásának engedélyezése az eszközön.|Igen|Igen|
|**Földrajzi hely meghatározásának engedélyezése**|Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.|Igen|Igen|
|**NFC használatának engedélyezése**|Engedélyezi az eszköz kis hatótávolságú kommunikációs (NFC) funkciójának használatát.|Igen|Igen|
|**Bluetooth használatának engedélyezése**|Engedélyezi a Bluetooth-képességek használatát az eszközön.|Igen|Igen|
|**Bluetooth-észlelhetőség engedélyezése**|Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.|Igen|Igen|
|**Bluetooth-hirdetés engedélyezése**|Engedélyezi, hogy az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.|Igen|Igen|
|**Bluetooth-csatlakozási üzemmód engedélyezése** **Fontos:** |Ez a beállítás a Windows 10 rendszerben már nem támogatott, és a jövőben meg fog szűnni.|Igen|Igen|
|**Telefon alaphelyzetbe állításának engedélyezése**|Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait.|Igen|Igen|
|**USB-kapcsolat engedélyezése**|Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.|Igen|Igen|
|**Lopásgátló üzemmód engedélyezése**|Annak beállítása, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.|Igen|Igen|

### Jellemzők

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|----------------------|---------------------|
|**Másolás és beillesztés használatának engedélyezése**|A másolás és beillesztés engedélyezése vagy letiltása az eszközön.|Nem|Igen|
|**Hangrögzítés engedélyezése**|Az eszköz hangrögzítési funkciói használatának engedélyezése vagy letiltása.|Nem|Igen|
|**A Cortana engedélyezése**|A Cortana beszédfelismerési asszisztens engedélyezése vagy letiltása.|Igen|Igen|
|**Műveletközponti értesítések engedélyezése**|Műveletközponti értesítések engedélyezése vagy letiltása az eszköz zárolási képernyőjén.|Nem|Igen|

### Defender

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|-|-|
|**Valós idejű figyelés engedélyezése**|Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű vizsgálatát.|Igen|Nem|
|**Viselkedésfigyelés engedélyezése**|Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.|Igen|Nem
|**Hálózatfelügyeleti rendszer engedélyezése**|A hálózatvizsgáló rendszer (NIS) a Microsoft Endpoint Protection-központtól származó ismert biztonsági rések aláírásai alapján észleli és blokkolja a kártékony hálózati forgalmat, ezáltal segíti az eszközök védelmét a hálózati támadásokkal szemben.|Igen|Nem
|**Minden letöltött fájl vizsgálata**|Meghatározza, hogy a Defender az internetről letöltött összes fájlt megvizsgálja-e.|Igen|Nem
|**Szkriptek ellenőrzésének engedélyezése**|Engedélyezi a Defender számára az Internet Explorer által használt parancsfájlok vizsgálatát.|Igen|Nem
|**A fájl- és programtevékenység figyelése**|Engedélyezése esetén a Defender megfigyelheti a fájl- és programtevékenységet az eszközökön.|Igen|Nem
|**Ártalmatlanított kártevő szoftverek követése (nap)**|A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok számát **0**-ra állítja, a kártevő a karanténban marad, és a rendszer nem távolítja el automatikusan. |Igen|Nem
|**Ügyfél-kezelőfelület elérésének engedélyezése**|Azt szabályozza, hogy a Windows Defender kezelőfelülete rejtett legyen-e a végfelhasználók számára.<br>Módosítás esetén a beállítás a végfelhasználó számítógépének következő újraindításakor lép érvénybe.|Igen|Nem
|**Napi gyors vizsgálat ütemezése**|Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé.|Igen|Nem
|**Rendszervizsgálat ütemezése**|A választott napokon és időpontban rendszeresen végzett teljes vagy gyors rendszervizsgálat beütemezését teszi lehetővé.|Igen|Nem
|**CPU-használatát korlátozása a vizsgálatok alatt**|Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**%-tól **100**%-ig).)|Igen|Nem
|**Archív fájlok vizsgálata**|Engedélyezi a Defender számára az archív fájlok – például ZIP- vagy CAB-fájlok – vizsgálatát.|Igen|Nem
|**E-mail üzenetek vizsgálata**|Engedélyezi a Defender számára az eszközre érkező e-mailek azonnal vizsgálatát.|Igen|Nem
|**Cserélhető adathordozók vizsgálata**|Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát.|Igen|Nem
|**Csatlakoztatott hálózati meghajtók vizsgálata**|Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon tárolt fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|Igen|Nem
|**Hálózati megosztott mappákból megnyitott fájlok vizsgálata**|Engedélyezi a Defender számára a megosztott hálózati meghajtókon található (például az UNC elérési útvonalon megnyitott) fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|Igen|Nem
|**Aláírás-frissítési időköz**|Meghatározza, hogy a Defender milyen időközönként keressen új aláírásfájlokat.|Igen|Nem
|**Felhővédelem engedélyezése**|Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.|Igen|Nem
|**Minták küldésének kérése a felhasználóktól**|Azt szabályozza, hogy a rendszer automatikusan elküldje a Microsoftnak azokat a fájlokat, amelyeken további vizsgálat szükséges annak megállapításához, hogy kártékonyak-e.|Igen|Nem
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó fájlok és mappák**|Vegye fel a kívánt fájlokat és mappákat – például **C:\Elérési_út** vagy **%ProgramFiles%\Elérési_út\fájlnév.exe** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.|Igen|Nem
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó fájlkiterjesztések**|Vegye fel a kívánt fájlkiterjesztéseket – például **jpg** vagy **txt** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja az ilyen kiterjesztésű fájlokat.|Igen|Nem
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó folyamatok**|Vegye fel a kívánt típusú folyamatokat – **.exe**, **.com** vagy **.scr** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.|Igen|Nem| 


### Frissítések beállításai

|Beállítás neve|Részletek|Windows 10 asztali verzió|Windows 10 mobil verzió|
|----------------|---------------|----------------------|---------------------|
|**Automatikus frissítések engedélyezése**|A beállítás engedélyezésével engedélyezheti az automatikus frissítéseket. Ezt követően a következő lehetőségek egyikének beállításával szabályozhatja a frissítések működését:<br /><br />**Értesítést kérek a letöltésről**<br /><br />**Automatikus telepítés karbantartási időpontban**<br /><br />**Automatikus telepítés és újraindítás karbantartási időpontban**<br /><br />**Automatikus telepítés és újraindítás ütemezett időpontban** **Megjegyzés:** Kiválasztása esetén a következő beállítások konfigurálása is lehetővé válik: **Végfelhasználói értesítések letiltása**, illetve **Adja meg az ütemezett frissítések telepítésének napját**..|Igen|Nem|

## Egyéni házirend-beállítások
A Microsoft Intune Windows 10-hez és a Windows 10 Mobile-hoz készült **egyéni konfigurációs házirendjeivel** OMA-URI beállítások telepíthetők, amelyek a Windows 10- és Windows 10 Mobile-eszközökön elérhető szolgáltatások vezérlésére használhatók. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

E funkció révén olyan Windows 10-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune általános konfigurációs házirendjével. Az ezen házirendekkel konfigurálható beállításokkal kapcsolatos további információért lásd: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

A regisztrált Windows 10-eszközökön konfigurálható OMA-URI beállítások listájáért lásd a jelen témakör „Windows 10-eszközök egyéni URI-beállításai” című szakaszát.

### Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név**|Adjon meg egy egyedi nevet a házirend számára, hogy azonosítható legyen az Intune konzolján.|
    |**Leírás**|Adjon meg egy olyan leírást, amely áttekintést nyújt a szabályzatról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek megkeresésében.|

### OMA-URI-beállítások

|Beállítás neve|Részletek|
    |--------|--------------------|
    |**Beállítás neve**|Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    |**Beállítás leírása**|Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**Adattípus**|Válassza ki a dátumtípust, amelyben meg szeretné adni ezt az OMA-URI beállítást. A következő lehetőségek közül választhat:<br /><br />-   **Karakterlánc**<br />-   **Karakterlánc (XML)**<br />-   **Dátum és időpont**<br />-   **Egész szám**<br />-   **Lebegőpontos szám**<br />-   **Logikai**|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)**|Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    |**Érték**|Adja meg a korábban megadott OMA-URI azonosítóhoz társítandó értéket.|


## Windows 10-eszközök egyéni URI-beállításai
Ez a témakör a Microsoft Intune **egyéni Windows 10-házirendjeiben** konfigurálható beállításokat sorolja fel Windows 10- és Windows 10 Mobile-eszközökhöz..


> [!NOTE]
> Az alábbi táblázat **Támogatás** oszlopában a következő értékeket használjuk:
> 
> -   **Asztali** – A beállítás a csak az Intune-ban regisztrált Windows 10 Professional- és Enterprise-számítógépeket támogatja.
> -   **Mobil** – A beállítás csak a Windows 10 Mobile-eszközöket támogatja.
> -   **Mindkettő** – A beállítás az asztali és mobileszközöket egyaránt támogatja.
> 
> Az összes eszköznek regisztrálva kell lennie az Intune-ban, ha használni kívánja az egyéni Windows URI-házirendet.

### Házirend

|Házirend neve|Támogatás|Részletek|
|---------------|------------|-----------|
|**​Automatikus frissítés engedélyezése**|Asztali|**URI teljes elérési útja**: ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** - **5**<br /><br />**Alapértelmezett érték:** 1|
|**Telepítés napjának ütemezése**|Mindkettő|**URI teljes elérési útja**: ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – naponta<br /><br />**1** – vasárnap<br /><br />**2** – hétfő<br /><br />**3** – kedd<br /><br />**4** – szerda<br /><br />**5** – csütörtök<br /><br />**6** – péntek<br /><br />**7** – szombat.<br /><br />**Alapértelmezett érték:** 0|
|**Telepítés időpontjának ütemezése**|Mindkettő|**URI teljes elérési útja**: ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0**–**23** óra (a 0 éjfélt jelent)<br /><br />**Alapértelmezett érték:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Mobil|**URI teljes elérési útja**: ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – a felhasználó nem állíthatja be a jelszó türelmi idejének időzítőjét, és az érték „minden alkalommal” lesz<br /><br />**1** – a felhasználó beállíthatja a jelszó türelmi idejének időzítőjét<br /><br />**Alapértelmezett érték:** 1|
|**WiFi/AllowWiFi**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezi a **Wi-Fi kapcsolat használatát**..<br /><br />**1** – **Engedélyezi a Wi-Fi kapcsolat használatát**..<br /><br />**Alapértelmezett érték:** 1|
|**WiFi/AllowInternetSharing**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezi az Internetmegosztást.<br /><br />**1** – Engedélyezi az Internetmegosztást<br /><br />**Alapértelmezett érték:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Az MDM által kiépítettektől eltérő Wi-Fi kapcsolatok nem engedélyezettek.<br /><br />**1** – Az MDM által kiépítettektől eltérő hálózati SSID-k hozzáadása engedélyezett.<br /><br />**Alapértelmezett érték:** 1|
|**System/AllowLocation**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**System/AllowTelemetry**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezett (csak Enterprise rendszerekre vonatkozó beállítás)<br /><br />**1** – Korlátozott<br /><br />**2** – Teljes<br /><br />**3** – Teljes és diagnosztikai információk<br /><br />**Alapértelmezett érték:** 2|
|**System/AllowExperimentation**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezett<br /><br />**1** – Csak beállítások<br /><br />**2** – Beállítások és kísérletezés<br /><br />**Alapértelmezett érték:** 1|
|**Security/AntiTheftMode**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Lopásgátló üzemmód tiltása<br /><br />**1** – Felhasználói beállítás szerint<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowUSBConnection**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**System/AllowUserToResetPhone**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowCellularDataRoaming**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowVPNOverCellular**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – VPN tiltása mobileszközökön<br /><br />**1** – A VPN bármilyen kapcsolatot használhat, beleértve a mobilkapcsolatot is.<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Connectivity/AllowBluetooth**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezi a felhasználónak a Bluetooth aktiválását.<br /><br />**1** – Fenntartva. A Bluetooth bekapcsolásának és konfigurálásának engedélyezése a felhasználónak (nem támogatott Windows Phone 8.1 MDM, EAS, a Windows 10 asztali verziója és Windows 10 Mobile esetén).<br /><br />**2** – Engedélyezett. A Bluetooth bekapcsolásának és konfigurálásának engedélyezése a felhasználónak.<br /><br />**Alapértelmezett érték:** 2|
|**Experience/AllowScreenCapture**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowTaskSwitcher**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowVoiceRecording**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowSyncMySettings**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Roaming tiltása<br /><br />**1** – Roaming engedélyezése<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowManualMDMUnenrollment**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Security/AllowManualRootCertificateInstallation**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Security/AllowAddProvisioningPackages**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Search/DisableBackoff**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**Search/PreventRemoteQueries**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 1|
|**Search/AllowUsingDiacritics**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**Search/AlwaysUseAutoLangDetection**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**Search/DisableRemovableDriveIndexing**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**Security/AllowRemoveProvisioningPackage**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Security/RequireProvisioningPackageSignature**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**<br /><br />**1**<br /><br />**Alapértelmezett érték:** 0|
|**AboveLock/AllowActionCenterNotifications**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowIMENetworkAccess**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Nem engedélyezett<br /><br />A nyílt kiterjesztett szótár ki van kapcsolva.<br /><br />A felhasználók nem tehetik a következőket:<br /><br />Új nyílt kiterjesztett szótár felvétele<br /><br />Új keresésintegrációs konfigurációs fájl felvétele<br /><br />A felhőben való használatra jelölt szolgáltatás használata<br /><br />Felhasználó által regisztrált szó küldése<br /><br />Egyéb rendelkezések:<br /><br />A házirend-beállítás engedélyezése előtt felvett nyílt kiterjesztett szótárak nem lesznek felhasználva az átalakításhoz.<br /><br />A házirend jóváhagyása előtt telepített keresésintegrációs konfigurációs fájl nincs használatban.<br /><br />**1** – Engedélyezés<br /><br />A nyílt kiterjesztett könyvtár alapértelmezés szerint felvehető és használható. A keresésintegráció funkció is alapértelmezés szerint használható.<br /><br />A felhasználó a következőket teheti:<br /><br />A felhőben való használatra jelölt szolgáltatás használata<br /><br />Felhasználó által regisztrált szó küldése<br /><br />**Alapértelmezett érték:**|
|**TextInput/AllowKoreanExtendedHanja**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowIMELogging**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – A helytelen átalakítások naplózása ki van kapcsolva. Az automatikusan beállított és a bemeneti előzményadatok nincsenek fájlba mentve.<br /><br />**1** – A helytelen átalakítások naplózása be van kapcsolva. Az automatikusan beállított és a bemeneti előzményadatok fájlba vannak mentve.<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – A JIS-karakterek kivételével minden karakter szűrve<br /><br />**1** – Egyetlen karakter sincs szűrve<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – A JIS0208-karakterek kivételével minden karakter szűrve<br /><br />**1** – Egyetlen karakter sincs szűrve.<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – A JIS0208- és az EUDC-karakterek kivételével minden karakter szűrve<br /><br />**1** – Egyetlen karakter sincs szűrve.<br /><br />**Alapértelmezett érték:** 1|
|**TextInput/AllowInputPanel**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Bluetooth/AllowDiscoverableMode**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Bluetooth/AllowAdvertising**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowDataSense**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowVPN**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowWorkplace**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowDateTime**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowLanguage**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowRegion**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowSignInOptions**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowYourAccount**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowPowerSleep**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Settings/AllowAutoPlay**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowCortana**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Search/SafeSearchPermissions**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Felnőtt tartalom szigorú, legmagasabb fokú szűrése<br /><br />**1** – Felnőtt tartalom mérsékelt, közepes szintű szűrése (az érvényes keresési eredmények nem lesznek szűrve)<br /><br />**Alapértelmezett érték:** 1|
|**Experience/AllowCopyPaste**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**Kezdőméret kényszerítése**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – méretmódosítás engedélyezése a felhasználó számára<br /><br />**1** – nem teljes képernyő kényszerítése<br /><br />**2** – teljes képernyő kényszerítése<br /><br />**Alapértelmezett érték:** 0|
|**Update/RequireDeferUpgrade**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**: A frissítés késleltetésének mellőzése (maradás az aktuális fejlesztési ágban (CB))<br /><br />**1**: A frissítések késleltetésének engedélyezése (az eszköz az aktuális üzleti ág (CBB) szabályait követi)<br /><br />**Alapértelmezett érték: 0**<br /><br />További információkért lásd:<br /><br />[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Mindkettő|**Leírás:** A szoftverfrissítéseket 4 héttel késleltető házirend.<br /><br />**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:** 0: Frissítések azonnali alkalmazása; 1-4: a hetek száma, amíg a rendszer elhalasztja a szoftverfrissítéseket.<br /><br />**Alapértelmezett érték: 0**<br /><br /><br />További információkért lásd:<br /><br />[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Mindkettő|**Leírás:** A funkciófrissítéseket 8 hónappal késleltető házirend.<br /><br />**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:** 0: Frissítések azonnali alkalmazása; 1-8: a hónapok száma, amíg a rendszer elhalasztja a funkciófrissítéseket.<br /><br />**Alapértelmezett érték: 0**<br /><br />További információkért lásd:<br /><br />[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Mindkettő|**Leírás:** Lehetővé teszi a CBB-gépeknek a frissítések letöltésének leállítását 5 hétre. Ezt akkor kell használni, ha probléma van a frissítéssel.<br /><br />**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0**: A frissítések azonnali alkalmazása (alapértelmezett)<br /><br />**1**: A frissítések és verziófrissítések szüneteltetése (5 hét után lejár)<br /><br />**Alapértelmezett érték: 0**|

### Windows Defender

|Házirend neve|Támogatás|Részletek|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowBehaviorMonitoring**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowIntrusionPreventionSystem**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowIOAVProtection**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowScriptScanning**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowOnAccessProtection**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**RealTimeScanDirection**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Minden fájl figyelése (kétirányú)<br /><br />**1** – Bejövő fájlok figyelése<br /><br />**2** – Kimenő fájlok figyelése<br /><br />**Alapértelmezett érték:** 0|
|**DaysToRetainCleanedMalware**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** - **90** – Megadja, hogy a kártevő szoftverek mennyi ideig lesznek megőrizve<br /><br />**Alapértelmezett érték:** 0 – Végleg a karantén mappában tartja, automatikusan nem távolítja el|
|**AllowUserUIAccess**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**ScanParameter**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**1** – Gyorsvizsgálat<br /><br />**2** – Teljes vizsgálat<br /><br />**Alapértelmezett érték:** 1|
|**ScheduleScanDay**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – minden nap<br /><br />**1** – hétfő<br /><br />**2** – kedd<br /><br />**3** – szerda<br /><br />**4** – csütörtök<br /><br />**5** – péntek<br /><br />**6** – szombat<br /><br />**7** – vasárnap<br /><br />**8** – Nincs ütemezett vizsgálat<br /><br />**Alapértelmezett érték:** 0|
|**ScheduleScanTime**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – 00:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1381** – Karbantartási időszak<br /><br />**Alapértelmezett érték:** 120|
|**ScheduleQuickScanTime**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – 00:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1380** – 23:00<br /><br />**Alapértelmezett érték:** 120|
|**AVGCPULoadFactor**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** - **100**<br /><br />**Alapértelmezett érték:** 50|
|**AllowArchiveScanning**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowEmailScanning**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 0|
|**AllowFullScanRemovableDriveScanning**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**AllowScanningNetworkFiles**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1 – Ha engedélyezettre van állítva, akkor is fut, amikor az RTP be van kapcsolva|
|**SignatureUpdateInterval**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Aláírások időközönkénti ellenőrzése kikapcsolva<br /><br />**1** – Aláírások ellenőrzése óránként<br /><br />**2** – Aláírások ellenőrzése 2 óránként stb.<br /><br />**24** – Aláírások ellenőrzése naponta<br /><br />**Alapértelmezett érték:** 8 – Aláírások ellenőrzése 8 óránként|
|**AllowCloudProtection**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – nem engedélyezett<br /><br />**1** – engedélyezett<br /><br />**Alapértelmezett érték:** 1|
|**SubmitSamplesConsent**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek:**<br /><br />**0** – Mindig kérdezzen rá<br /><br />**1** – Biztonságos minták automatikus küldése<br /><br />**2** – Soha ne küldjön<br /><br />**3** – Az összes minta automatikus küldése<br /><br />**Alapértelmezett érték:** 0|
|**ExcludedExtensions**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Adattípus:** Karakterlánc<br /><br />**Megengedett értékek:**<br /><br />*&lt;a kiterjesztések listája, pontosvesszővel elválasztva&gt;* Például: **obj;lib**<br /><br />**Alapértelmezett érték:** Nincs kizárt kiterjesztés|
|**ExcludedPaths**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Adattípus:** Karakterlánc<br /><br />**Megengedett értékek:**<br /><br />*&lt;az elérési utak listája pontosvesszővel elválasztva&gt;*<br /><br />Például: **c:\test;c:\test1.exe**<br /><br />**Alapértelmezett érték:** Nincsenek elérési utak kizárva|
|**ExcludedProcesses**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Adattípus:** Karakterlánc<br /><br />**Megengedett értékek:**<br /><br />*&lt;az elérési utak listája pontosvesszővel elválasztva&gt;*<br /><br />Például: **c:\test.exe;c:\test1.exe**<br /><br />**Alapértelmezett érték:** Nincs kizárt eljárás|

### Edge böngésző

|Házirend neve|Támogatás|Részletek|
|---------------|------------|-----------|
|**Böngésző engedélyezése**|Mobil|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0**: böngészés kikapcsolva; **1**: böngészés bekapcsolva.<br /><br />**Alapértelmezett érték:** 1|
|**AllowSearchSuggestionsinAddressBar**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0**: ne jelenítsen meg keresési javaslatokat; **1**: keresési javaslatok megjelenítése.<br /><br />**Alapértelmezett érték:** 1|
|**SendIntranetTraffictoInternetExplorer**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – Letiltva (internetes webhelyek megnyitása az Edge böngészőben); **1** – Engedélyezve (intranetes webhelyek megnyitása az Internet Explorerben).<br /><br />**Alapértelmezett érték:** 0|
|**Követés letiltásának engedélyezése**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – Letiltva (nem küld követést tiltó fejlécet); **1** – Engedélyezve (követést tiltó fejléc küldése)<br /><br />**Alapértelmezett érték:** 0|
|**SmartScreen konfigurálása**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – nem engedélyezett; **1** – engedélyezve<br /><br />**Alapértelmezett érték:** 1|
|**Előugró ablakok engedélyezése**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – előugró ablakok tiltása; **1** – előugró ablakok engedélyezése<br /><br />**Alapértelmezett érték:** 0|
|**Cookie-k engedélyezése**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – Ne tiltsa le. Cookie-k engedélyezése minden webhelyről; **1** – Csak a külső cookie-k blokkolása; **2** – Az összes cookie blokkolása.<br /><br />**Alapértelmezett érték:** 0|
|**Jelszó mentésének engedélyezése**|Mindkettő|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Adattípus:** Egész szám<br /><br />**Engedélyezett értékek: 0** – Jelszókezelő letiltva; <br />                        **1** – Jelszókezelő engedélyezve<br /><br />**Alapértelmezett érték:** 1|
|**Automatikus kitöltés engedélyezése**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Adattípus:** Egész szám<br /><br />**Megengedett értékek: 0** – Letiltva; **1** – Engedélyezve<br /><br />**Alapértelmezett érték:** 0|
|**Vállalati webhelylista konfigurálása**|Asztali|**URI teljes elérési útja:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Adattípus:** Karakterlánc<br /><br />**Megengedett értékek: 0** – Nincs beállítva; **1** – IE vállalati üzemmód webhelylistájának használata, ha be van állítva; **2** – Webhelylista helyének meghatározása<br /><br />**Alapértelmezett érték:** 1|

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->



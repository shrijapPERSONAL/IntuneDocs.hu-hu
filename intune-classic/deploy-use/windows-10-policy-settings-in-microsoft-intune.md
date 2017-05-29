---
title: "Windows 10-es szabályzatbeállítások | Microsoft Docs"
description: "Az ebben a témakörben ismertetett szabályzatbeállítások segítségével konfigurálhatja a regisztrált asztali Windows 10- és Windows 10 Mobile-eszközök beépített és egyéni beállításait."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dd81102eb768ab8ad5f9ee1d2f122f15a8e17b89
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-házirendbeállítások

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör ismerteti azokat az Intune-szabályzatbeállításokat, amelyeket Windows 10-eszközök felügyeletére használhat. A témakörben olvasható információkat [Az eszközök beállításainak és funkcióinak felügyelete a Microsoft Intune-szabályzatok használatával](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune) című cikk útmutatásaival egészítheti ki.

Két szabályzattípus közül választhat:

- **Egyéni szabályzat**: A Microsoft Intune a Windows 10 és a Windows 10 Mobile rendszerhez készült **egyéni szabályzatával** OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállítások telepíthetők, amelyek segítségével szabályozhatók az eszközök funkciói. A Windows 10-ben számos CSP-beállítás érhető el, mint például a [Szabályzatkonfiguráció-szolgáltató (Policy Configuration Service Provider, Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Általános konfigurációs szabályzat**: Ezt a szabályzattípust használja, ha a Microsoft Intune-hoz biztosított beépített listából szeretne beállításokat választani.

## <a name="custom-policy-settings"></a>Egyéni szabályzatbeállítások

Egyéni szabályzatokban a következő beállításokat adja meg.

### <a name="general-settings"></a>Általános beállítások

Adja meg a szabályzat nevét és – szükség esetén – a leírását, hogy könnyebben megtalálja az Intune-konzolon.

### <a name="oma-uri-settings"></a>OMA-URI-beállítások

Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat. A rendelkezésre álló beállítások áttekintését a jelen témakör [Windows 10 URI-beállítások](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) című részében találja:

- **Beállítás neve**: Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
- **Beállítás leírása**: Itt adhatja meg a beállítás leírását (nem kötelező).
- **Adattípus**: A következő adattípusok közül választhat:
    - **Karakterlánc**
    - **Karakterlánc (XML)**
    - **Dátum és időpont**
    - **Egész**
    - **Lebegőpontos szám**
    - **Logikai**
- **OMA-URI (megkülönbözteti a kis- és nagybetűket)**: Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
- **Érték**: Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.

### <a name="example"></a>Példa
A következő képernyőképen a **Connectivity/AllowVPNOverCellular** beállítást engedélyezték. Ez lehetővé teszi, hogy a Windows 10-es eszköz VPN-kapcsolatot nyisson meg, ha éppen mobilhálózathoz csatlakozik.

> ![VPN-beállításokat tartalmazó egyéni szabályzat – példa](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A Windows 10 által támogatott konfigurációszolgáltatók (CSP-k) teljes listája a Windows dokumentációs könyvtárának [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (A konfigurációszolgáltatók referenciája) című témakörében található meg.

Nem minden beállítás kompatibilis a Windows 10 összes verziójával. A Windows-témakörben szereplő táblázatból kiolvasható, hogy az egyes konfigurációszolgáltatók mely verziókat támogatják.

Ezen felül az Intune sem támogatja a témakörben felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó témakört. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.

## <a name="general-configuration-policy-settings"></a>Az általános konfigurációs szabályzat beállításai

A Microsoft Intune Windows 10-es eszközökhöz készült **általános konfigurációs szabályzatát** regisztrált asztali Windows 10 és Windows 10 Mobile rendszerű eszközök beépített beállításainak konfigurálásához használhatja.

### <a name="password"></a>Jelszó

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Jelszó kérése az eszközzárolás feloldásához**|-|
|**Kötelező jelszótípus**|Azt határozza meg, hogy a jelszó számokból és betűkből vagy csak számokból állhat|
|**Kötelező jelszótípus** - **Karakterkészletek minimális száma**| Meghatározza, hogy hány karakterkészletnek (kisbetűk, nagybetűk, számok és szimbólumok) kell szerepelnie a jelszóban|
|**Jelszó minimális hossza**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Megengedett sikertelen bejelentkezések száma az eszközön tárolt adatok törléséig**|Windows 10 rendszerű eszközök esetében: ha a BitLocker engedélyezve van az eszközön, akkor az a megadott számú sikertelen bejelentkezési kísérlet után a BitLocker helyreállítási módjába kerül. Ha az eszközön nincs engedélyezve a BitLocker, akkor ez a beállítás nem alkalmazható.<br>Windows 10 Mobile-eszközök esetében: a megadott számú sikertelen bejelentkezési kísérlet után az eszköz tartalma törlődik.|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt|
|**Jelszó lejárata (nap)**|Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót|
|**Jelszóelőzmények megjegyzése**|Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg|
|**Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**|Azt adja meg, hogy köteles-e a felhasználó jelszót megadnia az eszköz feloldásához (csak Windows 10 Mobile esetén)|

### <a name="encryption"></a>Titkosítás

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Mobileszköz titkosításának kötelezővé tétele**|A titkosítás engedélyezése a megcélzott eszközökön<br>(csak a Windows 10 Mobile)|

### <a name="system"></a>Rendszer

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Képernyőfelvétel engedélyezése**|Engedélyezése esetén a felhasználó rögzítheti képként a képernyőn látható tartalmat (Csak Windows 10 Mobile eszközökön).|
|**Regisztráció manuális törlésének engedélyezése**|Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.|
|**Főtanúsítvány manuális telepítésének engedélyezése**|A Windows 10 Mobile verzióra vonatkozik|
|**Diagnosztikai és használati adatok küldésének engedélyezése a Microsoft felé**|Lehetséges értékek:<br><br>**Nem** – Az eszköz nem küld adatokat a Microsoftnak.<br>**Alapszintű** – Az eszköz korlátozott információkat küld a Microsoftnak<br>**Bővített** – Az eszköz bővebb diagnosztikai adatokat küld a Microsoftnak<br>**Teljes (ajánlott)** – A **Bővített** beállítással küldött adatok mellett az eszköz állapotával kapcsolatos információkat is küld.|


### <a name="account-and-synchronization"></a>Fiók és szinkronizálás

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Microsoft-fiók használatának engedélyezése**|Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.|
|**Nem Microsoft-fiókok manuális felvételének engedélyezése**|Lehetővé teszi, hogy a felhasználó olyan e-mail fiókokat vegyen fel az eszközön, amelyek nincsenek Microsoft-fiókhoz társítva.|
|**Microsoft-fiókok beállításszinkronizálásának engedélyezése**|Lehetővé teszi a Microsoft-fiókhoz kapcsolódó eszköz- és alkalmazásbeállítások szinkronizálását az eszközök között.|

### <a name="microsoft-edge"></a>Microsoft Edge

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Webböngésző engedélyezése**|Engedélyezi az Edge webböngésző használatát az eszközön<br>(csak a Windows 10 Mobile)|
|**Keresési javaslatok engedélyezése a címsorban**|Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben|
|**Intranetes adatforgalom küldésének engedélyezése az Internet Explorerbe**|Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben<br>(csak a Windows 10 asztali verzió)|
|**Követés letiltásának engedélyezése**|Lehetővé teszi az Edge böngésző számára a Do Not Track (Követés letiltása) fejlécek küldését a felhasználók által meglátogatott webhelyeknek|
|**SmartScreen engedélyezése**||
|**Active Scripting engedélyezése**|A parancsprogramok, például a JavaScriptek futtatásának engedélyezés az Edge böngészőben|
|**Előugró ablakok engedélyezése**|Csak a Windows 10 asztali verzióra vonatkozik|
|**Cookie-k engedélyezése**||
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását<br>(csak a Windows 10 asztali verzió)|
|**Jelszókezelő engedélyezése**|Engedélyezi vagy letiltja az Edge böngésző Jelszókezelő szolgáltatását|
|**Vállalati üzemmód webhelylistájának helye**|Megadja, hogy hol található a Vállalati üzemmódban megnyíló webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.<br>(csak a Windows 10 asztali verzió)|

### <a name="apps"></a>Alkalmazások

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Alkalmazás-áruház engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|



### <a name="cellular"></a>Mobil

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Adatroaming engedélyezése**|Hálózatok közötti barangolás engedélyezése adatok elérése közben|
|**VPN engedélyezése mobilhálózaton**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.|
|**VPN engedélyezése mobilhálózati roaming esetén**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming esetén.|

### <a name="hardware"></a>Hardver

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Kamera engedélyezése**|-|
|**Cserélhető tároló engedélyezése**|Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.|
|**Wi-Fi engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Internetmegosztás engedélyezése**|Az internetkapcsolat megosztásának engedélyezése az eszközön|
|**Manuális Wi-Fi konfiguráció engedélyezése**|Azt szabályozza, hogy a felhasználó konfigurálhat-e saját Wi-Fi-kapcsolatokat, vagy csak a Wi-Fi-profillal konfigurált kapcsolatokat használhatja.<br>(csak a Windows 10 Mobile)|
|**Ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás engedélyezése**|Az ingyenes Wi-Fi-elérési pontokhoz történő automatikus csatlakozás és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadásának engedélyezése az eszközön.|
|**Földrajzi hely meghatározásának engedélyezése**|Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.|
|**NFC használatának engedélyezése**|Engedélyezi az eszköz kis hatótávolságú kommunikációs (NFC) funkciójának használatát.|
|**Bluetooth engedélyezése**|-|
|**Bluetooth-észlelhetőség engedélyezése**|Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.|
|**Bluetooth-hirdetés engedélyezése**|Engedélyezi, hogy az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.|
|**Telefon alaphelyzetbe állításának engedélyezése**|Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait|
|**USB-kapcsolat engedélyezése**|Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.|
|**Lopásgátló üzemmód engedélyezése**|Annak beállítása, hogy engedélyezve van-e a Windows lopásgátló üzemmódja|

### <a name="features"></a>Jellemzők

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Másolás és beillesztés engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Hangrögzítés engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Cortana engedélyezése**|A Cortana beszédfelismerési asszisztens engedélyezése vagy letiltása|
|**Műveletközponti értesítések engedélyezése**|Műveletközponti értesítések engedélyezése vagy letiltása az eszköz zárolási képernyőjén<br>(csak a Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Ezek a beállítások csak a Windows 10 asztali verziójában érvényesek.

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Valós idejű figyelés engedélyezése**|Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű vizsgálatát|
|**Viselkedésfigyelés engedélyezése**|Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön|
|**Hálózatvizsgáló rendszer engedélyezése**|A hálózatvizsgáló rendszer (NIS) a Microsoft Endpoint Protection-központtól származó ismert biztonsági rések aláírásai alapján észleli és blokkolja a kártékony hálózati forgalmat, ezáltal segíti az eszközök védelmét a hálózati támadásokkal szemben|
|**Minden letöltés ellenőrzése**|Meghatározza, hogy a Defender az internetről letöltött összes fájlt megvizsgálja-e|
|**Szkriptek ellenőrzésének engedélyezése**|Engedélyezi a Defender számára az Internet Explorer által használt parancsfájlok vizsgálatát|
|**A fájl- és programtevékenység figyelése**|Engedélyezi a Defender számára az eszközökön zajló a fájl- és programtevékenységet|
|**Ártalmatlanított kártevő szoftverek követése**|A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok számát **0**-ra állítja, a kártevő a karanténban marad, és a rendszer nem távolítja el automatikusan. |
|**Ügyfél-kezelőfelület elérésének engedélyezése**|Azt szabályozza, hogy a Windows Defender kezelőfelülete rejtett legyen-e a felhasználók számára.<br>Módosítás esetén a beállítás a felhasználó számítógépének következő újraindításakor lép érvénybe.|
|**Napi gyorsvizsgálat ütemezése**|Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé|
|**Rendszervizsgálat ütemezése**|A választott napokon és időpontban rendszeresen végzett teljes vagy gyors rendszervizsgálat beütemezését teszi lehetővé|
|**Processzorhasználat korlátozása az ellenőrzések során**|Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**%-tól **100**%-ig).|
|**Archív fájlok ellenőrzése**|Engedélyezi a Defender számára az archív fájlok – például .zip- vagy .cab-fájlok – vizsgálatát.|
|**E-mailek ellenőrzése**|Engedélyezi a Defender számára az eszközre érkező e-mailek azonnal vizsgálatát|
|**Cserélhető adathordozók ellenőrzése**|Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát|
|**Csatlakoztatott hálózati meghajtók ellenőrzése**|Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon tárolt fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|
|**A megosztott hálózati mappákból megnyitott fájlok ellenőrzése**|Engedélyezi a Defender számára a megosztott hálózati meghajtókon található (például az UNC elérési útvonalon megnyitott) fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|
|**Aláírás-frissítési időköz**|Meghatározza, hogy a Defender milyen időközönként keressen új aláírásfájlokat.|
|**Felhővédelem engedélyezése**|Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.|
|**Minták küldésének kérése a felhasználóktól**|Azt szabályozza, hogy a rendszer automatikusan elküldje a Microsoftnak azokat a fájlokat, amelyeken további vizsgálat szükséges annak megállapításához, hogy kártékonyak-e|
|**Vélhetően nemkívánatos alkalmazások észlelése**|Védi a regisztrált Windows rendszerű asztali eszközöket a Windows Defender által a vélhetően nemkívánatosak közé sorolt szoftverek futtatása ellen. Biztosíthatja a védelmet ezen alkalmazások futtatása ellen, vagy a vizsgálati üzemmóddal jelentést készíthet a vélhetően nemkívánatos alkalmazások telepítéséről.|
|**A valós idejű védelem által és a teljes ellenőrzések végrehajtásakor figyelmen kívül hagyott fájlok és mappák**|A kívánt fájlok és mappák – például **C:\Elérési_út** vagy **%ProgramFiles%\Elérési_út\fájlnév.exe** – felvétele a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.|
|**A valós idejű védelem által és a teljes ellenőrzések végrehajtásakor figyelmen kívül hagyott fájltípusok**|Vegye fel a kívánt fájlkiterjesztéseket – például **jpg** vagy **txt** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja az ilyen kiterjesztésű fájlokat.|
|**A valós idejű védelem által és a teljes ellenőrzések végrehajtásakor figyelmen kívül hagyott folyamatok**|A kívánt típusú folyamatok – **.exe**, **.com** vagy **.scr** – felvétele a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.|


### <a name="updates"></a>Frissítések

|Beállítás neve|További információ (ha szükséges)|
|----------------|---------------|
|**Automatikus frissítések engedélyezése**|Az automatikus frissítések engedélyezése. A következő lehetőségek egyikének beállításával szabályozhatja a frissítések működését:<br />**Értesítést kérek a letöltésről**<br />**Automatikus telepítés karbantartási időpontban**<br />**Automatikus telepítés és újraindítás karbantartási időpontban**<br />**Automatikus telepítés és újraindítás ütemezett időpontban**: Felhívjuk figyelmét, hogy kiválasztása esetén a következő beállítások konfigurálása is lehetővé válik: **Végfelhasználói értesítések letiltása**, illetve **Adja meg az ütemezett frissítések telepítésének napját**.<br>(csak a Windows 10 asztali verzió)|
|**Előzetes funkciók engedélyezése**|Lehetővé teszi a Microsoft számára, hogy előzetes verziójú beállításokat és funkciókat telepítsen a Windows 10 rendszerű eszközökre. Meghatározhatja, hogy csak a beállítások telepítését engedélyezi, vagy minden előzetes verziójú beállítás és funkció telepítését is.|

### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


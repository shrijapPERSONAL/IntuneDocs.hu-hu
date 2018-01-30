---
title: "Intune Endpoint Protection-beállítások Windows 10 rendszerhez"
titlesuffix: Azure portal
description: "Ez a cikk azt mutatja be, hogy Windows 10 rendszerű eszközökön milyen Intune-beállításokkal szabályozhatja az olyan Endpoint Protection szolgáltatások beállításait, mint például a BitLocker."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f33598abe08ffb958ddac9eb7725ab500f9db981
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune Endpoint Protection-beállítások Windows 10 és újabb rendszerekhez

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Endpoint Protection-profillal a Windows 10-es eszközök olyan biztonsági szolgáltatásait szabályozhatja, mint például a BitLocker és a Windows Defender.

A következő témakör az Endpoint Protection-profilok létrehozását mutatja be.

> [!Note]
> Ezek a beállítások nem támogatottak a Windows 10 Home és Professional kiadásaiban.

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection-profil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az eszközfunkció-profil **Nevét** és **Leírását**.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listából válassza az **Endpoint Protection** lehetőséget.
7. Adja meg a kívánt beállításokat. A következő témakörben leírtak alapján megértheti, milyen funkciót látnak el az egyes beállítások. Ha elkészült, válassza az **OK** elemet.
8. Lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** lehetőséget.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="windows-defender-application-guard"></a>Windows Defender alkalmazásőr

Az Alkalmazásőr csak a 64 bites Windows 10-eszközöknél érhető el. Ennek a profilnak a használatával telepítve lesz az Alkalmazásőr aktiválásához szükséges Win32-összetevő.

- **Alkalmazásőr** – A nem jóváhagyott helyeket Hyper-V-vel virtualizált, tárolóalapú böngészővel nyithatja meg.
- **A vágólap működése** – Meghatározhatja, hogy milyen másolási és beillesztési műveletek legyenek engedélyezve a helyi PC és az alkalmazásőrrel védett virtuális böngésző között.
- **Vállalati webhelyeken lévő külső tartalom** – A nem jóváhagyott webhelyekről származó tartalom betöltésének tiltása.
- **Nyomtatás a virtuális böngészőből** – Engedélyezheti, hogy a virtuális böngészőben megjelenő tartalom a PDF-, az XPS-, a helyi és/vagy a hálózati nyomtatókkal nyomtathatók legyenek.
- **Naplók gyűjtése** – Az alkalmazásőr virtuális böngészési munkamenetében előforduló események naplóinak összegyűjtése.
- **Felhasználó által létrehozott böngészési adatok megtartása** – Engedélyezheti az alkalmazásőr által védett böngészési munkamenet során létrehozott felhasználói adatok (például jelszavak, kedvencek vagy cookie-ek) mentését.


## <a name="windows-defender-firewall"></a>Windows Defender-tűzfal

### <a name="global-settings"></a>Globális beállítások

Ezek a beállítások minden hálózattípusnál alkalmazhatók.

- **File Transfer Protocol** – Letilthatja az állapot-nyilvántartó FTP-t.
- **Biztonsági társítás üresjárati ideje törlés előtt** – Ha *n* másodpercig nincs hálózati forgalom, a biztonsági társítások törölve lesznek.
- **Előmegosztott kulcsok kódolása** – Az előmegosztott kulcsok kódolása UTF-8 használatával.
- **IPsec-kivételek** – Beállítható, hogy bizonyos forgalomra ne vonatkozzon az IPsec. Ilyen lehet például a **Szomszédfelderítési IPv6 ICMP-típuskódok**, az **ICMP**, az **Útválasztó-felderítési IPv6 ICMP-típuskódok**, valamint **Mind az IPv4-es, mind az IPv6-os DHCP hálózati forgalom**.
- **Visszavont tanúsítványok listájának ellenőrzése** – Beállítható egy érték, amely kötelezően alkalmazva lesz a visszavont tanúsítványok ellenőrzésekor, például **CRL-ellenőrzés letiltása**, **Sikertelen CRL-ellenőrzés csak visszavont tanúsítványok esetén**, valamint **Sikertelen CRL-ellenőrzés bármilyen hibánál**.
- **Hitelesítési készlet alkalomszerű egyeztetése kulcsmodulonként** – Beállítható, hogy a kulcskezelő modulok hagyják figyelmen kívül a teljes hitelesítési készletet, ha az adott készlet nem minden hitelesítési csomagját támogatják.
- **Csomagok várólistára helyezése** – Annak megadása, hogy a fogadó oldali szoftver skálázása IPsec-alagutas átjáró használata esetén miként legyen engedélyezve a titkosított fogadás és az egyszerű szöveges továbbítás számára. Ezzel biztosítható a csomagsorrend megőrzése. Ezzel biztosítható a csomagsorrend megőrzése.

### <a name="network-settings"></a>Hálózati beállítások

Ezek a beállítások meghatározott hálózattípusokra vonatkoznak. Ilyen többek között a **Tartományi (munkahelyi) hálózat**, a **Magánhálózat (észlelhető)** és a **	Nyilvános (nem észlelhető) hálózat**.

#### <a name="general-settings"></a>Általános beállítások

- **Windows Defender-tűzfal** – Ezzel a beállítással letiltható a hálózati forgalom.
- **Rejtett üzemmód** – Letiltható, hogy a tűzfal rejtett üzemmódban működjön. Ennek a tiltásnak a beállítása az **IPsec-et használó csomagok mentességének** letiltását is lehetővé teszi.
- **Védett** – Ha ezt és a tűzfalbeállítást is letiltja, akkor a teljes bejövő forgalom le lesz tiltva.
- **Egyedi küldésű válaszok a csoportos küldésű szórásokra** – Egyedi küldésű válaszok tiltása a csoportos küldésű válaszokra. Csoportos küldésű vagy szórási üzenetekre általában nem kívánatos egyedi küldésű válaszokat kapni, mivel az ilyen típusú válaszok szolgáltatásmegtagadási támadást jeleznek, vagy azt jelzik, hogy egy támadó egy ismert aktív számítógépbe próbál bejutni.
- **Bejövő értesítések** – Letiltható az üzenetek felhasználóknak való megjelenítése, ha le van tiltva, hogy az alkalmazás figyeljen egy portot.
- **Alapértelmezett művelet bejövő kapcsolatokhoz** – Letiltható az az alapbeállítás szerinti művelet, amelyet a tűzfal a bejövő kapcsolatoknál alkalmaz.

#### <a name="rule-merging"></a>Szabályegyesítés

- **Engedélyezett alkalmazás Windows Defender-tűzfalszabályai a helyi tárolóban** – A helyi tároló elfogadandó és érvényesítendő tűzfalszabályainak alkalmazása.
- **Portokkal kapcsolatos globális Windows Defender-tüzfalszabályok a helyi tárolóban** – A helyi tároló elfogadandó és érvényesítendő, portokkal kapcsolatos globális tűzfalszabályainak alkalmazása.
- **Windows Defender-tűzfalszabályok a helyi tárolóban** – A helyi tároló elfogadtatni és érvényesíteni kívánt globális tűzfalszabályainak alkalmazása.
- **Helyi tároló IPSec-szabályai** – A helyi tároló kapcsolatbiztonsági szabályainak alkalmazása, függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától.

## <a name="windows-defender-smartscreen-settings"></a>A Windows Defender SmartScreen beállításai

- **SmartScreen használata alkalmazások és fájlok esetén** –  A Windows SmartScreen használata fájlok és alkalmazások futtatásához.
- **Nem ellenőrzött fájlok futtatása** – Letilthatja a végfelhasználóknál a Windows SmartScreen által nem ellenőrzött fájlok futtatását.

## <a name="windows-encryption"></a>Windows-titkosítás

### <a name="windows-settings"></a>Windows-beállítások

Ezek a beállítások a Windows 10 minden verziójára érvényesek.

- **Eszközök titkosítása** – Ha bekapcsolja ezt a beállítást, a rendszer kérni fogja a felhasználótól, hogy engedélyezze az eszköz titkosítását. Ezen túlmenően rá fog kérdezni, hogy nincs-e engedélyezve másik szolgáltató titkosítási funkciója. Az eszköz ugyanis instabillá válhat, ha a windowsos titkosítást úgy kapcsolják be, hogy közben egy másik titkosítási módszer aktív marad.
- **Tárolókártya titkosítása** – Ha engedélyezi ezt a beállítást, az eszközhöz használt minden cserélhető tárolókártyát titkosítani fog a rendszer.


### <a name="bitlocker-base-settings"></a>BitLocker-alapbeállítások

Az alapbeállítások minden típusú adatmeghajtóra vonatkozó univerzális BitLocker-beállítások. A BitLocker Csoportházirend-beállításai szabályozzák a végfelhasználók által a különböző típusú adatmeghajtókon módosítható meghajtótitkosítási feladatokat vagy konfigurációs beállításokat.

- **Figyelmeztetés egyéb lemeztitkosításra** – Az egyéb lemeztitkosítással kapcsolatos figyelmeztető üzenet letiltása a végfelhasználók gépein.
- **Titkosítási módszerek konfigurálása** – Ha engedélyezi ezt a beállítást, különböző titkosítási algoritmusokat állíthat be az operációs rendszerhez, a rendszeren található adatokhoz és a cserélhető meghajtókhoz.
    - **Operációsrendszer-meghajtók titkosítása** – Az operációs rendszer meghajtóihoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
    - **Rögzített adatmeghajtók titkosítása** – A rögzített (beépített) adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
    - **Cserélhető adatmeghajtók titkosítása** – A cserélhető adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Ha a cserélhető meghajtót olyan eszközökkel is használja, amelyeken nem Windows 10 operációs rendszer fut, az AES-CBC algoritmus használatát javasoljuk.

### <a name="bitlocker-os-drive-settings"></a>Operációsrendszer-meghajtók BitLocker-beállításai

Ezek a beállítások kifejezetten az operációsrendszer-adatmeghajtókra érvényesek.

- **További hitelesítés indításkor** – A számítógép indítására vonatkozó hitelesítési követelmények konfigurálása, beleértve a platformmegbízhatósági modul (TPM) használatát.
    - **BitLocker nem kompatibilis TPM-lapkával**
    - **Kompatibilis TPM-indítás** – Ezzel a beállítással adható meg, hogy a TPM-lapka (Trusted Platform Module – platformmegbízhatósági modul) használata engedélyezett, nem engedélyezett vagy kötelező legyen-e.
    - **Kompatibilis TPM-indítási PIN-kód** – Ezzel a beállítással adható meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítási PIN-kód használatát.
    - **Kompatibilis TPM-indítási kulcs** – Ezzel a beállítással adható meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítási kulcs használatát.
    - **Kompatibilis TPM-indítási kulcs és PIN-kód** – Ezzel a beállítással adhatja meg, hogy a TPM-lapkához engedélyezi, nem engedélyezi vagy kötelezővé teszi-e egy indítókulcs és PIN-kód használatát.
- **PIN-kód minimális hossza** – Ha engedélyezi ezt a beállítást, megadhatja a TPM-indítási PIN-kód minimális hosszát.
    - **Karakterek minimális száma** – Ezzel a beállítással megadható, hogy hány karaktert kell tartalmaznia az indításkor beírandó PIN-kódnak. A PIN-kód hossza **4**-**20** karakter lehet.
- **Operációsrendszer-meghajtó helyreállítása** – Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett operációsrendszer-meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
    - **Tanúsítványalapú adat-helyreállítási ügynök** – Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett operációsrendszer-meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
    - **Helyreállítási jelszó felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.
    - **Helyreállítási kulcs felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
    - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában** – Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
    - **A BitLocker helyreállítási adatainak mentése az AD DS-be** – Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
    - **AD DS-ben tárolt BitLocker helyreállítási adatok** – Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
        - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
        - **Csak a helyreállítási jelszavak biztonsági mentése**
    - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt** – Ezzel a beállítással szabályozható, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.
- **Rendszerindítás előtti helyreállítási üzenet és URL-cím** – Ezzel a beállítással engedélyezhető, hogy a rendszerindítás előtti kulcshelyreállítási képernyőn a rendszer megjelenítsen egy üzenetet és egy URL-címet.
    - **Rendszerindítás előtti helyreállítási üzenet** – Itt adhatja meg, milyen rendszerindítás előtti helyreállítási üzenet jelenjen meg a felhasználók számára. A következő lehetőségek közül választhat:
        - **Az alapértelmezett helyreállítási üzenet és URL-cím használata**
        - **Üres helyreállítási üzenet és URL-cím használata**
        - **Egyéni helyreállítási üzenet**
        - **Egyéni helyreállítási URL**


### <a name="bitlocker-fixed-data-drive-settings"></a>Rögzített adatmeghajtók BitLocker-beállításai

- **Írási hozzáférés BitLockerrel nem védett rögzített adatmeghajtóhoz** – Ha ezt a beállítást engedélyezi, a rögzített vagy beépített adatmeghajtók csak azután lesznek írhatók, ha BitLocker-védelmüket engedélyezte a felhasználó.
- **Rögzített meghajtó helyreállítása** – Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett rögzített meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
    - **Adat-helyreállítási ügynök** – Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett rögzített meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
    - **Helyreállítási jelszó felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.  
    - **Helyreállítási kulcs felhasználói létrehozása** – Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
    - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában** – Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
    - **A BitLocker helyreállítási adatainak mentése az AD DS-be** – Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
    - **AD DS-ben tárolt BitLocker helyreállítási adatok** – Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
        - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
        - **Csak a helyreállítási jelszavak biztonsági mentése**
    - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt** – Ezzel a beállítással szabályozható, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.

### <a name="bitlocker-removable-data-drive-settings"></a>Cserélhető adatmeghajtók BitLocker-beállításai

- **Írási hozzáférés BitLockerrel nem védett cserélhető adatmeghajtóhoz** – Ezzel a beállítással szabályozható, hogy kötelező-e BitLocker-titkosítással védeni a cserélhető adattárolókat.
  - **Írási hozzáférés a más szervezetben konfigurált eszközökhöz** – Ezt a beállítást használva megadhatja, hogy írhatnak-e a felhasználók más szervezethez tartozó cserélhető adatmeghajtókra.

## <a name="windows-defender-exploit-guard"></a>Windows Defender – biztonsági rés kiaknázása elleni védelem

A [Windows Defender - biztonsági rés kiaknázása elleni védelem](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) használatával az alkalmazottak által használt alkalmazásokat lehet kezelni, és csökkenthető vele az alkalmazások támadási felülete.

### <a name="attack-surface-reduction"></a>Támadási felület csökkentése

[Kiküszöbölhetők azok az események és alkalmazások](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), amelyeket általában a biztonsági réseket kereső kártevő szoftverek használnak a számítógépek megfertőzése céljából.

#### <a name="rules-to-prevent-office-macro-threats"></a>Veszélyes Office-makrók letiltására szolgáló szabályok

Az alábbi műveletek elvégzését letilthatja Office-alkalmazások esetén:

- **Office-alkalmazások más folyamatokba való injektálása (nincs kivétel)**
- **Végrehajtható tartalmat létrehozó Office-alkalmazások és -makrók**
- **Gyermekfolyamatokat elindító Office-alkalmazások**
- **Office-makró-kódból történő Win32-alapú importálás**

#### <a name="rules-to-prevent-script-threats"></a>Veszélyes szkriptek letiltására szolgáló szabályok

Az alábbiak letiltásával a veszélyes szkriptek ellen védekezhet:

- **Js-, VBS-, PS-fájlok és makrók rejtjelezett kódja**
- **Internetről letöltött .js vagy .vbs fájlok végrehajtása (nincs kivétel)**

#### <a name="rules-to-prevent-email-threats"></a>E-mail-fenyegetések megakadályozását szolgáló szabályok

Az alábbiak letiltásával megakadályozhatja az e-mail-fenyegetéseket:

- **Webes levelezés vagy az asztali levelezőprogramok e-mailjeiből eltávolított végrehajtható tartalom (például .exe, .dll, .ps, .js, és .vbs fájlok) futtatása (nincs kivétel)**

#### <a name="attack-surface-reduction-exceptions"></a>Támadási felület csökkentése – kivételek

- **Fájlok és mappák kizárása a támadási felület csökkentésére szolgáló szabályok hatálya alól** – Helyek listájának importálása és hozzáadása a konfigurált szabályok alóli kizárásra.

### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

Rosszindulatú alkalmazások és fenyegetések, például zsarolóprogramok ellen védheti értékes adatait.

- **Mappavédelem** – A fájlok és mappák rosszindulatú alkalmazások által végrehajtott jogosulatlan módosításainak megakadályozása. **Védett mappákhoz hozzáférő alkalmazások listáját** importálhatja, vagy manuálisan is hozzáadhatja. **További védendő mappák listáját** is hozzáadhatja feltöltéssel, vagy manuálisan is hozzáadhatja őket.

### <a name="network-filtering"></a>Hálózatszűrés

Bármely alkalmazásból letilthatja az alacsony megbízhatóságú IP-címekre vagy tartományokba irányuló kimenő kapcsolatokat.

### <a name="exploit-protection"></a>Biztonsági rés kiaknázása elleni védelem

Letilthatja, hogy a **felhasználók a Biztonsági rés kiaknázása elleni védelem felületét módosítsák**, ha feltölt egy olyan XML-fájlt, amely lehetővé teszi a memória, a vezérlésfolyam és az alkalmazás biztonsági rések elleni védelmét biztosító szabályzatkorlátozások konfigurálását.

A biztonsági rés kiaknázása elleni védelem engedélyezéséhez hozzon létre egy XML-fájlt, amely a rendszer és az alkalmazások kockázatcsökkentésének kívánt beállításait tartalmazza. Ezt kétféle módon végezheti el:

 1. PowerShell: Egy vagy több Get-ProcessMitigation, Set-ProcessMitigation és ConvertTo-ProcessMitigationPolicy PowerShell-parancsmag használatával konfigurálja a kockázatcsökkentési beállításokat, majd exportálja ezek XML-reprezentációját.

 2. A Windows Defender Security Center felhasználói felülete: A Windows Defender Security Centerben kattintson az Alkalmazás- és böngészőszabályozásra, majd a megjelenő képernyő alján keresse meg az Biztonsági rés kiaknázása elleni védelem elemet. Először a Rendszerbeállítások és a Programbeállítások lap használatával konfigurálja a kockázatcsökkentési beállításokat. Ha végzett, a képernyő alján keresse meg az Exportálási beállítások hivatkozást, amellyel exportálhatja ezek XML-reprezentációját.

## <a name="windows-defender-application-control"></a>Windows Defender Alkalmazásvezérlés

Az **Alkalmazás-ellenőrző kódintegritási szabályzatok** használatával további alkalmazásokat is kiválaszthat, amelyeket a Windows Defender Alkalmazásvezérlésnek vagy ellenőriznie kell, vagy biztonságosan futtathatónak kell besorolnia. A Windows-összetevők és a Windows Áruházból származó alkalmazások automatikusan biztonságosan futtathatóként lesznek besorolva.

„Naplózási módban” az alkalmazások nem lesznek letiltva. A „naplózási mód” minden eseményt egy ügyfélnaplóban rögzít.

## <a name="windows-defender-security-center"></a>Windows Defender biztonsági központ

A Windows Defender biztonsági központ alkalmazás az egyes funkcióktól elkülönített alkalmazásként működik, és a Műveletközponton keresztül jelenít meg értesítéseket. Olyan gyűjtőhelyként funkcionál, ahol megtekinthetők az állapotok, és ahol minden funkció esetében elvégezhetők bizonyos beállítások. További információt a [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) dokumentációjában talál.

#### <a name="windows-defender-security-center-app-and-notifications"></a>A Windows Defender biztonsági központ alkalmazás és az értesítések

Letilthatja a felhasználói hozzáférést a Windows Defender biztonsági központ alkalmazás különböző területeihez. Egy szakasz elrejtése a kapcsolódó értesítéseket is letiltja.

- **Vírusok és veszélyforrások elleni védelem**
- **Eszközteljesítmény és -állapot**
- **Tűzfal és hálózatvédelem**
- **Alkalmazás- és böngészővezérlés**
- **Családi beállítások**
- **Az alkalmazás megjelenített területeihez kapcsolódó értesítések** – Annak kiválasztása, hogy mely értesítések jelenjenek meg a végfelhasználók számára. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső összefoglalói, például a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül.

#### <a name="it-contact-information"></a>Az informatikai szolgálat kapcsolattartási adatai

Adja meg az informatikai szolgálat azon elérhetőségeit, amelyek megjelennek majd a Windows Defender biztonsági központ alkalmazásban és az alkalmazásértesítésekben. Az alábbi lehetőségek közül választhat: **Az alkalmazásban és az értesítésekben is jelenjen meg**, **Csak az alkalmazásban jelenjen meg**, **Csak az értesítésekben jelenjen meg** és **Ne jelenjen meg**. Meg kell adnia az **IT-szervezet nevét**, és az alábbiak közül legalább egyet:

- **IT-részleg telefonszáma vagy Skype-elérhetősége**
- **IT-részleg e-mail címe**
- **Informatikai támogatási webhely URL-címe**

## <a name="next-steps"></a>További lépések

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

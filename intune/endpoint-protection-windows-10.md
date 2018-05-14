---
title: Endpoint Protection hozzáadása Windows 10 rendszeren az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsot Intune-ban, Windows 10-eszközökön az Endpoint Protection-beállítások használatával vagy konfigurálásával engedélyezheti a Windows Defender funkcióit, így az alkalmazásőrt, a tűzfalat, a SmartScreent, a titkosítást és a BitLockert, a biztonsági rés kiaknázása elleni védelmet, az alkalmazásvezérlést, a biztonsági központot és a helyi eszközök biztonságát.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 22eceb7792aee714fb728d64d8bec2ae8db4167c
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Intune Endpoint Protection-beállítások Windows 10 és újabb rendszerekhez

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Endpoint Protection-profillal a Windows 10-es eszközök olyan biztonsági szolgáltatásait szabályozhatja, mint például a BitLocker és a Windows Defender.

A következő cikk az Endpoint Protection-profilok létrehozását mutatja be.

> [!NOTE]
> Ezek a beállítások nem támogatottak a Windows 10 Home és Professional kiadásaiban.

## <a name="windows-defender-application-guard"></a>Windows Defender alkalmazásőr

A Microsoft Edge használata közben a Windows Defender alkalmazásőr megvédi a környezetét az olyan webhelyektől, amelyek nincsenek megbízhatóként meghatározva a szervezetében. Amikor a felhasználók az elkülönített hálózathatáron kívüli webhelyekre lépnek, a webhelyek egy virtuális böngésző-munkamenetben, a Hyper-V-ben nyílnak meg. A megbízható webhelyeket egy hálózathatár definiálja, amely az Eszközkonfiguráció menüben konfigurálható. 

Az Alkalmazásőr csak a 64 bites Windows 10-eszközöknél érhető el. Ennek a profilnak a használatával telepítve lesz az Alkalmazásőr aktiválásához szükséges Win32-összetevő.

- **Alkalmazásőr**: A nem jóváhagyott helyeket Hyper-V-vel virtualizált, tárolóalapú böngészővel nyithatja meg.
- **A vágólap működése**: Meghatározhatja, hogy milyen másolási és beillesztési műveletek legyenek engedélyezve a helyi PC és az alkalmazásőrrel védett virtuális böngésző között.
- **Vállalati webhelyeken lévő külső tartalom**: A nem jóváhagyott webhelyekről származó tartalom betöltésének tiltása.
- **Nyomtatás a virtuális böngészőből**: Engedélyezheti, hogy a virtuális böngészőben megjelenő tartalom a PDF-, az XPS-, a helyi és/vagy a hálózati nyomtatókkal nyomtathatók legyenek.
- **Naplók gyűjtése**: Az alkalmazásőr virtuális böngészési munkamenetében előforduló események naplóinak összegyűjtése.
- **Felhasználó által létrehozott böngészési adatok megtartása**: Az alkalmazásőr által védett böngészési munkamenet során létrehozott felhasználói adatok (például jelszavak, kedvencek vagy cookie-ek) mentése.
- **Grafikus gyorsítás**: Az alkalmazásőr virtuális böngészési munkameneteiben gyorsabban betöltheti a magas grafikai igényű webhelyeket. A webhelyek gyorsabban betöltenek, ha engedélyezi a virtuális grafikai feldolgozóegységhez való hozzáférést.
- **Fájlok letöltése a gazdagép fájlrendszerébe**: Engedélyezheti a felhasználóknak, hogy letöltsenek fájlokat a virtualizált böngészőből a gazdagép operációs rendszerébe.

## <a name="windows-defender-firewall"></a>Windows Defender-tűzfal

### <a name="global-settings"></a>Globális beállítások

Ezek a beállítások minden hálózattípusnál alkalmazhatók.

- **File Transfer Protocol**: Letilthatja az állapot-nyilvántartó FTP-t.
- **Biztonsági társítás üresjárati ideje törlés előtt**: Ha *n* másodpercig nincs hálózati forgalom, a biztonsági társítások törölve lesznek.
- **Előmegosztott kulcsok kódolása**: Az előmegosztott kulcsok kódolása UTF-8 használatával.
- **IPsec-kivételek**: Beállítható, hogy bizonyos forgalomra ne vonatkozzon az IPsec. Ilyen lehet például a **Szomszédfelderítési IPv6 ICMP-típuskódok**, az **ICMP**, az **Útválasztó-felderítési IPv6 ICMP-típuskódok**, valamint **Mind az IPv4-es, mind az IPv6-os DHCP hálózati forgalom**.
- **Visszavont tanúsítványok listájának ellenőrzése**: Beállítható egy érték, amely kötelezően alkalmazva lesz a visszavont tanúsítványok ellenőrzésekor, például **CRL-ellenőrzés letiltása**, **Sikertelen CRL-ellenőrzés csak visszavont tanúsítványok esetén**, valamint **Sikertelen CRL-ellenőrzés bármilyen hibánál**.
- **Hitelesítési készlet alkalomszerű egyeztetése kulcsmodulonként**: Beállítható, hogy a kulcskezelő modulok hagyják figyelmen kívül a teljes hitelesítési készletet, ha az adott készlet nem minden hitelesítési csomagját támogatják.
- **Csomagok várólistára helyezése**: Megadható, hogy a fogadó oldali szoftver skálázása IPsec-alagutas átjáró használata esetén miként legyen engedélyezve a titkosított fogadás és az egyszerű szöveges továbbítás számára. Ezzel biztosítható a csomagsorrend megőrzése. Ezzel a beállítással biztosítható a csomagsorrend megőrzése.

### <a name="network-settings"></a>Hálózati beállítások

Ezek a beállítások meghatározott hálózattípusokra vonatkoznak. Ilyen többek között a **Tartományi (munkahelyi) hálózat**, a **Magánhálózat (észlelhető)** és a **Nyilvános (nem észlelhető) hálózat**.

#### <a name="general-settings"></a>Általános beállítások

- **Windows Defender-tűzfal**: Ezzel a beállítással letiltható a hálózati forgalom.
- **Rejtett üzemmód**: Letiltható, hogy a tűzfal rejtett üzemmódban működjön. A rejtett üzemmód tiltásnak a beállítása az **IPsec-et használó csomagok mentességének** letiltását is lehetővé teszi.
- **Védett**: Ha ezt és a tűzfalbeállítást is engedélyezi, akkor a teljes bejövő forgalom le lesz tiltva.
- **Egyedi küldésű válaszok a csoportos küldésű szórásokra**: Egyedi küldésű válaszok tiltása a csoportos küldésű válaszokra. Csoportos küldésű vagy szórási üzenetekre általában nem kívánatos egyedi küldésű válaszokat kapni, mivel az ilyen típusú válaszok szolgáltatásmegtagadásos (DOS-) támadást jelezhetnek, vagy azt, hogy egy támadó egy ismert aktív számítógépbe próbál bejutni.
- **Bejövő értesítések**: Letiltható az üzenetek felhasználóknak való megjelenítése, ha le van tiltva, hogy az alkalmazás figyeljen egy portot.
- **Alapértelmezett művelet bejövő kapcsolatokhoz**: Letiltható az az alapbeállítás szerinti művelet, amelyet a tűzfal a bejövő kapcsolatoknál alkalmaz.

#### <a name="rule-merging"></a>Szabályegyesítés

- **Engedélyezett alkalmazás Windows Defender-tűzfalszabályai a helyi tárolóban**: A helyi tároló elfogadandó és érvényesítendő tűzfalszabályainak alkalmazása.
- **Portokkal kapcsolatos globális Windows Defender-tüzfalszabályok a helyi tárolóban**: A helyi tároló elfogadandó és érvényesítendő, portokkal kapcsolatos globális tűzfalszabályainak alkalmazása.
- **Windows Defender-tűzfalszabályok a helyi tárolóban**: A helyi tároló elfogadtatni és érvényesíteni kívánt globális tűzfalszabályainak alkalmazása.
- **Helyi tároló IPSec-szabályai**: A helyi tároló kapcsolatbiztonsági szabályainak alkalmazása, függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától.

## <a name="windows-defender-smartscreen-settings"></a>A Windows Defender SmartScreen beállításai

- **SmartScreen használata alkalmazások és fájlok esetén**: A Windows SmartScreen használata fájlok és alkalmazások futtatásához.
- **Nem ellenőrzött fájlok futtatása**: Letilthatja a végfelhasználóknál a Windows SmartScreen által nem ellenőrzött fájlok futtatását.

## <a name="windows-encryption"></a>Windows-titkosítás

### <a name="windows-settings"></a>Windowsos beállítások

Az alábbi két beállítás a Windows 10 minden verziójára érvényes:

- **Eszközök titkosítása**: Ha bekapcsolja ezt a beállítást, a rendszer kérni fogja a felhasználótól, hogy engedélyezze az eszköz titkosítását. Ezen túlmenően rá fog kérdezni, hogy nincs-e engedélyezve másik szolgáltató titkosítási funkciója. Az eszköz ugyanis instabillá válhat, ha a windowsos titkosítást úgy kapcsolják be, hogy közben egy másik titkosítási módszer aktív marad.
- **Tárolókártya titkosítása**: Ha engedélyezi ezt a beállítást, az eszközhöz használt minden cserélhető tárolókártyát titkosítani fog a rendszer.


### <a name="bitlocker-base-settings"></a>BitLocker-alapbeállítások

Az alapbeállítások minden típusú adatmeghajtóra vonatkozó univerzális BitLocker-beállítások. A BitLocker Csoportházirend-beállításai szabályozzák a végfelhasználók által a különböző típusú adatmeghajtókon módosítható meghajtótitkosítási feladatokat vagy konfigurációs beállításokat.

- **Figyelmeztetés egyéb lemeztitkosításra**: Az egyéb lemeztitkosítással kapcsolatos figyelmeztető üzenet letiltása a végfelhasználók gépein.
- **Titkosítási módszerek konfigurálása**: Ha engedélyezi ezt a beállítást, különböző titkosítási algoritmusokat állíthat be az operációs rendszerhez, a rendszeren található adatokhoz és a cserélhető meghajtókhoz.
  - **Operációsrendszer-meghajtók titkosítása**: Az operációs rendszer meghajtóihoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
  - **Rögzített adatmeghajtók titkosítása**: A rögzített (beépített) adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
  - **Cserélhető adatmeghajtók titkosítása**: A cserélhető adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Ha a cserélhető meghajtót olyan eszközökkel is használja, amelyeken nem Windows 10 operációs rendszer fut, az AES-CBC algoritmus használatát javasoljuk.

### <a name="bitlocker-os-drive-settings"></a>Operációsrendszer-meghajtók BitLocker-beállításai

Ezek a beállítások kifejezetten az operációsrendszer-adatmeghajtókra érvényesek.

- **További hitelesítés indításkor**: A számítógép indítására vonatkozó hitelesítési követelmények konfigurálása, beleértve a platformmegbízhatósági modul (TPM) használatát.
  - **BitLocker nem kompatibilis TPM-lapkával**
  - **Kompatibilis TPM indítás**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapka használatát.
  - **Kompatibilis TPM-indítási PIN-kód**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítási PIN-kód használatát.
  - **Kompatibilis TPM-indítókulcs**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítókulcs használatát.
  - **Kompatibilis TPM-indítókulcs és PIN-kód**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítókulcs és PIN-kód használatát.
- **PIN-kód minimális hossza**: Ha engedélyezi ezt a beállítást, megadhatja a TPM-indítási PIN-kód minimális hosszát.
  - **Karakterek minimális száma**: Megadhatja, hogy hány karaktert kell tartalmaznia az indításkor beírandó PIN-kódnak. A PIN-kód hossza **4**-**20** karakter lehet.
- **Operációsrendszer-meghajtó helyreállítása**: Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett operációsrendszer-meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
  - **Tanúsítványalapú adat-helyreállítási ügynök**: Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett operációsrendszer-meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 jegyű helyreállítási jelszó létrehozását.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
  - **A BitLocker helyreállítási adatainak mentése az AD DS-be**: Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
  - **AD DS-ben tárolt BitLocker helyreállítási adatok**: Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt**: Ezzel a beállítással szabályozható, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.
- **Rendszerindítás előtti helyreállítási üzenet és URL-cím**: Ezzel a beállítással engedélyezhető, hogy a rendszerindítás előtti kulcshelyreállítási képernyőn a rendszer megjelenítsen egy üzenetet és egy URL-címet.
  - **Rendszerindítás előtti helyreállítási üzenet**: Itt adhatja meg, milyen rendszerindítás előtti helyreállítási üzenet jelenjen meg a felhasználók számára. A következő lehetőségek közül választhat:
    - **Az alapértelmezett helyreállítási üzenet és URL-cím használata**
    - **Üres helyreállítási üzenet és URL-cím használata**
    - **Egyéni helyreállítási üzenet**
    - **Egyéni helyreállítási URL**

### <a name="bitlocker-fixed-data-drive-settings"></a>Rögzített adatmeghajtók BitLocker-beállításai

- **Írási hozzáférés BitLockerrel nem védett rögzített adatmeghajtóhoz**: Ha ezt a beállítást engedélyezi, a rögzített vagy beépített adatmeghajtók csak azután lesznek írhatók, ha BitLocker-védelmüket engedélyezte a felhasználó.
- **Rögzített meghajtó helyreállítása**: Ennek a beállításnak a megadásával vezérelheti, hogyan állíthatók helyre a BitLocker által védett rögzített meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk.
  - **Adat-helyreállítási ügynök**: Ezt a beállítást akkor érdemes engedélyezni, ha a BitLocker által védett rögzített meghajtók helyreállításához szeretne adat-helyreállítási ügynököket használni.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.  
  - **Helyreállítási kulcs felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Ennek a beállításnak az engedélyezésével megakadályozhatja, hogy a BitLocker bekapcsolásakor a felhasználók lássák vagy módosítani tudják a helyreállítási lehetőségeket.
  - **A BitLocker helyreállítási adatainak mentése az AD DS-be**: Ezzel a beállítással engedélyezhető, hogy a BitLocker helyreállítási információit az Active Directoryban tárolja a rendszer.
  - **AD DS-ben tárolt BitLocker helyreállítási adatok**: Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Active Directoryban. A következő lehetőségek közül választhat:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt**: Ezzel a beállítással szabályozható, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg az eszköz nem csatlakozott a tartományhoz, és nem sikerült menteni a BitLocker helyreállítási információit az Active Directoryban.

### <a name="bitlocker-removable-data-drive-settings"></a>Cserélhető adatmeghajtók BitLocker-beállításai

- **Írási hozzáférés BitLockerrel nem védett cserélhető adatmeghajtóhoz**: Ezzel a beállítással szabályozható, hogy kötelező-e BitLocker-titkosítással védeni a cserélhető adattárolókat.
  - **Írási hozzáférés a más szervezetben konfigurált eszközökhöz**: Ezt a beállítást használva megadhatja, hogy írhatnak-e a felhasználók más szervezethez tartozó cserélhető adatmeghajtókra.

## <a name="windows-defender-exploit-guard"></a>Windows Defender – biztonsági rés kiaknázása elleni védelem

A [Windows Defender - biztonsági rés kiaknázása elleni védelem](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) használatával az alkalmazottak által használt alkalmazásokat lehet kezelni, és csökkenthető vele az alkalmazások támadási felülete.

### <a name="attack-surface-reduction"></a>Támadási felület csökkentése

- **A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése**

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
- **Folyamatlétrehozás a PSExec- és WMI-parancsokból**
- **Nem megbízható és aláíratlan, USB-ről futó folyamatok**
- **Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok**

#### <a name="rules-to-prevent-email-threats"></a>E-mail-fenyegetések megakadályozását szolgáló szabályok

Az alábbiak letiltásával megakadályozhatja az e-mail-fenyegetéseket:

- **Webes levelezés vagy az asztali levelezőprogramok e-mailjeiből eltávolított végrehajtható tartalom (például .exe, .dll, .ps, .js, és .vbs fájlok) futtatása (nincs kivétel)**

#### <a name="rules-to-protect-against-ransomware"></a>Zsarolóprogramok elleni szabályok
- **Zsarolóprogramok elleni speciális védelem**

> [!TIP]
> További információ a szabályokról: [A támadási felület csökkentése a Windows Defender – biztonsági rés kiaknázása elleni védelemmel](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard).

#### <a name="attack-surface-reduction-exceptions"></a>Támadási felület csökkentése – kivételek

- **Fájlok és mappák kizárása a támadási felület csökkentésére szolgáló szabályok hatálya alól**: Helyek listájának importálása és hozzáadása a konfigurált szabályok alóli kizárásra.

### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

Rosszindulatú alkalmazások és fenyegetések, például zsarolóprogramok ellen védheti értékes adatait.

- **Mappavédelem**: A fájlok és mappák rosszindulatú alkalmazások által végrehajtott jogosulatlan módosításainak megakadályozása. **Védett mappákhoz hozzáférő alkalmazások listáját** importálhatja, vagy manuálisan is hozzáadhatja. **További védendő mappák listáját** is hozzáadhatja feltöltéssel, vagy manuálisan is hozzáadhatja őket.

### <a name="network-filtering"></a>Hálózatszűrés

Bármely alkalmazásból letilthatja az alacsony megbízhatóságú IP-címekre vagy tartományokba irányuló kimenő kapcsolatokat.

### <a name="exploit-protection"></a>Biztonsági rés kiaknázása elleni védelem

Letilthatja, hogy a **felhasználók a Biztonsági rés kiaknázása elleni védelem felületét módosítsák**, ha feltölt egy olyan XML-fájlt, amely lehetővé teszi a memória, a vezérlésfolyam és a szabályzatkorlátozások konfigurálását. Az XML-fájlban található beállításokkal megvédheti az alkalmazást a biztonsági rések ellen.

A biztonsági rés kiaknázása elleni védelem engedélyezéséhez hozzon létre egy XML-fájlt, amely a rendszer és az alkalmazások kockázatcsökkentésének kívánt beállításait tartalmazza. Ezt kétféle módon végezheti el:

 1. PowerShell: Egy vagy több Get-ProcessMitigation, Set-ProcessMitigation és ConvertTo-ProcessMitigationPolicy PowerShell-parancsmagot használhat. A parancsmagokkal konfigurálhatja a kockázatcsökkentési beállításokat, és exportálhatja ezek XML-reprezentációját.

 2. A Windows Defender Security Center felhasználói felülete: A Windows Defender Security Centerben kattintson az Alkalmazás- és böngészőszabályozásra, majd a megjelenő képernyő alján keresse meg az Biztonsági rés kiaknázása elleni védelem elemet. Először a Rendszerbeállítások és a Programbeállítások lap használatával konfigurálja a kockázatcsökkentési beállításokat. Ha végzett, a képernyő alján keresse meg az Exportálási beállítások hivatkozást, amellyel exportálhatja ezek XML-reprezentációját.

## <a name="windows-defender-application-control"></a>Windows Defender Alkalmazásvezérlés

Az **Alkalmazás-ellenőrző kódintegritási szabályzatok** használatával további alkalmazásokat is kiválaszthat, amelyeket a Windows Defender Alkalmazásvezérlésnek ellenőriznie kell, vagy biztonságosan futtathatónak kell besorolnia. A Windows-összetevők és a Windows Áruházból származó alkalmazások automatikusan biztonságosan futtathatóként lesznek besorolva.

**Naplózási módban** az alkalmazások nincsenek letiltva. A **naplózási mód** minden eseményt egy ügyfélnaplóban rögzít.

Ha az Alkalmazásvezérlést bekapcsolták, utána csak úgy lehet letiltani, ha a módot **Kényszerítésről** **Naplózási módra** változtatja. Ha a módot **Kényszerítésről** **Nincs konfigurálva** értékre változtatja, akkor az Alkalmazásvezérlés a hozzárendelt eszközökön továbbra is kényszerítve lesz.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard
A Windows Defender Credential Guard a hitelesítő adatok ellopása ellen nyújt védelmet. Úgy különíti el a titkos kulcsokat, hogy csak a jogosult rendszerszoftverek férjenek hozzájuk.

A **Credential Guard** beállításai:

- **Disabled**: Távolról kikapcsolja a Credential Guardot, ha azt korábban bekapcsolta az **Engedélyezve UEFI-zárolás nélkül** funkcióval.
- **Engedélyezve UEFI-zárolás nélkül**: Ezzel a beállítással biztosíthatja, hogy a Credential Guard ne legyen letiltható egy távoli beállításkulccsal vagy egy csoportházirenddel.

    > [!NOTE]
    > Ha ezt a beállítást használja, majd később le szeretné tiltani a Credential Guardot, a csoportházirendet **letiltott** állapotra kell állítania, majd törölnie kell az UEFI-konfigurációs adatokat minden számítógépről. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

- **Engedélyezve UEFI-zárolás nélkül**: Távolról letilthatja a Credential Guardot egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, a Windows 10 1511-es vagy újabb verziójának kell futnia.

Ha engedélyezi a Credential Guardot, azzal az alábbi kötelező funkciókat is engedélyezi:

- **Virtualizálás-alapú biztonság** (VBS): A következő újraindítás során lép életbe. A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz.
- **Biztonságos rendszerindítás közvetlen memóriaeléréssel**: Bekapcsolja a VBS-t a biztonságos rendszerindítás és a közvetlen memóriaelérés (DMA) védelmi funkcióival. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.

## <a name="windows-defender-security-center"></a>Windows Defender biztonsági központ

A Windows Defender biztonsági központ alkalmazás az egyes funkcióktól elkülönített alkalmazásként működik. Az értesítéseket a Műveletközponton keresztül jeleníti meg. Olyan gyűjtőhelyként funkcionál, ahol megtekinthetők az állapotok, és ahol minden funkció esetében elvégezhetők bizonyos beállítások. További információt a [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) dokumentációjában talál.

#### <a name="windows-defender-security-center-app-and-notifications"></a>A Windows Defender biztonsági központ alkalmazás és az értesítések

Letilthatja a felhasználói hozzáférést a Windows Defender biztonsági központ alkalmazás különböző területeihez. Egy szakasz elrejtése a kapcsolódó értesítéseket is letiltja.

- **Vírusok és veszélyforrások elleni védelem**
- **Eszközteljesítmény és -állapot**
- **Tűzfal és hálózatvédelem**
- **Alkalmazás- és böngészővezérlés**
- **Családi beállítások**
- **Az alkalmazás megjelenített területeihez kapcsolódó értesítések**: Annak kiválasztása, hogy mely értesítések jelenjenek meg a végfelhasználók számára. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső összefoglalói, például a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül.

#### <a name="it-contact-information"></a>Az informatikai szolgálat kapcsolattartási adatai

Adja meg az informatikai szolgálat azon elérhetőségeit, amelyek megjelennek majd a Windows Defender biztonsági központ alkalmazásban és az alkalmazásértesítésekben. Az alábbi lehetőségek közül választhat: **Az alkalmazásban és az értesítésekben is jelenjen meg**, **Csak az alkalmazásban jelenjen meg**, **Csak az értesítésekben jelenjen meg** és **Ne jelenjen meg**. Meg kell adnia az **IT-szervezet nevét**, és az alábbi kapcsolatfelvételi lehetőségek közül legalább egyet:

- **IT-részleg telefonszáma vagy Skype-elérhetősége**
- **IT-részleg e-mail címe**
- **Informatikai támogatási webhely URL-címe**

## <a name="local-device-security-options"></a>Helyi eszközbiztonsági beállítások

Ezekkel a beállításokkal konfigurálhatja a Windows 10-eszközök helyi biztonsági beállításait.

### <a name="accounts"></a>Fiókok

- **Új Microsoft-fiókok hozzáadása**: Megakadályozza, hogy a felhasználók új Microsoft-fiókokat adjanak hozzá a számítógépen.
- **Távoli bejelentkezés jelszó nélkül**: Engedélyezi a jelszóval nem védett helyi fiókok számára a fizikai eszközön kívüli helyekről történő bejelentkezést.

#### <a name="admin"></a>Felügyelet

- **Helyi rendszergazdai fiók**: Eldöntheti, hogy a helyi rendszergazdai fiók engedélyezve legyen vagy le legyen-e tiltva.
- **Rendszergazdai fiók átnevezése**: Adjon meg egy másik fióknevet, amelyet társíthat a rendszergazdai fiók biztonsági azonosítójához.

#### <a name="guest"></a>Vendég

- **Vendégfiók**: Eldöntheti, hogy engedélyezi vagy letiltja a vendégfiókot.
- **Vendégfiók átnevezése**: Adjon meg egy másik fióknevet, amelyet társíthat a vendégfiók biztonsági azonosítójához.

### <a name="devices"></a>Eszközök

- **Eszköz dokkolásának megszüntetése bejelentkezés nélkül**: Megakadályozza, hogy egy hordozható számítógép dokkolását megszüntessék bejelentkezés nélkül.
- **Nyomtató-illesztőprogramok telepítése a megosztott nyomtatók számára**: Csak rendszergazdákra korlátozhatja a megosztott nyomtatókhoz való csatlakozáskor a nyomtató-illesztőprogramok telepítését.
- **CD-ROM-hozzáférés korlátozása a helyi aktív felhasználókra**: Ezzel a beállítással csak az interaktív módon bejelentkezett felhasználók férhetnek hozzá a CD-ROM-okhoz
- **Cserélhető adathordozó formázása és kiadása**: Megadhatja, ki formázhat és adhat ki cserélhető NTFS-adathordozókat:
  - **Nincs konfigurálva**
  - **Rendszergazdák és kiemelt felhasználók**
  - **Rendszergazdák és interaktív felhasználók**

### <a name="interactive-logon"></a>Interaktív bejelentkezés

- **Ennyi perc inaktivitás a zárolási képernyőn a képernyővédő aktiválása előtt**: Megadhatja az interaktív asztal bejelentkezési képernyőjén töltött inaktív percek maximum számát, mielőtt elindul a képernyővédő.
- **CTRL+ALT+DEL billentyűkombináció a bejelentkezéshez**: A CTRL+ALT+DEL billentyűkombináció kötelezővé tétele a felhasználói bejelentkezésekhez.
- **Viselkedés intelligens kártya eltávolításakor**: Meghatározza, hogy mi történik, ha egy bejelentkezett felhasználó intelligens kártyáját eltávolítják az intelligenskártya-olvasóból.
A [LocalPoliciesSecurity-beállítások](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) című témakörben további információt találhat.

#### <a name="display"></a>Megjelenítés

- **Felhasználói adatok a zárolási képernyőn**: A lezárt munkamenetek során megjelenített felhasználói adatokat konfigurálja. Ha nincs konfigurálva, a felhasználó megjelenített neve, a tartomány és a felhasználónév látható.
  - **Csak a felhasználó megjelenített neve**
  - **Ne jelenjenek meg a felhasználói adatok**
  - **Nincs konfigurálva**: Felhasználó megjelenített neve, a tartomány és a felhasználónév
- **Utolsó bejelentkezett felhasználó elrejtése**: Ne jelenjen meg az eszközön legutóbb bejelentkezett személy felhasználóneve.
- **Felhasználónév elrejtése a bejelentkezéskor**: Ne jelenjen meg az eszközre bejelentkező személy felhasználóneve a hitelesítő adatok megadása után, valamint az eszköz asztalának megjelenítése előtt.
- **Bejelentkezési üzenet címe:** A bejelentkező felhasználók számára megjelenő üzenet címe.
- **Bejelentkezési üzenet szövege:** A bejelentkező felhasználók számára megjelenő üzenet szövege.

### <a name="network-access-and-security"></a>Hálózati hozzáférés és biztonság

- **Névtelen hozzáférés a nevesített csövekhez és a megosztásokhoz**: Korlátozza a névtelen hozzáférést a megosztási és a névtelen csövekre vonatkozó beállításokhoz. A névtelenül megadható beállításokra vonatkozik.
- **SAM-fiókok névtelen enumerálása**: Lehetővé teszi a névtelen felhasználók számára a SAM-fiókok enumerálását. A Windows engedélyezi a névtelen felhasználók számára a tartományfiókok és hálózati megosztások enumerálását.
- **SAM-fiókok és megosztások névtelen enumerálása**: Letilthatja a SAM-fiókok és megosztások névtelen enumerálását. A Windows engedélyezi a névtelen felhasználók számára a tartományfiókok és hálózati megosztások enumerálását.
- **A LAN Manager üzenetkivonatának tárolása jelszómódosításkor**: A következő jelszómódosításakor megadhatja, hogy a rendszer tárolja-e az új jelszó LAN Manager- (LM-) üzenetkivonatát. Az alapértelmezett beállítás a Nem.
- **PKU2U hitelesítési kérelmek**: Az eszköz PKU2U hitelesítési kérelmeinek letiltása az online azonosító adatok használatához.
- **Távoli RPC-kapcsolatok korlátozása SAM-re**: Az alapértelmezett Security Descriptor Definition Language-karakterlánc szerkesztésével engedélyezheti vagy letilthatja a felhasználók és csoportok számára a SAM felé intézett távoli hívásokat.
- **Biztonsági leíró**

### <a name="recovery-console-and-shutdown"></a>Helyreállítási konzol és leállítás

- **A virtuális memória lapozófájljának törlése leállításkor**: Törli a virtuális memória lapozófájlját az eszköz leállításakor.
- **Leállítás bejelentkezés nélkül**: Letiltja a számítógép a Windows bejelentkezési képernyőről való leállításának beállítását. Ebben az esetben a felhasználóknak be kell jelentkezniük a számítógépbe, mielőtt rendszerleállítást kezdeményezhetnek.

### <a name="user-account-control"></a>Felhasználói fiókok felügyelete

- **UIA-integritás biztonságos hely nélkül**: Engedélyezi a fájlrendszer nem biztonságos helyein található alkalmazások UIAccess integritási szint nélküli futtatását.
- **Fájl- és beállításjegyzékbeli írási hibák virtualizálása felhasználónkénti helyekre**: Megadhatja, hogy az alkalmazás írási hibái meghatározott beállításjegyzékbeli és fájlrendszerbeli helyekre legyenek átirányítva. Másik lehetőségként a hibák az alkalmazás sikertelen futását eredményezik.
- **Csak az aláírt és érvényesített végrehajtható fájlok jogosultságszintjének emelése**: Kényszerítheti a PKI-tanúsítványlánc érvényesítését egy adott végrehajtható fájlhoz, mielőtt az engedélyt kapna a futtatásra.

#### <a name="uia-elevation-prompt-behavior-settings"></a>UIA jogosultságszint-emelési kérés viselkedésének beállításai

- **Jogosultságszint-emelési kérés rendszergazdák számára**: Meghatározhatja a jogosultságszint-emelési kérés működését rendszergazdák esetében, rendszergazdai engedélyezéses módban:
  - **Jogosultságszint-emelés kérés nélkül**
  - **Hitelesítő adatok bekérése a biztonságos asztalon**
  - **Beleegyezés kérése a biztonságos asztalon**
  - **Hitelesítő adatok bekérése**
  - **Beleegyezés kérése**
  - **Nincs konfigurálva**: Beleegyezés kérése nem Windowsos bináris fájlokhoz
- **Jogosultságszint-emelési kérés általános jogú felhasználók számára**: Meghatározhatja a jogosultságszint-emelési kérés működését általános jogú felhasználók esetében:
  - **Jogosultságszint-emelési kérések automatikus megtagadása**
  - **Hitelesítő adatok bekérése a biztonságos asztalon**
  - **Nincs konfigurálva**: Hitelesítő adatok bekérése
- **Jogosultságszint-emelési kérések átirányítása a felhasználó interaktív asztalára**: Engedélyezheti minden jogosultságszint-emelési kéréshez, hogy az interaktív felhasználó asztalára legyenek irányítva a biztonságos asztal helyett. A rendszer a rendszergazdákra és az általános jogú felhasználókra vonatkozó kérések viselkedését szabályzó házirend-beállításokat alkalmazza.
- **Jogosultságszint-emelési kérések alkalmazástelepítéshez**: A megemelt jogosultsági szintet igénylő alkalmazástelepítések rendszergazdai hitelesítő adatokat kérnek.
- **UIA jogosultságszint-emelési kérés biztonságos asztal nélkül**: Az alkalmazások kérhetik a UIAccess jog emelését a biztonsági asztal használata nélkül.

#### <a name="admin-approval-mode-settings"></a>A rendszergazdai engedélyezéses mód beállításai

- **Rendszergazdai engedélyezéses mód a beépített rendszergazdához**: Meghatározza, hogy a beépített rendszergazdai fiók rendszergazdai engedélyezéses módot használ, vagy minden alkalmazást teljes rendszergazdai jogosultságokkal futtat.
- **Minden rendszergazda futtatása rendszergazdai engedélyezéses módban**: Meghatározhatja, hogy engedélyezve legyen-e a rendszergazdai engedélyezéses mód és az összes UAC-házirendbeállítás.

### <a name="microsoft-network-client"></a>Microsoft hálózati ügyfél

- **Kommunikáció digitális aláírása (ha a kiszolgáló egyetért)**: Meghatározza, hogy az SMB-ügyfél SMB-csomagok aláírását próbálja-e egyeztetni. Ha ez a beállítás engedélyezve van (ez az alapértelmezés), a Microsoft hálózati ügyfél a kiszolgálótól a munkamenet beállításakor az SMB-csomagok aláírását kéri. Ha a csomagaláírás engedélyezve van a kiszolgálón, a csomagaláírás egyeztetése megkezdődik. Ha ez a szabályzat le van tiltva, az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Titkosítatlan jelszó küldése külső SMB-kiszolgálóknak**: Ha ez a beállítás engedélyezve van, a Server Message Block- (SMB-) átirányító egyszerű szöveges jelszavakat küldhet az olyan, nem Microsoftos SMB-kiszolgálóknak, amelyek nem támogatják a hitelesítés közbeni jelszótitkosítást.

### <a name="microsoft-network-server"></a>Microsoft hálózati kiszolgáló

- **Kommunikáció digitális aláírása (ha az ügyfél egyetért)**: Meghatározza, hogy az SMB-kiszolgáló egyezteti-e az SMB-csomagok aláírását az ezt kérő ügyfelekkel. Ha ez a beállítás engedélyezve van, a Microsoft hálózati kiszolgáló egyezteti az SMB-csomagok aláírását az ügyfél kérése szerint. Ez azt jelenti, hogy ha a csomagaláírás engedélyezve van az ügyfélnél, a csomagaláírás egyeztetése megkezdődik. Ha ez a szabályzat le van tiltva (ez az alapértelmezett beállítás), az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Kommunikáció digitális aláírása (mindig)**: Meghatározza, hogy a csomagaláírás kötelező-e az SMB-kiszolgáló-összetevő számára. Ha ez a beállítás engedélyezve van, a Microsoft hálózati kiszolgáló nem kommunikál a Microsoft hálózati ügyféllel, hacsak az ügyfél bele nem egyezik az SMB-csomagok aláírásába. Ha ez a beállítás le van tiltva (ez az alapértelmezett állapot), az SMB-csomagok aláírásának egyeztetése megkezdődik az ügyfél és a kiszolgáló között.

## <a name="next-steps"></a>További lépések

Ha a profilt csoportokhoz szeretné rendelni, az [Eszközprofilok hozzárendelése](device-profile-assign.md) című cikkben talál további információt.

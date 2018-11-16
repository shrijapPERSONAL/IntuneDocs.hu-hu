---
title: Endpoint Protection hozzáadása Windows 10 rendszeren az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsot Intune-ban, Windows 10-eszközökön az Endpoint Protection-beállítások használatával vagy konfigurálásával engedélyezheti a Windows Defender funkcióit, így az alkalmazásőrt, a tűzfalat, a SmartScreent, a titkosítást és a BitLockert, a biztonsági rés kiaknázása elleni védelmet, az alkalmazásvezérlést, a biztonsági központot és a helyi eszközök biztonságát.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a7c7ebca1c6472b58021a57b1b4a59fc42966b0
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576953"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Intune Endpoint Protection-beállítások Windows 10 és újabb rendszerekhez

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Endpoint Protection-profillal a Windows 10-es eszközök olyan biztonsági szolgáltatásait szabályozhatja, mint például a BitLocker és a Windows Defender.

A cikk segítségével Endpoint Protection-profilokat hozhat létre. A Windows Defender víruskereső konfigurálásához tekintse meg a [Windows 10-es eszközkorlátozásokat](device-restrictions-windows-10.md#windows-defender-antivirus). 

## <a name="windows-defender-application-guard"></a>Windows Defender alkalmazásőr

A következő Windows 10-kiadásokon támogatott:

- Vállalati 
- Professional

A Microsoft Edge használata közben a Windows Defender alkalmazásőr megvédi a környezetét az olyan webhelyektől, amelyek nincsenek megbízhatóként meghatározva a szervezetében. Amikor a felhasználók az elkülönített hálózathatáron kívüli webhelyekre lépnek, a webhelyek egy Hyper-V-beli virtuális böngésző-munkamenetben nyílnak meg. A megbízható webhelyeket egy hálózathatár definiálja, amely az Eszközkonfiguráció menüben konfigurálható.

Az Alkalmazásőr csak a 64 bites Windows 10-eszközöknél érhető el. Ennek a profilnak a használatával telepítve lesz az Alkalmazásőr aktiválásához szükséges Win32-összetevő.

- **Alkalmazásőr**: **Engedélyezze** a nem jóváhagyott helyeket Hyper-V-vel virtualizált, tárolóalapú böngészővel való funkció bekapcsolásához. A **Nincs konfigurálva** (alapértelmezett) érték azt jelenti, bármely – jóváhagyott és nem jóváhagyott – webhely megnyitható az eszközön.
- **A vágólap működése**: Meghatározhatja, hogy milyen másolási és beillesztési műveletek legyenek engedélyezve a helyi PC és az alkalmazásőrrel védett virtuális böngésző között.
- **Vállalati webhelyeken lévő külső tartalom**: A nem jóváhagyott webhelyekről származó tartalom betöltésének **tiltása**. A **Nincs konfigurálva** (alapértelmezett) érték azt jelenti, hogy a nem vállalati webhelyek megnyílhatnak az eszközön.
- **Nyomtatás a virtuális böngészőből**: **Engedélyezze** a virtuális böngészőben megjelenő tartalom a PDF-, az XPS-, a helyi és/vagy a hálózati nyomtatókkal történő nyomtatásának engedélyezéséhez. A **Nincs konfigurálva** (alapértelmezett) érték letilt minden nyomtatási funkciót.
- **Naplók gyűjtése**: **Engedélyezze** az alkalmazásőr virtuális böngészési munkamenetében előforduló események naplóinak összegyűjtéséhez. A **Nincs konfigurálva** (alapértelmezett) érték nem gyűjt naplókat a böngészési munkamenetben.
- **Felhasználó által létrehozott böngészési adatok megtartása**: **Engedélyezze** az alkalmazásőr által védett böngészési munkamenet során létrehozott felhasználói adatok (például jelszavak, kedvencek vagy cookie-ek) mentéséhez. A **Nincs konfigurálva** (alapértelmezett) érték elveti a felhasználó által letöltött fájlokat és adatokat az eszköz újraindulásakor vagy a felhasználó kijelentkezésekor.
- **Grafikus gyorsítás**: **Engedélyezze** a magas grafikus igénylő webhelyek és videók egy virtuális grafikus feldolgozóegységgel történő gyorsabb betöltéséhez. A **Nincs konfigurálva** (alapértelmezett) érték az eszköz CPU-ját használja a grafikus feladatokhoz, és nem a virtuális grafikus feldolgozóegységet.
- **Fájlok letöltése a gazdagép fájlrendszerébe**: **Engedélyezze** a felhasználóknak, hogy letöltsenek fájlokat a virtualizált böngészőből a gazdagép operációs rendszerébe. A **Nincs konfigurálva** (alapértelmezett) érték a fájlokat helyi szinten, az eszközön tárolja, és nem tölti le őket a gazdarendszerbe.

## <a name="windows-defender-firewall"></a>Windows Defender-tűzfal

A következő Windows 10-kiadásokon támogatott:
- Otthoni
- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

### <a name="global-settings"></a>Globális beállítások

Ezek a beállítások minden hálózattípusnál alkalmazhatók.

- **File Transfer Protocol**: **Tiltsa le** az állapot-nyilvántartó FTP letiltásához. Ha a **Nincs konfigurálva** (alapértelmezett) érték van beállítva, a tűzfal szűrést végez az állapot-nyilvántartó FTP-re a másodlagos kapcsolatok engedélyezéséhez.
- **Biztonsági társítás üresjárati ideje törlés előtt**: Ha *n* másodpercig nincs hálózati forgalom, a biztonsági társítások törölve lesznek. Adja meg másodpercben az üresjárati időt.
- **Előmegosztott kulcsok kódolása**: **Engedélyezze** az előmegosztott kulcsok UTF-8 használatával történő kódolásához. A **Nincs konfigurálva** (alapértelmezett) érték a helyi tárolóértéket használja.
- **IPsec-kivételek**: Beállítható, hogy bizonyos forgalomra ne vonatkozzon az IPsec, például:
  - **Szomszédfelderítési IPv6 ICMP-típuskódok**
  - **ICMP**
  - **Útválasztó-felderítési IPv6 ICMP-típuskódok**
  - **IPv4-es és IPv6-os DHCP hálózati forgalom**
- **Visszavont tanúsítványok listájának ellenőrzése**: Megadhatja, hogy hogyan lesz kötelezően alkalmazva a visszavont tanúsítványok ellenőrzése, például a **CRL-ellenőrzés letiltása**, a **Sikertelen CRL-ellenőrzés csak visszavont tanúsítványok esetén**, valamint a **Sikertelen CRL-ellenőrzés bármilyen hibánál**.
- **Hitelesítési készlet alkalomszerű egyeztetése kulcsmodulonként**: **Engedélyezze**, hogy a kulcskezelő modulok kizárólag a nem támogatott hitelesítési csomagokat hagyják figyelmen kívül. **Ha nincs konfigurálva**, a kulcsmoduloknak kötelező figyelmen kívül hagyniuk a teljes hitelesítési készletet, ha nem támogatják a készletben megadott összes hitelesítési csomagot.
- **Csomagok várólistára helyezése**: Megadható, hogy a fogadó oldali szoftver skálázása IPsec-alagutas átjáró használata esetén miként legyen engedélyezve a titkosított fogadás és az egyszerű szöveges továbbítás számára. Ezzel biztosítható a csomagsorrend megőrzése. Ezzel a beállítással biztosítható a csomagsorrend megőrzése.

### <a name="network-settings"></a>Hálózati beállítások

Ezek a beállítások meghatározott hálózattípusokra vonatkoznak. Ilyen többek között a **Tartományi (munkahelyi) hálózat**, a **Magánhálózat (észlelhető)** és a **Nyilvános (nem észlelhető) hálózat**.

#### <a name="general-settings"></a>Általános beállítások

- **Windows Defender tűzfal**: **Engedélyezze** a tűzfal és a speciális biztonság bekapcsolásához. A **Nincs konfigurálva** (alapértelmezett) beállítással a házirendbeállításokból függetlenül minden hálózati forgalom engedélyezve van.
- **Rejtett üzemmód**: **Letiltja** a tűzfal rejtett üzemmódban való működését. A rejtett üzemmód tiltásnak a beállítása az **IPsec-et használó csomagok mentességének** letiltását is lehetővé teszi. A **Nincs konfigurálva** (alapértelmezett) érték rejtett üzemmódban működteti a tűzfalat, ami segít megelőzni az ellenőrzési kérelmekre adott válaszokat.
- **Védett**: A **letiltással** kikapcsolhatja a funkciót. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást. Ha a beállítás és a Windows Defender-tűzfal be van kapcsolva, minden bejövő forgalom le van tiltva az egyéb házirend-beállításoktól függetlenül.
- **Egyedi küldésű válaszok a csoportos küldésű szórásokra**: **Letiltás** értékre állítva letiltja az egyedi küldésű válaszokat a csoportos küldésű válaszokra. Csoportos küldésű vagy szórási üzenetekre általában nem kívánatos egyedi küldésű válaszokat kapni, mivel az ilyen típusú válaszok szolgáltatásmegtagadásos (DOS-) támadást jelezhetnek, vagy azt, hogy egy támadó egy ismert aktív számítógépbe próbál bejutni. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást.
- **Bejövő értesítések**: **Letiltás** értékre állítva elrejti az értesítéseket a felhasználók elől, amikor le van tiltva, hogy egy alkalmazás figyeljen egy portot. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást, és megjeleníthet értesítéseket a felhasználóknak, amikor le van tiltva, hogy egy alkalmazás figyeljen egy portot.
- **Alapértelmezett művelet bejövő kapcsolatokhoz**: **Letiltás** értékre állítva az alapértelmezett tűzfalművelet nem fut a bejövő kapcsolatoknál. A **Nincs konfigurálva** (alapértelmezett) értékre állítva az alapértelmezett tűzfalművelet elindul a bejövő kapcsolatoknál.

#### <a name="rule-merging"></a>Szabályegyesítés

- **Engedélyezett alkalmazás Windows Defender-tűzfalszabályai a helyi tárolóban**: **Engedélyezze** elfogadandó és érvényesítendő tűzfalszabályainak alkalmazásához. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló alkalmazásának engedélyezett tűzfalszabályait.
- **Portokkal kapcsolatos globális Windows Defender-tűzfalszabályok a helyi tárolóban**: **Engedélyezze** a helyi tároló elfogadandó és érvényesítendő, portokkal kapcsolatos globális tűzfalszabályainak alkalmazásához. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló globális portjának engedélyezett tűzfalszabályait.
- **Windows Defender-tűzfalszabályok a helyi tárolóban**: **Engedélyezze** a helyi tároló elfogadtatni és érvényesíteni kívánt tűzfalszabályainak alkalmazásához. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló tűzfalszabályait.
- **Helyi tároló IPSec-szabályai**: **Engedélyezze** a helyi tároló kapcsolatbiztonsági szabályainak alkalmazásához, függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló kapcsolatbiztonsági szabályait, függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától.

## <a name="windows-defender-smartscreen-settings"></a>A Windows Defender SmartScreen beállításai

A következő, Microsoft Edge böngészővel rendelkező Windows 10- kiadásokon támogatott:
- Otthoni
- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

**Beállítások**:

- **SmartScreen használata alkalmazások és fájlok esetén**: A Windows SmartScreen **használata** fájlok és alkalmazások futtatásához. A SmartScreen egy felhőalapú, adathalászat elleni és kártevőirtó összetevő. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a SmartScreent.
- **Nem ellenőrzött fájlok futtatása**: **Letilthatja** a végfelhasználóknál a Windows SmartScreen által nem ellenőrzött fájlok futtatását. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót, és engedélyezi a végfelhasználók számára, hogy nem ellenőrzött fájlokat futtassanak.

## <a name="windows-encryption"></a>Windows-titkosítás

### <a name="windows-settings"></a>Windowsos beállítások

A következő Windows 10-kiadásokon támogatott:

- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

**Beállítások**:

- **Eszközök titkosítása**: **Kötelezővé teszi** az eszköz titkosításának felhasználói engedélyezését. A Windows kiadásától és a rendszerkonfigurációtól függően a rendszer a következőket kérheti a felhasználóktól:  
  - Megerősítés arról, hogy nincs engedélyezve másik szolgáltató titkosítási funkciója
  - A BitLocker meghajtótitkosítás kikapcsolása, majd a Bitlocker újbóli bekapcsolása
    
    Az eszköz ugyanis instabillá válhat, ha a windowsos titkosítást úgy kapcsolják be, hogy közben egy másik titkosítási módszer aktív marad. 
- **Tárolókártya titkosítása (csak mobil)**: Az eszközhöz használt minden cserélhető tárolókártya **kötelező** titkosítása. A **Nincs konfigurálva** (alapértelmezett) érték nem teszi kötelezővé a tárolókártya titkosítását, és nem kéri a felhasználót, hogy kapcsolja be. Ez a beállítás csak Windows 10 Mobile-eszközökre vonatkozik.

### <a name="bitlocker-base-settings"></a>BitLocker-alapbeállítások

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

Az alapbeállítások minden típusú adatmeghajtóra vonatkozó univerzális BitLocker-beállítások. Ezek a beállítások szabályozzák a végfelhasználók által a különböző típusú adatmeghajtókon módosítható meghajtótitkosítási feladatokat vagy konfigurációs beállításokat.

- **Figyelmeztetés egyéb lemeztitkosításra**: A **Letiltás** funkcióval letilthatja a lemeztitkosítással kapcsolatos figyelmeztető üzeneteket, ha egy másik lemeztitkosítási szolgáltatás is található az eszközön. A **Nincs konfigurálva** (alapértelmezett) értékre állítva megjelenhetnek a figyelmeztetések.
- **Titkosítási módszerek konfigurálása**: Ha **engedélyezi** ezt a beállítást, különböző titkosítási algoritmusokat állíthat be az operációs rendszerhez, a rendszeren található adatokhoz és a cserélhető meghajtókhoz. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a BitLocker az XTS-AES 128 bites funkciót használja alapértelmezett titkosítási módszerként, vagy egy telepítési szkript által meghatározott titkosítási módszert.
  - **Operációsrendszer-meghajtók titkosítása**: Az operációs rendszer meghajtóihoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
  - **Rögzített adatmeghajtók titkosítása**: A rögzített (beépített) adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
  - **Cserélhető adatmeghajtók titkosítása**: A cserélhető adatmeghajtókhoz használandó titkosítási módszer kiválasztására szolgál. Ha a cserélhető meghajtót olyan eszközökkel is használja, amelyeken nem Windows 10 operációs rendszer fut, az AES-CBC algoritmus használatát javasoljuk.

### <a name="bitlocker-os-drive-settings"></a>Operációsrendszer-meghajtók BitLocker-beállításai
A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

Ezek a beállítások kifejezetten az operációsrendszer-adatmeghajtókra érvényesek.

- **További hitelesítés indításkor**: A számítógép indítására vonatkozó hitelesítési követelmények konfigurálásához, beleértve a platformmegbízhatósági modul (TPM) használatát, válassza a **Kötelező** értéket. Válassza a **Nincs konfigurálva** (alapértelmezett) értéket, ha csak az alapszintű beállításokat szeretné konfigurálni a TPM-mel rendelkező eszközökön.
  - **BitLocker nem kompatibilis TPM-lapkával**: **Letiltás** a BitLockerrel, ha egy eszköz nem rendelkezik kompatibilis TPM-lapkával. Ha **nincs konfigurálva**, a felhasználók kompatibilis TPM-lapka nélkül használhatják a BitLockert. A BitLockerhez jelszóra vagy indítókulcsra lehet szüksége.
  - **Kompatibilis TPM indítás**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapka használatát.
  - **Kompatibilis TPM-indítási PIN-kód**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítási PIN-kód használatát. Indítási PIN-kód engedélyezéséhez végfelhasználói beavatkozás szükséges. 
  - **Kompatibilis TPM-indítókulcs**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítókulcs használatát. Indítókulcs engedélyezéséhez végfelhasználói beavatkozás szükséges. 
  - **Kompatibilis TPM-indítókulcs és PIN-kód**: Engedélyezheti, letilthatja vagy kötelezővé teheti a TPM-lapkához tartozó indítókulcs és PIN-kód használatát. Indítókulcs és indítási PIN-kód engedélyezéséhez végfelhasználói beavatkozás szükséges.
- **PIN-kód minimális hossza**: Ha **engedélyezi** ezt a beállítást, megadhatja a TPM-indítási PIN-kód minimális hosszát. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók bármilyen, 6 és 20 karakter közötti hosszúságú indítási PIN-kódot megadhatnak.
  - **Karakterek minimális száma**: Megadhatja, hogy hány karaktert kell tartalmaznia az indításkor beírandó PIN-kódnak. A PIN-kód hossza **4**-**20** karakter lehet.
- **Operációsrendszer-meghajtó helyreállítása**: Ennek a beállításnak az **engedélyezésével** vezérelheti, hogyan állíthatók helyre a BitLocker által védett operációsrendszer-meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk. A **Nincs konfigurálva** (alapértelmezett) értékre állítva az alapértelmezett helyreállítási beállítások támogatva vannak a BitLocker-helyreállításhoz. Alapértelmezés szerint a DRA engedélyezve van, a felhasználó adja meg a helyreállítási beállításokat, így a helyreállítási jelszót és helyreállítási kulcsot, a helyreállítási adatok pedig nincsenek mentve az AD DS-re.
  - **Tanúsítványalapú adat-helyreállítási ügynök**: **Letiltás** értékre állítva nem használhat adat-helyreállítási ügynököket BitLocker által védett operációsrendszer-lemezekkel. A beállítás engedélyezéséhez állítsa azt **Nincs konfigurálva** (alapértelmezett) értékre, így használhatók adat-helyreállítási ügynökök a BitLocker által védett operációsrendszer-lemezekkel.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 jegyű helyreállítási jelszó létrehozását.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Állítsa **Letiltás** értékre, ha nem szeretné, hogy a felhasználók lássák és módosíthassák a helyreállítási beállításokat. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók láthatják és módosíthatják a helyreállítási beállításokat a BitLocker bekapcsolásakor.
  - **A BitLocker helyreállítási adatainak mentése az AD DS-be**: Ezzel a beállítással **engedélyezheti**, hogy a BitLocker helyreállítási információit az Azure Active Directoryban (AAD) tárolja a rendszer. **Nincs konfigurálva** (alapértelmezett) értékre állítva a rendszer nem tárolja a helyreállítási információkat az AAD-ben.
  - **AD DS-ben tárolt BitLocker helyreállítási adatok**: Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Azure AD-ben. A következő lehetőségek közül választhat:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt**: A beállítás **kötelezővé tételével** szabályozhatja, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg nem sikerült menteni a BitLocker helyreállítási információit az Azure Active Directoryban. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók akkor is bekapcsolhatják a BitLockert, ha a helyreállítási információkat nem sikerült tárolni az Azure Active Directoryban.
- **Rendszerindítás előtti helyreállítási üzenet és URL-cím**: Ezzel a beállítással **engedélyezheti**, hogy a rendszerindítás előtti kulcshelyreállítási képernyőn a rendszer megjelenítsen egy üzenetet és egy URL-címet. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót.
  - **Rendszerindítás előtti helyreállítási üzenet**: Itt adhatja meg, milyen rendszerindítás előtti helyreállítási üzenet jelenjen meg a felhasználók számára. A következő lehetőségek közül választhat:
    - **Az alapértelmezett helyreállítási üzenet és URL-cím használata**
    - **Üres helyreállítási üzenet és URL-cím használata**
    - **Egyéni helyreállítási üzenet**
    - **Egyéni helyreállítási URL**

### <a name="bitlocker-fixed-data-drive-settings"></a>Rögzített adatmeghajtók BitLocker-beállításai

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

**Beállítások**:

- **Írási hozzáférés BitLockerrel nem védett rögzített adatmeghajtóhoz**: **Letiltás** értékre állítva csak olvasási hozzáférést adhat a BitLocker által nem védett adatmeghajtókhoz. **Nincs konfigurálva** (alapértelmezett) értékre állítva olvasási és írási hozzáférést ad a BitLocker által nem védett adatmeghajtókhoz.
- **Rögzített meghajtó helyreállítása**: Ennek a beállításnak az **engedélyezésével** vezérelheti, hogyan állíthatók helyre a BitLocker által védett rögzített meghajtók, ha nem állnak rendelkezésre az indításhoz szükséges információk. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót.
  - **Adat-helyreállítási ügynök**: **Letilthatja** az adat-helyreállítási ügynök használatát a BitLocker által védett rögzített meghajtók házirendszerkesztőjével. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi az adat-helyreállítási ügynök a BitLocker által védett rögzített meghajtókkal történő használatát.
  - **Helyreállítási jelszó felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 48 jegyű helyreállítási jelszó létrehozását.  
  - **Helyreállítási kulcs felhasználói létrehozása**: Ezzel a beállítással megadhatja, hogy a felhasználók számára engedélyezi, nem engedélyezi vagy kötelezővé teszi-e 256 bites helyreállítási kulcs létrehozását.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Állítsa **Letiltás** értékre, ha nem szeretné, hogy a felhasználók lássák és módosíthassák a helyreállítási beállításokat. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók láthatják és módosíthatják a helyreállítási beállításokat a BitLocker bekapcsolásakor.
  - **A BitLocker helyreállítási adatainak mentése az AD DS-be**: Ezzel a beállítással **engedélyezheti**, hogy a BitLocker helyreállítási információit az Azure Active Directoryban (AAD) tárolja a rendszer. **Nincs konfigurálva** (alapértelmezett) értékre állítva a rendszer nem tárolja a helyreállítási információkat az AAD-ben.
  - **AD DS-ben tárolt BitLocker helyreállítási adatok**: Ezzel a beállítással adható meg, hogy a BitLocker helyreállítási információi mely részét tárolja a rendszer az Azure Active Directoryban. A következő lehetőségek közül választhat:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Helyreállítási adatok AD DS-be való mentése a BitLocker engedélyezése előtt**: A beállítás **kötelezővé tételével** szabályozhatja, hogy a felhasználók ne tudják bekapcsolni a BitLockert addig, amíg nem sikerült menteni a BitLocker helyreállítási információit az Azure Active Directoryban. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók akkor is bekapcsolhatják a BitLockert, ha a helyreállítási információkat nem sikerült tárolni az Azure Active Directoryban.

### <a name="bitlocker-removable-data-drive-settings"></a>Cserélhető adatmeghajtók BitLocker-beállításai

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

**Beállítások**:

- **Írási hozzáférés BitLockerrel nem védett cserélhető adatmeghajtóhoz**: **Letiltás** értékre állítva csak olvasási hozzáférést adhat a BitLocker által nem védett adatmeghajtókhoz. **Nincs konfigurálva** (alapértelmezett) értékre állítva olvasási és írási hozzáférést ad a BitLocker által nem védett adatmeghajtókhoz.
  - **Írási hozzáférés a más szervezetben konfigurált eszközökhöz**: A **Letiltás** értékkel írási hozzáférést adhat a más szervezetekben konfigurált eszközökhöz. A **Nincs konfigurálva** (alapértelmezett) érték letiltja az írási hozzáférést.

## <a name="windows-defender-exploit-guard"></a>Windows Defender – biztonsági rés kiaknázása elleni védelem

A következő Windows 10-kiadásokon támogatott:

- Otthoni
- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

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

A biztonsági rés kiaknázása elleni védelem engedélyezéséhez hozzon létre egy XML-fájlt, amely a rendszer és az alkalmazások kockázatcsökkentésének kívánt beállításait tartalmazza. Két lehetőség érhető el:

 1. PowerShell: Egy vagy több Get-ProcessMitigation, Set-ProcessMitigation és ConvertTo-ProcessMitigationPolicy PowerShell-parancsmagot használhat. A parancsmagokkal konfigurálhatja a kockázatcsökkentési beállításokat, és exportálhatja ezek XML-reprezentációját.

 2. A Windows Defender Security Center felhasználói felülete: A Windows Defender Security Centerben kattintson az Alkalmazás- és böngészőszabályozásra, majd a megjelenő képernyő alján keresse meg az Biztonsági rés kiaknázása elleni védelem elemet. Először a Rendszerbeállítások és a Programbeállítások lap használatával konfigurálja a kockázatcsökkentési beállításokat. Ha végzett, a képernyő alján keresse meg az Exportálási beállítások hivatkozást, amellyel exportálhatja ezek XML-reprezentációját.

Letilthatja, hogy a **felhasználók a Biztonsági rés kiaknázása elleni védelem felületét módosítsák**, ha feltölt egy olyan XML-fájlt, amely lehetővé teszi a memória, a vezérlésfolyam és a szabályzatkorlátozások konfigurálását. Az XML-fájlban található beállításokkal megvédheti az alkalmazást a biztonsági rések ellen. A **Nincs konfigurálva** (alapértelmezett) érték nem nyújt egyéni konfigurációt. 

## <a name="windows-defender-application-control"></a>Windows Defender Alkalmazásvezérlés

A következő Windows 10-kiadásokon támogatott:

**Mobileszköz-felügyelet (MDM)**: 
- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

**Csoportházirend-kezelés**: 
- Vállalati

Az **Alkalmazás-ellenőrző kódintegritási szabályzatok** használatával további alkalmazásokat is kiválaszthat, amelyeket a Windows Defender Alkalmazásvezérlés ellenőriz, vagy biztonságosan futtathatónak sorolja be. A Windows-összetevők és a Windows Áruházból származó alkalmazások automatikusan biztonságosan futtathatóként lesznek besorolva.

**Naplózási módban** az alkalmazások nincsenek letiltva. A **naplózási mód** minden eseményt egy ügyfélnaplóban rögzít.

Ha az Alkalmazásvezérlést bekapcsolták, utána csak úgy lehet letiltani, ha a módot **Kényszerítésről** **Naplózási módra** változtatja. Ha a módot **Kényszerítésről** **Nincs konfigurálva** értékre változtatja, akkor az Alkalmazásvezérlés a hozzárendelt eszközökön továbbra is kényszerítve lesz.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

A következő Windows 10-kiadásokon támogatott:

- Vállalati

A Windows Defender Credential Guard a hitelesítő adatok ellopása ellen nyújt védelmet. Úgy különíti el a titkos kulcsokat, hogy csak a jogosult rendszerszoftverek férjenek hozzájuk.

A **Credential Guard** beállításai:

- **Letiltás**: Távolról kikapcsolja a Credential Guardot, ha azt korábban bekapcsolta az **Engedélyezve UEFI-zárolás nélkül** funkcióval.

- **Engedélyezve UEFI-zárolás nélkül**: A Credential Guardot nem lehet letiltani egy távoli beállításkulccsal vagy egy csoportházirenddel.

    > [!NOTE]
    > Ha ezt a beállítást használja, majd később le szeretné tiltani a Credential Guardot, a csoportházirendet **letiltott** állapotra kell állítania, majd törölnie kell az UEFI-konfigurációs adatokat minden számítógépről. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

- **Engedélyezve UEFI-zárolás nélkül**: A Credential Guard távolról letiltható egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, a Windows 10 1511-es vagy újabb verziójának kell futnia.

Ha engedélyezi a Credential Guardot, azzal az alábbi kötelező funkciókat is engedélyezi:

- **Virtualizálás-alapú biztonság** (VBS): A következő újraindítás során lép életbe. A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz.
- **Biztonságos rendszerindítás közvetlen memóriaeléréssel**: Bekapcsolja a VBS-t a biztonságos rendszerindítás és a közvetlen memóriaelérés (DMA) védelmi funkcióival. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.

## <a name="windows-defender-security-center"></a>Windows Defender biztonsági központ

A következő Windows 10-kiadásokon támogatott:

- Otthoni
- Professional
- Munkahelyi
- Vállalati
- Oktatás
- Mobil
- Mobile Enterprise

A Windows Defender biztonsági központ az egyes funkcióktól elkülönített alkalmazásként működik. Az értesítéseket a Műveletközponton keresztül jeleníti meg. Olyan gyűjtőhelyként funkcionál, ahol megtekinthetők az állapotok, és ahol minden funkció esetében elvégezhetők bizonyos beállítások. További információt a [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) dokumentációjában talál.

#### <a name="windows-defender-security-center-app-and-notifications"></a>A Windows Defender biztonsági központ alkalmazás és az értesítések

Letilthatja a felhasználói hozzáférést a Windows Defender biztonsági központ alkalmazás különböző területeihez. Egy szakasz elrejtése a kapcsolódó értesítéseket is letiltja.

- **Vírusok és veszélyforrások elleni védelem**
- **Eszközteljesítmény és -állapot**
- **Tűzfal és hálózatvédelem**
- **Alkalmazás- és böngészővezérlés**
- **Családi beállítások**
- **Az alkalmazás megjelenített területeihez kapcsolódó értesítések**: Annak kiválasztása, hogy mely értesítések jelenjenek meg a végfelhasználók számára. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső összefoglalói, például a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül.

#### <a name="it-contact-information"></a>Az informatikai szolgálat kapcsolattartási adatai

Adja meg az informatikai szolgálat azon elérhetőségeit, amelyek megjelennek majd a Windows Defender biztonsági központ alkalmazásban és az alkalmazásértesítésekben. Az alábbi lehetőségek közül választhat: **Az alkalmazásban és az értesítésekben is jelenjen meg**, **Csak az alkalmazásban jelenjen meg**, **Csak az értesítésekben jelenjen meg** és **Ne jelenjen meg**. Adja meg az **IT-szervezet nevét**, és az alábbi kapcsolatfelvételi lehetőségek közül legalább egyet:

- **IT-részleg telefonszáma vagy Skype-elérhetősége**
- **IT-részleg e-mail címe**
- **Informatikai támogatási webhely URL-címe**

## <a name="local-device-security-options"></a>Helyi eszközbiztonsági beállítások

A következő Windows 10-kiadásokon támogatott:
 
- Otthoni
- Professional
- Munkahelyi
- Vállalati
- Oktatás

Ezekkel a beállításokkal konfigurálhatja a Windows 10-eszközök helyi biztonsági beállításait.

### <a name="accounts"></a>Fiókok

- **Új Microsoft-fiókok hozzáadása**: A **Letiltás** lehetőséggel megakadályozhatja, hogy a felhasználók új Microsoft-fiókokat adjanak hozzá az eszközhöz. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók használhatnak Microsoft-fiókokat az eszközön.
- **Távoli bejelentkezés jelszó nélkül**: Az **Engedélyezés** beállítással az üres jelszóval rendelkező helyi fiókok bejelentkezhetnek az eszköz billentyűzetével. A **Nincs konfigurálva** (alapértelmezett) értékkel az üres jelszóval rendelkező helyi fiókok nem csak a fizikai eszközön jelentkezhetnek be.

#### <a name="admin"></a>Felügyelet

- **Helyi rendszergazdai fiók**: **Engedélyezve** értékre állítva engedélyezheti a helyi rendszergazdai fiókot. A **Nincs konfigurálva** (alapértelmezett) értékkel letilthatja a helyi rendszergazdai fiókot.
- **Rendszergazdai fiók átnevezése**: Adjon meg egy másik fióknevet, amelyet társíthat a rendszergazdai fiók biztonsági azonosítójához.

#### <a name="guest"></a>Vendég

- **Vendégfiók**: **Engedélyezve** értékre állítva engedélyezheti a helyi vendégfiókot. A **Nincs konfigurálva** (alapértelmezett) értékkel letilthatja a helyi vendégfiókot.
- **Vendégfiók átnevezése**: Adjon meg egy másik fióknevet, amelyet társíthat a vendégfiók biztonsági azonosítójához.

### <a name="devices"></a>Eszközök

- **Eszköz dokkolásának megszüntetése bejelentkezés nélkül**: **Letiltás** értékre állítva a felhasználók a dokkolt hordozható eszközök fizikai kiadógombjával szüntethetik meg biztonságosan az eszköz dokkolását. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználóknak be kell jelentkezniük az eszközbe, és engedélyt kell kapniuk az eszköz dokkolásának megszüntetéséhez.
- **Nyomtató-illesztőprogramok telepítése a megosztott nyomtatók számára**: **Engedélyezve** értékre állítva bármely felhasználó telepítheti a megosztott nyomtatókhoz való csatlakozáskor a nyomtató-illesztőprogramokat. **Nincs konfigurálva** (alapértelmezett) értékre állítva csak a rendszergazdák telepíthetik a megosztott nyomtatókhoz való csatlakozáskor a nyomtató-illesztőprogramok telepítését.
- **CD-ROM-hozzáférés korlátozása a helyi aktív felhasználókra**: Ha a beállítás **engedélyezve** van, csak az interaktív módon bejelentkezett felhasználók használhatják a CD-ROM-okat. Ha a házirend engedélyezve van, és nincs interaktív módon bejelentkezett felhasználó, a CD-ROM-hoz a hálózaton keresztül lehet hozzáférni. **Nincs konfigurálva** (alapértelmezett) értékre állítva bárki hozzáférhet a CD-ROM-hoz.
- **Cserélhető adathordozó formázása és kiadása**: Megadhatja, ki formázhat és adhat ki cserélhető NTFS-adathordozókat:
  - **Nincs konfigurálva**
  - **Rendszergazdák**
  - **Rendszergazdák és kiemelt felhasználók**
  - **Rendszergazdák és interaktív felhasználók**

### <a name="interactive-logon"></a>Interaktív bejelentkezés

- **Ennyi perc inaktivitás a zárolási képernyőn a képernyővédő aktiválása előtt**: Megadhatja az interaktív asztal bejelentkezési képernyőjén töltött inaktív percek maximum számát, mielőtt elindul a képernyővédő.
- **CTRL+ALT+DEL billentyűkombináció a bejelentkezéshez**: **Engedélyezés** értékre állítva nem kötelező a felhasználók számára a CTRL+ALT+DEL billentyűkombináció lenyomása. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók csak a CTRL+ALT+DEL billentyűkombináció lenyomásával jelentkezhetnek be a Windowsba.
- **Viselkedés intelligens kártya eltávolításakor**: Meghatározza, hogy mi történik, ha egy bejelentkezett felhasználó intelligens kártyáját eltávolítják az intelligenskártya-olvasóból. A választható lehetőségek:

  - **Munkaállomás zárolása**: Az intelligens kártya eltávolítása zárolja a munkaállomást. Ez a beállítás lehetővé teszi a felhasználóknak, hogy elhagyják a helyiséget, magukkal vigyék az intelligens kártyájukat, és továbbra is fenntartsák védett munkamenetüket.
  - **Kijelentkezés kényszerítése**: Az intelligens kártya eltávolítása automatikusan kijelentkezteti a felhasználót.
  - **Munkamenet szétkapcsolása távoli asztali szolgáltatás esetén**: Az intelligens kártya eltávolítása a felhasználó kijelentkeztetése nélkül kapcsolja szét a munkamenetet. Ez a beállítás lehetővé teszi, hogy a felhasználó az intelligens kártya újbóli beillesztésével később, vagy más intelligenskártya-olvasóval felszerelt gépnél újbóli bejelentkezés nélkül folytathassa a munkamenetet. Helyi munkamenet esetén ez a szabályzat pontosan úgy működik, mint a Munkaállomás zárolása.

    A [LocalPoliciesSecurity-beállítások](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) című témakörben további információt találhat.

#### <a name="display"></a>Megjelenítés

- **Felhasználói adatok a zárolási képernyőn**: A lezárt munkamenetek során megjelenített felhasználói adatokat konfigurálja. Ha nincs konfigurálva, a felhasználó megjelenített neve, a tartomány és a felhasználónév látható.
  - **Nincs konfigurálva**
  - **Felhasználó megjelenített neve, tartomány- és felhasználónév**
  - **Csak a felhasználó megjelenített neve**
  - **Ne jelenjenek meg a felhasználói adatok**
- **Utolsó bejelentkezett felhasználó elrejtése**: Az **Engedélyezés** értékkel elrejtheti a felhasználónevet. A **Nincs konfigurálva** (alapértelmezett) értékkel megjelenítheti a felhasználónevet.
- **Felhasználónév elrejtése a bejelentkezéskor**: Az **Engedélyezés** értékkel elrejtheti a felhasználónevet. A **Nincs konfigurálva** (alapértelmezett) értékkel megjelenítheti a felhasználónevet.
- **Bejelentkezési üzenet címe:** A bejelentkező felhasználók számára megjelenő üzenet címe.
- **Bejelentkezési üzenet szövege:** A bejelentkező felhasználók számára megjelenő üzenet szövege.

### <a name="network-access-and-security"></a>Hálózati hozzáférés és biztonság

- **Névtelen hozzáférés nevesített csövekhez és megosztásokhoz**: **Nem konfigurált** (alapértelmezett) módban korlátozza a névtelen hozzáférést a megosztási és nevesített csövekre vonatkozó beállításokhoz. A névtelenül megadható beállításokra vonatkozik.
- **SAM-fiókok névtelen számbavétele**: **Engedélyezi** a névtelen felhasználók számára a SAM-fiókok számbavételét. A Windows engedélyezi a névtelen felhasználók számára a tartományfiókok és hálózati megosztások enumerálását.
- **SAM-fiókok és -megosztások névtelen számbavétele**: **Nem konfigurált** (alapértelmezett) állapot esetén a névtelen felhasználók számba vehetik a tartományi fiókok és hálózati megosztások neveit. A SAM-fiókok és -megosztások névtelen számbavételének megakadályozásához állítsa **Letilt** értékre.
- **A LAN Manager üzenetkivonatának tárolása jelszómódosításkor**: Amikor legközelebb módosítja a jelszót, **Engedélyezze** a LAN Manager (LM) számára az új jelszó üzenetkivonatának tárolását. **Nincs konfigurálva** (alapértelmezett) érték esetén az üzenetkivonat nem tárolódik.
- **PKU2U hitelesítési kérelmek**: **Tiltsa le** az online azonosító adatok használatához az eszközre érkező PKU2U hitelesítési kérelmeket. **Nem konfigurált** (alapértelmezett) érték esetén ezek a kérelmek engedélyezve vannak.
- **A SAM-re érkező távoli RPC-kapcsolatok korlátozása**: **Engedélyezze** az alapértelmezett Security Descriptor Definition Language-karakterláncnak, hogy megtagadhassa a felhasználók és csoportok SAM felé intézett távoli hívásait. **Nem konfigurált** (alapértelmezett) érték esetén a Security Descriptor Definition Language-karakterlánc engedélyezi a felhasználók és csoportok SAM felé intézett távoli hívásait.
  - **Biztonsági leíró**

### <a name="recovery-console-and-shutdown"></a>Helyreállítási konzol és leállítás

- **A virtuális memória lapozófájljának törlése leállításkor**: **Engedélyezés** értékre állítva törli a virtuális memória lapozófájlját az eszköz leállításakor. A **Nincs konfigurálva** érték nem törli a virtuális memóriát.
- **Leállítás bejelentkezés nélkül**: A **Letiltás** érték elrejti a Leállítás lehetőséget a Windows bejelentkezési képernyőjén. A felhasználóknak a leállítás előtt be kell jelentkezniük az eszközbe. **Nincs konfigurálva** (alapértelmezett) értékkel a felhasználók leállíthatják az eszközt a Windows bejelentkezési képernyőjén.

### <a name="user-account-control"></a>Felhasználói fiókok felügyelete

- **UIA-integritás biztonságos hely nélkül**: **Engedélyezés** értékre állítva a fájlrendszer biztonságos helyein található alkalmazások csak UIAccess integritási szinttel futtathatók. **Nincs konfigurálva** (alapértelmezett) értékkel az alkalmazások akkor is futtathatók UIAccess integritási szinttel, ha a fájlrendszer nem biztonságos helyein találhatók.
- **Fájl- és beállításjegyzékbeli írási hibák virtualizálása felhasználónkénti helyekre**: **Letiltás** értékre állítva az alkalmazás írási hibái a futási időben meghatározott beállításjegyzékbeli és fájlrendszerbeli felhasználói helyekre lesznek átirányítva. **Nincs konfigurálva** (alapértelmezett) értékkel a védett helyre adatokat író alkalmazások hibába ütköznek.
- **Csak az aláírt és érvényesített végrehajtható fájlok jogosultságszintjének emelése**: **Engedélyezve** értékkel kényszerítheti a PKI-tanúsítványlánc érvényesítését egy végrehajtható fájlhoz, mielőtt az futhatna. **Nincs konfigurálva** (alapértelmezett) értékkel nem kényszeríti a PKI-tanúsítványlánc érvényesítését egy végrehajtható fájlhoz, mielőtt az futhatna.

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
- **Jogosultságszint-emelési kérések átirányítása a felhasználó interaktív asztalára**: **Engedélyezheti** minden jogosultságszint-emelési kéréshez, hogy az interaktív felhasználó asztalára legyenek irányítva a biztonságos asztal helyett. A rendszer a rendszergazdákra és az általános jogú felhasználókra vonatkozó kérések viselkedését szabályzó házirend-beállításokat alkalmazza. A **Nincs konfigurálva** (alapértelmezett) értékre állítva minden jogosultságszint-emelési kérés a biztonságos asztalra lesz irányítva a rendszergazdákra és szabványos felhasználókra vonatkozó, a kérések viselkedését szabályzó házirend-beállításoktól függetlenül.
- **Jogosultságszint-emelési kérések alkalmazástelepítéshez**: **Letiltás** értékre állítva a rendszer nem észleli az alkalmazástelepítési csomagokat, és nem kéri azok jogosultságszint-emelését. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a rendszer rendszergazdai felhasználónevet és jelszót kér a felhasználótól, amikor egy alkalmazástelepítési csomag emelt szintű jogosultságot igényel.
- **UIA jogosultságszint-emelési kérés biztonságos asztal nélkül**: **Engedélyezés** értékre állítva az alkalmazások kérhetik a UIAccess jogosultság emelését a biztonsági asztal használata nélkül. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a jogosultságszint-emelési kérések egy biztonsági asztalt használnak.

#### <a name="admin-approval-mode-settings"></a>A rendszergazdai engedélyezéses mód beállításai

- **Rendszergazdai engedélyezéses mód a beépített rendszergazdához**: **Engedélyezett** értékre állítva a beépített rendszergazdai fiók használhatja a rendszergazdai engedélyezéses módot. A jogosultságszint-emelést igénylő műveletek felhasználói jóváhagyást kérnek. A **Nincs konfigurálva** (alapértelmezett) érték minden alkalmazást teljes rendszergazdai jogosultságokkal futtat.
- **Minden rendszergazda futtatása rendszergazdai engedélyezéses módban**: **Letiltás** értékre állítva letilthatja a rendszergazdai engedélyezéses módot és az összes kapcsolódó UAC-házirendbeállítást. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a rendszergazdai engedélyezéses módot.

### <a name="microsoft-network-client"></a>Microsoft hálózati ügyfél

- **Kommunikáció digitális aláírása (ha a kiszolgáló egyetért)**: Meghatározza, hogy az SMB-ügyfél SMB-csomagok aláírását egyezteti-e. Ha ez a beállítás **Nincs konfigurálva**, vagy engedélyezve van (ez az alapértelmezés), a Microsoft hálózati ügyfél a kiszolgálótól a munkamenet beállításakor az SMB-csomagok aláírását kéri. Ha a csomagaláírás engedélyezve van a kiszolgálón, a csomagaláírás egyeztetése megkezdődik. Ha ez a szabályzat **le van tiltva**, az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Titkosítatlan jelszó küldése külső SMB-kiszolgálóknak**: Ha ez a beállítás **engedélyezve van**, a Server Message Block- (SMB-) átirányító egyszerű szöveges jelszavakat küldhet az olyan, nem Microsoftos SMB-kiszolgálóknak, amelyek nem támogatják a hitelesítés közbeni jelszótitkosítást. A **Nincs konfigurálva** (alapértelmezett) értékkel a jelszavak titkosítva vannak.

### <a name="microsoft-network-server"></a>Microsoft hálózati kiszolgáló

- **Kommunikáció digitális aláírása (ha az ügyfél egyetért)**: Meghatározza, hogy az SMB-kiszolgáló egyezteti-e az SMB-csomagok aláírását az ezt kérő ügyfelekkel. **Engedélyezés** értékre állítva a Microsoft hálózati kiszolgáló egyezteti az SMB-csomagok aláírását az ügyfél kérése szerint. Ez azt jelenti, hogy ha a csomagaláírás engedélyezve van az ügyfélnél, a csomagaláírás egyeztetése megkezdődik. Ha ez a beállítás **Nem konfigurált** állapotú vagy le van tiltva (alapértelmezett), akkor az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Kommunikáció digitális aláírása (mindig)**: Meghatározza, hogy a csomagaláírás kötelező-e az SMB-kiszolgáló-összetevő számára. **Engedélyezés** értékre állítva a Microsoft hálózati kiszolgáló nem kommunikál a Microsoft hálózati ügyféllel, hacsak az ügyfél bele nem egyezik az SMB-csomagok aláírásába. Ha ez a beállítás **Nincs konfigurálva** vagy le van tiltva (alapértelmezett), akkor az SMB-csomagok aláírásának egyeztetése megkezdődik az ügyfél és a kiszolgáló között.

## <a name="next-steps"></a>További lépések

Ha a profilt csoportokhoz szeretné rendelni, az [Eszközprofilok hozzárendelése](device-profile-assign.md) című cikkben talál további információt.

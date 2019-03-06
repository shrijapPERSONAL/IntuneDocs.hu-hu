---
title: Védelmi beállítások Windows 10 rendszerű eszközökhöz a Microsoft Intune – Azure |} A Microsoft Docs
description: A Microsot Intune-ban, Windows 10-eszközökön az Endpoint Protection-beállítások használatával vagy konfigurálásával engedélyezheti a Windows Defender funkcióit, így az alkalmazásőrt, a tűzfalat, a SmartScreent, a titkosítást és a BitLockert, a biztonsági rés kiaknázása elleni védelmet, az alkalmazásvezérlést, a biztonsági központot és a helyi eszközök biztonságát.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: db5c0053fce35f6a441c60185f4a16d894e38139
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391476"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>A Windows 10 (és újabb verziók) beállítások az Intune-eszközök védelméhez

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune az eszközök védelme érdekében számos beállításokat tartalmaz. Ez a cikk bemutatja az összes beállítás engedélyezheti és konfigurálhatja a Windows 10-es és újabb eszközökre. Ezek a beállítások az endpoint protection konfigurációs profilban az Intune-ban biztonság szabályozásához, beleértve a BitLocker és a Windows Defender jönnek létre.

A Windows Defender víruskereső beállítása: [eszközkorlátozások Windows 10-es](device-restrictions-windows-10.md#windows-defender-antivirus).

## <a name="before-you-begin"></a>Előkészületek

[Az endpoint protection eszközkonfigurációs profil létrehozása](endpoint-protection-configure.md).

## <a name="windows-defender-application-guard"></a>Windows Defender alkalmazásőr

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Professional

A Microsoft Edge használata közben a Windows Defender alkalmazásőr megvédi a környezetét az olyan webhelyektől, amelyek nincsenek megbízhatóként meghatározva a szervezetében. Amikor a felhasználók a webhelyeket, amely nem szerepel a elkülönített hálózat határát, a helyek nyissa meg a Hyper-V virtuális böngészési munkamenetben. Megbízható helyek határozzák meg hálózati határok, amely megtörténik az eszköz konfigurálása a.

Az Alkalmazásőr csak a 64 bites Windows 10-eszközöknél érhető el. Ennek a profilnak a használatával telepítve lesz az Alkalmazásőr aktiválásához szükséges Win32-összetevő.

- **Alkalmazásőr**: **Az Edge-hez engedélyezett** , kapcsolja be ezt a szolgáltatást, amely nem megbízható webhelyek egy Hyper-V virtualizált böngészési tárolóban nyitja meg. **Nincs konfigurálva** (alapértelmezett) azt jelenti, hogy minden hely (megbízható és nem megbízható) megnyitja az eszközön.
- **A vágólap viselkedése**: Válassza ki a helyi számítógép és az Alkalmazásőr virtuális böngészőjében között milyen másolási és beillesztési műveletek engedélyezettek.
- **Vállalati webhelyeken lévő külső tartalom**: **Blokk** betöltését nem jóváhagyott webhelyekről származó tartalom. A **Nincs konfigurálva** (alapértelmezett) érték azt jelenti, hogy a nem vállalati webhelyek megnyílhatnak az eszközön.
- **Nyomtatás virtuális böngészőből**: Válasszon **engedélyezése** Igen PDF-, XPS, helyi, és a hálózati nyomtatók a a virtuális böngészőben megjelenő tartalom nyomtatását is. A **Nincs konfigurálva** (alapértelmezett) érték letilt minden nyomtatási funkciót.
- **Naplók gyűjtése**: **Lehetővé teszi** az alkalmazásőr virtuális böngészési munkamenetében előforduló események naplóinak összegyűjtése. A **Nincs konfigurálva** (alapértelmezett) érték nem gyűjt naplókat a böngészési munkamenetben.
- **Felhasználó által létrehozott böngészési adatok megtartása**: **Lehetővé teszi** menti a felhasználói adatok (például jelszavak, Kedvencek és cookie-k) az Alkalmazásőr virtuális böngészési munkamenet során létrehozott. A **Nincs konfigurálva** (alapértelmezett) érték elveti a felhasználó által letöltött fájlokat és adatokat az eszköz újraindulásakor vagy a felhasználó kijelentkezésekor.
- **Grafikus gyorsítás**: Válasszon **engedélyezése** grafikai igényű webhelyeket és gyorsabb videó betöltése egy virtuális grafikai feldolgozóegységhez való hozzáférést is. A **Nincs konfigurálva** (alapértelmezett) érték az eszköz CPU-ját használja a grafikus feladatokhoz, és nem a virtuális grafikus feldolgozóegységet.
- **Fájlok letöltése a gazdagép fájlrendszerébe**: **Engedélyezése** így a felhasználók letölteni a fájlokat a virtualizált böngészőből a gazdagép operációs rendszeréhez. A **Nincs konfigurálva** (alapértelmezett) érték a fájlokat helyi szinten, az eszközön tárolja, és nem tölti le őket a gazdarendszerbe.

## <a name="windows-defender-firewall"></a>Windows Defender-tűzfal

A következő Windows 10-kiadásokon támogatott:
- Otthoni
- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
- Mobile Enterprise

### <a name="global-settings"></a>Globális beállítások

Ezek a beállítások minden hálózattípusnál alkalmazhatók.

- **File Transfer Protocol**: **Blokk** állapot-nyilvántartó FTP letiltása. Ha a **Nincs konfigurálva** (alapértelmezett) érték van beállítva, a tűzfal szűrést végez az állapot-nyilvántartó FTP-re a másodlagos kapcsolatok engedélyezéséhez.
- **Biztonsági társítás üresjárati ideje törlés előtt**: Biztonsági társítások törölve lesznek az észlelt nincs hálózati forgalom *n* másodperc. Adja meg másodpercben az üresjárati időt.
- **Előmegosztott kulcsok kódolása**: Válasszon **engedélyezése** használatához az előmegosztott kulcsok kódolása az UTF-8 használatával. A **Nincs konfigurálva** (alapértelmezett) érték a helyi tárolóértéket használja.
- **IPsec-kivételek**: Az IPsec, alól mentesülő forgalomtípusok megadása többek között:
  - **Szomszédfelderítési IPv6 ICMP-típuskódok**
  - **ICMP**
  - **Útválasztó-felderítési IPv6 ICMP-típuskódok**
  - **IPv4-es és IPv6-os DHCP hálózati forgalom**
- **Visszavont tanúsítványok listájának ellenőrzése**: Válassza ki, hogyan ellenőrzi az eszköz, a visszavont tanúsítványok listáját. Lehetőségek a következők **CRL-ellenőrzés letiltása**, **sikertelen CRL-ellenőrzés csak visszavont tanúsítvány**, és **sikertelen CRL-ellenőrzés bármilyen hibánál**.
- **Hitelesítési készlet kulcsmodulonként megfelelő**: **Engedélyezése** , a kulcskezelő modulok figyelmen kívül kell hagynia csak a hitelesítési csomagokat tartalmaz, amelyek nem támogatják. **Ha nincs konfigurálva**, a kulcsmoduloknak kötelező figyelmen kívül hagyniuk a teljes hitelesítési készletet, ha nem támogatják a készletben megadott összes hitelesítési csomagot.
- **Csomagok várólistára helyezése**: Adja meg, a fogadó oldali skálázás szoftverek miként legyen engedélyezve a titkosított fogadás és az egyszerű szöveges továbbítás számára az IPsec alagutas átjáró használata esetén. Ezzel a beállítással ellenőrzi, hogy a csomagsorrend megőrzése.

### <a name="network-settings"></a>Hálózati beállítások

Ezek a beállítások meghatározott hálózattípusokra vonatkoznak. Ilyen többek között a **Tartományi (munkahelyi) hálózat**, a **Magánhálózat (észlelhető)** és a **Nyilvános (nem észlelhető) hálózat**.

#### <a name="general-settings"></a>Általános beállítások

- **Windows Defender-tűzfal**: Válasszon **engedélyezése** a tűzfal és a speciális biztonsági bekapcsolása. A **Nincs konfigurálva** (alapértelmezett) beállítással a házirendbeállításokból függetlenül minden hálózati forgalom engedélyezve van.
- **Rejtett üzemmód**: **Blokk** a tűzfal rejtett üzemmódban. A rejtett üzemmód tiltásnak a beállítása az **IPsec-et használó csomagok mentességének** letiltását is lehetővé teszi. A **Nincs konfigurálva** (alapértelmezett) érték rejtett üzemmódban működteti a tűzfalat, ami segít megelőzni az ellenőrzési kérelmekre adott válaszokat.
- **Védett**: **Blokk** kapcsolja ki ezt a szolgáltatást. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást. Ha a beállítás és a Windows Defender-tűzfal be van kapcsolva, minden bejövő forgalom le van tiltva az egyéb házirend-beállításoktól függetlenül.
- **Egyedi küldésű válaszok a csoportos küldésű szórásokra**: Ha a beállítása **blokk**, egyedi küldésű válaszok a csoportos küldésű szórásokra letilt. Csoportos küldésű vagy szórási üzenetekre általában nem kívánatos egyedi küldésű válaszokat kapni, Ezek a válaszok szolgáltatásmegtagadási (DOS) támadásokkal szemben, vagy egy támadó mintavételi egy ismert aktív számítógépbe próbál adhatja meg. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást.
- **Bejövő értesítések**: Ha a beállítása **blokk**, azt elrejti értesítések küldéséhez felhasználók számára, ha az alkalmazás figyeljen egy portot az le van tiltva. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a beállítást, és megjeleníthet értesítéseket a felhasználóknak, amikor le van tiltva, hogy egy alkalmazás figyeljen egy portot.
- **Alapértelmezett művelet bejövő kapcsolatokhoz**: Ha a beállítása **blokk**, a tűzfal alapértelmezett művelet bejövő kapcsolatokat nem futtathatók. A **Nincs konfigurálva** (alapértelmezett) értékre állítva az alapértelmezett tűzfalművelet elindul a bejövő kapcsolatoknál.

#### <a name="rule-merging"></a>Szabályegyesítés

- **Engedélyezett alkalmazás Windows Defender-tűzfal-szabályokat a helyi tároló**: Válasszon **engedélyezése** tűzfalszabályok a helyi tároló alkalmazandó, így Ön elfogadtatni és érvényesíteni. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló alkalmazásának engedélyezett tűzfalszabályait.
- **Globális Windows Defender-tűzfal portszabályok a helyi tároló**: Válasszon **engedélyezése** , a helyi tároló elfogadtatni és érvényesíteni kívánt globális tűzfalszabályainak alkalmazása. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló globális portjának engedélyezett tűzfalszabályait.
- **A Windows Defender-tűzfalszabályok a helyi tároló**: Válasszon **engedélyezése** , a helyi tároló elfogadandó és érvényesítendő tűzfalszabályainak alkalmazása. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló tűzfalszabályait.
- **A helyi tároló IPsec-szabályai**: Válasszon **engedélyezése** , függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától, a helyi tároló kapcsolatbiztonsági szabályainak alkalmazása. A **Nincs konfigurálva** (alapértelmezett) érték figyelmen kívül hagyja és nem kényszeríti a helyi tároló kapcsolatbiztonsági szabályait, függetlenül a sémától és a kapcsolatbiztonsági szabály verziójától.

## <a name="windows-defender-smartscreen-settings"></a>A Windows Defender SmartScreen beállításai

A következő, Microsoft Edge böngészővel rendelkező Windows 10- kiadásokon támogatott:
- Otthoni
- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
- Mobile Enterprise

**Beállítások**:

- **SmartScreen használata alkalmazások és fájlok esetén**: **Engedélyezése** Windows SmartScreen használata fájlok, és alkalmazások futtatásához. A SmartScreen egy felhőalapú, adathalászat elleni és kártevőirtó összetevő. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a SmartScreent.
- **Nem ellenőrzött fájlok futtatása**: **Blokk** futtatását, fájlok, amelyek végfelhasználók által a Windows SmartScreen még nem jóvá lett hagyva. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót, és engedélyezi a végfelhasználók számára, hogy nem ellenőrzött fájlokat futtassanak.

## <a name="windows-encryption"></a>Windows Encryption

### <a name="windows-settings"></a>Windowsos beállítások

A következő Windows 10-kiadásokon támogatott:

- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
- Mobile Enterprise

**Beállítások**:

- **Eszközök titkosítása**: **Szükséges** az eszköztitkosítás engedélyezése a felhasználóknak. A Windows kiadásától és a rendszerkonfigurációtól függően a rendszer a következőket kérheti a felhasználóktól:  
  - Megerősítés arról, hogy nincs engedélyezve másik szolgáltató titkosítási funkciója
  - A BitLocker meghajtótitkosítás kikapcsolása, majd a Bitlocker újbóli bekapcsolása
    
    Az eszköz ugyanis instabillá válhat, ha a windowsos titkosítást úgy kapcsolják be, hogy közben egy másik titkosítási módszer aktív marad. 
- **(Csak mobil) tárolókártya titkosítása**: **Szükséges** , minden cserélhető tárolókártyát titkosítani fog a eszköz által használt. A **Nincs konfigurálva** (alapértelmezett) érték nem teszi kötelezővé a tárolókártya titkosítását, és nem kéri a felhasználót, hogy kapcsolja be. Ez a beállítás csak Windows 10 Mobile-eszközökre vonatkozik.

### <a name="bitlocker-base-settings"></a>BitLocker-alapbeállítások

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- mobil
- Mobile Enterprise
- Professional

Az alapbeállítások minden típusú adatmeghajtóra vonatkozó univerzális BitLocker-beállítások. Ezek a beállítások szabályozzák a végfelhasználók által a különböző típusú adatmeghajtókon módosítható meghajtótitkosítási feladatokat vagy konfigurációs beállításokat.

- **Figyelmeztetés egyéb lemeztitkosításra**: Válassza ki **blokk** figyelmeztető üzenet letiltása, ha egy másik lemez titkosítási szolgáltatás az eszközön. A **Nincs konfigurálva** (alapértelmezett) értékre állítva megjelenhetnek a figyelmeztetések.
    - **Engedélyezze a titkosítást az Azure AD Join során általános jogú felhasználók**: Ha úgy dönt **engedélyezése**, normál felhasználók/nem rendszergazda engedélyezheti a BitLocker-titkosítást, amikor a felhasználó bejelentkezett. Ez a beállítás csak az Azure Active Directoryhoz csatlakoztatott (Azure beállítás) eszközökre vonatkozik. **Nincs konfigurálva** csak lehetővé teszi, hogy rendszergazdái engedélyezhetik a BitLocker-titkosítást az eszközön.
      
      Ez a beállítás csak az Azure Active Directoryhoz csatlakoztatott (Azure beállítás) eszközökre vonatkozik. Azt is megköveteli, hogy a **figyelmeztetés egyéb lemeztitkosításra** beállítást megadni **blokk**.
- **Titkosítási módszerek konfigurálása**: **Engedélyezése** ezt a beállítást, az operációs rendszer, az adat- és cserélhető meghajtók titkosítási algoritmusok konfigurálásához. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a BitLocker az XTS-AES 128 bites funkciót használja alapértelmezett titkosítási módszerként, vagy egy telepítési szkript által meghatározott titkosítási módszert.
  - **Operációsrendszer-meghajtók titkosítása**: Válassza ki az operációsrendszer-meghajtók titkosítási módszer kiválasztására szolgál. Javasoljuk az XTS-AES algoritmus használatát.
  - **Rögzített adatmeghajtók titkosítása**: A rögzített (beépített) adatmeghajtókhoz titkosítási módszert választania. Javasoljuk az XTS-AES algoritmus használatát.
  - **Cserélhető adatmeghajtók titkosítása**: Válassza ki a cserélhető adatmeghajtók titkosítási módszer kiválasztására szolgál. Ha a cserélhető meghajtót olyan eszközökkel is használja, amelyeken nem Windows 10 operációs rendszer fut, az AES-CBC algoritmus használatát javasoljuk.

### <a name="bitlocker-os-drive-settings"></a>Operációsrendszer-meghajtók BitLocker-beállításai
A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- mobil
- Mobile Enterprise
- Professional

Ezek a beállítások kifejezetten az operációsrendszer-adatmeghajtókra érvényesek.

- **További hitelesítés indításkor**: Válassza ki **megkövetelése** konfigurálhatja a hitelesítési követelmények, a számítógép indításakor, beleértve a platformmegbízhatósági modul (TPM) használatát. Válassza a **Nincs konfigurálva** (alapértelmezett) értéket, ha csak az alapszintű beállításokat szeretné konfigurálni a TPM-mel rendelkező eszközökön.
  - **BitLocker nem kompatibilis TPM-lapkával**: **Blokk** (letiltása) használatával a BitLocker, amikor egy eszköz nem kompatibilis TPM-lapka. Ha **nincs konfigurálva**, a felhasználók kompatibilis TPM-lapka nélkül használhatják a BitLockert. A BitLockerhez jelszóra vagy indítókulcsra lehet szüksége.
  - **Kompatibilis TPM-indítási**: Engedélyezi, nem engedélyezi, vagy választhat megkövetelése a TPM-lapka.
  - **Kompatibilis TPM-indítási PIN-kód**: Engedélyezi, nem engedélyezése, vagy választhat egy indítási PIN-kód használatát a TPM-lapka igényelnek. Indítási PIN-kód engedélyezéséhez végfelhasználói beavatkozás szükséges. 
  - **Kompatibilis TPM-indítási kulcs**: Válassza ki, lehetővé teszik, nem engedélyezi vagy megkövetelése a TPM-lapkával indítási kulcs használatával. Indítókulcs engedélyezéséhez végfelhasználói beavatkozás szükséges. 
  - **Kompatibilis TPM-indítási kulcs és PIN-kód**: Válassza ki, lehetővé teszik, nem engedélyezi vagy megkövetelése a TPM-lapkával indítókulcs és PIN-kód használatával. Indítókulcs és indítási PIN-kód engedélyezéséhez végfelhasználói beavatkozás szükséges.
- **PIN-kód minimális hossza**: **Engedélyezése** ezzel a beállítással a TPM-indítási PIN-kód minimális hosszának konfigurálása. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók bármilyen, 6 és 20 karakter közötti hosszúságú indítási PIN-kódot megadhatnak.
  - **Karakterek minimális száma**: Az indítási PIN-kód a karakterek számát adja meg a **4**-**20**.
- **Operációsrendszer-meghajtók helyreállítási**: **Engedélyezése** ezzel a beállítással szabályozhatja, hogyan a BitLocker által védett operációsrendszer-meghajtók helyreállítása, ha nem áll rendelkezésre az indításhoz szükséges információk. A **Nincs konfigurálva** (alapértelmezett) értékre állítva az alapértelmezett helyreállítási beállítások támogatva vannak a BitLocker-helyreállításhoz. Alapértelmezés szerint a DRA engedélyezve van, a helyreállítási lehetőségek közül választ a felhasználó, beleértve a helyreállítási jelszó és a helyreállítási kulcsot, és helyreállítási adatok AD DS-ben nem készíteni.
  - **Tanúsítványalapú adat-helyreállítási ügynök**: Ha a beállítása **blokk**, adat-helyreállítási ügynök nem használható együtt a BitLocker által védett operációsrendszer-meghajtók esetében. A beállítás engedélyezéséhez állítsa azt **Nincs konfigurálva** (alapértelmezett) értékre, így használhatók adat-helyreállítási ügynökök a BitLocker által védett operációsrendszer-lemezekkel.
  - **A helyreállítási jelszó felhasználói létrehozása**: Válassza ki, ha a felhasználók engedélyezi, kötelező vagy nem engedélyezett egy 48 jegyű helyreállítási jelszó létrehozása.
  - **Helyreállítási kulcs felhasználói létrehozása**: Válassza ki, ha a felhasználó engedélyezi, kötelező vagy egy 256 bites helyreállítási kulcs létrehozása nem engedélyezett.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Állítsa be **blokk** így a felhasználók nem látják, és a helyreállítási beállítások megváltoztatása. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók láthatják és módosíthatják a helyreállítási beállításokat a BitLocker bekapcsolásakor.
  - **BitLocker helyreállítási adatainak mentése az AD DS**: Válasszon **engedélyezése** a BitLocker helyreállítási információit az Azure Active Directory (AAD) tárolásához. **Nincs konfigurálva** (alapértelmezett) értékre állítva a rendszer nem tárolja a helyreállítási információkat az AAD-ben.
  - **Az AD DS-ben tárolt BitLocker helyreállítási adatok**: Konfigurálja a BitLocker helyreállítási információi mely részeit az Azure ad-ben tárolódnak. A következő lehetőségek közül választhat:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Store helyreállítási adatok AD DS-ben a BitLocker engedélyezése előtt**: **Szükséges** ezt a beállítást, hogy a felhasználók ne tudják bekapcsolni a Bitlockert, kivéve, ha a BitLocker helyreállítási információi nem sikerült menteni az Azure Active Directory (AD). **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy kapcsolja be a Bitlockert, hogy a felhasználók akkor is, ha nem sikerült menteni a helyreállítási információit az Azure ad-ben.
- **Rendszerindítás előtti helyreállítási üzenet és URL-cím**: **Engedélyezése** ezt a beállítást, konfigurálhatja az üzenet és URL-címet, a rendszerindítás előtti kulcsalapú helyreállítási képernyőn jelennek meg. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót.
  - **Rendszerindítás előtti helyreállítási üzenet**: Konfigurálja, hogy a rendszerindítás előtti helyreállítási üzenet jelenik meg, a felhasználóknak. A következő lehetőségek közül választhat:
    - **Az alapértelmezett helyreállítási üzenet és URL-cím használata**
    - **Üres helyreállítási üzenet és URL-cím használata**
    - **Egyéni helyreállítási üzenet**
    - **Egyéni helyreállítási URL**

### <a name="bitlocker-fixed-data-drive-settings"></a>Rögzített adatmeghajtók BitLocker-beállításai

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- mobil
- Mobile Enterprise
- Professional

**Beállítások**:

- **Rögzített adatmeghajtók BitLocker által nem védett írási hozzáférést**: Állítsa be **blokk** a csak olvasási hozzáférést biztosíthat, amelyek nem a BitLocker által védett meghajtók. Amikor **nincs konfigurálva** (alapértelmezett), hogy az olvasási és írási hozzáférés, amelyek nem a BitLocker által védett adatok meghajtókra.
- **Rögzített meghajtó helyreállítása**: **Engedélyezése** a beállításnak a megadásával vezérelheti, hogy a BitLocker által védett rögzített meghajtók helyreállítása, ha nem áll rendelkezésre az indításhoz szükséges információk. A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót.
  - **Adat-helyreállítási ügynök**: **Blokk** a BitLocker által védett adat-helyreállítási megbízott használatának rögzített meghajtók Helyicsoportházirend-szerkesztő. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi az adat-helyreállítási ügynök a BitLocker által védett rögzített meghajtókkal történő használatát.
  - **A helyreállítási jelszó felhasználói létrehozása**: Beállíthatja, hogy a felhasználók engedélyezett, kötelező vagy nem engedélyezett egy 48 jegyű helyreállítási jelszó létrehozása.  
  - **Helyreállítási kulcs felhasználói létrehozása**: Beállíthatja, hogy a felhasználók engedélyezett, kötelező vagy nem engedélyezett egy 256 bites helyreállítási kulcs létrehozásához.
  - **Helyreállítási beállítások a BitLocker konfigurációs varázslójában**: Állítsa be **blokk** így a felhasználók nem látják, és a helyreállítási beállítások megváltoztatása. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók láthatják és módosíthatják a helyreállítási beállításokat a BitLocker bekapcsolásakor.
  - **BitLocker helyreállítási adatainak mentése az Azure Active Directoryhoz**: Válasszon **engedélyezése** a BitLocker helyreállítási adatok tárolására az Azure Active Directoryban (Azure AD). Amikor **nincs konfigurálva** (alapértelmezett), a helyreállítási információk nem tárolja az Azure ad-ben.
  - **Az Azure Active Directoryban tárolt BitLocker helyreállítási adatok**: Konfigurálja a BitLocker helyreállítási információi mely részeit az Azure ad-ben tárolódnak. A választható lehetőségek:
    - **A helyreállítási jelszavak és a kulcscsomagok biztonsági mentése**
    - **Csak a helyreállítási jelszavak biztonsági mentése**
  - **Helyreállítási információk Store az Azure Active Directoryban a BitLocker engedélyezése előtt**: **Szükséges** ezt a beállítást, hogy a felhasználók ne tudják bekapcsolni a Bitlockert, kivéve, ha a BitLocker helyreállítási információi nem sikerült menteni az Azure ad-ben. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy kapcsolja be a Bitlockert, hogy a felhasználók akkor is, ha a helyreállítási információk nem sikerült tárolja az Azure ad-ben.

### <a name="bitlocker-removable-data-drive-settings"></a>Cserélhető adatmeghajtók BitLocker-beállításai

A következő Windows 10-kiadásokon támogatott:

- Vállalati
- Oktatás
- mobil
- Mobile Enterprise
- Professional

**Beállítások**:

- **Cserélhető adatmeghajtók BitLocker által nem védett írási hozzáférést**: Állítsa be **blokk** a csak olvasási hozzáférést biztosíthat, amelyek nem a BitLocker által védett meghajtók. Amikor **nincs konfigurálva** (alapértelmezett), hogy az olvasási és írási hozzáférés, amelyek nem a BitLocker által védett adatok meghajtókra.
  - **Írási hozzáférés a más szervezetben konfigurált eszközökhöz**: **Blokk** írási hozzáférést biztosít a más szervezetben konfigurált eszközökhöz. A **Nincs konfigurálva** (alapértelmezett) érték letiltja az írási hozzáférést.

## <a name="windows-defender-exploit-guard"></a>Windows Defender – biztonsági rés kiaknázása elleni védelem

A következő Windows 10-kiadásokon támogatott:

- Otthoni
- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
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

- **Fájlok és mappák kizárása a támadási felület csökkentésére szolgáló szabályok**: Importálása és hozzáadása a konfigurált szabályok hatálya alól kizárandó helyek listáját.

> [!IMPORTANT]
> Ahhoz, hogy a megfelelő telepítéséhez és futtatásához a LOB-Win32-alkalmazások, a kártevőirtó-beállítások a következő könyvtárait kizárása kell éppen beolvasott:<p>
> **A X64 ügyfélgépek**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **A X86 ügyfélgépek**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

Rosszindulatú alkalmazások és fenyegetések, például zsarolóprogramok ellen védheti értékes adatait.

- **Mappavédelem**: Rosszindulatú alkalmazások által végrehajtott jogosulatlan módosításainak megakadályozása védelme fájlokat és mappákat. **Védett mappákhoz hozzáférő alkalmazások listáját** importálhatja, vagy manuálisan is hozzáadhatja. **További védendő mappák listáját** is hozzáadhatja feltöltéssel, vagy manuálisan is hozzáadhatja őket.

### <a name="network-filtering"></a>Hálózatszűrés

- **Hálózatvédelem**: IP-címek vagy tartományok védelmet biztosít a kimenő kapcsolatok bármely alkalmazásból. A célja a végfelhasználók szembeni hozzáféréssel rendelkező alkalmazások folytathatnak, biztonsági rés kiaknázása elleni futtató helyek és az interneten rosszindulatú tartalmat. Azt is megakadályozza, hogy külső böngészők veszélyes helyek csatlakozik.

  A választható lehetőségek:

  - A **Nincs konfigurálva** (alapértelmezett) érték letiltja a funkciót. Felhasználók és alkalmazások nincsenek letiltva veszélyes tartományokhoz csatlakozzon. A rendszergazdák nem láthatják ezt a tevékenységet, a Windows Defender biztonsági központban.
  - **Engedélyezése** bekapcsolja a hálózatvédelem, és blokkolja-felhasználók és alkalmazások veszélyes tartományokhoz csatlakozzon. A rendszergazdák láthatják ezt a tevékenységet, a Windows Defender biztonsági központban.
  - **Csak naplózás**: Felhasználók és alkalmazások nincsenek letiltva veszélyes tartományokhoz csatlakozzon. A rendszergazdák láthatják ezt a tevékenységet, a Windows Defender biztonsági központban.

  [Defender/EnableNetworkProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

### <a name="exploit-protection"></a>Biztonsági rés kiaknázása elleni védelem

Biztonsági rés kiaknázása elleni védelem használatához hozzon létre egy XML-fájlt, amely tartalmazza azt szeretné, a rendszer- és kockázatcsökkentési beállításokat. Két lehetőség érhető el:

 1. PowerShell: Egy vagy több Get-ProcessMitigation, Set-ProcessMitigation és ConvertTo-ProcessMitigationPolicy PowerShell-parancsmagot használja. A parancsmagokkal konfigurálhatja a kockázatcsökkentési beállításokat, és exportálhatja ezek XML-reprezentációját.

 2. A Windows Defender biztonsági központ felhasználói felülete: A Windows Defender biztonsági központ alkalmazás-és böngészőszabályozás kattintson, és keresse meg a biztonsági rés kiaknázása elleni védelem a megjelenő képernyő alján görgessen. Először a Rendszerbeállítások és a Programbeállítások lap használatával konfigurálja a kockázatcsökkentési beállításokat. Ha végzett, a képernyő alján keresse meg az Exportálási beállítások hivatkozást, amellyel exportálhatja ezek XML-reprezentációját.

Letilthatja, hogy a **felhasználók a Biztonsági rés kiaknázása elleni védelem felületét módosítsák**, ha feltölt egy olyan XML-fájlt, amely lehetővé teszi a memória, a vezérlésfolyam és a szabályzatkorlátozások konfigurálását. Az XML-fájlban található beállításokkal megvédheti az alkalmazást a biztonsági rések ellen. A **Nincs konfigurálva** (alapértelmezett) érték nem nyújt egyéni konfigurációt. 

## <a name="windows-defender-application-control"></a>Windows Defender Alkalmazásvezérlés

A következő Windows 10-kiadásokon támogatott:

**Mobileszköz-felügyelet (MDM)**: 
- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
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

- **Tiltsa le**: Kikapcsolja a Credential Guard távolról, ha azt korábban bekapcsolta az a **engedélyezve UEFI-zárolás nélkül** lehetőséget.

- **UEFI-zárolással engedélyezése**: Credential Guard egy beállításkulcs használatával nem tiltható le távolról, vagy a csoportházirend.

    > [!NOTE]
    > Ha ezt a beállítást használja, majd később le szeretné tiltani a Credential Guardot, a csoportházirendet **letiltott** állapotra kell állítania, majd törölnie kell az UEFI-konfigurációs adatokat minden számítógépről. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

- **Engedélyezés UEFI-zárolás nélkül**: Lehetővé teszi a Credential Guard csoportházirenddel távolról le kell tiltani. Azokon az eszközökön, amelyek ezt a beállítást használják, a Windows 10 1511-es vagy újabb verziójának kell futnia.

Ha engedélyezi a Credential Guardot, azzal az alábbi kötelező funkciókat is engedélyezi:

- **A virtualizálás-alapú biztonsági** (VBS): Kapcsolja be a során a következő újraindításkor. A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz.
- **A biztonságos rendszerindítás, a memória-hozzáférés Directory**: A biztonságos rendszerindítással és közvetlen memória-hozzáférés (DMA) védelmi VBS bekapcsolása. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.

## <a name="windows-defender-security-center"></a>Windows Defender biztonsági központ

A következő Windows 10-kiadásokon támogatott:

- Otthoni
- Professional
- Üzleti
- Vállalati
- Oktatás
- mobil
- Mobile Enterprise

A Windows Defender biztonsági központ az egyes funkcióktól elkülönített alkalmazásként működik. Az értesítéseket a Műveletközponton keresztül jeleníti meg. Gyűjtő vagy egyetlen helyen megnézheti az állapotukat, és futtathat néhány beállítást a minden funkció működik. További információt a [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) dokumentációjában talál.

#### <a name="windows-defender-security-center-app-and-notifications"></a>A Windows Defender biztonsági központ alkalmazás és az értesítések

Letilthatja a felhasználói hozzáférést a Windows Defender biztonsági központ alkalmazás különböző területeihez. Egy szakasz elrejtése a kapcsolódó értesítéseket is letiltja.

- **Vírusok és veszélyforrások elleni védelem**
- **Eszközteljesítmény és -állapot**
- **Tűzfal és hálózatvédelem**
- **Alkalmazás- és böngészővezérlés**
- **Családi beállítások**
- **Alkalmazás megjelenített területeihez kapcsolódó értesítések**: Válassza ki, hogy mely értesítések jelenjenek meg a végfelhasználók számára. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső összefoglalói, például a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül.

#### <a name="it-contact-information"></a>Az informatikai szolgálat kapcsolattartási adatai

Adja meg az informatikai szolgálat azon elérhetőségeit, amelyek megjelennek majd a Windows Defender biztonsági központ alkalmazásban és az alkalmazásértesítésekben. Az alábbi lehetőségek közül választhat: **Az alkalmazásban és az értesítésekben is jelenjen meg**, **Csak az alkalmazásban jelenjen meg**, **Csak az értesítésekben jelenjen meg** és **Ne jelenjen meg**. Adja meg az **IT-szervezet nevét**, és az alábbi kapcsolatfelvételi lehetőségek közül legalább egyet:

- **IT-részleg telefonszáma vagy Skype-elérhetősége**
- **IT-részleg e-mail címe**
- **Informatikai támogatási webhely URL-címe**

## <a name="local-device-security-options"></a>Helyi eszközbiztonsági beállítások

A következő Windows 10-kiadásokon támogatott:
 
- Otthoni
- Professional
- Üzleti
- Vállalati
- Oktatás

Ezekkel a beállításokkal konfigurálhatja a Windows 10-eszközök helyi biztonsági beállításait.

### <a name="accounts"></a>Fiókok

- **Új Microsoft-fiókok hozzáadása**: Állítsa be **blokk** megakadályozza, hogy a felhasználók új Microsoft-fiókok hozzáadásának az eszközön. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók használhatnak Microsoft-fiókokat az eszközön.
- **Távoli bejelentkezés jelszó nélkül**: **Blokk** lehetővé teszi, hogy csak helyi fiókok jelentkezzen be az eszköz billentyűzet üres jelszó mellett. A **Nincs konfigurálva** (alapértelmezett) értékkel az üres jelszóval rendelkező helyi fiókok nem csak a fizikai eszközön jelentkezhetnek be.

#### <a name="admin"></a>rendszergazda

- **Helyi rendszergazdai fiók**: Állítsa be **engedélyezve** , hogy a helyi rendszergazdai fiók. A **Nincs konfigurálva** (alapértelmezett) értékkel letilthatja a helyi rendszergazdai fiókot.
- **Rendszergazdai fiók átnevezése**: Adja meg a rendszergazdai fiók biztonsági azonosítójához (SID) társítani kell egy másik fióknevet.

#### <a name="guest"></a>Vendég

- **Vendégfiók**: Állítsa be **engedélyezve** , hogy a helyi Vendég fiókhoz. A **Nincs konfigurálva** (alapértelmezett) értékkel letilthatja a helyi vendégfiókot.
- **Vendégfiók átnevezése**: Adja meg a Vendég fiók biztonsági azonosítójához (SID) társítani kell egy másik fióknevet.

### <a name="devices"></a>Eszközök

- **Bejelentkezés nélkül az eszköz zárolásának feloldása**: Állítsa be **blokk** így a felhasználók nyomja le a dokkolt hordozható eszközön fizikai kiadása gombra kattintva biztonságosan a az eszköz zárolásának feloldása. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználóknak be kell jelentkezniük az eszközbe, és engedélyt kell kapniuk az eszköz dokkolásának megszüntetéséhez.
- **A megosztott nyomtatók nyomtató-illesztőprogramjainak telepítése**: Amikor **engedélyezve**, bármely felhasználó megosztott nyomtatókhoz való csatlakozás részeként is telepítheti a nyomtató-illesztőprogramot. **Nincs konfigurálva** (alapértelmezett) értékre állítva csak a rendszergazdák telepíthetik a megosztott nyomtatókhoz való csatlakozáskor a nyomtató-illesztőprogramok telepítését.
- **CD-ROM-hozzáférés korlátozása aktív helyi felhasználó**: Amikor **engedélyezve**, csak az interaktív módon bejelentkezett felhasználó a CD-ROM adathordozóhoz használható. Ha a házirend engedélyezve van, és nincs interaktív módon bejelentkezett felhasználó, a CD-ROM-hoz a hálózaton keresztül lehet hozzáférni. **Nincs konfigurálva** (alapértelmezett) értékre állítva bárki hozzáférhet a CD-ROM-hoz.
- **Cserélhető adathordozó formázására és kiadására**: A cserélhető NTFS-adathordozók formázására és kiadására jogosult felhasználók megadása:
  - **Nincs konfigurálva**
  - **Rendszergazdák**
  - **Rendszergazdák és kiemelt felhasználók**
  - **Rendszergazdák és interaktív felhasználók**

### <a name="interactive-logon"></a>Interaktív bejelentkezés

- **Percek száma zárolási képernyőn a képernyőkímélő**: Adja meg a ennyi perc inaktivitás az interaktív asztal bejelentkezési képernyő, mindaddig, amíg a képernyőkímélő elindul.
- **CTRL + ALT + DEL való bejelentkezéshez szükséges**: Állítsa be **engedélyezése** , nyomja le a CTRL + ALT + DEL nem szükséges a felhasználók jelentkezhetnek be. **Nincs konfigurálva** (alapértelmezett) értékre állítva a felhasználók csak a CTRL+ALT+DEL billentyűkombináció lenyomásával jelentkezhetnek be a Windowsba.
- **Viselkedés az intelligens kártya eltávolításakor**: Meghatározza, hogy mi történik, ha a bejelentkezett felhasználó intelligens kártyáját eltávolítják az intelligenskártya-olvasó. A választható lehetőségek:

  - **Munkaállomás zárolása**: A munkaállomás zárolva van, az intelligens kártya eltávolításakor. Ez a beállítás lehetővé teszi a felhasználóknak, hogy elhagyják a helyiséget, magukkal vigyék az intelligens kártyájukat, és továbbra is fenntartsák védett munkamenetüket.
  - **Kijelentkezés kényszerítése**: A felhasználó rendszer automatikusan kijelentkezteti az intelligens kártya eltávolításakor.
  - **Ha egy távoli asztali szolgáltatások munkamenet leválasztása**: Az intelligens kártya eltávolítása nélkül a felhasználó kijelentkeztetése leválasztja a munkamenetet. Ez a beállítás lehetővé teszi, hogy a felhasználó az intelligens kártya újbóli beillesztésével később, vagy más intelligenskártya-olvasóval felszerelt gépnél újbóli bejelentkezés nélkül folytathassa a munkamenetet. Helyi munkamenet esetén ez a szabályzat pontosan úgy működik, mint a Munkaállomás zárolása.

    A [LocalPoliciesSecurity-beállítások](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) című témakörben további információt találhat.

#### <a name="display"></a>Megjelenítés

- **Felhasználói adatokat a zárolási képernyőn**: A munkamenet zárolásakor megjelenített felhasználói adatok konfigurálása. Ha nincs konfigurálva, a felhasználó megjelenített neve, a tartomány és a felhasználónév látható.
  - **Nincs konfigurálva**  
  - **Felhasználó megjelenített neve, tartomány- és felhasználónév**
  - **Csak a felhasználó megjelenített neve**
  - **Ne jelenjenek meg a felhasználói adatok**
- **Utolsó bejelentkezett felhasználó elrejtése**: **Engedélyezése** elrejti a felhasználónevet. A **Nincs konfigurálva** (alapértelmezett) értékkel megjelenítheti a felhasználónevet.
- **Bejelentkezés felhasználónév elrejtése**: **Engedélyezése** elrejti a felhasználónevet. A **Nincs konfigurálva** (alapértelmezett) értékkel megjelenítheti a felhasználónevet.
- **Bejelentkezési üzenet címe**: Az üzenet címének megadása a bejelentkező felhasználókat.
- **Bejelentkezési üzenet szövege**: Az üzenet szövegének megadása a bejelentkező felhasználókat.

### <a name="network-access-and-security"></a>Hálózati hozzáférés és biztonság

- **Nevesített csövekhez és megosztások való névtelen hozzáférés**: **Nincs konfigurálva** (alapértelmezett) korlátozza a névtelen hozzáférés a megosztás és a Named Pipe-beállítások. A névtelenül megadható beállításokra vonatkozik.
- **SAM-fiókok névtelen felsorolása**: **Lehetővé teszi** névtelen felhasználók számára a SAM-fiókok. A Windows engedélyezi a névtelen felhasználók számára a tartományfiókok és hálózati megosztások enumerálását.
- **SAM-fiókok és-megosztások névtelen felsorolása**: **Nincs konfigurálva** (alapértelmezett) azt jelenti, névtelen felhasználók névlistázás tartományi fiókok és hálózati megosztásokra. A SAM-fiókok és -megosztások névtelen számbavételének megakadályozásához állítsa **Letilt** értékre.
- **Jelszómódosításkor tárolt LAN-kezelő üzenetkivonatát**: Jelenleg a következő jelszómódosításkor dönt, hogy **engedélyezése** a LAN Manager-(LM-) tárolására, az új jelszó a kivonat értékével. **Nincs konfigurálva** (alapértelmezett) érték esetén az üzenetkivonat nem tárolódik.
- **PKU2U hitelesítési kérelmek**: **Blokk** PKU2U hitelesítési kérelmek, az eszköz online identitások használatára. **Nem konfigurált** (alapértelmezett) érték esetén ezek a kérelmek engedélyezve vannak.
- **Távoli RPC-kapcsolatok az SAM korlátozása**: Állítsa be **engedélyezése** számára megtagadja a felhasználók és csoportok abban, hogy a távoli RPC-hívások, a biztonsági fiókkezelő (SAM), amely tárolja a felhasználói fiókkal és jelszóval. **Lehetővé teszi** is lehetővé teszi, hogy módosítja az alapértelmezett Security Descriptor Definition Language (SDDL) karakterlánc explicit módon engedélyezi vagy megtagadja a felhasználók és csoportok távoli hívásokat ezeket. **Nincs konfigurálva** (alapértelmezett) használja az alapértelmezett biztonsági leíró, és engedélyezheti a felhasználók és csoportok távoli RPC hívásokat küldjenek a SAM-nek.
  - **Biztonsági leíró**

### <a name="recovery-console-and-shutdown"></a>Helyreállítási konzol és leállítás

- **Virtuális memória lapozófájljának törlése leállításkor**: Állítsa be **engedélyezése** törölje a virtuális memória lapozófájljának törlése, amikor az eszköz le van-e kapcsolva. A **Nincs konfigurálva** érték nem törli a virtuális memóriát.
- **A napló nélkül leállítása**: **Blokk** elrejti a leállítási lehetőséget, a Windows bejelentkezési képernyő. A felhasználóknak a leállítás előtt be kell jelentkezniük az eszközbe. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a felhasználók számára, hogy állítsa le az eszközt a Windows bejelentkezési képernyő.

### <a name="user-account-control"></a>Felhasználói fiókok felügyelete

- **Az UIA integritása biztonságos hely hiányában**: Ha a beállítása **blokk**, biztonságos helyen a fájlrendszerben található alkalmazások futnak, csak a UIAccess integritási szinttel. **Nincs konfigurálva** (alapértelmezett) értékkel az alkalmazások akkor is futtathatók UIAccess integritási szinttel, ha a fájlrendszer nem biztonságos helyein találhatók.
- **Fájl- és beállításjegyzék-írási hibák felhasználónként különböző helyekre virtualizálása**: Ha a beállítása **engedélyezve**, az alkalmazásokat, amelyek adatokat író védett helyek sikertelen. Ha a beállítása **nincs konfigurálva** (alapértelmezett), alkalmazás-írási hibák irányítja át a futási időt a fájlrendszer és a beállításjegyzék definiált felhasználói helyét.
- **Csak az aláírt és érvényesített végrehajtható fájlok jogosultságszintjének emelése**: Állítsa be **engedélyezve** kényszeríteni a nyilvános kulcsokra épülő infrastruktúra tanúsítványlánc érvényességének ellenőrzését egy végrehajtható fájlt, ahhoz, hogy futtatható. **Nincs konfigurálva** (alapértelmezett) értékkel nem kényszeríti a PKI-tanúsítványlánc érvényesítését egy végrehajtható fájlhoz, mielőtt az futhatna.

#### <a name="uia-elevation-prompt-behavior-settings"></a>UIA jogosultságszint-emelési kérés viselkedésének beállításai

- **Jogosultságszint-emelési kérés rendszergazdák**: Rendszergazdai engedélyezéses módban a rendszergazdák számára a jogosultságszint-emelési kérés viselkedésének megadása:
  - **Jogosultságszint-emelés kérés nélkül**
  - **Hitelesítő adatok bekérése a biztonságos asztalon**
  - **Beleegyezés kérése a biztonságos asztalon**
  - **Hitelesítő adatok bekérése**
  - **Beleegyezés kérése**
  - **Nincs konfigurálva**: Beleegyezés kérése nem Windows bináris fájlok
- **Jogosultságszint-emelési kérés általános jogú felhasználók esetében**: Általános jogú felhasználók esetében a jogosultságszint-emelési kérés viselkedésének megadása:
  - **Jogosultságszint-emelési kérések automatikus megtagadása**
  - **Hitelesítő adatok bekérése a biztonságos asztalon**
  - **Nincs konfigurálva**: Hitelesítő adatok kérése
- **Jogosultságszint-emelési kérések átirányítása a felhasználó interaktív asztalára**: **Engedélyezése** , nyissa meg az összes jogosultságszint-emelési kérések az interaktív felhasználó asztalán, nem a biztonsági asztal. A rendszer a rendszergazdákra és az általános jogú felhasználókra vonatkozó kérések viselkedését szabályzó házirend-beállításokat alkalmazza. A **Nincs konfigurálva** (alapértelmezett) értékre állítva minden jogosultságszint-emelési kérés a biztonságos asztalra lesz irányítva a rendszergazdákra és szabványos felhasználókra vonatkozó, a kérések viselkedését szabályzó házirend-beállításoktól függetlenül.
- **Jogosultságszint-emelési kérés alkalmazástelepítések**: Ha a beállítása **engedélyezve**, alkalmazáscsomagok telepítési nem észlelhető, vagy a jogosultságszint-emeléshez kéri. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a rendszer rendszergazdai felhasználónevet és jelszót kér a felhasználótól, amikor egy alkalmazástelepítési csomag emelt szintű jogosultságot igényel.
- **UIA jogosultságszint-emelési kérés biztonsági asztal hiányában**: **Engedélyezése** , hogy UIAccess-alkalmazások emelését, a biztonsági asztal használata nélkül. A **Nincs konfigurálva** (alapértelmezett) értékre állítva a jogosultságszint-emelési kérések egy biztonsági asztalt használnak.

#### <a name="admin-approval-mode-settings"></a>A rendszergazdai engedélyezéses mód beállításai

- **Rendszergazdai jóváhagyás mód a beépített rendszergazdához**: **Engedélyezett** lehetővé teszi, hogy a beépített Rendszergazda fiók rendszergazdai engedélyezéses mód használatára. A jogosultságszint-emelést igénylő műveletek felhasználói jóváhagyást kérnek. A **Nincs konfigurálva** (alapértelmezett) érték minden alkalmazást teljes rendszergazdai jogosultságokkal futtat.
- **Minden rendszergazda futtatása rendszergazdai engedélyezéses módban**: Állítsa be **engedélyezve** letiltani a rendszergazdai engedélyezéses mód és az összes kapcsolódó felhasználói fiókok Felügyeletének házirend-beállításokat. A **Nincs konfigurálva** (alapértelmezett) érték engedélyezi a rendszergazdai engedélyezéses módot.

### <a name="microsoft-network-client"></a>Microsoft hálózati ügyfél

- **Kommunikáció digitális aláírása (Ha a kiszolgáló egyetért)**: Azt határozza meg, ha az SMB-ügyfél egyezteti az SMB-csomagaláírást. Ha ez a beállítás **Nincs konfigurálva**, vagy engedélyezve van (ez az alapértelmezés), a Microsoft hálózati ügyfél a kiszolgálótól a munkamenet beállításakor az SMB-csomagok aláírását kéri. Ha a csomagaláírás engedélyezve van a kiszolgálón, a csomagaláírás egyeztetése megkezdődik. Ha ez a szabályzat **le van tiltva**, az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Titkosítatlan jelszavak küldése egyéb SMB-kiszolgálóknak**: Ha a beállítása **engedélyezése**, a Server Message Block (SMB) átirányító egyszerű szöveges jelszavakat küldhet nem Microsoft SMB - kiszolgálóknak, amelyek nem támogatják a titkosítási jelszó a hitelesítés során. A **Nincs konfigurálva** (alapértelmezett) értékkel a jelszavak titkosítva vannak.

### <a name="microsoft-network-server"></a>Microsoft hálózati kiszolgáló

- **Kommunikáció digitális aláírása (ha az ügyfél egyetért)**: Azt határozza meg, ha az SMB-kiszolgálón egyezteti az SMB-csomagaláírás, az azt kérő ügyfelekkel. **Engedélyezés** értékre állítva a Microsoft hálózati kiszolgáló egyezteti az SMB-csomagok aláírását az ügyfél kérése szerint. Ez azt jelenti, hogy ha a csomagaláírás engedélyezve van az ügyfélnél, a csomagaláírás egyeztetése megkezdődik. Ha ez a beállítás **Nem konfigurált** állapotú vagy le van tiltva (alapértelmezett), akkor az SMB-ügyfél soha nem egyezteti az SMB-csomagok aláírását.
- **Kommunikáció digitális aláírása (mindig)**: Azt határozza meg, ha az SMB kiszolgáló-összetevő szüksége van a csomag aláírása. **Engedélyezés** értékre állítva a Microsoft hálózati kiszolgáló nem kommunikál a Microsoft hálózati ügyféllel, hacsak az ügyfél bele nem egyezik az SMB-csomagok aláírásába. Ha ez a beállítás **Nincs konfigurálva** vagy le van tiltva (alapértelmezett), akkor az SMB-csomagok aláírásának egyeztetése megkezdődik az ügyfél és a kiszolgáló között.

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md), és [állapotát nyomon](device-profile-monitor.md).

Végpont-védelmi beállítások konfigurálása a [macOS](endpoint-protection-macos.md) eszközök.

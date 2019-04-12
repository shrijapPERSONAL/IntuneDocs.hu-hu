---
title: A Microsoft Intune hálózati követelményei és sávszélességi adatai
titleSuffix: ''
description: Az Intune hálózati konfigurációja követelményeinek és a sávszélességi adatainak áttekintése.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/11/2019
ms.locfileid: "59509708"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Intune – a hálózati konfiguráció követelményei és sávszélessége

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ez az útmutató az Intune szolgáltatás hálózati követelményeivel kapcsolatban nyújt segítséget a rendszergazdáknak. Információt talál benne a sávszélességre vonatkozó követelményekről, valamint a proxybeállításokhoz szükséges IP-cím- és portbeállításokról.

## <a name="average-network-traffic"></a>Átlagos hálózati forgalom
A táblázat az egyes ügyfelek esetében a hálózaton áthaladó általános tartalmak hozzávetőleges méretét és gyakoriságát tartalmazza.

> [!NOTE]
> Annak biztosítása érdekében, hogy az eszközök megkapják a frissítéseket és a tartalmakat az Intune-ból, rendszeresen kapcsolódniuk kell az internethez. A frissítések vagy tartalmak fogadásához szükséges idő változó lehet, de az eszközöket minden nap legalább egy óráig folyamatosan az internethez csatlakoztatva kell tartani.

|Tartalom típusa|Hozzávetőleges méret|Gyakoriság és részletek|
|----------------|--------------------|-------------------------|
|Intune-ügyfél telepítése<br /><br />**Az alábbi követelmények az Intune-ügyfél telepítésén kívül értendők**|125 MB|**Egy alkalommal**<br /><br />Az ügyfél letöltési mérete az adott ügyfélszámítógép operációs rendszerétől függ.|
|Ügyfélregisztrációs csomag|15 MB|**Egy alkalommal**<br /><br />További letöltések is előfordulhatnak, ha frissítések érhetők el ehhez a tartalomtípushoz.|
|Endpoint Protection-ügynök|65 MB|**Egy alkalommal**<br /><br />További letöltések is előfordulhatnak, ha frissítések érhetők el ehhez a tartalomtípushoz.|
|Operations Manager-ügynök|11 MB|**Egy alkalommal**<br /><br />További letöltések is előfordulhatnak, ha frissítések érhetők el ehhez a tartalomtípushoz.|
|Házirendügynök|3 MB|**Egy alkalommal**<br /><br />További letöltések is előfordulhatnak, ha frissítések érhetők el ehhez a tartalomtípushoz.|
|A Távsegítség a Microsoft Easy Assist használatával szolgáltatás ügynöke|6 MB|**Egy alkalommal**<br /><br />További letöltések is előfordulhatnak, ha frissítések érhetők el ehhez a tartalomtípushoz.|
|Ügyfél napi szintű működése|6 MB|**Naponta**<br /><br />Az Intune-ügyfél rendszeresen kommunikál az Intune szolgáltatással, hogy ellenőrizze a frissítéseket és a szabályzatokat, és jelentse az ügyfél állapotát a szolgáltatásnak.|
|Az Endpoint Protection szolgáltatás kártevő-definícióinak frissítései|Változó<br /><br />Általában 40 KB és 2 MB között|**Naponta**<br /><br />Naponta legfeljebb három alkalommal.|
|Az Endpoint Protection motor frissítése|5 MB|**Havonta**|
|Szoftverfrissítések|Változó<br /><br />A méret a telepített frissítésektől függ.|**Havonta**<br /><br />Általában minden hónap második keddjén jelennek meg szoftverfrissítések.<br /><br />Az újonnan regisztrált vagy telepített számítógépek a korábban kiadott frissítések teljes készletének letöltésével több hálózati sávszélességet használhatnak.|
|Szervizcsomagok|Változó<br /><br />Az egyes telepített szervizcsomagok mérete változó.|**Változó**<br /><br />A szervizcsomagok telepítésének idejétől függ.|
|Szoftverterjesztés|Változó<br /><br />A méret a telepített szoftverektől függ.|**Változó**<br /><br />A szoftverek telepítésének idejétől függ.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>A hálózatisávszélesség-felhasználás csökkentésének módjai
Az alábbi eljárások közül egynek vagy többnek az alkalmazásával csökkenthető az Intune-ügyfelek által felhasznált hálózati sávszélesség.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Proxykiszolgáló használata a tartalomkérelmek gyorsítótárazásához
A proxykiszolgálók képesek gyorsítótárazni a tartalmakat, amivel csökkenthető az ismétlődő letöltések és az internetről származó tartalmakhoz felhasznált hálózati sávszélesség mennyisége.

Az ügyfelek tartalomkéréseit fogadó gyorsítótárazási proxykiszolgálók be tudják olvasni a megfelelő tartalmakat, és képesek gyorsítótárazni a webes válaszokat és a letöltéseket is. A kiszolgáló az ügyfelek későbbi kérelmeire a gyorsítótárazott adatok alapján ad választ.

Az alábbiakban az Intune-ügyfelek számára tartalmakat gyorsítótárazó proxykiszolgálókhoz használható tipikus beállítások láthatók.


|          Beállítás           |           Javasolt érték           |                                                                                                  Részletek                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Gyorsítótár mérete         |             5 GB-tól 30 GB-ig             | Az érték a hálózatban lévő ügyfélszámítógépek számától és a használt beállításoktól függ. A fájlok túl korai törlésének elkerülése érdekében a gyorsítótár mérete a környezethez igazítható. |
| Egyedi gyorsítótárfájlok mérete |                950 MB                 |                                                                     Ez a beállítás nem feltétlenül érhető el minden gyorsítótárazási proxykiszolgálón.                                                                     |
|   Gyorsítótárazandó objektumtípusok    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Az Intune-csomagok olyan CAB-fájlok, amelyeket a Háttérben futó intelligens átviteli szolgáltatás (BITS) tölt le HTTP protokollal.                                               |
> [!NOTE]
> Ha proxykiszolgálót használ a tartalomkérelmek gyorsítótárazásához, a kommunikáció csak titkosított az ügyfél és a proxy közötti és a proxy, az Intune-hoz. A kapcsolat az Intune-hoz az ügyfél nem lesz teljes körű titkosított.

A proxykiszolgálók tartalmak gyorsítótárazására való használatával kapcsolatos további tudnivalókat a proxykiszolgáló-megoldása dokumentációjában találhat.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Háttérben futó intelligens átviteli szolgáltatás (BITS) használatát a számítógépeken
Konfigurált munkaidőben BITS használhatja olyan Windows-számítógépen a hálózati sávszélesség csökkentése érdekében. A BITS-szabályzatot állíthat be a **hálózati sávszélesség** lap az Intune-ügynök házirend.

> [!NOTE]
> Az MDM-kezelést a Windows a MobileMSI alkalmazástípus csak az operációs rendszer felügyeleti felület bittel letöltéséhez. AppX/MsiX saját a BITS letöltési verem használata, és Win32-alkalmazások az Intune-ügynök használata helyett a BITS kézbesítésoptimalizálás.

A BITS Windows rendszerű számítógépeken való használatáról a TechNet könyvtár a [Háttérben futó intelligens átviteli szolgáltatással foglalkozó témakörében](http://technet.microsoft.com/library/bb968799.aspx) olvashat bővebben.

### <a name="use-branchcache-on-computers"></a>A BranchCache használata a számítógépeken
Az Intune-ügyfeleken a BranchCache szolgáltatással is csökkenthető a nagykiterjedésű hálózati (WAN) forgalom. A következő operációs rendszerek támogatják a BranchCache használatát:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

A BranchCache használatához az ügyfélszámítógépen engedélyezni kell a BranchCache-t, majd az **elosztott gyorsítótáras módot** kell beállítani rajta.

Ha az Intune-ügyfél telepítve van a számítógépeken, a BranchCache és az elosztott gyorsítótáras mód alapértelmezés szerint engedélyezve van. Csoportházirend BranchCache le van tiltva, ha az Intune nem bírálja felül ezt a házirendet, és a BranchCache letiltva marad.

A BranchCache használatakor a szervezet más rendszergazdáival együttműködve kezeljék a Csoportházirendet és az Intune-tűzfalházirendet. Ellenőrizze, hogy azok ne helyezze üzembe a BranchCache vagy a tűzfalkivételeket letiltó szabályzatokat. A BranchCache-sel kapcsolatban bővebben lásd: [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx) (A BranchCache áttekintése).

## <a name="network-communication-requirements"></a>Hálózati kommunikációs követelmények

A felügyelt eszközök és a felhőalapú szolgáltatásokhoz szükséges végpontok közötti hálózati kommunikáció engedélyezéséhez.

Csak felhőalapú szolgáltatás az Intune a helyszíni infrastruktúrát, például a kiszolgálókat vagy átjárókat nem szükséges.

Tűzfalak és proxykiszolgálók mögött található eszközök felügyeletére, engedélyeznie kell a kommunikációt az Intune-hoz.

- A proxykiszolgálónak támogatnia kell mind a **HTTP (80)**, mind a **HTTPS (443)** protokollt, mert az Intune-ügyfelek mindkét protokollt használják
- Bizonyos tevékenységek (például a szoftverfrissítések letöltése), az Intune hitelesített proxykiszolgálói hozzáférést igényel a manage.microsoft.com

Proxykiszolgáló beállításai az egyes ügyfélszámítógépeken módosíthatja. A csoportházirend-beállítások segítségével módosíthatja az összes, egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza:

|**Tartományok**|**IP-cím**|
|---------------------|-----------|
|login.microsoftonline.com | További információ: [Office 365-ös URL-címek és IP-címtartományok](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Apple-eszközhálózati információ


|Használt|Hostname (IP address/subnet)|Protokoll|Port|
|-----|--------|------|-------|
|Leküldéses értesítések fogadásának via Apple Push Notification Service (APNS) az Intune szolgáltatástól. Az Apple dokumentációjában talál [Itt](https://support.apple.com/en-us/HT203609)|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|-N keresztül az Apple Push Notification Service (APNS) Intune-hoz küldhető visszajelzés|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Beolvasása és a tartalom Apple kiszolgálókról történő megjelenítése|itunes.apple.com<br>\*. itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|APNS-kiszolgálókkal való kommunikációhoz|#-courier.push.apple.com (17.0.0.0/8)<br>'#' egy véletlenszerű szám 0-50-re.|    TCP     |  5223 és 443  |
|Különböző funkcióit, többek között a hozzáférés a webes, iTunes Store-ban, macOS app Store áruházból, icloud-alapú, üzenetkezelés, stb. |phobos.apple.com<br>ocsp.apple.com<br>AX.iTunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 vagy 443   |

További információkért tekintse meg az Apple [szoftvertermékek Apple által használt TCP és UDP-portok](https://support.apple.com/en-us/HT202944), [kiszolgálókapcsolatok gazdagép és az iTunes macOS, iOS és az iTunes kapcsolatos háttér-folyamatok](https://support.apple.com/en-us/HT201999), és [Ha a macOS- és iOS-ügyfelek nincsenek rájuk vonatkozó Apple leküldéses értesítéseket](https://support.apple.com/en-us/HT203609).

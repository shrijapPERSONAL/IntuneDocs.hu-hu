---
title: "Az Intune hálózatisávszélesség-felhasználása"
description: "az Intune hálózatisávszélesség-felhasználása"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f5af3aefe814a52ae3b43a894242ac972e0cc8fc
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="intune-network-bandwidth-use"></a>Az Intune hálózatisávszélesség-felhasználása

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ez az útmutató az Intune szolgáltatás hálózati követelményeivel kapcsolatban nyújt segítséget a rendszergazdáknak. Információt talál benne a sávszélességre vonatkozó követelményekről, valamint a proxybeállításokhoz szükséges IP-cím- és portbeállításokról.

## <a name="average-network-traffic"></a>Átlagos hálózati forgalom
A táblázat az egyes ügyfelek esetében a hálózaton áthaladó általános tartalmak hozzávetőleges méretét és gyakoriságát tartalmazza.

> [!NOTE]
> Ahhoz, hogy a számítógépek és mobileszközök biztosan megkapják a szükséges frissítéseket és tartalmakat az Intune szolgáltatástól, rendszeresen kapcsolódniuk kell az internethez. A frissítések vagy tartalmak fogadásához szükséges idő változó, de az eszközöket ajánlott minden nap legalább 1 óráig folyamatosan az internethez csatlakoztatva tartani.

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
A tartalmak egy proxykiszolgálóval való gyorsítótárazásával csökkenthető az ismétlődő letöltések mennyisége és az internetről tartalmat igénylő ügyfelek által felhasznált hálózati sávszélesség.

A gyorsítótárazási proxykiszolgáló fogadja a hálózaton lévő ügyfélszámítógépek tartalomkérelmeit, beszerzi ezeket a tartalmakat az interneten, és ezután a HTTP-válaszokat és a bináris letöltéseket is képes gyorsítótárazni. A kiszolgáló a gyorsítótárban lévő adatokkal válaszolja meg az Intune-ügyfélszámítógépektől érkező későbbi kérelmeket.

Az alábbiakban az Intune-ügyfelek számára tartalmakat gyorsítótárazó proxykiszolgálókhoz használható tipikus beállítások láthatók.

|Beállítás|Javasolt érték|Részletek|
|-----------|---------------------|-----------|
|Gyorsítótár mérete|5 GB-tól 30 GB-ig|Az érték a hálózatban lévő ügyfélszámítógépek számától és a használt beállításoktól függ. A fájlok túl korai törlésének elkerülése érdekében a gyorsítótár mérete a környezethez igazítható.|
|Egyedi gyorsítótárfájlok mérete|950 MB|Ez a beállítás nem feltétlenül érhető el minden gyorsítótárazási proxykiszolgálón.|
|Gyorsítótárazandó objektumtípusok|HTTP<br /><br />HTTPS<br /><br />BITS|Az Intune-csomagok olyan CAB-fájlok, amelyeket a Háttérben futó intelligens átviteli szolgáltatás (BITS) tölt le HTTP protokollal.|
A proxykiszolgálók tartalmak gyorsítótárazására való használatával kapcsolatos további tudnivalókat a proxykiszolgáló-megoldása dokumentációjában találhat.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>A Háttérben futó intelligens átviteli szolgáltatás használata a számítógépeken
Az Intune a beállított időszakokban felhasznált hálózati sávszélesség csökkentése érdekében támogatja a Háttérben futó intelligens átviteli szolgáltatás (BITS) használatát a Windows rendszerű számítógépeken. A BITS szolgáltatáshoz az Intune-ügynök szabályzatának **Hálózati sávszélesség** lapján állíthat be házirendet.

A BITS Windows rendszerű számítógépeken való használatáról a TechNet könyvtár a [Háttérben futó intelligens átviteli szolgáltatással foglalkozó témakörében](http://technet.microsoft.com/library/bb968799.aspx) olvashat bővebben.

### <a name="use-branchcache-on-computers"></a>A BranchCache használata a számítógépeken
Az Intune-ügyfeleken a BranchCache szolgáltatással is csökkenthető a nagykiterjedésű hálózati (WAN) forgalom. A következő, ügyfélként is támogatott operációs rendszerek támogatják a BranchCache szolgáltatást is:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

A BranchCache használatához az ügyfélszámítógépen engedélyezni kell a BranchCache-t, majd az **elosztott gyorsítótáras módot** kell beállítani rajta.

A BranchCache és az elosztott gyorsítótáras mód alapértelmezés szerint engedélyezve van azokon a számítógépeken, amelyekre telepítve van az Intune-ügyfél. Ha azonban az ügyfélre már érvényes egy, a BranchCache szolgáltatást letiltó csoportházirend, az Intune ezt nem bírálja felül, és a BranchCache letiltva marad ezen a számítógépen.

A BranchCache használata eseten lépjen kapcsolatba a szervezet más, a Csoportházirendet és az Intune tűzfalszabályzatát kezelő rendszergazdáival, hogy ne alkalmazzanak a BranchCache szolgáltatást vagy a tűzfalkivételeket letiltó szabályzatokat. A BranchCache-sel kapcsolatban bővebben lásd: [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx) (A BranchCache áttekintése).

## <a name="network-communication-requirements"></a>Hálózati kommunikációs követelmények

Engedélyezni kell a hálózati kommunikációt a felügyelt eszközök és az Intune-előfizetés kezelésére használt eszközök között, illetve a felhőalapú szolgáltatásokhoz szükséges webhelyek között.

Az Intune nem használja a helyszíni infrastruktúrát (például olyan kiszolgálót, amelyen Intune szoftverek futnak), de a helyi infrastruktúra (így például Exchange és az Active Directory szinkronizálási eszközök) használata is lehetőséges.

A tűzfalak és proxykiszolgálók mögött található számítógépek kezeléséhez olyan tűzfalakat és proxykiszolgálókat kell beállítania, amelyek engedélyezik a kommunikációt az Intune számára. A proxykiszolgáló mögött található számítógépek kezelésével kapcsolatban fontos tudni a következőket:

-   A proxykiszolgálónak támogatnia kell mind a **HTTP (80)**, mind a **HTTPS (443)** protokollt, mert az Intune-ügyfelek mindkét protokollt használják
-   Az Intune hitelesített proxykiszolgálói hozzáférést igényel a manage.microsoft.com webcímhez bizonyos műveletekhez, például szoftver és frissítések letöltéséhez

Az egyes ügyfélszámítógépeken módosíthatja a proxykiszolgáló beállításait, vagy csoportházirend-beállítások segítségével módosíthatja egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.

A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza:

|**Tartományok**|**IP-cím**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|

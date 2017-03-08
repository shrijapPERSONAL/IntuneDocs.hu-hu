---
title: "Az Intune hálózatisávszélesség-felhasználása | A Microsoft Docs"
description: "az Intune hálózatisávszélesség-felhasználása"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0f5972171349325eeb750e552481cbcf903fdf95
ms.openlocfilehash: 9f1cd7ea3e92ac2e3a1b828e8185961060a7c619
ms.lasthandoff: 02/10/2017


---

# <a name="intune-network-bandwidth-use"></a>Az Intune hálózatisávszélesség-felhasználása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez az útmutató a vállalatnál az eszközkezelésért felelős rendszergazdák számára készült. Az Intune mobileszközös használatával kapcsolatban lásd [az Intune-os céges portállal kapcsolatos gyakori kérdéseket](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

A Microsoft Intune beállítása előtt olvassa el ezt a témakört, valamint a [Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md) című témakörben felsorolt követelmények listáját.

Az alábbiakban megadott információk segítségével megtervezhető a Microsoft Intune-ügyfelek hálózati forgalma.

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

A tűzfalak és proxykiszolgálók mögött található számítógépek kezeléséhez olyan tűzfalakat és proxykiszolgálókat kell beállítania, amelyek engedélyezik a kommunikációt az Intune számára.

### <a name="requirements-for-proxy-servers"></a>A proxykiszolgálókra vonatkozó követelmények
A proxykiszolgáló mögött található számítógépek kezelésével kapcsolatban fontos tudni a következőket:

-   A proxykiszolgálónak támogatnia kell mind a **HTTP**, mind a **HTTPS** protokollt, mert az Intune-ügyfelek mindkét protokollt használják.
-   Az Intune a hitelesítés nélküli proxykiszolgálókat is támogatja.

Az egyes ügyfélszámítógépeken módosíthatja a proxykiszolgáló beállításait, vagy csoportházirend-beállítások segítségével módosíthatja egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.

### <a name="requirements-for-firewalls-ports-and-domains"></a>A tűzfalakra, portokra és tartományokra vonatkozó követelmények
A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza.

|**Tartomány**|**Portok**|**IP-cím**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 és 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 és 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 és 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 és 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 és 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 és 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 és 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 és 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 és 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 és 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 és 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 és 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 és 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 és 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 és 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 és 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 és 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 és 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 és 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 és 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 és 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 és 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 és 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 és 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 és 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 és 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 és 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 és 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 és 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 és 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 és 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 és 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 és 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 és 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 és 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 és 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 és 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 és 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 és 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 és 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 és 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 és 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 és 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 és 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 és 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 és 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 és 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 és 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 és 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 és 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 és 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 és 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 és 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 és 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 és 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 és 443|111.221.76.60
|msua01.manage.microsoft.com|80 és 443|157.55.50.182
|msua02.manage.microsoft.com|80 és 443|134.170.49.121
|msua04.manage.microsoft.com|80 és 443|134.170.49.126
|msua05.manage.microsoft.com|80 és 443|157.55.240.190
|msub01.manage.microsoft.com|80 és 443|94.245.121.50
|msub02.manage.microsoft.com|80 és 443|94.245.121.58
|msub03.manage.microsoft.com|80 és 443|94.245.121.56
|msub05.manage.microsoft.com|80 és 443|157.56.113.123
|msuc01.manage.microsoft.com|80 és 443|104.44.84.187
|msuc02.manage.microsoft.com|80 és 443|104.44.84.188
|msuc03.manage.microsoft.com|80 és 443|104.44.84.189
|msuc05.manage.microsoft.com|80 és 443|111.221.76.60
|msua06.manage.microsoft.com|80 és 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 és 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 és 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 és 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 és 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 és 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 és 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 és 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 és 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 és 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 és 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 és 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 és 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 és 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 és 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 és 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 és 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 és 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 és 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 és 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 és 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 és 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 és 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 és 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 és 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 és 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 és 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 és 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 és 443|134.170.49.114
|ssu2.manage.microsoft.com|80 és 443|157.55.99.181
|status.manage.microsoft.com|80 és 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 és 443|93.184.215.200
|*.microsoftonline-p.com|80 és 443||
|has.spserv.microsoft.com<br>Eszközállapot-igazolási szolgáltatáshoz szükséges|443||
|*.microsoftonline-p.net|80 és 443||
|*.portal.office.com|80 és 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 és 443||
|c1.microsoft.com|80 és 443||
|blob.core.windows.net|80 és 443||
|ajax.aspnetcdn.com|80 és 443||
|*.googleapis.com<br>Ez a tartomány a vállalati portál webhelyének használatakor a JQuery támogatásához szükséges.|80 és 443||
|wustat.microsoft.com|80 és 443||
|Microsoft Update szolgáltatás|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 és 443|
|DNS-címkeresési kérelmek|manage.microsoft.com.nsatc.net|80|
|Samsung KNOX Standard-eszközök kommunikációja a tűzfalon keresztül|Ha engedélyezni szeretné, hogy a Samsung KNOX Standard-eszközök a tűzfalon keresztül csatlakozhassanak a KNOX Standard-kiszolgálókhoz, kövesse a Samsung KNOX Standarddel kapcsolatos gyakori kérdéseket ismertető dokumentum útmutatását.||
|Feltételes hozzáférési kommunikáció|443|204.79.197.200|
|Dokumentáció, súgó és támogatás</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||


>[!div class="step-by-step"]

>[&larr; **Előfeltételek**](what-to-know-before-you-start-microsoft-intune.md)     [**Előfizetés** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  


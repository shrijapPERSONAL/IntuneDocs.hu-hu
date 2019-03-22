---
title: A Microsoft Intune hálózati követelményei és sávszélességi adatai
titlesuffix: ''
description: Az Intune hálózati konfigurációja követelményeinek és a sávszélességi adatainak áttekintése.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
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
ms.openlocfilehash: 2a34c4fe8e010e60e0969d33d70b0e98993f7e23
ms.sourcegitcommit: b0b1030017e741d92c508130447a8242d9ad7a51
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58343008"
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

A proxykiszolgálók tartalmak gyorsítótárazására való használatával kapcsolatos további tudnivalókat a proxykiszolgáló-megoldása dokumentációjában találhat.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>A Háttérben futó intelligens átviteli szolgáltatás használata a számítógépeken
Az Intune a beállított időszakokban felhasznált hálózati sávszélesség csökkentése érdekében támogatja a Háttérben futó intelligens átviteli szolgáltatás (BITS) használatát a Windows rendszerű számítógépeken. A BITS szolgáltatáshoz az Intune-ügynök szabályzatának **Hálózati sávszélesség** lapján állíthat be házirendet.

A BITS Windows rendszerű számítógépeken való használatáról a TechNet könyvtár a [Háttérben futó intelligens átviteli szolgáltatással foglalkozó témakörében](http://technet.microsoft.com/library/bb968799.aspx) olvashat bővebben.

### <a name="use-branchcache-on-computers"></a>A BranchCache használata a számítógépeken
Az Intune-ügyfeleken a BranchCache szolgáltatással is csökkenthető a nagykiterjedésű hálózati (WAN) forgalom. A következő operációs rendszerek támogatják a BranchCache használatát:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

A BranchCache használatához az ügyfélszámítógépen engedélyezni kell a BranchCache-t, majd az **elosztott gyorsítótáras módot** kell beállítani rajta.

A BranchCache és az elosztott gyorsítótáras mód alapértelmezés szerint engedélyezve van azokon a számítógépeken, amelyekre telepítve van az Intune-ügyfél. Ugyanakkor ha a BranchCache le van tiltva a Csoportházirendben, az Intune nem bírálja felül ezt a szabályzatot, és a BranchCache letiltva marad.

A BranchCache használatakor a szervezet más rendszergazdáival együttműködve kezeljék a Csoportházirendet és az Intune-tűzfalházirendet. Győződjön meg arról, hogy nem alkalmaznak a BranchCache szolgáltatást vagy a tűzfalkivételeket letiltó szabályzatokat. A BranchCache-sel kapcsolatban bővebben lásd: [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx) (A BranchCache áttekintése).

## <a name="network-communication-requirements"></a>Hálózati kommunikációs követelmények

Engedélyezze a hálózati kommunikációt a kezelt eszközök és a felhőalapú szolgáltatásokhoz szükséges webhelyek között.

Az Intune nem használja a helyszíni infrastruktúrát (például olyan kiszolgálót, amelyen Intune szoftverek futnak), de a helyi infrastruktúra (így például Exchange és az Active Directory szinkronizálási eszközök) használata is lehetőséges.

A tűzfal mögötti számítógépek és a proxykiszolgálók kezeléséhez engedélyeznie kell az Intune-nal való kommunikációt.

-   A proxykiszolgálónak támogatnia kell mind a **HTTP (80)**, mind a **HTTPS (443)** protokollt, mert az Intune-ügyfelek mindkét protokollt használják
-   Az Intune bizonyos feladatokhoz, például szoftverek és frissítések letöltéséhez hitelesített proxykiszolgálói hozzáférést igényel a manage.microsoft.com webcímhez

Az egyes ügyfélszámítógépeken módosíthatja a proxykiszolgáló beállításait, vagy csoportházirend-beállítások segítségével módosíthatja egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza:

|**Tartományok**|**IP-cím**|
|---------------------|-----------|
|login.microsoftonline.com | További információ: [Office 365-ös URL-címek és IP-címtartományok](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212<br>52.234.146.75|
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
|enterpriseregistration.windows.net|52.175.211.189|

### <a name="apple-device-network-information"></a>Apple-eszközhálózati információ

|         Állomásnév         |                                        URL (IP-cím/alhálózat)                                        |  Protokoll  |     Port     |                          Eszköz                           |
|--------------------------|-------------------------------------------------------------------------------------------------------|------------|--------------|-----------------------------------------------------------|
|      Felügyeleti konzol       |                                  gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |                    Apple iOS és macOS                    |
|      Felügyeleti konzol       |                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |                    Apple iOS és macOS                    |
|      Felügyeleti konzol       | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net |    HTTP    |      80      |                    Apple iOS és macOS                    |
|        PI-kiszolgáló         |                gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8)                 |    TCP     |  2195, 2196  |         Apple iOS és macOS esetén felhőalapú üzenetekhez.          |
|     Eszközszolgáltatások      |                                        gateway.push.apple.com                                         |    TCP     |     2195     |                           Apple                           |
|     Eszközszolgáltatások      |                                        feedback.push.apple.com                                        |    TCP     |     2196     |                           Apple                           |
|     Eszközszolgáltatások      |   Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net   |    HTTP    |      80      |                           Apple                           |
| Eszközök (Internet/Wi-Fi) |                                 #-courier.push.apple.com(17.0.0.0/8)                                  |    TCP     | 5223 és 443 | Csak Apple. &#39;#&#39; véletlenszerű szám 0 és 200 között. |
| Eszközök (Internet/Wi-Fi) |                           phobos.apple.comocsp.apple.comax.itunes.apple.com                           | HTTP/HTTPS |  80 vagy 443   |                        Csak Apple                         |


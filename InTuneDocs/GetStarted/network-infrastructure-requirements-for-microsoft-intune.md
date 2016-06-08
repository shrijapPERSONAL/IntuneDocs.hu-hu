---
# required metadata

title: A Microsoft Intune hálózati infrastruktúrával kapcsolatos követelményei | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 074de65b-84a5-4a01-a824-18ffd838eab0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# A Microsoft Intune hálózati infrastruktúrával kapcsolatos követelményei
A Microsoft Intune beállítása előtt olvassa el ezt a témakört, valamint a [Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md) című témakörben felsorolt követelmények listáját..

Ez a témakör azokat a követelményeket ismerteti, amelyek lehetővé teszik, hogy a hálózati infrastruktúra továbbítani tudja a kezelt eszközök, az Intune-előfizetés kezeléséhez használt eszközök, valamint a felhőalapú szolgáltatás által használt internetes webhelyek között folyó kommunikációt.

Nem kötelező a helyszíni infrastruktúra használata (például egy olyan kiszolgáló használata, amelyen telepítenie kell a szoftvereket), de lehetősége van a helyi infrastruktúra felhasználására, beleértve az Exchange és az Active Directory szinkronizálási eszközöket is.

A tűzfalak és proxykiszolgálók mögött található számítógépek kezeléséhez olyan tűzfalakat és proxykiszolgálókat kell beállítania, amelyek engedélyezik a kommunikációt az Intune számára.

## A tűzfalakra, portokra és tartományokra vonatkozó követelmények
A felügyelt eszközöket úgy kell beállítani, hogy **Minden felhasználó** hozzáférjen a különböző szolgáltatásokhoz a tűzfalon keresztül.

A következő táblázat az Intune-ügyfél által elért portokat és szolgáltatásokat tartalmazza.


|**Domain**|**Portok**|**IP-cím**|
|------|----|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 és 443|134.170.168.254<br>134.170.51.126
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
|Samsung KNOX-eszközök kommunikációja a tűzfalon keresztül|Ha engedélyezni szeretné, hogy a KNOX-eszközök a tűzfalon keresztül csatlakozhassanak a KNOX-kiszolgálókhoz, kövesse a következő dokumentum utasításait: Samsung KNOX – gyakori kérdések.||
|Dokumentáció, súgó és támogatás</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||



## A proxykiszolgálókra vonatkozó követelmények
A proxykiszolgáló mögött található számítógépek kezelésével kapcsolatban fontos tudni a következőket:

-   A proxykiszolgálónak támogatnia kell mind a **HTTP**, mind a **HTTPS** protokollt, mert az Intune-ügyfelek mindkét protokollt használják.

-   Az Intune a hitelesítés nélküli proxykiszolgálókat is támogatja.

Az egyes ügyfélszámítógépeken módosíthatja a proxykiszolgáló beállításait, vagy csoportházirend-beállítások segítségével módosíthatja egy adott proxykiszolgáló mögött található ügyfélszámítógépek beállításait.

Olyan proxykiszolgálót is használhat, amely a tartalom gyorsítótárazásával [csökkenti az Intune-ügyfelek sávszélesség-használatát](network-bandwidth-use.md).



## A Service to Service összekötőre vonatkozó követelmények
A Service to Service összekötő csak a felhőalapú Exchange-et támogatja, így nincsenek a helyszíni infrastruktúrára vonatkozó követelményei.

Az összekötő használatához teljesülniük kell a következőknek:

-   Olyan Office 365-előfizetéssel rendelkezik, amelyhez tartozik egy Exchange Server 2013-bérlő. Mindaddig, amíg a bérlő az Exchange Server 2013, az összekötő ugyanabban a környezetben támogatja az Exchange Server 2010-et is.

-   Az On-Premises Connector telepítéséhez használt felhasználói fióknak bérlői rendszergazdának kell lennie az Intune-ban, és rendszergazdának az Exchange Server 2013 használatához licenccel rendelkező Exchange-bérlőnél.

### További információ
[Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


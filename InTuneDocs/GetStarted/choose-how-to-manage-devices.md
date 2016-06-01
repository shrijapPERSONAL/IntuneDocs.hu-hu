---
# required metadata

title: A Microsort Intune-nal történő eszközkezelés módjának kiválasztása | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Az eszközkezelés módjának kiválasztása
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] segítségével sokféle eszközt kezelhet úgy, hogy *regisztrálja* őket a szolgáltatásban. A felhasználók ezt követően sokféle műveletet végezhetnek el a *vállalati portál* segítségével: regisztrálhatják az alkalmazásokat, válogathatnak az alkalmazások közül, telepíthetik őket, ellenőrizhetik, hogy megfelel-e az eszközük a vállalat szabályzatainak, és az informatikai támogatási munkatársakhoz fordulhatnak.

## A mobileszközök kezelésének módjai
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a következő eszközplatformokat képes kezelni:

- Apple iOS 7.1 és újabb verziók
- Google Android 4.0 és újabb verziók (beleértve a Samsung KNOX-ot is)
- Windows Phone 8.0 és újabb verziók
- Windows RT és Windows 8.1 RT
- Windows 8.1 és újabb operációs rendszerű számítógépek
- Mac OS X 10.9 és újabb verziók

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>Ha korábban regisztrált olyan eszközöket, amelyen az iOS-nak a támogatottnál korábbi verziója fut, azok regisztrálva maradnak. Azonban minden [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-verzió dokumentációjában ellenőrizze, hogy az adott iOS-verziót támogatja-e a funkció.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] képes a felhasználók eszközeinek (közkeletű nevén a „saját eszközök használatának” (BYOD)) kezelésére. A vállalat tulajdonában lévő eszközök kezelésére is alkalmas, beleértve az olyan helyzeteket is, amikor a vállalat a választható eszközök listáját bocsátja a felhasználók rendelkezésére (közkeletű nevén „saját eszköz kiválasztása” vagy CYOD).

### Az eszközök regisztrálása felügyeletre
A mobileszköz-operációs rendszert (iOS, Android, Windows Phone) használó eszközöket mindig regisztrálni kell. Az eszközök regisztrálásának módja azonban függ a szervezet igényeitől:

|Beléptetés típusa|BYOD|CYOD|Megosztott eszköz kezelő fiókkal|Megosztott eszköz felhasználói fiók nélkül|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Leírás**|Személyes eszköz regisztrálva a Microsoft Intune segítségével|Vállalat által birtokolt eszköz egyetlen felhasználó számára|Vállalat által birtokolt, kezelői fiókkal kezelt, sok felhasználó között megosztott eszköz|Vállalati által birtokolt, felhasználó nélküli, sok felhasználó által használt eszköz.|
|**Az eszköz felhasználója**|Tulajdonos|Hozzárendelt felhasználó|Nincs felhasználóspecifikus fiók|Nincs adott felhasználó|
|**Regisztrációt végzi**|Tulajdonos|Rendszergazda|Eszközkezelő|Bárki|
|**Regisztráció törlését végzi**|Tulajdonos vagy a rendszergazda|Rendszergazda|Rendszergazda|Rendszergazda|
|**Alaphelyzetbe állíthatja**|Tulajdonos vagy a rendszergazda|Rendszergazda|Rendszergazda|Rendszergazda|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>Az eszközök regisztrálásával elérhető lehetőséget teljes listájáért lásd: [Mobileszköz-kezelési képességek](mobile-device-management-capabilities-in-microsoft-intune.md).</p>
</div>



## A Windows rendszerű számítógépek kezelésének módjai
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] képes Windows Vista és újabb rendszerű Windows-számítógépek kezelésére az Intune-számítógépügyféllel. A Windows-számítógépek esetében eldöntheti azonban, hogy regisztrálja őket, vagy telepíti az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-számítógépügyfelet. Az utóbbi néhány olyan lehetőséget is nyújt, amely az eszközök regisztrálása esetén nem érhető el. A legtöbb esetben azonban célszerű regisztrálni a Windows-eszközöket az Intune-ban, ez ugyanis több funkciót biztosít, mint a számítógépes ügyfél.

Akkor fontolja meg az Intune-számítógépügyfél használatát, ha a következők a céljai:
<ul>
<li>A Microsoft Intune-számítógépügyfél nyújtotta funkciók használata a Windows-számítógépek kezelésére</li>
<li>Olyan Windows-számítógép kezelése, amelyen a regisztrációt nem támogató operációs rendszer fut</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>A támogatott Windows-számítógépeken futó Intune-számítógépügyfél által nyújtott funkciók teljes listáját lásd: [A Windows-számítógépek felügyeletére szolgáló képességek](windows-pc-management-capabilities-in-microsoft-intune.md).</p>
</div>

## Felügyelet az Exchange ActiveSync segítségével
Az Exchange ActiveSync segítségével is kezelheti az eszközöket. Ehhez telepítenie kell az intézményi összekötőt, vagy a beépített Service to Service összekötővel kell kapcsolódnia az Exchange Serverhez.

Az On-Premises Connector telepítésére vonatkozó hardver- és a szoftverkövetelményeket a következő szakaszban találja: [Az intézményi összekötőre vonatkozó követelmények](/Intune/network-infrastructure-requirements-for-microsoft-intune.md)..

További információ az On-Premises Connectornak vagy a Service to Service Connectornak az Exchange-dzsel történő használatáról: [Mobileszközök felügyeletének beállítása az Exchange ActiveSynckel a Microsoft Intune-ban](/Intune/get-started/mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)..



## További lépések
Megismerte azoknak a lehetőségeknek egy részét, amelyet az eszközöknek az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-ban való regisztrálásával elérhet, most [felkészítheti az eszközöket a regisztrációra](/Intune/get-started/get-ready-to-enroll-devices-in-microsoft-intune.md). Az eszközök regisztrálását követően élhet mindazoknak a funkcióknak az előnyeivel, amelyekről ebben a témakörben olvasott. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->


<!--HONumber=May16_HO1-->



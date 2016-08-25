---
title: "Az eszközkezelés módjának kiválasztása | Microsoft Intune"
description: "Ismerje meg az eszközök regisztrálására és kezelésére szolgáló különböző módszereket."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Az eszközkezelés módjának kiválasztása
Az Intune segítségével számos különböző eszközt kezelhet a szolgáltatásban való *regisztrálásukat* követően. A felhasználók ezt követően számos különböző műveletet végezhetnek el a *vállalati portál* segítségével: regisztrálhatják az alkalmazásokat, válogathatnak az alkalmazások közül, telepíthetik őket, ellenőrizhetik, hogy megfelel-e az eszközük a vállalat szabályzatainak, és az informatikai támogatási munkatársakhoz fordulhatnak.

## A mobileszközök kezelésének módjai
Az Intune a következő eszközplatformokat képes kezelni:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> Ha korábban regisztrált olyan eszközöket, amelyeken az iOS-nak a támogatottnál korábbi verziója fut, azok regisztrálva maradnak. Ellenőrizze a dokumentációban, hogy mely szolgáltatás támogatja az iOS adott verzióját.

Az Intune képes a felhasználók saját eszközeinek (amelyekre általában „hozott eszközök” (BYOD) néven hivatkoznak) kezelésére. A vállalat tulajdonában lévő eszközök kezelésére is alkalmas, beleértve az olyan helyzeteket is, amikor a vállalat a választható eszközök listáját bocsátja a felhasználók rendelkezésére (közkeletű nevén „saját eszköz kiválasztása” vagy CYOD).

### Az eszközök regisztrálása felügyeletre
A mobileszköz-operációs rendszert (iOS, Android, Windows Phone) használó eszközöket mindig regisztrálni kell. Az eszközök regisztrálásának módja a vállalat igényeitől függ:

|Beléptetés típusa|BYOD|CYOD|Megosztott eszköz kezelő fiókkal|Megosztott eszköz felhasználói fiók nélkül|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Leírás**|Személyes eszköz regisztrálva a Microsoft Intune segítségével|Vállalat által birtokolt eszköz egyetlen felhasználó számára|Vállalat által birtokolt, kezelői fiókkal kezelt, sok felhasználó között megosztott eszköz|Vállalati által birtokolt, felhasználó nélküli, sok felhasználó által használt eszköz.|
|**Az eszköz felhasználója**|Tulajdonos|Hozzárendelt felhasználó|Nincs felhasználóspecifikus fiók|Nincs adott felhasználó|
|**Regisztrációt végzi**|Tulajdonos|Rendszergazda|Eszközkezelő|Bárki|
|**Regisztráció törlését végzi**|Tulajdonos vagy a rendszergazda|Platform |Rendszergazda vagy felhasználó|Rendszergazda vagy felhasználó|
|**Alaphelyzetbe állíthatja**|Tulajdonos vagy a rendszergazda|Rendszergazda|Rendszergazda|Rendszergazda|

További információkért lásd: [a mobileszközök regisztrálásának módjai](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Az eszközök regisztrálásával elérhető lehetőségek teljes listájáért lásd: [Mobileszköz-kezelési képességek](mobile-device-management-capabilities-in-microsoft-intune.md).

## A Windows rendszerű számítógépek kezelésének módjai
Az Intune képes a Windows Vista vagy újabb Windows rendszerű számítógépek kezelésére az Intune-számítógépügyféllel. A Windows rendszerű számítógépek esetében azonban választhat, hogy regisztrálja őket, vagy telepíti az Intune-számítógépügyfelet. Az utóbbi olyan lehetőségeket is kínál, amelyek az eszközök regisztrálása esetén nem érhetők el. A legtöbb esetben azonban célszerű regisztrálni a Windows-eszközöket az Intune-ban, ez ugyanis több funkciót biztosít, mint a számítógépes ügyfél.

Akkor fontolja meg az Intune-számítógépügyfél használatát, ha a következők a céljai:

- A Microsoft Intune-számítógépügyfél által nyújtott funkciók használata a Windows rendszerű számítógépek felügyelete céljából
- Olyan Windows rendszerű számítógépek kezelése, amelyeken a regisztrációt nem támogató operációs rendszer fut

> [!NOTE]
> A támogatott Windows-számítógépeken futó Intune-számítógépügyfél által nyújtott funkciók teljes listáját lásd: [A Windows-számítógépek felügyeletére szolgáló képességek](windows-pc-management-capabilities-in-microsoft-intune.md).

## Felügyelet az Exchange ActiveSync segítségével
Az Exchange ActiveSync segítségével is felügyelheti az eszközöket. Ehhez telepítenie kell az intézményi összekötőt, vagy a beépített Service to Service összekötővel kell kapcsolódnia az Exchange Serverhez.

A helyszíni összekötő telepítésére vonatkozó hardver- és a szoftverkövetelményekről [A helyszíni összekötőre vonatkozó követelmények](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector) című témakörben olvashat.

További információk az On-Premises Connector vagy a Service to Service Connector összekötőnek az Exchange-dzsel történő használatáról: [Mobileszköz-kezelés az Exchange ActiveSync és a Microsoft Intune használatával](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## További lépések
Az előzőekben megismert néhány funkciót, amelyeket akkor használhat, ha regisztrálja eszközét a [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-nal. Következő lépésként [regisztrálja eszközeit](/intune/deploy-use/enroll-devices-in-microsoft-intune). Az eszközök regisztrálását követően élhet az előnyökkel, amelyeket az ebben a témakörben tárgyalt funkciók biztosítanak. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->



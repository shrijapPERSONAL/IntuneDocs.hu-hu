---
title: "Úgy tűnik, hogy az androidos eszköze titkosított"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Úgy tűnik, hogy az androidos eszköze titkosított, de a Céges portál nem így gondolja

Az eszköz titkosításakor egy, csak Ön által ismert titkos kulcs használatával kódolja a rajta lévő információt, így illetéktelenek nem férhetnek hozzá. Az információbiztonság érdekében a munkahelye az androidos eszközök titkosítását követeli meg Öntől, mielőtt hozzáférhetne a vállalati fájlokhoz, e-mailekhez és adatokhoz.

## <a name="common-issues"></a>Gyakori problémák

Az Android új verziói, különösen is a 7.0 és későbbi verziók indítási PIN-kód használatát követelik meg annak érdekében, hogy az eszköz teljes mértékben titkosított legyen. A különféle eszközgyártók az indítási PIN-kódra különféle leírásokat adnak meg, és különféle helyeken kérhetik azt. A legtöbbször azonban ezt „Biztonságos indításnak” hívják. 

## <a name="solutions"></a>Megoldások

### <a name="add-a-startup-pin"></a>Indítási PIN-kód hozzáadása

Egyes Android-eszközök indítási PIN-kód létrehozását teszik kötelezővé az eszköz biztonsága érdekében. Az Android rendszer különféle verziói érhetőek el számos különféle gyártótól. Lehetséges, hogy ezt a problémát megoldhatja, ha a megkeresi ezt a beállítási lehetőséget a beállításokat végző alkalmazásban. A Samsung Galaxy S7 eszközökön például a biztonságos indítást a **Beállítások** > **Képernyőzár és biztonság** > **Biztonságos indítás** területen engedélyezheti.  

### <a name="downgrade-your-version-of-android"></a>Az Android alacsonyabb verzióra való visszaléptetése
Ha az eszköz felkínálja az Android egy alacsonyabb, 6.0-s vagy újabb verziójára való visszalépés lehetőségét, használja azt. Amennyiben egy alacsonyabb verzióra való visszalépést kell megkísérelni az eszközön, az adatvesztési kockázattal jár. Ellenkező esetben javasoljuk, hogy a probléma megoldásához lépjen kapcsolatba a rendszergazdával. A rendszergazda kapcsolattartási adatait a [Céges portál webhelyen](http://portal.manage.microsoft.com) a kapcsolattartási adatoknál találja.

## <a name="specific-manufacturer-issues"></a>Gyártóspecifikus problémák

Néhány, 7.0-s vagy újabb Android-verzióval működő eszköz az androidos platformra vonatkozó bizonyos szabványokkal inkonzisztens módon titkosítja az adatokat. Ezek az eszközök alapesetben titkosítottnak tűnhetnek, de az Intune felismeri azon használt módszereket, amelyek az eszközön lévő információkat az eszközhöz fizikai hozzáféréssel rendelkező rosszindulatú felhasználók által jelentett veszélynek teszik ki.

> [!Note]
> A Microsoft együttműködik a gyártókkal a tesztelés közben feltárt vagy a felhasználók által jelzett problémák elhárítása érdekében. Ezt a cikket folyamatosan frissítjük, ha új információk állnak rendelkezésünkre. 

## <a name="known-devices"></a>Ismert eszközök

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>A probléma elhárítása érdekében frissíthető ismert eszközök

A probléma előfordulhat, ha az alábbi eszközök valamelyikével rendelkezik, és még nem frissítette azt a legújabb Android-verzióra. Ezeken az eszközökön a frissítést a **Beállítások** > **Frissítés** területen végezheti el. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>A probléma elhárítása érdekében jelenleg nem frissíthető ismert eszközök

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi okostelefonok](https://xiaomi-mi.com/mi-smartphones/)

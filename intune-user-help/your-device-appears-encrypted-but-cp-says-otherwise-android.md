---
title: "Úgy tűnik, hogy az androidos eszköze titkosított | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ab67a6f2fd1f861ba197464a9e369ca0b54e6b5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Úgy tűnik, hogy az androidos eszköze titkosított, de a Céges portál nem így gondolja

Az eszköz titkosításakor egy, csak Ön által ismert titkos kulcs használatával kódolja a rajta lévő információt. Ez megakadályozza, hogy jogosulatlan személyek férhessenek hozzájuk. Számos szervezet megköveteli a felhasználóitól Android-eszközeik titkosítását a vállalati fájlok, e-mailek vagy adatok eléréséhez.

## <a name="common-issues"></a>Gyakori problémák

Az Android új verziói, különösen is a 7.0 és későbbi verziók indítási PIN-kód használatát követelik meg annak érdekében, hogy az eszköz teljes mértékben titkosított legyen. A különféle eszközgyártók az indítási PIN-kódra különféle leírásokat adnak meg, és különféle helyeken kérhetik azt. A legtöbbször ezt a beállítást „Biztonságos indításnak” hívják. 

## <a name="solutions"></a>Megoldások

### <a name="add-a-startup-pin"></a>Indítási PIN-kód hozzáadása

Egyes Android-eszközök indítási PIN-kód létrehozását teszik kötelezővé az eszköz biztonsága érdekében. Az Android rendszer különféle verziói érhetőek el számos különféle gyártótól. Lehetséges, hogy ezt a problémát megoldhatja, ha a megkeresi ezt a beállítási lehetőséget a beállításokat végző alkalmazásban. A Samsung Galaxy S7 eszközökön például a biztonságos indítást a **Beállítások** > **Képernyőzár és biztonság** > **Biztonságos indítás** területen engedélyezheti.  

### <a name="encrypt-the-entire-device"></a>Titkosítsa a teljes eszközt

Egyes eszközök esetében választható a teljes eszköz titkosítása vagy csak a használatban lévő tárterület titkosítása. A „csak a használatban lévő tárterület titkosítása” lehetőség helyett válassza a teljes eszköz titkosítását. Ha már megtörtént a csak a használatban lévő tárterület titkosítása:

1. [Távolítsa el ezt az eszközt a Céges portálról](unenroll-your-device-from-intune-android.md)
2. Fejtse vissza a használatban lévő tárterületet
3. Titkosítsa a teljes eszközt
4. Regisztrálja újra az eszközt

### <a name="downgrade-your-version-of-android"></a>Az Android alacsonyabb verzióra való visszaléptetése

Ha az eszköz felkínálja az Android egy alacsonyabb, 6.0-s vagy újabb verziójára való visszalépés lehetőségét, használja azt. Amennyiben egy alacsonyabb verzióra való visszalépést kell megkísérelni az eszközön, az adatvesztési kockázattal jár. Ellenkező esetben javasoljuk, hogy a probléma megoldásához lépjen kapcsolatba a cég informatikai támogató szolgálatával. A cég informatikai támogató szolgálatának kapcsolattartási adatait a [Céges portál webhelyen](https://portal.manage.microsoft.com#HelpDeskDialog) a kapcsolattartási adatoknál találja.

## <a name="specific-manufacturer-issues"></a>Gyártóspecifikus problémák

Néhány, 7.0-s vagy újabb Android-verzióval működő eszköz az androidos platformra vonatkozó bizonyos szabványokkal inkonzisztens módon titkosítja az adatokat. Ezek az eszközök akkor is titkosítottnak tűnhetnek, ha vadonatújak. Az Intune felismeri, hogy ezen eszközök titkosítási módszerei veszélynek teszik ki az eszközadatokat. A kockázatot elsősorban az eszközhöz való fizikai hozzáféréssel rendelkező rosszindulatú felhasználók jelentik.

> [!Note]
> A Microsoft együttműködik a gyártókkal a tesztelés közben feltárt vagy a felhasználók által jelzett problémák elhárítása érdekében. Ezt a cikket folyamatosan frissítjük, ha új információk állnak rendelkezésünkre. 

## <a name="known-devices"></a>Ismert eszközök

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>A probléma elhárítása érdekében frissíthető ismert eszközök

A probléma előfordulhat, ha az alábbi eszközök valamelyikével rendelkezik, és még nem frissítette azt a legújabb Android-verzióra. Ezeken az eszközökön a frissítést a **Beállítások** > **Frissítés** területen végezheti el. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>A probléma elhárítása érdekében jelenleg nem frissíthető ismert eszközök

A probléma az alábbi eszközök nem oldható fel. Szüksége lehet egy másik eszköz használatára a vállalati erőforrások eléréséhez. 

- [Huawei Mate 8](https://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [OPPO eszközök](http://www.oppo.com/en/smartphones)
- [Vivo eszközök](https://www.vivo.co.in)
- [Xiaomi Mi okostelefonok](https://xiaomi-mi.com/mi-smartphones/)

---
title: Úgy tűnik, hogy az androidos eszköze titkosított | Microsoft Docs
description: Oldja meg a titkosítási állapot és a Microsoft Intune céges portál alkalmazásban
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8c35400f37ab4ddee275cf23f7a50f280322e3b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501578"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Az eszköz titkosított, de alkalmazásokat tegyük fel, ellenkező esetben

Ha a vállalati portál vagy a Microsoft Intune app tegyük fel, hogy az eszköz nincs titkosítva, de biztos benne, hogy éppen, próbálja meg a jelen cikkben ismertetett lépések.  

## <a name="add-a-startup-pin"></a>Indítási PIN-kód hozzáadása

Egyes Android-eszközök indítási PIN-kód létrehozását teszik kötelezővé az eszköz biztonsága érdekében. Az eszköz helyét, ez a beállítás lesz **beállítások** alkalmazást. A nevének és helyének beállítás eltérőek lehetnek. Például a Samsung Galaxy S7, a beállítás a neve **biztonságos indításnak**. Az engedélyezéshez és a egy PIN-kód létrehozása, **beállítások** > **zárolási képernyő és biztonság** > **biztonságos indításnak**.  

## <a name="encrypt-the-entire-device"></a>Titkosítsa a teljes eszközt

Ez a szakasz csak a vállalati portál alkalmazás vonatkozik. Egyes eszközök esetében választható a teljes eszköz titkosítása vagy csak a használatban lévő tárterület titkosítása. Válassza ki a lehetőséget a teljes eszköz titkosítását. Ha azt választotta, hogy csak a használatban lévő tárterület titkosítása:

1. [Eltávolítja az eszközt a vállalati portálról](unenroll-your-device-from-intune-android.md).
2. A használatban lévő tárterület visszafejteni.  
3. Eszköz teljes titkosítása.  
4. Regisztrálja újra az eszközt.  

## <a name="downgrade-your-version-of-android"></a>Az Android alacsonyabb verzióra való visszaléptetése

Ez a szakasz csak a vállalati portál alkalmazás vonatkozik. Ha az eszköz felkínálja a lehetőséget, alacsonyabb szolgáltatásszintre váltásához az Android 6.0-s és újabb verziók, használja azt. Ha alacsonyabb szolgáltatásszintre váltásához az eszköz megpróbálja, nincs adatvesztés kockázatát. Ellenkező esetben javasoljuk, hogy a probléma megoldásához lépjen kapcsolatba a cég informatikai támogató szolgálatával. A cég informatikai támogatási szolgálatának kapcsolattartási adatait szerezni a [céges portál webhelyen](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Gyártóspecifikus problémák

Néhány Android-eszközök a 7.0-s és újabb titkosítja az adatokat, hogy egyes Android-platformtól szabványok nem konzisztens. Ezek az eszközök akkor is titkosítottnak tűnhetnek, ha vadonatújak. Az Intune felismeri, hogy ezen eszközök titkosítási módszerei veszélynek teszik ki az eszközadatokat. A kockázatot elsősorban az eszközhöz való fizikai hozzáféréssel rendelkező rosszindulatú felhasználók jelentik.

> [!Note]
> A Microsoft együttműködik a gyártókkal a tesztelés közben feltárt vagy a felhasználók által jelzett problémák elhárítása érdekében. Ezt a cikket folyamatosan frissítjük, ha új információk állnak rendelkezésünkre. 

## <a name="update-known-devices"></a>Ismert eszközök frissítése   

Ha az eszköz Android legújabb verziójára még nem frissítette, nyissa meg az eszköz **beállítások** alkalmazást, és válassza **frissítés**. Ezek az eszközök nem jelenhet megfelelő, amíg nem frissíti őket.  

- Huawei Honor 8
- Huawei P9

## <a name="known-devices-that-always-appear-encrypted"></a>Mindig megjelennek a titkosított ismert eszközök  
Az alábbi eszközök mindig megjelenik a titkosított, és nem használható a vállalati erőforrások eléréséhez. Vállalati erőforrások eléréséhez másik eszközt kell használnia.  

- Huawei Mate 8
- OPPO eszközök
- Vivo eszközök
- Xiaomi Mi okostelefonok  

## <a name="next-steps"></a>További lépések   
További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.  
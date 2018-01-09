---
title: "A Google Play Protect megfelelőségvizsgálatának engedélyezése az Intune-nal"
titleSuffix: Azure portal
description: "A cikk azt mutatja be, hogyan hozható létre megfelelőségi szabályzat androidos eszközökön a Google Play Protect engedélyezéséhez."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3d9e687ff31d50e30ea4d15a4eb751c0e78dc24e
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Eszközmegfelelőségi szabályzat létrehozása a Google Play Protect engedélyezéséhez ‒ útmutató

A Google Play Protect (GPP) megfelelőségvizsgálatához létrehozhat egy új, Android platformon alkalmazható megfelelőségi szabályzatot.

Az adott beállításokat szükségessé tevő megfelelőségi szabályzatot Android-felhasználókra és Android-eszközökre lehet alkalmazni. Ha egy eszközön nincsenek engedélyezve ezek a beállítások, akkor az eszköz nem megfelelőnek minősül.

## <a name="create-a-compliance-policy"></a>Megfelelőségi házirend létrehozása

1. Jelentkezzen be az Azure Portalra. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
2. A **Kezelés** csoportból válassza az **Eszközmegfelelőség** elemet. 
3. Válassza a **Szabályzatok** majd a **Szabályzat létrehozása** lehetőséget.
4. Adja meg a szabályzat **Nevét** és **Leírását**.
5. A platformra vonatkozóan adja meg az **Android** értéket.
6. Válassza a **Beállítások** > **Eszközállapot** lehetőséget.
7. Adja meg a **Google Play Protect**-beállításokat.
8. Ha megadta a Google Play Protect-beállításokat, adja meg a **Biztonság**- és az **Eszköztulajdonság**-beállításokat. Ha elkészült, válassza az **OK** elemet.

## <a name="configure-the-google-play-protect-settings"></a>Google Play Protect-beállítások megadása

 - **A Google Play-szolgáltatások be van állítva**  
   Megadása esetén a Google Play-szolgáltatások alkalmazást telepíteni és engedélyezni kell. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön.
 - **Naprakész biztonsági szolgáltató**  
   Megadása esetén egy naprakész biztonsági szolgáltatóval kell védeni az eszközöket az ismert biztonsági kockázatokkal szemben.
 - **Alkalmazások fenyegetettségvizsgálata**  
   Megadása esetén engedélyezve kell lennie az androidos **Alkalmazások ellenőrzése** (Verify Apps) szolgáltatásnak.
    > [!Note]  
    > A régebbi Android platformon ez a szolgáltatás egy megfelelőségi beállítás. Az Intune csak azt tudja ellenőrizni, hogy eszközszinten engedélyezett-e ez a beállítás. A korábban Android for Work néven ismert, munkahelyi profilokkal rendelkező eszközökön a konfigurációs szabályzat (configuration policy) beállításai között található ez a beállítás. A rendszergazdák itt tudják engedélyezni az adott eszközre vonatkozóan.

    Ha cég használ androidos munkahelyi profilokat, a regisztrált eszközökre vonatkozóan engedélyezhető az **Alkalmazások fenyegetettségvizsgálata** beállítás. Hozzon létre egy eszközprofilt, és tegye kötelezővé a rendszerbiztonsági beállítást. További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

 - **SafetyNet eszközigazolás**  
   Adja meg a szükséges SafetyNet eszközigazolás-integritási szintet. A megadható szintek többek között: **Nincs konfigurálva**, **Alapvető integritás ellenőrzése**, és **Alapvető integritás ellenőrzés és tanúsított eszközök**.




## <a name="next-steps"></a>További lépések

Az Intune-beli eszközmegfelelőségi szabályzatok kezelésével kapcsolatban további információkat talál [Az Intune eszközmegfelelőségi szabályzatai – első lépések](device-compliance-get-started.md) című témánál.
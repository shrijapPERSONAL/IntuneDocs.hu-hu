---
title: Az Intune vállalati portál Android-eszköz titkosítása |} A Microsoft Docs
description: Az Android-eszközökön az eszköztitkosítás bekapcsolását lépések
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ad953049b9d2efd6f7a828ee70b5e1cede4ee68
ms.sourcegitcommit: d0749cbc68df41893742f5187ac378a5ade824f2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58406248"
---
# <a name="encrypt-your-android-device"></a>Az Android-eszköz titkosítása

Az eszköztitkosítás védi a fájlok és mappák a jogosulatlan hozzáférés ellen, ha az eszköz elvesztésekor vagy ellopásakor. Az eszköztitkosítás bekapcsolását követően csak a helyes jelszót vagy PIN-kód lesznek jelentkezhet be az eszközre. 

Iskolai vagy munkahelyi erőforrások eléréséhez, a szervezet szükség lehet az Android-eszköz titkosítását. Alapértelmezés szerint néhány újabb Android-eszközök titkosítottak-a-beépített.  

Ha egy üzenetet kap a vállalati portált, amelyen az eszközt titkosítania kell, végezze el az alábbi lépéseket. 

> [!Note]
> A Huawei, a Vivo és az OPPO bizonyos Android-eszközökön nem lehet titkosítani. További információért [kattintson ide](your-device-appears-encrypted-but-cp-says-otherwise-android.md).  

1.  Egy eszköz képernyőzár beállítása.  
    a. Lépjen a **beállítások** > **zárolási képernyő és biztonság** > **képernyő-zárolási típus**.  
    b. Ezek közül bármelyikre **PIN-kód**, **jelszó**, vagy **minta**.  
    c. Kövesse a képernyőn megjelenő utasításokat, a képernyőzárat konfigurálásához.  

2. Lépjen vissza a **zárolási képernyő és biztonság** válassza **biztonságos indításnak**.
3. Válasszon **PIN-kód megkövetelése amikor az eszköz bekapcsolása** > **OK**.
4. Adja meg a PIN-kód megerősítése és az eszköz titkosítása.
5. Nyissa meg a céges portál alkalmazást, válassza ki az eszközt, és koppintson **eszközbeállítások ellenőrzése**.  

4.4-es és régebbi Android rendszerű eszközök nem feltétlenül a **biztonságos indítás** lehetőséget. Ebben az esetben a következő lépéseket az eszköz titkosítását.

1. Lépjen a **beállítások** > **biztonsági** > **eszköz titkosítása**. Képernyőn címkék Android-eszközök között változhat. Ha nem látja a **eszköz titkosítása** lehetőség választásakor ellenőrizze:
    * **Tárolási** > **tárolás titkosítása**
    * **Tárolási** > **zárolási képernyő és biztonság** > **további biztonsági beállítások** 

2. Kövesse a képernyőn megjelenő utasításokat. Titkosítás során az eszköz lehetett többször újraindul.
3. Nyissa meg a céges portál alkalmazást, válassza ki az eszközt, és koppintson **eszközbeállítások ellenőrzése**.  

## <a name="troubleshoot"></a>Hibaelhárítás  
**A probléma**: Azt, hogy már titkosította az eszközt, és

- A titkosítási gomb le van tiltva.
- Egy üzenet azt jelzi, hogy titkosítania kell az eszközt.
- Hibaüzenet jelenik meg a Vállalati portál alkalmazás használatakor.

**Az alábbiakkal próbálkozhat**

- Ellenőrizze, hogy az eszköz fel van-e töltve és csatlakoztatva van-e.  
- Ellenőrizze, hogy beállított-e PIN-kódot vagy jelszót az eszközön.  

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.  

---
title: Az Endpoint Protection hibaelhárítása az Intune-ban – Azure | Microsoft Docs
description: Megoldhatja a Microsoft Intune végpontvédelmi szolgáltatásának használata közben felmerülő problémákat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: f828394c48b5b7d55d9180da875d9cb3062f23c6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181683"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Az Endpoint Protection hibáinak elhárítása az Intune-ban

Ezek az információk segítséget nyújtanak a végpontvédelmi szolgáltatás használata közben felmerülő problémák megoldásához. Ezenkívül [áttekintheti az eseménynaplókat és a hibakódokat a Windows Defender AV problémáinak hibaelhárításához](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Ha ezek az információk nem segítettek, akkor [támogatást kérhet a Microsoft Intune-hoz](get-support.md).

### <a name="error-messages"></a>Hibaüzenetek
Ez a szakasz a következő hibák és figyelmeztetések lehetséges okait és megoldásait ismerteti.

|Állapotelem|Lehetséges okok|Lehetséges megoldások|
|---------------|--------------------|-----------------------|
|**Az Endpoint Protection-motor nem érhető el**|Az Intune végpontvédelmi motorja sérült vagy törölték.|Ha az Intune végpontvédelmi motorja sérült, megpróbálhatja frissíteni vagy újratelepíteni a szoftvert.<br /><br />Az azonnali frissítés kényszerítéséhez válassza a végpontvédelmi ügyfélszoftver **Frissítés** elemét (amely a felügyelt számítógépek tálcáján található).<br /><br />Ha nem lehet frissíteni, akkor újra kell telepítenie a végpontvédelmi motort.<br /><br />A felügyelt számítógép Vezérlőpultján, a telepített programok listájában keresse meg a **Microsoft Intune Endpoint Protection-ügynököt**, majd távolítsa el az alkalmazást.<br /><br />A következő frissítési szinkronizálás során a Microsoft Online Management frissítéskezelője észleli a hiányzó programot, és az ütemezés szerinti telepítési időpontban újratelepíti.|
|**Az Endpoint Protection le van tiltva**|Az Intune végpontvédelmi funkciót letiltotta egy konfigurációs profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A végpontok védelmének engedélyezése. Lásd: [végpontvédelmi beállítások hozzáadása](endpoint-protection-configure.md) az Intune-ban, vagy [a Windows Defender bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows).|
|**A valós idejű védelem le van tiltva**|A valós idejű védelmet letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A végpontok védelmének engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A letöltések vizsgálata le van tiltva**|A letöltések vizsgálatát letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A vizsgálat engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A fájl- és programtevékenységek figyelése le van tiltva**|A fájl- és programtevékenységek figyelését letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A fájl- és programtevékenység figyelésének engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A viselkedésfigyelés le van tiltva**|A viselkedésfigyelést letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A viselkedésfigyelés engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A parancsfájlok vizsgálata le van tiltva**|A szkriptek vizsgálatát letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A szkriptek vizsgálatának engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A hálózatfelügyeleti rendszer le van tiltva**|A hálózatfelügyeleti rendszert letiltotta egy profilt használó rendszergazda vagy egy felügyelt számítógép felhasználója.|A hálózatvizsgáló rendszer (NIS) engedélyezése. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) az Intune-ban, vagy [a valósidejű védelem bekapcsolása a vállalati erőforrásokhoz való hozzáféréshez](/intune-user-help/turn-on-defender-windows). |
|**A kártevő-definíciók elavultak**|Előfordulhat, hogy a számítógép hosszabb ideig nem csatlakozott az internethez, és még nem frissültek a kártevő-definíciói. Ez az állapot akkor jelenik meg, ha a számítógép kártevő-definíciói legalább 14 napja elavultak.|Az elavult kártevő-definíciókat a [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus) segítségével frissítheti.|
|**Teljes vizsgálat késésben**|14 napja nem végzett teljes vizsgálatot. Ezt az okozhatja, ha egy számítógép újraindul a teljes vizsgálat közben.|Ha a teljes vizsgálat késésben van, akkor futtathat egy egyszeri teljes vizsgálatot, vagy ismétlődő teljes vizsgálatokat ütemezhet. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Gyorsvizsgálat késésben**|14 napja nem végzett gyorsvizsgálatot. Ezt az okozhatja, ha egy számítógép újraindul a gyorsvizsgálat közben.|Ha a gyorsvizsgálat késésben van, akkor lefuttathat egy egyszeri gyorsvizsgálatot, de ismétlődő gyorsvizsgálatokat is ütemezhet. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Egy másik végpontvédelmi alkalmazás fut**|Egy másik végpontvédelmi alkalmazás fut, és a számítógép megfelelő állapotban van.|Ha egy másik végpontvédelmi alkalmazás is telepítve van, és az Intune érzékeli azt, akkor az eszköz instabillá válhat.|

### <a name="next-steps"></a>További lépések
Ha ezek az információk nem segítettek, akkor [támogatást kérhet a Microsoft Intune-hoz](get-support.md).

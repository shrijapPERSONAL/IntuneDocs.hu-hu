---
title: "Eszközök kezelése az Intune-nal"
titleSuffix: Intune on Azure
description: "Útmutató az Intune-nal felügyelt eszközök megjelenítéséhez és az eszközökön végrehajtható különféle műveletekhez.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0fc5337b92ac604a448038f685b27623b6153f9
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszközök** munkafolyamat áttekintést nyújt a felügyelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Ekkor végrehajthatja az alábbiakban felsorolt távoli eszközműveleteket. Az egyes műveletek az eszköz platformjának és konfigurációjának függvényében érhetők el:

## <a name="available-device-actions"></a>Elérhető eszközműveletek

- [Az eszközleltár megtekintése](device-inventory.md)
- Távoli eszközműveletek végrehajtása:
    - [Céges adatok eltávolítása](device-company-data-remove.md) 
    - [Gyári beállítások visszaállítása](device-factory-reset.md)
    - [Távoli zárolás](device-remote-lock.md)
    - [Új PIN-kód](device-passcode-reset.md)
    - [Az aktiválási zár megkerülése](device-activation-lock-bypass.md)
    - [Újrakezdés](device-fresh-start.md)
    - [Elveszett eszköz mód](device-lost-mode.md)
    - [Eszköz megkeresése](device-locate.md)
    - [Újraindítás](device-restart.md)
    - [Windows 10-es PIN-kód alaphelyzetbe állítása](device-windows-pin-reset.md)
    - [Távirányítás Androidhoz](device-profile-android-teamviewer.md)
    - [Eszköz szinkronizálása](device-sync.md)


## <a name="next-steps"></a>További lépések

- Válassza az **Eszközműveletek** lehetőséget az Ön által kezelt eszközökön végzett műveletek állapotának megtekintéséhez. 
![Eszközműveletek figyelése](./media/monitor-device-actions.png)

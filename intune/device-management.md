---
title: "Eszközök kezelése az Intune-nal"
titlesuffix: Azure portal
description: "Útmutató az Intune-nal felügyelt eszközök megjelenítéséhez és az eszközökön végrehajtható különféle műveletekhez.”"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca40eee8a53fa3e8b2610ce414f0037180d4beaf
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszközök** munkafolyamat áttekintést nyújt a felügyelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Megtekintheti az eszközökre vonatkozó információkat, és végrehajthatja a felsorolt távoli eszközműveleteket.

## <a name="available-device-actions"></a>Elérhető eszközműveletek
Az egyes műveletek az eszköz platformjának és konfigurációjának függvényében érhetők el.

- [Az eszközleltár megtekintése](device-inventory.md)
- Távoli eszközműveletek végrehajtása:
    - [Céges adatok eltávolítása](devices-wipe.md#remove-company-data)
    - [Gyári beállítások visszaállítása](devices-wipe.md#factory-reset)
    - [Távoli zárolás](device-remote-lock.md)
    - [Új PIN-kód](device-passcode-reset.md)
    - [Az aktiválási zár megkerülése](device-activation-lock-bypass.md) (kizárólag iOS esetében)
    - [Újrakezdés](device-fresh-start.md) (kizárólag Windowson)
    - [Elveszett eszköz mód](device-lost-mode.md) (kizárólag iOS esetében)
    - [Eszköz megkeresése](device-locate.md) (kizárólag iOS esetében)
    - [Újraindítás](device-restart.md) (kizárólag Windowson)
    - [Windows 10-es PIN-kód alaphelyzetbe állítása](device-windows-pin-reset.md)
    - [Távirányítás Androidhoz](device-profile-android-teamviewer.md)
    - [Eszköz szinkronizálása](device-sync.md)


## <a name="next-steps"></a>További lépések

- Válassza az **Eszközműveletek** lehetőséget az Ön által kezelt eszközökön végzett műveletek állapotának megtekintéséhez.
![Eszközműveletek figyelése](./media/monitor-device-actions.png)

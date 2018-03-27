---
title: Eszközök kezelése a Microsoft Intune-nal
titleSuffix: ''
description: Áttekintheti az Intune-nal felügyelt eszközöket, és különféle műveleteket hajthat végre rajtuk.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 436eeb306bf4ba343ae4d88a824aeed2077a3426
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Rendszergazdaként meg kell győződnie arról, hogy a felügyelt eszközök a végfelhasználók munkájához szükséges erőforrásokat nyújtják, és megvédik az adatokat.

Az **Eszközök** munkafolyamat áttekintést nyújt a felügyelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune-ban** válassza az **Eszközök** lehetőséget.
4. Megtekintheti az eszközökre vonatkozó információkat, és végrehajthatja az alábbi távoli eszközműveleteket:
    - **Áttekintés** – A kezelhető regisztrált eszközök pillanatképe.
    - **Minden eszköz** – Az Ön által kezelt regisztrált eszközök. A megjelenített adatok pontosításához válassza a **Szűrő** vagy az **Oszlopok** lehetőséget . [Az eszközleltár megtekintéséhez](device-inventory.md) jelöljön ki egy eszközt.
    - **Azure AD-eszközök** – Az Azure Active Directory (AD) szolgáltatásban regisztrált vagy azzal összekapcsolt eszközök. További tudnivalók az [Azure AD eszközkezeléséről](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Eszközműveletek** – Az eszközökön végrehajtott távoli műveletek előzményei, amelyek tartalmazzák a műveletet, az állapotot, a műveletet kezdeményező felhasználót és az időt.

        ![Képernyőkép az eszközműveletek figyeléséről](./media/monitor-device-actions.png)

    - **Auditnaplók** – Az auditnaplókban a Microsoft Intune-ban változást előidéző tevékenységek jegyzéke érhető el. További információk az [Auditnaplókról](monitor-audit-logs.md).
    - **TeamViewer-összekötő** – A TeamViewer szolgáltatás révén az Intune-ban kezelt Android-eszközök használói távsegítséget kérhetnek a rendszergazdájuktól. További információ a [TeamViewerről](device-profile-android-teamviewer.md).
    - **Súgó és támogatás** – Hibaelhárítási információkat kereshet, támogatást kérhet, és megtekintheti az Intune állapotát.  
    
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

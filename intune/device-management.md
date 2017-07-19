---
title: "Eszközök kezelése az Intune-nal"
titleSuffix: Intune on Azure
description: "Útmutató az Intune-nal felügyelt eszközök megjelenítéséhez és az eszközökön végrehajtható különféle műveletekhez.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>A Microsoft Intune-eszközfelügyelet ismertetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Eszközök** munkafolyamat áttekintést nyújt a felügyelt eszközökről, és lehetővé teszi, hogy távolról hajtson végre műveleteket rajtuk. A munkafolyamat elérése:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.

Ekkor az alábbi műveletekre van lehetősége:

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


## <a name="support-for-each-device-action"></a>Az egyes eszközműveletek támogatása

Használja a következő táblázatot az egyes műveletek által támogatott eszközplatformok megértéséhez.

|||||||
|-|-|-|-|-|-|
|Eszközművelet|Windows|Windows Phone|iOS|macOS|Android|
|**Céges adatok eltávolítása**|Igen|Igen|Igen|Igen|Igen|
|**Gyári beállítások visszaállítása**|Windows 8.1 és újabb (nem EAS-ban kezelt eszközök)|Igen|Igen|Nem|Az Android for Work nem támogatott|
|**Törlés**|Igen|Igen|Igen|Igen|Igen|
|**Távoli zárolás**|Nem|Windows Phone 8.1 és újabb verziók|Igen|Nem|Igen|
|**Új PIN-kód**|Nem|A Windows Phone 8.1-es verziótól a Windows 10 alkotói frissítés nem Azure AD-hoz csatlakoztatott verziójáig, Windows 10 alkotói frissítés és újabb – mind|Igen|Nem|Az Android 7-nél régebbi, az Android for Work nem támogatott|
|**Új jelszó** (Windows 10-es eszközökhöz)|Nem|Windows 10 alkotói frissítés és újabb (Azure AD-hoz csatlakozott)|Nem|Nem|Az Android for Work nem támogatott|
|**Az aktiválási zár megkerülése**|Nem|Nem|Vállalati tulajdonú eszközök|Nem|Nem|
|**Elveszett eszköz mód**|Nem|Nem|iOS 9.3 és újabb, felügyelt és vállalati tulajdonú|Nem|Nem|
|**Eszköz megkeresése**|Nem|Nem|Elveszett módú iOS 9.3 és újabb, felügyelt és vállalati tulajdonú|Nem|Nem|
|**Aktuális felhasználó kijelentkeztetése**|Nem|Nem|iOS 9.3 és újabb (csak megosztott iPad eszközök)|Nem|Nem|
|**Újraindítás**|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|Nem|Nem|Nem|
|**Újrakezdés**|Windows 10 alkotói frissítés és újabb|Nem|Nem|Nem|Nem|
|**Új távsegítség-munkamenet**|Nem|Nem|Nem|Nem|Igen|
|**Felhasználó eltávolítása**|Nem|Nem|iOS 9.3 és újabb (csak megosztott iPad eszközök)|Nem|Nem|

## <a name="next-steps"></a>További lépések

- Válassza az **Eszközműveletek** lehetőséget az Ön által kezelt eszközökön végzett műveletek állapotának megtekintéséhez. 
![Eszközműveletek figyelése](./media/monitor-device-actions.png)
---
title: Frissítés a Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Tudja meg, hogyan frissítheti a Windows Holographic operációs rendszert futtató eszközöket a Windows Holographic for Business verzióra
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c268785e3cce7477203e78f321af15c5067d51ae
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041757"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>A Windows Holographic operációs rendszert futtató eszközök frissítése a Windows Holographic for Business verzióra

A Microsoft Intune az eszközök kezelésében és védelmében érdekében számos beállításokat tartalmaz. Ez a cikk sorolja fel, és az eszközök a Windows Holographic frissítése a Windows Holographic for Business-beállításokat ismerteti. Ezek a beállítások az Intune-ban, amelyek leküldött vagy eszközökre telepített egy frissítési konfigurációs profilban jönnek létre.

A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat a Windows Holographic eszközök frissítéséhez. A Microsoft HoloLens esetében a frissítés a szükséges licenc beszerzéséhez a Commercial Suite-ot is vásárolhat. További információkért lásd: [Unlock Windows Holographic for Business features](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise) (A Windows Holographic for Business új funkcióinak elérése).

Ez a szolgáltatás további információkért lásd: [frissítése a Windows 10-es kiadás vagy S engedélyezése módban](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Kiadásfrissítés

- **Frissítés erre a kiadásra**: Válassza ki **Windows 10 Holographic for Business**.
- **Licencfájl**: Keresse meg és válassza ki a kapott XML formátumú licencfájlt.

  ![Adja meg az XML-fájl neve, amely tartalmazza a Holographic for Business licencinformációk](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>További lépések

A profil létrehozása, de előfordulhat, hogy nem lehet sikeres bármit még. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md), és [állapotát nyomon](device-profile-monitor.md).

Ezenkívül létrehozhat edition frissítési profilok [Windows 10 és újabb](edition-upgrade-windows-settings.md) eszközök.

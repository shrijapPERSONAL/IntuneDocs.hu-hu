---
title: Windows 10-es frissítési és S mód beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg az összes beállítás listáját, és mit tesznek azt az eszközön egy Windows 10-es kiadásra való frissítéskor, vagy a Microsoft Intune-ban egy eszközkonfigurációs profilt használó eszközök S mód engedélyezéséhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c34f683bfd16362dfb9af9a69c6f7d9b04860c7
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042198"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>A Windows 10 (és újabb) eszközbeállítások verziófrissítési kiadásait, vagy engedélyezze S mód az Intune-ban

A Microsoft Intune az eszközök kezelésében és védelmében érdekében számos beállításokat tartalmaz. Ez a cikk és kiadások frissítéséhez, vagy S mód Windows 10 rendszerű eszközökön engedélyezze a beállításokat ismerteti. Ezek a beállítások az Intune-ban, amelyek leküldött vagy eszközökre telepített egy frissítési konfigurációs profilban jönnek létre.

A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások használatával edition és a Windows 10 rendszerű eszközökhöz S mód beállításai.

Ez a szolgáltatás további információkért lásd: [frissítése a Windows 10-es kiadás vagy S engedélyezése módban](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Előkészületek

[A profil létrehozásához](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Kiadásfrissítés

- **Frissítés erre a kiadásra**: Válassza ki a Windows 10-es kiadása, amely kiadására való frissítés. A szabályzat hatókörébe tartozó eszközök ekkor frissülnek a választott kiadásra.
- **Termékkulcs**: Adja meg a termékkulcsot a Microsofttól kapott. Miután létrehozta a termékkulcsot tartalmazó szabályzatot, a termékkulcsot nem lehet többé frissíteni, és biztonsági okokból rejtve marad. A termékkulcs módosításához a teljes kulcsot újra meg kell adnia.
- **Licencfájl**: A **Windows 10 Holographic for Business** vagy **Windows 10 Mobile-edition**, válassza a **Tallózás** a Microsofttól kapott licencfájl kiválasztásához. Ezt a fájlt tartalmaz, amelyre az eszközök a kiadás licencadatait.

## <a name="mode-switch"></a>Módváltás

- **Nincs konfiguráció**: -S mód eszköz S módban marad. A végfelhasználók válthatnak S módból.
- **Tartsa S módban**: Letiltja a végfelhasználó számára az eszköz S módból váltásban.
- **Kapcsoló**: Az eszköz S módból vált.

## <a name="next-steps"></a>További lépések

A profil létrehozása, de előfordulhat, hogy nem lehet sikeres bármit még. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md), és [állapotát nyomon](device-profile-monitor.md).

Ezenkívül létrehozhat edition frissítési profilok [Windows Holographic for Business](holographic-upgrade.md) eszközök.

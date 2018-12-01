---
title: Kézbesítésoptimalizálási beállításait a Windows 10-beli Microsoft Intune - ban |} A Microsoft Docs
description: 'Konfigurálja a szoftverfrissítések hogyan érkeznek az eszközök a kézbesítési optimalizálás cloud services elérhető Windows 10-es és újabb rendszerű eszközök használatával. Az Intune-ban hozzon létre egy konfigurációs profil frissítések telepítése az internetről. Lásd még: cserélje le a meglévő frissítési körök kézbesítési optimalizálás profillal.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36cfb5ac05b2d69b5c7349f4ebc6054848a08fc8
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2018
ms.locfileid: "52730107"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>A Windows 10 (és újabb) kézbesítésoptimalizálási beállításait a Microsoft Intune-ban

Ez a cikk és az összes a kézbesítésoptimalizálási beállításait konfigurálhatja a Windows 10-es eszközök ismerteti. Ezek a beállítások hozzá eszközkonfigurációs profil, és ezután hozzárendelt vagy az eszközöket a Microsoft Intune segítségével telepítve.

## <a name="settings"></a>Beállítások

**Kézbesítésoptimalizálásos letöltési mód**: válassza ki, hogyan frissítések beszerzését, az eszközöket. A választható lehetőségek:

- **Nincs konfigurálva**: frissítsenek eszközeiket a saját módszereivel használni, akkor a **Windows-frissítések** vagy **kézbesítésoptimalizálás** érhető el az operációs rendszer beállításait.
- **Csak HTTP, nincs társviszony-létesítés**: frissítések letöltése csak az internetről. Nem kap a frissítések más számítógépeket a hálózaton (nevű társviszony-létesítési vagy társ-társ).
- **Azonos mögötti társviszony-létesítéssel kombinálva HTTP-NAT HTTP privát csoportbeli társviszony-létesítéssel**: frissítések letöltése az internetről, és a hálózat más számítógépeiről. Társviszony-létesítés történik az ugyanazon Active Directory-hely (ha van ilyen), vagy ugyanabban a tartományban lévő eszközökön. Ha ezt a lehetőséget választja, a hálózati címfordítás (NAT) IP-címek társviszony-létesítés átlép.
- **HTTP internetes társviszony-létesítéssel**: frissítések letöltése az internetről, és a hálózat más számítógépeiről.
- **Egyszerű letöltési mód társviszony létesítés nélkül**: az internetről, közvetlenül a frissítés tulajdonosa, például a Microsoft a frissítéseket. Ez nem lépjen kapcsolatba a kézbesítési optimalizálás cloud services.
- **Megkerülő mód**: használata háttérben futó intelligens átviteli szolgáltatás (BITS) frissítéseket. Ne használja a kézbesítés optimalizálása.

## <a name="move-from-existing-update-rings-to-delivery-optimization"></a>Kézbesítésoptimalizálás meglévő frissítési körök áthelyezése

**Szoftverfrissítések – a Windows 10-es frissítési körök** helyébe a **kézbesítésoptimalizálás** beállításait. A meglévő frissítési körök használatával könnyedén módosítható a **kézbesítésoptimalizálás** beállításait. lépések:

1. Kézbesítési optimalizálás konfigurációs profil létrehozása:

    1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok** > **profil létrehozása**.
    2. Adjon meg egy **nevet** és egy **leírást** a profil számára.
    3. A **Platform**, válassza a **Windows 10 és újabb**. A **profiltípus**, válassza a **kézbesítésoptimalizálás**.
    4. Válassza a **Beállítások** lehetőséget. A **kézbesítésoptimalizálásos letöltési mód**, válassza ki a meglévő szoftverek frissítési kör által használt azonos módot. A választható lehetőségek:
        - **Nincs konfigurálva**
        - **Csak HTTP, nincs társviszony-létesítés**
        - **HTTP privát csoportbeli társviszony-létesítéssel kombinálva HTTP ugyanazon NAT mögötti társviszony-létesítéssel**
        - **HTTP internetes társviszony-létesítéssel kombinálva**
        - **Egyszerű letöltési mód társviszony létesítés nélkül**
        - **Megkerülő mód**

2. Az új profil hozzárendelése eszközök és a felhasználók, a meglévő szoftverek frissítési kört. [A profil hozzárendelése](device-profile-assign.md) felsorolja azokat a lépéseket.

3. A meglévő szoftverek gyűrű konfigurációjának törlése:
    1. Az Intune-ban nyissa meg **szoftverfrissítések** > Windows 10-es frissítési körök.
    2. A listában válassza ki a frissítési kört.
    3. A beállítások, állítsa be a **kézbesítésoptimalizálásos letöltési mód** való **nincs konfigurálva**.
    4. **OK** > **mentése** a módosításokat.

## <a name="next-steps"></a>További lépések

[A profil hozzárendelése](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md) annak állapotát.
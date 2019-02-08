---
title: Kézbesítésoptimalizálási beállításait a Windows 10-beli Microsoft Intune - ban |} A Microsoft Docs
description: 'Konfigurálja a szoftverfrissítések hogyan érkeznek az eszközök a kézbesítési optimalizálás cloud services elérhető Windows 10-es és újabb rendszerű eszközök használatával. Az Intune-ban hozzon létre egy konfigurációs profil frissítések telepítése az internetről. Lásd még: cserélje le a meglévő frissítési körök kézbesítési optimalizálás profillal.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f335c8acf9e979366fe75d1a3da2318b7ec46400
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836693"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>A Windows 10 (és újabb) kézbesítésoptimalizálási beállításait a Microsoft Intune-ban

> [!NOTE]
> **Szoftverfrissítések – a Windows 10-es frissítési körök** helyébe a **kézbesítésoptimalizálás** beállításait. A meglévő frissítési körök használatával módosítható a **kézbesítésoptimalizálás** beállításait. [Helyezze át meglévő frissítési körök kézbesítésoptimalizálás](#move-existing-update-rings-to-delivery-optimization) (a jelen cikkben) felsorolja azokat a lépéseket. 


Ez a funkció az alábbi platformra vonatkozik:

- Windows 10 és újabb

Ez a cikk és az összes a kézbesítésoptimalizálási beállításait konfigurálhatja a Windows 10-es eszközök ismerteti. Ezek a beállítások hozzá eszközkonfigurációs profil, és ezután hozzárendelt vagy az eszközöket a Microsoft Intune segítségével telepítve.

[Kézbesítésoptimalizálás frissíti](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) egy nagyszerű forrás, amely további tudnivalók a kézbesítésoptimalizálás a Windows 10-es.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.

2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.

3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki a platformot:  

        - **Windows 10 és újabb**

    - **Profil típusa**: Válassza ki **kézbesítésoptimalizálás**.
    - **Beállítások**: Válassza ki, hogyan szeretné letölteni a frissítéseket. A választható lehetőségek: 

        - **Nincs konfigurálva**: Frissítsenek eszközeiket a saját módszereivel használni, akkor a **Windows-frissítések** vagy **kézbesítésoptimalizálás** érhető el az operációs rendszer beállításait.
        - **Csak HTTP, nincs társviszony-létesítés**: Frissítések letöltése csak az internetről. Nem kap a frissítések más számítógépeket a hálózaton (nevű társviszony-létesítési vagy társ-társ).
        - **HTTP társviszony-létesítéssel kombinálva a ugyanazon NAT mögötti**: Frissítések letöltése az internetről, és a hálózat más számítógépeiről. 
        - **HTTP privát csoportbeli társviszony-létesítéssel**: Társviszony-létesítés történik az ugyanazon Active Directory-hely (ha van ilyen), vagy ugyanabban a tartományban lévő eszközökön. Ha ezt a lehetőséget választja, a hálózati címfordítás (NAT) IP-címek társviszony-létesítés átlép.
        - **HTTP internetes társviszony-létesítéssel**: Frissítések letöltése az internetről, és a hálózat más számítógépeiről.
        - **Egyszerű letöltési mód társviszony létesítés nélkül**: Az internetről, közvetlenül a frissítés tulajdonosa, például a Microsoft a lekérdezi a frissítéseket. Ez nem lépjen kapcsolatba a kézbesítési optimalizálás cloud services.
        - **Megkerülő mód**: Frissítések letöltése a háttérben futó intelligens átviteli szolgáltatás (BITS) használatával. Ne használja a kézbesítés optimalizálása.

4. Amikor végzett, válassza ki a **OK** > **létrehozás** a módosítások mentéséhez.

A profil jön létre, és megjelenik a listában. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Helyezze át meglévő frissítési körök kézbesítésoptimalizálás

**Szoftverfrissítések – a Windows 10-es frissítési körök** helyébe a **kézbesítésoptimalizálás** beállításait. A meglévő frissítési körök használatával könnyedén módosítható a **kézbesítésoptimalizálás** beállításait. lépések:

1. Kézbesítési optimalizálás konfigurációs profil létrehozása:

    1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok** > **profil létrehozása**.
    2. Adja meg a következő tulajdonságokat:

        - **Név**: Adja meg az új profil leíró nevét.
        - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
        - **Platform**: Válassza ki **Windows 10 és újabb**.
        - **Profil típusa**: Válassza ki **kézbesítésoptimalizálás**.
        - **Beállítások**: A **kézbesítésoptimalizálásos letöltési mód**, válassza ki a meglévő szoftverek frissítési kör által használt azonos módot. A választható lehetőségek:
            - **Nincs konfigurálva**
            - **Csak HTTP, nincs társviszony-létesítés**
            - **A HTTP az ugyanazon NAT mögötti társviszony-létesítéssel kombinálva**
            - **HTTP privát csoportbeli társviszony-létesítéssel kombinálva**
            - **HTTP internetes társviszony-létesítéssel kombinálva**
            - **Egyszerű letöltési mód társviszony létesítés nélkül**
            - **Megkerülő mód**

2. Az új profil hozzárendelése eszközök és a felhasználók, a meglévő szoftverek frissítési kört. [A profil hozzárendelése](device-profile-assign.md) felsorolja azokat a lépéseket.

3. A meglévő szoftverek gyűrű konfigurációjának törlése:
    1. Az Intune-ban nyissa meg **szoftverfrissítések** > Windows 10-es frissítési körök.
    2. A listában válassza ki a frissítési kört.
    3. Állítsa be a beállítások **kézbesítésoptimalizálásos letöltési mód** való **nincs konfigurálva**.
    4. **OK** > **mentése** a módosításokat.

## <a name="next-steps"></a>További lépések

[A profil hozzárendelése](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md) annak állapotát.

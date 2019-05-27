---
title: Kézbesítésoptimalizálási beállításait a Windows 10-beli Microsoft Intune - ban |} A Microsoft Docs
description: 'Állítsa be, hogyan használja az Intune-nal felügyelt Windows 10 rendszerű eszközökön a kézbesítésoptimalizálás. Az Intune-ban hozzon létre egy konfigurációs profil frissítések telepítése az internetről. Lásd még: cserélje le a meglévő frissítési körök kézbesítési optimalizálás profillal.'
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: d927c886bbb3f82c18d5873a86fc427d00d96337
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042640"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Kézbesítésoptimalizálási beállításait a Microsoft Intune-ban

Az Intune-nal kézbesítésoptimalizálási beállításait a Windows 10-es eszközök esetén használhatja, ha sávszélesség-használat csökkentésére, amikor töltse le azokat az eszközöket, alkalmazásokat és frissítéseket. Kézbesítésoptimalizálás a eszközkonfigurációs profil részeként van konfigurálva.  

Ez a cikk ismerteti, hogyan eszközkonfigurációs profil részeként kézbesítésoptimalizálási beállításait konfigurálja. Miután létrehozott egy profilt, majd rendelje hozzá, vagy a profil telepítése a Windows 10 rendszerű eszközökre. 

A kézbesítésoptimalizálási beállításait az Intune által támogatott listáját lásd: [kézbesítésoptimalizálási beállításait az Intune-ban](delivery-optimization-settings.md).  

Kézbesítésoptimalizálás a Windows 10-es kapcsolatos további információkért lásd: [kézbesítésoptimalizálás frissíti](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) a Windows dokumentációjában.  


> [!NOTE]
> **Szoftverfrissítések – a Windows 10-es frissítési körök** helyébe a **kézbesítésoptimalizálás** beállításait. A meglévő frissítési körök használatával módosítható a **kézbesítésoptimalizálás** beállításait. [Helyezze át meglévő frissítési körök kézbesítésoptimalizálás](#move-existing-update-rings-to-delivery-optimization) (a jelen cikkben) 
## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.

2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.

3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki a platformot:  

        - **Windows 10 és újabb**

    - **Profil típusa**: Válassza ki **kézbesítésoptimalizálás**.
    - **Beállítások**: Frissítések és alkalmazások letöltéséhez módját meghatározó beállításokat. Rendelkezésre álló beállításokkal kapcsolatos további információkért lásd: [kézbesítésoptimalizálási beállításait az Intune-ban](delivery-optimization-settings.md).

4. Amikor végzett, válassza ki a **OK** > **létrehozás** a módosítások mentéséhez.

A profil jön létre, és megjelenik a listában. Ezután [rendelje hozzá a profilt](device-profile-assign.md) , majd [állapotát nyomon](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Helyezze át meglévő frissítési körök kézbesítésoptimalizálás

**Kézbesítésoptimalizálás** beállítások csere **szoftverfrissítések – a Windows 10-es frissítési körök**. A meglévő frissítési körök használatával könnyedén módosítható a **kézbesítésoptimalizálás** beállításait. Karbantartása ugyanazokat a beállításokat, amikor kézbesítési optimalizálás profilt hoz létre, használja ugyanazt *kézbesítésoptimalizálásos letöltési mód* majd állítsa be ugyanazokat a beállításokat, akkor már használja. Azonban lehet váltani, konfigurálja újra a kézbesítésoptimalizálási beállításait előnyeit a teljes tartomány hozzáadása a beállításokat, amelyeket a kézbesítésoptimalizálás profilt kezelheti.

1. Kézbesítési optimalizálás konfigurációs profil létrehozása:

    1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok** > **profil létrehozása**.
    2. Adja meg a következő tulajdonságokat:

        - **Név**: Adja meg az új profil leíró nevét.
        - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
        - **Platform**: Válassza ki **Windows 10 és újabb**.
        - **Profil típusa**: Válassza ki **kézbesítésoptimalizálás**.
        - **Beállítások**: A **kézbesítésoptimalizálásos letöltési mód**, hacsak nem módosíthatja a beállításokat, az eszközök a alkalmazni szeretné a meglévő szoftverek frissítési kör által használt azonos módot válassza. A választható lehetőségek:
            - **Nincs konfigurálva**
            - **Csak HTTP, nincs társviszony-létesítés**
            - **A HTTP az ugyanazon NAT mögötti társviszony-létesítéssel kombinálva**
            - **HTTP privát csoportbeli társviszony-létesítéssel kombinálva**
            - **HTTP internetes társviszony-létesítéssel kombinálva**
            - **Egyszerű letöltési mód társviszony létesítés nélkül**
            - **Megkerülő mód**
    3. Konfigurálja az esetleges egyéb beállításokat, előfordulhat, hogy szeretné kezelni.
1. Az új profil hozzárendelése eszközök és a felhasználók, a meglévő szoftverek frissítési kört. [A profil hozzárendelése](device-profile-assign.md) felsorolja azokat a lépéseket.

3. A meglévő szoftverek gyűrű konfigurációjának törlése:
    1. Az Intune-ban nyissa meg **szoftverfrissítések** > Windows 10-es frissítési körök.
    2. A listában válassza ki a frissítési kört.
    3. Állítsa be a beállítások **kézbesítésoptimalizálásos letöltési mód** való **nincs konfigurálva**.
    4. **OK** > **mentése** a módosításokat.

## <a name="next-steps"></a>További lépések

[A profil hozzárendelése](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md) annak állapotát.  
Nézet a [kézbesítésoptimalizálási beállításait](delivery-optimization-settings.md) az Intune-hoz.

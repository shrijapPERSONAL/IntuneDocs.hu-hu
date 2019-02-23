---
title: Az iOS-szoftverfrissítési szabályzatok konfigurálása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Konfigurációs szabályzat létrehozása vagy felvétele a Microsoft Intune-ban, amellyel korlátozhatja, mikor kerüljenek automatikusan telepítésre az Intune által felügyelt, vagy ellenőrzött iOS-eszközök szoftverfrissítései. Megadhatja azokat a dátumokat és időpontokat, amelyeknél nem szeretné, hogy települjenek a frissítések. Ezt a szabályzatot csoportokhoz, felhasználókhoz és eszközökhöz is hozzárendelheti, és ellenőrizheti az esetleges telepítési hibákat is vele.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/06/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d39f4c541fd7ccf5ab2d09fdcf4f871ba3ee639c
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742397"
---
# <a name="add-ios-software-update-policies-in-intune"></a>IOS-szoftverfrissítési szabályzatok hozzáadása az Intune-ban

A-frissítési szabályzatokkal kikényszerítheti a legújabb elérhető rendszerfrissítések automatikus telepítését a felügyelt iOS-eszközökön. A szabályzat beállításakor megadhatja azokat a napokat és időpontokat, amikor nem szeretné, hogy az eszközök frissítéseket telepítsenek. 

Ez a funkció az alábbiakra vonatkozik:

- iOS 10.3 vagy újabb (csak felügyelt eszköz)

Az eszköz körülbelül 8 óránként jelentkezik be az Intune-ba. Ha az eszköz elérhető frissítést talál a megadott korlátozott időszakokon kívül, akkor letölti és telepíti a legújabb rendszerfrissítéseket. Az eszköz frissítéséhez nincs szükség felhasználói beavatkozásra. A szabályzat nem akadályozza meg, hogy a felhasználó manuálisan frissítse az operációs rendszert.

## <a name="configure-the-policy"></a>A szabályzat konfigurálása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** > **Létrehozás** lehetőséget.
3. Adja meg a következő beállításokat:

    - **Név**: Adja meg a szoftver frissítések házirend nevét. Például írja be a következőt: `iOS restricted update times`.
    - **Description** (Leírás): Adja meg a házirend leírását. A beállítás használata nem kötelező, de ajánlott.

4. Válassza ki **beállítások > konfigurálása**. Adja meg a következő beállításokat:

    - **Válassza ki a frissítések telepítésének elkerüléséhez alkalommal**: Adja meg egy korlátozott időkeretet, amikor nem kényszerített telepíti a frissítéseket. A korlátozott időtartamon beállításakor adja meg a következő adatokat:

      - **Nap**: Válassza ki a nap, hét, ha nincsenek telepítve a frissítések. Ellenőrizze például, hétfőn, szerdán és pénteken ahhoz, hogy ezek a napok való telepítése is.
      - **Időzóna**: Válasszon időzónát.
      - **Kezdési idő**: Válassza ki a korlátozott időkeret kezdési idejét. Adja meg például 05-kor, így a frissítések nincsenek telepítve, 05-kor kezdődik.
      - **Befejezési idő**: Válassza ki a korlátozott időkeret befejezési időpontja. Adja meg például 1 AM, így a frissítések telepíthetők, hogy 1 Órakor indítása.

    - **Látható-e a szoftverfrissítések a végfelhasználók számára nem változik az ütemezett frissítések késleltetése (nap)**: 

      **Ez a beállítás át [Eszközkorlátozások](device-restrictions-ios.md#general). Ezen a helyen, a portálon eltávolítjuk**. Egy rövid ideig a meglévő szabályzatok itt módosítható. Miután körülbelül egy hónap, ezzel a beállítással a meglévő szabályzatok törlődik.

      Szeretné korlátozni a hatás, a következőket javasoljuk:
        - Távolítsa el a meglévő szabályzat ezen a helyen, a portálon.
        - Hozzon létre egy új [eszközkorlátozási szabályzatot](device-restrictions-ios.md#general).
        - A céloznia ugyanazokat a felhasználókat, mint az eredeti házirenddel.

      Ütközés esetén ez a beállítás nem módosítja *, kivéve, ha* a két érték azonosak. Ütközés elkerülése érdekében ügyeljen arra, módosítsa vagy távolítsa el a meglévő szabályzatot erről a helyről a portálon.

5. Válassza ki **OK** > **létrehozás** a módosítások mentéséhez és a szabályzat létrehozásához.

A szabályzat létrejön, és megjelenik a szabályzatok listájában. 

> [!NOTE]
> Az Apple mobileszköz-kezelése nem teszi lehetővé, hogy a készülékek számára kikényszerítse a frissítések adott időpontban történő telepítését.

## <a name="change-the-restricted-times-for-the-policy"></a>A korlátozott időtartamok módosítása a szabályzatban

1. A **Szoftverfrissítések** területen válassza **iOS-frissítési szabályzatok** lehetőséget.
2. Válasszon ki egy meglévő szabályzatot > **Tulajdonságok**.
3. Frissítse a korlátozás időpontjait:

    1. Válassza ki a hét napjait
    2. Válassza ki, hogy melyik időzóna szerint kívánja alkalmazni a szabályzatot
    3. Adja meg a feketelistás órák kezdő és záró idejét

    > [!NOTE]
    > Ha a **Kezdési idő** és a **Befejezési idő** egyaránt déli 12 óra, akkor a karbantartási időszak ellenőrzése kikapcsolt állapotban lesz.

## <a name="assign-the-policy-to-users"></a>A szabályzat hozzárendelése a felhasználókhoz

A meglévő szabályzatokat csoportokhoz, felhasználókhoz vagy eszközökhöz rendelheti. Hozzárendelés után a szabályzatok alkalmazásra fognak kerülni.

1. A **Szoftverfrissítések** területen válassza **iOS-frissítési szabályzatok** lehetőséget.
2. Válasszon ki egy meglévő szabályzatot > **Hozzárendelések**. 
3. Válassza ki azokat az Azure Active Directory csoportokat, felhasználókat vagy eszközöket, amelyeknél alkalmazni vagy kizárni szeretné a szabályzatot.
4. Válassza a **Mentés** lehetőséget a szabályzat csoportok felé történő telepítéséhez.

A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök frissítési megfelelőségét. Ez a szabályzat a felhasználó nélküli eszközöket is támogatja.

## <a name="monitor-device-installation-failures"></a>Eszközök telepítési hibáinak figyelése
A <!-- 1352223 -->
**Szoftverfrissítések** > **iOS-eszközök telepítési hibái** területen láthatja azoknak a felügyelt iOS-eszközöknek a listáját, amelyekre érvényben van egy frissítési szabályzat, de a frissítésük nem járt sikerrel. Minden eszköz mellett látható egy állapotleírás, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. A kifogástalan, naprakész eszközök nem jelennek meg a listában. A naprakész eszközökön telepítve van az a legújabb frissítés, amelyet az eszköz támogatni képes.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
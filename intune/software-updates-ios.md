---
title: Az iOS-szoftverfrissítési szabályzatok konfigurálása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Konfigurációs szabályzat létrehozása vagy felvétele a Microsoft Intune-ban, amellyel korlátozhatja, mikor kerüljenek automatikusan telepítésre az Intune által felügyelt, vagy ellenőrzött iOS-eszközök szoftverfrissítései. Megadhatja azokat a dátumokat és időpontokat, amelyeknél nem szeretné, hogy települjenek a frissítések. Ezt a szabályzatot csoportokhoz, felhasználókhoz és eszközökhöz is hozzárendelheti, és ellenőrizheti az esetleges telepítési hibákat is vele.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: b9cc34b2fa45ae447a015f1b3105081041bd0afe
ms.sourcegitcommit: 0a2e737c5520c1a1dec5d732e5df52b5614b27e1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268838"
---
# <a name="configure-ios-update-policies-in-intune"></a>Az iOS-es frissítési szabályzatok konfigurálása az Intune-ban

A-frissítési szabályzatokkal kikényszerítheti a legújabb elérhető rendszerfrissítések automatikus telepítését a felügyelt iOS-eszközökön. Ez a funkció csak felügyelt eszközök esetén használható. A szabályzat beállításakor megadhatja azokat a napokat és időpontokat, amikor nem szeretné, hogy az eszközök frissítéseket telepítsenek. 

Az eszköz körülbelül 8 óránként jelentkezik be az Intune-ba. Ha az eszköz elérhető frissítést talál a megadott korlátozott időszakokon kívül, akkor letölti és telepíti a legújabb rendszerfrissítéseket. Az eszköz frissítéséhez nincs szükség felhasználói beavatkozásra. A szabályzat nem akadályozza meg, hogy a felhasználó manuálisan frissítse az operációs rendszert.

Ez a funkció iOS 10.3-as vagy újabb rendszerű eszközök esetében érhető el.

## <a name="configure-the-policy"></a>A szabályzat konfigurálása
1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** > **Létrehozás** lehetőséget.
4. Adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** lehetőséget. 

    Adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére. Ezekkel a beállításokkal megadhatja azt az időkeretet, amikor a korlátozás érvényben lesz. Beállíthatja a hét napjait, az időzónát, a kezdési időt és a befejezési időt.

6. A módosítások mentéséhez válassza az **OK** gombot. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához.

A szabályzat létrejön, és megjelenik a szabályzatok listájában. Az Apple mobileszköz-kezelése nem teszi lehetővé, hogy a készülékek számára kikényszerítse a frissítések adott időpontban történő telepítését. 

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


---
title: Az iOS-szoftverfrissítési szabályzatok konfigurálása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Konfigurációs szabályzat létrehozása vagy felvétele a Microsoft Intune-ban, amellyel korlátozhatja, mikor kerüljenek automatikusan telepítésre az Intune által felügyelt, vagy ellenőrzött iOS-eszközök szoftverfrissítései. Megadhatja azokat a dátumokat és időpontokat, amelyeknél nem szeretné, hogy települjenek a frissítések. Ezt a szabályzatot csoportokhoz, felhasználókhoz és eszközökhöz is hozzárendelheti, és ellenőrizheti az esetleges telepítési hibákat is vele.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.openlocfilehash: 12b387a5c09e0d009fa5014ff355104f6bff71f3
ms.sourcegitcommit: e0d55bdda1a818ffe4cfc0ef0592833e22f65a89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290638"
---
# <a name="configure-ios-update-policies-in-intune"></a>Az iOS-es frissítési szabályzatok konfigurálása az Intune-ban

A-frissítési szabályzatokkal kikényszerítheti a legújabb elérhető rendszerfrissítések automatikus telepítését a felügyelt iOS-eszközökön. Ez a szolgáltatás csak felügyelt eszközök esetén használható. A szabályzat beállításakor megadhatja azokat a napokat és időpontokat, amikor nem szeretné, hogy az eszközök frissítéseket telepítsenek. 

Az eszköz körülbelül 8 óránként jelentkezik be az Intune-ba. Ha az eszköz elérhető frissítést talál a megadott korlátozott időszakokon kívül, akkor letölti és telepíti a legújabb rendszerfrissítéseket. Az eszköz frissítéséhez nincs szükség felhasználói beavatkozásra. A szabályzat nem akadályozza meg, hogy a felhasználó manuálisan frissítse az operációs rendszert.

A szolgáltatás az iOS 10.3-as és újabb rendszerű eszközöket támogatja. A késleltetési beállítás az iOS 11.3-as és újabb verzióiban érhető el.

## <a name="configure-the-policy"></a>A szabályzat konfigurálása
1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** > **Létrehozás** lehetőséget.
4. Adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** lehetőséget. 

    Adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére. Ezekkel a beállításokkal megadhatja azt az időkeretet, amikor a korlátozás érvényben lesz. Konfigurálhatja a hét **napjait**, az **időzónát**, a **kezdési időt**, a **befejezési időt** és **a szoftverfrissítések láthatóságának késleltetését (napokban)** a megadott felhasználókhoz. A szoftverfrissítések késleltetéséhez 1 és 90 nap közötti értéket adhat meg. A szoftverfrissítések késleltetésének megszüntetéséhez írja be a 0 értéket. Ezek a frissítési beállítások csak felügyelt iOS-eszközökre érvényesek.

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


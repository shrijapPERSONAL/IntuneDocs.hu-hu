---
title: "Egyéni beállítások az Intune-ban Windows Holographic for Business esetén"
titlesuffix: Azure portal
description: "A Windows Holographic for Business egyéni profiljaiban használható egyéni beállítások ismertetése.”"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>A Windows Holographic for Business rendszert futtató eszközökre vonatkozó egyéni eszközbeállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 A Microsoft Intune Windows Holographic for Businesshez készült **egyéni** profiljával az eszközfunkciók szabályozására szolgáló OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállításokat lehet telepíteni. A Windows Holographic for Business számos konfigurációs szolgáltatásból származó beállítást támogat. A konfigurációszolgáltatásokról a [Bevezetés a konfigurációszolgáltatásokba (CSP) informatikai szakértők számára](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) című témakörben olvashat. A Windows Holographic által támogatott konkrét konfigurációszolgáltatók listáját a [Windows Holographic által támogatott CSP-k](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben találja.

Ha egy adott beállítást keres, ne feledje, a [Windows Holographic for Business eszközkorlátozási profil](device-restrictions-windows-holographic.md) számos olyan beállítást tartalmaz, amely be van építve az Intune-ba, és nem követeli meg egyéni értékek megadását.

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. OMA-URI beállítások hozzáadásához a **Profil létrehozása** panelen válassza a **Beállítások** lehetőséget.
3. Az **Egyéni OMA-URI beállítások** panelen a **Hozzáadás** elemre kattintva adhat meg új értéket. Az **Exportálás** elemre kattintva az összes Ön által konfigurált értéket exportálhatja egy csv-fájlba.
4. Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat. A rendelkezésre álló beállításokat a témakörben alább található listában tekintheti át:
    - **Beállítás neve** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Beállítás leírása** – Itt adhatja meg a beállítás leírását (nem kötelező).
    - **Adattípus** – Válasszon egyet a következő lehetőségek közül:
        - **Karakterlánc**
        - **Karakterlánc (XML)**
        - **Dátum és időpont**
        - **Egész**
        - **Lebegőpontos szám**
        - **Logikai**
    - **OMA-URI (megkülönbözteti a kis- és nagybetűket)** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.
5. Miután elkészült, lépjen vissza a **Profil létrehozása** panelre, és kattintson a **Létrehozás** elemre.
Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="supported-custom-settings"></a>Támogatott egyéni beállítások

A Windows Holographic for Business az alábbi egyéni beállításokat támogatja:


|Beállítás neve|OMA-URI|Adattípus  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Egész szám (0 – nem engedélyezett, 1 – engedélyezett)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Egész szám (0 – nem engedélyezett, 1 – engedélyezett)|



## <a name="how-to-find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A [Windows Holographic for Business által támogatott CSP-k](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) című cikkben megtalálja Windows Holographic által támogatott konfigurációszolgáltatók teljes listáját. Nem minden beállítás kompatibilis a Windows Holographic összes verziójával. A Windows-témakörben szereplő táblázatból kiolvasható, hogy az egyes konfigurációszolgáltatók mely verziókat támogatják.

Ezen felül az Intune sem támogatja a témakörben felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó témakört. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.



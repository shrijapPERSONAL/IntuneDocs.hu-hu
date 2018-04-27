---
title: Egyéni Microsoft Intune-beállítások Windows 10 rendszert futtató iOS-eszközökhöz
titlesuffix: ''
description: Az egyéni Windows 10-profilban használható egyéni beállítások ismertetése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36705c49a55c88c41470feaad14520e900dcb3dd
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Egyéni Microsoft Intune-beállítások Windows 10 rendszert futtató iOS-eszközökhöz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 A Microsoft Intune Windows 10-hez és Windows 10 Mobile-hoz készült **egyéni** profiljával az eszközfunkciók szabályozására szolgáló OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállításokat lehet telepíteni. A Windows 10 számos konfigurációszolgáltatói beállítást tesz elérhetővé, ilyen például a [Szabályzat-konfigurációszolgáltató (Policy Configuration Service Provider, Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Ha egy adott beállítást keres, ne feledje, a [Windows 10-es eszközkorlátozási profil](device-restrictions-windows-10.md) számos olyan beállítást tartalmaz, amely be van építve az Intune-ba, és nem követeli meg egyéni értékek megadását.

## <a name="configure-custom-settings"></a>Egyéni beállítások konfigurálása

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
1. Az **Egyéni OMA-URI beállítások** panelen a **Hozzáadás** elemre kattintva adhat meg új értéket. Az **Exportálás** elemre kattintva az összes Ön által konfigurált értéket exportálhatja egy csv-fájlba.
1. Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat. A rendelkezésre álló beállításokat a témakörben alább található listában tekintheti át:
    - **Név** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Leírás** – Itt adhatja meg a beállítás leírását (nem kötelező).
    - **OMA-URI (megkülönbözteti a kis- és nagybetűket)** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Adattípus** – Válasszon egyet a következő lehetőségek közül:
        - **Karakterlánc**
        - **Karakterlánc (XML)**
        - **Dátum és időpont**
        - **Egész**
        - **Lebegőpontos szám**
        - **Logikai**
        - **Base64**
    - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket vagy fájlt.
1. Ha elkészült, válassza az **OK** gombot, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** gombot.
Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="example"></a>Példa
A következő képernyőképen a **Connectivity/AllowVPNOverCellular** beállítást engedélyezték. Ez lehetővé teszi, hogy a Windows 10-es eszköz VPN-kapcsolatot nyisson meg mobilhálózaton keresztül.

> ![VPN-beállításokat tartalmazó egyéni szabályzat – példa](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A Windows 10 által támogatott konfigurációszolgáltatók (CSP-k) teljes listája a Windows dokumentációs könyvtárának [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (A konfigurációszolgáltatók referenciája) című témakörében található meg.

Nem minden beállítás kompatibilis a Windows 10 összes verziójával. A Windows-cikkben szereplő táblázatból kiolvasható, hogy az egyes konfigurációszolgáltatók mely verziókat támogatják.

Ezen felül az Intune sem támogatja a témakörben felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó cikket. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.

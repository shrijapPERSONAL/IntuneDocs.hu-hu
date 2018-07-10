---
title: Egyéni beállítások Windows 10-es eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: A Microsoft Intune-ban egyéni profil használatával konfigurálhatja a Windows 10 rendszerű eszközök egyéni OMA-URI beállításait.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232826"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Egyéni OMA-URI beállítások Windows 10-es eszközökhöz – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune Windows 10-hez és Windows 10 Mobile-hoz készült **egyéni** profiljával OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállításokat lehet telepíteni. Ezek a beállítások az eszközfunkciók szabályozására szolgálnak. A Windows 10 számos konfigurációszolgáltatói beállítást tesz elérhetővé, ilyen például a [Szabályzat-konfigurációszolgáltató (Policy Configuration Service Provider, Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Ha egy adott beállítást keres, ne feledje, a [Windows 10-es eszközkorlátozási profil](device-restrictions-windows-10.md) számos olyan beállítást tartalmaz, amely be van építve az Intune-ba, és nem követel meg egyéni értékeket.

## <a name="configure-custom-settings"></a>Egyéni beállítások konfigurálása

1. Hozzon létre új konfigurációs profilt az **Egyéni** profiltípus használatával. Ennek módját [Az egyéni eszközbeállítások konfigurálása](custom-settings-configure.md) című cikk lépésenként ismerteti.
2. Új beállítás létrehozásához az **Egyéni OMA-URI beállítások** területen válassza a **Hozzáadás** lehetőséget. Az **Exportálás** elemre kattintva az összes Ön által konfigurált értéket exportálhatja egy csv-fájlba.
3. Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat:

- **Név** – Adjon meg egy egyedi nevet az OMA-URI-beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
- **Leírás** – Itt adhatja meg a beállítás leírását (nem kötelező).
- **OMA-URI (megkülönbözteti a kis- és nagybetűket)**: Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
- **Adattípus**: Válasszon egyet a következő lehetőségek közül:
  - 
  **Sztring**
  - 
  **Sztring (XML)**
  - **Dátum és időpont**
  - **Egész**
  - **Lebegőpontos szám**
  - **Logikai**
  - **Base64**
- **Érték**: Adja meg a megadott OMA-URI-azonosítóhoz társítandó értéket vagy fájlt.

4. Ha elkészült, kattintson az **OK** elemre. A **Profil létrehozása** alatt kattintson a **Létrehozás** lehetőségre. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="example"></a>Példa
A következő példa a **Connectivity/AllowVPNOverCellular** beállítás engedélyezését mutatja be. Ez a beállítás lehetővé teszi, hogy a Windows 10-es eszköz VPN-kapcsolatot nyisson meg mobilhálózaton keresztül.

![VPN-beállításokat tartalmazó egyéni szabályzat – példa](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>A konfigurálható szabályzatok megkeresése

A Windows 10 által támogatott konfigurációszolgáltatók (CSP-k) teljes listája a [Konfigurációszolgáltatók referenciája](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) című témakörében található meg.

Nem minden beállítás kompatibilis a Windows 10 összes verziójával. A [Konfigurációszolgáltatók referenciája](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) című témakörből megtudhatja, hogy az egyes CSP-k mely verziókat támogatják.

Ezen felül az Intune sem támogatja a felsorolt beállítások mindegyikét. Ha tudni szeretné, hogy az Intune támogatja-e a kívánt beállítást, nyissa meg a beállításhoz tartozó cikket. Minden beállítás oldalán szerepelnek a támogatott műveletek. Az Intune használatához a beállításnak támogatnia kell a **Hozzáadás** vagy a **Csere** műveletet.

---
title: Endpoint Protection-beállítások konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: macOS- vagy Windows 10-eszközprofil az Intune-ban való létrehozásakor létrehozhat Endpoint Protection-beállításokat is.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: c13c5d71d1ff631d7a3c84cd3f62037569757917
ms.sourcegitcommit: bc5e4dff18f5f9b79077a888f8a58dcc490708c0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975764"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Endpoint Protection-beállítások hozzáadása az Intune-ban

Az Intune-nal kezelheti a közös endpoint protection biztonsági funkciókat az eszközökön, beleértve a eszközkonfigurációs profilok használhatja:
- Tűzfal 
- BitLocker
- Alkalmazások engedélyezéséről és tiltásáról  
- A Windows Defender és a titkosítás

Létrehozhat például egy olyan Endpoint Protection-profilt, amely csak a Maces App Store áruházból származó alkalmazásokat engedélyezi telepíteni a macOS felhasználók számára. Vagy engedélyezheti a Windows SmartScreent a Windows 10-eszközök alkalmazásain.

Egy profil létrehozása előtt tekintse át a következő cikkek, amelyek részletesen, minden támogatott platformhoz az endpoint protection-beállítások az Intune kezelhető: 
   - [macOS-beállítások](endpoint-protection-macos.md)
   - [Windows 10-beállítások](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
4. Adja meg az Endpoint Protection-profil **nevét** és **leírását**.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre egyéni beállításokat szeretne alkalmazni. Jelenleg az alábbi platformokra vonatkozóan lehet eszközkorlátozási beállításokat megadni:
   - **macOS**
   - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listából válassza az **Endpoint Protection** lehetőséget. 
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Lásd:
   - [macOS-beállítások](endpoint-protection-macos.md)
   - [Windows 10-beállítások](endpoint-protection-windows-10.md)  

8. Beállításainak megadása után a alkalmazni, válassza ki a **létrehozás** a a **profil létrehozása** lapot.

   Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó lapon. Ha csoportokhoz szeretné hozzárendelni a profilt, tekintse meg az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikket.


## <a name="next-steps"></a>További lépések  

Ha csoportokhoz szeretne hozzárendelni egy profilt, tekintse meg az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikket.

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
ms.openlocfilehash: cbac3627a17fb28f7ec0bf06898038a6c6001ac8
ms.sourcegitcommit: f8bbd9bac2016a77f36461bec260f716e2155b4a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/16/2019
ms.locfileid: "65733044"
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

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Windows 10-eszközökre vonatkozó egyéni Tűzfalszabályok hozzáadása  

A Windows Defender-tűzfal konfigurálásakor olyan profilt, amely a Windows 10-es endpoint protection szabályokat tartalmaz részeként egyéni szabályok is konfigurálható a tűzfalakhoz. Egyéni szabályok bontsa ki az előre meghatározott készletét támogatja a Windows 10-es tűzfalszabályok lehetővé teszik.  

A profilok az egyéni tűzfalszabályok tervezésekor vegye figyelembe az alábbi adatokat, amelyek befolyásolhatják, hogyan válassza a csoport tűzfalszabályok a profilok:  
- Az egyes profilok legfeljebb 150 tűzfalszabályok támogatja. Ha több mint 150 szabályokat használ, létre kell hoznia további, minden egyes legfeljebb 150 szabályokat.  
- Az egyes profilok, ha egyetlen szabály nem lép érvénybe, az összes szabály, hogy a feladatátvételben profil, és egyetlen szabály sem lépnek az eszközön.  
- Amikor egy szabály sikertelen a alkalmazni, a profilban található összes szabály van jelentve. Az Intune nem tudja azonosítani, melyik egyéni szabály sikertelen volt. 

A Windows Intune képes kezelni a tűzfalszabályok részletezett [tűzfal-konfigurációs szolgáltató]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) (CSP). Tekintse át a Windows 10 rendszerű eszközökhöz az Intune által támogatott egyéni tűzfal beállításait, lásd: [egyéni tűzfal-szabályok](endpoint-protection-windows-10.md#custom-firewall-rules).   

#### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Endpoint protection-profil egyéni tűzfal-szabályok hozzáadása  

1. Az Intune-ban nyissa meg **eszközkonfiguráció** > **profilok** > **profil létrehozása**.  

2. A *Platform*, jelölje be **Windows 10 és újabb**, majd *profiltípus* kiválasztása **az Endpoint protection**.  

3. Válassza ki **Windows Defender-tűzfal** a konfigurációs lap megnyitásához majd *tűzfalszabályok* kiválasztása **Hozzáadás** megnyitásához a **szabálylétrehozása**lapot.  

4. Adja meg a tűzfalszabály beállítása beállításait, és válassza ki **OK** mentéséhez. A rendelkezésre álló egyéni szabály tűzfalbeállítások dokumentáció áttekintéséhez lásd: [egyéni tűzfal-szabályok](endpoint-protection-windows-10.md#custom-firewall-rules).  

5. Miután a szabály menti, az megjelenik a *Windows Defender-tűzfal* szabályok listáján a lapot.  

6. A szabály módosításához válassza ki a szabályt a listáról, nyissa meg a **szabály szerkesztése** lapot.  

7. A profil a szabály törléséhez válassza ki a három pontra **(...)**  a szabályt, és válassza ki a **törlése**.  

8. Mely szabályok megjelenítése sorrendjének módosításához jelölje ki a *felfelé vagy lefelé mutató nyíl* ikonra a szabálylista tetején.  





## <a name="next-steps"></a>További lépések  

Ha csoportokhoz szeretne hozzárendelni egy profilt, tekintse meg az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikket.

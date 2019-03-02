---
title: A frissítések megfelelőségének jelentések használata a Microsoft Intune Windows-frissítések |} A Microsoft Docs
description: Jelentés adatainak megtekintése a Windows frissítéseket telepít az Intune-nal a OMS frissítési megfelelőségét.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2a91afc016fe3847488968cbaef08feef8cf4cfc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238921"
---
# <a name="intune-compliance-reports-for-updates"></a>Frissítések az Intune megfelelőségi jelentések
A Windows 10-eszközökre telepíti központilag a Windows update Intune használatakor a frissítési megfelelőség szempontjából, az Intune-ban vagy egy ingyenes megoldási részleteinek megtekintése nevű *Update Compliance*, amelynek része a Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Az Intune-nal
A konfigurált Windows 10-es frissítési körök telepítési állapotát tekinteni: 
1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com/).
2. Kattintson a **Minden szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
3. Válassza a **Szoftverfrissítések** > **Áttekintés** lehetőséget. Itt általános információkat találhat minden hozzárendelt frissítési kör állapotáról.
4. Nyissa meg az alábbi jelentések valamelyikét:  

   **Minden frissítési körhöz**:
   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen
   2. A **Figyelés** szakaszban válassza a **Frissítési körönkénti telepítési állapot** lehetőséget.  

   **Meghatározott frissítési körökhöz**:  

   1. A **Szoftverfrissítések** > **Windows 10-es frissítési körök** területen válassza ki az áttekinteni kívánt frissítési kört.  
   2. Az adott frissítési kör adatainak megtekintéséhez a **Figyelés** szakaszban válasszon az alábbi jelentések közül:  
      - **Eszközállapot**  
      - **Felhasználó állapota**  

## <a name="use-update-compliance"></a>Frissítés-megfelelőség
Windows 10-es update Compliance használatával figyelheti [Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor), a Windows Analytics megoldás. Az Azure Portalon keresztül érhető el frissítési megfelelőség szempontjából, és érhető el ingyenes eszközök, amelyek megfelelnek a [Előfeltételek](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Ez a megoldás használata esetén telepít egy kereskedelmi azonosító bármelyik, az Intune-nal felügyelt Windows 10-es eszközök, amelynek meg szeretné jelentés frissítési megfelelőség szempontjából.  

Az Intune-konzolon használja az egyéni szabályzat OMA-URI beállítások konfigurálása a kereskedelmi azonosítót. További információ: [A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-szabályzatbeállítások](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

A kereskedelmi azonosító konfigurálásához az OMA-URI (megkülönbözteti a kis-és nagybetűket) elérési út: *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

Az **OMA-URI beállítások hozzáadása vagy módosítása** alatt például a következő beállítások használhatók:
- **Beállítás neve**: Windows Analytics kereskedelmi azonosító
- **Beállítás leírása**: Kereskedelmi azonosító a Windows Analytics-megoldások konfigurálása
- **OMA-URI** (megkülönbözteti a kis-és nagybetűket): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Adattípus**: Sztring
- **Érték**: \<Használja az OMS-munkaterület Windows-Telemetria lapján látható GUID >
 
> [!NOTE]  
> További információ az MS DM-kiszolgálóról: [DMClient konfigurációs szolgáltató (CSP)]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>További lépések
[Szoftverfrissítések kezelése az Intune-ban](windows-update-for-business-configure.md)


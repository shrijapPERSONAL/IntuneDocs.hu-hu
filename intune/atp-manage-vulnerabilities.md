---
title: A Microsoft Defender ATP – Azure által észlelt biztonsági rések az Intune-nal |} A Microsoft Docs
description: Tekintse meg az biztonsági feladatok és a fenyegetések és biztonsági rések kezelése, az Intune konzolban, a Microsoft Defender komplex veszélyforrások elleni védelem (ATP) a rész kezeléséhez.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 987e3171c4e5c5ba3f15097837e2c018ddc7a4b6
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66049191"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>A Microsoft Defender ATP által azonosított biztonsági rések az Intune-nal  

Az Intune integrálása a Microsoft Defender komplex veszélyforrások elleni védelem (ATP), ATPs fenyegetések és biztonsági rések kezelése (TVM) előnyeit, és az Intune-nal TVM által azonosított végpont gyengeségét javítása. Ez az integráció a kockázatalapú megközelítést biztosít a felderítési és javíthatja a szervizelési válaszidő a környezete biztonsági rések priorizálását.  

[Fenyegetések és biztonsági rések kezelése](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) része [Microsoft Defender komplex veszélyforrások elleni védelem](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Hogyan működik az integráció  

Után az Intune-ban kapcsolódik a Microsoft Defender komplex veszélyforrások elleni védelem, a ATP fenyegetések és a biztonsági rés részletei kap a felügyelt eszközökről.  

A Windows Defender biztonsági központ konzolon ATP biztonsági rendszergazdák tekintse át a végponti biztonsági adatait. A rendszergazdák majd, hogy ez a jelző azt az érintett eszközök szervizelési biztonsági feladatok létrehozásához használja a egyetlen kattintással. A biztonsági feladatok azonnal átadott az Intune-konzolon, ahol Intune-rendszergazdák megtekinthetik azokat. A biztonsági feladat a biztonsági rések, prioritás, állapota és milyen lépéseket kell tennie a biztonsági rések javítása típusát jelöli. Az Intune-rendszergazda úgy dönt, hogy elfogadja vagy elutasítsa a feladatot.  

Elfogadható egy feladatot, amikor az Intune-rendszergazda majd funkcionál, ha Intune útmutatása a biztonsági feladat részeként a biztonsági rések javítása.  

Szervizelési gyakori műveletek a következők:  
- **Blokk** egy alkalmazás futtatása  
- **Üzembe helyezése** az operációs rendszer frissítését, a biztonsági rés elhárításához.  
- **Módosítsa** beállításjegyzékbeli érték.  
- **Tiltsa le** vagy **engedélyezése** hatással vannak a biztonsági rés konfigurációt.  
- **Beavatkozást igényelnek** a rendszergazdát, hogy a fenyegetés figyelmezteti, ha ott nem adja meg a nem megfelelő javaslat.  

Példa-munkafolyamat:  
- Microsoft Defender ATP-ben az alkalmazás neve Contoso Media Player v4 biztonsági rést fel van derítve és rendszergazdai feladatot hoz létre biztonsági, amelyet az alkalmazás frissítéséhez. A Contoso Media player egy nem felügyelt alkalmazást, amely az Intune-ban üzemel.  

  Ez a feladat az Intune-konzolon függőben állapottal jelenik meg:  
  ![Biztonsági tevékenységek listájának megtekintése az Intune-konzolon](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- Az Intune-rendszergazda választja ki a biztonsági feladat a feladat részleteinek megtekintéséhez.  A rendszergazda ezután kiválasztja **elfogadás**, amely frissíti az állapotát az Intune-ban, és az ATP kell *elfogadva*.  
  ![Fogadja el vagy biztonsági tevékenység visszautasítása](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- A rendszergazda ezután javítja a megfelelőséget a feladatot a megadott útmutatás alapján.  Az útmutatót, amely rendelkezik a szükséges javítási típusától függően változik. Ha elérhető, a szervizelési útmutatást tartalmaz hivatkozásokat, nyissa meg a megfelelő ablaktáblák konfigurációk esetén az Intune-ban. 

  Ebben a példában a media player nem egy felügyelt alkalmazást, mert az Intune csak biztosíthat szöveg utasításokat. Ha az alkalmazás felügyelt volt, Intune-ban sikerült meg utasításokat követve töltse le a frissített verzióját, és adjon meg egy hivatkozást, hogy a frissített fájljait is hozzáadhatók a központi telepítés, nyissa meg az alkalmazás központi telepítését. 

- Befejezése a szervizelés után az Intune-rendszergazda megnyílik a biztonsági feladat, és kiválasztja **feladat elvégzése**.  A korrigálás állapota az Intune-hoz, és az ATP, ahol biztonsági rendszergazdák erősítse meg a biztonsági rés módosított állapota frissül.  

## <a name="prerequisites"></a>Előfeltételek  

**Előfizetések**:  
- Microsoft Intune  
- A Microsoft Defender komplex veszélyforrások elleni védelem ([regisztráljon egy ingyenes próbaverzióra](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink).)  

**Az ATP Intune konfigurációk**:  
- Szolgáltatások közötti kapcsolat konfigurálása a Microsoft Defender ATP.  
- Profil típusú eszközmegfelelőségi szabályzat üzembe helyezése **Microsoft Defender ATP-ben (Windows 10 asztali verzió)** az ATP értékelte kockázati majd rendelkező eszközöket.
  Állítsa be az Intune a ATP kapcsolatos információkért lásd: [kényszerítse a megfelelőséget a Microsoft Defender ATP feltételes hozzáférés az Intune-ban](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Biztonsági tevékenységek használata  

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) , majd **eszközbiztonsági** > **biztonsági feladatok**.  
2. Válasszon egy feladatot a listából, nyisson meg egy erőforrás-ablakot, amely a biztonsági feladatról további részleteket jeleníti meg.  
3. A biztonsági feladat erőforrás ablak megtekintésekor választhatja további hivatkozásokat tartalmaz:  
   - FELÜGYELT alkalmazások - nézet, amely ki van téve az alkalmazást. Ha a biztonsági rés több alkalmazásokra vonatkozik, látni fogja a szűrt azon alkalmazások listáját.  
   - -ESZKÖZÖK listájának megtekintése a *sebezhető eszközök*, amely kapcsolat keresztül egy bejegyzést, amelyen további részletek az eszközön lévő biztonsági a.  
   - KÉRELMEZŐ – a hivatkozásra használja az e-mailt küldjön a rendszergazda, aki ezt a feladatot.  
   - Megjegyzések – egyéni üzenetek olvasása a kérelmező által küldött, a biztonsági feladat megnyitásakor.  
4. Válassza ki **elfogadás** vagy **elutasítása** küldhet értesítéseket az ATP a tervezett művelet. Ha nem fogadja el, vagy egy tevékenység elutasítása, elküldheti a megjegyzések, az ATP küldött.  

5. Követő feladat, nyissa meg újra a biztonsági feladat (Ha lezárt), és kövesse a SZERVIZELÉSI részletei a biztonsági rések javítása.  A biztonsági feladat részletes adatait az ATP utasításait a biztonsági rés függenek.  

   Amikor erre lehetőség, a javítással kapcsolatos utasításokat hivatkozásokat tartalmazhat, amelyek az Intune-konzolon nyissa meg a megfelelő konfigurációs objektumok.  

6. A javítási lépések elvégzése után nyissa meg a biztonsági feladat, és válassza **feladat elvégzése**.  Ez a művelet frissíti az Intune és az ATP biztonsági feladat állapotát.  

Sikeres szervizelés után a kockázati kitettség pontszám az ATP vethetők el, a szervizelési eszközök új információkon alapulnak. 

## <a name="next-steps"></a>További lépések
További információ az Intune és a [Microsoft Defender ATP-ben](https://docs.microsoft.com/intune/advanced-threat-protection)  
Tekintse át az Intune-ban [a Mobile Threat Defense](https://docs.microsoft.com/intune/mobile-threat-defense)  
Tekintse át a [fenyegetések és biztonsági rések kezelése irányítópult](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) a Microsoft Defender ATP-ben

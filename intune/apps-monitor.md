---
title: "Alkalmazásadatok és -hozzárendelések monitorozása"
titlesuffix: Azure portal
description: "Miután társított egy alkalmazást a felhasználókhoz vagy eszközökhöz, ezekkel az információkkal monitorozhatja az alkalmazás állapotát."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0298fc255b3c11a12b5bf225968d6f2303192053
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune több módot is kínál a felügyelt alkalmazások jellemzőinek, valamint hozzárendelési állapotának figyelésére.

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. A **Mobilalkalmazások** területen válassza az **Alkalmazások** elemet a **Kezelés** csoportban.
5. Az alkalmazáslista panelen válasszon egy alkalmazást. Ekkor megjelenik az <*alkalmazásnév*> **Eszköz telepítési állapota** panel.

## <a name="app-overview-blade"></a>Alkalmazás áttekintése panel

Az <*alkalmazás neve*> **Eszköz telepítési állapota** panelen áttekintheti a környezetében lévő alkalmazás részletes állapotadatait.

### <a name="essentials"></a>Alapadatok

Az **Alapadatok** szakasz az alábbi információkat nyújtja az alkalmazásról:

 - **Kiadó**  
Az alkalmazás kiadója.
 - **Operációs rendszer**  
Az alkalmazás operációs rendszere (Windows, iOS, Android stb.).
 - **Létrehozás**  
A jelen változat létrehozásának ideje.
 - **Kiosztott**  
**Igen** vagy **Nem** attól függően, hogy az alkalmazás ki lett-e osztva.

### <a name="status"></a>Állapot
Az egyes diagramok az alábbi állapotadatok számlálóját jelenítik meg:

 - **Telepítve**  
A telepített alkalmazások száma.
 - **Nincs telepítve**  
A nem telepített alkalmazások száma.
 - **Telepítés függőben**  
Azon alkalmazások száma, amelyek telepítése jelenleg zajlik.
 - **Sikertelen**  
A sikertelen telepítések száma.
 - **Ismeretlen**  
Az ismeretlen állapotú alkalmazások száma.

### <a name="device-status"></a>Eszközállapot

Az eszköz állapota. Egy fánkdiagramban láthatja az alkalmazás telepítési állapotát eszközönként. A diagramra kattintva megnyithatja az eszközállapot részletes listáját. A részleteket tartalmazó táblázatban az alábbi oszlopok szerepelnek:

 - **Eszköz neve**  
Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem minden eszköz esetén elérhető.
 - **Felhasználónév**  
A felhasználó neve.
 - **Platform**  
Az eszköz operációs rendszere (Windows, iOS, Android stb.).
 - **Verzió**  
Az alkalmazás verziószáma. Üzletági alkalmazások esetében az alkalmazás teljes verziószáma látható. A teljes verziószám az alkalmazás egy adott verzióját azonosítja. A szám az alábbi formátumban jelenik meg: _Verzió_(_Build_). Például: 2.2(2.2.17560800)
 - **Állapot**  
Az alkalmazás állapota.
 - **Állapot részletei**  
Az állapot részletei.
 - **Legutóbbi bejelentkezés**  
Az eszköz Intune-nal való utolsó szinkronizálásának dátuma.


### <a name="user-status"></a>Felhasználó állapota

A felhasználó állapota. Egy fánkdiagramban láthatja az alkalmazás telepítési állapotát felhasználónként. A diagramra kattintva megnyithatja az eszközállapot részletes listáját. A részleteket tartalmazó táblázatban az alábbi oszlopok szerepelnek:
 - **Név**  
A felhasználó Azure AD-beli neve.
 - **Felhasználónév**  
A felhasználó egyedi neve.
 - **Telepítések**  
A felhasználó által használt alkalmazástelepítések száma.
 - **Hibák**  
A felhasználó sikertelen telepítéseinek száma.
 - **Nincs telepítve**  
A felhasználó által nem telepített alkalmazások száma.


## <a name="next-steps"></a>További lépések

Az Intune-adatok használatáról bővebben [Az Intune-adattárház használata](reports-nav-create-intune-reports.md) című témakörben tájékozódhat.
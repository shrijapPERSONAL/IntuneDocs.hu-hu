---
title: Beléptetési állapotlap beállítása
titleSuffix: Microsoft Intune
description: Köszöntheti a Windows 10 rendszerű eszközeiket regisztráló felhasználókat.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-an-enrollment-status-page"></a>Beléptetési állapotlap beállítása
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
A beléptetési állapotlap telepítési információkat jelenít meg a végfelhasználók eszközén az eszköz beállítása során. Előfordulhat, hogy egyes alkalmazások, profilok és tanúsítványok nincsenek még teljesen telepítve a felhasználó regisztrálásakor. Az állapotlap segít a felhasználóknak megérteni az eszközük állapotát a beléptetés alatt és után. Bekapcsolhatja az állapotlapot az összes felhasználónak, illetve meggátolhatja a felhasználókat az eszköz használatában, amíg be nem fejeződik az összes vonatkozó alkalmazás és profil telepítése.
 
A beléptetési állapotlap összes felhasználónak való bekapcsolásához kövesse az alábbi lépéseket.
 
1.  Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Beléptetés állapota oldal (előzetes verzió)** lehetőséget.
2.  A **Beléptetés állapota oldal** panelen válassza az **Alapértelmezett** > **Beállítások** lehetőséget.
3.  A **Show app and profile installation progress** (Alkalmazások és profilok telepítési állapotának megjelenítése) beállításnál válassza a **Yes** (Igen) lehetőséget.
4.  Adja meg a többi kívánt beállítást, majd válassza a **Mentés** gombot.
 
## <a name="enrollment-status-page-tracking-information"></a>A beléptetési állapotlapon megjelenített állapotadatok

Az állapotlap megjeleníti az eszköz-előkészítés, az eszközbeállítás és a fiókbeállítás folyamatának adatait.

### <a name="device-preparation"></a>Eszköz előkészítése

Az eszköz előkészítése során a beléptetési állapotlap megjeleníti a TPM-kulcsigazolásokat (ha vannak ilyenek), az Azure Active Directoryhoz való csatlakozás folyamatát, valamint az Intune-ba való beléptetés állapotát.

### <a name="device-setup"></a>Eszköz beállítása

Az eszköz beállítása során a beléptetési állapotlap az alábbi „Minden eszköz” társítású elemeket jeleníti meg:
- Biztonsági házirendek
    - Egy konfigurációs szolgáltató (CSP) az összes beléptetéshez.
    - Az Intune által konfigurált tényleges konfigurációs szolgáltatók nem jelennek meg itt.
- Alkalmazások
    - Gépenkénti üzletági (LoB) MSI-alkalmazások.
    - LoB-áruházbeli alkalmazások, melyek telepítési kontextusa „Device”.
    - Offline áruházbeli és LoB-áruházbeli alkalmazások, melyek telepítési kontextusa „Device”.
- A csatlakozási profilok (VPN és Wi-Fi) jelenleg nem jelennek meg, ezért ezeknél „0 / 0” állapot látható.
- A tanúsítványok jelenleg nem jelennek meg, ezért ezeknél „0 / 0” állapot látható.

### <a name="account-setup"></a>Fiók beállítása
A fiók beállítása során a beléptetési állapotlap az alábbi elemeket jeleníti meg:
- Biztonsági házirendek
    - Egy konfigurációs szolgáltató minden beléptetéshez.
    - Az Intune által konfigurált tényleges konfigurációs szolgáltatók nem jelennek meg itt.
- Alkalmazások
    - Felhasználónkénti LoB MSI-alkalmazások, melyek társítása „Minden eszköz”, „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
    - Gépenkénti LoB MSI-alkalmazások, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
    - LoB-áruházbeli alkalmazások, melyek társítása „Minden eszköz”, „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja, a telepítési kontextus pedig „User”.
    - Online áruházbeli alkalmazások, melyek társítása „Minden eszköz”, „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja, a telepítési kontextus pedig „User”.
    - Offline áruházbeli alkalmazások, melyek társítása „Minden eszköz”, „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja, a telepítési kontextus pedig „User”.
- Csatlakozási profilok
    - VPN- vagy Wi-Fi-profilok, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
- Tanúsítványok
    - Tanúsítványprofilok, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.

## <a name="next-steps"></a>További lépések
Ha végzett a Windows-alapú beléptetési lapok beállításával, ismerje meg, hogyan tudja kezelni a Windows-eszközöket. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](https://docs.microsoft.com/intune/device-management) című témakörben talál.
---
title: Beléptetési állapotlap beállítása
titleSuffix: Microsoft Intune
description: Állítsa be a felhasználók számára a Windows 10 rendszerű üdvözlő oldal.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: f01009a0cb35f4270bdb1e768ee781172c8bfa2f
ms.sourcegitcommit: 17f58d35a6bdff3e179662f3731fc74d39144470
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2019
ms.locfileid: "55105187"
---
# <a name="set-up-an-enrollment-status-page"></a>Beléptetési állapotlap beállítása
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Az Intune-nal eszköz beállítása során a regisztrálási állapot oldal az eszközön telepítési információit jeleníti meg. Előfordulhat, hogy egyes alkalmazások, profilok és tanúsítványok még nincsenek telepítve, mire a felhasználó végez az alapértelmezett regisztrációval, és bejelentkezik az eszközre. A regisztrációs állapotlap segít a felhasználóknak megérteni az eszközük állapotát az eszköz telepítése folyamán. Létrehozhat több regisztrációs állapotlapot is, és különböző csoportokhoz rendelheti őket. A profilok a következőkre állíthatók be:
- A telepítési folyamat kijelzése.
- A használat tiltása a telepítés befejezéséig.
- Megadható, hogy mit tehet meg a felhasználó, ha az eszköz telepítése sikertelen.

Beállíthatja a prioritásuk szerinti sorrendben történik, hogy figyelembe vegye az ugyanazon felhasználóhoz vagy eszközhöz ütköző profil-hozzárendeléseket az egyes profilok is.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Az alapértelmezett regisztrációs állapotlap bekapcsolása minden felhasználónak

A regisztrációs állapotlap bekapcsolásához kövesse az alábbi lépéseket.
 
1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Beléptetés állapota oldal (előzetes verzió)** lehetőséget.
2. A **Beléptetés állapota oldal** panelen válassza az **Alapértelmezett** > **Beállítások** lehetőséget.
3. A **Show app and profile installation progress** (Alkalmazások és profilok telepítési állapotának megjelenítése) beállításnál válassza a **Yes** (Igen) lehetőséget.
4. Adja meg a többi kívánt beállítást, majd válassza a **Mentés** gombot.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Regisztrációs állapotlapi profil létrehozása és csoporthoz rendelése

1. Az [Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrációja** > **Windows-alapú regisztráció** > **Regisztráció állapota oldal (előzetes verzió)** > **Profil létrehozása** lehetőséget.
2. Adjon meg egy **nevet** és egy **leírást**.
3. Válassza a **Létrehozás** lehetőséget.
4. A **Regisztráció állapota oldal** listájában válassza ki az új profilt.
5. Válassza a **Hozzárendelések** > **Csoportok kiválasztása** területet, majd válassza ki a profillal ellátni kívánt csoportokat, végül válassza a **Kiválasztás** > **Mentés** lehetőséget.
6. Válassza a **Beállítások** területet, adja meg az a profilra alkalmazni kívánt beállításokat, majd válassza a **Mentés** lehetőséget.

## <a name="set-the-enrollment-status-page-priority"></a>Regisztrációs állapotlap prioritásának beállítása

Egy eszköz vagy felhasználó több csoportnak is tagja lehet, így több regisztrációs állapotlapi profillal is rendelkezhet. Az ilyen ütközések az egyes profilok prioritásának megadásával kezelhetők. Ha valaki több regisztrációs állapotlapi profillal is rendelkezik, csak a legmagasabb prioritású profil lesz alkalmazva.

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Beléptetés állapota oldal (előzetes verzió)** lehetőséget.
2. Vigye a kurzort a listában a profilra.
3. A függőleges három ponttal húzza a profilt a kívánt helyre a listában.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Hozzáférés letiltása egy eszközhöz csak egy adott alkalmazás telepítve van

Megadhatja, hogy mely alkalmazásokat kell telepíteni, mielőtt a felhasználó számára elérhető az asztalon.

1. Válassza ki az Intune-ban **eszközregisztráció** > **Windows regisztrációs** > **regisztrálási állapot oldal (előzetes verzió)**.
2. Válasszon egy profilt > **beállítások**.
3. Válasszon **Igen** a **alkalmazás és a profil telepítés állapotának megjelenítése**.
4. Válasszon **Igen** a **letiltja az eszköz használatát, alkalmazások és a profilok telepítéséig**.
5. Válasszon **kijelölt** a **letiltja az eszköz használatát, amíg ezekre szükség az alkalmazások vannak telepítve, ha vannak rendelve a felhasználó/eszköz**.
 6. Válasszon **alkalmazások kiválasztása** > Válassza ki az alkalmazások > **kiválasztása** > **mentése**.

## <a name="enrollment-status-page-tracking-information"></a>A beléptetési állapotlapon megjelenített állapotadatok

Az állapotlap megjeleníti az eszköz-előkészítés, az eszközbeállítás és a fiókbeállítás folyamatának adatait.

### <a name="device-preparation"></a>Eszköz előkészítése

Az eszköz előkészítése során a beléptetési állapotlap megjeleníti a TPM-kulcsigazolásokat (ha vannak ilyenek), az Azure Active Directoryhoz való csatlakozás folyamatát, valamint az Intune-ba való beléptetés állapotát.

### <a name="device-setup"></a>Eszköz beállítása

Az eszköz beállítása során a beléptetési állapotlap az alábbi „Minden eszköz” társítású elemeket jeleníti meg:
- Biztonsági szabályzatok
    - Egy konfigurációs szolgáltató (CSP) az összes beléptetéshez.
    - Az Intune által konfigurált tényleges konfigurációs szolgáltatók nem jelennek meg itt.
- Alkalmazások
    - Gépenkénti üzletági (LoB) MSI-alkalmazások.
    - LoB-áruházbeli alkalmazások, melyek telepítési kontextusa „Device”.
    - Offline áruházbeli és LoB-áruházbeli alkalmazások, melyek telepítési kontextusa „Device”.
- Csatlakozási profilok
    - A **Minden eszközhöz** vagy olyan eszközcsoporthoz hozzárendelt VPN- vagy Wi-Fi-profilok, amelyeknek az éppen regisztrált eszköz a tagja, de csak Autopilot-eszközök esetén
- A **Minden eszközhöz**, vagy olyan eszközcsoporthoz hozzárendelt tanúsítványprofilok, amelyeknek az éppen regisztrált eszköz a tagja, de csak Autopilot-eszközök esetén

### <a name="account-setup"></a>Fiók beállítása
A fiók beállítása során a beléptetési állapotlap az alábbi elemeket jeleníti meg:
- Biztonsági szabályzatok
    - Egy konfigurációs szolgáltató minden beléptetéshez.
    - Az Intune által konfigurált tényleges konfigurációs szolgáltatók nem jelennek meg itt.
- Alkalmazások
    - Felhasználónkénti LoB MSI-alkalmazások, melyek társítása „Minden eszköz”, „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
    - Gépenkénti LoB MSI-alkalmazások, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
    - Üzletági áruházbeli alkalmazások, online áruházbeli alkalmazások és offline áruházbeli alkalmazások, amelyek a következők egyikéhez vannak hozzárendelve:
        - Minden eszköz
        - Minden felhasználó
        - egy olyan felhasználói csoport, amelynek az eszközt regisztráló felhasználó a tagja, a telepítési kontextus pedig „User”.
- Csatlakozási profilok
    - VPN- vagy Wi-Fi-profilok, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.
- Tanúsítványok
    - Tanúsítványprofilok, melyek társítása „Minden felhasználó” vagy egy olyan felhasználói csoport, amelynek az eszközt beléptető felhasználó a tagja.

## <a name="next-steps"></a>További lépések
Ha végzett a Windows-alapú beléptetési lapok beállításával, ismerje meg, hogyan tudja kezelni a Windows-eszközöket. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](https://docs.microsoft.com/intune/device-management) című témakörben talál.

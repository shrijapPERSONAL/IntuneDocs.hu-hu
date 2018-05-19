---
title: Windows-eszköz törlése az Intune-ból
description: Egy Windows-eszköz Intune-ból való törlését mutatja be
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1dd64250c1996c6b13c62f80572282d639112ba6
ms.sourcegitcommit: 8ee543c864097dc195b6f440471dca713fc21ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/09/2018
---
# <a name="remove-your-windows-device-from-intune-management"></a>Windows-eszköz eltávolítása az Intune-ból

Eltávolíthatja a regisztrált Windows-eszközét az Intune-ból, ha már nem szeretné a következőkre használni:  
* Az eszköz munkahelyi vagy iskolai használata. 
* Hozzáférés a munkahelyi vagy iskolai e-mailekhez, alkalmazásokhoz és egyéb erőforrásokhoz.

Az eltávolítást követően nem férhet hozzá az iskolai vagy munkahelyi erőforrásokhoz az eszközről. Az alábbi Windows-eszközök távolíthatók el az Intune-ból:  
* Windows 10-es eszközök 
* Windows 8.1-es számítógépek
* WIndows 8.1-es mobileszközök
 
További információ az eszköz Intune-felügyelet alóli kivonásának további következményeiről: [Mi történik, ha eltávolítja az eszközt az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Windows 10 rendszerű eszköz törlése
Az alábbi lépésekkel eltávolíthat egy Windows 10-es eszközt az Intune-ból.

### <a name="via-the-company-portal-app"></a>A Céges portál alkalmazásban

1. Nyissa meg a Vállalati portál alkalmazást.
2. Jelentkezzen be a munkahelyi vagy iskolai fiókjával.
3. Az **Eszközök** területen válassza ki az eltávolítani kívánt eszközt.
4. Az alkalmazás jobb felső sarkában kattintson a **Továbbiak** ikonra.
5. Válassza az **Eltávolítás** lehetőséget. 
6. Az eszköz eltávolításának megerősítéséhez válassza az **Eszköz eltávolítása** lehetőséget.

### <a name="via-device-settings-app"></a>Az eszköz Beállítások alkalmazásában
1. Nyissa meg a Beállítások alkalmazást. 
2. Lépjen a **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** pontra.
3. Válassza ki az eltávolítani kívánt csatlakoztatott fiókot, majd válassza a **Leválasztás** lehetőséget.
4. Az eszköz eltávolításának megerősítéséhez válassza az **Igen** lehetőséget.

## <a name="remove-your-windows-81-computer"></a>Windows 8.1-es számítógép törlése
Az alábbi lépésekkel eltávolíthat egy Windows 8.1-es számítógépet az Intune-ból.

1.  Lépjen a **Gépház** > **Hálózat** > **Munkahely** lehetőséghez.
2.  A **Csatlakozás munkahelyhez** területen válassza a **Kilépés** lehetőséget.
3.  Válassza az **Eszközkezelés bekapcsolása** terület **Kikapcsolás** lehetőségét.
4.  A megjelenő előugró ablakban válassza a **Kikapcsolás** lehetőséget.

## <a name="remove-your-windows-81-mobile-device"></a>Windows 8.1-es mobileszköz eltávolítása
Az alábbi lépésekkel eltávolíthat egy Windows 8.1-es mobileszközt az Intune-ból.

1.  Lépjen a **Beállítások** > **Munkahely** területre.
2.  Koppintson a törölni kívánt munkahelyi fiókra.
3.  A képernyő alsó részén koppintson a **Törlés** elemre.
4.  A **Fiók törlése** párbeszédpanelen koppintson a **Törlés** gombra.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Személyes információk törlése a Céges portál eltávolítása után
A Céges portál kétféle adatot tárol az Ön windowsos eszközén:

-   **Diagnosztikai naplók**: A Microsoft által gyűjtött szabványos alkalmazástevékenység-adatok automatikusan törlődnek az eszköz a Céges portálból való eltávolításakor. Az alkalmazástevékenységi adatok például az alkalmazás használatának időtartama vagy az összeomlási adatok.
-   **Alkalmazás-gyorsítótár**: Olyan támogató fájlok, amelyek tárolása szükséges az alkalmazás működéséhez, például ikonok és beállítások.

Ennek az információnak a teljes törléséhez végre kell hajtania néhány lépést.

1. Távolítsa el a Céges portált. [A Céges portál alkalmazás eltávolítása](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) törli az eszközön tárolt alkalmazásadatok egy részét.  

2. Állítsa alaphelyzetbe a Céges portált a tárolt alkalmazásadatok visszaállításához. Nyissa meg a **Beállítások** alkalmazást, és válassza az **Alkalmazások** > **Céges portál** > **Speciális beállítások** > **Alaphelyzetbe állítás** lehetőséget. 

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).
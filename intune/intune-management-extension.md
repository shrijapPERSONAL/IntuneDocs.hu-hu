---
title: PowerShell-parancsfájlok kezelése a Microsoft Intune-ban Windows 10-es eszközök esetén
titlesuffix: ''
description: Megtudhatja, hogyan tölthet fel PowerShell-parancsfájlokat a Microsoft Intune-ba, amelyeket Windows 10-es eszközökön futtathat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3de7af01ffa64293e420913258919eff118b4abc
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén
Az Intune felügyeleti bővítményével Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat tölthet fel az Intune-ba. A felügyeleti bővítmény kiegészíti a Windows 10 mobileszköz-kezelési funkcióit, és könnyebbé teszi a modern felügyeletre váltást.

## <a name="moving-to-modern-management"></a>Váltás modern felügyeletre
A végfelhasználói számítástechnika a digitális átalakulás korszakát éli. A klasszikus, hagyományos informatika egyetlen eszközplatformra, vállalati tulajdonú eszközökre, az irodából dolgozó felhasználókra és számos kézi, reaktív informatikai folyamatra hagyatkozik. A modern munkahely azonban több eszközplatformot képes befogadni, amelyek felhasználói és vállalati tulajdonban is lehetnek, a felhasználók bárhonnan dolgozhatnak, és automatizált, proaktív informatikai folyamatok használatosak. 

Az MDM-szolgáltatások, mint például a Microsoft Intune, az MDM-protokollal felügyelhetik a Windows 10-es eszközöket. A beépített Windows 10 felügyeleti ügyfél kommunikálhat az Intune-nal, így vállalati felügyeleti feladatokat láthat el. Ez segít a Windows 10-es eszközök modern felügyeletre váltásában. Vannak azonban bizonyos funkciók, amelyekre szüksége lehet, jelenleg mégsem elérhetők a Windows 10 MDM-ben. Ilyen a fejlett eszközkonfiguráció, a hibaelhárítás, valamint az elavult Win32-alkalmazáskezelés. Előfordulhat, hogy ezekhez a funkciókhoz futtatnia kell az Intune-szoftverügyfelet a Windows 10-es eszközein. Ennek eredményeképpen nem fogja tudni használni a Windows 10 MDM új funkcióit. [Hasonlítsa össze az Intune-szoftverügyfél és a Windows 10 MDM különbségeit](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

Az Intune felügyeleti bővítmény kiegészíti a Windows 10 MDM beépített funkcióit. Létrehozhat olyan PowerShell-parancsfájlokat, amelyek azokon a Windows 10-es eszközökön futnak, amelyek a szükséges funkciókat nyújtják. Létrehozhat például egy olyan PowerShell-parancsfájlt, amely egy elavult Win32-alkalmazást telepít a Windows 10-es eszközeire, feltöltheti a parancsfájlt az Intune-ba, hozzárendelheti egy Azure Active Directory-csoporthoz, majd futtathatja a Windows 10-es eszközökön. Ezt követően megfigyelheti a parancsfájl futtatási állapotát a Windows 10-es eszközökön a folyamat teljes időtartama alatt.

## <a name="prerequisites"></a>Előfeltételek
Az Intune felügyeleti bővítmény előfeltételei a következők:
- Az eszközöknek csatlakozniuk kell az Azure AD-hoz. Ez a Hybrid AD-hoz csatlakoztatott eszközökre nem vonatkozik.
- Az eszközöknek a Windows 10 1607-es vagy újabb verziójával kell rendelkezniük.

## <a name="create-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó szabályzat létrehozása 
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **PowerShell-parancsfájlok** lehetőséget.
5. A **PowerShell-parancsfájlok** panelen válassza a **Hozzáadás** lehetőséget.
6. A **PowerShell-parancsfájl hozzáadása** panelen adjon meg a PowerShell-parancsfájl **Nevét** és **Leírását**.
7. A **Parancsfájl helye** beállításhoz keresse meg a PowerShell-parancsfájlt. A szkriptnek 200 kB-nál kisebbnek kell lennie.
8. Válassza a **Konfigurálás** lehetőséget, majd adja meg, hogy a parancsfájl a felhasználó hitelesítő adataival fusson-e az eszközön (**Igen**) vagy a rendszerkörnyezetben (**Nem**). Alapértelmezés szerint a parancsfájl a rendszerkörnyezetben fut. Hacsak a parancsfájlt nem a rendszerkörnyezetben kell futtatnia, válassza az **Igen** lehetőséget. 
  ![PowerShell-parancsfájl hozzáadása panel](./media/mgmt-extension-add-script.png)
9. Adja meg, hogy a parancsfájl megkövetelje-e egy megbízható közzétevő aláírását (**Igen**). Alapértelmezés szerint a parancsfájl aláírása nem kötelező. 
10. A parancsfájl mentéséhez kattintson az **OK** gombra, majd a **Létrehozás** lehetőségre.

## <a name="assign-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó házirend hozzárendelése
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **PowerShell-parancsfájlok** lehetőséget.
5. A **PowerShell-parancsfájlok** panelen válassza ki a hozzárendelni kívánt parancsfájlt, majd válassza a **Felügyelet** > **Hozzárendelések** lehetőséget.
  ![PowerShell-parancsfájl hozzáadása panel](./media/mgmt-extension-assignments.png)
 
6. Az elérhető Azure AD-csoportok listázásához válassza a **Csoportok kiválasztása** lehetőséget. 
7. Jelöljön ki egy vagy több olyan csoportot, amelyek azokat a felhasználókat tartalmazzák, akiknek az eszközeire telepíteni szeretné a parancsfájlt, majd a **Kiválasztás** lehetőségre kattintva társítsa a szabályzatot a kijelölt csoportokhoz.

Az Intune felügyeleti bővítmény óránként szinkronizál az Intune-nal. Miután hozzárendelte a szabályzatot az Azure AD-csoportokhoz, elindul a PowerShell-parancsfájl, és elkészül a futtatási eredmények jelentése. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>A PowerShell-parancsfájlok futtatási állapotának figyelése
Megfigyelheti a felhasználók és eszközök PowerShell-parancsfájljainak futtatási állapotát az Azure Portalon.
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **PowerShell-parancsfájlok** lehetőséget.
5. A **PowerShell-parancsfájlok** panelen válassza ki a megfigyelendő parancsfájlt, válassza a **Figyelés** lehetőséget, majd válassza ki az alábbi jelentések egyikét:
   - **Eszközállapot**
   - **Felhasználó állapota**

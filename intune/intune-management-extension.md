---
title: PowerShell-parancsfájlok hozzáadása a Microsoft Intune-ban Windows 10-es eszközökhöz – Azure | Microsoft Docs
description: PowerShell-parancsfájlok hozzáadása, parancsfájlszabályzat hozzárendelése Azure Active Directory-csoportokhoz, parancsfájlok figyelése jelentésekkel, és a parancsfájlok Windows 10 rendszerű eszközökről való törlésének lépései a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ad8e874dda47b7c6deeb614b0f893f7c922241ce
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236339"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén
Az Intune felügyeleti bővítményével Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat tölthet fel az Intune-ba. A felügyeleti bővítmény kiegészíti a Windows 10 mobileszköz-kezelési funkcióit, és könnyebbé teszi a modern felügyeletre váltást.

## <a name="moving-to-modern-management"></a>Váltás modern felügyeletre
A végfelhasználói számítástechnika a digitális átalakulás korszakát éli. A klasszikus, hagyományos informatika egyetlen eszközplatformra, vállalati tulajdonú eszközökre, az irodából dolgozó felhasználókra és számos kézi, reaktív informatikai folyamatra hagyatkozik. A modern munkahely azonban több eszközplatformot képes befogadni, amelyek felhasználói és vállalati tulajdonban is lehetnek, a felhasználók bárhonnan dolgozhatnak, és automatizált, proaktív informatikai folyamatok használatosak. 

Az MDM-szolgáltatások, mint például a Microsoft Intune, az MDM-protokollal felügyelhetik a Windows 10-es eszközöket. A beépített Windows 10 felügyeleti ügyfél kommunikálhat az Intune-nal, így vállalati felügyeleti feladatokat láthat el. Ez segít a Windows 10-es eszközök modern felügyeletre váltásában. Vannak azonban bizonyos funkciók, amelyekre szüksége lehet, jelenleg mégsem elérhetők a Windows 10 MDM-ben. Ilyen a fejlett eszközkonfiguráció, a hibaelhárítás, valamint az elavult Win32-alkalmazáskezelés. Előfordulhat, hogy ezekhez a funkciókhoz futtatnia kell az Intune-szoftverügyfelet a Windows 10-es eszközein. Ennek eredményeképpen nem fogja tudni használni a Windows 10 MDM új funkcióit. [Hasonlítsa össze az Intune-szoftverügyfél és a Windows 10 MDM különbségeit](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

Az Intune felügyeleti bővítmény kiegészíti a Windows 10 MDM beépített funkcióit. Létrehozhat olyan PowerShell-parancsfájlokat, amelyek azokon a Windows 10-es eszközökön futnak, amelyek a szükséges funkciókat nyújtják. Létrehozhat például egy olyan PowerShell-parancsfájlt, amely egy elavult Win32-alkalmazást telepít a Windows 10-es eszközeire, feltöltheti a parancsfájlt az Intune-ba, hozzárendelheti egy Azure Active Directory-csoporthoz, majd futtathatja a Windows 10-es eszközökön. Ezt követően megfigyelheti a parancsfájl futtatási állapotát a Windows 10-es eszközökön a folyamat teljes időtartama alatt.

## <a name="prerequisites"></a>Előfeltételek
Az Intune felügyeleti bővítmény előfeltételei a következők:
- Az eszközöknek csatlakozniuk kell az Azure AD-hoz. Az Intune felügyeleti bővítménye támogatja az Azure Active Directoryhoz és a hibrid tartományhoz csatlakoztatott, valamint a közösen felügyelt regisztrált Windows-eszközöket.
- Az eszközöknek a Windows 10 1607-es vagy újabb verziójával kell rendelkezniük.
- Az automatikus MDM-regisztrációt [engedélyeznie kell az Azure AD-ban](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment), és az eszközöket automatikusan regisztrálnia kell az Intune-ban.

## <a name="create-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó szabályzat létrehozása 
1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **PowerShell-parancsfájlok** > **Hozzáadás** lehetőséget.
4. Adja meg a PowerShell-parancsfájl nevét és leírását a **Név** és a **Leírás** mezőben. A **Parancsfájl helye** beállításhoz keresse meg a PowerShell-parancsfájlt. A parancsfájlnak 200 KB-nál (ASCII) vagy 100 KB-nál (Unicode) kisebbnek kell lennie.
5. Válassza a **Konfigurálás** elemet. Ezután adja meg, hogy a parancsfájl a felhasználó hitelesítő adataival fusson-e az eszközön (**Igen**) vagy a rendszerkörnyezetben (**Nem**). Alapértelmezés szerint a parancsfájl a rendszerkörnyezetben fut. Hacsak a parancsfájlt nem a rendszerkörnyezetben kell futtatnia, válassza az **Igen** lehetőséget. 
  ![PowerShell-parancsfájl hozzáadása panel](./media/mgmt-extension-add-script.png)
6. Adja meg, hogy a parancsfájl megkövetelje-e egy megbízható közzétevő aláírását (**Igen**). Alapértelmezés szerint a parancsfájl aláírása nem kötelező. 
7. A parancsfájl mentéséhez válassza az **OK**, majd a **Létrehozás** gombot.

## <a name="assign-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó házirend hozzárendelése
1. A **PowerShell-parancsfájlok** panelen válassza ki a hozzárendelni kívánt parancsfájlt, majd válassza a **Kezelés** > **Hozzárendelések** lehetőséget.
  ![PowerShell-parancsfájl hozzáadása panel](./media/mgmt-extension-assignments.png)
 
2. Az elérhető Azure AD-csoportok listázásához válassza a **Csoportok kiválasztása** lehetőséget. 
3. Jelöljön ki egy vagy több olyan csoportot, amelyek azokat a felhasználókat tartalmazzák, akiknek az eszközeire telepíteni szeretné a parancsfájlt. Válassza a **Kiválasztás** lehetőséget a szabályzat kijelölt csoportokhoz rendeléséhez.

> [!NOTE]
> - A PowerShell-szkriptek nem alkalmazhatók számítógép-csoportokra.
> - A végfelhasználóknak nem kell bejelentkezniük az eszközön a PowerShell-parancsfájlok végrehajtásához. 
> - Az Intune-beli PowerShell-parancsfájlok beállíthatók úgy, hogy AAD-eszközbiztonsági csoportokat célozzanak meg.

Az Intune felügyeleti bővítmény óránként szinkronizál az Intune-nal. Miután hozzárendelte a szabályzatot az Azure AD-csoportokhoz, elindul a PowerShell-parancsfájl, és elkészül a futtatási eredmények jelentése. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>A PowerShell-parancsfájlok futtatási állapotának figyelése
Megfigyelheti a felhasználók és eszközök PowerShell-parancsfájljainak futtatási állapotát az Azure Portalon.

A **PowerShell-parancsfájlok** panelen válassza ki a megfigyelendő parancsfájlt, válassza a **Figyelés** lehetőséget, majd válassza az alábbi jelentések egyikét:
   - **Eszközállapot**
   - **Felhasználó állapota**

## <a name="delete-a-powershell-script"></a>PowerShell-parancsfájl törlése
A **PowerShell-parancsfájlok** panelen kattintson a jobb gombbal a parancsfájlra, és válassza a **Törlés** lehetőséget.

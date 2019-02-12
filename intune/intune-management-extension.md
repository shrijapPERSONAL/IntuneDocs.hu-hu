---
title: PowerShell-parancsfájlok hozzáadása a Microsoft Intune-ban Windows 10-es eszközökhöz – Azure | Microsoft Docs
description: PowerShell-parancsfájlok hozzáadása, parancsfájlszabályzat hozzárendelése Azure Active Directory-csoportokhoz, parancsfájlok figyelése jelentésekkel, és a parancsfájlok Windows 10 rendszerű eszközökről való törlésének lépései a Microsoft Intune-ban. Néhány gyakori problémák és megoldásuk is megtekintheti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d0594c9f14b9d18c597de9ca37826a669dde5f3
ms.sourcegitcommit: e262b0ad8df610e25eb9421b9ebc2673bcf1020e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2019
ms.locfileid: "55986875"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén

Az Intune felügyeleti bővítmény használatával töltse fel az Intune-ban Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat. A felügyeleti bővítmény fokozza a Windows 10 mobileszköz-felügyelet (MDM), és megkönnyíti a modern felügyeletre váltást.

## <a name="moving-to-modern-management"></a>Váltás modern felügyeletre

A végfelhasználói számítástechnika a digitális átalakulás korszakát éli. A klasszikus, hagyományos informatika egyetlen eszközplatformra, vállalati tulajdonú eszközökre, az irodából dolgozó felhasználókra és számos kézi, reaktív informatikai folyamatra hagyatkozik. A modern munkahely számos platformon, amelyek a felhasználói és vállalati tulajdonú használ, lehetővé teszi, hogy a felhasználók bárhonnan dolgozhatnak, és automatizált, proaktív informatikai folyamatok biztosít.

Az MDM-szolgáltatások, például a Microsoft Intune, a Windows 10 rendszerű asztali és mobil eszközöket kezelheti. A beépített Windows 10 felügyeleti ügyfél kommunikál az Intune-nal vállalati felügyeleti feladat futtatására. Bizonyos feladatokat, amelyeket érdemes lehet, például a fejlett eszközkonfiguráció, hibaelhárítási és az örökölt Win32-Alkalmazáskezelés, amely jelenleg nem érhető el a Windows 10 mobileszköz-kezelést. Ezen funkciók az Intune-szoftverügyfél futtathatja a Windows 10 rendszerű eszközökön. [Hasonlítsa össze a Windows rendszerű számítógépek felügyeletét, számítógépek vagy mobileszközök](pc-management-comparison.md) egy nagyszerű forrás.

Az Intune felügyeleti bővítmény kiegészíti a beépített Windows 10 MDM-funkció. A Windows 10-es eszközökön futtatandó PowerShell-szkripteket hozhat létre. Ha például egy PowerShell-parancsprogram, amely egy elavult Win32-alkalmazást telepít, a parancsfájl feltölti az Intune-hoz, a parancsfájl hozzárendeli egy Azure Active Directory (AD) csoportnak és a parancsfájl futtatása is létrehozhat. Ezt követően megfigyelheti az elejétől a végéig a parancsfájl futtatási állapotát.

## <a name="prerequisites"></a>Előfeltételek

Az Intune felügyeleti bővítmény előfeltételei a következők:

- Eszközök csatlakoztatva kell lennie, vagy az Azure-bA regisztrált AD és az Azure ad-ben van beállítva [automatikus regisztráció az Intune-ban](windows-enroll.md#enable-windows-10-automatic-enrollment). Az Intune felügyeleti bővítmény támogatja az Azure AD-hez, a hibrid tartományhoz csatlakoztatott és comanaged regisztrált Windows-eszközökön.
- Eszközök a Windows 10-es verzióját kell futtatnia, 1607-es vagy újabb.
- Az Intune felügyeleti bővítmény-ügynök telepítve van, amikor egy PowerShell-parancsprogram, vagy egy Win32-alkalmazás egy felhasználó vagy eszköz biztonsági csoport üzemel.

## <a name="create-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó szabályzat létrehozása 

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **a Microsoft Intune**.
2. Válassza az **Eszközkonfiguráció** > **PowerShell-parancsfájlok** > **Hozzáadás** lehetőséget.
3. Adja meg a PowerShell-parancsfájl nevét és leírását a **Név** és a **Leírás** mezőben. A **Parancsfájl helye** beállításhoz keresse meg a PowerShell-parancsfájlt. A parancsfájl nem lehet nagyobb, mint 200 KB-nál.
4. Válassza a **Konfigurálás** elemet. Ezután adja meg, hogy a parancsfájl a felhasználó hitelesítő adataival fusson-e az eszközön (**Igen**) vagy a rendszerkörnyezetben (**Nem**). Alapértelmezés szerint a parancsfájl a rendszerkörnyezetben fut. Hacsak a parancsfájlt nem a rendszerkörnyezetben kell futtatnia, válassza az **Igen** lehetőséget. 
  ![PowerShell-parancsfájl hozzáadása panel](./media/mgmt-extension-add-script.png)
5. Adja meg, hogy a parancsfájl megkövetelje-e egy megbízható közzétevő aláírását (**Igen**). Alapértelmezés szerint a parancsfájl aláírása nem kötelező. 
6. A parancsfájl mentéséhez válassza az **OK**, majd a **Létrehozás** gombot.

## <a name="assign-a-powershell-script-policy"></a>PowerShell-parancsfájlhoz tartozó házirend hozzárendelése

1. A **PowerShell-parancsfájlok** panelen válassza ki a hozzárendelni kívánt parancsfájlt, majd válassza a **Kezelés** > **Hozzárendelések** lehetőséget.

    ![Adja hozzá a PowerShell parancsfájl panel](./media/mgmt-extension-assignments.png)

2. Az elérhető Azure AD-csoportok listázásához válassza a **Csoportok kiválasztása** lehetőséget. 
3. Válassza ki egy vagy több olyan csoportot, amely tartalmazza a felhasználókat, akiknek az eszközei kap a parancsfájlt. Válassza a **Kiválasztás** lehetőséget a szabályzat kijelölt csoportokhoz rendeléséhez.

> [!NOTE]
> - Jelentkezzen be az eszköz PowerShell-szkriptek végrehajtása a végfelhasználók számára nem szükséges.
> - Az Intune-ban a PowerShell-parancsfájlok megcélozhatóvá válnak az Azure AD-eszközök biztonsági csoportjainak.
> - Az Intune-ban a PowerShell-parancsfájlok megcélozhatóvá válnak az Azure AD-felhasználó biztonsági csoportokba.

Az Intune felügyeleti bővítmény-ügyfelet az Intune-nal óránként egyszer ellenőrzi. Miután hozzárendelte a szabályzatot az Azure AD-csoportokhoz, elindul a PowerShell-parancsfájl, és elkészül a futtatási eredmények jelentése.

## <a name="monitor-run-status-for-powershell-scripts"></a>A PowerShell-parancsfájlok futtatási állapotának figyelése

Megfigyelheti a felhasználók és eszközök PowerShell-parancsfájljainak futtatási állapotát az Azure Portalon.

A **PowerShell-parancsfájlok** panelen válassza ki a megfigyelendő parancsfájlt, válassza a **Figyelés** lehetőséget, majd válassza az alábbi jelentések egyikét:

- **Eszközállapot**
- **Felhasználó állapota**

## <a name="troubleshoot-powershell-scripts"></a>PowerShell-parancsfájlok hibáinak elhárítása

Az ügyfélszámítógépen Agent-naplók általában a rendszer `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Használhat [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) , ezek a naplófájlok megtekintése. 

![Képernyőkép – Az ügynöknaplók](./media/apps-win32-app-10.png)  

## <a name="delete-a-powershell-script"></a>PowerShell-parancsfájl törlése

A **PowerShell-parancsfájlok** panelen kattintson a jobb gombbal a parancsfájlra, és válassza a **Törlés** lehetőséget.

## <a name="common-issues-and-resolutions"></a>Gyakori hibák és megoldásaik

A PowerShell-parancsfájlok minden bejelentkezéskor nem futnak. Csak után újraindul, futtatása vagy, ha a **a Microsoft Intune felügyeleti bővítmény** szolgáltatás újraindításakor. Az Intune felügyeleti bővítmény ügyfélellenőrzés óránként egyszer bármely módosítása a parancsfájl vagy a szabályzat az Intune-ban.

#### <a name="issue-intune-management-extension-doesnt-download"></a>A probléma leírása: Az Intune felügyeleti bővítmény nem sikerül letölteni.

**A lehetséges megoldások**:

- Győződjön meg arról, hogy az eszközök is automatikusan regisztrálva az Azure ad-ben. Annak ellenőrzéséhez, az eszközön: 

  1. Lépjen a **beállítások** > **fiókok** > **hozzáférés munkahelyi vagy iskolai**.
  2. Válassza ki a csatlakoztatott fiókot > **Info**.
  3. A **speciális diagnosztikai jelentés**válassza **jelentés létrehozása**.
  4. Nyissa meg a `MDMDiagReport` a webböngészőt, és nyissa meg a **konfigurációs adatforrások regisztrálva** szakaszban.
  5. Keresse meg a **MDMDeviceWithAAD** tulajdonság. Ha ez a tulajdonság nem létezik, az eszköz nem regisztrált automatikus.

    [A Windows 10 automatikus regisztrációjának engedélyezése](windows-enroll.md#enable-windows-10-automatic-enrollment) szükséges lépéseket.

#### <a name="issue-the-powershell-scripts-do-not-run"></a>A probléma leírása: A PowerShell-parancsfájlok nem működnek.

**A lehetséges megoldások**:

- Győződjön meg róla, az Intune felügyeleti bővítmény letöltődik minden olyan `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Parancsfájlok a Surface hubokon nem futnak.
- Ellenőrizze a naplókat `\ProgramData\Microsoft\IntuneManagementExtension\Logs` hibaüzeneteket.
- Lehetséges engedélyekkel kapcsolatos problémák, lehet, hogy a PowerShell-parancsfájl tulajdonságai vannak beállítva `Run this script using the logged on credentials`. Emellett ellenőrizze, hogy a bejelentkezett felhasználó rendelkezik-e a megfelelő engedélyekkel a parancsfájl futtatásához.
- Parancsfájl-kezelési probléma azonosítása, minta parancsfájl futtatása. Hozzon létre például a `C:\Scripts` könyvtárat, és adjon mindenkinek teljes hozzáférése. Futtassa a következő parancsfájlt:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Ha ez sikeres, a kimenet.txt kell létrehozni, és tartalmaznia kell a "Szkript működött" szöveget.

- Parancsfájl végrehajtása nélkül Intune teszteléséhez futtassa a parancsfájlokat a a rendszerkörnyezetben használatával a [psexec eszköz](https://docs.microsoft.com/sysinternals/downloads/psexec) helyileg:

  `psexec -i -s`

## <a name="next-steps"></a>További lépések

[A figyelő](device-profile-monitor.md) és [hibaelhárítása](device-profile-troubleshoot.md) a profilok.

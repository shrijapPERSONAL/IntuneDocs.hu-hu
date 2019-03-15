---
title: PowerShell-parancsfájlok hozzáadása a Microsoft Intune - Azure-ban Windows 10 rendszerű eszközökre |} A Microsoft Docs
description: Hozzon létre és a PowerShell-parancsfájlok futtatása, a parancsfájlhoz tartozó házirend hozzárendelése az Azure Active Directory-csoportok, jelentések használatával figyelheti a szkriptek és a lépések a Windows 10 rendszerű eszközökön a Microsoft Intune-ban hozzáadhat parancsprogramokat törlése. Néhány gyakori problémák és megoldásuk is megtekintheti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f02b8849b626715471e5cabea937f89a08ab540c
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57390650"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>PowerShell-parancsfájlok használata a Windows 10 rendszerű eszközökön az Intune-ban

A Microsoft Intune felügyeleti bővítmény használatával töltse fel az Intune-ban Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat. A felügyeleti bővítmény fokozza a Windows 10 mobileszköz-felügyelet (MDM), és megkönnyíti a modern felügyeletre váltást.

Ez a funkció az alábbiakra vonatkozik:

- Windows 10 és újabb

## <a name="move-to-modern-management"></a>Modern felügyeletre váltást

A végfelhasználói számítástechnika a digitális átalakulás korszakát éli. A klasszikus, hagyományos informatika egyetlen eszközplatformra, vállalati tulajdonú eszközökre, az office és a különböző kézi, reaktív informatikai folyamatok dolgozó felhasználókra. A modern munkahely számos platformon, amelyek a felhasználói és vállalati tulajdonú használ, lehetővé teszi, hogy a felhasználók bárhonnan dolgozhatnak, és automatizált, proaktív informatikai folyamatok biztosít.

Az MDM-szolgáltatások, például a Microsoft Intune, a Windows 10 rendszerű asztali és mobil eszközöket kezelheti. A beépített Windows 10 felügyeleti ügyfél kommunikál az Intune-nal vállalati felügyeleti feladat futtatására. Van néhány feladatot, amelyeket érdemes lehet, például a fejlett eszközkonfiguráció és a hibaelhárítás. A Win32-Alkalmazáskezelés, használhatja a [Win32-Alkalmazáskezelés](apps-win32-app-management.md) funkció a Windows 10 rendszerű eszközökön.

Az Intune felügyeleti bővítmény kiegészíti a beépített Windows 10 MDM-funkció. A Windows 10-es eszközökön futtatandó PowerShell-szkripteket hozhat létre. Például létrehozhat egy PowerShell-parancsprogram, amely speciális eszköz-konfigurációk nem, a parancsfájl feltölti az Intune-hoz, a parancsfájl hozzárendeli egy Azure Active Directory (AD) csoportnak, és futtatja a szkriptet. Ezt követően megfigyelheti az elejétől a végéig a parancsfájl futtatási állapotát.

## <a name="prerequisites"></a>Előfeltételek

Az Intune felügyeleti bővítmény előfeltételei a következők:

- Eszközök csatlakoztatva kell lennie, vagy az Azure-bA regisztrált AD és az Azure ad-ben van beállítva [automatikus regisztráció az Intune-ban](windows-enroll.md#enable-windows-10-automatic-enrollment). Az Intune felügyeleti bővítmény támogatja az Azure AD-hez, a hibrid tartományhoz csatlakoztatott és közösen kezelt regisztrált Windows-eszközök.
- Eszközök a Windows 10-es verzióját kell futtatnia, 1607-es vagy újabb.
- Az Intune felügyeleti bővítmény-ügynök telepítve van, amikor egy PowerShell-parancsprogram, vagy egy Win32-alkalmazás egy felhasználó vagy eszköz biztonsági csoport üzemel.

## <a name="create-a-script-policy"></a>A parancsfájlhoz tartozó szabályzat létrehozása 

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **PowerShell-parancsfájlok** > **Hozzáadás** lehetőséget.
3. Adja meg a következő tulajdonságokat:
    - **Név**: Adjon meg egy nevet a PowerShell-parancsfájlt. 
    - **Description** (Leírás): Adjon meg egy leírást a PowerShell-parancsfájlt. A beállítás használata nem kötelező, de ajánlott. 
    - **Parancsfájl helye**: Keresse meg a PowerShell-parancsfájlt. A szkript kevesebb, mint 200 KB (ASCII) kell lennie.
4. Válasszon **konfigurálása**, és adja meg a következő tulajdonságokat:
    - **Futtassa ezt a szkriptet a hitelesítő adatok használatával a bejelentkezett**: Válassza ki **Igen** a parancsfájl futtatásához a felhasználó hitelesítő adataival az eszközön. Válasszon **nem** (alapértelmezett), a parancsfájl futtatásához a rendszerkörnyezetben. Hacsak a parancsfájlt nem a rendszerkörnyezetben kell futtatnia, válassza az **Igen** lehetőséget.
    - **Ellenőrzésének kényszerítése**: Válassza ki **Igen** , ha a parancsfájl megkövetelje-e egy megbízható közzétevő. Válassza ki **nem** (alapértelmezett), ha egy követelmény a parancsfájl aláírása nem áll rendelkezésre. 
    - **Futtassa a szkriptet a PowerShell-gazdagépet 64 bites**: Válassza ki **Igen** , futtassa a parancsfájlt a PowerShell (PS) 64 bites gazdagépen egy 64 bites ügyfél architektúrájának. Válassza ki **nem** (alapértelmezett) a 32 bites PowerShell-gazdagépet a parancsfájlt futtatja.

      Ha beállítás **Igen** vagy **nem**, a következő táblázat tartalmazza ezen új és meglévő szabályzat:

      | Futtassa a szkriptet a 64 bites PS gazdagép | Ügyfél-architektúrája | Új PS-parancsprogram | Meglévő házirend PS-parancsprogram |
      | --- | --- | --- | --- | 
      | Nem | 32 bites  | támogatja a 32 bites PS állomás | Csak 32 bites PS gazdagéptől, ami 32 bites és 64 bites rendszereken futtatható. |
      | Igen | 64 bites | 64 bites PS fogadó 64 bites architektúrák parancsfájlt futtatja. Ha 32 bites futtatunk, a szkript futtatása a 32 bites PS gazdagépen. | 32 bites PS fogadó parancsfájlt futtatja. Ha 64 bites, a (ez nem fut) parancsfájl megnyílik egy 64 bites PS gazdagépre, és a jelentésekben az eredmények módosítja ezt a beállítást. Ha 32 bites futtatunk, a szkript futtatása a 32 bites PS gazdagépen. |

    ![Adja hozzá, és a PowerShell-parancsfájlok használata a Microsoft Intune-ban](./media/mgmt-extension-add-script.png)
5. Válassza ki **OK** > **létrehozás** a parancsfájl mentéséhez.

## <a name="assign-the-policy"></a>A szabályzat hozzárendelése

1. A **PowerShell-parancsfájlok** panelen válassza ki a hozzárendelni kívánt parancsfájlt, majd válassza a **Kezelés** > **Hozzárendelések** lehetőséget.

    ![Rendelje hozzá, vagy helyezze üzembe a PowerShell-parancsprogram eszközcsoportokra a Microsoft Intune-ban](./media/mgmt-extension-assignments.png)

2. Az elérhető Azure AD-csoportok listázásához válassza a **Csoportok kiválasztása** lehetőséget. 
3. Válassza ki egy vagy több olyan csoportot, amely tartalmazza a felhasználókat, akiknek az eszközei kap a parancsfájlt. Válassza a **Kiválasztás** lehetőséget a szabályzat kijelölt csoportokhoz rendeléséhez.

> [!NOTE]
> - Jelentkezzen be az eszköz PowerShell-szkriptek végrehajtása a végfelhasználók számára nem szükséges.
> - Az Intune-ban a PowerShell-parancsfájlok megcélozhatóvá válnak az Azure AD-eszközök biztonsági csoportjainak.
> - Az Intune-ban a PowerShell-parancsfájlok megcélozhatóvá válnak az Azure AD-felhasználó biztonsági csoportokba.

Az Intune felügyeleti bővítmény ügyfél óránként egyszer ellenőrzi, és minden új parancsfájlokat vagy-változások az Intune-nal rendszer újraindítása után. Miután hozzárendelte a szabályzatot az Azure AD-csoportokhoz, elindul a PowerShell-parancsfájl, és elkészül a futtatási eredmények jelentése. A szkript végrehajtása után a nem újra végrehajtani, kivéve, ha módosítják a parancsfájl vagy a szabályzat.

## <a name="monitor-run-status"></a>Futási állapotának figyelése

Megfigyelheti a felhasználók és eszközök PowerShell-parancsfájljainak futtatási állapotát az Azure Portalon.

A **PowerShell-parancsfájlok** panelen válassza ki a megfigyelendő parancsfájlt, válassza a **Figyelés** lehetőséget, majd válassza az alábbi jelentések egyikét:

- **Eszközállapot**
- **Felhasználó állapota**

## <a name="troubleshoot-scripts"></a>Parancsfájlok hibáinak elhárítása

Az ügyfélszámítógépen Agent-naplók általában a rendszer `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Használhat [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) , ezek a naplófájlok megtekintése. 

![Képernyőkép vagy minta cmtrace agent-naplók a Microsoft Intune-ban](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>A parancsfájl törlése

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

#### <a name="issue-powershell-scripts-do-not-run"></a>A probléma leírása: PowerShell-parancsfájlok nem működnek.

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

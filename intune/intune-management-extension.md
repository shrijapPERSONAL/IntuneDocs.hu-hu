---
title: PowerShell-parancsfájlok hozzáadása a Microsoft Intune - Azure-ban Windows 10 rendszerű eszközökre |} A Microsoft Docs
description: Hozzon létre és a PowerShell-parancsfájlok futtatása, a parancsfájlhoz tartozó házirend hozzárendelése az Azure Active Directory-csoportok, jelentések használatával figyelheti a szkriptek és a lépések a Windows 10 rendszerű eszközökön a Microsoft Intune-ban hozzáadhat parancsprogramokat törlése. Néhány gyakori problémák és megoldásuk is megtekintheti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 90b3e858a06a6f3a34de6ec8102e1a6c458369a2
ms.sourcegitcommit: cd451ac487c7ace18ac9722a28b9facfba41f6d3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67298419"
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

Az Intune felügyeleti bővítmény előfeltételei a következők. Amint ezek teljesülnek, az Intune felügyeleti bővítmény telepítése automatikusan megtörténik egy PowerShell-parancsprogram, vagy Win32-alkalmazás hozzá van rendelve a felhasználó vagy eszköz.

- Az eszközök a Windows 10-es verzió fut, 1607-es vagy újabb. Ha az eszköz regisztrálva van a használatával [automatikus igénylés tömeges](windows-bulk-enroll.md), eszközöket kell futtatni a Windows 10-es verzió, 1703-as vagy újabb. Az Intune felügyeleti bővítmény módban nem támogatott a Windows 10 S, mivel S mód nem engedélyezi áruházon belüli alkalmazások futtatásához. 
  
- Tartományhoz csatlakozó eszközök az Azure Active Directory (AD), beleértve:  
  
  - Hibrid Azure AD-hez csatlakoztatott: Eszközök az Azure Active Directory (AD) tartományhoz, és csatlakoztatva a helyszíni Active Directory (AD). Lásd: [a hibrid Azure Active Directory join implementáció megtervezésébe](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) útmutatást.

- Az Intune-ban regisztrált eszközök többek között:

  - Eszközök regisztrálása a csoportházirend (GPO). Lásd: [automatikusan a csoportházirend segítségével a Windows 10-es eszközök](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) útmutatást.
  
  - Manuálisan regisztrált eszközök az Intune-ban, amely a következő esetekben:
  
    - [Automatikus regisztráció az Intune-bA](quickstart-setup-auto-enrollment.md) engedélyezve van az Azure ad-ben. A végfelhasználó számára az eszköz helyi felhasználói fiókkal jelentkezik be, manuálisan csatlakoztatja az eszközt az Azure AD- és majd bejelentkezik az eszközre, az Azure AD-fiókjával.
    
    VAGY  
    
    - Felhasználó jelentkezik be az eszközt az Azure AD-fiókjával, és ezután regisztrálja az Intune-ban.

  - Közösen kezelt eszközök, amelyek a Configuration Manager és az Intune-ban. Győződjön meg a **ügyfélalkalmazás** munkaterhelés értékre van állítva **az Intune-próbaüzem** vagy **Intune**. Tekintse meg a következő útmutatást: 
  
    - [Mi a megosztott kezelés](https://docs.microsoft.com/sccm/comanage/overview) 
    - [Ügyfél apps munkafolyamat](https://docs.microsoft.com/sccm/comanage/workloads#client-apps)
    - [Configuration Manager számításai az Intune-hoz](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads)
  
> [!TIP]
> Lehet, hogy eszközök [csatlakoztatott](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) az Azure ad-hez. Eszközök, amelyek csak [regisztrált](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) az Azure ad-ben nem kap a parancsfájlokat.

## <a name="create-a-script-policy"></a>A parancsfájlhoz tartozó szabályzat létrehozása 

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza az **Eszközkonfiguráció** > **PowerShell-parancsfájlok** > **Hozzáadás** lehetőséget.
3. Adja meg a következő tulajdonságokat:
    - **Név**: Adjon meg egy nevet a PowerShell-parancsfájlt. 
    - **Description** (Leírás): Adjon meg egy leírást a PowerShell-parancsfájlt. A beállítás használata nem kötelező, de ajánlott. 
    - **Parancsfájl helye**: Keresse meg a PowerShell-parancsfájlt. A szkript kevesebb, mint 200 KB (ASCII) kell lennie.
4. Válasszon **konfigurálása**, és adja meg a következő tulajdonságokat:
    - **Futtassa ezt a szkriptet a hitelesítő adatok használatával a bejelentkezett**: Válassza ki **Igen** a parancsfájl futtatásához a felhasználó hitelesítő adataival az eszközön. Válasszon **nem** (alapértelmezett), a parancsfájl futtatásához a rendszerkörnyezetben. A rendszergazdák számos **Igen**. Ha a parancsfájl a rendszerkörnyezetben futtatásához szükséges, válassza a **nem**.
    - **Ellenőrzésének kényszerítése**: Válassza ki **Igen** , ha a parancsfájl megkövetelje-e egy megbízható közzétevő. Válassza ki **nem** (alapértelmezett), ha egy követelmény a parancsfájl aláírása nem áll rendelkezésre. 
    - **Futtassa a szkriptet a PowerShell-gazdagépet 64 bites**: Válassza ki **Igen** , futtassa a parancsfájlt a PowerShell (PS) 64 bites gazdagépen egy 64 bites ügyfél architektúrájának. Válassza ki **nem** (alapértelmezett) a 32 bites PowerShell-gazdagépet a parancsfájlt futtatja.

      Ha beállítás **Igen** vagy **nem**, a következő táblázat tartalmazza ezen új és meglévő szabályzat:

      | Futtassa a szkriptet a 64 bites PS gazdagép | Ügyfél-architektúrája | Új PS-parancsprogram | Meglévő házirend PS-parancsprogram |
      | --- | --- | --- | --- | 
      | Nem | 32 bites  | támogatja a 32 bites PS állomás | Csak 32 bites PS gazdagéptől, ami 32 bites és 64 bites rendszereken futtatható. |
      | Igen | 64 bites | 64 bites PS fogadó 64 bites architektúrák parancsfájlt futtatja. Ha 32 bites futtatunk, a szkript futtatása a 32 bites PS gazdagépen. | 32 bites PS fogadó parancsfájlt futtatja. Ha 64 bites, a (ez nem fut) parancsfájl megnyílik egy 64 bites PS gazdagépre, és a jelentésekben az eredmények módosítja ezt a beállítást. Ha 32 bites futtatunk, a szkript futtatása a 32 bites PS gazdagépen. |

    ![Adja hozzá, és a PowerShell-parancsfájlok használata a Microsoft Intune-ban](./media/mgmt-extension-add-script.png)
5. Válassza ki **OK** > **létrehozás** a parancsfájl mentéséhez.

> [!NOTE]
> Parancsprogramok vannak beállítva, hogy a felhasználói környezetet, és a felhasználó rendelkezik rendszergazdai jogosultságokkal, alapértelmezés szerint, ha a PowerShell-parancsfájlt a rendszergazdai jogosultsággal alatt fut.

## <a name="assign-the-policy"></a>A szabályzat hozzárendelése

1. A **PowerShell-parancsfájlok** panelen válassza ki a hozzárendelni kívánt parancsfájlt, majd válassza a **Kezelés** > **Hozzárendelések** lehetőséget.

    ![Rendelje hozzá, vagy helyezze üzembe a PowerShell-parancsprogram eszközcsoportokra a Microsoft Intune-ban](./media/mgmt-extension-assignments.png)

2. Az elérhető Azure AD-csoportok listázásához válassza a **Csoportok kiválasztása** lehetőséget. 
3. Válassza ki egy vagy több olyan csoportot, amely tartalmazza a felhasználókat, akiknek az eszközei kap a parancsfájlt. Válassza a **Kiválasztás** lehetőséget a szabályzat kijelölt csoportokhoz rendeléséhez.

> [!NOTE]
> - Jelentkezzen be az eszköz PowerShell-szkriptek végrehajtása a végfelhasználók számára nem szükséges.
> - PowerShell-parancsfájlokat az Intune-ban az Azure AD-eszközök biztonsági csoportjainak vagy az Azure AD-felhasználó biztonsági csoportjai célozhatók lesznek.

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

#### <a name="issue-intune-management-extension-doesnt-download"></a>A probléma leírása: Az Intune felügyeleti bővítmény nem sikerül letölteni.

**A lehetséges megoldások**:

- Az eszköz nem csatlakozik tartományhoz, az Azure ad-hez. Győződjön meg az eszközök megfelelnek a [Előfeltételek](#prerequisites) (a jelen cikkben). 
- Nincsenek PowerShell-parancsfájlok vagy Win32-alkalmazások, a társított, amely a felhasználó vagy eszköz tartozik.
- Az eszköz nem be az Intune szolgáltatás, nincs internet-hozzáférés miatt nem érhető el a Windows leküldéses értesítési szolgáltatása (WNS), és így tovább.
- Az eszköz S módban van. Az Intune felügyeleti bővítmény S módban rendszerű eszközökön nem támogatott. 

Ha az eszköz automatikus regisztrált megtekintéséhez a következőket teheti:

  1. Lépjen a **beállítások** > **fiókok** > **hozzáférés munkahelyi vagy iskolai**.
  2. Válassza ki a csatlakoztatott fiókot > **Info**.
  3. A **speciális diagnosztikai jelentés**válassza **jelentés létrehozása**.
  4. Nyissa meg a `MDMDiagReport` egy webböngészőben.
  5. Keresse meg a **MDMDeviceWithAAD** tulajdonság. Ha a tulajdonság már létezik, az eszköz, automatikusan regisztrálva. Ha ez a tulajdonság nem létezik, az eszköz nem, automatikusan regisztrálva.

[A Windows 10 automatikus regisztrációjának engedélyezése](windows-enroll.md#enable-windows-10-automatic-enrollment) automatikus igénylés konfigurálása az Intune-ban a lépéseket tartalmazza.

#### <a name="issue-powershell-scripts-do-not-run"></a>A probléma leírása: PowerShell-parancsfájlok nem működnek.

**A lehetséges megoldások**:

- A PowerShell-parancsfájlok minden bejelentkezéskor nem futnak. Futtassa:

  - Ha a parancsfájl egy az eszközhöz rendelt
  - Ha módosítja a parancsfájlt, és töltse fel, a parancsfájl hozzárendelése egy felhasználóhoz vagy eszközhöz
  
    > [!TIP]
    > A **a Microsoft Intune felügyeleti bővítmény** egy szolgáltatás, amely futtatja az eszközön, ugyanúgy, mint bármely más szolgáltatást a szolgáltatások alkalmazást (services.msc) szerepel. Miután egy eszköz újraindult, ezt a szolgáltatást előfordulhat, hogy is indítsa újra, és ellenőrizze minden hozzárendelt a PowerShell-parancsfájlok és az Intune szolgáltatás. Ha a **a Microsoft Intune felügyeleti bővítmény** szolgáltatás a Manual értékre van állítva, akkor előfordulhat, hogy indítsa újra a szolgáltatás, az eszköz újraindítása után.

- Lehet, hogy eszközök [az Azure AD-csatlakoztatott](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Csak a munkahelyi vagy szervezeti csatlakoztatott eszközök ([regisztrált](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) az Azure AD) a parancsfájlok nem kap.
- Az Intune felügyeleti bővítmény ügyfél ellenőrzi a módosításokat a parancsfájl vagy a szabályzat az Intune-ban óránként egyszer.
- Győződjön meg róla, az Intune felügyeleti bővítmény letöltődik minden olyan `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Parancsfájlok S módban a Surface Hubokban vagy a Windows 10-es nem futnak.
- Tekintse át a naplóiban található hibaüzeneteket. Lásd: [parancsfájlok hibaelhárítása](#troubleshoot-scripts) (a jelen cikkben).
- Lehetséges engedélyekkel kapcsolatos problémák, lehet, hogy a PowerShell-parancsfájl tulajdonságai vannak beállítva `Run this script using the logged on credentials`. Emellett ellenőrizze, hogy a bejelentkezett felhasználó rendelkezik-e a megfelelő engedélyekkel a parancsfájl futtatásához.

- Parancsfájl-kezelési probléma azonosítása, tegye a következőket:

  - Tekintse át a PowerShell-végrehajtás konfigurálását az eszközökön. Tekintse meg a [PowerShell végrehajtási házirend](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) útmutatást.
  - Az Intune felügyeleti bővítmény használatával minta parancsfájl futtatása. Hozzon létre például a `C:\Scripts` könyvtárat, és adjon mindenkinek teljes hozzáférése. Futtassa a következő parancsfájlt:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Ha ez sikeres, a kimenet.txt kell létrehozni, és tartalmaznia kell a "Szkript működött" szöveget.

  - Parancsfájl végrehajtása nélkül Intune teszteléséhez a szkriptek futtatása a System fiók használata a [psexec eszköz](https://docs.microsoft.com/sysinternals/downloads/psexec) helyileg:

    `psexec -i -s`

## <a name="next-steps"></a>További lépések

[A figyelő](device-profile-monitor.md) és [hibaelhárítása](device-profile-troubleshoot.md) a profilok.

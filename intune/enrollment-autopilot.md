---
title: Eszközök regisztrálása a Windows AutoPilot használatával
titleSuffix: Microsoft Intune
description: Útmutató Windows 10-eszközök regisztrálásához a Windows AutoPilot használatával.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: b3c374e4ce6baeab8cc6fde3f6c45c63c48e34dd
ms.sourcegitcommit: d99def6e4ceb44f3e7ca10fe7cdd7f222cf814c8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903075"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Windows-eszközök regisztrálása a Windows AutoPilot használatával
A Windows AutoPilot leegyszerűsíti az eszközök üzembe helyezését. A testre szabott operációsrendszer-lemezképek létrehozása és karbantartása sok időt vesz igénybe. Gyakran ezeknek az egyéni operációsrendszer-lemezképeknek az új eszközökre való alkalmazásával is időt kell töltenie, hogy felkészítse az eszközöket a használatra, mielőtt a végfelhasználóknak adná azokat. A Microsoft Intune és az AutoPilot révén új eszközöket adhat hozzá a végfelhasználók számára anélkül, hogy egyéni operációsrendszer-lemezképek létrehozására, kezelésére és az eszközökre való alkalmazására lenne szükség. Az AutoPilot-eszközök Intune-nal való felügyelete során a regisztrációt követően szabályzatokat, profilokat, alkalmazásokat és sok mást is kezelni tud. A megoldás előnyeinek, használati eseteinek és előfeltételeinek áttekintéséhez lásd [a Windows AutoPilot áttekintését](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Előfeltételek
- [Engedélyezni kell a Windowsos eszközök automatikus regisztrációját](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Prémium szintű Azure Active Directory előfizetéssel kell rendelkeznie](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Eszközök felvétele

Windows AutoPilot-eszközök felvételéhez importálhat egy CSV-fájlt az adataikkal.

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** > **Importálás** elemet.

    ![Windows AutoPilot-eszközök képernyőképe](media/enrollment-autopilot/autopilot-import-device.png)

2. A **Windows AutoPilot-eszközök hozzáadása** alatt keresse meg a hozzáadni kívánt eszközöket felsoroló CSV-fájlt. A fájlnak tartalmaznia kell a sorozatszámokat, a Windows-termékazonosítókat és a hardverkivonatokat, és tartalmazhatja az eszközök rendelésazonosítóit is.

    ![Képernyőkép Windows AutoPilot-eszközök felvételéről](media/enrollment-autopilot/autopilot-import-device2.png)

3. Válassza az **Importálás** lehetőséget az eszközadatok importálásának elindításához. Az importálás több percig is eltarthat.

4. Az importálás befejezése után válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Windows AutoPilot** > **Eszközök** > **Szinkronizálás** lehetőséget. Egy üzenet jelenik meg, hogy a szinkronizálás folyamatban van. Nagyszámú eszköz szinkronizálása esetén előfordulhat, hogy várnia kell pár percet, amíg a folyamat befejeződik.

5. Frissítse a nézetet az új eszközök megjelenítéséhez.

## <a name="create-an-autopilot-device-group"></a>AutoPilot-eszközcsoport létrehozása

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza a **Csoportok** elemet.
2. A **Csoport** panelen:
    1. A **Csoport típusa** beállításnál válassza a **Biztonsági** lehetőséget.
    2. Gépelje be a **Csoport nevét** és a **Csoport leírását**.
    3. A **Tagság típusa** beállításnál válassza a **Hozzárendelt** vagy a **Dinamikus eszköz** lehetőséget.
3. Ha a **Tagság típusa** alatt az előző lépésben a **Hozzárendelt** lehetőséget választotta, akkor válassza a **Csoport** panel **Tagok** elemét, és adjon hozzá AutoPilot-eszközöket a csoporthoz.
    A még nem regisztrált AutoPilot-eszközök azok, amelyeknek a neve megegyezik az eszköz sorozatszámával.
4. Ha a **Tagság típusa** alatt a **Dinamikus eszköz** lehetőséget választotta, akkor válassza a **Csoport** panel **Dinamikus eszköz tagok** lehetőségét, és gépelje be az alábbi kódok bármelyikét a **Speciális szabály** mezőbe.
    - Ha az összes AutoPilot-eszközét tartalmazó csoportot kíván létrehozni, gépelje be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Ha egy adott rendelésazonosítóval rendelkező összes AutoPilot-eszközét tartalmazó csoportot kíván létrehozni, gépelje be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Ha egy adott beszerzési rendelésazonosítóval rendelkező összes AutoPilot-eszközét tartalmazó csoportot kíván létrehozni, gépelje be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    A **Speciális szabály** kódjának megadása után válassza a **Mentés** lehetőséget.
5. Válassza a **Létrehozás** lehetőséget.



## <a name="create-an-autopilot-deployment-profile"></a>AutoPilot Deployment-profil létrehozása
Az AutoPilot Deployment-profilok segítségével konfigurálhatja az AutoPilot-eszközöket.
1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** elemet.
2. Adjon meg egy **Nevet**, és igény esetén **Leírást**.
3. A **Telepítési mód** beállításnál két lehetőség közül választhat:
    - **Felhasználó-alapú**: Az ilyen profillal rendelkező eszközök az őket regisztráló felhasználóhoz vannak társítva. Az eszköz telepítéséhez felhasználói hitelesítő adatokra van szükség.
    - **Öntelepítő (előzetes verzió)**: (Windows 10 Insider Preview Build 17672 vagy újabb) Az ilyen profillal rendelkező eszközök nincsenek az őket regisztráló felhasználóhoz társítva. Az eszköz telepítéséhez nincs szükség felhasználói hitelesítő adatokra.
4. A **Csatlakozás az Azure AD-hez mint** mezőben válassza az **Azure AD-hez csatlakoztatott** lehetőséget.
5. Válassza a **Kezdőélmény (OOBE)** lehetőséget, konfigurálja a következő beállításokat, majd válassza a **Mentés** lehetőséget:
    - **Nyelv (Régió)**\*: Válassza ki az eszközön használandó nyelvet. Ez a lehetőség csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő** lehetőséget választotta.
    - **Billentyűzet automatikus konfigurálása**\*: Ha a **Nyelv (Régió)** ki van választva, akkor hagyja ki a billentyűzetválasztó oldalt. Ez a lehetőség csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő** lehetőséget választotta.
    - **Végfelhasználói licencszerződés (EULA)**: (Windows 10, 1709 vagy újabb verzió) válasszon, hogy a felhasználók számára megjelenjen-e a végfelhasználói licencszerződés.
    - **Adatvédelmi beállítások**: válasszon, hogy a felhasználók számára megjelenjenek-e az adatvédelmi beállítások.
    - **Felhasználói fiók típusa**: válassza ki, hogy a felhasználói fiók típusa egy **Rendszergazdafiók**, vagy **Általános jogú** felhasználó-e. 

6. Válassza a **Létrehozás** lehetőséget a profil létrehozásához. Az AutoPilot Deployment-profil ettől kezdve már hozzárendelhető az eszközökhöz.

A **Nyelv (Régió)** és a **Billentyűzet automatikus konfigurálása** is csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő (előzetes verzió)** lehetőséget választja (Windows 10 Insider Preview Build 17672 vagy újabb verzió esetén).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>AutoPilot telepítési profil hozzárendelése eszközcsoporthoz

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Telepítési profilok** elemet, majd válasszon egy profilt.
2. A megadott profil paneljén válassza a **Hozzárendelések** elemet. 
3. Válassza a **Csoportok kijelölése** lehetőséget, majd a **Csoportok kijelölése** panelen jelölje ki a csoport(ok)at, amelyekhez a profilt hozzá kívánja rendelni, végül válassza a **Kijelölés** lehetőséget.

## <a name="edit-an-autopilot-deployment-profile"></a>AutoPilot Deployment-profil szerkesztése
Az AutoPilot Deployment-profil létrehozását követően módosíthatja a telepítési profil egyes részeit.   

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** elemet.
2. A **Windows-regisztráció** terület **Windows AutoPilot** szakaszában válassza a **Telepítési profilok** lehetőséget.
3. Válassza ki a szerkeszteni kívánt profilt.
4. A telepítési profil nevének vagy leírásának módosításához kattintson a bal oldali **Tulajdonságok** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.
5. A Kezdőélmény beállításainak módosításához kattintson a **Beállítások** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.

> [!NOTE]
> A profil módosításai alkalmazva lesznek a profilhoz társított eszközökön. Azonban a frissített profilt az Intune-ban korábban már regisztrált eszközökre csak azok alaphelyzetbe állítása és megújítása után alkalmazza a rendszer.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>A Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztások <!-- 163236 -->
Egy riasztást megtekintve láthatja, hogy az AutoPilot-programban hány eszközhöz nincs hozzárendelve AutoPilot telepítési profil. A riasztás adatai alapján a profilok létrehozhatók és a hozzárendelés nélküli eszközökhöz rendelhetők. A riasztásra kattintva megjelenik a Windows AutoPilot-eszközök részletes adatokat is tartalmazó, teljes listája.

A nem társított eszközökre vonatkozó riasztások megtekintéséhez az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Áttekintés** > **Nem társított eszközök** lehetőséget.  

## <a name="delete-autopilot-devices"></a>AutoPilot-eszközök törlése

A nem regisztrált Windows AutoPilot-eszközök törölhetők.

1. Ha az eszközök regisztrálva vannak az Intune-ban, akkor először [törölnie kell azokat az Azure Active Directory portálról](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** lehetőséget.

3. A **Windows AutoPilot-eszközök** területen jelölje ki a törölni kívánt eszközöket, majd válassza a **Törlés** gombot.

4. Hagyja jóvá a törlést az **Igen** választásával. A törlés eltarthat néhány percig.

## <a name="using-autopilot-in-other-portals"></a>Az AutoPilot használata más portálokon
Ha nem érdekli a mobileszköz-kezelés, használhatja az AutoPilot megoldást például a Vállalati Microsoft Áruházban. A más portálok használata elérhető lehetőség, de csak az AutoPilot használatával történő központi telepítések felügyeletéhez javasolt használni. Az Intune és egy másik portál használatakor az Intune nem tudja:
- Megjeleníteni az Intune-ban létrehozott, de egy másik portálon szerkesztett profilok módosításait
- Szinkronizálni egy másik portálon létrehozott profilokat
- Megjeleníteni a profil-hozzárendelések más portálon végzett módosításait
- Szinkronizálni a más portálon végzett profil-hozzárendeléseket
- Megjeleníteni az eszközlista más portálon végzett módosításait

## <a name="next-steps"></a>További lépések
Miután konfigurálta a Windows AutoPilotot regisztrált Windows 10 rendszerű eszközökhöz, sajátítsa el azok felügyeletét. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](https://docs.microsoft.com/intune/device-management) című témakörben talál.

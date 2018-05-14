---
title: Eszközök regisztrálása a Windows AutoPilot Deployment Program használatával
titleSuffix: Microsoft Intune
description: Útmutató Windows 10-eszközök regisztrálásához a Windows AutoPilot Deployment Program használatával.
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
ms.openlocfilehash: 934b80d1c174c25d37e30695f46afc88c8d8bfc3
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2018
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot-deployment-program"></a>Windows-eszközök regisztrálása a Windows AutoPilot Deployment Program használatával
A Windows AutoPilot Deployment Program leegyszerűsíti az eszközök üzembe helyezését. A testre szabott operációsrendszer-lemezképek létrehozása és karbantartása sok időt vesz igénybe. Gyakran ezeknek az egyéni operációsrendszer-lemezképeknek az új eszközökre való alkalmazásával is időt kell töltenie, hogy felkészítse az eszközöket a használatra, mielőtt a végfelhasználóknak adná azokat. A Microsoft Intune és az AutoPilot révén új eszközöket adhat hozzá a végfelhasználók számára anélkül, hogy egyéni operációsrendszer-lemezképek létrehozására, kezelésére és az eszközökre való alkalmazására lenne szükség. Az Intune AutoPilot-eszközök felügyeletére való használatakor regisztrálásukat követően kezelheti az eszközökön a szabályzatokat, profilokat, alkalmazásokat és így tovább. A megoldás előnyeinek, használati eseteinek és előfeltételeinek áttekintéséhez lásd [a Windows AutoPilot áttekintését](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Előfeltételek
- [Engedélyezni kell a Windowsos eszközök automatikus regisztrációját](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Prémium szintű Azure Active Directory előfizetéssel kell rendelkeznie](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Eszközök felvétele

Windows AutoPilot-eszközök felvételéhez importálhat egy CSV-fájlt az adataikkal.

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** > **Importálás** elemet.

    ![Windows AutoPilot-eszközök képernyőképe](media/enrollment-autopilot/autopilot-import-device.png)

2. A **Windows AutoPilot-eszközök hozzáadása** alatt tallózzon a hozzáadni kívánt eszközök sorozatszámait, Windows-termékazonosítóit és hardverkivonatait tartalmazó CSV-fájlhoz.

    ![Képernyőkép Windows AutoPilot-eszközök felvételéről](media/enrollment-autopilot/autopilot-import-device2.png)

3. Válassza az **Importálás** lehetőséget az eszközadatok importálásának elindításához. Ez néhány percig tarthat.

## <a name="synchronize-devices"></a>Eszközök szinkronizálása
Szinkronizálja a regisztrált eszközöket az Intune-ban, hogy konfigurálhassa őket.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** területen az **Eszközregisztráció** lehetőséget.
4. Válassza a **Windows-alapú regisztráció** lehetőséget, majd a **Windows AutoPilot Deployment Program** szakaszban válassza az **Eszközök** lehetőséget.
5. Kattintson a **Szinkronizálás** lehetőségre a regisztrált eszközök importálásához. Egy üzenet jelenik meg, hogy a szinkronizálás folyamatban van.
6. Frissítse a nézetet az új eszközök megjelenítéséhez. Nagyszámú eszköz szinkronizálása esetén előfordulhat, hogy várnia kell pár percet, amíg a folyamat befejeződik.  

## <a name="create-an-autopilot-deployment-profile"></a>AutoPilot Deployment-profil létrehozása
Az AutoPilot Deployment-profilok segítségével konfigurálhatja az AutoPilot-eszközöket.
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** területen az **Eszközregisztráció** lehetőséget.
4. Válassza a **Windows-alapú regisztráció** lehetőséget, majd a **Windows AutoPilot Deployment Program** szakaszban válassza a **Telepítési profilok** lehetőséget.
5. Válassza a **Profil létrehozása** lehetőséget, és válasszon egy nevet és leírást (utóbbi elhagyható).
6. A **Csatlakozás az Azure AD-hez mint** beállításnál válassza az **Azure AD-hez csatlakoztatott** lehetőséget.
7. A **Kezdőélmény (OOBE)** esetében konfigurálja a következő beállításokat, majd kattintson a **Mentés** gombra:

   - **Végfelhasználói licencszerződés (EULA)**: válasszon, hogy a felhasználók számára megjelenjen-e a végfelhasználói licencszerződés.
   - **Adatvédelmi beállítások**: válasszon, hogy a felhasználók számára megjelenjenek-e az adatvédelmi beállítások.
   - **Felhasználói fiók típusa**: válassza ki, hogy a felhasználói fiók típusa egy **Rendszergazdafiók**, vagy **Általános jogú** felhasználó-e.

     > [!Note]    
     > Ez a beállítás nem vonatkozik a globális rendszergazdai vagy a vállalati rendszergazdai fiókokra. Ezek a fiókok nem tartozhatnak sztenderd felhasználókhoz, mert hozzáféréssel rendelkeznek az Azure AD minden felügyeleti funkciójához.


6. Kattintson a **Létrehozás** elemre a profil létrehozásához. Az AutoPilot Deployment-profil ettől kezdve már hozzárendelhető az eszközökhöz.

> [!Note]    
> A következő beállítások az összes AutoPilot Deployment-profilra kiterjednek:
> - A Cortana, a OneDrive és az OEM-regisztráció beállításlapjainak kihagyása
> - Munkahelyi vagy iskolai fiók automatikus beállítása
> - Céges vagy iskolai arculatot használó bejelentkezési módszer    

## <a name="assign-an-autopilot-deployment-profile"></a>AutoPilot Deployment-profil hozzárendelése
Miután létrehozta az AutoPilot Deployment-profilokat, hozzárendelheti azokat a kiválasztott eszközökhöz.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** területen az **Eszközregisztráció** lehetőséget.
4. Válassza a **Windows-alapú regisztráció** lehetőséget, majd a **Windows AutoPilot Deployment Program** szakaszban válassza az **Eszközök** lehetőséget.
5. Válassza ki, hogy mely eszközökhöz szeretné hozzárendelni a központi telepítési profilt. A **Profil állapota** oszlop szűrésével könnyedén megtalálhatja a hozzárendelt profil nélküli eszközöket.
6. Kattintson a **Profil hozzárendelése** lehetőségre, válassza ki az AutoPilot Deployment-profilt, és kattintson a **Hozzárendelés** elemre. Egy üzenet jelenik meg, hogy a hozzárendelés folyamatban van.
7. Frissítse a nézetet annak megjelenítéséhez, hogy vannak-e a profilhoz rendelt eszközök. A folyamat eltarthat néhány percig, attól függően, hogy hány eszközt választott ki.

> [!Note]
> A rendszer hozzárendeli az eszközhöz az új profilt, Az Intune-ban már regisztrált eszközökre azonban a profil csak az eszköz alaphelyzetbe állítása és ismételt regisztrálása után lesz alkalmazva.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Másik AutoPilot Deployment-profil hozzárendelése
Ha már hozzárendelt egy AutoPilot Deployment-profilt egy eszközhöz, és egy másik profilt szeretne hozzárendelni, rendelje az új profilt az eszközhöz.  

## <a name="edit-an-autopilot-deployment-profile"></a>AutoPilot Deployment-profil szerkesztése
Az AutoPilot Deployment-profil létrehozását követően módosíthatja a telepítési profil egyes részeit.   

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** területen az **Eszközregisztráció** lehetőséget.
4. A **Windows-alapú regisztráció** terület **Windows AutoPilot Deployment Program** szakaszában válassza a **Telepítési profilok** lehetőséget.
5. Válassza ki a szerkeszteni kívánt profilt.
6. A telepítési profil nevének vagy leírásának módosításához kattintson a bal oldali **Tulajdonságok** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.
7. A Kezdőélmény beállításainak módosításához kattintson a **Beállítások** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.

> [!NOTE]
> A frissített profil hozzá van rendelve eszközökhöz. Azonban a frissített profilt az Intune-ban korábban már regisztrált eszközökre csak azok alaphelyzetbe állítása és megújítása után alkalmazza a rendszer.

## <a name="using-autopilot-in-other-portals"></a>Az AutoPilot használata más portálokon
Ha nem érdekli a mobileszköz-kezelés, használhatja az AutoPilot megoldást például a Vállalati Microsoft Áruházban. A más portálok használata elérhető lehetőség, de csak az AutoPilot használatával történő központi telepítések felügyeletéhez javasolt használni. Az Intune és egy másik portál használatakor az Intune nem tudja:
- Megjeleníteni az Intune-ban létrehozott, de egy másik portálon szerkesztett profilok módosításait
- Szinkronizálni egy másik portálon létrehozott profilokat
- Megjeleníteni a profil-hozzárendelések más portálon végzett módosításait
- Szinkronizálni a más portálon végzett profil-hozzárendeléseket
- Megjeleníteni az eszközlista más portálon végzett módosításait

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>A Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztások <!-- 163236 -->
Megjeleníthet a Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztásokat, hogy megtudja, az AutoPilot programban résztvevő eszközök közül hányhoz nincs hozzárendelve AutoPilot Deployment-profil. A riasztás adatai alapján a profilok létrehozhatók és a hozzárendelés nélküli eszközökhöz rendelhetők. A riasztásra kattintva megjelenik a Windows AutoPilot-eszközök részletes adatokat is tartalmazó, teljes listája.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** területen az **Eszközregisztráció** lehetőséget.
4. A riasztás megjelenítéséhez válassza az **Áttekintés** lehetőséget. Az AutoPilot-eszközök listájának megjelenítéséhez kattintson a riasztásra.  

## <a name="delete-autopilot-devices"></a>AutoPilot-eszközök törlése

A nem regisztrált Windows AutoPilot-eszközök törölhetők. Megszüntetheti az eszközök regisztrációját, és törölheti őket.

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** lehetőséget.

2. A **Windows AutoPilot-eszközök** területen jelölje ki a törölni kívánt eszközöket, majd válassza a **Törlés** gombot.

3. Hagyja jóvá a törlést az **Igen** választásával. A törlés eltarthat néhány percig.


## <a name="next-steps"></a>További lépések
Miután konfigurálta a Windows AutoPilotot regisztrált Windows 10 rendszerű eszközökhöz, sajátítsa el azok felügyeletét. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](https://docs.microsoft.com/intune/device-management) című témakörben talál.

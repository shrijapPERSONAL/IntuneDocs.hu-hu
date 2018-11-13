---
title: Eszközök regisztrálása a Windows AutoPilot használatával
titleSuffix: Microsoft Intune
description: Útmutató a Windows 10-eszközök Windows AutoPilot használatával történő regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 5fa3079c994a2e0ea2d587185e12c52085133f9c
ms.sourcegitcommit: 814d1d473de2de2e735efab826b1091de2b093f5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025185"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Windows-eszközök regisztrálása a Windows AutoPilot használatával  
A Windows AutoPilot leegyszerűsíti az eszközök regisztrálását. A testre szabott operációsrendszer-lemezképek létrehozása és karbantartása sok időt vesz igénybe. Gyakran ezeknek az egyéni operációsrendszer-lemezképeknek az új eszközökre való alkalmazásával is időt kell töltenie, hogy felkészítse az eszközöket a használatra, mielőtt a végfelhasználóknak adná azokat. A Microsoft Intune és az AutoPilot révén új eszközöket adhat hozzá a végfelhasználók számára anélkül, hogy egyéni operációsrendszer-lemezképek létrehozására, kezelésére és az eszközökre való alkalmazására lenne szükség. Az AutoPilot-eszközök Intune-nal való felügyelete során a regisztráció után szabályzatokat, profilokat, alkalmazásokat és sok mást is kezelni tud. A megoldás előnyeinek, használati eseteinek és előfeltételeinek áttekintéséről lásd [a Windows AutoPilot áttekintését](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Előfeltételek
- [Engedélyezni kell a Windowsos eszközök automatikus regisztrációját](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Prémium szintű Azure Active Directory előfizetéssel kell rendelkeznie](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>CSV-fájl letöltése importáláshoz az InTune-ban

Ennek használatáról a PowerShell parancsmag ismertetése című rész szolgál további információkkal.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo/1.3/Content/Get-WindowsAutoPilotInfo.ps1)

## <a name="add-devices"></a>Eszközök felvétele

A Windows AutoPilot-eszközök felvételéhez importálhat egy CSV-fájlt az adataikkal.

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** > **Importálás** elemet.

    ![A Windows AutoPilot-eszközök képernyőképe](media/enrollment-autopilot/autopilot-import-device.png)

2. A **Windows AutoPilot-eszközök hozzáadása** alatt keresse meg a hozzáadni kívánt eszközöket felsoroló CSV-fájlt. A fájlnak tartalmaznia kell a sorozatszámokat, a Windows-termékazonosítókat és a hardverkivonatokat, és tartalmazhatja az eszközök rendelésazonosítóit is.

    ![A Windows AutoPilot-eszközök hozzáadásának képernyőképe](media/enrollment-autopilot/autopilot-import-device2.png)

3. Válassza az **Importálás** lehetőséget az eszközadatok importálásának elindításához. Az importálás több percig is eltarthat.

4. Az importálás befejezése után válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Windows AutoPilot** > **Eszközök** > **Szinkronizálás** lehetőséget. Egy üzenet jelenik meg, hogy a szinkronizálás folyamatban van. Nagyszámú eszköz szinkronizálása esetén előfordulhat, hogy várnia kell pár percet, amíg a folyamat befejeződik.

5. Frissítse a nézetet az új eszközök megjelenítéséhez.

## <a name="create-an-autopilot-device-group"></a>AutoPilot-eszközcsoport létrehozása

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza a **Csoportok** > **Új csoport** elemet.
2. A **Csoport** panelen:
    1. A **Csoport típusa** beállításnál válassza a **Biztonsági** lehetőséget.
    2. Gépelje be a **Csoport nevét** és a **Csoport leírását**.
    3. A **Tagság típusa** beállításnál válassza a **Hozzárendelt** vagy a **Dinamikus eszköz** lehetőséget.
3. Ha a **Tagság típusa** beállításnál az előző lépésben a **Hozzárendelt** értéket választotta, akkor válassza a **Csoport** panel **Tagok** elemét, és adjon hozzá AutoPilot-eszközöket a csoporthoz.
    A még nem regisztrált AutoPilot-eszközök olyan eszközök, amelyek neve megegyezik az eszköz sorozatszámával.
4. Ha a **Tagság típusa** alatt a **Dinamikus eszköz** lehetőséget választotta, akkor válassza a **Csoport** panel **Dinamikus eszköz tagok** lehetőségét, és gépelje be az alábbi kódok bármelyikét a **Speciális szabály** mezőbe.
    - Ha létre kíván hozni egy csoportot az összes AutoPilot-eszközéből, írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Ha létre kíván hozni egy csoportot egy adott rendelésazonosítóval rendelkező összes Autopilot-eszközből, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `.
    - Ha létre kíván hozni egy csoportot egy adott beszerzési rendelési azonosítóval rendelkező összes Autopilot-eszközből, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
    A **Speciális szabály** kódjának megadása után válassza a **Mentés** lehetőséget.
5. Válassza a **Létrehozás** lehetőséget.  

## <a name="create-an-autopilot-deployment-profile"></a>AutoPilot üzembehelyezési profil létrehozása
Az AutoPilot üzembehelyezési profilokkal konfigurálhatja az AutoPilot-eszközöket.
1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** elemet.
2. Adjon meg egy **Nevet**, és igény esetén **Leírást**.
3. Ha azt szeretné, hogy a hozzárendelt csoportokban lévő minden eszköz automatikusan átálljon az AutoPilotra, állítsa a **Minden megcélzott eszköz AutoPilot-eszközzé alakítása** beállítást **Igen** értékre. A hozzárendelt csoportokban lévő nem AutoPilot-eszközök az AutoPilot üzembehelyezési szolgáltatással regisztrálnak. A regisztráció feldolgozása 48 órát is igénybe vehet. Az eszköz regisztrációjának törlése és alaphelyzetbe állítása után az Autopilot regisztrálja az eszközt. Miután ilyen módon regisztrál egy eszközt, a beállítás letiltása vagy a profil-hozzárendelés eltávolítása nem távolítja el az eszközt az Autopilot üzembehelyezési szolgáltatásból. Ehhez [közvetlenül kell törölnie az eszközt](enrollment-autopilot.md#delete-autopilot-devices).
4. A **Telepítési mód** beállításnál két lehetőség közül választhat:
    - **Felhasználó-alapú**: Az ilyen profillal rendelkező eszközök az őket regisztráló felhasználóhoz vannak társítva. Az eszköz regisztrálásához felhasználói hitelesítő adatokra van szükség.
    - **Öntelepítő (előzetes verzió)**: (ehhez a [Windows 10 Insider előzetes buildje](https://docs.microsoft.com/windows-insider/at-work-pro/) szükséges) Az ilyen profillal rendelkező eszközök nincsenek az őket regisztráló felhasználóhoz társítva. Az eszköz telepítéséhez nincs szükség felhasználói hitelesítő adatokra.
5. A **Csatlakozás az Azure AD-hez mint** mezőben válassza az **Azure AD-hez csatlakoztatott** lehetőséget.
6. Válassza a **Kezdőélmény (OOBE)** lehetőséget, konfigurálja a következő beállításokat, majd válassza a **Mentés** lehetőséget:
    - **Nyelv (Régió)***: Válassza ki az eszközön használandó nyelvet. Ez a lehetőség csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő** lehetőséget választotta.
    - **Billentyűzet automatikus konfigurálása***: Ha a **Nyelv (Régió)** ki van választva, akkor az **Igen** lehetőség választásával hagyja ki a billentyűzetválasztó oldalt. Ez a lehetőség csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő** lehetőséget választotta.
    - **Végfelhasználói licencszerződés (EULA)**: (Windows 10, 1709-es vagy újabb verzió) Eldöntheti, hogy a felhasználók számára megjelenjen-e a végfelhasználói licencszerződés.
    - **Adatvédelmi beállítások**: Eldöntheti, hogy a felhasználók számára megjelenjenek-e az adatvédelmi beállítások.
    - **Fiókváltási lehetőségek elrejtése (csak a Windows Insiderben)**: Az **Elrejtés** beállítás kiválasztásával megakadályozhatja, hogy a fiókváltási lehetőségek megjelenjenek a vállalati bejelentkezési oldalakon és a tartományi hibalapokon. Ez a beállítás megköveteli, hogy [az Azure Active Directoryban konfigurálva legyen a Vállalati védjegyezés](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Felhasználói fiók típusa**: Válassza ki a felhasználói fiók típusát (**Rendszergazda** vagy **Normál**).
    - **Számítógépnév-sablon alkalmazása (csak a Windows Insiderben)**: Az **Igen** lehetőség választásával létrehozhat egy sablont az eszközök elnevezéséhez az üzembe helyezés során. A nevek legfeljebb 15 karakterből állhatnak, és betűket, számokat és kötőjelet tartalmazhatnak. A nevek nem állhatnak csak számokból. Hardverspecifikus sorozatszám hozzáadásához használja a [%SERIAL% makrót](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp). Egy másik lehetőség a [%RAND:x% makró](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) használata, amellyel véletlenszerű számsort adhat hozzá. Az x a hozzáadni kívánt számjegyek számát jelenti. 

6. Válassza a **Létrehozás** lehetőséget a profil létrehozásához. Az AutoPilot üzembehelyezési profil most már hozzárendelhető az eszközökhöz.

*A **Nyelv (Régió)** és a **Billentyűzet automatikus konfigurálása** is csak akkor érhető el, ha a **Telepítési mód** beállításnál az **Öntelepítő (előzetes verzió)** lehetőséget választja (ehhez a [Windows 10 Insider Preview buildje](https://docs.microsoft.com/windows-insider/at-work-pro/) szükséges).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>AutoPilot üzembehelyezési profil hozzárendelése eszközcsoporthoz

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Telepítési profilok** elemet, majd válasszon egy profilt.
2. A megadott profil paneljén válassza a **Hozzárendelések** elemet. 
3. Válassza a **Csoportok kijelölése** lehetőséget, majd a **Csoportok kijelölése** panelen jelölje ki a csoport(ok)at, amelyekhez a profilt hozzá kívánja rendelni, végül válassza a **Kijelölés** lehetőséget.

## <a name="edit-an-autopilot-deployment-profile"></a>AutoPilot üzembehelyezési profil szerkesztése
Az AutoPilot üzembehelyezési profil létrehozása után módosíthatja az üzembehelyezési profil egyes részeit.   

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** elemet.
2. A **Windows-regisztráció** terület **Windows AutoPilot** szakaszában válassza az **Üzembehelyezési profilok** lehetőséget.
3. Válassza ki a szerkeszteni kívánt profilt.
4. A telepítési profil nevének vagy leírásának módosításához kattintson a bal oldali **Tulajdonságok** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.
5. A Kezdőélmény beállításainak módosításához kattintson a **Beállítások** elemre. A módosítások elvégzését követően kattintson a **Mentés** gombra.

> [!NOTE]
> A profil módosításai alkalmazva lesznek a profilhoz társított eszközökön. Azonban a frissített profilt az Intune-ban korábban már regisztrált eszközökre csak azok alaphelyzetbe állítása és megújítása után alkalmazza a rendszer.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>A Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztások <!-- 163236 -->  

A riasztások jelzik, hogy az AutoPilot programban hány eszközhöz nincs hozzárendelve AutoPilot üzembehelyezési profil. A riasztás adatai alapján a profilok létrehozhatók és a hozzárendelés nélküli eszközökhöz rendelhetők. A riasztásra kattintva megjelenik a Windows AutoPilot-eszközök részletes adatokat is tartalmazó, teljes listája.


A nem társított eszközökre vonatkozó riasztások megtekintéséhez az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Áttekintés** > **Nem társított eszközök** lehetőséget.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Felhasználó hozzárendelése egy adott Autopilot-eszközhöz

Felhasználót rendelhet hozzá egy adott Autopilot-eszközhöz. Ez a hozzárendelés előre kitölti a [vállalati védjeggyel ellátott](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) bejelentkezési oldal felhasználói űrlapját az Azure Active Directoryból származó adatokkal a Windows beállítása során. Egyéni üdvözlési megnevezés beállítását is lehetővé teszi. A windowsos bejelentkezési adatokat nem tölti ki előre és nem is módosítja. Ilyen módon csak licenccel rendelkező Intune-felhasználók rendelhetők hozzá.

Előfeltételek: A már konfigurált Azure Active Directory Céges portál és a [Windows 10 Insider Preview legújabb buildje](https://docs.microsoft.com/windows-insider/at-work-pro/).

1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközregisztráció** > **Windows-regisztráció** > **Eszközök** > eszköz kijelölése > **Felhasználó hozzárendelése** lehetőséget.

    ![Képernyőkép a felhasználó hozzárendeléséről](media/enrollment-autopilot/assign-user.png)

2. Jelöljön ki egy Intune-licenccel rendelkező Azure-felhasználót, és válassza a **Kiválasztás** lehetőséget.

    ![Képernyőkép a felhasználó kiválasztásáról](media/enrollment-autopilot/select-user.png)

3. A **Rövid felhasználónév** mezőbe gépeljen be egy rövid nevet, vagy fogadja el az alapértelmezettet. Ez a rövid név jelenik meg, amikor a felhasználó bejelentkezik a Windows telepítése során.

    ![A rövid felhasználónév képernyőképe](media/enrollment-autopilot/friendly-name.png)

4. Válassza az **OK** gombot.


## <a name="delete-autopilot-devices"></a>AutoPilot-eszközök törlése

A nem regisztrált Windows AutoPilot-eszközök törölhetők.

1. Ha az eszközök regisztrálva vannak az Intune-ban, akkor először [törölnie kell azokat az Azure Active Directory portálról](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök** lehetőséget.

3. A **Windows AutoPilot-eszközök** területen jelölje ki a törölni kívánt eszközöket, majd válassza a **Törlés** elemet.

4. Hagyja jóvá a törlést az **Igen** választásával. A törlés eltarthat néhány percig.

## <a name="using-autopilot-in-other-portals"></a>Az AutoPilot használata más portálokon
Ha nem kíván a mobileszközök felügyeletével foglalkozni, más portálokon is használhatja az AutoPilotot. Más portálok is használhatók, de javasoljuk, hogy az Intune-t csak AutoPilottal végzett üzembe helyezések felügyeletéhez használja. Az Intune más portálokkal való használatakor az Intune nem tudja végrehajtani a következőket:  

- Megjeleníteni az Intune-ban létrehozott, de egy másik portálon szerkesztett profilok módosításait
- Szinkronizálni egy másik portálon létrehozott profilokat
- Megjeleníteni a profil-hozzárendelések más portálon végzett módosításait
- Szinkronizálni a más portálon végzett profil-hozzárendeléseket
- Megjeleníteni az eszközlista más portálon végzett módosításait

## <a name="windows-autopilot-for-existing-devices"></a>Windows Autopilot meglévő eszközökhöz

Ha a Configuration Manager [meglévő eszközökhöz használható AutoPilot szolgáltatásával](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) regisztrál, egy korrelátorazonosítóval csoportosíthatja a Windows-eszközöket. A korrelátorazonosító az AutoPilot konfigurációs fájljának egyik paramétere. Az [enrollmentProfileName Azure AD-beli eszközattribútum](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) beállítása automatikusan az ezzel megegyező „OfflineAutopilotprofile-\<korrelátorazonosítóra\>” módosul. Így tetszőleges dinamikus Azure AD-csoportok hozhatók létre korrelátorazonosító alapján az enrollmentprofileName attribútum használatával.

>[!WARNING] 
> Mivel a korrelátorazonosító nincs előzetesen megadva az Intune-on, az eszköz tetszés szerint jelenthet be bármilyen korrelátorazonosítót. Ha a felhasználó által létrehozott korrelátorazonosító egyezik egy AutoPilot- vagy Apple DEP-profil nevével, az eszköz hozzá lesz adva az enrollmentProfileName attribútumon alapuló összes dinamikus Azure AD-eszközcsoporthoz. Az ütközés elkerüléséhez:
> - A dinamikus csoportokra vonatkozó szabályokat mindig a *teljes* enrollmentProfileName érték használatával hozza létre.
> - Az Autopilot- és Apple DEP-profilok nevét soha ne kezdje az OfflineAutopilotprofile- előtaggal.

## <a name="next-steps"></a>További lépések
Miután konfigurálta a Windows AutoPilotot a regisztrált Windows 10-eszközökhöz, sajátítsa el, hogyan felügyelheti az eszközöket. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](https://docs.microsoft.com/intune/device-management) című témakörben talál.

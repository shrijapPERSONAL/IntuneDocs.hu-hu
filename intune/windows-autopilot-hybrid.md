---
title: Az Active Directory hibrid regisztrációs csatlakoztatott Windows Autopilot-eszközök –
titleSuffix: ''
description: Használat Windows Autopilot regisztrálni az Active Directory hibrid csatlakoztatott eszközök Microsoft Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 171e994be67a24e351b242967c8af934272da356
ms.sourcegitcommit: 17f58d35a6bdff3e179662f3731fc74d39144470
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2019
ms.locfileid: "55105170"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Hibrid Azure AD-hez csatlakoztatott eszközök üzembe helyezése az Intune és a Windows Autopilot használatával (előzetes verzió)
Az Intune és a Windows Autopilot használatával elvégezheti a hibrid Azure Active Directoryhoz csatlakoztatott eszközök beállítását. Ehhez kövesse az alábbi lépéseket:

## <a name="prerequisites"></a>Előfeltételek

- Sikeresen konfigurálta a [hibrid Azure Active Directoryhoz csatlakoztatott eszközöket](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).
    - Ügyeljen rá, hogy [a regisztráció ellenőrzése a Get-MsolDevice parancsmag használatával]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) megtörténjen.

A regisztrálni kívánt eszközöknek a következő feltételeknek kell megfelelniük:
- Windows 10-es operációs rendszert kell futtatniuk, amelyen telepítve van a [2018 októberi frissítés](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
- Rendelkezniük kell internet-hozzáféréssel.
- Hozzáféréssel kell rendelkezniük az Active Directoryhoz (a VPN-kapcsolat nem támogatott).
- Konfigurálták őket a Kezdőélmény (OOBE) használatával.

## <a name="set-up-windows-10-automatic-enrollment"></a>Windows 10-es eszközök automatikus regisztrációjának beállítása

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com), majd válassza az **Azure Active Directory** elemet.

   ![Az Azure Portal képernyőképe](./media/auto-enroll-azure-main.png)

2. Válassza a **Mobilitás (MDM és MAM)** elemet.

   ![Az Azure Portal képernyőképe](./media/auto-enroll-mdm.png)

3. Válassza a **Microsoft Intune** elemet.

   ![Az Azure Portal képernyőképe](./media/auto-enroll-intune.png)

4. Ügyeljen arra, hogy azok a felhasználók, akik az Intune és a Windows használatával helyeznek üzembe Azure Active Directoryhoz csatlakoztatott készülékeket, egy olyan csoportba tartozzanak, amelyre kiterjed az **MDM-felhasználói hatókör**.

   ![Az Azure Portal képernyőképe](./media/auto-enroll-scope.png)

5. A következő URL-címekhez használja az alapértelmezett értékeket:
    - **MDM használati feltételeinek URL-címe**
    - **MDM-felderítési URL-cím**
    - **MDM megfelelőségi URL-címe**
6. Válassza a **Mentés** elemet.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>A számítógépfiókok maximális számának növelése a Szervezeti egység területen

Az Active Directoryhoz készült Intune-összekötő Autopilot-regisztrációt végző számítógépeket hoz létre a Helyszíni Active Directory-tartományban. Ehhez az Intune-összekötőt üzemeltető számítógépnek jogosultsággal kell rendelkeznie a számítógép-objektumok létrehozásához a tartományban. 

Bizonyos tartományoknál előfordulhat, hogy a számítógépek nem jogosultak arra, hogy más számítógépeket hozzanak létre. Tartományok továbbá rendelkezik egy beépített korlátja (alapértelmezés szerint 10), amely érvényes az összes felhasználók és számítógépek, amelyek nem a számítógép-objektumok létrehozása delegált jogosultságokkal. Ezért a szervezeti egységre, ahol hibrid Azure AD-csatlakoztatott eszközök az Intune-összekötő üzemeltető számítógépeken delegálható rights kell jönnek létre.

Annak a szervezeti egységnek, amelyre a jogosultságok átruházva lesznek, meg kell egyeznie:
- a tartományhoz való csatlakozási profilban megadott szervezeti egységgel
- illetve, ha nincs kiválasztott profil, akkor a számítógép adott tartományban érvényes tartománynevével.

1. Nyissa meg az **Active Directory – felhasználók és számítógépek** szolgáltatást (DSA.msc).

2. Kattintson a jobb gombbal arra a szervezeti egységre, amelyet a hibrid Azure AD-hez csatlakoztatott eszközök létrehozásához használni kíván > **Vezérlés delegálása**.

    ![Képernyőkép a Vezérlés delegálása képernyőről](media/windows-autopilot-hybrid/delegate-control.png)

3. A **Vezérlés delegálása** varázslóban válassza a **Tovább** > **Hozzáadás...** > **Objektumtípusok** lehetőséget.

4. Az **Objektumtípusok** párbeszédpanelen jelölje be a **Számítógépek** jelölőnégyzetet, majd válassza az **OK** lehetőséget.

    ![Képernyőkép a Vezérlés delegálása képernyőről](media/windows-autopilot-hybrid/object-types-computers.png)

5. A **Felhasználók, számítógépek vagy csoportok kiválasztása** párbeszédpanelen az **Írja be a kijelölendő objektumok nevét** mezőben adja meg annak a számítógépnek a nevét, amelyen az összekötő telepítve van.

    ![Képernyőkép a Vezérlés delegálása képernyőről](media/windows-autopilot-hybrid/enter-object-names.png)

6. Az adatok ellenőrzéséhez válassza ki a **Névellenőrzés** lehetőséget, majd válassza az **OK** > **Tovább** lehetőségeket.

7. Válassza az **Egyéni feladat létrehozása delegálásra** > **Tovább** lehetőségeket.

8. Válassza ki a **Csak a mappa itt felsorolt objektumaira** lehetőséget, majd jelölje be a következőket:
    - **Számítógép-objektumok**
    - **A kijelölt objektumok létrehozása a mappában**
    - **A kijelölt objektumok törlése a mappából**

    ![Képernyőkép a Vezérlés delegálása képernyőről](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. Kattintson a **Tovább** gombra.

10. Az **Engedélyek** területen válassza a **Teljes jogosultság** (ezzel minden további beállítást bekapcsol) > **Következő** > **Befejezés** lehetőségeket.

    ![Képernyőkép a Vezérlés delegálása képernyőről](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>Az Intune-összekötő telepítése

Az Intune-összekötő az Active Directory kell lennie a Windows Server 2016 rendszert futtató számítógépre telepíthető (vagy újabb), amely hozzáfér az internethez, és az Active Directoryban. A méret és a rendelkezésre állás növelése érdekében, valamint egyszerre több Active Directory-tartomány támogatásához egyszerre több összekötőt is telepíthet környezetében. Javasoljuk, hogy az összekötőt egy olyan kiszolgálón telepítse, amelyet nem használ más Intune-összekötő futtatására.

1. Győződjön meg arról, hogy rendelkezik-e telepítve és konfigurálva, a nyelvi csomag [az Intune-összekötő (előzetes verzió) nyelvi követelmények](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. Az [Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Active Directoryhoz készült Intune-összekötő (előzetes verzió)** > **Összekötő hozzáadása** lehetőségeket. 
3. Kövesse az utasításokat az összekötő letöltéséhez.
4. Az összekötő telepítéséhez nyissa meg az összekötő letöltött telepítőfájlját (ODJConnectorBootstrapper.exe).
5. A telepítés végén válassza a **Konfigurálás** lehetőséget.
6. Válassza a **Bejelentkezés** lehetőséget.
7. Adja meg a globális rendszergazda szerepkör, vagy az Intune-rendszergazda szerepkör felhasználói hitelesítő adatait. A felhasználói fiókot az Intune-licenccel kell rendelkeznie.
8. Navigáljon az **Eszközregisztráció** > **Windows regisztráció** > **Active Directoryhoz készült Intune-összekötő (előzetes verzió)** területre, és győződjön meg róla, hogy a kapcsolat állapota **Aktív**.

 > [!NOTE]
 > Miután **bejelentkezés** az összekötőben is igénybe vehet néhány percet, amíg megjelennek [Intune](https://aka.ms/intuneportal). Ügyeljen arra, hogy az összekötő lesz egyetlen show Ha képes sikeresen kommunikálni az Intune szolgáltatással.

### <a name="configure-web-proxy-settings"></a>Webproxy-beállítások konfigurálása

Ha olyan webproxyt hálózati környezetében, kövesse az itt, hogy az Intune-összekötő az Active Directory megfelelően működik: [Munka a meglévő helyszíni proxykiszolgálók](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Eszközcsoport létrehozása
1. Az [Intune-ban](https://aka.ms/intuneportal) válassza a **Csoportok** > **Új csoport** elemet.
2. A **Csoport** panelen:
    1. A **Csoport típusa** beállításnál válassza a **Biztonsági** lehetőséget.
    2. Gépelje be a **Csoport nevét** és a **Csoport leírását**.
    3. Válasszon egyet a **Tagság típusa** lehetőségek közül.
3. Ha a **Tagság típusa** alatt a **Dinamikus eszköz** lehetőséget választotta, akkor válassza a **Csoport** panel **Dinamikus eszköz tagok** lehetőségét, és gépelje be az alábbi kódok bármelyikét a **Speciális szabály** mezőbe.
    - Ha létre kíván hozni egy csoportot, amely tartalmazza az összes AutoPilot-eszközét, írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Ha létre kíván hozni egy csoportot, amely az egy adott rendelésazonosítóval rendelkező összes Autopilot-eszközét tartalmazza, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Ha létre kíván hozni egy csoportot, amely az egy adott beszerzési rendelési azonosítóval rendelkező összes Autopilot-eszközét tartalmazza, írja be a következőt: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    A **Speciális szabály** kódjának megadása után válassza a **Mentés** lehetőséget.
5. Válassza a **Létrehozás** lehetőséget.  

## <a name="register-your-autopilot-devices"></a>Az Autopilot-eszközök regisztrálása

Az Autopilot-eszközök beléptetéséhez válassza ki a következő módszerek valamelyikét:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>A már beléptetett Autopilot-eszközök regisztrálása

1. Autopilot-üzembehelyezési profil létrehozása a **Minden megcélzott eszköz AutoPilot-eszközzé alakítása** beállítás **Igen** értékre állításával. 
2. Rendelje hozzá a profilt ahhoz a csoporthoz, amelynek tagjait az Autopilot használatával automatikusan regisztrálni kívánja.

További információért lásd: [AutoPilot-üzembehelyezési profil létrehozása](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>A nem beléptetett Autopilot-eszközök regisztrálása

Ha az eszközök még nincsenek beléptetve, regisztrációjukat saját kezűleg elvégezheti. További információkért lásd: [Eszközök hozzáadása](enrollment-autopilot.md#add-devices)

### <a name="register-devices-from-an-oem"></a>OEM-eszközök regisztrálása

Új eszközök vásárlásakor egyes számítógépgyártók (OEM) regisztrálhatják az eszközöket az Ön számára. További információkat a [Windows Autopilot oldala](http://aka.ms/WindowsAutopilot) tartalmaz.

A regisztráció során (de még azelőtt, hogy beléptetné őket az Intune-ba) három helyen tekintheti meg az Autopilot-eszközök listáját (sorszámokhoz rendelt névvel):
- Az Autopilot-eszközök panelen az Azure Portalbeli Intune-ban (**Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök**).
- Az Azure AD-eszközök panelen az Azure Portalbeli Intune-ban (**Eszközök** > **Azure AD-eszközök**).
- A Minden AAD-eszköz panelen az Azure Portalbeli Azure Active Directoryban (**Eszközök** > **Minden eszköz**).

A beléptetés után négy helyen tekintheti meg az Autopilot-eszközök listáját:
- Az Autopilot-eszközök panelen az Azure Portalbeli Intune-ban (**Eszközök regisztrálása** > **Windows-regisztráció** > **Eszközök**).
- Az Azure AD-eszközök panelen az Azure Portalbeli Intune-ban (**Eszközök** > **Azure AD-eszközök**).
- A Minden AAD-eszköz panelen az Azure Portalbeli Azure Active Directoryban (**Eszközök** > **Minden eszköz**).
- A Minden eszköz panelen az Azure Portalbeli Intune-ban (**Eszközök** > **Minden eszköz**).

Autopilot-eszközök beléptetése után nevük az eszköz állomásnevére módosul. A név alapértelmezés szerint a „DESKTOP-” előtaggal kezdődik.




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Autopilot-üzembehelyezési profil létrehozása és hozzárendelése
Az Autopilot-üzembehelyezési profilokkal Autopilot-eszközeit konfigurálhatja.

1. Az [Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** elemet.
2. Adjon meg egy **Nevet**, és igény esetén **Leírást**.
3. Az **Üzembehelyezési mód** beállításnál válassza a **Felhasználó által vezérelt** lehetőséget.
4. A **Csatlakozás az Azure AD-hez mint** mezőben válassza a **Hibrid Azure AD-hez csatlakoztatott (előzetes verzió)** lehetőséget.
5. Válassza a **Kezdőélmény (OOBE)** lehetőséget, igény szerint konfigurálja a beállításokat, majd válassza a **Mentés** lehetőséget.
6. Válassza a **Létrehozás** lehetőséget a profil létrehozásához. 
7. A profil paneljén válassza a **Hozzárendelések** elemet.
8. Válassza a **Csoportok kiválasztása** lehetőséget, majd a **Csoportok kiválasztása** panelen válassza ki az eszközcsoportot, végül pedig a **Kiválasztás** lehetőséget.

Körülbelül 15 percbe telik, amíg az eszközprofil állapota **Nincs hozzárendelve** állapotról **Hozzárendelés** állapotra, végül pedig **Hozzárendelve** állapotra vált.

## <a name="turn-on-the-enrollment-status-page-optional"></a>Kapcsolja be a Beléptetés állapota oldalt (nem kötelező)

1. Az [Intune](https://aka.ms/intuneportal) portálon válassza az **Eszközök beléptetése** > **Windows-alapú regisztráció** > **Beléptetés állapota oldal (előzetes verzió)** lehetőséget.
2. A **Beléptetés állapota oldal** panelen válassza az **Alapértelmezett** > **Beállítások** lehetőséget.
3. A **Show app and profile installation progress** (Alkalmazások és profilok telepítési állapotának megjelenítése) beállításnál válassza a **Yes** (Igen) lehetőséget.
4. Igény szerint konfigurálja a többi beállítást.
5. Válassza a **Mentés** elemet.

## <a name="create-and-assign-a-domain-join-profile"></a>Tartomány-csatlakoztatási profil létrehozása és hozzárendelése

1. Az [Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
2. Adja meg a következő tulajdonságokat:
   - **Név**: Adja meg az új profil leíró nevét.
   - **Description** (Leírás): Adja meg a profil leírását.
   - **Platform**: Válasszon **Windows 10 és újabb**.
   - **Profil típusa**: Válasszon **tartományhoz való csatlakozás (előzetes verzió)**.
3. Válasszon **beállítások** , és adja meg egy **számítógépnév előtagja**, **tartománynév**, és (nem kötelező) **szervezeti egység** a[DN formátum](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
4. Válassza az **OK** > **Létrehozás** lehetőségeket. Ekkor létrejön a profil, és megjelenik a listában.
5. A profil hozzárendeléséhez kövesse az [Eszközprofil hozzárendelése](device-profile-assign.md#assign-a-device-profile) cikk lépéseit. 

## <a name="next-steps"></a>További lépések

Miután konfigurálta a Windows Autopilotot, ideje elsajátítani, hogyan felügyelheti az eszközöket. További információt [A Microsoft Intune-eszközfelügyelet ismertetése](device-management.md) című témakörben talál.

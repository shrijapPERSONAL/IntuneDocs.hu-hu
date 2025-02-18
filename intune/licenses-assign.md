---
title: Microsoft Intune-licencek hozzárendelése
description: Intune-licencek hozzárendelése a felhasználókhoz, hogy regisztrálhassák az eszközöket
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 14d5e01577100e0a66cfcf6ce935289a1dc26fab
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57459900"
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Intune-licencek hozzárendelése a felhasználókhoz, hogy regisztrálhassák az eszközöket

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Akár manuálisan adja hozzá a felhasználókat, akár a helyszíni Active Directoryból szinkronizál, először Intune-licencet kell hozzárendelnie minden felhasználóhoz, hogy a felhasználók regisztrálhassák eszközeiket az Intune-ban. A licencek listáját az [Intune-t tartalmazó licencek](licenses.md) című témakörben találja.

## <a name="assign-an-intune-license-in-the-microsoft-365-admin-center"></a>Rendeljen Intune-licencet, a Microsoft 365 felügyeleti központban

Használhatja a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) manuálisan adja hozzá a felhőalapú felhasználók és licencek hozzárendelése a felhőalapú felhasználói fiókokhoz és a helyszíni Active Directoryból az Azure AD-be szinkronizált fiókokhoz is.

1. Jelentkezzen be a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) bérlői rendszergazdai hitelesítő adataival, és válassza a **felhasználók** > **aktív felhasználók**.

2. Válassza ki a felhasználói fiókot az Intune felhasználói licencek hozzárendelésére, és válassza a **Terméklicencek** > **Szerkesztés** lehetőséget.

3. Kapcsolja az **Intune** vagy az **Enterprise Mobility + Security** beállítást **Be**, és válassza a **Mentés** lehetőséget.

   ![Képernyőkép a Microsoft 365 felügyeleti központban termék szakasz licenceket.](./media/office-assign-license.png)

4. A felhasználói fiókot most már rendelkezik a szolgáltatás használatához és az eszközöknek a felügyelet alá való regisztrálásához szükséges engedélyekkel.

> [!NOTE]
> Miután regisztrálnak egy eszközt, a felhasználók már megjelennek a felügyeleti konzolon. Emellett kiválaszthat egy felhasználói csoportot az egyszerre való szerkesztéshez, vagy hozzáadva, vagy lecserélve az összes kijelölt felhasználó licencét.

## <a name="assign-an-intune-license-by-using-azure-active-directory"></a>Intune-licent hozzárendelése az Azure Active Directoryval

Az Azure Active Directory segítségével is hozzárendelhet Intune-licenceket a felhasználókhoz. További információ: [Felhasználók licencelése az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal). 

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>A School Data Sync használata licencek kiosztására a felhasználók számára az Intune for Educationben
Az oktatási szervezetek a School Data Sync (SDS) segítségével Intune for Education-licenceket oszthatnak ki a szinkronizált felhasználóknak. Az SDS-profil beállítása esetén jelölje be az Intune for Education jelölőnégyzetet.  

![Képernyőkép az SDS-profil beállításáról](./media/i4e-sds-profile-setup-setting.png)

Az Intune for Education-licencek kiosztásakor ellenőrizze, hogy az Intune A Direct-licenc is ki van-e osztva.

![Képernyőkép a terméklicenc beállításáról](./media/i4e-set-licenses.png)

További tudnivalók az SDS-ről: [A School Data Sync áttekintése](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>A felhasználói és eszközlicencek hatása a szolgáltatásokhoz való hozzáférésre
* Azok a **felhasználók**, akiknek felhasználói licencet oszt ki, elérhetik és használhatják az online szolgáltatásokat és a kapcsolódó szoftvereket (köztük a System Centert) az alkalmazások és legfeljebb 15 eszköz felügyelete céljából.
* Bármely eszközhöz vásárolhat a felhasználói licencektől különálló licenceket. Az eszközlicenceket nem szükséges hozzárendelni az eszközökhöz. Minden, az online szolgáltatásokhoz és a kapcsolódó szoftverekhez (köztük a System Centerhez) hozzáférő és azokat használó eszköznek rendelkeznie kell egy eszközlicenccel.
* Ha egy eszköz több felhasználó is használ, akkor mindegyiknek eszközlicencre, vagy minden felhasználónak felhasználói licencre van szüksége.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>A megvásárolt licencek típusainak ismertetése

Az Intune vásárlási módja határozza meg az előfizetési adatokat:

- Ha Nagyvállalati Szerződés keretében vásárolta meg az Intune-t, az előfizetési adatait a Mennyiségi licenc portál **Előfizetések** területén tekintheti meg.
- Ha az Intune-t egy felhőszolgáltatótól vásárolta meg, keresse fel a viszonteladót.
- Ha az Intune-t a CC# vagy az Invoice szolgáltatáson keresztül vásárolta, a licencek felhasználóalapúak.




## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Az EMS felhasználói licencek szelektív kezelése a PowerShell segítségével
Előfordulhat, hogy a Microsoft Enterprise Mobility + Security (korábban: Nagyvállalati mobilitási csomag) megoldást használó szervezeteknek vannak olyan felhasználói, akiknek csak az EMS csomagban foglalt Azure Active Directory Premium vagy Intune szolgáltatásra van szükségük. Az [Azure Active Directory PowerShell-parancsmagok](https://msdn.microsoft.com/library/jj151815.aspx) használatával egy-egy szolgáltatás vagy a szolgáltatások egy részhalmaza is hozzárendelhető.

A felhasználói licencek EMS-szolgáltatásokhoz való szelektív hozzárendeléséhez nyissa meg a PowerShellt rendszergazdaként egy olyan számítógépen, amelyre telepítve van a [Windows PowerShellhez készült Microsoft Azure Active Directory-modul ](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) megoldással rendelkező számítógépen. A PowerShell helyi számítógépre vagy ADFS-kiszolgálóra telepíthető.

Létre kell hoznia egy új licenctermékváltozat-definíciót, amely csak a szükséges szolgáltatáscsomagokra vonatkozik. Ehhez tiltsa le az alkalmazni nem kívánt csomagokat. Például létrehozhat olyan licenctermékváltozat-definíciót, amely nem rendel hozzá Intune-licencet. Az elérhető szolgáltatások listájának megtekintéséhez írja be:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Az Intune szolgáltatáscsomag kizárásához a következő parancsot futtathatja. Ugyanezzel a módszerrel kibonthat egy teljes biztonsági csoportot, vagy még részletesebb szűrőket is használhat.

**1. példa**<br>
Új felhasználó létrehozása a parancssorból, és EMS-licenc hozzárendelése a licenc Intune-részének engedélyezése nélkül:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Ellenőrizze a következővel:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**2. példa**<br>
A hozzárendelt licenccel már rendelkező felhasználó EMS-licencéből az Intune-rész letiltása:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Ellenőrizze a következővel:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

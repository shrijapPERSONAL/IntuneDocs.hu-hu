---
# required metadata

title: Intune-licencek kezelése | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune licencek kezelése
A felhasználóknak a bejelentkezéshez és az Intune szolgáltatás használatához rendelkezniük kell egy licenccel, amely lehetővé teszi a szolgáltatás használatát vagy az eszközeik felügyeletre történő regisztrálását. A licenccel rendelkező felhasználók tagjai a [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] felhasználói csoportnak. Ez a csoport az összes olyan felhasználót tartalmazza, aki jogosult az előfizetés használatára. **Minden felhasználói licenc legfeljebb 5 eszköz regisztrálását teszi lehetővé.**.

## Az Intune-licencek hozzárendelésének módja
Ha a felhasználói fiókok szinkronizálása a helyszíni Active Directoryból történik, vagy a fiókportál segítségével manuálisan veszik fel őket felhőalapú szolgáltatások előfizetésébe, akkor a rendszer nem rendel hozzájuk Intune-licencet automatikusan. Ehelyett egy későbbi időpontban egy Intune bérlői rendszergazdának a fiókportálról kell egy licencet a felhasználóhoz hozzárendelnie a felhasználói fiók szerkesztésével.

Ha az előfizetése a hozzá társított más felhőalapú szolgáltatásokkal közösen használja az Azure AD-t, Ön hozzáférhet az ezekbe a szolgáltatásokba felvett felhasználókhoz. Ezek a felhasználók mindaddig nem jogosultak a [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] használatára, amíg hozzájuk nem rendel egy licencet.

> [!TIP]
> Ha az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] használatára jogosító licenc hozzárendelésére vagy visszavonására szolgáló beállítás nem érhető el, előfordulhat, hogy az előfizetés olyan mennyiségi licencelési lehetőségeket tartalmaz, mint amilyenek például a [Nagyvállalati mobilitási csomag](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) használatakor érhetők el. A licencek hozzárendeléséről vagy visszavonásáról a licencelési lehetőségek dokumentációjában tájékozódhat.

## Intune felhasználói licenc hozzárendelése

A(z) **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** használatával a felhőalapú felhasználók és licencek manuálisan hozzáadhatók, illetve hozzárendelhetők a felhőalapú felhasználói fiókokhoz és a helyszíni Active Directoryból az Azure AD-be szinkronizált fiókokhoz is.

1.  Jelentkezzen be az Intune fiókportálon a bérlői rendszergazdai hitelesítő adatokkal.

2.  Válassza ki azt a felhasználói fiókot, amelyhez Intune felhasználói licencet kíván hozzárendelni, és a felhasználói fiók tulajdonságainál jelölje be a **Microsoft Intune** jelölőnégyzetet.

3.  A felhasználói fiók ezzel bekerül a Microsoft Intune felhasználói csoportba, amely engedélyt ad a felhasználónak a szolgáltatás használatára és eszközeinek felügyeletre való regisztrálására.

### Az EMS felhasználói licencek szelektív kezelése a PowerShell segítségével
Előfordulhat, hogy a Microsoft Nagyvállalati mobilitási csomag (EMS) megoldást használó szervezeteknek vannak felhasználói, akik csak az EMS csomagban foglalt Azure Active Directory Premium vagy Intune szolgáltatást igénylik. Az [Azure Active Directory PowerShell-parancsmagok](https://msdn.microsoft.com/library/jj151815.aspx) használatával egy-egy szolgáltatás vagy a szolgáltatások egy részhalmaza is hozzárendelhető. 

A felhasználói licencek EMS-szolgáltatásokhoz való szelektív hozzárendeléséhez nyissa meg a PowerShellt rendszergazdaként egy olyan számítógépen, amelyre telepítve van a [Windows PowerShellhez készült Microsoft Azure Active Directory-modul ](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) megoldással rendelkező számítógépen. A PowerShell helyi számítógépre vagy ADFS-kiszolgálóra telepíthető.

Létre kell hoznia egy új licenctermékváltozat-definíciót, amely csak a szükséges szolgáltatáscsomagokra vonatkozik. Ehhez tiltsa le az alkalmazni nem kívánt csomagokat. Például létrehozhat olyan licenctermékváltozat-definíciót, amely nem rendel hozzá Intune-licencet. Az elérhető szolgáltatások listájának megtekintéséhez írja be:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Az Intune szolgáltatáscsomag kizárásához a következő parancsot futtathatja. Ugyanezzel a módszerrel kibonthat egy teljes biztonsági csoportot, vagy még részletesebb szűrőket is használhat. 

**1. példa**
Új felhasználó létrehozása a parancssorból, és EMS-licenc hozzárendelése a licenc Intune-részének engedélyezése nélkül:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Ellenőrizze a következővel:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**2. példa**
A hozzárendelt licenccel már rendelkező felhasználó EMS-licencéből az Intune-rész letiltása:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Ellenőrizze a következővel:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### További lépések
Gratulálunk! Ezzel befejezte az *Intune – Első lépések útmutató* 4. lépését..
>[!div class="step-by-step"]

>[&larr; **Felhasználók szinkronizálása az Intune-nal**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Felhasználók és eszközök rendszerezése** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->



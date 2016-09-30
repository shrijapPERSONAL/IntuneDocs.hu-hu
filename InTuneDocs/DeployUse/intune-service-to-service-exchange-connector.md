---
title: "Exchange-összekötő Exchange Online-hoz | Microsoft Intune"
description: "Csatlakoztathatja az Intune-t az Office 365 Exchange szolgáltatáshoz az Exchange ActiveSync-alapú mobileszköz-felügyelet (MDM) támogatása érdekében."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Intune szolgáltatások közötti összekötő konfigurálása az Exchange Online-hoz

Az alábbi információk segítségével a Microsoft Intune-t az Exchange Online-hoz vagy az új dedikált Exchange Online szolgáltatáshoz csatlakoztathatja. Annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **örökölt**, lépjen kapcsolatba a fiókkezelővel. Típustól függetlenül az Intune előfizetésenként csak egy Exchange-összekötő kapcsolatot támogat.

## A Service to Service Connector alkalmazásra vonatkozó követelmények
A **Service to Service Connector** csak az Exchange Online-t és az új dedikált Exchange Online-t támogatja, és nincsenek a helyszíni infrastruktúrára vonatkozó követelményei.

|Követelmény|További információ|
|---------------|--------------------|
|Konfigurált és működő Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobileszköz-kezelő szolgáltató| [A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Microsoft Exchange verzió|Exchange Online vagy új dedikált Exchange Online szolgáltatás|
|Active Directory-szinkronizálás|Mielőtt bármely összekötővel csatlakoztatná az Intune Connectort az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure AD-példányával.|

### Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Exchange Online-felhasználói fiókot is, amelyet az Intune Exchange-összekötő fog használni. A fióknak engedéllyel kell rendelkeznie az Intune felügyeleti konzol használatához, illetve a Windows PowerShell Exchange-parancsmagok futtatásához.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## A szolgáltatások közötti összekötő beállítása

1. Nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com) a [fenti](#exchange-cmdlet-requirements) parancsmagokhoz Exchange-rendszergazdai jogosultságokkal és engedélyekkel rendelkező felhasználói fiókkal. A Microsoft Intune az aktuálisan bejelentkezett felhasználó e-mail címét használja a kapcsolat beállításához.

2.  A munkaterület parancsikon-ablaktábláján válassza a **FELÜGYELET** lehetőséget, majd lépjen a **Mobileszköz-kezelés** > **Microsoft Exchange** > **Exchange-kapcsolat beállítása** pontra.
![A Service To Service Connector telepítése oldal](../media/intunesa5cservicetoserviceconnector.png)

3.  Az **Exchange-kapcsolat beállítása** lapon kattintson a **Service To Service Connector telepítése** parancsra.


A Service-to-Service Connector konfigurációja és szinkronizálása az Exchange Online- vagy új dedikált Exchange Online-környezettel automatikusan megtörténik.

## Az Exchange-kapcsolat ellenőrzése

Miután sikeresen konfigurálta az Exchange-összekötőt, a [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) válassza a **Felügyelet** munkaterületet, majd a **Mobileszköz-kezelés** > ** területen válassza a Microsoft Exchange** elemet, és ellenőrizze, hogy a megadott adatok megjelennek-e **Az Exchange-kapcsolat információi** területen.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.



<!--HONumber=Sep16_HO4-->



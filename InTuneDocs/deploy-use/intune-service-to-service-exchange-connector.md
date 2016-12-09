---
title: "Exchange-összekötő Exchange Online-hoz | Microsoft Intune"
description: "Csatlakoztathatja az Intune-t az Office 365 Exchange szolgáltatáshoz az Exchange ActiveSync-alapú mobileszköz-felügyelet (MDM) támogatása érdekében."
keywords: 
author: staciebarker
ms.author: stabar
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
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: b6d67391b50954e591817610164d8fe80fda8fd5


---

# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Intune szolgáltatások közötti összekötő konfigurálása az Exchange Online-hoz

Az alábbi információk segítségével a Microsoft Intune-t az Exchange Online-hoz vagy az új dedikált Exchange Online szolgáltatáshoz csatlakoztathatja. Annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **örökölt** verzió, lépjen kapcsolatba a fiókkezelővel. Típustól függetlenül az Intune előfizetésenként csak egy Exchange-összekötő kapcsolatot támogat.

## <a name="service-to-service-connector-requirements"></a>A Service to Service Connector használatára vonatkozó követelmények
A **Service to Service Connector** csak az Exchange Online-t és a dedikált Exchange Online-t támogatja, és nincsenek a helyszíni infrastruktúrára vonatkozó követelményei.

|Követelmény|További információ|
|---------------|--------------------|
|Konfigurált és működő Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobileszköz-kezelő szolgáltató| [A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Microsoft Exchange verzió|Exchange Online vagy új dedikált Exchange Online szolgáltatás|
|Active Directory-szinkronizálás|Mielőtt bármely összekötővel csatlakoztatná az Intune Connectort az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure AD-példányával.|

### <a name="exchange-cmdlet-requirements"></a>Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Exchange Online-felhasználói fiókot is, amelyet az Intune Exchange-összekötő fog használni. A fióknak engedéllyel kell rendelkeznie az Intune felügyeleti konzol használatához, illetve az alábbi Windows PowerShell Exchange-parancsmagok futtatásához:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>A szolgáltatások közötti összekötő beállítása

1. Nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com) a [korábban megadott](#exchange-cmdlet-requirements) parancsmagokhoz Exchange-rendszergazdai jogosultságokkal és engedélyekkel rendelkező felhasználói fiókkal. A Microsoft Intune az aktuálisan bejelentkezett felhasználó e-mail címét használja a kapcsolat beállításához.

2.  A munkaterület parancsikon ablaktábláján válassza a **FELÜGYELET**>** lehetőséget, majd lépjen a Mobileszköz-kezelés** > **Microsoft Exchange** > **Exchange-kapcsolat beállítása** pontra.
![A Service To Service Connector telepítése oldal](../media/intunesa5cservicetoserviceconnector.png)

3.  Az **Exchange-kapcsolat beállítása** lapon kattintson a **Service To Service Connector telepítése** parancsra.


A Service-to-Service Connector konfigurációja és szinkronizálása az Exchange Online- vagy új dedikált Exchange Online-környezettel automatikusan megtörténik.

## <a name="validate-your-exchange-connection"></a>Az Exchange-kapcsolat ellenőrzése

Amint sikeresen konfigurálta az Exchange Connectort, látogasson el a [Microsoft Intune felügyeleti konzol](http://manage.microsoft.com) lapra. Válassza a **Rendszergazda**> **Mobileszköz-kezelés** > **Microsoft Exchange** elemet. Majd ellenőrizze, hogy a megadott adatok láthatók-e az **Exchange-kapcsolat információi** között.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.



<!--HONumber=Dec16_HO2-->



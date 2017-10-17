---
title: "Exchange-összekötő az Exchange Online-hoz"
description: "Csatlakoztathatja az Intune-t az Office 365 Exchange szolgáltatáshoz az Exchange ActiveSync-alapú mobileszköz-felügyelet (MDM) támogatása érdekében."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b475e4b1e82feb7449bd0c591f70e806d5b8c9a4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Intune szolgáltatások közötti összekötő konfigurálása az Exchange Online-hoz

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az alábbi információk segítségével a Microsoft Intune-t az Exchange Online-hoz vagy az új dedikált Exchange Online szolgáltatáshoz csatlakoztathatja. Annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **örökölt** verzió, lépjen kapcsolatba a fiókkezelővel. Típustól függetlenül az Intune előfizetésenként csak egy Exchange-összekötő kapcsolatot támogat.

## <a name="service-to-service-connector-requirements"></a>A Service to Service Connector használatára vonatkozó követelmények
A **Service to Service Connector** csak az Exchange Online-t és a dedikált Exchange Online-t támogatja, és nincsenek a helyszíni infrastruktúrára vonatkozó követelményei.

|Követelmény|További információ|
|---------------|--------------------|
|Konfigurált és működő Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobileszköz-kezelő szolgáltató| [A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Microsoft Exchange verzió|Exchange Online vagy új dedikált Exchange Online szolgáltatás|/intune/users-permissions-add
|Active Directory-szinkronizálás|Mielőtt bármely összekötővel csatlakoztatná az Intune Connectort az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](/intune/users-permissions-add), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure AD-példányával.|

### <a name="exchange-cmdlet-requirements"></a>Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Exchange Online-felhasználói fiókot is, amelyet az Intune Exchange-összekötő fog használni. A fióknak engedéllyel kell rendelkeznie az Intune felügyeleti konzol használatához, illetve az alábbi Windows PowerShell Exchange-parancsmagok futtatásához:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>A szolgáltatások közötti összekötő beállítása

1. Nyissa meg a [Microsoft Intune felügyeleti konzolt](https://manage.microsoft.com) a [korábban megadott](#exchange-cmdlet-requirements) parancsmagokhoz Exchange-rendszergazdai jogosultságokkal és engedélyekkel rendelkező felhasználói fiókkal. A Microsoft Intune az aktuálisan bejelentkezett felhasználó e-mail címét használja a kapcsolat beállításához.

2.  A munkaterület parancsikon ablaktábláján válassza a **FELÜGYELET**> **lehetőséget, majd lépjen a Mobileszköz-kezelés** > **Microsoft Exchange** > **Exchange-kapcsolat beállítása** pontra.
![A Service To Service Connector telepítése oldal](../media/intunesa5cservicetoserviceconnector.png)

3.  Az **Exchange-kapcsolat beállítása** lapon kattintson a **Service To Service Connector telepítése** parancsra.


A Service-to-Service Connector konfigurációja és szinkronizálása az Exchange Online- vagy új dedikált Exchange Online-környezettel automatikusan megtörténik.

## <a name="validate-your-exchange-connection"></a>Az Exchange-kapcsolat ellenőrzése

Amint sikeresen konfigurálta az Exchange Connectort, látogasson el a [Microsoft Intune felügyeleti konzol](https://manage.microsoft.com) lapra. Válassza a **Rendszergazda**> **Mobileszköz-kezelés** > **Microsoft Exchange** elemet. Majd ellenőrizze, hogy a megadott adatok láthatók-e az **Exchange-kapcsolat információi** között.

Ellenőrizheti a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

---
title: Intune Exchange-összekötő az Exchange Online-hoz
titleSuffix: ''
description: Csatlakoztathatja az Intune-t az Office 365 Exchange szolgáltatáshoz az Exchange ActiveSync-alapú mobileszköz-felügyelet (MDM) támogatása érdekében.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 640d1a5cbd785248cb309bc250c95631295955b3
ms.sourcegitcommit: 71497f0215fc8bed454ac318b0548b1281a8fe0f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/08/2018
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Az Exchange-összekötő konfigurálása az Intune-ban és az Exchange Online-ban

A cikk segítségével a Microsoft Intune-t az Exchange Online-hoz vagy az új dedikált Exchange Online szolgáltatáshoz csatlakoztathatja. Annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **örökölt** verzió, lépjen kapcsolatba a fiókkezelővel.

## <a name="service-to-service-connector-requirements"></a>A Service to Service Connector használatára vonatkozó követelmények
A **Service to Service Connector** csak az Exchange Online-t és a dedikált Exchange Online-t támogatja, és nincsenek a helyszíni infrastruktúrára vonatkozó követelményei.


|              Követelmény               |                                                                                                            További információ                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurált és működő Exchange Online |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Mobileszköz-kezelő szolgáltató   |                                                       [A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként](mdm-authority-set.md)                                                       |
|       Microsoft Exchange verzió       |                                                                                      Exchange Online vagy új dedikált Exchange Online szolgáltatás                                                                                      |
|    Active Directory-szinkronizálás    | Mielőtt bármely összekötővel csatlakoztatná az Intune Connectort az Exchange-kiszolgálóhoz, [állítsa be az Active Directory-szinkronizálást](/intune/users-add), hogy a helyi felhasználók és biztonsági csoportok szinkronizálva legyenek az Azure AD-példányával. |

### <a name="exchange-cmdlet-requirements"></a>Exchange-parancsmagokkal kapcsolatos követelmények

Létre kell hoznia egy Exchange Online-felhasználói fiókot is, amelyet az Intune Exchange-összekötő fog használni. A fióknak engedéllyel kell rendelkeznie az alábbi szükséges Windows PowerShell Exchange-parancsmagok futtatásához:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>A szolgáltatások közötti összekötő beállítása

1. Jelentkezzen be az [Azure Portalra](http://portal.azure.com) a [korábban ismertetett parancsmagokhoz](#exchange-cmdlet-requirements) Exchange-rendszergazdai jogosultságokkal és engedélyekkel rendelkező felhasználói fiókkal. A Microsoft Intune az aktuálisan bejelentkezett felhasználó e-mail címét használja a kapcsolat beállításához.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. A Microsoft Intune-irányítópult megnyitásához válassza az **Intune** lehetőséget. Válassza a **Feltételes hozzáférés** elemet, majd a **Beállítás** terület **Az Exchange szolgáltatási összekötője** lehetőségét.

4.  A **Feltételes hozzáférés – Az Exchange szolgáltatási összekötője** lapon válassza a **Service To Service Connector telepítése** lehetőséget. 
   
     ![Kép a Service To Service Connector telepítése hivatkozás kijelöléséről](media/exchange_service_connector.png)

A Service-to-Service Connector konfigurációja és szinkronizálása az Exchange Online- vagy új dedikált Exchange Online-környezettel automatikusan megtörténik.

## <a name="validate-your-exchange-connection"></a>Az Exchange-kapcsolat ellenőrzése

Az Exchange Service To Service Connector konfigurálása után ellenőrizze az Exchange Connector-kiszolgáló adatait a **Feltételes hozzáférés – Az Exchange szolgáltatási összekötője** lapon.

Itt a **kapcsolódási állapotot** és a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

## <a name="next-steps"></a>További lépések
[Az Exchange feltételes hozzáférésének figyelése a Microsoft Intune-ban](conditional-access-exchange-monitor.md)
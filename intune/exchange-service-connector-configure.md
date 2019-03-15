---
title: Az Intune Exchange Connectort az Exchange online-hoz |} A Microsoft Intune-ban
description: Csatlakoztathatja az Intune-t az Office 365 Exchange szolgáltatáshoz az Exchange ActiveSync-alapú mobileszköz-felügyelet (MDM) támogatása érdekében.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 828cd17c320bd13b1b7fcce6578727015be3a77b
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460444"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Az Exchange-összekötő konfigurálása az Intune-ban és az Exchange Online-ban
A cikk segítségével a Microsoft Intune-t az Exchange Online-hoz vagy az új dedikált Exchange Online szolgáltatáshoz csatlakoztathatja. Annak megállapításához, hogy a dedikált Exchange Online-környezet **új** vagy **örökölt** verzió, lépjen kapcsolatba a fiókkezelővel.

A **szolgáltatások közötti összekötő** használatával az Exchange ActiveSync (EAS) és az Intune által felügyelt eszközöket is egyetlen rendszergazdai konzolról felügyelheti.  Az összekötőben az Exchange Online feltételes hozzáférésének engedélyezése nem szükséges.

A feltételes hozzáférés egy bevezetésének megtervezésekor fontos gyakran mely felhasználók és felhasználói száma fog rendelkezni az új felhasználói felületre. A Microsoft 365 felügyeleti központban biztosít Ez egy Exchange Online e-mailek Alkalmazáshasználati jelentés az adott portál tevékenységre vonatkozó jelentések funkcióját részeként formájában. Ezek a jelentések megismeréséhez a környezetében mobil e-mail-elfogadása előtt, és a feltételes hozzáférés üzembe helyezése után is használható.

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

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com) egy olyan felhasználói fiókkal, amely rendelkezik Exchange rendszergazdai jogosultságokkal, engedélyekkel a [korábban ismertetett](#exchange-cmdlet-requirements) parancsmagok futtatására, egy érvényes Intune-licenccel, valamint a globális rendszergazdai szerepkörrel. A Microsoft Intune az aktuálisan bejelentkezett felhasználó e-mail címét használja a kapcsolat beállításához.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. A Microsoft Intune-irányítópult megnyitásához válassza az **Intune** lehetőséget. Válassza ki **Exchange-hozzáférés**, majd a **telepítő** válassza ki **az Exchange online-összekötő**.

4.  Az a **Exchange-hozzáférés – Exchange online-összekötő** lapon a **Service to Service Connector telepítése**. 

A Service-to-Service Connector konfigurációja és szinkronizálása az Exchange Online- vagy új dedikált Exchange Online-környezettel automatikusan megtörténik.

## <a name="validate-your-exchange-connection"></a>Az Exchange-kapcsolat ellenőrzése

Miután sikeresen konfigurálta az Exchange-szolgáltatások közötti összekötő, érvényesíteni az Exchange Connector-kiszolgáló adatait a a **Exchange-hozzáférés – Exchange online-összekötő** lapot.

Itt a **kapcsolódási állapotot** és a legutóbbi sikeres szinkronizálási kísérlet dátumát és időpontját is.

 

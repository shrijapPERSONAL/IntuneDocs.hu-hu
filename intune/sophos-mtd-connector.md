---
title: A Sophos Mobile Intune szolgáltatással való integráció beállítása
titleSuffix: Intune on Azure
description: Hogyan állítható be a Microsoft Intune-nal a Sophos Mobile megoldás annak érdekében, hogy a vállalati erőforrások mobil elérése.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94af7600ddfc5612c666bc38cb871d84c8c4baa5
ms.sourcegitcommit: b1ad73f5c9fd0ad8026c572aef8d15e258951c8f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64880826"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>A Sophos Mobile Threat Defense-összekötő az Intune-ban
Szabályozhatja a Sophos Mobile, a Mobile Threat Defense (MTD) megoldás, amely a Microsoft Intune-nal integrálható kockázatfelmérése alapján feltételes hozzáféréssel a vállalati erőforrások mobil elérése. A kockázatfelmérés a Sophos Mobile alkalmazást futtató eszközökről gyűjtött telemetriai adatokon alapul.
Konfigurálhatja a feltételes hozzáférési szabályzatok engedélyezve az Intune eszközmegfelelőségi szabályzatai, amelyek segítségével engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz az észlelt fenyegetések alapján a Sophos Mobile-kockázatfelmérés alapján.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Hogyan Intune és a Sophos Mobile segíti a vállalati erőforrások védelmét?
A Sophos Mobile alkalmazás Android és IOS-es rögzíti a fájlrendszer, a hálózati protokollkészlet, az eszköz és a Alkalmazáshasználati, ha elérhetők, és ezután elküldi a telemetriai adatokat a Sophos Mobile felhőszolgáltatáshoz, amely felméri az eszköz kockázatát a mobil veszélyforrások tekintetében.
Az Intune eszközmegfelelőségi szabályzata tartalmaz egy szabályt a Sophos Mobile Threat Defense, amely a Sophos Mobile-kockázatfelmérés alapján. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét. Amennyiben az eszköz nem megfelelőnek minősül, akkor megszűnik a felhasználók hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A felhasználók útmutatást is kapnak a Sophos Mobile App, telepítve van a összekeveri az eszközein a probléma megoldásához és a vállalati erőforrásokhoz való hozzáférés visszaszerzéséhez.  

## <a name="sample-scenarios"></a>Mintaforgatókönyvek
Néhány gyakori helyzet:  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján
Ha az eszközön rosszindulatú alkalmazásokat, például kártevőket észlel a rendszer, a probléma megoldásáig az eszközön letilthatók az alábbi műveletek:
- Hozzáférés a vállalati e-mailekhez
- A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással
- Hozzáférés vállalati alkalmazásokhoz

**Letiltása rosszindulatú alkalmazások észlelése esetén**:
 
![Észlelt rosszindulatú alkalmazások fogalmi képe](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**A fenyegetés kiküszöbölését követően hozzáférés**:  
![Megadja a hozzáférést a szervizelés után fogalmi képe](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján  
A hálózat, például a Man-in-the-middle támadások észlelése, és az eszközkockázat alapján Wi-Fi-hálózatok elérésének védelmét.  

**Wi-Fi hálózati elérés letiltása**:  
![Wi-Fi hálózati elérés letiltása](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**A fenyegetés kiküszöbölését követően hozzáférés**:   
![A fenyegetés kiküszöbölését követően hozzáférés](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján  
A hálózat, például a Man-in-the-middle támadások észlelése, és megakadályozza a az eszközkockázat alapján a vállalati fájlok szinkronizálását.  

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén**:   
![A SharePoint Online letiltása hálózati fenyegetések észlelése esetén](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**A fenyegetés kiküszöbölését követően hozzáférés**:  
![A Sharepoint például a fenyegetés kiküszöbölését követően hozzáférés](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Támogatott platformok  
- Az Android 5.0 és újabb verziók
- az iOS 11.0-s és újabb verziók

## <a name="prerequisites"></a>Előfeltételek  
- Prémium szintű Azure Active Directory
- Microsoft Intune-előfizetés 
- A Sophos Mobile Threat Defense-előfizetés

További információkért lásd: a [Sophos webhely](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>További lépések  
- [A Sophos integrálása az Intune-nal](sophos-mtd-connector-integration.md)
- [A Sophos alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [A Sophos eszközmegfelelőségi szabályzat létrehozása](mtd-device-compliance-policy-create.md)
- [A Sophos MTD-összekötő engedélyezése](mtd-connector-enable.md)

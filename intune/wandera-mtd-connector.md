---
title: Állítsa be az Intune-nal Wandera Mobile Security
titleSuffix: Intune on Azure
description: Hogyan állítható be a Microsoft Intune-nal Wandera Mobile Security annak érdekében, hogy a vállalati erőforrások mobil elérése.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6219d4a176eebf81747461b3cc8b478e46e86898
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407692"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Wandera Mobile Threat Defense-összekötő az Intune-ban  

Szabályozhatja a Wandera kockázatfelmérése alapján feltételes hozzáféréssel a vállalati erőforrások mobil elérése. Wandera a Mobile Threat Defense (MTD) megoldás, amely a Microsoft Intune-nal integrálható.  A kockázatfelmérés a Wandera szolgáltatás által az eszközökről gyűjtött telemetriai adatokon alapul többek között:
- Az operációs rendszer biztonsági rései
- Telepített kártékony alkalmazások
- Kártékony hálózati profilok
- Cryptojacking

Konfigurálható *feltételes hozzáférési* Wandera a alapuló házirendeket kockázatok felmérése, az Intune eszközmegfelelőségi szabályzatai által engedélyezett. Kockázatok felmérése a szabályzat engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz az észlelt fenyegetések alapján.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Hogyan Intune Wandera Mobile Threat Defense segíti és a vállalati erőforrások védelmét?  

Wandera a mobilalkalmazás zökkenőmentesen telepíti a Microsoft Intune-nal. Ez az alkalmazás rögzíti a fájlrendszer, a hálózati protokollkészlet és az eszközök és alkalmazások telemetrikus adatait (ha elérhető). Ez az információ szinkronizálja a Wandera felhőszolgáltatáshoz, amely felméri az eszköz kockázatát a mobil veszélyforrások tekintetében. Kockázati szint besorolásokra is a MÉRLEGELI Wandera konzolon igény szerint konfigurálható.

Az Intune megfelelőségi szabályzata tartalmaz egy szabályt az MTD-hez Wandera által jelentett kockázatértékelés alapján. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Nem megfelelő eszközökhöz erőforrásokhoz, mint az Office 365-höz való hozzáférés blokkolva lesz. A letiltott eszközök felhasználói útmutatót kap a probléma megoldásához és a hozzáférés visszaszerzéséhez Wandera alkalmazásból.

## <a name="supported-platforms"></a>Támogatott platformok  

A következő platformokon az Intune-ban regisztrált Wandera támogatottak:

- Az Android 5.0 és újabb verziók  
- iOS 10,2 és újabb verziók  

Platformra és eszközre vonatkozó további információkért lásd: a [Wandera webhely](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Előfeltételek  

- Microsoft Intune-előfizetés  
- Azure Active Directory  
- Wandera Mobile Threat Defense (korábbi nevén Wandera Secure)  

További információkért lásd: [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Itt a gyakori forgatókönyvek használata esetén Wandera MTD Intune-nal.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján  

Rosszindulatú alkalmazások, például a kártevők észlelése esetén az eszközökön, letilthatók a közös eszközök mindaddig, amíg a fenyegetés oldható meg. Közös címblokkok a következők:  
- Hozzáférés a vállalati e-mailekhez  
- A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással  
- Hozzáférés vállalati alkalmazásokhoz  

**Letiltása rosszindulatú alkalmazások észlelése esetén**:

![Észlelt rosszindulatú alkalmazások fogalmi képe](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**A fenyegetés kiküszöbölését követően hozzáférés**: 

![Megadja a hozzáférést a szervizelés után fogalmi képe](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján  

Észleli a hálózat, például man-in-the-middle támadásokat, és az eszközkockázat alapján Wi-Fi-hálózatok elérésének védelmét.  

**Wi-Fi hálózati elérés letiltása**:  

![Wi-Fi-s hálózati elérés letiltása](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**A fenyegetés kiküszöbölését követően hozzáférés**:  

![A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján

Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén**:  

![A SharePoint Online letiltása hálózati fenyegetések észlelése esetén](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**A fenyegetés kiküszöbölését követően hozzáférés**:  

![A SharePoint például a fenyegetés kiküszöbölését követően hozzáférés](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>További lépések

- [Wandera integrálása az Intune-nal](Wandera-mtd-connector-integration.md)
- [Wandera alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Wandera eszközmegfelelőségi szabályzat létrehozása](mtd-device-compliance-policy-create.md)
- [Wandera MTD-összekötő engedélyezése](mtd-connector-enable.md)
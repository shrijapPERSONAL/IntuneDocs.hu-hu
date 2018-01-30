---
title: "Lookout Mobile Threat Defense-összekötő az Intune-nal"
titlesuffix: Azure portal
description: "Lookout Mobile Threat Defense-összekötő beállítása az Intune-hoz"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41270fb217c87880e67c1c5e0adf319576031126
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Lookout Mobile Threat Defense-összekötő az Intune-nal

A Microsoft Intune-nal integrálható, Lookout nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Lookout által az eszközökről gyűjtött telemetriai adatokon alapul, például:
- Az operációs rendszer biztonsági rései
- Telepített kártékony alkalmazások
- Kártékony hálózati profilok

Az Intune megfelelőségi szabályzatai által engedélyezett, a Lookout által jelentett kockázatértékelés alapján feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. A beállítások lehetővé teszik a nem megfelelő eszközök engedélyezését vagy letiltását az észlelt fenyegetések alapján.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Hogyan segít az Intune és a Lookout Mobile Threat Defense a céges erőforrások védelmében?
A Lookout mobilalkalmazása, a **Lookout for Work** telepítve van és fut a mobileszközökön. Az alkalmazás rögzíti a fájlrendszer, a hálózati protokollkészlet, valamint az eszközök és az alkalmazások telemetriai adatait, ha elérhetők, és továbbítja őket a Lookout veszélyforrások elleni eszközvédelmi felhőszolgáltatásnak, amely kiszámítja az eszköz kockázatát a mobil veszélyforrások tekintetében. A Lookout konzolon igény szerint módosítható a fenyegetések kockázatiszint-besorolása.  

Az Intune megfelelőségi szabályzata tartalmaz egy szabályt a Lookout Mobile Threat Defense-hez, amely a Lookout kockázatértékelésén alapul. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Amennyiben az eszköz nem megfelelőnek minősül, akkor letiltható a hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A letiltott eszközök felhasználói értesítést kapnak arról, hogyan lehet a problémát elhárítani az újbóli hozzáféréshez. Az útmutatót a Lookout for Work alkalmazás szolgáltatja.

## <a name="supported-platforms"></a>Támogatott platformok
A Lookout az alábbi Intune-ban regisztrált platformokat támogatja:
* **Android 4.1 és újabb verziók**
* **iOS 8 és újabb verziók** Ha további információt szeretne a támogatott platformokról és nyelvekről, látogassa meg a [Lookout webhelyét](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Előfeltételek
* Microsoft Intune-előfizetés
* Azure Active Directory
* Vállalati előfizetés a Lookout Mobile EndPoint Securityhez  

További információ: [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Alább a Lookout Mobile Threat Defense Intune-nal való használatának gyakori eseteit soroljuk fel.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján
Ha az eszközön rosszindulatú alkalmazásokat, például kártevőket észlel a rendszer, a probléma megoldásáig az eszközön letilthatók az alábbiak:
* Hozzáférés a vállalati e-mailekhez
* A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással
* Hozzáférés vállalati alkalmazásokhoz

**Letiltás kártékony alkalmazás észlelése esetén:**

![az ábra azt mutatja, hogy a feltételes hozzáférési szabályzat letiltja a hozzáférést, ha az eszköz a rajta észlelt kártékony alkalmazások alapján nem megfelelőnek minősül](./media/malicious-apps-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést, amikor a fenyegetés kiküszöbölését követően az eszköz ismét megfelelőnek minősül](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján
Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadásokat, és az eszközkockázat alapján biztosítja a Wi-Fi-hálózatok elérésének védelmét.

**Wi-Fi-s hálózati elérés letiltása:**

![az ábra azt mutatja, hogy a feltételes hozzáférési szabályzat a hálózati fenyegetések alapján letiltja a Wi-Fi-hálózat elérését](./media/network-wifi-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján

Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén:**

![Ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat letiltotta az eszköz hozzáférését a SharePoint Online-hoz az észlelt fenyegetés alapján](./media/network-spo-blocked.png)


**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![Ábra, amely azt mutatja, hogy a hálózati fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>További lépések
A legfontosabb lépések a megoldás megvalósítása érdekében:
1.  [A Lookout-integráció beállítása](lookout-mtd-connector-integration.md)
2.  [A Lookout Mobile Threat Defense engedélyezése az Intune-ban](mtd-connector-enable.md)
3.  [A Lookout for Work felvétele és hozzárendelése](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [A Lookout eszközmegfelelőségi szabályzatának konfigurálása](mtd-device-compliance-policy-create.md)

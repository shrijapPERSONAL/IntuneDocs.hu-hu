---
title: "Lookout Mobile Threat Defense-összekötő"
description: "A vállalati erőforrásokhoz való hozzáférés védelme az eszköz-, a hálózati és az alkalmazáskockázat alapján a Lookout Mobile Threat Defense-összekötővel."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6ed808e3dd1db1bf58d4c0caa8cddccbc49c05f7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Lookout Mobile Threat Defense-összekötő az Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune-nal integrálható, Lookout nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Lookout által az eszközökről gyűjtött telemetriai adatokon alapul, például:
- Az operációs rendszer biztonsági rései
- Telepített kártékony alkalmazások
- Kártékony hálózati profilok

Az Intune megfelelőségi szabályzatai által engedélyezett, a Lookout által jelentett kockázatértékelés alapján feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. A beállítások lehetővé teszik a nem megfelelő eszközök engedélyezését vagy letiltását az észlelt fenyegetések alapján.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Hogyan segít az Intune és a Lookout Mobile Threat Defense a céges erőforrások védelmében?
A Lookout mobilalkalmazása, a **Lookout for Work** telepítve van és fut a mobileszközökön. Az alkalmazás rögzíti a fájlrendszer, a hálózati protokollkészlet, valamint az eszközök és az alkalmazások telemetriai adatait, ha elérhetők, és továbbítja őket a Lookout veszélyforrások elleni eszközvédelmi felhőszolgáltatásnak, amely kiszámítja az eszköz kockázatát a mobil veszélyforrások tekintetében. A Lookout konzolon igény szerint módosítható a fenyegetések kockázatiszint-besorolása.  

Az Intune megfelelőségi szabályzata tartalmaz egy szabályt a Lookout Mobile Threat Defense-hez, amely a Lookout kockázatértékelésén alapul. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Amennyiben az eszköz nem megfelelőnek minősül, akkor letiltható a hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A letiltott eszközök felhasználói értesítést kapnak arról, hogyan lehet a problémát elhárítani az újbóli hozzáféréshez. Az útmutatót a Lookout for Work alkalmazás szolgáltatja.

## <a name="supported-platforms"></a>Támogatott platformok:
A Lookout az alábbi Intune-ban regisztrált platformokat támogatja:
* **Android 4.1 és újabb verziók**
* **iOS 8 és újabb verziók** Ha további információt szeretne a támogatott platformokról és nyelvekről, látogassa meg a [Lookout webhelyét](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Előfeltételek:
* Microsoft Intune-előfizetés
* Azure Active Directory
* Vállalati előfizetés a Lookout Mobile EndPoint Securityhez  

További információ: [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Mintaforgatókönyvek
Néhány gyakori helyzet:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján
Ha az eszközön rosszindulatú alkalmazásokat, például kártevőket észlel a rendszer, a probléma megoldásáig az eszközön letilthatók az alábbiak:
* Hozzáférés a vállalati e-mailekhez
* A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással
* Hozzáférés vállalati alkalmazásokhoz

**Hozzáférés letiltása rosszindulatú alkalmazások észlelése esetén:**
![ábra, amely azt mutatja, ahogy a feltételes hozzáférési szabályzat letiltja a hozzáférést, ha az eszköz a rajta észlelt rosszindulatú alkalmazások alapján nem megfelelőnek minősül](../media/mtp/malicious-apps-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést, amikor a fenyegetés kiküszöbölését követően az eszköz ismét megfelelőnek minősül](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján
Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadásokat, és az eszközkockázat alapján biztosítja a Wi-Fi-hálózatok elérésének védelmét.

**Wi-Fi-hálózaton keresztüli hozzáférés letiltása:**
![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat a hálózati fenyegetések alapján letiltja a Wi-Fi-hálózat elérését](../media/mtp/network-wifi-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján

Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén:**

![Ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat letiltotta az eszköz hozzáférését a SharePoint Online-hoz az észlelt fenyegetés alapján](../media/mtp/network-spo-blocked.png)


**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![Ábra, amely azt mutatja, hogy a hálózati fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>További lépések
A legfontosabb lépések a megoldás megvalósítása érdekében:
1.  [A Lookout-előfizetés beállítása](setup-your-lookout-mtd-subscription.md)
2.  [A Lookout Mobile Threat Defense engedélyezése az Intune-ban](enable-lookout-mtd-connection.md)
3.  [A Lookout Mobile Threat Defense alkalmazás konfigurálása és üzembe helyezése](configure-deploy-lookout-for-work-app.md)
4.  [A Lookout eszközmegfelelőségi szabályzatának konfigurálása](create-lookout-device-compliance-policy.md)
5.  [A Lookout Mobile Threat Defense-integráció hibáinak elhárítása](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
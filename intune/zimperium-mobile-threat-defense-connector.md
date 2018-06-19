---
title: Zimperium MTD-összekötő az Intune-nal
titleSuffix: Intune on Azure
description: Megismerheti az Intune a Zimperium Mobile Threat Defense-szel való integrálását, amellyel vezérelheti a mobileszközök a vállalati erőforrásokhoz való hozzáférését.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 513db12094b5f58ccf743b68101b820afbcdff48
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
ms.locfileid: "29780067"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Zimperium Mobile Threat Defense-összekötő az Intune-nal

A Microsoft Intune-nal integrálható, Zimperium által irányított, veszélyforrások elleni mobileszköz-védelmi (MTD) megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Zimperium alkalmazást futtató eszközökről gyűjtött telemetriai adatokon alapul.

Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Zimperium által jelentett kockázatértékelés alapján feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, amelyekkel az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Hogyan segíti az Intune és a Zimperium a vállalati erőforrások védelmét?

Az Androidra és iOS-re készült Zimperium alkalmazás rögzíti a fájlrendszer, a hálózati protokollkészlet, valamint az eszközök és az alkalmazások telemetriai adatait, ha elérhetők, és továbbítja őket a Zimperium felhőszolgáltatásnak, amely felméri az eszköz kockázatát a mobil veszélyforrások tekintetében.

Az Intune eszközmegfelelőségi szabályzata tartalmaz egy szabályt a Zimperium mobilfenyegetések elleni védelméhez, amely a Zimperium kockázatfelmérésén alapul. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét. Amennyiben az eszköz nem megfelelőnek minősül, akkor megszűnik a felhasználók hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A mobileszközeikre telepített Zimperium mobilalkalmazás segítséget nyújt a felhasználóknak a probléma elhárításához és a vállalati erőforrásokhoz való hozzáférés visszaszerzéséhez.

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Az alábbi forgatókönyvek a Zimperium Intune-nal való integrációjához használhatók:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján

Ha az eszközön kártékony alkalmazásokat, például kártevőket észlel a rendszer, a probléma megoldásáig az eszközön letilthatók az alábbiak:

-   Hozzáférés a vállalati e-mailekhez

-   A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással

-   Hozzáférés vállalati alkalmazásokhoz

**Letiltás kártékony alkalmazás észlelése esetén:**

![A program kártevőt észlelt](./media/Maliciousapps_blocked_Zimperium.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A program kártevőt észlelt, hozzáférés megadva](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján

Észleli a hálózaton a fenyegetéseket, például a **közbeékelődéses (man-in-the-middle)** támadást, és az eszköz jelentette kockázat alapján biztosítja a Wi-Fi-hálózatok elérésének védelmét.

**Wi-Fi-s hálózati elérés letiltása:**

![Wi-Fi-s hálózati elérés letiltása](./media/network_wifi_blocked_Zimperium.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján

Észleli a hálózaton a fenyegetéseket, például a **közbeékelődéses (man-in-the-middle)** támadást, és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén:**

![A SharePoint Online letiltása hálózati fenyegetések észlelése esetén](./media/network_spo_blocked_Zimperium.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A fenyegetés kiküszöbölését követően a SharePoint-hozzáférés ismét biztosított – példa](./media/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Támogatott platformok

-   **Android 4.1 és újabb verziók**

-   **iOS 8 és újabb verziók**

## <a name="prerequisites"></a>Előfeltételek

-   Prémium szintű Azure Active Directory

-   Microsoft Intune-előfizetés

-   Zimperium Mobile Threat Defense-előfizetés

    -   További tájékoztatást a [Zimperium webhelyén](https://www.zimperium.com/zips-mobile-ips) találhat.

## <a name="next-steps"></a>További lépések

- [A Zimperium integrálása az Intune-nal](zimperium-mtd-connector-integration.md)

- [Zimperium-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Zimperiummal használható eszközmegfelelőségi szabályzat létrehozása](mtd-device-compliance-policy-create.md)

- [Zimperium MTD-összekötő engedélyezése](mtd-connector-enable.md)

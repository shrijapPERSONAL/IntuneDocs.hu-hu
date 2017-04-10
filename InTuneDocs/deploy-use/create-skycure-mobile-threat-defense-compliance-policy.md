---
title: "A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása | Microsoft Docs"
description: "A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása a klasszikus Intune-konzolon."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 3a7322bd389b6d2ca72108b9f54318000857895b
ms.lasthandoff: 03/22/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Skycure Mobile Threat Defense révén az Intune lehetővé teszi a mobileszközökön a veszélyforrások azonosítását és a kapcsolódó kockázatfelmérést. Intune-os megfelelőségi szabályzatban létrehozhat olyan szabályt, amely a kockázat felmérésével állapítja meg az eszköz megfelelőségét. Ezután a feltételes hozzáférési szabályzat segítségével az eszközmegfelelőség alapján szabályozhatja a szolgáltatásokhoz való hozzáférést.

## <a name="before-you-begin"></a>Előkészületek

A Skycure eszközvédelem megfelelőségi szabályzatának előfeltételei:

-   [A Skycure és az Intune közötti integráció beállítása](https://docs.microsoft.com/en-us/intune/deploy-use/setup-the-skycure-integration-with-Intune)

-   [A Skycure-kapcsolat engedélyezése az Intune-ban](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

A Skycure Mobile Threat Defense beállítása során a Skycure-konzolon létrehozott egy szabályzatot, amely a fenyegetéseket magas, közepes és alacsony szintűként osztályozza. Most az Intune-os megfelelőségi szabályzatban meg kell adni a maximális megengedett kockázati szintet.

## <a name="to-create-skycure-compliance-policy"></a>A Skycure megfelelőségi szabályzatának létrehozása

1.  A [klasszikus Intune-konzolon](https://manage.microsoft.com/) adja meg hitelesítő adatait.

2.  Válassza a **Házirend** &gt; **Megfelelőségi szabályzatok** elemet. Használhat meglévő megfelelőségi szabályzatot, vagy létrehozhat egy újat.

3.  Válassza a **Hozzáadás** &gt; **Eszközállapot-figyelő** lehetőséget, majd kapcsolja be a **Device Threat Protection** beállítást.

4.  Adja meg a **Legnagyobb megengedett fenyegetettségi szint** értékét:

    a.  **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Az eszköz csak akkor fér hozzá a céges erőforrásokhoz, ha semmilyen veszélyforrás nincs rajta. Ha bármilyen veszélyforrás észlelhető, az eszköz nem megfelelőnek minősül.

    b.  **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű veszélyforrások vannak rajta. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.

    c.  **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt veszélyforrások alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.

    d.  **Magas**: Ez a legkevésbé biztonságos beállítás. Nem léptet életbe korlátozást semmilyen veszélyforrás-szinten, és a Skycure Mobile Threat Defense szoftvert csak jelentéskészítésre használja.

> [!IMPORTANT] 
> Ha feltételes hozzáférési szabályzatokat hoz létre az Office 365 vagy más szolgáltatások számára, a rendszer ennek a megfelelőségi értékelésnek az alapján tiltja le a nem megfelelő eszközök adott szolgáltatásokhoz való hozzáférését a fenyegetés megszüntetéséig.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>További lépések

-   Feltételes hozzáférési szabályzat létrehozása:

    -   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Helyszíni Exchange](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype Vállalati online verzió](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)


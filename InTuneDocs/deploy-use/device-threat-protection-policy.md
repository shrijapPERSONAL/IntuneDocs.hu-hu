---
title: "Eszközvédelmi szabály engedélyezése | Microsoft Docs"
description: "A mobilfenyegetések elleni védelmet szolgáló szabály engedélyezése az eszköz megfelelőségi szabályzatában."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 08edca426901eda3017bf17dda3b330dd186ce58


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Lookout Mobile Threat Protection révén az Intune lehetővé teszi a mobileszközökön a veszélyforrások azonosítását és a kapcsolódó kockázatfelmérést. Megfelelőségi szabályzatban létrehozhat olyan szabályt, amely a kockázat felmérésével állapítja meg az eszköz megfelelőségét. Ezután a feltételes hozzáférési szabályzat segítségével az eszközmegfelelőség alapján szabályozhatja a szolgáltatásokhoz való hozzáférést.

A Lookout eszközvédelem megfelelőségi szabályzatának előfeltételei:

- [A Lookout eszközvédelem előfizetésének beállítása](set-up-your-subscription-with-lookout-mtp.md)
- [A Lookout-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md)
- [A Lookout for Work alkalmazás konfigurálása](configure-and-deploy-lookout-for-work-apps.md)

A Lookout veszélyforrások elleni eszközvédelmének beállítása során a [Lookout-konzolon](https://aad.lookout.com) létrehozott egy szabályzatot, amely a fenyegetéseket magas, közepes és alacsony szintűként osztályozza. Az Intune megfelelőségi szabályzatban megadta a maximális megengedett kockázati szintet.

1. Lépjen az [Intune felügyeleti konzol](https://manage.microsoft.com) **Megfelelőségi szabályzatok** lapjára. Használhat meglévő megfelelőségi szabályzatot, vagy létrehozhat egy újat. Az **Eszközállapot** alatt engedélyezze a **Veszélyforrások elleni eszközvédelem** funkciót.
  ![képernyőfelvétel az eszközvédelmi szabály beállításáról](../media/mtp/mtp-compliance-policy-rule.png)

2. Adja meg a **Legnagyobb megengedett fenyegetettségi szint** értékét:
  * **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség.  Az eszköz csak akkor fér hozzá a céges erőforrásokhoz, ha semmilyen veszélyforrás nincs rajta.  Ha bármilyen veszélyforrás észlelhető, az eszköz nem megfelelőnek minősül.  
  * **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű veszélyforrások vannak rajta. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  * **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt veszélyforrások alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
  * **Magas**: Ez a legkevésbé biztonságos beállítás. Nem léptet életbe korlátozást semmilyen veszélyforrás-szinten, és a Lookout Mobile Threat Protection szoftvert csak jelentéskészítésre használja.

![képernyőkép az eszközvédelmi szabály beállításának kockázatiszint-beállításáról](../media/mtp/mtp-compliance-policy-setting.png)

Ha feltételes hozzáférési szabályzatokat hoz létre az Office 365 vagy más szolgáltatások számára, a rendszer ennek a megfelelőségi értékelésnek az alapján tiltja le a nem megfelelő eszközök adott szolgáltatásokhoz való hozzáférését a fenyegetés megszüntetéséig.

## <a name="monitor-device-threats"></a>Eszközök veszélyforrásainak figyelése
Az eszközök megfelelőségi állapota az [Intune felügyeleti konzol](https://manage.microsoft.com) **Minden eszköz** lapján tekinthető meg.

![képernyőfelvétel az eszköz megfelelőségi állapotáról az Intune felügyeleti konzol Eszközök lapján](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>További lépések
* Feltételes hozzáférési szabályzat létrehozása
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Helyszíni Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Vállalati online verzió](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jan17_HO4-->



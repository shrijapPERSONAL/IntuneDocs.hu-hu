---
title: "Eszközvédelmi szabály engedélyezése a megfelelőségi szabályzatban | Microsoft Intune"
description: "A mobilfenyegetések elleni védelmet szolgáló szabály engedélyezése az eszköz megfelelőségi szabályzatában."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 686321a1c19acb9a3a7e262822b11304d07adb40
ms.openlocfilehash: 3e6aef013ae8764d9b031e880c333e184191feb4


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban
A Lookout mobilfenyegetések elleni védelemmel az Intune lehetővé teszi a mobilfenyegetések azonosítását és az eszköz kockázatértékelését. Létrehozhat megfelelőségi szabályzatban meghatározott szabályokat, amelyek lehetővé teszik a kockázatértékelés felhasználását annak megállapítására, hogy az eszköz megfelelő-e. Ezután a feltételes hozzáférési szabályzat segítségével az eszközmegfelelőség alapján engedélyezheti vagy tilthatja a hozzáférést az Exchange-hez, a SharePointhoz és más szolgáltatásokhoz.

Ahhoz, hogy a Lookout veszélyforrások elleni eszközvédelmi funkciója befolyásolhassa az eszköz megfelelőségi szabályzatát:

* Az **Eszközök fenyegetések elleni védelme** szabályt engedélyezni kell a megfelelőségi szabályzatban.

* Az **Intune felügyeleti konzolján** a **Lookout-állapot** lapon ekkor az **Aktív** állapotnak kell megjelennie. További információért a Lookout-integráció aktiválásáról lásd a [Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md) című témakört.


Az eszköz fenyegetések elleni védelmét szolgáló szabály létrehozása előtt javasoljuk, hogy [állítsa be Lookout veszélyforrások elleni eszközvédelem-előfizetését](set-up-your-subscription-with-lookout-mtp.md), [engedélyezze a Lookout-kapcsolatot az Intune-ban](enable-lookout-mtp-connection-in-intune.md), és [konfigurálja a Lookout for Work alkalmazást](configure-and-deploy-lookout-for-work-apps.md). A megfelelőségi szabály csak a beállítás végrehajtását követően lép érvénybe.

A fenyegetés elleni védelmi szabály engedélyezéséhez az eszközön használhat meglévő megfelelőségi szabályzatot, vagy létrehozhat egy újat.

A Lookout veszélyforrások elleni eszközvédelmének beállítása részeként a [Lookout-konzolon](https://aad.lookout.com) létrehozott egy szabályzatot, amely a fenyegetéseket magas, közepes és alacsony szintűként osztályozza. Az Intune megfelelőségi szabályzatban a fenyegetés szintje alapján határozhatja meg a maximális megengedett kockázati szintet.

Az **Intune felügyeleti konzoljának** **Megfelelőségi szabályzatok** lapján válassza az **Eszközállapot** munkaterületet, és engedélyezze az **Veszélyforrások elleni eszközvédelem** szabályt a váltógombbal. Ezután válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:
* **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség.  Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett.  Ha bármilyen szintű fenyegetés észlelhető, az eszköz nem megfelelőnek minősül.  
* **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha vonatkozásában kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
* **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
* **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ezért valószínűleg csak jelentéskészítési célokra lehet hasznos.

![képernyőfelvétel az eszköz fenyegetés elleni védelmi szabálya beállításáról ](../media/mtp/mtp-compliance-policy-rule.png)

![képernyőfelvétel az eszköz fenyegetés elleni védelmi szabálya beállításának kockázatiszint-opciójáról](../media/mtp/mtp-compliance-policy-setting.png)

Ha feltételes hozzáférési szabályzatokat hoz létre az Office 365 és más szolgáltatások számára, a rendszer figyelembe veszi a fenti megfelelőségi értékelést, és letiltja a nem megfelelő eszközök vállalati erőforrásokhoz való hozzáférését a fenyegetés megszüntetéséig.

Az eszközök megfelelőségi állapota az **Intune felügyeleti konzoljának** **Minden eszköz** lapján tekinthető meg.

![képernyőfelvétel az eszköz megfelelőségi állapotáról az Intune felügyeleti konzol Eszközök lapján](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>További lépések
* Feltételes hozzáférési szabályzat létrehozása
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Helyszíni Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Vállalati online verzió](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO5-->



---
title: "Eszközvédelmi szabály engedélyezése a megfelelőségi szabályzatban | Microsoft Intune"
description: "A mobilfenyegetések elleni védelmet szolgáló szabály engedélyezése az eszköz megfelelőségi szabályzatában."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban
A Lookout mobilfenyegetések elleni védelemmel az Intune lehetővé teszi a mobilfenyegetések azonosítását és az eszköz kockázatértékelését.  
A megfelelőségi szabályzatban meghatározott szabályok lehetővé teszik e kockázatértékelés felhasználását annak megállapítására, hogy az eszköz megfelel-e a szabályzatnak. Ezután a feltételes hozzáférési szabályzat segítségével az eszközmegfelelőség alapján engedélyezhető vagy tiltható a hozzáférés az Exchange-hez, a SharePointhoz és más szolgáltatásokhoz.

Ahhoz, hogy a Lookout MTP veszélyforrás-észlelési funkciója befolyásolhassa az eszköz megfelelőségi szabályzatát:

1.  Az **Eszközök fenyegetések elleni védelme** szabályt engedélyezni kell a megfelelőségi szabályzatban.

2.  Az Intune felügyeleti konzolon a **Lookout állapota** oldalon ekkor az **Aktív** státusznak kell megjelennie. További információért a Lookout-integráció aktiválásáról lásd a [Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md) című témakört.


## Az eszköz fenyegetések elleni védelmét szolgáló szabály konfigurálása

Az eszköz fenyegetések elleni védelmét szolgáló szabály létrehozása előtt javasoljuk, hogy [állítsa be Lookout MTP-előfizetését](set-up-your-subscription-with-lookout-mtp.md), engedélyezze [a Lookout-kapcsolatot az Intune-ban](enable-lookout-mtp-connection-in-intune.md), és [konfigurálja a Lookout for Work alkalmazást](configure-and-deploy-lookout-for-work-apps.md). A megfelelőségi szabály csak a beállítás végrehajtását követően lép érvénybe.

A fenyegetés elleni védelmi szabály engedélyezéséhez az eszközön használhat meglévő megfelelőségi szabályzatot, vagy létrehozhat egy újat.

A Lookout MTP beállítása részeként a [Lookout MTP-konzolon](https://aad.lookout.com) létrehozott egy szabályzatot, amely a fenyegetéseket magas, közepes és alacsony szintűként osztályozza. Az Intune megfelelőségi szabályzatban a fenyegetés szintje alapján határozhatja meg a maximális megengedett kockázati szintet.

Az Intune felügyeleti konzol megfelelőségi szabályzat lapján válassza az **Eszköz állapota** munkaterületet és engedélyezze az **Eszköz fenyegetés elleni védelme** szabályt a váltógombbal. Ezután válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:
* **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség.  Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett.  Bármilyen szintű fenyegetés észlelése esetén az eszköz értékelése nem megfelelő lesz.  
* **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha vonatkozásában kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
* **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
* **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ezért valószínűleg csak jelentéskészítési célokra használható.

![képernyőfelvétel az eszköz fenyegetés elleni védelmi szabálya beállításáról ](../media/mtp/mtp-compliance-policy-rule.png)

![képernyőfelvétel az eszköz fenyegetés elleni védelmi szabálya beállításának kockázatiszint-opciójáról](../media/mtp/mtp-compliance-policy-setting.png)

Ha feltételes hozzáférési szabályzatokat hoz létre az O365 és más szolgáltatások számára, a rendszer figyelembe veszi a fenti megfelelőségi értékelést, és letiltja a nem megfelelő eszközöket a fenyegetés megszüntetéséig.

Az eszközök megfelelőségi állapota az Intune felügyeleti konzol Eszközök lapján tekinthető meg.

![képernyőfelvétel az eszköz megfelelőségi állapotáról az Intune felügyeleti konzol Eszközök lapján](../media/mtp/mtp-device-status-intune-console.png)

## További lépések
* Feltételes hozzáférési szabályzat létrehozása
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Helyszíni Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Vállalati online verzió](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->



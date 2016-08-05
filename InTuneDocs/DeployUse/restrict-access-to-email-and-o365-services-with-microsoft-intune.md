---
title: "Az e-mailek és az O365-szolgáltatások elérésének korlátozása | Microsoft Intune"
description: "Ez a témakör azt ismerteti, hogyan használható a feltételes hozzáférés arra, hogy csak a megfelelő eszközök férhessenek hozzá a vállalati e-mailekhez, valamint a SharePoint Online-on és más szolgáltatásokban tárolt vállalati adatokhoz."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 536d34e618efdc78b3103a3b1b36f13fb784781c


---

# Az e-mailek, az O365- és egyéb szolgáltatások elérésének korlátozása
Az Intune feltételes hozzáférés funkciójával korlátozhatja a hozzáférést a vállalati e-mail- és O365-szolgáltatásokhoz. Az Intune feltételes hozzáférési funkciói révén elérheti, hogy a vállalati e-mail- és O365-szolgáltatásokhoz csak olyan eszközök férhessenek hozzá, amelyek megfelelnek az Ön által beállított szabályoknak.
## Hogyan működik a feltételes hozzáférés?
A rendszer a megfelelőségi szabályok beállításai alapján ellenőrzi az eszköz megfelelőségét. A feltételes hozzáférési szabályzat ennek az ellenőrzésnek az eredménye alapján engedélyezi vagy korlátozza a hozzáférést az adott szolgáltatásokhoz. A feltételes hozzáférési szabályzat és a megfelelőségi szabályok együttes alkalmazásával elérheti, hogy a szolgáltatáshoz csak megfelelő eszközök férjenek hozzá. A megfelelőségi szabályzat és a feltételes hozzáférési szabályzat telepítve van a felhasználónál. A rendszer minden olyan eszköz megfelelőségét ellenőrzi, amelyről a felhasználó használja a szolgáltatásokat.

Ne feledje, hogy ahhoz, hogy a rendszer képes legyen az eszköz megfelelőségének ellenőrzésére, az eszközt használó felhasználóra vonatkozóan megfelelőségi szabályzatot kell alkalmazni.
Amennyiben a felhasználóra nem vonatkozik megfelelőségi szabályzat, a rendszer megfelelőként kezeli az eszközt, és egyáltalán nem korlátozza a hozzáférést.

Ha az eszközök nem felelnek meg a szabályzatokban megadott feltételeknek, a rendszer végigvezeti a végfelhasználót az eszköz regisztrálásának és az eszköz kompatibilitását megakadályozó problémák megoldásának a folyamatán.

A feltételes hozzáférés jellemzően a következő folyamatot követi:

![Azokat a döntési pontokat megjelenítő diagram, amelyek segítségével a rendszer meghatározza, hogy kapjon-e hozzáférést az adott eszköz a szolgáltatáshoz](../media/ConditionalAccess4.png)

## A feltételes hozzáférés konfigurálásának módja
Feltételes hozzáféréssel a következő Microsoft-szolgáltatásokhoz való hozzáférést kezelheti: **Helyszíni Exchange**, **Exchange Online**, **Dedikált Exchange Online**, **SharePoint Online** és **Skype vállalati online verzió**.

A feltételes hozzáférés beállításához állítson be eszközmegfelelőségi szabályzatot és feltételes hozzáférési szabályzatot.

A megfelelőségi szabályzathoz többek között a következő beállítások tartoznak: PIN-kód, titkosítás, feltörték-e az eszközt. Ahhoz, hogy az eszközt a rendszer megfelelőnek értékelje, meg kell felelnie a szabályoknak.

A feltételes hozzáférési szabályzat segítségével a következők alapján korlátozhatja a hozzáférést:
- Az eszköz megfelelőségi állapota.
- A platform, amelyen az eszköz fut.
- A szolgáltatásokhoz való hozzáféréshez használt alkalmazások típusa.

Az Intune más szabályzataitól eltérően a feltételes hozzáférési szabályzatokat nem kell telepítenie. Elég konfigurálni a szabályzatot, kiválasztani, hogy mely felhasználókra vonatkozzon, és a rendszer már alkalmazza is a szabályzatot a megcélzott felhasználókra. Amikor egy felhasználóra házirend vonatkozik, az erőforrások eléréséhez az általa használt összes eszköznek meg kell felelnie a házirendnek.


## További lépések
1. [Tudjon meg többet az eszközmegfelelőségről és annak működéséről ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Megfelelőségi házirend létrehozása](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Megfelelőségi szabályzat létrehozása a következők valamelyikéhez:
> [!div class="op_single_selector"]
  - [Feltételes hozzáférési szabályzat létrehozása az Exchange Online-hoz](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása az új Dedikált Exchange Online-hoz](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a régi Dedikált Exchange Online-hoz](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a SharePoint Online-hoz](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a Skype vállalati online verziójához](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a Dynamics CRM Online-hoz](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->



---
title: "Mi a feltételes hozzáférés? | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató a felhasználókra és eszközökre vonatkozó feltételek meghatározásához a vállalati adatok eléréséhez az Azure-beli Intune előzetesben."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 41931f64db969c82f79e007c4be9e68b7caf4ce9
ms.openlocfilehash: 20696fb2dc0126aa224e779738cedb4f95f666e8


---

# <a name="what-is-conditional-access"></a>Mi a feltételes hozzáférés?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Ez a témakör az Enterprise Mobility + Security szolgáltatásra vonatkozó feltételes hozzáférést, valamint az Intune feltételes hozzáférési képességeit ismerteti.

Az Enterprise Mobility + Security (EMS) által kínált feltételes hozzáférés az Azure Active Directory és a Microsoft Intune képességeit használva teszi lehetővé a vállalati adatok biztonságának védelmét, miközben a felhasználók számára bármilyen eszközről kényelmes munkavégzést biztosít.

A feltételes hozzáféréssel olyan feltételeket adhat meg, amelyek a vállalati adatokhoz való hozzáférést helyszín, eszköz, felhasználói állapot vagy az alkalmazás bizalmassági szintje alapján korlátozzák.

Az Intune és az Azure Active Directory együttesen gondoskodik róla, hogy csak felügyelt és megfelelő eszközök férhessenek hozzá az e-mailekhez és az Office 365-szolgáltatásokhoz. Az Azure Active Directoryban beállíthat például olyan szabályzatot, amely az Office 365-szolgáltatásokhoz való hozzáférést csak tartományhoz csatlakozó számítógépek és olyan mobileszközök számára engedélyezi, amelyek regisztrálva vannak valamilyen mobileszköz-felügyeleti alkalmazásban, például az Intune-ban. Az Intune-nal létrehozhat olyan eszközmegfelelőségi profilt, amely kiértékeli az eszköz megfelelőségi állapotát. A megfelelőségi állapotot a rendszer jelenti az Azure Active Directorynak, amely azt a szabályzat érvényre juttatásához használja, amikor a felhasználó megpróbálja elérni a vállalati erőforrásokat. Az Intune-beli eszközmegfelelőségről további információkat talál a [Mi az eszközmegfelelőség?](/intune-azure/set-device-compliance/what-is-device-compliance) című cikkben.

A felhőalkalmazásokhoz, például az Exchange Online-hoz a feltételes hozzáférést az Azure Active Directoryban lehet konfigurálni. További információt [ebben a cikkben](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal) talál.

## <a name="on-premises-conditional-access-in-intune"></a>Helyszíni feltételes hozzáférés az Intune-ban

Az Intune-beli feltételes hozzáféréssel az eszközfelügyelet és eszközregisztráció alapján tiltható vagy engedélyezhető a hozzáférés a **helyszíni Exchange-hez**.

A rendszer az eszközmegfelelőségi profil beállításai alapján ellenőrzi az eszköz megfelelőségét. A feltételes hozzáférés az ellenőrzés eredménye alapján engedélyezi vagy tiltja a hozzáférést a helyszíni Exchange-hez. A feltételes hozzáférés és az eszközmegfelelőségi profil együttes alkalmazásával elérheti, hogy a helyszíni Exchange-hez csak megfelelő eszközök férhessenek hozzá. A feltételes hozzáférés speciális beállításainak használatával pontosabb szabályozást is érvényesíthet, például egyes platformok engedélyezése vagy tiltása, vagy a nem az Intune által felügyelt eszközök azonnali tiltása.

Az eszközmegfelelőségi profil és a feltételes hozzáférés a felhasználóhoz vannak rendelve. A rendszer ellenőrzi a felhasználó által a helyszíni Exchange elérésére használt minden eszköz megfelelőségét. Ne feledje, hogy ahhoz, hogy a rendszer képes legyen az eszköz megfelelőségének ellenőrzésére, az eszközt használó felhasználóhoz megfelelőségi profilt kell hozzárendelni. Amennyiben a felhasználóra nem vonatkozik megfelelőségi szabályzat, a rendszer megfelelőként kezeli az eszközt, és egyáltalán nem korlátozza a hozzáférést.

Ha az eszközök nem tesznek eleget a megadott feltételeknek, a program végigvezeti a felhasználót az eszköz regisztrálásának és az eszköz megfelelőségét akadályozó probléma megoldásának lépésein.

## <a name="next-steps"></a>További lépések

[Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez](create-conditional-access-policy-for-exchange-on-premises.md)

[Feltételes hozzáférés konfigurálása az Azure Active Directoryban](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO1-->



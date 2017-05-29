---
title: "A Lookout MTP engedélyezése az Intune-ban | Microsoft Docs"
description: "A Lookout mobil veszélyforrások elleni védelem engedélyezése az Intune felügyeleti konzolon."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2a99839ece16c56c7bfaacb295796525903f9464
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>A Lookout MTD-kapcsolat engedélyezése a klasszikus Intune-konzolon

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Lookout Mobile Threat Defense (MTD) funkciójának Intune-ra vonatkozó engedélyezéséhez előzőleg konfigurálni kell az Intune-összekötőt a Lookout-konzolon.  Ha még nem tette meg, hajtsa végre a [Lookout Mobile Threat Defense-előfizetés beállítása](setup-your-lookout-mtd-subscription.md) című részben leírt lépéseket.

A Lookout MTP-kapcsolat engedélyezéséhez az Intune-ban a [Microsoft Intune felügyeleti konzol](https://manage.microsoft.com) **Felügyelet** lapján válassza a **Harmadik fél szolgáltatásának integrációja** lehetőséget. Válassza a **Lookout állapota** lehetőséget és engedélyezze a **Szinkronizálás MTP-vel** funkciót a váltógomb segítségével.

![képernyőkép a Lookout szinkronizálási lapjáról a váltógomb kiemelésével](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> A Lookout for Work alkalmazás konfigurálását **kötelező** a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.

Ez végrehajtja a Lookout és az Intune közötti integráció beállítását az Intune felügyeleti konzolon.  A megoldás kivitelezésének további néhány lépésében a [Lookout for Work alkalmazások](/intune-classic/deploy-use/device-threat-protection-policy) szabályzatának telepítésére is sor kerül.


## <a name="next-steps"></a>További lépések
[A Lookout for Work alkalmazás konfigurálása](/intune-classic/deploy-use/device-threat-protection-apps)


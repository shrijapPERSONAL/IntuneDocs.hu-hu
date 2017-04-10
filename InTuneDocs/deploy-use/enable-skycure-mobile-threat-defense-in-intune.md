---
title: "A Skycure Mobile Threat Defense engedélyezése az Intune-ban | Microsoft Docs"
description: "A Skycure Mobile Threat Defense engedélyezése a klasszikus Intune-konzolon."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>A Skycure Mobile Threat Defense engedélyezése az Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Skycure mobileszköz-védelmi (MTD) funkciójának Intune-beli engedélyezéséhez előzőleg konfigurálni kell az [Intune-összekötőt a Skycure-konzolon](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>A Skycure MTD-kapcsolat engedélyezése az Intune-ban

1.  A [klasszikus Intune-konzolon](https://manage.microsoft.com/) adja meg hitelesítő adatait.

2.  Válassza az **Admin** (Felügyelet) &gt; **Third Party Service Integration** (Külső szolgáltatások integrációja), majd a **Skycure Status** (Skycure állapota) lehetőséget, és a kapcsológombbal engedélyezze a **Synchronization with MTD** (Szinkronizálás az MTD-vel) beállítást.

    ![A Skycure-t engedélyező kapcsoló a klasszikus Intune-konzolon](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> A Skycure alkalmazás konfigurálását a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt kell elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.

Ezzel a lépéssel fejeződik be a Skycure és az Intune közötti integráció beállítása az Intune felügyeleti konzolon. A megoldás implementálásának következő néhány lépésében kerül sor a Skycure for Work alkalmazások központi telepítésére és a megfelelőségi szabályzat beállítására.

## <a name="next-steps"></a>További lépések

[A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)


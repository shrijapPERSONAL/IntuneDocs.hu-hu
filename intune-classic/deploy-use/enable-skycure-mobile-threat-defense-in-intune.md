---
title: "A Skycure Mobile Threat Defense engedélyezése az Intune-ban"
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
ms.openlocfilehash: 4dad45d15fec7189fdcf184839040b9e3f9a3a48
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>A Skycure Mobile Threat Defense engedélyezése az Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Skycure Mobile Threat Defense engedélyezéséhez már konfigurálnia kellett az [Intune Connectort a Skycure-konzolon] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>A Skycure MTD-kapcsolat engedélyezése az Intune-ban

1.  A [klasszikus Intune-konzolon](https://manage.microsoft.com/) adja meg hitelesítő adatait.

2.  Válassza az **Admin** (Felügyelet) &gt; **Third Party Service Integration** (Külső szolgáltatások integrációja), majd a **Skycure Status** (Skycure állapota) lehetőséget, és a kapcsológombbal engedélyezze a **Synchronization with MTD** (Szinkronizálás az MTD-vel) beállítást.

    ![A Skycure-t engedélyező kapcsoló a klasszikus Intune-konzolon](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> A Skycure alkalmazás konfigurálását a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt kell elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.

Ezzel a lépéssel fejeződik be a Skycure és az Intune közötti integráció beállítása az Intune felügyeleti konzolon. A megoldás implementálásának következő néhány lépésében kerül sor a Skycure for Work alkalmazások központi telepítésére és a megfelelőségi szabályzat beállítására.

## <a name="next-steps"></a>További lépések

[A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
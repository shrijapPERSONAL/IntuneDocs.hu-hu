---
title: A Skycure Mobile Threat Defense engedélyezése az Intune-ban
description: A Skycure Mobile Threat Defense engedélyezése a klasszikus Intune-portálon.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da4197a41798f4e47ff35d2dfab36c5317f92e21
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>A Skycure Mobile Threat Defense engedélyezése az Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A Skycure Mobile Threat Defense engedélyezéséhez előzőleg konfigurálni kell az [Intune-összekötőt a Skycure-konzolon](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>A Skycure MTD-kapcsolat engedélyezése az Intune-ban

1.  Nyissa meg a [klasszikus Intune-portált](https://manage.microsoft.com/), és adja meg hitelesítő adatait.

2.  Válassza az **Admin** (Felügyelet) &gt; **Third Party Service Integration** (Külső szolgáltatások integrációja), majd a **Skycure Status** (Skycure állapota) lehetőséget, és a kapcsológombbal engedélyezze a **Synchronization with MTD** (Szinkronizálás az MTD-vel) beállítást.

    ![A Skycure-t engedélyező kapcsoló a klasszikus Intune-portálon](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> A Skycure alkalmazás konfigurálását a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt kell elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.

Ezzel a lépéssel fejeződik be a Skycure és az Intune közötti integráció beállítása az Intune felügyeleti konzolon. A megoldás implementálásának következő néhány lépésében kerül sor a Skycure for Work alkalmazások központi telepítésére és a megfelelőségi szabályzat beállítására.

## <a name="next-steps"></a>További lépések

[A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

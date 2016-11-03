---
title: "A Lookout MTP engedélyezése az Intune-ban | Microsoft Intune"
description: "A Lookout mobil veszélyforrások elleni védelem engedélyezése az Intune felügyeleti konzolon."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1334500471d2aea5e8c58a3219c755bfd9953424
ms.openlocfilehash: 4ae7d6c571f69c0cc51dc15355e50325afb88694


---

# A Lookout MTP-kapcsolat engedélyezése az Intune felügyeleti konzolon
Ez a témakör a Lookout MTP-kapcsolat engedélyezését mutatja be az Intune-ban. Mielőtt végrehajtaná a jelen lépést, konfigurálni kell az Intune-összekötőt a Lookout MTP-konzolon.  Ha ezt még nem tette meg, hajtsa végre a [Lookout mobil veszélyforrások elleni védelem beállítása az előfizetéshez](set-up-your-subscription-with-lookout-mtp.md) című részben leírt lépéseket.

A Lookout MTP-kapcsolat engedélyezéséhez az Intune-ban a [Microsoft Intune felügyeleti konzol](https://manage.microsoft.com) **Felügyelet** lapján válassza a **Harmadik fél szolgáltatásának integrációja** lehetőséget. Válassza a **Lookout állapota** lehetőséget és engedélyezze a **Szinkronizálás MTP-vel** funkciót a váltógomb segítségével.

![képernyőkép a Lookout szinkronizálási lapjáról a váltógomb kiemelésével](../media/mtp/lookout-intune-synchronization.png)

Ez végrehajtja a Lookout és az Intune közötti integráció beállítását az Intune felügyeleti konzolon.  A megoldás megvalósításának következő néhány lépésében kerül sor a [Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) alkalmazások központi telepítésére és a [megfelelőségi](enable-device-threat-protection-rule-in-compliance-policy.md) szabályzat beállítására.

>[!IMPORTANT]
> A Lookout for Work alkalmazás konfigurálását **kötelező** a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.
## További lépések
[A Lookout for Work alkalmazás konfigurálása ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO2-->



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
translationtype: Human Translation
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>A Lookout MTP-kapcsolat engedélyezése az Intune felügyeleti konzolon

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Lookout veszélyforrások elleni védelmi funkciójának (MTP) Intune-ra vonatkozó engedélyezéséhez előzőleg konfigurálni kell az Intune-összekötőt a Lookout-konzolon.  Ha ezt még nem tette meg, hajtsa végre a [Lookout mobil veszélyforrások elleni védelem beállítása az előfizetéshez](set-up-your-subscription-with-lookout-mtp.md) című részben leírt lépéseket.

A Lookout MTP-kapcsolat engedélyezéséhez az Intune-ban a [Microsoft Intune felügyeleti konzol](https://manage.microsoft.com) **Felügyelet** lapján válassza a **Harmadik fél szolgáltatásának integrációja** lehetőséget. Válassza a **Lookout állapota** lehetőséget és engedélyezze a **Szinkronizálás MTP-vel** funkciót a váltógomb segítségével.

![képernyőkép a Lookout szinkronizálási lapjáról a váltógomb kiemelésével](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> A Lookout for Work alkalmazás konfigurálását **kötelező** a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.

Ez végrehajtja a Lookout és az Intune közötti integráció beállítását az Intune felügyeleti konzolon.  A megoldás megvalósításának következő néhány lépésében kerül sor a [Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) alkalmazások központi telepítésére és a [megfelelőségi](enable-device-threat-protection-rule-in-compliance-policy.md) szabályzat beállítására.


## <a name="next-steps"></a>További lépések
[A Lookout for Work alkalmazás konfigurálása](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->



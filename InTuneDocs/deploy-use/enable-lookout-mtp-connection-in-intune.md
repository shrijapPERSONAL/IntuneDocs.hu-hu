---
title: "A Lookout MTP engedélyezése az Intune-ban | Microsoft Intune"
description: "A Lookout mobil veszélyforrások elleni védelem engedélyezése az Intune felügyeleti konzolon."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 1bef6c15387309e1b36bc85758ca699acd54fdd0


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>A Lookout MTP-kapcsolat engedélyezése az Intune felügyeleti konzolon
Ez a témakör a Lookout MTP-kapcsolat engedélyezését mutatja be az Intune-ban. Mielőtt végrehajtaná ezt a lépést, konfigurálnia kell az Intune-összekötőt a Lookout konzolon.  Ha ezt még nem tette meg, hajtsa végre a [Lookout mobil veszélyforrások elleni védelem beállítása az előfizetéshez](set-up-your-subscription-with-lookout-mtp.md) című részben leírt lépéseket.

A Lookout MTP-kapcsolat engedélyezéséhez az Intune-ban a [Microsoft Intune felügyeleti konzol](https://manage.microsoft.com) **Felügyelet** lapján válassza a **Harmadik fél szolgáltatásának integrációja** lehetőséget. Válassza a **Lookout állapota** lehetőséget és engedélyezze a **Szinkronizálás MTP-vel** funkciót a váltógomb segítségével.

![képernyőkép a Lookout szinkronizálási lapjáról a váltógomb kiemelésével](../media/mtp/lookout-intune-synchronization.png)

Ez végrehajtja a Lookout és az Intune közötti integráció beállítását az Intune felügyeleti konzolon.  A megoldás megvalósításának következő néhány lépésében kerül sor a [Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) alkalmazások központi telepítésére és a [megfelelőségi](enable-device-threat-protection-rule-in-compliance-policy.md) szabályzat beállítására.

>[!IMPORTANT]
> A Lookout for Work alkalmazás konfigurálását **kötelező** a megfelelőségi szabályok létrehozása és a feltételes hozzáférés konfigurálása előtt elvégezni. Ez biztosítja, hogy az alkalmazás elérhető és készen áll a végfelhasználók általi telepítésre még azelőtt, hogy hozzáférhetnének a levelezéshez és más vállalati erőforrásokhoz.
## <a name="next-steps"></a>További lépések
[A Lookout for Work alkalmazás konfigurálása](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO2-->



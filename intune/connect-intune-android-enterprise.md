---
title: Az Intune-fiók csatlakoztatása a Vállalati Android-fiókjához
titlesuffix: Microsoft Intune
description: Útmutató Intune-fiók Vállalati Android-fiókhoz való csatlakoztatásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 698bc4e7e2d2cf8ece1b1c17b091a91c76a7d178
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/17/2019
ms.locfileid: "54386895"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Az Intune-fiók csatlakoztatása a Vállalati Android-fiókjához

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Támogatásához [Androidos munkahelyi profil](android-work-profile-enroll.md), [teljes körűen felügyelt Android](android-fully-managed-enroll.md), és [Android dedikált eszközök](android-kiosk-enroll.md), az Intune-bérlői fiók kapcsolódnia kell az Android enterprise fiók.  

> [!NOTE]
> A Google- és a Microsoft-tartományok közötti interakció miatt ennél a lépésnél előfordulhat, hogy módosítania kell a böngésző beállításait.  Ügyeljen rá, hogy a „portal.azure.com” és a „play.google.com” tartomány azonos biztonsági zónában legyen található a böngészőben.

1. Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** állítja be [mobileszköz-kezelői szolgáltatóként](mdm-authority-set.md).
2. Jelentkezzen be az [Azure Portalbeli Intune-ba](https://aka.ms/intuneportal), és válassza az **Eszközregisztráció** > **Android-regisztráció** > **Felügyelt Google Play** lehetőséget.  Ha egyéni Intune-rendszergazdai szerepkört használ, akkor ennek eléréséhez szervezeti olvasási és frissítési engedély szükséges.
   
   ![Vállalati Android regisztrációs képernyő](./media/android-work-bind.png)

3. Az **Elfogadom** lehetőség választásával engedélyezze a Microsoftnak a [felhasználó- és eszközadatok Google-nak való elküldését](data-intune-sends-to-google.md). 
   
4. Válassza a **Google elindítása az azonnali csatlakozáshoz** lehetőséget. Ezzel megnyitja a Felügyelt Google Play webhelyet. A webhely egy új lapon nyílik meg a böngészőben.
  
5. A Google bejelentkezési oldalán lépjen be az adott bérlő összes Vállalati Android-alapú felügyeleti feladatához társítandó Google-fiókkal. Ezt a Google-fiókot osztják meg a vállalati rendszergazdák az alkalmazások Google Play konzolon való felügyeletéhez és közzétételéhez. Meglévő Google-fiókot is használhat, illetve újat is létrehozhat. A választott fiók nem lehet G Suite-tartományhoz rendelve.
    
    > [!Note]
    > Ha a Microsoft Edge böngészőt használja, akkor a Google-fiókjába való bejelentkezéshez kattintson a jobb felső sarokban lévő **Bejelentkezés** lehetőségre.

6. Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a **Microsoft Intune** értéknek kell megjelennie.

7. Fogadja el az Android-szerződést, majd válassza a **Jóváhagyás** gombot. Megtörténik a kérelem feldolgozása.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Vállalati Andoid rendszergazdai fiók leválasztása

A Vállalati Android-regisztrációt és -felügyeletet ki is kapcsolhatja. Ehhez először szüntesse meg minden munkahelyi profilos, regisztrált Android-eszköz regisztrációját. Ezután az Intune felügyeleti konzolján a **Leválasztás** lehetőséget választva minden munkahelyi profilos, regisztrált Android-eszköz és kioszkeszköz regisztrációja megszűnik. Ezzel megszűnik a vállalati Android-fiók és az Intune közötti kapcsolat is.

1. Az Intune rendszergazdájaként az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** > **Figyelés + felügyelet** > **Intune** elemet.
2. Válassza az **Eszközregisztráció** > **Android-regisztráció** > **Felügyelt Google Play** > **Leválasztás** lehetőséget.
3. Válassza az **Igen** választ az összes vállalati androidos eszköz leválasztásához és az Intune-beli regisztrációjuk megszüntetéséhez.

## <a name="next-steps"></a>További lépések

A Vállalati Android-fiókhoz való csatlakozás után [beállíthatja az androidos munkahelyi profilos eszközöket](android-work-profile-enroll.md) és [beállíthatja az androidos kioszkeszközöket](android-kiosk-enroll.md).

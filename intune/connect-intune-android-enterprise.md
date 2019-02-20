---
title: Az Intune-fiók csatlakozhat a felügyelt Google Play-fiókjához.
titlesuffix: Microsoft Intune
description: Ismerje meg, hogyan csatlakozhat a felügyelt Google Play fiókot az Intune-fiók.
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a886359c9a7d789b06851cde7a5c1857b6fd282
ms.sourcegitcommit: 67e4e66e8c05b36c0897fb2955ef68666d22b094
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2019
ms.locfileid: "56427011"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Intune-fiókjához csatlakozhat a felügyelt Google Play-fiók

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Támogatásához [Android Enterprise munkahelyi profil](android-work-profile-enroll.md), [teljes körűen felügyelt Android Enterprise](android-fully-managed-enroll.md), és [Android Enterprise dedikált eszközök](android-kiosk-enroll.md), csatlakoznia kell az Intune-bérlő a fiók a felügyelt Google Play-fiókjába.  

> [!NOTE]
> A Google- és a Microsoft-tartományok közötti interakció miatt ennél a lépésnél előfordulhat, hogy módosítania kell a böngésző beállításait.  Ügyeljen rá, hogy a „portal.azure.com” és a „play.google.com” tartomány azonos biztonsági zónában legyen található a böngészőben.

1. Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** állítja be [mobileszköz-kezelői szolgáltatóként](mdm-authority-set.md).
2. Jelentkezzen be az [Azure Portalbeli Intune-ba](https://aka.ms/intuneportal), és válassza az **Eszközregisztráció** > **Android-regisztráció** > **Felügyelt Google Play** lehetőséget.  Ha egyéni Intune-rendszergazdai szerepkört használ, akkor ennek eléréséhez szervezeti olvasási és frissítési engedély szükséges.
   
   ![Vállalati Android regisztrációs képernyő](./media/android-work-bind.png)

3. Az **Elfogadom** lehetőség választásával engedélyezze a Microsoftnak a [felhasználó- és eszközadatok Google-nak való elküldését](data-intune-sends-to-google.md). 
   
4. Válassza a **Google elindítása az azonnali csatlakozáshoz** lehetőséget. Ezzel megnyitja a Felügyelt Google Play webhelyet. A webhely egy új lapon nyílik meg a böngészőben.
  
5. A Google bejelentkezési oldalán, adja meg a Google-fiókkal, amely a bérlő összes Android Enterprise felügyeleti feladatot társítva lesz. Ezt a Google-fiókot osztják meg a vállalati rendszergazdák az alkalmazások Google Play konzolon való felügyeletéhez és közzétételéhez. Meglévő Google-fiókot is használhat, illetve újat is létrehozhat. A választott fiók nem lehet G Suite-tartományhoz rendelve.
    
    > [!Note]
    > Ha a Microsoft Edge böngészőt használja, akkor a Google-fiókjába való bejelentkezéshez kattintson a jobb felső sarokban lévő **Bejelentkezés** lehetőségre.

6. Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a **Microsoft Intune** értéknek kell megjelennie.

7. Fogadja el az Android-szerződést, majd válassza a **Jóváhagyás** gombot. Megtörténik a kérelem feldolgozása.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Az Android vállalati rendszergazdai fiók leválasztása

Az Android vállalati regisztrációjának és felügyeleti kikapcsolhatja. Ehhez először vonja ki minden regisztrált nagyvállalati Android munkahelyi profilos eszközök. Ezután válassza ki **Disconnect** a az Intune felügyeleti konzol használatával távolítsa el az összes regisztrált vállalati Android munkahelyi profilos eszközök és a dedikált eszközök regisztrációját. Ez is eltávolítja a felügyelt Google Play-fiók és az Intune közötti kapcsolatot.

1. Az Intune rendszergazdájaként az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** > **Figyelés + felügyelet** > **Intune** elemet.
2. Válassza az **Eszközregisztráció** > **Android-regisztráció** > **Felügyelt Google Play** > **Leválasztás** lehetőséget.
3. Válassza az **Igen** választ az összes vállalati androidos eszköz leválasztásához és az Intune-beli regisztrációjuk megszüntetéséhez.

## <a name="next-steps"></a>További lépések

Miután csatlakozott a felügyelt Google Play-fiókba, akkor is [állítsa be a vállalati Android munkahelyi profilos eszközök](android-work-profile-enroll.md) és [dedikált vállalati Android-eszköz beállítása](android-kiosk-enroll.md).

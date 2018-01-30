---
title: "Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására"
titlesuffix: Azure portal
description: "Mobilalkalmazás-kezelési (MAM) szolgáltató beállítása az Azure AD-ban"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3254adc66c5fd5dc991364c3a33aabef8ac2030b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows 10-es rendszerhez mobilalkalmazás-kezelést (MAM) úgy engedélyezhet, hogy beállítja a MAM-szolgáltatót az Azure AD-ban. A MAM-szolgáltató Azure AD-n belüli beállításával meghatározhatja a regisztráció állapotát, amikor az Intune-ban új Windows Information Protection- (WIP-) szabályzatot hoz létre. A regisztráció állapota lehet MAM vagy mobileszköz-kezelés (MDM).

> [!NOTE]
> A MAM által regisztrált állapotú eszközöknek csatlakoztatva kell lenniük az Azure AD-hez.

## <a name="to-configure-the-mam-provider"></a>MAM-szolgáltató konfigurálása

1. Jelentkezzen be az Azure Portalon, majd válassza az **Azure Active Directory** elemet.

2. A **Kezelés** csoportban válassza a **Mobilitás (MDM és MAM)** elemet.

3. Kattintson a **Microsoft Intune** elemre.

4. A **Konfigurálás** panel **Alapértelmezett MAM URL-címek** csoportjában végezze el a konfigurációs beállításokat.

    **MAM-felhasználói hatókör**  
      Az automatikus MAM-regisztrációval a felhasználók Windows-eszközein található vállalati adatok kezelhetők. Az automatikus MAM-regisztráció a saját eszközök használatának esetén lesz konfigurálva.<ul><li>**Nincsenek**<br>Ezt akkor válassza, ha minden felhasználó regisztrálható a MAM-ban.</li><li>**Néhány**<br>Kiválaszthatja azokat az Azure AD-csoportokat, amelyekbe a MAM-ban regisztrálandó felhasználók tartoznak.</li><li>**Összes**<br>Ezt akkor válassza, ha minden felhasználó regisztrálható a MAM-ban.</li></ul>

    **A MAM használati feltételeinek URL-címe**  
     A MAM-szolgáltatás használati feltételeire mutató URL-cím. Ezt a címet használhatja arra, hogy a felhasználók számára még az eszköz regisztrálása előtt megjeleníthesse a szolgáltatásra vonatkozó használati feltételeket. A használati feltételekben a felhasználók tájékozódhatnak arról, hogy milyen szabályzatok vonatkoznak majd a mobileszközükre.

    **MDM-felderítési URL-cím**  
    A MAM-szolgáltatás regisztrálásra mutató URL-címe. A regisztrálási cím az eszközök MAM-szolgáltatásban történő regisztrálásához használatos.

    **A MAM megfelelőségi URL-címe**  
      A MAM-szolgáltatás megfelelőségi információkra mutató URL-címe. Ha a felhasználó nem megfelelő eszközről próbál erőforrást elérni, és a hozzáférését megtagadja a rendszer, a megfelelőséggel kapcsolatos információra mutató URL-cím jelenik meg számára. A felhasználók ezen a MAM által üzemeltetett URL-címen információt kaphatnak arról, hogy miért nem megfelelő az eszközük. Ezen kívül az eszköz megfelelővé tételének érdekében önkiszolgáló hibaelhárítást is elindíthatnak, hogy a kívánt erőforráshoz hozzá tudjanak férni.

5.  Kattintson a **Mentés**gombra.

## <a name="next-steps"></a>További lépések

[Alkalmazásvédelmi WIP-szabályzatok létrehozása](windows-information-protection-policy-create.md)

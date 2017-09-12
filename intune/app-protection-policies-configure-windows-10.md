---
title: "Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására"
titlesuffix: Azure portal
description: "Mobilalkalmazás-kezelési (MAM) szolgáltató beállítása az Azure AD-ban"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 52b273532935184918e65d25a37ca3d03e76680c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mielőtt Windows 10-es alkalmazásvédelmi szabályzatot hozhatna létre, az Azure AD-ben a MAM-szolgáltató beállításával engedélyeznie kell a Windows 10-es mobilalkalmazás-kezelést (MAM). Ezzel a beállítással meghatározhatja a regisztráció állapotát, amikor az Intune-ban új Windows Information Protection- (WIP-) szabályzatot hoz létre.

> [!NOTE]
> A regisztráció állapota lehet MAM vagy mobileszköz-kezelés (MDM).

## <a name="to-configure-the-mam-provider"></a>MAM-szolgáltató konfigurálása

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be Intune-os hitelesítő adataival.

2.  A baloldali menüben válassza az **Azure Active Directory** elemet.

    ![MAM-szolgáltató konfigurálása](./media/mam-provider-sc-1.png)

3.  A megnyíló **Azure AD** panelen válassza a **Mobilitás (MDM és MAM)** lehetőséget, majd kattintson a **Microsoft Intune** elemre.

    ![Mobilitás: MDM és MAM](./media/mam-provider-sc-1.png)

4.  A megnyíló konfigurációs panelen először válassza a **Alapértelmezett MAM URL-címeinek visszaállítása** elemet, majd végezze el az alábbi beállításokat:

    a.  MAM felhasználói hatókör: a MAM használatával a vállalati adatokat védheti egy meghatározott, Windows 10-es eszközöket használó felhasználói csoport vagy az összes felhasználó célzásával is.

    b.  A MAM használati feltételeinek URL-címe: a MAM-szolgáltatás használati feltételeire mutató URL-cím. A végfelhasználók itt férhetnek hozzá a MAM-szolgáltatás használati feltételeihez.

    c.  A MAM felderítési URL-címe: az eszközök ezt az URL-címet keresik, amikor alkalmazásvédelmi szabályzatokat kell alkalmazniuk.

    d.  A MAM megfelelőségi URL-címe:

5.  Ha a beállításokkal végzett, válassza a **Mentés** elemet.

## <a name="next-steps"></a>További lépések

[Alkalmazásvédelmi WIP-szabályzatok létrehozása](windows-information-protection-policy-create.md)

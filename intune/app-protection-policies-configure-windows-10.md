---
title: "Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására"
titleSuffix: Intune on Azure
description: "Mobilalkalmazás-kezelési (MAM) szolgáltató beállítása az Azure AD-ban"
keywords: 
author: andredm7
ms.author: andredm
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
ms.openlocfilehash: bf56d3a80f0d167baa95e9dfdb20d08e02590984
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
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
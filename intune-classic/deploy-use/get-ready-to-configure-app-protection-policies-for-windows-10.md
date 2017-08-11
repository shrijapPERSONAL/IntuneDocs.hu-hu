---
title: "Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására"
description: "Mobilalkalmazás-kezelési (MAM) szolgáltató beállítása az Azure AD-ban"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4c410913adb32a5957552e453b49de9c7cda097
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Felkészülés az alkalmazásvédelmi szabályzatok Windows 10 rendszereken történő konfigurálására

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Mielőtt Windows 10-es alkalmazásvédelmi szabályzatot hozhatna létre, az Azure AD-ben a MAM-szolgáltató beállításával engedélyeznie kell a Windows 10-es mobilalkalmazás-kezelést (MAM). Ezzel a beállítással meghatározhatja a regisztráció állapotát, amikor az Intune-ban új Windows Information Protection- (WIP-) szabályzatot hoz létre.

> [!NOTE]
> A regisztráció állapota lehet MAM vagy mobileszköz-kezelés (MDM).

## <a name="to-configure-the-mam-provider"></a>MAM-szolgáltató konfigurálása

1.  Az [Azure Portalon](https://portal.azure.com/) jelentkezzen be Intune-os hitelesítő adataival.

2.  A baloldali menüben válassza az **Azure Active Directory** elemet.

    ![MAM-szolgáltató konfigurálása](../media/AppManagement/mam-provider-sc-1.png)

3.  A megnyíló **Azure AD** panelen válassza a **Mobilitás (MDM és MAM)** lehetőséget, majd kattintson a **Microsoft Intune** elemre.

    ![Mobilitás: MDM és MAM](../media/AppManagement/mam-provider-sc-2.png)

4.  A megnyíló konfigurációs panelen először válassza a **Alapértelmezett MAM URL-címeinek visszaállítása** elemet, majd végezze el az alábbi beállításokat:

    a.  MAM felhasználói hatókör: a MAM használatával a vállalati adatokat védheti egy meghatározott, Windows 10-es eszközöket használó felhasználói csoport vagy az összes felhasználó célzásával is.

    b.  A MAM használati feltételeinek URL-címe: a MAM-szolgáltatás használati feltételeire mutató URL-cím. A végfelhasználók itt férhetnek hozzá a MAM-szolgáltatás használati feltételeihez.

    c.  A MAM felderítési URL-címe: az eszközök ezt az URL-címet keresik, amikor alkalmazásvédelmi szabályzatokat kell alkalmazniuk.

    d.  A MAM megfelelőségi URL-címe:

5.  Ha a beállításokkal végzett, válassza a **Mentés** elemet.

## <a name="next-steps"></a>További lépések

[Alkalmazásvédelmi WIP-szabályzatok létrehozása](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)

---
title: "Azure-portál a mobilalkalmazás-felügyeleti szabályzatok kezeléséhez"
description: "Hozzon létre mobilalkalmazás-felügyeleti szabályzatokat az Azure-portál segítségével. Az itt létrehozott szabályzatok az Intune-ban regisztrált és nem regisztrált eszközökre is alkalmazhatók."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0a5ac03ca213f18d9e0403a10cdf9f9cde721f02
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="azure-portal-for-intune-app-protection-policies"></a>Alkalmazásvédelmi szabályzatok az Azure Portalon

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Azure Portalon a következőkre vonatkozó alkalmazásvédelmi szabályzatokat hozhat létre és kezelhet:

- Az **Intune-ban regisztrált és általa kezelt** eszközökön futó alkalmazások.

- Semmilyen MDM-megoldásban **nem regisztrált** eszközökön futó alkalmazások.
- **Harmadik féltől származó MDM-megoldásban regisztrált** eszközökön futó alkalmazások.

>[!IMPORTANT]
> Az Azure Portal az új felügyeleti konzol az alkalmazásvédelmi szabályzatok létrehozására. Az Intune-ban regisztrált eszközök alkalmazásait támogató alkalmazásvédelmi szabályzatokat is létrehozhat azonban, ha az [Intune felügyeleti konzolt](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) használja a mobileszközök kezelésének bizonyos eseteire.

> Előfordulhat, hogy az Intune felügyeleti konzolon nem jelenik az alkalmazásvédelmi szabályzatok minden beállítása. Emellett ha az Intune felügyeleti konzolon és az Azure Portalon is hoz létre alkalmazásvédelmi szabályzatokat, az Azure Portalon létrehozott szabályzatok felülbírálják az Intune felügyeleti konzolon létrehozottakat. Ebben az esetben a rendszer az Azure Portal alkalmazásvédelmi szabályzatait érvényesíti az alkalmazásokra, illetve telepíti a felhasználók számára.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Bejelentkezés az Azure-portálra és a kezdőlap testreszabása

1.  Az [Azure Portalon](https://portal.azure.com) jelentkezzen be Intune-os hitelesítő adataival.

    ![Az Azure-portál bejelentkezési oldalának képernyőképe](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Miután sikeresen bejelentkezett, megjelenik az **Irányítópult**. Az **Irányítópult** oldal testreszabható.

    ![Az Azure-portál irányítópultjának képernyőképe](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

    ![A Tallózás menü képernyőképe az Intune kiemelésével](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Válassza az **Intune App Protection** > **Intune mobilalkalmazás-kezelés** > **Minden beállítás** elemet.

    ![Az Intune mobilalkalmazás-felügyelet panel képernyőfelvétele](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Nem kötelező): Ha rögzíteni szeretne egy panelt a **kezdőlapon**, válassza a **Rögzítés** lehetőséget a panelen. Az **Intune mobilalkalmazás-felügyelet** panelt a rögzítési ikonjára kattintva rögzítheti a **kezdőlapon**.

    ![Az Intune mobilalkalmazás-felügyeleti paneljének képernyőképe, a rögzítés ikonja kiemelve](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Az irányítópult és a rögzített Intune csempe képernyőképe](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>További lépések
[Felkészülés az alkalmazásvédelmi szabályzatok konfigurálására](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

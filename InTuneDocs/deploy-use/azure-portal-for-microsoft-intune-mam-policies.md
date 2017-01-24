---
title: "Azure-portál a mobilalkalmazás-felügyeleti szabályzatok kezeléséhez | Microsoft Docs"
description: "Hozzon létre mobilalkalmazás-felügyeleti szabályzatokat az Azure-portál segítségével. Az itt létrehozott szabályzatok az Intune-ban regisztrált és nem regisztrált eszközökre is alkalmazhatók."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Azure-portál a Microsoft Intune mobilalkalmazás-felügyeleti szabályzatainak kezeléséhez

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Azure Portal webhelyen a következőkre vonatkozó mobilalkalmazás-felügyeleti (MAM) szabályzatokat hozhat létre és kezelhet:

- Az **Intune-ban regisztrált és általa kezelt** eszközökön futó alkalmazások.

- Semmilyen MDM-megoldásban **nem regisztrált** eszközökön futó alkalmazások.
- **Harmadik féltől származó MDM-megoldásban regisztrált** eszközökön futó alkalmazások.

>[!IMPORTANT]
> Az Azure Portal az új felügyeleti konzol a MAM-szabályzatok létrehozásához, de az Intune-ban regisztrált eszközök alkalmazásait támogató MAM-szabályzatokat is létrehozhat, ha az [Intune felügyeleti konzolt](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) használja a mobileszköz-kezelési forgatókönyvekhez.

> Előfordulhat, hogy az Intune felügyeleti konzolon nem jelenik meg minden elérhető MAM-szabályzatbeállítás. Emellett ha az Intune felügyeleti konzolon és az Azure Portal webhelyen is hoz létre MAM-szabályzatokat, az Azure Portal webhelyen létrehozott szabályzatok felülbírálják az Intune felügyeleti konzolon létrehozottakat. Ebben az esetben a rendszer az Azure Portal MAM-szabályzatait alkalmazza az alkalmazásokra és telepíti a felhasználók számára.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Bejelentkezés az Azure-portálra és a kezdőlap testreszabása

1.  Az [Azure-portálon](https://portal.azure.com) jelentkezzen be [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-os hitelesítő adataival.

    ![Az Azure-portál bejelentkezési oldalának képernyőképe](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Miután sikeresen bejelentkezett, megjelenik az **Irányítópult**. Az **Irányítópult** oldal testreszabható.

    ![Az Azure-portál irányítópultjának képernyőképe](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Válassza a **Tallózás** menü **Intune** elemét.

    ![A Tallózás menü képernyőképe az Intune kiemelésével](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Válassza az **Intune** > **Intune mobilalkalmazás-kezelés** > **Beállítások** elemet.

    ![Az Intune mobilalkalmazás-felügyelet panel képernyőfelvétele](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Nem kötelező): Ha rögzíteni szeretne egy panelt a **kezdőlapon**, válassza a **Rögzítés** lehetőséget a panelen. Az **Intune mobilalkalmazás-felügyelet** panelt a rögzítési ikonjára kattintva rögzítheti a **kezdőlapon**.

    ![Az Intune mobilalkalmazás-felügyeleti paneljének képernyőképe, a rögzítés ikonja kiemelve](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Az irányítópult és a rögzített Intune csempe képernyőképe](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>További lépések
[Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->



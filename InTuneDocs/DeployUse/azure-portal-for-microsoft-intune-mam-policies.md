---
title: "Azure-portál a mobilalkalmazás-felügyeleti szabályzatok kezeléséhez | Microsoft Intune"
description: "Hozzon létre mobilalkalmazás-felügyeleti szabályzatokat az Azure portál segítségével. Az itt létrehozott szabályzatok az Intune-ban regisztrált és nem regisztrált eszközökre is alkalmazhatók."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 1ddb7a30a6f23a3f3d754bd18975c50f32662578


---

# Azure-portál a Microsoft Intune mobilalkalmazás-felügyeleti szabályzatainak kezeléséhez
## Az Azure-portál elérése
Az **Azure-portálon** lehetősége van mobilalkalmazás-felügyeleti szabályzatok létrehozására és kezelésére.

Az Azure-portálon az alábbiakhoz támogatott a MAM-szabályzatok létrehozása:
- Az **Intune-ban regisztrált és általa kezelt** eszközökön futó alkalmazások.
- Semmilyen MDM-megoldásban **nem regisztrált** eszközökön futó alkalmazások.
- **Harmadik féltől származó MDM-megoldásban regisztrált** eszközökön futó alkalmazások.

>[!IMPORTANT]

> Ha jelenleg az Intune felügyeleti konzolját használja eszközei kezelésére, az [Intune felügyeleti konzol](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) segítségével létrehozhat egy olyan MAM-szabályzatot, amely az Intune-ban regisztrált eszközökön futó alkalmazásokat támogatja.

> Előfordulhat, hogy az Intune felügyeleti konzolon nem lát minden MAM-szabályzatbeállítást. A MAM-szabályzatok létrehozására szolgáló új felügyeleti konzol az Azure-portál. Ha mind az Intune felügyeleti konzoljában, mind az Azure-portálon létrehoz MAM-szabályzatokat, a rendszer az Azure-portálon érvényes szabályzatot alkalmazza az alkalmazásokra, illetve telepíti a felhasználók számára.

## Bejelentkezés az Azure-portálra és a kezdőlap testreszabása

1.  Az [Azure-portálon](https://portal.azure.com) jelentkezzen be [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-os hitelesítő adataival.

    ![Az Azure-portál bejelentkezési oldalának képernyőképe](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Miután sikeresen bejelentkezett, megjelenik az **Irányítópult**. Az **Irányítópult** oldal testreszabható.

    ![Az Azure-portál irányítópultjának képernyőképe](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  A **Tallózás** menüben keresse meg az **Intune** elemet.![A Tallózás menü képernyőképe az Intune kiemelésével](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Válassza az **Intune > Intune mobilalkalmazás-kezelés > Beállítások** elemet.

    ![Az Intune mobilalkalmazás-felügyelet panel képernyőfelvétele](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Ha rögzíteni szeretne egy panelt a **kezdőlapon** , válassza a **Rögzítés** lehetőséget a panelen.  Az **Intune-alapú mobilalkalmazás-felügyelet**panelt a rögzítés ikonjára kattintva rögzítheti a **kezdőlapon** .

    ![Az Intune mobilalkalmazás-felügyeleti paneljének képernyőképe, a rögzítés ikonja kiemelve](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Az irányítópult és a rögzített Intune csempe képernyőképe](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## További lépések
[Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->



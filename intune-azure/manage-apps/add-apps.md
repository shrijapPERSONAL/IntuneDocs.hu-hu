---
title: "Alkalmazások hozzáadása a Microsoft Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Ezekkel az eljárásokkal felveheti az alkalmazásokat az Intune-ba, hogy készen álljanak a felhasználókhoz és eszközökhöz való hozzárendelésre. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Alkalmazás hozzáadása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse az alkalmazásokat, előbb hozzá kell adnia őket az Intune-hoz. Az Intune sokféle alkalmazástípust támogat, ezek beállításai eltérőek lehetnek.

Az Intune a következő típusú alkalmazások hozzáadását és hozzárendelését támogatja:

![Az Intune által támogatott alkalmazástípusok](./media/app-types.png)

A támogatott platformok közé a következők tartoznak. További tájékoztatásért kattintson kívánt alkalmazástípus témakörére.

- [Androidos üzletági alkalmazások](/intune-azure/manage-apps/android-lob-app)
- [Androidos áruházbeli alkalmazások](/intune-azure/manage-apps/android-store-app)
- [iOS rendszerhez készült üzletági alkalmazások](/intune-azure/manage-apps/ios-lob-app)
- [iOS rendszerhez készült áruházbeli alkalmazások](/intune-azure/manage-apps/ios-store-app)
- [Webalkalmazások (az összes platformra)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1-es áruházbeli alkalmazások](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Áruházbeli alkalmazások](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Amikor egy áruházból ad hozzá és telepít egy alkalmazást, a végfelhasználóknak rendelkezniük kell egy fiókkal az adott áruházban, hogy telepíteni tudják az alkalmazást.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Alkalmazáskategóriák létrehozása és szerkesztése 

Az alkalmazáskategóriák segítségével rendszerezheti az alkalmazásokat, hogy a végfelhasználók könnyebben találják meg őket a munkahelyi portálon. Egy alkalmazáshoz több kategóriát is hozzárendelhet (például **Fejlesztői alkalmazások** és **Kommunikációs alkalmazások**). Amikor hozzáad egy alkalmazást az Intune-hoz, kiválaszthatja a kívánt kategóriát. Az alkalmazások felvételéről és a kategóriák hozzárendeléséről az egyes platformokra vonatkozó témakörökből tájékozódhat. Saját kategóriáit a következő eljárással hozhatja létre és szerkesztheti: 

1. Jelentkezzen be az Azure Portalra. 
2. Válassza a **További szolgáltatások** > **Figyelés + Felügyelet** > **Intune** lehetőséget. 
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget. 
4. A **Mobilalkalmazások** területen válassza a **Beállítás** > **	Alkalmazáskategóriák** elemet. 
5. Az **Alkalmazáskategóriák** panelen látható az aktuális kategóriák listája. Válasszon a következő lehetőségek közül: 
    - **Új kategória létrehozása** – Adja meg az új kategória nevét a **Create category** (Kategória létrehozása) panelen. A neveket csak egy nyelven lehet megadni, és az Intune nem fordítja le őket. Ha végzett, kattintson a **Létrehozás** gombra.
    - **Kategória szerkesztése** – Bármelyik, a listán szereplő kategóriánál válassza a **...** elemet. A **Tulajdonságok** panelen átnevezheti a kategóriát, illetve törölheti a kategóriát. --->






<!--HONumber=Feb17_HO1-->



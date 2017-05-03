---
title: "Alkalmazások hozzáadása a Microsoft Intune-hoz"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Ezekkel az eljárásokkal felveheti az alkalmazásokat az Intune-ba, hogy készen álljanak a felhasználókhoz és eszközökhöz való hozzárendelésre. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d85544bdfaa3a369e1d2d03e5454ff7aa2d75467
ms.lasthandoff: 04/19/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Alkalmazás hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse az alkalmazásokat, előbb hozzá kell adnia őket az Intune-hoz. Az Intune sokféle alkalmazástípust támogat, ezek beállításai eltérőek lehetnek.

Az Intune a következő típusú alkalmazások hozzáadását és hozzárendelését teszi lehetővé:

![Az Intune által támogatott alkalmazástípusok](./media/app-types.png)

A támogatott platformok közé a következők tartoznak. További tájékoztatásért kattintson kívánt alkalmazástípus témakörére.

- [Androidos áruházbeli alkalmazások](/intune-azure/manage-apps/android-store-app)
- [Androidos üzletági alkalmazások](/intune-azure/manage-apps/android-lob-app)
- [iOS rendszerhez készült áruházbeli alkalmazások](/intune-azure/manage-apps/ios-store-app)
- [iOS-es üzletági alkalmazások](/intune-azure/manage-apps/ios-lob-app)
- [Webalkalmazások (az összes platformra)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1-es áruházbeli alkalmazások](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Áruházbeli alkalmazások](/intune-azure/manage-apps/windows-store-app)

Ezen kívül a bérlő beállításakor néhány Microsoft-alkalmazás is automatikusan hozzá lesz adva. Ezek listáját a jelen témakör későbbi részeiben láthatja.

## <a name="before-you-start"></a>Előkészületek

Mielőtt elkezdené az alkalmazások hozzáadását és hozzárendelését, vegye figyelembe a következőket.

- Amikor egy áruházból ad hozzá és telepít egy alkalmazást, a végfelhasználóknak rendelkezniük kell egy fiókkal az adott áruházban, hogy telepíteni tudják az alkalmazást.
- Előfordulhat, hogy egyes üzembe helyezendő alkalmazások beépített iOS-alkalmazásoktól függenek. Ha például könyvet telepít az iOS-es áruházból, akkor az eszközön elérhetőnek kell lennie az iBooks alkalmazásnak. Ha eltávolította a beépített iBooks alkalmazást, azt az Intune használatával nem tudja újratelepíteni.

## <a name="cloud-storage-space"></a>Felhőtárhely
A szoftvertelepítő típusú telepítéssel létrehozott összes alkalmazást (például az üzletági alkalmazásokat) a rendszer becsomagolja és feltölti a Microsoft Intune felhőtárhelyére. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A teljes előfizetése 20 GB tárterületet tartalmaz.

Az eredeti vásárlási móddal vásárolhat további tárterületet az Intune számára.  Ha számla ellenében vagy hitelkártyával fizetett, keresse fel az [Előfizetés-kezelési portált](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Más esetben forduljon vállalatának partnercégéhez vagy értékesítési kapcsolattartójához.

A felhőtárhelyre vonatkozó követelmények az alábbiak:

-   Az összes alkalmazás telepítési fájljainak ugyanabban a mappában kell lenniük.
-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Alkalmazáskategóriák létrehozása és szerkesztése

Az alkalmazáskategóriák segítségével rendszerezheti az alkalmazásokat, hogy a végfelhasználók könnyebben találják meg őket a munkahelyi portálon. Egy alkalmazáshoz több kategóriát is hozzárendelhet (például **Fejlesztői alkalmazások** és **Kommunikációs alkalmazások**).
Amikor hozzáad egy alkalmazást az Intune-hoz, kiválaszthatja a kívánt kategóriát. Az alkalmazások felvételéről és a kategóriák hozzárendeléséről az egyes platformokra vonatkozó témakörökből tájékozódhat. Saját kategóriáit a következő eljárással hozhatja létre és szerkesztheti:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Beállítás** > **	Alkalmazáskategóriák** elemet.
5. Az **Alkalmazáskategóriák** panelen látható az aktuális kategóriák listája. Válasszon a következő lehetőségek közül:
    - **Új kategória létrehozása** – Adja meg az új kategória nevét a **Create category** (Kategória létrehozása) panelen. A neveket csak egy nyelven lehet megadni, és az Intune nem fordítja le őket. Ha végzett, kattintson a **Létrehozás** gombra.
    - **Kategória szerkesztése** – Bármelyik, a listán szereplő kategóriánál válassza a **...** elemet. A **Tulajdonságok** panelen átnevezheti a kategóriát, illetve törölheti a kategóriát.


## <a name="apps-added-automatically-by-intune"></a>Az Intune által automatikusan hozzáadott alkalmazások

Az alábbi Microsoft-alkalmazások beépítve rendelkezésre állnak, és hozzárendelhetők az Intune-ban:

|||
|-|-|
|Név|Platform|Alkalmazás típusa|
|Azure Information Protection|Android|Felügyelt Android Áruházbeli alkalmazás|
|Dynamics CRM telefonokhoz|Android|Felügyelt Android Áruházbeli alkalmazás|
|Dynamics CRM táblagépekhez|Android|Felügyelt Android Áruházbeli alkalmazás|
|Excel|iOS|Felügyelt iOS Store-alkalmazás|
|Excel|Android|Felügyelt Android Áruházbeli alkalmazás|
|Felügyelt böngésző|Android|Felügyelt Android Áruházbeli alkalmazás|
|Felügyelt böngésző|iOS|Felügyelt iOS Store-alkalmazás|
|Microsoft Dynamics CRM telefonokon|iOS|Felügyelt iOS Store-alkalmazás|
|Microsoft Dynamics CRM táblagépeken|iOS|Felügyelt iOS Store-alkalmazás|
|Microsoft Power BI|iOS|Felügyelt iOS Store-alkalmazás|
|Microsoft Power BI|Android|Felügyelt Android Áruházbeli alkalmazás|
|Microsoft SharePoint|iOS|Felügyelt iOS Store-alkalmazás|
|Microsoft SharePoint|Android|Felügyelt Android Áruházbeli alkalmazás|
|Microsoft Teams|Android|Felügyelt Android Áruházbeli alkalmazás|
|Microsoft Teams|iOS|Felügyelt iOS Store-alkalmazás|
|OneDrive|iOS|Felügyelt iOS Store-alkalmazás|
|OneDrive|Android|Felügyelt Android Áruházbeli alkalmazás|
|OneNote|iOS|Felügyelt iOS Store-alkalmazás|
|Outlook|Android|Felügyelt Android Áruházbeli alkalmazás|
|Outlook|iOS|Felügyelt iOS Store-alkalmazás|
|Outlook Groups|Android|Felügyelt Android Áruházbeli alkalmazás|
|Outlook Groups|iOS|Felügyelt iOS Store-alkalmazás|
|PowerPoint|iOS|Felügyelt iOS Store-alkalmazás|


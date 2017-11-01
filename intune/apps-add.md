---
title: "Alkalmazások hozzáadása a Microsoft Intune-hoz"
titlesuffix: Azure portal
description: "Ezekkel az eljárásokkal felveheti az alkalmazásokat az Intune-ba, hogy készen álljanak a felhasználókhoz és eszközökhöz való hozzárendelésre. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 108f789f16304498cf54387326d112353bf70aa2
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Alkalmazás hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse az alkalmazásokat, előbb hozzá kell adnia őket az Intune-hoz. Az Intune sokféle alkalmazástípust támogat, ezek beállításai eltérőek lehetnek.

Az Intune a következő típusú alkalmazások hozzáadását és hozzárendelését teszi lehetővé:

![Az Intune által támogatott alkalmazástípusok](./media/app-types.png)

A támogatott platformok közé a következők tartoznak.

- Androidos áruházbeli alkalmazások
- Androidos üzletági (LOB) alkalmazások
- iOS-es áruházbeli alkalmazások
- iOS-es üzletági (LOB) alkalmazások
- Webalkalmazások
- Windows Phone 8.1-es áruházbeli alkalmazások
- Windows Phone rendszerű üzletági alkalmazások (.xap fájlok)
- Windows Áruházbeli alkalmazások
- Windows rendszerű üzletági alkalmazások (csak .msi fájlok)

>[!TIP]
> Az üzletági alkalmazásokat nem alkalmazás-áruházból, hanem telepítőfájlból lehet telepíteni. iOS-es üzletági alkalmazás telepítéséhez például az (.ipa kiterjesztésű) alkalmazásarchívum-fájlt kell megadni. Ezek jellemzően házon belül készült alkalmazások.

## <a name="before-you-start"></a>Előkészületek

Mielőtt elkezdené az alkalmazások hozzáadását és hozzárendelését, vegye figyelembe a következőket.

- Ha áruházból végzi az alkalmazások felvételét és hozzárendelését, a végfelhasználók csak akkor tudják telepíteni az alkalmazásokat, ha rendelkeznek fiókkal az adott áruházban.
- Előfordulhat, hogy egyes hozzárendelendő alkalmazások beépített iOS-alkalmazásoktól függenek. Ha például egy könyv iOS-es áruházból való hozzárendelését végzi, az eszközön elérhetőnek kell lennie az iBooks alkalmazásnak. Ha eltávolította a beépített iBooks alkalmazást, azt az Intune használatával nem tudja újratelepíteni.

## <a name="cloud-storage-space"></a>Felhőtárhely
A szoftvertelepítő típusú telepítéssel létrehozott összes alkalmazást (például az üzletági alkalmazásokat) a rendszer becsomagolja és feltölti az Intune felhőtárhelyére. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A teljes előfizetés 20 GB tárterületet tartalmaz.

Az eredeti vásárlási móddal vásárolhat további tárterületet az Intune számára.  Ha számla ellenében vagy hitelkártyával fizetett, keresse fel az [Előfizetés-kezelési portált](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Más esetben forduljon vállalatának partnercégéhez vagy értékesítési kapcsolattartójához.

A felhőtárhelyre vonatkozó követelmények az alábbiak:

-   Az összes alkalmazás telepítési fájljainak ugyanabban a mappában kell lenniük.
-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Alkalmazáskategóriák létrehozása és szerkesztése

Az alkalmazáskategóriák segítségével úgy rendezheti az alkalmazásokat, hogy a felhasználók könnyebben találják meg őket a céges portálon. Egy alkalmazáshoz több kategóriát is hozzárendelhet (például **Fejlesztői alkalmazások** és **Kommunikációs alkalmazások**).
Amikor hozzáad egy alkalmazást az Intune-hoz, kiválaszthatja a kívánt kategóriát. Az alkalmazások felvételéről és a kategóriák hozzárendeléséről az egyes platformokra vonatkozó témakörökből tájékozódhat. Saját kategóriáit a következő eljárással hozhatja létre és szerkesztheti:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Beállítás** > **Alkalmazáskategóriák** elemet.
5. Az **Alkalmazáskategóriák** panelen látható az aktuális kategóriák listája. Válasszon a következő lehetőségek közül:
    - **Új kategória létrehozása** – Adja meg az új kategória nevét a **Create category** (Kategória létrehozása) panelen. A neveket csak egy nyelven lehet megadni, és az Intune nem fordítja le őket. Ha végzett, kattintson a **Létrehozás** gombra.
    - **Kategória szerkesztése** – Bármelyik, a listán szereplő kategóriánál válassza a **...** elemet. A **Tulajdonságok** panelen átnevezheti a kategóriát, illetve törölheti a kategóriát.


## <a name="apps-added-automatically-by-intune"></a>Az Intune által automatikusan hozzáadott alkalmazások

Korábban az Intune számos beépített alkalmazást tartalmazott, melyeket hamar hozzá lehetett rendelni egy kategóriához. A visszajelzések alapján azonban eltávolítottuk ezt a listát, és többé már nem jelennek meg beépített alkalmazások.
Ugyanakkor ha vannak olyan beépített alkalmazások, melyeket korábban már hozzárendelt valamelyik kategóriához, azok továbbra is meg fognak jelenni az alkalmazások listáján. Ezek az alkalmazások szükség szerint továbbra is hozzárendelhetők.
Terveink szerint egy későbbi kiadásban elérhetővé teszünk majd egy egyszerűbb módszert a beépített alkalmazások Azure Portalról történő kiválasztására és hozzárendelésére.

## <a name="next-steps"></a>További lépések

Az alábbi témakörök ismertetik az egyes platformok alkalmazásainak felvételét az Intune-ba:

- [Androidos áruházbeli alkalmazások](store-apps-android.md)
- [Androidos üzletági alkalmazások](lob-apps-android.md)
- [iOS rendszerhez készült áruházbeli alkalmazások](store-apps-ios.md)
- [iOS-es üzletági alkalmazások](lob-apps-ios.md)
- [Webalkalmazások (az összes platformra)](web-app.md)
- [Windows Phone 8.1-es áruházbeli alkalmazások](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB-alkalmazások](lob-apps-windows-phone.md)
- [Windows Áruházbeli alkalmazások](store-apps-windows.md)
- [Windows LOB-alkalmazás](lob-apps-windows.md)
- [Windows 10-es Office 365-alkalmazások](apps-add-office365.md)


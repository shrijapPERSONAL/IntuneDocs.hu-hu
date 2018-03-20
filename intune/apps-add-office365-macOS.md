---
title: "Office 365 telepítése macOS-eszközökön a Microsoft Intune-nal"
titlesuffix: 
description: "Ismertető: hogyan telepítheti az Office 365-alkalmazásokat macOS-eszközökön a Microsoft Intune használatával."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Az Office 365 hozzárendelése macOS rendszerű eszközökhöz a Microsoft Intune-nal

Az **áruházbeli alkalmazástípussal** könnyedén hozzárendelheti az Office 365-alkalmazásokat a macOS rendszerű eszközökhöz. Ezzel a típussal a Word, az Excel, a PowerPoint, az Outlook és a OneNote alkalmazásokat telepítheti. Az alkalmazásokhoz a Microsoft automatikus frissítési (MAU) szolgáltatása is rendelkezésre áll, amely segít azokat biztonságosabban és naprakészebben tartani. A kívánt alkalmazások egyetlen alkalmazásként jelennek meg az Intune-konzol alkalmazáslistájában.


## <a name="before-you-start"></a>Előkészületek

Mielőtt elkezdené az Office 365 hozzáadását a macOS-eszközökhöz, érdemes figyelembe vennie az alábbiakat:

- Azokon az eszközökön, melyekre telepíti az alkalmazásokat, a macOS 10.10-es vagy újabb verziójának kell futnia.
- Az Intune csak a Mac Office 2016 csomagban megtalálható Office-alkalmazások hozzáadását támogatja.
- Ha bármely Office-alkalmazás meg van nyitva, amikor az Intune telepíti az alkalmazáscsomagot, előfordulhat, hogy elvesznek a végfelhasználók adatai a nem mentett fájlokból.

## <a name="create-and-configure-the-app-suite"></a>Az alkalmazáscsomag létrehozása és konfigurálása

Adja hozzá az Office 365-öt az **Alkalmazások** panelen.
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza az **Összes szolgáltatás** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen kattintson a **Mobilalkalmazások** elemre.
4. A **Mobilalkalmazások** területen a **Kezelés** csoportban válassza az **Alkalmazások** lehetőséget. 
5. Kattintson a **Hozzáadás** elemre az **Alkalmazás hozzáadása** panel megjelenítéséhez.
6. Az **Office 365 csomag** csoport **Alkalmazás típusa** listájáról válassza ki a **macOS** lehetőséget.
7. Az **Alkalmazáscsomag adatai** lehetőségre kattintva megtekintheti az alkalmazáscsomagra vonatkozó információkat. Ezek alapján azonosíthatja az alkalmazáscsomagot az Intune-ban, és a felhasználók is ezek alapján találhatják meg azt a Céges portál alkalmazásban.
8.  Adja meg a következő adatokat:
    - **Suite Name** (Csomag neve) – Itt adhatja meg az alkalmazáscsomag a céges portálon megjelenő nevét. Ügyeljen arra, hogy minden megadott csomagnév egyedi legyen. Ha ugyanazt a csomagnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Suite Description** (Csomag leírása) – Itt adhatja meg az alkalmazáscsomag leírását.
    - **Gyártó** – Gyártóként a Microsoft jelenik meg.
    - **Kategória** – Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ez a beállítás megkönnyíti a Céges portálon kereső felhasználóknak az alkalmazás megtalálását.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a Céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** (nem kötelező) – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe** (nem kötelező) – Itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő** – Fejlesztőként a Microsoft jelenik meg.
    - **Tulajdonos** – Tulajdonosként a Microsoft jelenik meg.
    - **Megjegyzések** (nem kötelező) – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Embléma** – Amikor a felhasználók a Céges portálon keresnek, az alkalmazás mellett megjelenik az Office 365-embléma.
9.  Az **Alkalmazásadatok** panelen kattintson az **OK** elemre.
10. Az **Alkalmazás hozzáadása** panelen kattintson a **Hozzáadás** elemre.
    A csomag egyetlen bejegyzés formájában jelenik meg az alkalmazások listájában.

## <a name="configure-app-assignments"></a>Alkalmazás-hozzárendelések konfigurálása

Ebben a lépésben az alkalmazáscsomag hozzárendeléseit konfigurálhatja. 

1. Az **Office 365** csomagot áttekintő panel megjelenítéséhez válassza az **Office 365** alkalmazáscsomagot az alkalmazások listáján.
2. Az **Office 365** panelen kattintson a **Hozzárendelések** elemre.
3. Az alkalmazáscsomagot használó csoport hozzáadásához kattintson a **Csoport hozzáadása** elemre. Ekkor megjelenik a **Csoport hozzáadása** panel.
3. A **Hozzárendelés típusát** állítsa **Kötelező** értékre.
4. Rendelje hozzá a csomagot a kívánt csoportokhoz. További információ: [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal).

    >[!Note]
    > Csoportok esetén nem távolíthatja el a számukra igényelt Office 365-alkalmazáscsomagot a Microsoft Intune használatával.

5. Kattintson az **OK** elemre a **Hozzárendelés** panelen.
6. Kattintson az **OK** elemre a **Csoport hozzáadása** panelen.
7. A hozzárendelés véglegesítéséhez válassza a **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések

- Az Office 365-alkalmazások Windows 10-es eszközökhöz való hozzáadásával kapcsolatos további tudnivalókért lásd: [Office 365 ProPlus 2016-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal](apps-add-office365.md).
- Felhasználói csoportok esetén az alkalmazás-hozzárendelések belefoglalásához és kizárásához az [Alkalmazás-hozzárendelések belefoglalása és kizárása](apps-inc-exl-assignments.md) részben talál további információkat.

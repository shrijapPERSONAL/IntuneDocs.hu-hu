---
title: "Az Office 365 telepítése macOS rendszerű eszközökre az Intune-nal"
titlesuffix: Azure portal
description: "Annak ismertetése, hogyan egyszerűsíthető az Office 365-alkalmazások macOS rendszerű eszközökre való telepítése az Intune használatával."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Az Office 365 hozzárendelése macOS rendszerű eszközökhöz a Microsoft Intune-nal

Ezzel az alkalmazástípussal könnyedén hozzárendelhet Office 365-alkalmazásokat macOS rendszerű eszközökhöz. Az új alkalmazástípussal telepítheti a Word, az Excel, a PowerPoint, az Outlook és a OneNote alkalmazást. Az alkalmazásokhoz a Microsoft automatikus frissítési (MAU) szolgáltatása is rendelkezésre áll, amely segít azokat biztonságosabban és naprakészebben tartani. A kívánt alkalmazások egyetlen alkalmazásként jelennek meg az Intune-konzol alkalmazáslistájában.


## <a name="before-you-start"></a>Előkészületek

- Azokon az eszközökön, melyekre telepíti az alkalmazásokat, a macOS 10.10-es vagy újabb verziójának kell futnia.
- Az Intune csak a Mac Office 2016 csomagban megtalálható Office-alkalmazások hozzáadását támogatja.
- Ha bármely Office-alkalmazás meg van nyitva, amikor az Intune telepíti az alkalmazáscsomagot, előfordulhat, hogy elvesznek a végfelhasználók adatai a nem mentett fájlokból.


## <a name="get-started"></a>Első lépések
Adja hozzá az Office 365-öt az **Alkalmazások** panelen.
1.  Jelentkezzen be az Azure Portalra.
2.  Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4.  A **Mobilalkalmazások** területen válassza az **Alkalmazások** lehetőséget a **Kezelés** csoportban. Válassza a **Hozzáadás** lehetőséget.
5.  Az **Alkalmazás felvétele** panelen válassza az **Office 365** > **macOS** lehetőséget.
6.  Válassza a **Hozzáadás** elemet.

## <a name="configure-the-app-suite"></a>Az alkalmazáscsomag konfigurálása

Adja meg az alkalmazáscsomag adatait. Ezen adatok alapján azonosíthatja azt az Intune-ban, és a végfelhasználónak is segítenek megtalálni azt a Céges portál alkalmazásban.

1.  Az **Alkalmazás felvétele** panelen válassza az **App Suite Information** (Alkalmazáscsomag adatai) elemet.
2.  Adja meg a következő adatokat:
    - **Suite Name** (Csomag neve) – Itt adhatja meg az alkalmazáscsomag a céges portálon megjelenő nevét. Ügyeljen arra, hogy minden megadott csomagnév egyedi legyen. Ha ugyanazt a csomagnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Suite Description** (Csomag leírása) – Itt adhatja meg az alkalmazáscsomag leírását.
    - **Gyártó** – Gyártóként a Microsoft jelenik meg.
    - **Kategória** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Így megkönnyítheti a felhasználók számára az alkalmazáscsomag megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a Céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő** – Fejlesztőként a Microsoft jelenik meg.
    - **Tulajdonos** – Tulajdonosként a Microsoft jelenik meg.
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése** – Feltölthet egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
3.  Válassza az **OK** gombot. A csomag egyetlen bejegyzés formájában jelenik meg az alkalmazások listájában.

## <a name="configure-app-assignments"></a>Alkalmazás-hozzárendelések konfigurálása

Ebben a lépésben az alkalmazáscsomag hozzárendeléseit konfigurálhatja. Fontos megjegyezni, hogy a rendelkezésre álló alkalmazástípus hamarosan elérhető lesz.

1.  Válassza ki az alkalmazáscsomagot az alkalmazások listájában, majd válassza a **Hozzárendelések** lehetőséget.
2.  Válassza a **Csoportok kiválasztása** lehetőséget.
3.  Rendelje hozzá a csomagot a kívánt csoportokhoz. További információ: [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal).
4.  Minden egyes csoportnál válassza a **Require Install** (Telepítés megkövetelése) lehetőséget.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. A hozzárendelés véglegesítéséhez válassza a **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések

Az Office 365-alkalmazások Windows 10-es eszközökhöz való hozzáadásával kapcsolatos további tudnivalókért lásd: [Office 365 ProPlus 2016-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal](/intune/apps-add-office365).

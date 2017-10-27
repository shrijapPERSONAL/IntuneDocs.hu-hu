---
title: "iOS áruházbeli alkalmazások hozzáadása az Intune-hoz | Microsoft Docs"
titlesuffix: Azure portal
description: "Útmutató iOS-es áruházbeli alkalmazások hozzáadásához az Intune-ban.”"
keywords: Intune
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c5d18f217659c9be59c116670fbf92a6d1b2ab4
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


A témakörben található információ segítségével iOS-es áruházbeli alkalmazásokat adhat hozzá az Intune-hoz.

>[!NOTE]
>Bár az iOS-eszközök felhasználói eltávolíthatnak néhányat a beépített iOS-alkalmazások közül – például a Részvények vagy a Térképek alkalmazást –, az Intune nem használható ezek újratelepítésére. Amennyiben a végfelhasználó törölte ezeket az alkalmazásokat, manuálisan telepítheti újra őket az App Store áruházból.

## <a name="before-you-start"></a>Előkészületek

Ezzel az eljárással csak az áruházban ingyenesen elérhető alkalmazások hozzárendelése lehetséges. Ha fizetős alkalmazást szeretne az Intune segítségével hozzárendelni, fontolja meg az [iOS mennyiségi vásárlási program](vpp-apps-ios.md) használatát.


## <a name="step-1---search-for-the-app-in-the-store"></a>1. lépés: Az alkalmazás megkeresése az áruházban

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Felügyelet** > Alkalmazások elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Keresés az App Store-ban** lehetőséget.
7. Az **Apple App Store** panelen válassza ki az App Store országkódját.
8. Írja be a keresőmezőbe az alkalmazás nevét (vagy a név egy részét). Az Intune ekkor rákeres arra az áruházban, és a kapott eredmények listáját adja vissza.
9. Válassza ki a kívánt alkalmazást a listából, majd kattintson az **OK** gombra.

## <a name="step-2---configure-app-information"></a>2. lépés – Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
2. Az **Alkalmazás szerkesztése** panelen konfigurálja az alkalmazásadatokat. Amikor elkészült, kattintson a **Hozzáadás** lehetőségre. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
- **Név** – Itt adhatja meg az alkalmazás céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
- **Leírás** – Adja meg az alkalmazás leírását, amelyet a felhasználók is láthatnak majd a céges portálon.
- **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
- **Alkalmazás-áruház URL-címe** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
- **Áruház országa/régiója** – Válassza ki az App Store országkódját.
- **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legkorábbi olyan verzióját, amelyre az alkalmazás telepíthető. Az alkalmazás nem telepíthető régebbi operációs rendszert futtató eszközön.
- **Érvényes eszköztípusok** – A listából válassza ki az alkalmazás által használt eszközöket.
- **Kategória** (nem kötelező). Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. A kategóriákkal megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
- **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
- **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
- **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
- **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét. Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
- **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).  Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
- **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket. Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
- **Ikon** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
3. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza az **OK** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

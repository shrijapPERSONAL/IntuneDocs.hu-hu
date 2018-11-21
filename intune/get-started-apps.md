---
title: Bevezetés a Microsoft Intune alkalmazásainak használatába
titlesuffix: ''
description: Alkalmazásokat kereshet és adhat hozzá az eszközökhöz, hogy az alkalmazottak elvégezhessék a munkát.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: e206683575b60a5194d83dc829af4fbccfb9d32e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189286"
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Bevezetés a Microsoft Intune alkalmazásainak hozzáadásába

Az alkalmazások hozzárendelése, figyelése, konfigurálása és védelme előtt hozzá kell adnia őket az Intune-hoz. Az Intune számos különböző típusú alkalmazástípust támogat, amelyekhez az elérhető beállítások minden esetben eltérőek.

Az Intune a következő típusú alkalmazások a vállalati eszközökhöz való hozzáadását és hozzárendelését teszi lehetővé:
- **Áruházbeli alkalmazások** – Olyan eszközökhöz, amelyeknél további mobilalkalmazás-kezelést szeretne használni az App Store-ban elérhető alkalmazásokhoz.
- **Belső fejlesztésű (üzletági) alkalmazások** – Az Ön által feltöltött fájl töltődik le a felhasználók eszközeire.
- **Beépített alkalmazások** – Válogatott felügyelt alkalmazásokat, például Office 365-alkalmazásokat rendelhet iOS- és Android-eszközökhöz.
- **Alkalmazások a weben** – Az Intune létrehoz egy parancsikont a webalkalmazáshoz az eszköz kezdőképernyőjén.

> [!NOTE]
> A dinamikus eszközcsoportra alkalmazott új szabályzatoknak a csoportba tartozó összes eszközre történő propagálása akár nyolc órát is igénybe vehet.

## <a name="how-do-i-assign-a-public-store-app"></a>Hogyan oszthatok ki egy nyilvános áruházbeli alkalmazást?

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Ügyfélalkalmazások**, majd az **Alkalmazások** elemet.
4. Válassza a **Hozzáadás** lehetőséget, majd válassza az **iOS** lehetőséget az **Alkalmazástípus** megadásakor.
5. Válassza az **Alkalmazás kiválasztása** lehetőséget a **Keresés az App Store-ban** panel megjelenítéséhez.
6. A szövegdobozban keressen rá egy alkalmazásra, amelyet hozzárendel az eszközhöz. Válassza ki az alkalmazást, majd kattintson a **Kiválasztás** gombra.
7. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget, majd adja meg az összes adatot. Más, nem kötelező adatokat is megadhat, amelyek segítségére lehetnek az alkalmazás nyilvántartásában, kitöltheti például a **Tulajdonos**, a **Megjegyzések**, a **Fejlesztő** és az vállalat adatvédelmi nyilatkozatára mutató **Adatvédelmi nyilatkozat URL-címe** mezőt.
8. Először válassza az **Igen** lehetőséget a **Megjelenítés kiemelt alkalmazásként a Céges portálon** beállításnál, majd válassza az **OK** gombot.
9. Az alkalmazás hozzáadásához válassza az **Alkalmazás felvétele** panelen a **Hozzáadás** gombot. Ezzel megnyitja az alkalmazás **Áttekintés** lapját. Válassza a **Hozzárendelések** lehetőséget, majd az alkalmazás tesztcsoporthoz rendeléséhez kattintson a **Csoport hozzáadása** elemre. Tegye az alkalmazást letöltésre **Elérhető** állapotúvá. Az alkalmazásnak ekkor **Kiemelt alkalmazásként** kell megjelennie a teszteszközön.


- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

## <a name="learn-more"></a>További információ

* [Mi az Intune-alapú alkalmazásfelügyelet?](app-management.md)
* [Az alkalmazás-életciklus áttekintése](app-lifecycle.md)
* [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

---
title: "Bevezetés az alkalmazások használatába"
titlesuffix: Azure portal
description: "Alkalmazásokat kereshet és adhat hozzá az eszközökhöz, hogy az alkalmazottak elvégezhessék a munkát."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb02c362f056c454f4d141ce7ae20b9c3ca8035d
ms.sourcegitcommit: a7c1e10e615e5c975bb5d52eca986c5cf5287687
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2017
---
# <a name="get-started-with-adding-apps"></a>Az alkalmazások felvételének első lépései

Az Intune néhány eltérő módot támogat az alkalmazások céges eszközökön való üzembe helyezéséhez:

* **Szoftvertelepítők**: az Ön által feltöltött fájl töltődik le a felhasználók eszközeire
* __Külső hivatkozások__: nyilvános alkalmazás-áruházban lévő alkalmazáshoz vagy webalkalmazáshoz
* **Felügyelt alkalmazások**: olyan iOS-eszközökhöz, amelyeknél további mobilalkalmazás-kezelést szeretne használni az App Store-ban elérhető alkalmazásokhoz

Az alkalmazások üzembe helyezésének egyik gyorsabb módszerén fogjuk végigvezetni nyilvános áruházbeli alkalmazás hozzárendelésével.

## <a name="how-do-i-assign-a-public-store-app"></a>Hogyan oszthatok ki egy nyilvános áruházbeli alkalmazást?

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. A **Erőforrások keresése** használatával keressen rá az **Intune** kifejezésre.
3. Válassza a **Mobilalkalmazások**, majd az **Alkalmazások** elemet.
4. Válassza a **Hozzáadás** lehetőséget, majd válassza az **Áruházbeli alkalmazás** elem alatti **iOS** lehetőséget az **Alkalmazástípus** megadásakor.
5. Válassza az **Alkalmazás kiválasztása** lehetőséget a **Keresés az App Store-ban** panel megjelenítéséhez.
6. A szövegdobozban keressen rá egy alkalmazásra, amelyet hozzárendel az eszközhöz. Válassza ki az alkalmazást, majd kattintson a **Kiválasztás** gombra.
7. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget, majd adja meg az összes adatot. Más, nem kötelező adatokat is megadhat, amelyek segítségére lehetnek az alkalmazás nyilvántartásában, kitöltheti például a **Tulajdonos**, a **Megjegyzések**, a **Fejlesztő** és az vállalat adatvédelmi nyilatkozatára mutató **Adatvédelmi nyilatkozat URL-címe** mezőt.
8. Először válassza az **Igen** lehetőséget a **Megjelenítés kiemelt alkalmazásként a Céges portálon** beállításnál, majd válassza az **OK** gombot.
9. Az alkalmazás hozzáadásához válassza az **Alkalmazás felvétele** panelen a **Hozzáadás** gombot. Ezzel megnyitja az alkalmazás **Áttekintés** lapját. Válassza a **Hozzárendelések** lehetőséget, majd az alkalmazás tesztcsoporthoz rendeléséhez kattintson a **Csoportok kiválasztása** elemre. Tegye az alkalmazást letöltésre **Elérhető** állapotúvá. Az alkalmazásnak ekkor **Kiemelt alkalmazásként** kell megjelennie a teszteszközön.

## <a name="learn-more"></a>További információ

* [Mi az Intune-alapú alkalmazásfelügyelet?](app-management.md)
* [Az alkalmazás-életciklus áttekintése](app-lifecycle.md)
* [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

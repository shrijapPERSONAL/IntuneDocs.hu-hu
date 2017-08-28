---
title: "Bevezetés az alkalmazások használatába"
titleSuffix: Intune on Azure
description: "Alkalmazásokat kereshet és adhat hozzá az eszközökhöz, hogy az alkalmazottak elvégezhessék a munkát."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ac2a6f027a78c6b0093a0d299a7cae3265e5954
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-adding-apps"></a>Az alkalmazások felvételének első lépései

Az Intune néhány eltérő módot támogat az alkalmazások céges eszközökön való üzembe helyezéséhez:

* **Szoftvertelepítők**: az Ön által feltöltött fájl töltődik le a felhasználók eszközeire
* __Külső hivatkozások__: nyilvános alkalmazás-áruházban lévő alkalmazáshoz vagy webalkalmazáshoz
* **Felügyelt alkalmazások**: olyan iOS-eszközökhöz, amelyeknél további mobilalkalmazás-kezelést szeretne használni az App Store-ban elérhető alkalmazásokhoz

Az alkalmazások üzembe helyezésének egyik gyorsabb módszerén fogjuk végigvezetni nyilvános áruházbeli alkalmazás hozzárendelésével.

## <a name="how-do-i-assign-a-public-store-app"></a>Hogyan oszthatok ki egy nyilvános áruházbeli alkalmazást?

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. A **Erőforrások keresése** használatával keressen rá az **Intune** kifejezésre.
3. Válassza a **Mobilalkalmazások**, majd az **Alkalmazások** elemet.
4. Válassza a **Hozzáadás** elemet, majd az **iOS áruházbeli alkalmazás** lehetőséget az **Alkalmazástípus** megadásakor.
5. A szövegdobozban keressen rá egy alkalmazásra, amelyet hozzárendel az eszközhöz. Válassza ki az alkalmazást, majd válassza az **OK** gombot.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget, majd adja meg az összes adatot. Más, nem kötelező adatokat is megadhat, amelyek segítségére lehetnek az alkalmazás nyilvántartásában, kitöltheti például a **Tulajdonos**, a **Megjegyzések**, a **Fejlesztő** és az vállalat adatvédelmi nyilatkozatára mutató **Adatvédelmi nyilatkozat URL-címe** mezőt.
7. Először válassza ki az Igen lehetőséget a Megjelenítés kiemelt alkalmazásként a Céges portálon beállításnál, majd válassza az OK gombot.
8. Az alkalmazás hozzáadásához válassza a **Hozzáadás** gombot. Ezzel megnyitja az alkalmazás **Áttekintés** lapját. Válassza a **Hozzárendelések** lehetőséget, majd az alkalmazás tesztcsoporthoz rendeléséhez kattintson a **Csoportok kiválasztása** elemre. Tegye az alkalmazást letöltésre **Elérhető** állapotúvá. Az alkalmazásnak ekkor **Kiemelt alkalmazásként** kell megjelennie a teszteszközön.

## <a name="learn-more"></a>További információ

* [Mi az Intune-alapú alkalmazásfelügyelet?](app-management.md)
* [Az alkalmazás-életciklus áttekintése](app-lifecycle.md)
* [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

---
title: "Bevezetés az alkalmazások használatába"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a086da185681a91daad214f1be2d4ff0e2827fbb
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-with-apps"></a>Bevezetés az alkalmazások használatába

![A Microsoft Word alkalmazás felvételét ábrázoló kép.](/intune/media/generic-add-apps.png)

A munkahelyi eszközök a megfelelő telepített alkalmazások nélkül haszontalanok. Az Intune néhány eltérő módot támogat az alkalmazások céges eszközökön való üzembe helyezéséhez:

* **Szoftvertelepítők**: az Ön által feltöltött fájl töltődik le a felhasználók eszközeire
* __Külső hivatkozások__: nyilvános alkalmazás-áruházban lévő alkalmazáshoz vagy webalkalmazáshoz
* **Felügyelt alkalmazások**: olyan iOS-eszközökhöz, amelyeknél további mobilalkalmazás-kezelést szeretne használni az App Store-ban elérhető alkalmazásokhoz

Az alkalmazások üzembe helyezésének egyik gyorsabb módszerén fogjuk végigvezetni nyilvános áruházbeli alkalmazás hozzárendelésével.

__Hogyan oszthatok ki egy nyilvános áruházbeli alkalmazást?__

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. A **Erőforrások keresése** használatával keressen rá az **Intune** kifejezésre.
3. Válassza a **Mobilalkalmazások**, majd az **Alkalmazások** elemet.
4. Válassza a **Hozzáadás** elemet, majd az **iOS áruházbeli alkalmazás** lehetőséget az **Alkalmazástípus** megadásakor.
5. A szövegdobozban keressen rá egy alkalmazásra, amelyet hozzárendel az eszközhöz. Válassza ki az alkalmazást, majd válassza az **OK** gombot.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget, majd adja meg az összes adatot. Más, nem kötelező adatokat is megadhat, amelyek segítségére lehetnek az alkalmazás nyilvántartásában, kitöltheti például a **Tulajdonos**, a **Megjegyzések**, a **Fejlesztő** és az vállalat adatvédelmi nyilatkozatára mutató **Adatvédelmi nyilatkozat URL-címe** mezőt.
7. Először válassza ki az Igen lehetőséget a Megjelenítés kiemelt alkalmazásként a Céges portálon beállításnál, majd válassza az OK gombot.
8. Az alkalmazás hozzáadásához válassza a **Hozzáadás** gombot. Ezzel megnyitja az alkalmazás **Áttekintés** lapját. Válassza a **Hozzárendelések** lehetőséget, majd az alkalmazás tesztcsoporthoz rendeléséhez kattintson a **Csoportok kiválasztása** elemre. Tegye az alkalmazást letöltésre **Elérhető** állapotúvá. Az alkalmazásnak ekkor **Kiemelt alkalmazásként** kell megjelennie a teszteszközön.

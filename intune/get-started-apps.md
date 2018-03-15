---
title: "Bevezetés a Microsoft Intune alkalmazásainak használatába"
titlesuffix: 
description: "Alkalmazásokat kereshet és adhat hozzá az eszközökhöz, hogy az alkalmazottak elvégezhessék a munkát."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Bevezetés a Microsoft Intune alkalmazásainak hozzáadásába

Az alkalmazások hozzárendelése, figyelése, konfigurálása és védelme előtt hozzá kell adnia őket az Intune-hoz. Az Intune számos különböző típusú alkalmazástípust támogat, amelyekhez az elérhető beállítások minden esetben eltérőek.

Az Intune a következő típusú alkalmazások a vállalati eszközökhöz való hozzáadását és hozzárendelését teszi lehetővé:
- **Áruházbeli alkalmazások** – Olyan eszközökhöz, amelyeknél további mobilalkalmazás-kezelést szeretne használni az App Store-ban elérhető alkalmazásokhoz.
- **Belső fejlesztésű (üzletági) alkalmazások** – Az Ön által feltöltött fájl töltődik le a felhasználók eszközeire.
- **Beépített alkalmazások** – Válogatott felügyelt alkalmazásokat, például Office 365-alkalmazásokat rendelhet iOS- és Android-eszközökhöz. 
- **Alkalmazások a weben** – Az Intune létrehoz egy parancsikont a webalkalmazáshoz az eszköz kezdőképernyőjén.

## <a name="how-do-i-assign-a-public-store-app"></a>Hogyan oszthatok ki egy nyilvános áruházbeli alkalmazást?

Az alábbi példa végigvezeti egy iOS-alkalmazás a Microsoft Intune-ban történő hozzáadásán.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** lehetőséget az **Alkalmazások** panel jobb oldalán.
6. Az **Alkalmazás típusa** listában válassza az **iOS** lehetőséget az elérhető **Áruházbeli alkalmazások** közül.
6. Válassza a **Keresés az App Store-ban** lehetőséget.
7. A **Keresés az App Store-ban** panelen válassza ki az App Store országkódját.
8. Írja be a keresőmezőbe az alkalmazás nevét (vagy a név egy részét). Az Intune ekkor rákeres arra az áruházban, és a kapott eredmények listáját adja vissza.
9. Válassza ki a kívánt alkalmazást a listából, majd kattintson a **Kiválasztás** gombra.
10. Az alkalmazásadatok konfigurálásához válassza az **Alkalmazás adatai** lehetőséget.
11. (Nem kötelező) További adatokat is megadhat, amelyek segítségére lehetnek az alkalmazás nyilvántartásában, kitöltheti például a **Tulajdonos**, a **Megjegyzések**, a **Fejlesztő** és az vállalat adatvédelmi nyilatkozatára mutató **Adatvédelmi nyilatkozat URL-címe** mezőt.
12. Válassza az **Igen** lehetőséget a **Megjelenítés kiemelt alkalmazásként a Céges portálon** beállításnál. 
13. A szükséges alkalmazásadatok megadása után kattintson az **OK** gombra.
14. Kattintson a **Hozzáadás** gombra az **Alkalmazás hozzáadása** panelen. Ekkor megjelenik az adott alkalmazás **áttekintése**. 

## <a name="next-steps"></a>További lépések

Most, hogy hozzáadott egy alkalmazást az Intune-ban, megadhatja, hogy mely felhasználói csoportok adhatják hozzá az eszközükhöz.

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)
- 
## <a name="learn-more"></a>További információ

* [Mi az Intune-alapú alkalmazásfelügyelet?](app-management.md)
* [Az alkalmazás-életciklus áttekintése](app-lifecycle.md)
* [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

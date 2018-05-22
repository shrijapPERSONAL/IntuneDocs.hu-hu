---
title: Webalkalmazások hozzáadása az Intune-hoz
titleSuffix: ''
description: Webalkalmazások a Microsoft Intune-hoz való hozzáadásának ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d62341e35bf851bb429b15a582183bec62a9d4a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="add-web-apps-to-microsoft-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune számos különböző alkalmazástípust támogat, beleértve a webalkalmazásokat is. A webalkalmazások ügyfél-kiszolgáló alkalmazások. A kiszolgáló szolgáltatja a webalkalmazást, amely tartalmazza a felhasználói felületet, a tartalmat és a funkciókat. A modern webszolgáltatási platformok emellett gyakran kínálnak biztonsági, terheléselosztási és egyéb szolgáltatásokat is. A webalkalmazásokat külön, a weben kezelik. Ehhez az alkalmazástípushoz a Microsoft Intune-t kell használnia. Azt is megszabhatja, hogy mely felhasználói csoportok férhetnek hozzá az alkalmazáshoz. 

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse hozzá az alkalmazásokat, hozzá kell adnia őket az Intune-hoz. Az Intune létrehoz egy parancsikont a webalkalmazáshoz a felhasználó eszközének kezdőképernyőjén.

> [!Note]
> A webalkalmazások használata az Android for Work- és macOS-eszközökön nem támogatott.

## <a name="add-a-web-app-to-intune"></a>Webalkalmazás hozzáadása az Intune-hoz
A következő módon adhat hozzá egy alkalmazást az Intune-hoz egy alkalmazás webes hivatkozásaként:

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** munkaterületen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az **Alkalmazások** panelen válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás felvétele** panelen az **Alkalmazás típusa** legördülő listában válassza a **Webes hivatkozás** típust.
7. Válassza ki a **Konfigurálás** lehetőséget.
8. Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    - **Név**: Itt adhatja meg az alkalmazás céges portálon megjelenítendő nevét.
    - **Leírás**: Itt adhatja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Kiadó**: Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás URL-címe**: Adja meg annak a webhelynek az URL-címét, amelyen a hozzárendelni kívánt alkalmazás található.
    - **Kategória:** Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon:** Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Felügyelt böngésző használatának megkövetelése a hivatkozás megnyitásához**: Ezzel a lehetőséggel egy olyan webhelyre vagy webalkalmazásra mutató hivatkozást rendelhet a felhasználókhoz, amelyet az Intune által felügyelt böngészőben nyithatnak meg. Ezt a böngészőt telepíteni kell az eszközökön.
    - **Ikon**: Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
9. Válassza az **OK** gombot.
10. Az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.

> [!Note]
> Az Android-eszközökhöz rendelt webalkalmazások megjelenítéséhez a felhasználóknak hozzá kell adniuk az Intune widgetet a kezdőképernyőjükhöz.

## <a name="next-steps"></a>További lépések

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md). 

---
title: Webalkalmazások hozzáadása az Intune-hoz
titleSuffix: ''
description: Webalkalmazások a Microsoft Intune-hoz való hozzáadásának ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune számos különböző alkalmazástípust támogat, beleértve a webalkalmazásokat is. A webalkalmazások ügyfél-kiszolgáló alkalmazások. A kiszolgáló szolgáltatja a webalkalmazást, amely tartalmazza a felhasználói felületet, a tartalmat és a funkciókat. A modern webszolgáltatási platformok emellett gyakran kínálnak biztonsági, terheléselosztási és egyéb szolgáltatásokat. A webalkalmazásokat külön, a weben kezelik. Ehhez az alkalmazástípushoz a Microsoft Intune-t kell használnia. Azt is Ön dönti el, hogy mely felhasználói csoportok férhetnek hozzá az alkalmazáshoz. 

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse hozzá az alkalmazásokat, hozzá kell adnia őket az Intune-hoz. Az Intune létrehoz egy parancsikont a webalkalmazáshoz a felhasználó eszközének kezdőképernyőjén.

> [!Note]
> A webalkalmazások használata az Android for Work- és macOS-eszközökön nem támogatott.

A következő lépésekkel adhat hozzá egy alkalmazást az Intune-hoz egy alkalmazás webes hivatkozásaként:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. A **Microsoft Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** lehetőséget.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget. Ekkor az **Alkalmazás felvétele** panel jelenik meg.
6. Az **Alkalmazás felvétele** panelen válassza a **Webes hivatkozás** típust az **Alkalmazás típusa** legördülő listában.
7. Válassza a **Konfigurálás** lehetőséget az **Alkalmazásadatok** panel megjelenítéséhez.
8. Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    - **Név** – Itt adhatja meg az alkalmazás a céges portálon megjelenítendő nevét.
    - **Leírás** – Itt adhatja meg az alkalmazás leírását. Ez jelenik meg a végfelhasználók számára a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás URL-címe** – Adja meg annak a webhelynek az URL-címét, amelyen a hozzárendelni kívánt alkalmazás található.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel a kijelöléssel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Felügyelt böngésző használatának megkövetelése a hivatkozás megnyitásához** – Ha egy webhelyre vagy webalkalmazásra mutató hivatkozást rendel a felhasználókhoz, azt az Intune Managed Browser böngészőben nyithatják meg. Ezt a böngészőt telepíteni kell az eszközökön.
    - **Embléma** – Itt töltheti fel az alkalmazáshoz hozzárendelt emblémát. Ez az embléma jelenik meg az alkalmazásnál a céges portálon böngésző felhasználók számára.
9. Ha elkészült, az **Adatok hozzáadása** panelen válassza az **Ok** lehetőséget.
10. Ezután az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.

> [!Note]
> Az Android-eszközökhöz rendelt webalkalmazások megjelenítéséhez a felhasználóknak hozzá kell adniuk az Intune widgetet a kezdőképernyőjükhöz.

## <a name="next-steps"></a>További lépések

- A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).
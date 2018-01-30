---
title: "Webalkalmazások hozzáadása az Intune-hoz"
titleSuffix: Azure portal
description: "Információk a webalkalmazások Intune-hoz való hozzáadásáról."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfa70879a460826d22eb6fab2e0d08603e567d6e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse hozzá az alkalmazásokat, hozzá kell adnia őket az Intune-hoz. Az Intune számos különböző alkalmazástípust támogat, beleértve a webalkalmazásokat is.

> [!Note]
> A webalkalmazások használata az Android for Work-eszközökön nem támogatott.

A következő lépésekkel adhat hozzá egy alkalmazást az Intune-hoz egy alkalmazás webes hivatkozásaként:

1. Jelentkezzen be az Azure Portalra.
2. A **További erőforrások** lehetőséget használva keresse meg az **Intune-t**, és válassza ki.
3. A **Microsoft Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** lehetőséget.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget. Ekkor az **Alkalmazás felvétele** panel jelenik meg.
6. Az **Alkalmazás felvétele** panelen válassza a **Webalkalmazás** típust az **Alkalmazás típusa** legördülő listában.
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
9. Ha elkészült, az **Adatok felvétele** panelen válassza az **Ok** lehetőséget.
10. Ezután az **Alkalmazás felvétele** panelen válassza a **Hozzáadás** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).
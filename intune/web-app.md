---
title: Webalkalmazások hozzáadása az Intune-hoz
titleSuffix: ''
description: További web apps (ügyfél és kiszolgáló-alkalmazások) Microsoft Intune-ba való felvételéhez.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f1f0c36441b98c334311bdbfa85fa725c26b675
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57393546"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune számos különböző alkalmazástípust támogat, beleértve a webalkalmazásokat is. A webalkalmazások ügyfél-kiszolgáló alkalmazások. A kiszolgáló szolgáltatja a webalkalmazást, amely tartalmazza a felhasználói felületet, a tartalmat és a funkciókat. A modern webszolgáltatási platformok emellett gyakran kínálnak biztonsági, terheléselosztási és egyéb szolgáltatásokat is. A webalkalmazásokat külön, a weben kezelik. Ehhez az alkalmazástípushoz a Microsoft Intune-t kell használnia. Azt is megszabhatja, hogy mely felhasználói csoportok férhetnek hozzá az alkalmazáshoz. 

Ahhoz, hogy kezelhesse és felhasználókhoz rendelhesse hozzá az alkalmazásokat, hozzá kell adnia őket az Intune-hoz. Az Intune létrehoz egy parancsikont a webalkalmazáshoz a felhasználó eszközének kezdőképernyőjén.

> [!Note]
> A webalkalmazások használata az androidos munkahelyi profilt használó és macOS-eszközökön nincs támogatva.

## <a name="add-a-web-app-to-intune"></a>Webalkalmazás hozzáadása az Intune-hoz
A következő módon adhat hozzá egy alkalmazást az Intune-hoz egy alkalmazás webes hivatkozásaként:

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** tevékenységprofil panelén a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az **Alkalmazások** panelen válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás felvétele** panelen az **Alkalmazás típusa** legördülő listában válassza a **Webes hivatkozás** típust.
7. Válassza ki a **Konfigurálás** lehetőséget.
8. Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    - **Név**:  Adja meg az alkalmazás nevét, mivel a vállalati portálon megjeleníteni kívánt. 
    
        > [!NOTE]
        > Ha az alkalmazás telepítését követően módosítja annak nevét az Intune Azure Portalon, az alkalmazást nem fogják megtalálni a parancsok.
    
    - **Description** (Leírás): Adja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Közzétevő**: Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás URL-címe**: Adja meg az URL-címét a webhely, amelyen a hozzárendelni kívánt alkalmazás található.
    - **Kategória**: Kiválaszthat egy vagy több, a beépített Alkalmazáskategóriák vagy egy létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Válassza ki ezt a beállítást, az alkalmazáscsomag hangsúlyosan jelenítheti fő lapján, a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **A hivatkozás megnyitásához felügyelt böngésző szükséges**: Válassza ki ezt a beállítást, hozzárendelheti a felhasználókhoz egy webhelyre vagy webalkalmazásra alkalmazást, akkor az Intune által felügyelt böngészőben megnyitható mutató hivatkozást. Ezt a böngészőt telepíteni kell az eszközökön.
    - **Embléma**: Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
9. Kattintson az **OK** gombra.
10. Az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.

> [!Note]
> Az Android-eszközökhöz rendelt webalkalmazások megjelenítéséhez a felhasználóknak hozzá kell adniuk az Intune widgetet a kezdőképernyőjükhöz.
>
> Az Intune-webalkalmazások iOS-eszközökön való üzembe helyezése jelenleg a felügyeleti profillal van társítva, így manuálisan nem távolíthatók el. Az Intune portálon **Eltávolítás** értékre módosíthatja az üzembehelyezési típust, hogy a webalkalmazás automatikusan eltávolítható legyen. Ha azonban azelőtt távolítja el az üzemelő példányt, hogy az alkalmazás-hozzárendelési szándékot **Eltávolítás** értékre módosítaná, a webalkalmazás végleg az eszközön marad, amíg meg nem szűnik az eszköz regisztrációja az Intune-ban.

## <a name="next-steps"></a>További lépések

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md). 

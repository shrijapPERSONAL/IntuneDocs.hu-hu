---
title: Microsoft Store-alkalmazások hozzáadása a Microsoft Intune-hoz
titleSuffix: ''
description: Útmutató Microsoft Store-beli (Windows Áruházbeli) alkalmazások Microsoft Intune-ba való hozzáadásához.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: baa9b20ee8820915f3cdee6ee26ec2429c93d63b
ms.sourcegitcommit: 2b5d88c434bda7f1cdc32d1ccacc6b341a9a399b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store-alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alkalmazások hozzárendelése, figyelése, konfigurálása és védelme előtt hozzá kell adnia őket az Intune-hoz. 

## <a name="add-an-app-to-intune"></a>Alkalmazás hozzáadása az Intune-hoz
A következő módon adhat hozzá Microsoft Store-beli alkalmazást az Intune-hoz:

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** munkaterületen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az **Alkalmazások** panelen válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Windows** lehetőséget az **Alkalmazás típusa** területen, majd válassza az **Alkalmazásadatok** lehetőséget.
7. Az **Alkalmazásadatok** panelen adja meg az alkalmazás adatait. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név**: Itt adhatja meg az alkalmazás céges portálon megjelenítendő nevét. Gondoskodjon róla, hogy az alkalmazás neve egyedi legyen. Ha két alkalmazás neve megegyezik, a felhasználók csak az egyik alkalmazást fogják látni a céges portálon.
    - **Leírás**: Itt adhatja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Kiadó**: Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás-áruház URL-címe**: Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
    - **Kategória:** Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon:** Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím:** Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe:** Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő**: Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például *HR-osztály*).
    - **Megjegyzések:**: Ide írhatja be igény szerint az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon** (nem kötelező): Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
8. Válassza az **OK** gombot.
9. Válassza a **Hozzáadás** elemet.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz. 

## <a name="next-steps"></a>További lépések
- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

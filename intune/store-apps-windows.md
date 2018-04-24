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
ms.openlocfilehash: 511cf2e01a2f5db93f0e0db9dbe2a32326c17723
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store-alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alkalmazások hozzárendelése, figyelése, konfigurálása és védelme előtt hozzá kell adnia őket az Intune-hoz. A következő lépésekkel Microsoft Store-alkalmazásokat adhat hozzá a Microsoft Intune-hoz.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Windows** lehetőséget az **Alkalmazás típusa** területen, majd válassza az **Alkalmazásadatok** lehetőséget.
7. Az **Alkalmazás adatai** panelen konfigurálja az alábbi információkat. Amikor elkészült, kattintson az **OK** lehetőségre. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név** – Itt adhatja meg az alkalmazásnak a vállalati portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Leírás** – Adja meg az alkalmazás leírását, amelyet a felhasználók is láthatnak majd a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás-áruház URL-címe** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is, mely segít a felhasználóknak könnyebben megtalálni az alkalmazást a céges portál böngészésekor.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
8. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. 

## <a name="next-steps"></a>További lépések
- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)
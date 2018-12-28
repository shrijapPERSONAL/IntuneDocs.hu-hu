---
title: Androidos áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz
titleSuffix: ''
description: Útmutató Androidos áruházbeli alkalmazások hozzáadása a Google Play áruházból a Microsoft Intune-bA.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2391f6ec7de5a9d1b4d544f1ca07fd9f4e58ace8
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642406"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Androidos áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mielőtt az alkalmazást hozzárendelné egy eszközhöz vagy felhasználói csoporthoz, az eszközt először hozzá kell adnia a Microsoft Intune-hoz. 

## <a name="add-an-app"></a>Alkalmazás felvétele

A következő módon adhat hozzá Android-áruházból származó alkalmazást az Intune-hoz az Azure Portalon:

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** tevékenységprofil panelén a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen az elérhető **Áruházbeli alkalmazások** típusai közül válassza az **Android** lehetőséget.
7. Az alkalmazás adatainak megadásához válassza a **Konfigurálás** lehetőséget, majd adja meg a következő adatokat. Android-alkalmazások esetén keresse fel a [Google Play áruházat](https://play.google.com/store), és keresse meg az üzembe helyezni kívánt alkalmazást. Válassza ki az alkalmazást, és jegyezze fel az alkalmazás adatait. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név**: Adja meg az alkalmazás nevét, mivel a vállalati portálon megjeleníteni kívánt. Gondoskodjon róla, hogy az alkalmazás neve egyedi legyen. Ha két alkalmazás neve megegyezik, a felhasználók csak az egyik alkalmazást fogják látni a céges portálon.
    - **Description** (Leírás): Adja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Közzétevő**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Alkalmazásáruház URL-címe**: Adja meg az alkalmazást, amelyet a létrehozni kívánt alkalmazás áruházbeli URL-CÍMÉT.
    - **Az operációs rendszer minimális**: A listában válassza ki a legkorábbi operációs rendszer verziója, amelyen az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
    - **Kategória**: Kiválaszthat egy vagy több, a beépített Alkalmazáskategóriák vagy egy létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Válassza ki ezt a beállítást, az alkalmazáscsomag hangsúlyosan jelenítheti fő lapján, a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím**: Nem kötelező: megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi URL-címe**: Nem kötelező: megadhatja az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztői**: Megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Szükség esetén adja meg például az alkalmazás tulajdonosának nevét *HR részleg*.
    - **Megjegyzések**: Megadhatja, hogy az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Embléma**: Szükség esetén töltse fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
1. Kattintson az **OK** gombra.
2. Válassza a **Hozzáadás** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz. 

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

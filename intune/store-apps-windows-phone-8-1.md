---
title: Windows Phone 8.1-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz
titleSuffix: ''
description: Ez a témakör ismerteti a Windows Phone 8.1-es áruházbeli alkalmazások hozzáadása Microsoft Intune-bA.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f5d043d0f7d17825ebf8ce7d991372dc0587da15
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845618"
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Windows Phone 8.1-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mielőtt az alkalmazást hozzárendelné egy eszközhöz vagy felhasználói csoporthoz, az eszközt először hozzá kell adnia a Microsoft Intune-hoz. 

## <a name="add-an-app-to-intune"></a>Alkalmazás hozzáadása az Intune-hoz
A következő módon adhat hozzá Windows Phone 8.1-áruházbeli alkalmazást az Intune-hoz az Azure Portalon:

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** tevékenységprofil panelén a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az **Alkalmazások** panelen válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Windows Phone 8.1** lehetőséget az **Alkalmazás típusa** területen, majd válassza az **Alkalmazásadatok** lehetőséget.
7. Az **Alkalmazásadatok** panelen adja meg az alkalmazás adatait. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név**: Adja meg az alkalmazás nevét, mivel a vállalati portálon megjeleníteni kívánt. Gondoskodjon róla, hogy az alkalmazás neve egyedi legyen. Ha két alkalmazás neve megegyezik, a felhasználók csak az egyik alkalmazást fogják látni a céges portálon.
    - **Description** (Leírás): Adja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Közzétevő**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Alkalmazásáruház URL-címe**: Adja meg a létrehozni kívánt alkalmazás App Store URL-CÍMÉT.
    - **Kategória**: Kiválaszthat egy vagy több, a beépített Alkalmazáskategóriák vagy egy létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Válassza ki ezt a beállítást, az alkalmazáscsomag hangsúlyosan jelenítheti fő lapján, a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím**: Nem kötelező: megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi URL-címe**: Nem kötelező: megadhatja az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztői**: Megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Szükség esetén adja meg például az alkalmazás tulajdonosának nevét *HR részleg*.
    - **Megjegyzések**: Megadhatja, hogy az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Embléma**: Szükség esetén töltse fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
8. Kattintson az **OK** gombra.
9. Válassza a **Hozzáadás** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

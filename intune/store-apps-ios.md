---
title: iOS-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz
titlesuffix: ''
description: Útmutató iOS-es áruházbeli alkalmazások a Microsoft Intune-ba való hozzáadásához. Ezt a módszert használja, ha az alkalmazásokat az App Store ingyenesen elérhető alkalmazásokat rendelhet.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd4562b001eaefc8e10512a42b08d49385f75808
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834109"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>iOS-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A témakörben található információ segítségével iOS-es áruházbeli alkalmazásokat adhat hozzá a Microsoft Intune-hoz. Az iOS-es áruházbeli alkalmazásokat az Intune telepíti a felhasználói eszközökön. A felhasználók a cég munkatársai. Az iOS-es alkalmazásbeli alkalmazások automatikusan frissülnek.

>[!NOTE]
>Bár az iOS-eszközök felhasználói eltávolíthatnak néhányat a beépített iOS-alkalmazások közül – például a Részvények vagy a Térképek alkalmazást –, az Intune nem használható ezek újratelepítésére. Amennyiben a felhasználó törölte ezeket az alkalmazásokat, manuálisan telepítheti újra őket az App Store áruházból.

## <a name="before-you-start"></a>Előkészületek

Ezzel az eljárással csak az áruházban ingyenesen elérhető alkalmazások hozzárendelése lehetséges. Ha fizetős alkalmazást szeretne az Intune segítségével hozzárendelni, fontolja meg az [iOS mennyiségi vásárlási program](vpp-apps-ios.md) használatát.

>[!NOTE]
>A Microsoft Intune használatához javasoljuk, hogy a Microsoft Edge vagy a Google Chrome böngészőt használja.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** tevékenységprofil panelén a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az **Alkalmazások** panelen válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás típusa** lista **Áruházbeli alkalmazás** területén válassza az **iOS** lehetőséget.
7. Válassza a **Keresés az App Store-ban** lehetőséget.
8. A **Keresés az App Store-ban** panelen válassza ki az App Store országkódját.
9. Írja be a **Keresés** mezőbe az alkalmazás nevét (vagy a név egy részét).  
    Az Intune ekkor rákeres arra az áruházban, és a kapott eredmények listáját adja vissza.
10. Az eredmények listájában válassza ki a kívánt alkalmazást, majd válassza a **Kiválasztás** lehetőséget.
11. Az alkalmazás konfigurálásához az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
12. Az **Alkalmazásadatok** panelen adja meg az alkalmazás adatait. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név**: Adja meg az alkalmazás nevét, mivel a vállalati portálon megjeleníteni kívánt. Gondoskodjon róla, hogy az alkalmazás neve egyedi legyen. Ha két alkalmazás neve megegyezik, a felhasználók csak az egyik alkalmazást fogják látni a céges portálon.
    - **Description** (Leírás): Adja meg az alkalmazás leírását. A leírás a céges portálon jelenik meg a felhasználók számára.
    - **Közzétevő**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Alkalmazásáruház URL-címe**: Adja meg a létrehozni kívánt alkalmazás App Store URL-CÍMÉT.
    - **Az operációs rendszer minimális**: A listában válassza ki a legkorábbi operációs rendszer verziója, amelyen az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
    - **Alkalmazható eszköztípus**: A listában válassza ki az alkalmazás által használt eszközöket.
    - **Kategória**: Kiválaszthat egy vagy több, a beépített Alkalmazáskategóriák vagy egy létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Válassza ki ezt a beállítást, az alkalmazáscsomag hangsúlyosan jelenítheti fő lapján, a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím**: Nem kötelező: megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi URL-címe**: Nem kötelező: megadhatja az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztői**: Megadhatja az alkalmazás fejlesztőjének nevét. Ez a mező csak a rendszergazdák számára látható, a felhasználók számára nem.
    - **Tulajdonos**: Szükség esetén adja meg például az alkalmazás tulajdonosának nevét *HR részleg*. Ez a mező csak a rendszergazdák számára látható, a felhasználók számára nem.
    - **Megjegyzések**: Megadhatja, hogy az alkalmazáshoz társítani kívánt megjegyzéseket. Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
    - **Embléma**: Szükség esetén töltse fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
13. Kattintson az **OK** gombra.
14. Válassza a **Hozzáadás** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kiválasztott csoportokhoz.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

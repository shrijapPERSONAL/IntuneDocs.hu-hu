---
title: iOS-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz
titlesuffix: ''
description: Útmutató iOS-es áruházbeli alkalmazások a Microsoft Intune-ba való hozzáadásához.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4eaa4b279ab98c6fe41482628937e0f2b0dc70a5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS-es áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A témakörben található információ segítségével iOS-es áruházbeli alkalmazásokat adhat hozzá a Microsoft Intune-hoz. Az iOS-es áruházbeli alkalmazásokat az Intune telepíti a felhasználói eszközökön. A felhasználónak a cég munkatársának kell lennie. Az iOS-es alkalmazásbeli alkalmazások automatikusan frissülnek.

>[!NOTE]
>Bár az iOS-eszközök felhasználói eltávolíthatnak néhányat a beépített iOS-alkalmazások közül – például a Részvények vagy a Térképek alkalmazást –, az Intune nem használható ezek újratelepítésére. Amennyiben a végfelhasználó törölte ezeket az alkalmazásokat, manuálisan telepítheti újra őket az App Store áruházból.

## <a name="before-you-start"></a>Előkészületek

Ezzel az eljárással csak az áruházban ingyenesen elérhető alkalmazások hozzárendelése lehetséges. Ha fizetős alkalmazást szeretne az Intune segítségével hozzárendelni, fontolja meg az [iOS mennyiségi vásárlási program](vpp-apps-ios.md) használatát.

>[!NOTE]
>A Microsoft Intune-beli munkavégzéshez a Chrome és a Microsoft Edge böngészőt ajánljuk.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** lehetőséget az **Alkalmazások** panel jobb oldalán.
6. Az **Alkalmazás típusa** listában válassza az **iOS** lehetőséget az elérhető **Áruházbeli alkalmazások** közül.
7. Válassza a **Keresés az App Store-ban** lehetőséget.
8. A **Keresés az App Store-ban** panelen válassza ki az App Store országkódját.
9. Írja be a keresőmezőbe az alkalmazás nevét (vagy a név egy részét). Az Intune ekkor rákeres arra az áruházban, és a kapott eredmények listáját adja vissza.
10. Válassza ki a kívánt alkalmazást a listából, majd kattintson a **Kiválasztás** gombra.
11. Az alkalmazás konfigurálásához az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
12. Az **Alkalmazásadatok** panelen adja meg az alkalmazás adatait. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név** – Itt adhatja meg az alkalmazás céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Leírás** – Adja meg az alkalmazás leírását, amelyet a felhasználók is láthatnak majd a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás-áruház URL-címe** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
    - **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legkorábbi olyan verzióját, amelyre az alkalmazás telepíthető. Az alkalmazás nem telepíthető régebbi operációs rendszert futtató eszközön.
    - **Érvényes eszköztípusok** – A listából válassza ki az alkalmazás által használt eszközöket.
    - **Kategória** (nem kötelező). Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. A kategóriákkal megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét. Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).  Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket. Ez a mező csak rendszergazdáknak jelenik meg, a végfelhasználók nem láthatják.
    - **Ikon** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
13. Ha elkészült, az **Adatok hozzáadása** panelen kattintson az **OK** gombra.
14. Az **Alkalmazás hozzáadása** panelen kattintson a **Hozzáadás** elemre.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

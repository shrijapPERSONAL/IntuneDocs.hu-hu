---
title: "A Windows Information Protection (WIP) alkalmazásvédelmi szabályzatainak létrehozása és bevezetése az Intune használatával"
titlesuffix: Azure portal
description: "A WIP alkalmazásvédelmi szabályzatainak létrehozása és bevezetése az Intune használatával"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf11c53a5f1ce78dda9c703da32270b0b07874a
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/04/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>A Windows Information Protection (WIP) alkalmazásvédelmi szabályzatainak létrehozása és bevezetése az Intune használatával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune 1704-es kiadásától kezdve az eszközök regisztrálása nélkül használhatja az alkalmazásvédelmi szabályzatokat Windows 10 rendszer esetén.

## <a name="before-you-begin"></a>Előkészületek

Érdemes szót ejtenünk pár fogalomról, amelyek a WIP szabályzatainak hozzáadásakor merülnek fel.

### <a name="list-of-allowed-and-exempt-apps"></a>Az engedélyezett és mentesített alkalmazások listája

-   **Engedélyezett alkalmazások:** ezeknek meg kell felelniük az adott szabályzatnak.

-   **Mentesített alkalmazások:** ezek mentesülnek az adott szabályzat alól, és korlátozás nélkül hozzáférnek a céges adatokhoz.

### <a name="types-of-apps"></a>Alkalmazások típusai

-   **Ajánlott alkalmazások:** a szabályzatba egyszerűen importálható (leginkább Microsoft Office-) alkalmazásokból előre összeállított lista. <!---I really don't know what you mean by "easily import into policy"--->

-   **Áruházbeli alkalmazások:** bármilyen alkalmazást felvehet a szabályzatba a Microsoft Áruházból.

-   **Asztali Windows-alkalmazások:** bármilyen hagyományos asztali Windows-alkalmazást (.exe, .dll stb.) felvehet a szabályzatba.

## <a name="pre-requisites"></a>Előfeltételek

A WIP alkalmazásvédelmi szabályzatainak létrehozása előtt be kell állítania a MAM-szolgáltatót. További információk a [MAM-szolgáltató konfigurálásáról az Intune segítségével](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

Emellett rendelkeznie kell a következőkkel:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) licenc.
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> A WIP nem támogatja a többszörös identitás használatát, egyidejűleg csak egyetlen felügyelt identitás létezhet.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>WIP-szabályzat hozzáadása

Miután cégénél beállította az Intune-t, az [Azure Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) használatával hozhat létre WIP-specifikus szabályzatokat. <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Nyissa meg az **Intune mobilalkalmazás-kezelési irányítópultját**, majd válassza a **Minden beállítás** > **Alkalmazásszabályzat** lehetőséget.

2.  Az **Alkalmazásszabályzat** panelen válassza a **Szabályzat hozzáadása** lehetőséget, majd adja meg a következő értékeket:

    a.  **Név:** Adja meg az új szabályzat nevét (szükséges).

    b.  **Leírás:** Adjon meg hozzá leírást (nem kötelező).

    c.  **Platform:** Az alkalmazásvédelmi szabályzat támogatott platformjának válassza a **Windows 10** lehetőséget.

    d.  **Regisztráció állapota:** Válassza a **Regisztráció nélkül** lehetőséget a szabályzat regisztrációs állapotaként.

3.  Válassza a **Létrehozás** lehetőséget. A szabályzat létrejön, és megjelenik az **Alkalmazásszabályzat** panelen található táblázatban.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Javasolt alkalmazások hozzáadása az engedélyezett alkalmazások listájához

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd a **Házirend hozzáadása** panelen válassza az **Engedélyezett alkalmazások** lehetőséget. Megnyílik az **Engedélyezett alkalmazások** panel, ahol megjelenik azoknak az alkalmazásoknak a listája, amelyekre ez a szabályzat vonatkozik.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget. Megnyílik az **Alkalmazások hozzáadása** panel, amelyen láthatja a listában található összes alkalmazást.

3.  Válassza ki azokat az alkalmazásokat, amelyeknek hozzáférést kíván adni a céges adatokhoz, majd kattintson az **OK** gombra. Az **Engedélyezett alkalmazások** panel frissül, és kibővül a kiválasztott alkalmazásokkal.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Áruházbeli alkalmazás hozzáadása az engedélyezett alkalmazások listájához

**Áruházbeli alkalmazás hozzáadása**

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd válassza az **Engedélyezett alkalmazások** lehetőséget a megjelenő menüben, amely az alkalmazásszabályzathoz már korábban hozzáadott alkalmazások listáját jeleníti meg.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget.

3.  Az **Alkalmazások hozzáadása** panelen válassza az **Áruházbeli alkalmazások** lehetőséget a legördülő listából. A panelen szövegbeviteli mezők jelennek meg, amelyekkel megadhatja az alkalmazás **közzétevőjét** és az alkalmazás **nevét**.

4.  Írja be az alkalmazás és a közzétevő nevét, majd kattintson az **OK** gombra.

    > [!TIP]
    > Az alábbi példában a **Közzétevő** a *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US*, a termék **neve** pedig *Microsoft.MicrosoftAppForWindows*.

5.  Miután megadta az adatokat, kattintson az **OK** gombra, hogy hozzáadja az alkalmazást az **Engedélyezett alkalmazások** listájához.

> [!NOTE]
> Egyszerre több áruházbeli alkalmazást is hozzáadhat, ha az alkalmazások sor végén található **(...)** menügombra kattint és további alkalmazásokat választ ki. Ha elkészült, kattintson az **OK** gombra.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Asztali alkalmazás hozzáadása az engedélyezett alkalmazások listájához

**Asztali alkalmazás hozzáadása**

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd válassza az **Engedélyezett alkalmazások** lehetőséget. Megnyílik az **Engedélyezett alkalmazások** panel, ahol azoknak az alkalmazásoknak a listáját láthatja, amelyekre ez a szabályzat vonatkozik.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget.

3.  Az **Alkalmazások hozzáadása** panelen válassza az **Asztali alkalmazások** lehetőséget a legördülő listából.

4.  Miután megadta az adatokat, az **OK** gombra kattintva hozzáadhatja az alkalmazást az **Engedélyezett alkalmazások** listájához.

> [!NOTE]
> Egyszerre több **asztali alkalmazást** is hozzáadhat, ha az alkalmazások sor végén található **(...)** menügombra kattint és további alkalmazásokat választ ki. Ha elkészült, kattintson az **OK** gombra.

## <a name="wip-learning"></a>WIP Learning
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
A WIP által védeni kívánt alkalmazások hozzáadása után alkalmazni kell azokon az egyik védelmi módot a **WIP Learning** használatával.

### <a name="before-you-begin"></a>Előkészületek

A WIP Learning egy olyan jelentés, amellyel a WIP számára ismeretlen alkalmazásokat figyelheti. Ismeretlennek számítanak az olyan alkalmazások, amelyeket nem a munkahelyi IT-részleg helyezett üzembe. A jelentésből exportálhatja ezeket az alkalmazásokat, és a munka megzavarását elkerülendő hozzáadhatja őket a WIP-szabályzatokhoz, mielőtt a WIP-et „Felülbírálások elrejtése” módban alkalmazná.

Javasoljuk, hogy először a **Csendes** vagy a **Felülbírálások engedélyezése** módot válassza, és egy kisebb csoporton ellenőrizze, hogy az engedélyezett alkalmazások listájában a megfelelő alkalmazások szerepelnek-e. Ha ezzel végzett, a végleges szabályzatban használhatja a **Felülbírálások elrejtése** módot.

### <a name="what-are-the-protection-modes"></a>Milyen védelmi módok lehetségesek?

#### <a name="hide-overrides"></a>Felülbírálások elrejtése
A WIP figyeli a nem megfelelő adatmegosztási gyakorlatot, és megakadályozza, hogy a felhasználó elvégezze az adott műveletet. Ilyen gyakorlat lehet, ha nem céges védelem alatt álló alkalmazásokkal osztanak meg információt, vagy ha a munkahelyén kívüli személyekkel és eszközökkel osztanak meg céges adatokat.

#### <a name="allow-overrides"></a>Felülbírálások engedélyezése
A WIP figyeli a nem megfelelő adatmegosztásokat, és figyelmezteti a felhasználót az esetlegesen nem biztonságos tevékenységre. Ebben a módban azonban a felhasználónak lehetősége van a szabályzat felülbírálásával megosztani az adatokat, a tevékenység pedig megjelenik a műveleti naplóban.

#### <a name="silent"></a>Csendes
A WIP csendes módban üzemel, és úgy naplózza a nem megfelelő adatmegosztásokat, hogy nem akadályozza meg azokat a tevékenységeket, amelyek esetében a Felülbírálások engedélyezése módban figyelmeztetések jelennének meg a felhasználó számára. A nem engedélyezett műveletek azonban továbbra is tiltva vannak, például hálózati erőforrások vagy WIP-védelem alatt álló adatok nem megfelelő elérése.

#### <a name="off-not-recommended"></a>Kikapcsolva (nem ajánlott)
A WIP ki van kapcsolva, így nem védi és nem naplózza az adatokat.

A WIP kikapcsolása után a rendszer megkísérli visszafejteni a WIP-címkével ellátott fájlokat a csatlakoztatott helyszíni meghajtókon. Vegye figyelembe, hogy a WIP-védelem újbóli bekapcsolásakor a korábbi visszafejtési és szabályzatinformációk nem lesznek automatikusan újra alkalmazva.

### <a name="add-a-protection-mode"></a>Védelmi mód hozzáadása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd válassza a **Kötelező beállítások** lehetőséget.

    ![A tanulási mód képernyőképe](./media/learning-mode-sc1.png)

1.  Válassza a **Mentés** elemet.

### <a name="use-wip-learning"></a>A WIP Learning használata

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** lehetőséget. A szövegmezőbe írja be az **Intune** szót.

3. Válassza az **Intune** > **Mobilalkalmazások** elemet.

4. Válassza az **Alkalmazásvédelem állapota** > **Jelentések** > **Windows Information Protection Learning** elemet.  
 
    A WIP Learning naplójelentésében szereplő alkalmazásokat ezután exportálhatja az alkalmazásvédelmi szabályzatokba.

## <a name="deploy-your-wip-app-protection-policy"></a>WIP alkalmazásvédelmi szabályzat bevezetése

> [!IMPORTANT]
> Az alábbi információk az WIP eszközregisztráció nélküli használatára vonatkoznak.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

A WIP alkalmazásvédelmi szabályzat létrehozása után a MAM használatával kell bevezetnie azt a cégnél.

1.  Az **Alkalmazásszabályzat** panelen válassza ki az újonnan létrehozott alkalmazásvédelmi szabályzatot, majd válassza a **Felhasználói csoportok** > **Felhasználói csoport hozzáadása** elemet.

    A **Felhasználói csoport hozzáadása** panelen megjelenik az Azure Active Directoryban elérhető összes felhasználói csoport listája.

1.  Válassza ki azt a csoportot, amelyre alkalmazni szeretné a szabályzatot, majd válassza a **Kiválasztás** lehetőséget a szabályzat üzembe helyezéséhez.

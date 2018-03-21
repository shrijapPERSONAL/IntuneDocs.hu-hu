---
title: "Microsoft Intune kezdőképernyő-elrendezési beállításai iOS-eszközökhöz"
titleSuffix: 
description: "Útmutató a kezdőképernyő és a Dock testreszabásához használható beállításokhoz iOS-eszközökön a Microsoft Intune-ban."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 56527da7ac8c2ed00a4b33049c8ba4ad03299976
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-home-screen-layout-settings-for-devices-running-ios"></a>Microsoft Intune kezdőképernyő-elrendezési beállításai iOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ezekkel a beállításokkal konfigurálhatja az alkalmazások és mappák elrendezését az iOS-eszközök kezdőképernyőjén és a Dockban.

A hozzárendelt profillal rendelkező iOS-eszközöknek felügyelt módban kell lenniük, és az iOS legalább 9.3-as verzióját kell futtatniuk.

1. Az [Intune az Azure Portalon](https://portal.azure.com) felületről lépjen az eszközkonfigurációs terület [**Eszközfunkciók** részére](device-features-configure.md).
2. Az **Eszközfunkciók** panelen válassza a **Kezdőképernyő-elrendezés (csak felügyelt)** lehetőséget.
3. A **Kezdőképernyő-elrendezés (csak felügyelt)** panelen válassza ki, hogy a **Dock** vagy a **Lapok** elrendezését kívánja-e konfigurálni.

## <a name="add-items-to-the-dock"></a>Elemek hozzáadása a Dockhoz

A **Dock** panelen legfeljebb 6 elemet vagy mappát adhat hozzá az iOS-képernyőn elhelyezkedő Dockhoz. Sok eszköz azonban ennél kevesebb elemet enged meg, az iPhone-eszközök például csak négy elem elhelyezését támogatják. Ebben az esetben csak az első négyként konfigurált elemek jelennek meg az eszközön.

1. A **Hozzáadás** választásával adhat elemeket a Dockhoz.
2. A **Sor hozzáadása** panelen válassza ki, hogy **Alkalmazást** vagy **Mappát** kíván-e hozzáadni.
3. Az ebben a témakörben található információk alapján konfigurálja, hogy milyen alkalmazásokat és mappákat szeretne megjeleníteni a Dockban.
4. Folytassa az elemek hozzáadását. Ha elkészült, kattintson minden panelen az **OK** gombra, míg vissza nem tér a **Profil létrehozása** panelre. Válassza a **Létrehozás** lehetőséget.

>[!TIP]
> A kezdőképernyő és a lapok listáin húzással rendezheti át az elemek sorrendjét.

### <a name="example"></a>Példa

Ebben a példában úgy konfiguráltuk a Dockot, hogy csak a Safari, Mail és Stock alkalmazások jelenjenek meg rajta. A következő ábrán a Mail alkalmazás ki van jelölve, hogy megjelenjenek a tulajdonságai:

![Példa iOS Dock beállításokra](./media/FfFiUcP.png)

Ha a szabályzatot egy iPhone-eszközhöz társítja, akkor az eredmény az alábbi képernyőképen láthatóhoz hasonló Dock lesz:

![Példa iOS Dock elrendezésére iPhone-eszközön](./media/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Kezdőképernyő-lapok hozzáadása

Adja meg a kezdőképernyőn megjeleníteni kívánt lapokat és az egyes lapokon megjelenő alkalmazásokat. Az egyes lapokhoz adott alkalmazások balról jobbra jelennek meg, a listában megadott sorrendben. Ha több alkalmazást ad hozzá, mint amennyi a lapon elfér, akkor azok egy következő lapra kerülnek át.

1. A **Lapok** panelen válassza a **Hozzáadás** lehetőséget.
2. A **Sor hozzáadása** panelen írjon be egy **Lapnevet**. Ez a név arra való, hogy az Azure Portalon hivatkozzon rá, és *nem jelenik meg* az iOS-eszközön.
3. Válassza a **Hozzáadás** lehetőséget, majd válassza ki, hogy **Alkalmazást** vagy **Mappát** kíván hozzáadni a laphoz.
4. Az ebben a témakörben található információk alapján konfigurálja, hogy milyen alkalmazásokat és mappákat szeretne megjeleníteni a lapon.

### <a name="example"></a>Példa

Ebben a példában egy **Contoso** elnevezésű új lapot konfiguráltunk. A lapon csak a Barátok keresése és a Beállítások alkalmazás látható. A következő ábrán a Beállítások alkalmazás ki van jelölve, hogy megjelenjenek a tulajdonságai:

![Példa iOS-kezdőképernyő beállítására](./media/Jc2OxyX.png)

Ha a szabályzatot egy iPhone-eszközhöz társítja, akkor az eredmény az alábbi képernyőképen láthatóhoz hasonló lap lesz:

![iOS-eszköz módosított kezdőképernyővel](./media/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Alkalmazás hozzáadása a listához

1. Írjon be egy **Alkalmazásnevet**. Ez a név arra való, hogy az Azure Portalon hivatkozzon rá, és *nem jelenik meg* az iOS-eszközön.
2. Adja meg a megjeleníteni kívánt alkalmazás **csomagazonosítóját**. További információt az alább található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.
3. Kattintson az **OK** gombra, majd folytassa az elemek hozzáadását a Dock esetében legfeljebb **6**, lapok esetében legfeljebb **60** elemig.
4. Amikor végzett, kattintson az **OK**gombra.

## <a name="how-to-add-a-folder-to-the-list"></a>Mappa hozzáadása a listához

Az egyes lapokhoz egy mappában hozzáadott alkalmazások balról jobbra jelennek meg a listában megadott sorrendben. Ha több alkalmazást ad hozzá, mint amennyi a lapon elfér, akkor azok egy következő lapra kerülnek át.

1. Írja be a **Mappanevet**. Ez a név jelenik meg az eszközön a felhasználók számára.
2. A **Hozzáadás** választásával hozzon létre egy lapot a mappában. Legfeljebb 20 lapot adhat hozzá.
3. A **Sor hozzáadása** panelen írjon be egy nevet a laphoz. Ez a név arra való, hogy az Azure Portalon hivatkozzon rá, és *nem jelenik meg* az iOS-eszközön.
3. Írjon be egy **Alkalmazásnevet**. Ez a név arra való, hogy az Azure Portalon hivatkozzon rá, és *nem jelenik meg* az iOS-eszközön.
2. Adja meg a megjeleníteni kívánt alkalmazás **csomagazonosítóját**. Útmutatást kaphat az **Alkalmazás hozzáadása a listához** című szakaszban.
3. Válassza a **Hozzáadás** lehetőséget. Legfeljebb 60 elemet adhat hozzá.
4. Amikor végzett, kattintson az **OK**gombra.


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Csomagazonosító-referencia beépített iOS-alkalmazásokhoz

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, lépjen kapcsolatba a szoftver gyártójával.

|||
|-|-|
|Alkalmazás neve|Csomagazonosító|
|Alkalmazásáruház|com.apple.AppStore|
|Számológép|com.apple.calculator|
|Naptár|com.apple.mobilecal|
|Fényképezőgép|com.apple.camera|
|Óra|com.apple.mobiletimer|
|Iránytű|com.apple.compass|
|Névjegyek|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Barátok keresése|com.apple.mobileme.fmf1|
|iPhone keresése|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Állapot|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Térképek|com.apple.Maps|
|Üzenetek|com.apple.MobileSMS|
|Zene|com.apple.Music|
|Hírek|com.apple.news|
|Megjegyzések|com.apple.mobilenotes|
|Számok|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotók|com.apple.mobileslideshow|
|Podcastok|com.apple.podcasts|
|Emlékeztetők|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Beállítások|com.apple.Preferences|
|Részvények|com.apple.stocks|
|Tippek|com.apple.tips|
|Videók|com.apple.videos|
|Hangjegyzetek|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Időjárás|com.apple.weather|


## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).

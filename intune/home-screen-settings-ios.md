---
title: "Intune kezdőképernyő-elrendezési beállítások iOS-eszközökhöz"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Útmutató a kezdőképernyő és a Dock testreszabásához használható beállításokhoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7743573ab893b7d54c11e183133fa02368c00779
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Intune kezdőképernyő-elrendezési beállítások iOS-eszközökhöz

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ezekkel a beállításokkal konfigurálható az alkalmazások, mappák és webes videóklipek elrendezése mindazon iOS-eszközök kezdőképernyőjén és Dock sávján, amelyekhez társítja a szabályzatot.

Az iOS-eszközöknek, amelyekhez a profilt társítja, felügyelt módban kell lenniük, és az iOS legalább 9.3-as verzióját kell futtatniuk.

1. Az **Eszközfunkciók** panelen válassza a **Kezdőképernyő-elrendezés (csak felügyelt)** lehetőséget.
2. A **Kezdőképernyő-elrendezés (csak felügyelt)** panelen válassza ki, hogy a **Dock** vagy a **Lapok** elrendezését kívánja konfigurálni.

## <a name="add-items-to-the-dock"></a>Elemek hozzáadása a Dockhoz

A **Dock** panelen legfeljebb 6 elemet vagy mappát adhat hozzá az iOS képernyő alján elhelyezkedő Dockhoz. Sok eszköz ennél kevesebb elemet enged meg, az iPhone-eszközök például csak 4 elem elhelyezését támogatják. Ebben az esetben csak az első négyként konfigurált elemek jelennek meg az eszközön.

1. A **Hozzáadás** választásával adhat elemeket a Dockhoz.
2. A **Sor hozzáadása** panelen válassza ki, hogy **Alkalmazást** vagy **Mappát** kíván hozzáadni.
3. Konfigurálja a Dockon megjeleníteni kívánt alkalmazásokat és mappákat e témakör **Alkalmazás hozzáadása a listához** és **Mappa hozzáadása a listához** című szakaszai alapján.
4. Folytassa az elemek hozzáadását. Amikor elkészült, kattintson minden panelen az **OK** gombra, míg vissza nem tér a **Profil létrehozása** panelre. Válassza a **Létrehozás** lehetőséget.

>[!TIP]
> A kezdőképernyő és a lapok listáin húzással rendezheti át az elemek sorrendjét. 

### <a name="example"></a>Példa

Ebben a példában úgy konfiguráltuk a Dockot, hogy csak a Safari, Mail és Stock alkalmazások jelenjenek meg rajta. A következő ábrán a Mail alkalmazás ki van jelölve, hogy megjelenjenek a tulajdonságai:

![Példa iOS Dock beállításokra](http://i.imgur.com/FfFiUcP.png)

Ha a szabályzatot egy iPhone-eszközhöz társítja, akkor az eredmény az alábbihoz hasonló Dock lesz:

![Példa iOS Dock elrendezésére iPhone-eszközön](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Kezdőképernyő-lapok hozzáadása

Adja meg a kezdőképernyőn megjeleníteni kívánt lapokat és az egyes lapokon megjelenő alkalmazásokat. Az egyes lapokhoz adott alkalmazások balról jobbra jelennek meg, a listában megadott sorrendben. Ha több alkalmazást ad hozzá, mint amennyi a lapon elfér, akkor azok egy következő lapra kerülnek át.


1. A **Lapok** panelen válassza a **Hozzáadás** lehetőséget.
2. A **Sor hozzáadása** panelen írjon be egy **Lapnevet**. Ez arra való, hogy az Intune-portálon hivatkozzon rá, és *nem jelenik meg* az iOS eszközön.
3. Válassza a **Hozzáadás** lehetőséget, majd válassza ki, hogy **Alkalmazást** vagy **Mappát** kíván hozzáadni a laphoz.
4. Konfigurálja a lapon megjeleníteni kívánt alkalmazásokat és mappákat e témakör **Alkalmazás hozzáadása a listához** és **Mappa hozzáadása a listához** című szakaszai alapján.

### <a name="example"></a>Példa

Ebben a példában egy **Contoso** elnevezésű új lapot konfiguráltunk. A lapon csak a Barátok keresése és a Beállítások alkalmazás látható. A következő ábrán a Beállítások alkalmazás ki van jelölve, hogy megjelenjenek a tulajdonságai:

![Példa iOS-kezdőképernyő beállítására](http://i.imgur.com/Jc2OxyX.png)

Ha a szabályzatot egy iPhone-eszközhöz társítja, akkor az eredmény az alábbihoz hasonló lap lesz:

![iOS-eszköz módosított kezdőképernyővel](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Alkalmazás hozzáadása a listához

1. Írjon be egy **Alkalmazásnevet**. Ez arra való, hogy az Intune-portálon hivatkozzon rá, és *nem jelenik meg* az iOS eszközön.
2. Adja meg a megjeleníteni kívánt alkalmazás **csomagazonosítóját**. További információt az alább található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.
3. Kattintson az **OK** gombra, majd folytassa az elemek hozzáadását a Dock esetében legfeljebb **6**, lapok esetében legfeljebb **60** elemig.
4. Amikor végzett, kattintson az **OK**gombra.

## <a name="how-to-add-a-folder-to-the-list"></a>Mappa hozzáadása a listához

Az egyes lapokhoz egy mappában hozzáadott alkalmazások balról jobbra jelennek meg a listában megadott sorrendben. Ha több alkalmazást ad hozzá, mint amennyi a lapon elfér, akkor azok egy következő lapra kerülnek át.

1. Írja be a **Mappanevet**. Ez jelenik meg az eszközön a felhasználók számára.
2. A **Hozzáadás** választásával hozzon létre egy lapot a mappában. Legfeljebb 20 lapot adhat hozzá.
3. A **Sor hozzáadása** panelen írjon be egy nevet a laphoz. Ez arra való, hogy az Intune-portálon hivatkozzon rá, és *nem jelenik meg* az iOS eszközön.
3. Írjon be egy **Alkalmazásnevet**. Ez arra való, hogy az Intune-portálon hivatkozzon rá, és *nem jelenik meg* az iOS eszközön.
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



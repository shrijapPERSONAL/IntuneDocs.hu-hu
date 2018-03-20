---
title: "Alkalmazásértesítések létrehozása iOS-eszközökre – Microsoft Intune – Azure | Microsoft Docs"
description: "A Microsoft Intune-ban hozzáadhat vagy létrehozhat alkalmazásértesítéseket iOS-eszközök számára. Kiválaszthatja, mely alkalmazások küldjenek értesítéseket, konfigurálhatja a zárolási képernyő értesítési beállításait, engedélyezheti a hangot, kiválaszthatja az értesítés típusát és jelvényt adhat hozzá."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 018a04bd674e4f270ed2e356c08825ab1d5878da
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2018
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>iOS-eszközök alkalmazásértesítési beállításainak konfigurálása az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Konfigurálhatja, hogyan küldenek értesítéseket az iOS-eszközön telepített alkalmazások. Ezek a beállítások az iOS 9.3-at vagy újabb verziót futtató felügyelt eszközökön vannak támogatva.

## <a name="add-the-app-notification"></a>Az alkalmazásértesítés hozzáadása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Az iOS- vagy macOS-profilon válassza az **Eszközfunkciók** lehetőséget. Az [iOS- vagy macOS eszközök funkciói](device-features-configure.md) szakaszban megtekintheti a profil létrehozásának lépéseit.
3. Válassza az **Alkalmazásértesítések (csak felügyelt)** lehetőséget, majd a **Hozzáadás**: ![Alkalmazásértesítés hozzáadása iOS- vagy macOS-profilban az Intune-ban](./media/ios-macos-app-notifications.png) lehetőséget
4. Adja meg a következő tulajdonságokat:

  - **Alkalmazás csomagazonosítója** – Adja meg a konfigurálni kívánt alkalmazás **csomagazonosítóját**. Segítséget a jelen cikkben található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.
  - **Alkalmazásnév** – Adja meg a konfigurálni kívánt alkalmazás nevét. A név nem jelenik meg az eszközön, és arra szolgál, hogy az alkalmazás könnyebben megtalálható legyen a listában.
  - **Kiadó** – Adja meg a konfigurálni kívánt alkalmazás kiadójának nevét. A közzétett név nem jelenik meg az eszközön, és arra szolgál, hogy az alkalmazás könnyebben megtalálható legyen a listában.
  - **Értesítések** – Engedélyezi vagy tiltja, hogy az alkalmazás értesítéseket küldjön az eszközre. Ha ezt letiltja, a következő beállítások szintén le lesznek tiltva.
    - **Megjelenítés az Értesítési központban** – Ha engedélyezi ezt a beállítást, az alkalmazás értesítéseket jeleníthet meg az Értesítési központban.
    - **Megjelenítés a zárolási képernyőn** – Ha engedélyezi ezt a beállítást, az eszköz zárolási képernyőjén üzenetek jelenhetnek meg.
    - **Riasztás típusa** – Válassza ki, hogy az alábbiak közül milyen típusú értesítések jelenjenek meg az eszköz zárolásának feloldásakor:
      - **Egyik sem** – Nem jelennek meg értesítések.
      - **Szalagcím** – Egy szalagcím jelenik meg rövid időre az értesítés szövegével.
      - **Modális** – Az üzenetet a felhasználónak manuálisan kell bezárnia, mielőtt használni tudná az eszközt.
    - **Jelvény az alkalmazásikonon** – Ha engedélyezi ezt a beállítást, az alkalmazásikonon egy üzenetet jelző jelvény jelenik meg.
    - **Hangok** – Ha engedélyezi ezt a beállítást, az értesítés kézbesítését hang kíséri.

5. Folytassa, amíg hozzá nem adta az összes kívánt beállítást. Ha hozzáadta az alkalmazásokat, kattintson az **OK** gombra.
6. Válassz a **Létrehozás** elemet a profil mentéséhez.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Csomagazonosító-referencia beépített iOS-alkalmazásokhoz

Az alábbi listában néhány gyakori beépített iOS-alkalmazás csomagazonosítóját ismertetjük. Ha más alkalmazás csomagazonosítóját szeretné megismerni, ajánlott kapcsolatba lépni a szoftver gyártójával.

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

Rendelje hozzá az eszközprofilt a kiválasztott csoportokhoz. Ehhez az [Eszközprofilok hozzárendelése](device-profile-assign.md) című témakörben találhat segítséget.
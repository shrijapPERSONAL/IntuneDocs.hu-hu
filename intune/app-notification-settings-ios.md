---
title: "Intune alkalmazásértesítési beállítások iOS-eszközökhöz"
titlesuffix: Azure portal
description: "Ez a témakör az iOS-es eszközökre telepített alkalmazások értesítéseit szabályzó beállításokat ismerteti."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b87ffad8ee005fd8a164ec2891d81e19fb005a8b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>Intune alkalmazásértesítési beállítások iOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az eszközre telepített alkalmazások értesítésküldési módját állíthatja be. Ezek a beállítások az iOS 9.3-at vagy újabb verziót futtató felügyelt eszközökön vannak támogatva.

## <a name="configure-settings"></a>Beállítások konfigurálása

1. Az Eszközfunkciók panelen válassza az **Alkalmazásértesítések (csak felügyelt)** lehetőséget.
2. Az **Alkalmazásértesítések** panelen válassza a **Hozzáadás** lehetőséget, majd konfigurálja az alábbi értékeket:
    - **Alkalmazás csomagazonosítója** – Adja meg a konfigurálni kívánt alkalmazás **csomagazonosítóját**. További információt az alább található **Csomagazonosító-referencia beépített iOS-alkalmazásokhoz** című szakaszban talál.
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
3. Folytassa, amíg hozzá nem adta az összes kívánt beállítást. Ha elkészült, válassza az **OK** elemet.
4. Válassza az **OK** lehetőséget annyiszor, amíg vissza nem tér a **Profil létrehozása** panelhez, majd válassza a **Létrehozás** elemet. 


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

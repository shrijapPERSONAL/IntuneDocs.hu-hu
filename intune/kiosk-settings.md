---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A cikk tájékoztatást nyújt a Microsoft Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a Windows 10 rendszerű eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 897ff48253961d6e1aa83bf36113c362d4548fbf
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745148"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Kioszkbeállítások Windows 10 (és újabb) rendszerekhez az Intune-ban

A kioszkprofilokkal konfigurálhatók a Windows 10-eszközök, hogy egy vagy több alkalmazást futtassanak. Kioszkprofil konfigurálásakor kiválaszthatja, hogy megjelenjen-e a Start menü, legyen-e telepítve webböngésző, és további beállításokat adhat meg.

## <a name="kiosk-settings"></a>Kioszkbeállítások

1. Kioszkkörnyezet létrehozásához válassza a **Hozzáadás** lehetőséget.
2. Adjon meg egy **Kioszkkonfigurációs nevet** a kioszkmódhoz. Ez a név azonosítja az alkalmazások csoportját, ezeknek az alkalmazásoknak az elrendezését a Start menüben, és a kioszkkonfigurációhoz hozzárendelt felhasználókat.
3. Válassza a **Kioszkmód** lehetőséget. **Kioszkmód** Azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezés): A szabályzat nem engedélyezi a teljes képernyős módot.
  - **Egyetlen teljes képernyős alkalmazásos kioszk**: A profil lehetővé teszi, hogy az eszköz egyetlen felhasználói fiókként fusson, és egyetlen Univerzális Windows-platformbeli (UWP) alkalmazáshoz zárolja azt. Ezért, amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk**: A profil lehetővé teszik több Univerzális Windows-platformbeli (UWP) alkalmazás vagy Win32-es alkalmazások futtatását. Különböző alkalmazásokat különböző felhasználói fiókokhoz is hozzárendelhet. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználóknak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználóknak, amelyben csak a szükséges alkalmazások érhetőek el. A szükségtelen alkalmazásokat pedig elrejti.

#### <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Adja meg a következő beállításokat:

- **Univerzális Windows Platform (UWP) alkalmazásazonosító**: Adja meg a kioszkalkalmazás számára **Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)** értékét. Vagy válasszon ki egy, a [Mobile Apps](apps-add.md) használatával már hozzáadott, felügyelt alkalmazást.

    Lásd: [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése).

- **Felhasználói fiók típusa**: A választható lehetőségek:

  - **Automatikus bejelentkezés**: Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználót (például egyszerű helyi felhasználói fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `AzureAD\user@contoso.com` formátumot.
  - **Helyi felhasználói fiók**: Adja meg a kioszkalkalmazáshoz társított helyi (eszközön létező) felhasználói fiókot, vagy a Microsoft Azure Active Directory-fiókot. Azure AD-tartományhoz csatlakozó fiókot a következő formában tud megadni: `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk
Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni. 

A [többalkalmazásos kioszkeszközök](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) olyan kioszkkonfigurációt használnak, amely más beállítások mellett tartalmazza az engedélyezett alkalmazások listáját.

Adja meg a következő beállításokat:

- **Win32-alkalmazás hozzáadása**: A Win32-alkalmazás hagyományos asztali alkalmazás. Adja meg az **Alkalmazásnév** és az **Azonosító** értékét. Az **Azonosító** a végrehajtható fájl teljes elérési útja az eszközön.
- **Felügyelt alkalmazások hozzáadása**: Válasszon ki egy, az [Intune-beli Mobile Apps](apps-add.md) használatával már hozzáadott, felügyelt alkalmazást.
- **Alkalmazás hozzáadása AUMID alapján**: Adja meg az [alkalmazás AUMID azonosítóját](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-alkalmazások).
- **Tálca** – Válassza az **Engedélyezés** beállítást a tálca megjelenítéséhez, vagy hagyja meg az alapértelmezett **Nincs konfigurálva** beállítást a tálca kioszkeszközön való elrejtéséhez.
- **Start menü elrendezése**: Adjon meg egy XML-fájlt, amely meghatározza, hogyan jelenjenek meg az alkalmazások a Start menüben, beleértve azok sorrendjét. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

  Az XML-fájlok használatáról és létrehozásáról bővebb információt a [Több alkalmazást futtató Windows 10 rendszerű kioszk létrehozása](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) című cikkben találhat.

- **Felhasználói fiók típusa**: Adjon meg egy vagy több olyan felhasználói fiókot, amely jogosult a társított alkalmazások használatára. A fiókkal való bejelentkezéskor csak a konfigurációban meghatározott alkalmazások érhetők el. Ez lehet egy helyi fiók az eszközön, vagy egy Microsoft Azure Active Directory-fiók, amely a teljes képernyős alkalmazáshoz van társítva.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `domain\user@tenant.com` formátumot.

## <a name="kiosk-web-browser-settings"></a>Teljes képernyős böngészőbeállítások megadása

Ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Győződjön meg róla, hogy üzembe helyezett egy böngészőalkalmazást a kioszkmódban lévő eszközökön a [Mobile Apps](apps-add.md) használatával.

1. Adja meg a következő beállításokat:

  - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-címet, amelyet a teljes képernyős böngésző megnyit indításkor vagy újraindításkor.

  - **A Kezdőlap gomb megjelenítése**: A teljes képernyős böngésző Kezdőlap gombjának megjelenítése (**Kötelező**) vagy elrejtése (**Nincs konfigurálva**). Alapértelmezés szerint a gomb nincs konfigurálva.

  - **Navigációs gomb megjelenítése**: Az előre és vissza gombok megjelenítése (**Kötelező**) vagy elrejtése (**Nincs konfigurálva**). A navigációs gombok alapértelmezés szerint nincsenek konfigurálva.

  - **Böngésző frissítése, ha a felhasználó túllépi az inaktivitási időkorlátot**: Adja meg a munkamenet üresjárati idejét percben, amelynek elteltével a teljes képernyős böngésző friss állapotban újraindul. Az érték 1 és 1440 közötti egész szám. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

  - **Letiltott webhelyek**: A letiltott webhelyek URL-címeinek listája (a helyettesítő karakterek használata megengedett). Ezzel a beállítással megakadályozhatja, hogy a böngésző adott webhelyeket nyisson meg. **Importálhat** is egy listát tartalmazó .csv-fájlt. Vagy hozzon létre egy .csv-fájlt (**Exportálás**), amely tartalmazza a felvett webhelyeket.

  - **Engedélyezett webhelyek**: Kivétellista a blokkolt webhelyek URL-címeihez (helyettesítő karakterek használata megengedett). Ezzel a beállítással engedélyezheti a böngészőnek meghatározott webhelyek megnyitását. Ezek a kivételek a blokkolt URL-címek részhalmazába tartoznak. Ha egy URL-cím megtalálható a blokkolt webhelyek listájában és a webhelyek kivétellistájában, akkor a kivételszabály lesz rá érvényes.

    **Importálhat** is egy listát tartalmazó .csv-fájlt. Vagy hozzon létre egy .csv-fájlt (**Exportálás**), amely tartalmazza a felvett webhelyeket.

2. A módosítások mentéséhez válassza az **OK** gombot.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
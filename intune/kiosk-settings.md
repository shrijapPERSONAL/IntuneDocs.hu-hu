---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Windows 10 (és újabb) rendszerű eszközét egyalkalmazásos és többalkalmazásos kioszkeszközként konfigurálhatja, beleértve a Start menü testreszabását, alkalmazások hozzáadását, a tálcát és egy webböngésző konfigurálását. A Microsoft Intune-ban Windows Holographic for Business rendszerű eszközöket is konfigurálhat többalkalmazásos kioszkként.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6db58b1b1f19f789a2163f497c1f0da4c7c034a5
ms.sourcegitcommit: 5f6117b83f96f7d93dde3685c2ff2b67ae53740b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2018
ms.locfileid: "39481121"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Kioszkbeállítások Windows 10 (és újabb) rendszerekhez az Intune-ban

A Windows 10-eszközök kioszkprofilokkal vannak konfigurálva egy vagy több alkalmazás futtatására. Kioszkprofil létrehozásakor kiválaszthatja, hogy megjelenjen-e a Start menü, legyen-e telepítve webböngésző, és további beállításokat adhat meg.

## <a name="kiosk-settings"></a>Kioszkbeállítások

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Leírás:** Itt adhatja meg a profil leírását. Nem kötelező, de ajánlott a használata.
   - **Platform**: Válassza a **Windows 10 és újabb** lehetőséget.
   - **Profil típusa**: Válassza a **Kioszk (Előnézet)** lehetőséget.
   
4. Válassza ki a **Kioszk** > **Hozzáadás** lehetőséget.
5. Adjon meg egy **Kioszkkonfigurációs nevet** a kioszkmódhoz. Ez a név azonosítja az alkalmazások csoportját, ezeknek az alkalmazásoknak az elrendezését a Start menüben, és a kioszkkonfigurációhoz hozzárendelt felhasználókat.
6. Válassza a **Kioszkmód** lehetőséget. A **Kioszkmód** azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

    - **Nincs konfigurálva** (alapértelmezés): A szabályzat nem engedélyezi a kioszkmódot.
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

    - **Kezdőlap gomb**: A teljes képernyős böngésző Kezdőlap gombjának megjelenítése (**Engedélyezés**) vagy elrejtése (**Nincs konfigurálva**). Alapértelmezés szerint a gomb nincs konfigurálva.

    - **Navigációs gomb**: Az előre és vissza gombok megjelenítése (**Engedélyezés**) vagy elrejtése (**Nincs konfigurálva**). A navigációs gombok alapértelmezés szerint nincsenek konfigurálva.

    - **Munkamenet befejezése gomb**: A munkamenet befejezése gomb megjelenítése (**Engedélyezés**) vagy elrejtése (**Nincs konfigurálva**). Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, és visszatér az alapértelmezett URL-címre. Alapértelmezés szerint a gomb nincs konfigurálva. 

    - **Böngésző frissítése, ha a felhasználó túllépi az inaktivitási időkorlátot**: Adja meg a munkamenet üresjárati idejét percben, amelynek elteltével a teljes képernyős böngésző friss állapotban újraindul. Az érték 1 és 1440 közötti egész szám. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

    - **Letiltott webhelyek**: A letiltott webhelyek URL-címeinek listája (a helyettesítő karakterek használata megengedett). Ezzel a beállítással megakadályozhatja, hogy a böngésző adott webhelyeket nyisson meg. **Importálhat** is egy listát tartalmazó .csv-fájlt. Vagy hozzon létre egy .csv-fájlt (**Exportálás**), amely tartalmazza a felvett webhelyeket.

    - **Engedélyezett webhelyek**: Kivétellista a blokkolt webhelyek URL-címeihez (helyettesítő karakterek használata megengedett). Ezzel a beállítással engedélyezheti a böngészőnek meghatározott webhelyek megnyitását. Ezek a kivételek a blokkolt URL-címek részhalmazába tartoznak. Ha egy URL-cím megtalálható a blokkolt webhelyek listájában és a webhelyek kivétellistájában, akkor a kivételszabály lesz rá érvényes.

    **Importálhat** is egy listát tartalmazó .csv-fájlt. Vagy hozzon létre egy .csv-fájlt (**Exportálás**), amely tartalmazza a felvett webhelyeket.

2. A módosítások mentéséhez válassza az **OK** gombot.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business rendszerű eszközök egyalkalmazásos vagy többalkalmazásos kioszkmódban való használatra is konfigurálhatók. 

#### <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Adja meg a következő beállításokat:

- **Univerzális Windows Platform (UWP) alkalmazásazonosító**: Adja meg a kioszkalkalmazás számára **Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)** értékét. Vagy válasszon ki egy, a [Mobile Apps](apps-add.md) használatával már hozzáadott, felügyelt alkalmazást.

    Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.

- **Felhasználói fiók típusa**: Válassza a **Helyi felhasználói fiók** lehetőséget, és adja meg a kioszkalkalmazáshoz társított helyi (eszközön létező) felhasználói fiókot vagy Microsoft Account (MSA) fiókot. Az **Automatikus bejelentkezésű** felhasználói fiókokat a Windows Holographic for Business nem támogatja.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk
Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni.

Adja meg a következő beállításokat:

- **Felügyelt alkalmazások hozzáadása**: Válasszon ki egy, az [Intune-beli Mobile Apps](apps-add.md) használatával már hozzáadott, felügyelt alkalmazást.
- **Alkalmazás hozzáadása AUMID alapján**: Adja meg az [alkalmazás AUMID azonosítóját](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-alkalmazások).
- **Start menü elrendezése**: Adjon meg egy XML-fájlt, amely meghatározza, hogyan jelenjenek meg az alkalmazások a Start menüben, beleértve azok sorrendjét. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) című cikk nyújt némi útmutatást, és tartalmaz egy kimondottan Windows Holographic for Business rendszerű eszközökhöz készült XML-fájlt.
- **Felhasználói fiók típusa**: Adjon meg egy vagy több olyan felhasználói fiókot, amely jogosult a társított alkalmazások használatára. A támogatott lehetőségek a következők: 
  - **HoloLens vendég**: Ehhez a vendégfiókhoz [A megosztott számítógép üzemmód alapelvei](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) című szakaszban ismertetettek alapján nem szükségesek hitelesítő adatok.
  - **Azure AD-felhasználók**: Az eszközre való bejelentkezéshez hitelesítő adatokra van szükség. Használja a következő formátumot: `domain\user@tenant.com`.
  - **Helyi felhasználói fiókok**: Az eszközre való bejelentkezéshez hitelesítő adatokra van szükség. 

A fiókkal való bejelentkezéskor csak a konfigurációban meghatározott alkalmazások érhetők el.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

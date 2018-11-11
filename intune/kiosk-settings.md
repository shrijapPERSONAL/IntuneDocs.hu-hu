---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Windows 10 (és újabb) rendszerű eszközét egyalkalmazásos és többalkalmazásos kioszkeszközként konfigurálhatja, beleértve a Start menü testreszabását, alkalmazások hozzáadását, a tálcát és egy webböngésző konfigurálását. A Microsoft Intune-ban Windows Holographic for Business rendszerű eszközöket is konfigurálhat többalkalmazásos kioszkként.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b3de4d79e6121505718a75ffe64102bb1bc18347
ms.sourcegitcommit: 244456907e3ab4a4389d32d06060606a9591cfba
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2018
ms.locfileid: "50751643"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Kioszkbeállítások Windows 10 (és újabb) rendszerekhez az Intune-ban

A Windows 10-eszközökön az Intune segítségével ezeket az eszközöket kioszk módban futtathatja. A kioszk futtathat egyetlen alkalmazást, vagy többet. Emellett megjelenítheti és testre szabhatja a Start menüt, hozzáadhat különböző alkalmazásokat, beleértve a Win32-alkalmazásokat, egy adott kezdőlapot adhat egy webböngészőhöz és így tovább. 

A cikk ezen lépéseit követve egyalkalmazásos kioszkot vagy többalkalmazásos kioszkot hozhat létre az Intune-ban.

Az Intune eszközönként egy kioszkprofilt támogat. Ha egy adott eszközön több kioszkprofilra van szüksége, használhat egy [egyéni OMA-URI](custom-settings-windows-10.md)-t.

## <a name="kiosk-settings"></a>Kioszkbeállítások

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Leírás:** Itt adhatja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza a **Windows 10 és újabb** lehetőséget.
   - **Profil típusa**: Válassza a **Kioszk (Előnézet)** lehetőséget.

4. Válasszon egy **kioszkmódot**. A **Kioszkmód** azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

    - **Nincs konfigurálva** (alapértelmezés): A szabályzat nem engedélyezi a kioszkmódot.
    - **Egyalkalmazásos, teljes képernyős kioszk**: az eszköz egyetlen felhasználói fiókkal fut, és egyetlen Áruházbeli alkalmazásra van korlátozva. Ezért, amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
    - **Többalkalmazásos kioszk**: az eszköz több Áruházbeli alkalmazást, Win32-alkalmazást vagy postaláda Windows-alkalmazást futtat az alkalmazásfelhasználói modellben használt azonosító (AUMID) használatával. Az eszközön csak a hozzáadott alkalmazások lesznek elérhetők.

        A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználóknak, amelyben csak a szükséges alkalmazások érhetőek el. A szükségtelen alkalmazásokat pedig elrejti.

## <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Egyalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **Felhasználói bejelentkezés típusa**: a hozzáadott alkalmazások a megadott felhasználói fiókkal futnak. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10, 1803-as vagy újabb verzió)**: olyan, nyilvános környezetben működő kioszkokhoz, amelyek nem igényelnek felhasználói bejelentkezést, a vendégfiókokhoz hasonlóan. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: Adja meg a helyi (az eszközön létező) felhasználói fiókot. A megadott fiókkal történik a bejelentkezés a kioszkba.

- **Alkalmazástípus**: Válassza az **Áruházbeli alkalmazás** lehetőséget.

- **Kioszkmódban futtatni kívánt alkalmazás**: Válassza az **Áruházbeli alkalmazás hozzáadása** lehetőséget, és válasszon alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

    A módosítások mentéséhez válassza az **OK** gombot.

- **Teljes képernyős böngésző beállításai**: ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Feltétlenül szerezze be a [teljes képernyős böngészőalkalmazást](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) az Áruházból, adja hozzá az Intune-hoz [ügyfélalkalmazásként](apps-add.md), majd rendelje hozzá a kioszkeszközökhöz.

  Adja meg a következő beállításokat:

  - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-címet, amelyet a teljes képernyős böngésző indításakor vagy újraindításkor meg szeretne jeleníteni. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

  - **Kezdőlap gomb**: **Megjeleníti** vagy **elrejti** a teljes képernyős böngésző kezdőlap gombját. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Navigációs gombok**: **Megjelenítik** vagy **elrejtik** az előre és vissza gombokat. A navigációs gombok alapértelmezés szerint nem jelennek meg.

  - **Munkamenet befejezése gomb**: **Megjeleníti** vagy **elrejti** a munkamenet befejezése gombot. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

  - **A böngésző frissítése üresjárati idő után**: Adja meg az üresjárati időt (1-1440 perc), amelynek elteltével a teljes képernyős böngésző friss állapotban újraindul. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

  - **Engedélyezett webhelyek**: használja ezt a beállítást adott webhelyek megnyitásának engedélyezéséhez. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `http://contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.

    Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját tartalmazó .csv-fájlt. Ha nem ad hozzá .csv-fájlt, az összes webhely használata engedélyezve lesz. Az Intune támogatja a * (csillag) használatát helyettesítő karakterként.

  A módosítások mentéséhez válassza az **OK** gombot.

## <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni.

Többalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **S módú Windows 10-es eszközök megcélzása**: Válassza az **Igen** lehetőséget az Áruházbeli és az AUMID-alkalmazások engedélyezéséhez (a Win32-alkalmazások kizárásával) a kioszkprofilban. Válassza a **Nem** lehetőséget az áruházbeli alkalmazások, a Win32-alkalmazások és az AUMID-alkalmazások engedélyezéséhez a kioszkprofilban. Ha a **Nem** lehetőséget választja, a kioszkprofil S-módú eszközökön nem lesz üzembe helyezve.

- **Felhasználói bejelentkezés típusa**: a hozzáadott alkalmazások a megadott felhasználói fiókkal futnak. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10, 1803-as vagy újabb verzió)**: olyan, nyilvános környezetben működő kioszkokhoz, amelyek nem igényelnek felhasználói bejelentkezést, a vendégfiókokhoz hasonlóan. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: **Adja hozzá** a helyi (az eszközön létező) felhasználói fiókot. A megadott fiókkal történik a bejelentkezés a kioszkba.
  - **Azure AD-felhasználó vagy csoport (Windows 10, 1803-as vagy újabb verzió)**: Válassza a **Hozzáadás** lehetőséget Azure AD-felhasználók vagy -csoportok kiválasztásához a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens vendég**: Ehhez a vendégfiókhoz [A megosztott számítógép üzemmód alapelvei](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) című szakaszban ismertetettek alapján nem szükségesek hitelesítő adatok.

- **Alkalmazások**: Adja hozzá a kioszkmódú eszközön futtatandó alkalmazásokat. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Áruházbeli alkalmazás hozzáadása**: Alkalmazás hozzáadása a Vállalati Microsoft Áruházból. Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md). Például a teljes képernyős böngészőt, az Excelt, a OneNote-ot és egyéb alkalmazásokat is hozzáadhat.

  - **Win32-alkalmazás hozzáadása**: a Win32-alkalmazások hagyományos asztali alkalmazások, mint például a Visual Studio Code vagy a Google Chrome. Adja meg a következő tulajdonságokat:

    - **Alkalmazás neve**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Helyi elérési út**: Kötelező. Adja meg a végrehajtható fájl elérési útját, például `C:\Program Files (x86)\Microsoft VS Code\Code.exe` vagy `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Alkalmazásfelhasználói modellben használt azonosító (AUMID)**: Adja meg a Win32-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Ez a beállítás meghatározza a csempe kezdő elrendezését az asztalon. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) című témakörben leírtak alapján kereshető meg.
    - **Csempeméret**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.
  
  - **Hozzáadása AUMID alapján**: használja ezt a beállítást a postaláda Windows-alkalmazások, például a Jegyzettömb vagy a Számológép hozzáadásához. Adja meg a következő tulajdonságokat: 

    - **Alkalmazás neve**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.
    - **Csempeméret**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

  > [!TIP]
  > Miután hozzáadta az összes alkalmazást, kattintással és húzással módosíthatja a megjelenítés sorrendjét az alkalmazások listájában.  

  A módosítások mentéséhez válassza az **OK** gombot.

- **Teljes képernyős böngésző beállításai**: ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Böngészőalkalmazást a kioszkmódban lévő eszközökön az [ügyfélalkalmazások](apps-add.md) használatával kell üzembe helyeznie.

  Adja meg a következő beállításokat:

  - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-címet, amelyet a teljes képernyős böngésző indításakor vagy újraindításkor meg szeretne jeleníteni. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

  - **Kezdőlap gomb**: **Megjeleníti** vagy **elrejti** a teljes képernyős böngésző kezdőlap gombját. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Navigációs gombok**: **Megjelenítik** vagy **elrejtik** az előre és vissza gombokat. A navigációs gombok alapértelmezés szerint nem jelennek meg.

  - **Munkamenet befejezése gomb**: **Megjeleníti** vagy **elrejti** a munkamenet befejezése gombot. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

  - **A böngésző frissítése üresjárati idő után**: Adja meg az üresjárati időt (1-1440 perc), amelynek elteltével a teljes képernyős böngésző friss állapotban újraindul. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

  - **Engedélyezett webhelyek**: használja ezt a beállítást adott webhelyek megnyitásának engedélyezéséhez. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.

    Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját tartalmazó .csv-fájlt. Ha nem ad hozzá .csv-fájlt, az összes webhely használata engedélyezve lesz.

  A módosítások mentéséhez válassza az **OK** gombot.

- **Start menü alternatív elrendezésének használata**: Válassza az **Igen** lehetőséget egy XML-fájl megadásához, amely meghatározza, hogyan jelenjenek meg az alkalmazások a Start menüben, beleértve azok sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

- **Windows Tálca**: Válasszon a tálca **megjelenítése** és **elrejtése** közül. Alapértelmezés szerint a tálca nem jelenik meg.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business rendszerű eszközök egyalkalmazásos vagy többalkalmazásos kioszkmódban való használatra is konfigurálhatók. Bizonyos funkciókat a Windows Holographic for Business nem támogat.

#### <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Egyalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **Felhasználói bejelentkezés típusa**: Válassza a **Helyi felhasználói fiók** lehetőséget, és adja meg a kioszkalkalmazáshoz társított helyi (eszközön létező) felhasználói fiókot vagy Microsoft Account (MSA) fiókot. Az **Automatikus bejelentkezésű** felhasználói fiókokat a Windows Holographic for Business nem támogatja.

- **Alkalmazástípus**: Válassza az **Áruházbeli alkalmazás** lehetőséget.

- **Kioszkmódban futtatni kívánt alkalmazás**: Válassza az **Áruházbeli alkalmazás hozzáadása** lehetőséget, és válasszon alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

    A módosítások mentéséhez válassza az **OK** gombot.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk
Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni. Többalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **S módú Windows 10-es eszközök megcélzása**: válassza a **Nem** lehetőséget. Az S módot a Windows Holographic for Business nem támogatja.

- **Felhasználói bejelentkezés típusa**: Adjon meg egy vagy több olyan felhasználói fiókot, amely jogosult a társított alkalmazások használatára. A választható lehetőségek: 

  - **Automatikus bejelentkezés**: A Windows Holographic for Business nem támogatja.
  - **Helyi felhasználói fiókok**: **Adja hozzá** a helyi (az eszközön létező) felhasználói fiókot. A megadott fiókkal történik a bejelentkezés a kioszkba.
  - **Azure AD-felhasználó vagy csoport (Windows 10, 1803-as vagy újabb verzió)**: Felhasználói hitelesítő adatok szükségesek az eszközre való bejelentkezéshez. Válassza a **Hozzáadás** lehetőséget Azure AD-felhasználók vagy -csoportok kiválasztására a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens vendég**: Ehhez a vendégfiókhoz [A megosztott számítógép üzemmód alapelvei](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) című szakaszban ismertetettek alapján nem szükségesek hitelesítő adatok.

- **Alkalmazások**: Adja hozzá a kioszkmódú eszközön futtatandó alkalmazásokat. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Áruházbeli alkalmazások hozzáadása**: Válasszon az [ügyfélalkalmazások](apps-add.md) használatával már hozzáadott, felügyelt alkalmazást. Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md).
  - **Win32-alkalmazás hozzáadása**: a Windows Holographic for Business nem támogatja.
  - **Hozzáadás AUMID alapján**: használja ezt a beállítást a postaláda Windows-alkalmazások hozzáadásához. Adja meg a következő tulajdonságokat: 

    - **Alkalmazás neve**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.
    - **Csempeméret**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

- **Teljes képernyős böngésző beállításai**: a Windows Holographic for Business nem támogatja.

- **Start menü alternatív elrendezésének használata**: Válassza az **Igen** lehetőséget egy XML-fájl megadásához, amely meghatározza, hogyan jelenjenek meg az alkalmazások a Start menüben, beleértve azok sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) című cikk nyújt némi útmutatást, és tartalmaz egy kimondottan Windows Holographic for Business rendszerű eszközökhöz készült XML-fájlt.

- **Windows Tálca**: a Windows Holographic for Business nem támogatja.



## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

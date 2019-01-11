---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Egyalkalmazásos és többalkalmazásos kioszk konfigurálása a Windows 10 (és újabb) eszközöket, a start menü testreszabásához, alkalmazások hozzáadása, megjelenítése a tálcán és egy webes böngésző konfigurálása. A Microsoft Intune-ban Windows Holographic for Business rendszerű eszközöket is konfigurálhat többalkalmazásos kioszkként.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 353c18affa41e56501a76bf695f95cbe95796e99
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203467"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>A Windows 10 (és újabb) eszközbeállítások futtatása egy dedikált futtasson teljes képernyőn az Intune-nal

A Windows 10-eszközökön az Intune használatával eszközöket futtató egy teljes képernyős, más néven egy dedikált eszközök. Egy eszköz teljes képernyős módban futtathat egy alkalmazást, vagy számos alkalmazás futtatásához. Megjelenítése és a start menü testreszabásához, adja hozzá a különböző alkalmazásokat, beleértve a Win32-alkalmazások, adjon hozzá egy adott kezdőlap az egy webböngészőt, és egyéb. 

Ez a cikk és a Windows 10-es és újabb rendszerű eszközök szabályozhatja a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások használatával konfigurálja a Windows 10-eszközök kioszk módban futtatni.

Az Intune eszközönként egy kioszkprofilt támogat. Ha egy adott eszközön több kioszkprofilra van szüksége, használhat egy [egyéni OMA-URI](custom-settings-windows-10.md)-t.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](device-profile-create.md).

## <a name="kiosk-settings"></a>Kioszkbeállítások

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **a Microsoft Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza ki **Windows 10 és újabb verziók**
   - **Profil típusa**: Válassza ki **kioszk**

4. Válasszon egy **kioszkmódot**. A **Kioszkmód** azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

    - **Nincs konfigurálva** (alapértelmezett): A szabályzat nem teszi lehetővé a teljes képernyős mód.
    - **Önálló alkalmazás, a teljes képernyős**: Az eszköz fut, egyetlen felhasználói fiókkal, és lezárja az egyetlen Store alkalmazás. Ezért, amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
    - **Többalkalmazásos kioszk**: Az eszköz a több Store apps, a Win32-alkalmazások vagy a Beérkezett fájlok Windows-alkalmazások az alkalmazás felhasználói modellben használt azonosítója (AUMID) használatával futtatja. Az eszközön csak a hozzáadott alkalmazások lesznek elérhetők.

        A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználóknak, amelyben csak a szükséges alkalmazások érhetőek el. A szükségtelen alkalmazásokat pedig elrejti.

## <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Egyalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **Felhasználói bejelentkezési típus**: A hozzáadott alkalmazások futtatása a felhasználói fiókot, akkor adja meg. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10 1803-es és újabb verziók)**: A számítógépek, amelyek nem igényelnek a felhasználót, hogy jelentkezzen be, a Vendég fiók hasonló nyilvános környezetekben. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiókot. A megadott fiókkal történik a bejelentkezés a kioszkba.

- **Az alkalmazástípus**: Válassza ki **Store alkalmazás**.

- **Alkalmazás teljes képernyős módban való futásra**: Válasszon **áruházbeli alkalmazás hozzáadása**, és válasszon ki egy alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

    Válassza ki **OK** a módosítások mentéséhez.

- **Teljes képernyős böngésző beállításait**: Ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Lehet arra, hogy a [teljes képernyős böngészőalkalmazásban](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) a Store, adja hozzá az Intune-t egy [ügyfélalkalmazás](apps-add.md), majd rendelje hozzá az alkalmazást a teljes képernyős eszközökön.

  Adja meg a következő beállításokat:

  - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-cím jelenik meg, amikor a teljes képernyős böngésző megnyitja a, vagy ha a böngésző újraindítása. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

  - **Kezdőlap gombjának**: **Megjelenítés** vagy **elrejtése** a teljes képernyős böngésző home gombra. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Navigációs gombok**: **Megjelenítés** vagy **elrejtése** az előre és vissza gomb. A navigációs gombok alapértelmezés szerint nem jelennek meg.

  - **Záró munkamenet gomb**: **Megjelenítés** vagy **elrejtése** a teljes munkamenet gombra. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Üresjárati idő után frissítse a böngészőt**: Adja meg az üresjárati idő (1-1440 perc) mindaddig, amíg a teljes képernyős böngésző friss állapotban indul újra. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

  - **Engedélyezett webhelyek**: Használja ezt a beállítást, hogy az adott webhely megnyitásához. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `http://contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.
 
      Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját különböző sorokban tartalmazó fájlt. Ha nem ad hozzá fájlt, az összes webhely használata engedélyezve lesz. Az Intune támogatja a * (csillag) használatát helyettesítő karakterként.

      Az mintafájlnak a következő listához hasonlóan kell kinéznie:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Válassza ki **OK** a módosítások mentéséhez.

## <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni.

Többalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **A Windows 10 S mód eszközökön célzott**: Válasszon **Igen** áruházbeli alkalmazások és az alkalmazások AUMID (kivéve a Win32-alkalmazások) engedélyezéséhez a teljes képernyős profilban. Válassza a **Nem** lehetőséget az áruházbeli alkalmazások, a Win32-alkalmazások és az AUMID-alkalmazások engedélyezéséhez a kioszkprofilban. Ha a **Nem** lehetőséget választja, a kioszkprofil S-módú eszközökön nem lesz üzembe helyezve.

- **Felhasználói bejelentkezési típus**: A hozzáadott alkalmazások futtatása a felhasználói fiókot, akkor adja meg. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10 1803-es és újabb verziók)**: A számítógépek, amelyek nem igényelnek a felhasználót, hogy jelentkezzen be, a Vendég fiók hasonló nyilvános környezetekben. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: **Adjon hozzá** a helyi (eszközön létező) felhasználói fiók. A megadott fiókkal történik a bejelentkezés a kioszkba.
  - **Az Azure AD-felhasználó vagy csoport (Windows 10 1803-es és újabb verziók)**: Válassza a **Hozzáadás** lehetőséget Azure AD-felhasználók vagy -csoportok kiválasztására a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens-látogató**: A látogatói egy a Vendég fiók felhasználói hitelesítő adatokat vagy hitelesítést nem igénylő leírtak szerint [megosztott PC mód fogalmak](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Alkalmazások**: Adja hozzá az alkalmazások futtatását a teljes képernyős eszközön. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Áruházbeli alkalmazás hozzáadása**: Alkalmazás hozzáadása a Microsoft Store vállalatoknak. Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md). Például a teljes képernyős böngészőt, az Excelt, a OneNote-ot és egyéb alkalmazásokat is hozzáadhat.

  - **Win32-alkalmazás hozzáadása**: A Win32-alkalmazás egy hagyományos asztali alkalmazás, például a Visual Studio Code-ot vagy a Google Chrome. Adja meg a következő tulajdonságokat:

    - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Helyi elérési út**: Kötelező. Adja meg a végrehajtható fájl elérési útját, például `C:\Program Files (x86)\Microsoft VS Code\Code.exe` vagy `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Adja meg a Win32-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Ez a beállítás meghatározza a csempe kezdő elrendezését az asztalon. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) című témakörben leírtak alapján kereshető meg.
    - **Csempe méretének**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.
  
  - **Hozzáadása AUMID alapján**: Ezt a beállítást használja a Beérkezett fájlok Windows-alkalmazások, például a Jegyzettömbbel vagy a Számológép hozzáadása. Adja meg a következő tulajdonságokat: 

    - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.
    - **Csempe méretének**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

  > [!TIP]
  > Miután hozzáadta az összes alkalmazást, kattintással és húzással módosíthatja a megjelenítés sorrendjét az alkalmazások listájában.  

  Válassza ki **OK** a módosítások mentéséhez.

- **Teljes képernyős böngésző beállításait**: Ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Böngészőalkalmazást a kioszkmódban lévő eszközökön az [ügyfélalkalmazások](apps-add.md) használatával kell üzembe helyeznie.

  Adja meg a következő beállításokat:

  - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-cím jelenik meg, amikor a teljes képernyős böngésző megnyitja a, vagy ha a böngésző újraindítása. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

  - **Kezdőlap gombjának**: **Megjelenítés** vagy **elrejtése** a teljes képernyős böngésző home gombra. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Navigációs gombok**: **Megjelenítés** vagy **elrejtése** az előre és vissza gomb. A navigációs gombok alapértelmezés szerint nem jelennek meg.

  - **Záró munkamenet gomb**: **Megjelenítés** vagy **elrejtése** a teljes munkamenet gombra. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

  - **Üresjárati idő után frissítse a böngészőt**: Adja meg az üresjárati idő (1-1440 perc) mindaddig, amíg a teljes képernyős böngésző friss állapotban indul újra. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

  - **Engedélyezett webhelyek**: Használja ezt a beállítást, hogy az adott webhely megnyitásához. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.

    Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját tartalmazó .csv-fájlt. Ha nem ad hozzá .csv-fájlt, az összes webhely használata engedélyezve lesz.

  Válassza ki **OK** a módosítások mentéséhez.

- **Használat alternatív Start elrendezésének**: Válasszon **Igen** , adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a start menüben, beleértve az alkalmazások sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

- **Windows-tálcán**: Válassza ki a **megjelenítése** vagy **elrejtése** a tálcán. Alapértelmezés szerint a tálca nem jelenik meg.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business rendszerű eszközök egyalkalmazásos vagy többalkalmazásos kioszkmódban való használatra is konfigurálhatók. Bizonyos funkciókat a Windows Holographic for Business nem támogat.

#### <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok
Egyalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **Felhasználói bejelentkezési típus**: Válassza ki **helyi felhasználói fiók** , írja be a helyi (eszközön létező) felhasználói fiókot, vagy egy a teljes képernyős alkalmazáshoz társított Microsoft-fiók (MSA) fiók. Az **Automatikus bejelentkezésű** felhasználói fiókokat a Windows Holographic for Business nem támogatja.

- **Az alkalmazástípus**: Válassza ki **Store alkalmazás**.

- **Alkalmazás teljes képernyős módban való futásra**: Válasszon **áruházbeli alkalmazás hozzáadása**, és válasszon ki egy alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

    Válassza ki **OK** a módosítások mentéséhez.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk
Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni. Többalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **A Windows 10 S mód eszközökön célzott**: Válasszon **nem**. S mód nem támogatott a Windows Holographic for Business.

- **Felhasználói bejelentkezési típus**: Adjon hozzá egy vagy több felhasználói fiókok, amelyek használhatják a hozzáadott alkalmazások. A választható lehetőségek: 

  - **Automatikus bejelentkezés**: Nem támogatott a Windows Holographic for Business.
  - **A helyi felhasználói fiókok**: **Adjon hozzá** a helyi (eszközön létező) felhasználói fiók. A megadott fiókkal történik a bejelentkezés a kioszkba.
  - **Azure AD-felhasználó vagy csoport (Windows 10 1803-es és újabb verziók)**: Felhasználói hitelesítő adatokkal jelentkezzen be az eszköz szükséges. Válassza a **Hozzáadás** lehetőséget Azure AD-felhasználók vagy -csoportok kiválasztására a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens-látogató**: A látogatói egy a Vendég fiók felhasználói hitelesítő adatokat vagy hitelesítést nem igénylő leírtak szerint [megosztott PC mód fogalmak](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Alkalmazások**: Adja hozzá az alkalmazások futtatását a teljes képernyős eszközön. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Adja hozzá a Store apps**: Válasszon ki egy meglévő alkalmazást segítségével hozzáadott [ügyfélalkalmazás](apps-add.md). Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md).
  - **Win32-alkalmazás hozzáadása**: Nem támogatott a Windows Holographic for Business.
  - **Hozzáadása AUMID alapján**: Ez a beállítás használatával Beérkezett üzenetek Windows-alkalmazások hozzáadása. Adja meg a következő tulajdonságokat: 

    - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.
    - **Csempe méretének**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

- **Teljes képernyős böngésző beállításait**: Nem támogatott a Windows Holographic for Business.

- **Használat alternatív Start elrendezésének**: Válasszon **Igen** , adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a start menüben, beleértve az alkalmazások sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) című cikk nyújt némi útmutatást, és tartalmaz egy kimondottan Windows Holographic for Business rendszerű eszközökhöz készült XML-fájlt.

- **Windows-tálcán**: Nem támogatott a Windows Holographic for Business.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Teljes képernyős profilok is létrehozhat [Android](device-restrictions-android.md#kiosk) és [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) eszközök.

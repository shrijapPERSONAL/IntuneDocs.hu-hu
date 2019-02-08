---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Egyalkalmazásos és többalkalmazásos kioszk konfigurálása a Windows 10 (és újabb) eszközöket, a start menü testreszabásához, alkalmazások hozzáadása, megjelenítése a tálcán és egy webes böngésző konfigurálása a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7886f533f6ffa379132ac7c898bc5c1a1dac9111
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836540"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows 10-es és újabb beállításai az Intune-ban a teljes képernyős fiókként való futtatásra

A Windows 10-es és újabb rendszerű eszközök konfigurálhatja ezeket az eszközöket Egyalkalmazásos kioszk módban, vagy többalkalmazásos kioszk módban futtatni.

Ez a cikk és a Windows 10-es és újabb rendszerű eszközök szabályozhatja a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások használatával konfigurálja a Windows 10-es és újabb rendszerű eszközöket a kioszk módban futtatni.

Intune rendszergazdaként létrehozhat és rendelje hozzá ezeket a beállításokat az eszközökön.

Az Intune-ban, a Windows teljes képernyős szolgáltatással kapcsolatos további tudnivalókért lásd: [a kioszkmód konfigurálása](kiosk-settings.md).

## <a name="before-you-begin"></a>Előkészületek

[A profil létrehozásához](kiosk-settings.md#create-the-profile).

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
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Adja meg a Win32-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Ez a beállítás meghatározza a csempe kezdő elrendezését az asztalon. Ez az azonosító lekéréséhez lásd: [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
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

- **Windows-tálcán**: Válassza ki a **megjelenítése** vagy **elrejtése** a tálcán. Alapértelmezés szerint a tálca nem jelenik meg. Ikonok, például a Wi-Fi ikon látható, de a beállítások nem módosíthatók a végfelhasználók számára.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Teljes képernyős profilok is létrehozhat [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings), és [Windows Holographic for Business](kiosk-settings-holographic.md) eszközök.

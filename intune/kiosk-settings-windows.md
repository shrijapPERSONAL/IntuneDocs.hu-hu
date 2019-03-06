---
title: Kioszkbeállítások a Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Egyalkalmazásos és többalkalmazásos kioszk konfigurálása a Windows 10 (és újabb) eszközöket, a start menü testreszabásához, alkalmazások hozzáadása, megjelenítése a tálcán és egy webes böngésző konfigurálása a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ce63f836c006c44e88f939c29f3d9648acc045e
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57400364"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows 10-es és újabb beállításai az Intune-ban a teljes képernyős fiókként való futtatásra

A Windows 10-es és újabb rendszerű eszközök konfigurálhatja ezeket az eszközöket Egyalkalmazásos kioszk módban, vagy többalkalmazásos kioszk módban futtatni.

Ez a cikk és a Windows 10-es és újabb rendszerű eszközök szabályozhatja a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások használatával konfigurálja a Windows 10-es és újabb rendszerű eszközöket a kioszk módban futtatni.

Intune rendszergazdaként létrehozhat és rendelje hozzá ezeket a beállításokat az eszközökön.

Az Intune-ban, a Windows teljes képernyős szolgáltatással kapcsolatos további tudnivalókért lásd: [a kioszkmód konfigurálása](kiosk-settings.md).

## <a name="before-you-begin"></a>Előkészületek

- [A profil létrehozásához](kiosk-settings.md#create-the-profile).

- A teljes képernyős profilt közvetlenül kapcsolódik az eszközkorlátozások profiljának létrehozhatja a [Microsoft Edge-teljes képernyős beállítások](device-restrictions-windows-10.md#microsoft-edge-browser). Összefoglalásképpen:

  1. Az eszköz kioszk módban futtatni a teljes képernyős profil létrehozása.
  2. Hozzon létre a [eszközkorlátozások profiljának](device-restrictions-windows-10.md#microsoft-edge-browser), és a funkciók és a Microsoft Edge-ben engedélyezett beállításainak konfigurálása.

> [!IMPORTANT] 
> Ügyeljen arra, hogy a teljes képernyős profil hozzárendelése ugyanazokkal az eszközökkel, mint a [Microsoft Edge-profilhoz](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok

Csak egy alkalmazást futtat az eszközön.

- **Válassza ki a teljes képernyős módot**: Válasszon **egyetlen alkalmazás, a teljes képernyős**.

- **Felhasználói bejelentkezési típus**: A hozzáadott alkalmazások futtatása a felhasználói fiókot, akkor adja meg. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10 1803-es és újabb verziók)**: Használja a számítógépek, amelyek nem igényelnek a felhasználót, hogy jelentkezzen be, a Vendég fiók hasonló nyilvános környezetekben. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiókot. A fiók jelentkezik be a teljes képernyős adja meg.

- **Az alkalmazástípus**: Válassza ki az alkalmazás típusaként. A választható lehetőségek:

  - **Adja hozzá a Microsoft Edge böngésző**: Válassza ki **Microsoft Edge böngésző**, és válassza ki a **teljes képernyős mód típusát él**:

    - **Digitális és interaktív aláírási**: URL-cím teljes képernyőn megnyílik, és csak jeleníti meg a tartalmat az adott webhelyre. [Állítsa be a digitális jelentkezik](https://docs.microsoft.com/windows/configuration/setup-digital-signage) Ez a szolgáltatás további információkkal szolgál.
    - **Nyilvános tallózása (gyakori)**: A Microsoft Edge korlátozott több lapon verzióját futtatja. A felhasználók tallózással keresse meg nyilvánosan vagy azok böngészési munkamenetet.

    Ezekről a lehetőségekről további információkért lásd: [központi telepítése a Microsoft Edge-ben teljes képernyős mód](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Ez a beállítás lehetővé teszi, hogy a Microsoft Edge böngésző az eszközön. A Microsoft Edge-specifikus beállításokat, hozzon létre eszközkonfigurációs profil (**eszközkonfiguráció** > **profilok** > **profillétrehozása**  >  **Windows 10-es** tartozó platform > **Eszközkorlátozások** >  **a Microsoft Edge böngésző**). [A Microsoft Edge böngésző](device-restrictions-windows-10.md#microsoft-edge-browser) , és az elérhető beállításokat ismerteti.

    Válassza ki **OK** a módosítások mentéséhez.

  - **Adja hozzá a teljes képernyős böngésző**: Válassza ki **teljes képernyős böngésző beállításait**. Ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Lehet arra, hogy a [teljes képernyős böngészőalkalmazásban](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) a Store, adja hozzá az Intune-t egy [ügyfélalkalmazás](apps-add.md), majd rendelje hozzá az alkalmazást a teljes képernyős eszközökön.

    Adja meg a következő beállításokat:

    - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-cím jelenik meg, amikor a teljes képernyős böngésző megnyitja a, vagy ha a böngésző újraindítása. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

    - **Kezdőlap gombjának**: **Megjelenítés** vagy **elrejtése** a teljes képernyős böngésző home gombra. Alapértelmezés szerint a gomb nem jelenik meg.

    - **Navigációs gombok**: **Megjelenítés** vagy **elrejtése** az előre és vissza gomb. A navigációs gombok alapértelmezés szerint nem jelennek meg.

    - **Záró munkamenet gomb**: **Megjelenítés** vagy **elrejtése** a teljes munkamenet gombra. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

    - **Üresjárati idő után frissítse a böngészőt**: Adja meg az üresjárati idő (1-1440 perc) mindaddig, amíg a teljes képernyős böngésző friss állapotban indul újra. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

    - **Engedélyezett webhelyek**: Használja ezt a beállítást, hogy az adott webhely megnyitásához. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `http://contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.

      Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját különböző sorokban tartalmazó fájlt. Ha nem ad hozzá fájlt, az összes webhely használata engedélyezve lesz. Az Intune támogatja a `*` (csillag) helyettesítő karakterként.

      Az mintafájlnak a következő listához hasonlóan kell kinéznie:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

    Válassza ki **OK** a módosítások mentéséhez.

  - **Adja hozzá az Store app**: Válassza ki **áruházbeli alkalmazás hozzáadása**, és válasszon egy alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

  Válassza ki **OK** a módosítások mentéséhez.

## <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni.

- **Válassza ki a teljes képernyős módot**: Válasszon **Többalkalmazásos kioszk**.

- **A Windows 10 S mód eszközökön célzott**:
  - **Igen**: Lehetővé teszi a teljes képernyős profil áruházbeli alkalmazások és az alkalmazások AUMID (Win32-alkalmazások az kivételével).
  - **Nem**: Lehetővé teszi a teljes képernyős profil áruházbeli alkalmazások, a Win32-alkalmazások és a AUMID alkalmazásokat. A teljes képernyős profil nincs telepítve S módú eszközökön.

- **Felhasználói bejelentkezési típus**: A hozzáadott alkalmazások futtatása a felhasználói fiókot, akkor adja meg. A választható lehetőségek:

  - **Automatikus bejelentkezés (Windows 10 1803-es és újabb verziók)**: Használja a számítógépek, amelyek nem igényelnek a felhasználót, hogy jelentkezzen be, a Vendég fiók hasonló nyilvános környezetekben. Ez a beállítás az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)-t használja.
  - **Helyi felhasználói fiók**: **Adjon hozzá** a helyi (eszközön létező) felhasználói fiók. A fiók jelentkezik be a teljes képernyős adja meg.
  - **Az Azure AD-felhasználó vagy csoport (Windows 10 1803-es és újabb verziók)**: Válassza ki **Hozzáadás**, és az Azure AD-felhasználók vagy csoportok kiválasztása a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens-látogató**: A látogatói egy a Vendég fiók felhasználói hitelesítő adatokat vagy hitelesítést nem igénylő leírtak szerint [megosztott PC mód fogalmak](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Böngésző és az alkalmazások**: Adja hozzá az alkalmazások futtatását a teljes képernyős eszközön. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Böngészők**

    - **Adja hozzá a Microsoft Edge**: Microsoft Edge bekerül az alkalmazás rács, és minden alkalmazást a teljes képernyős futhatnak. Válassza ki a **Microsoft Edge teljes képernyős mód típusát**:

      - **Normál üzemmódban (teljes verzióját a Microsoft Edge)**: A Microsoft Edge teljes-verziója fut az összes böngészési funkció. Felhasználói adatok és -munkamenetek között lesznek mentve.
      - **Nyilvános tallózása (gyakori)**: A Microsoft Edge InPrivate több lapon verziója fut kioszkok, amely a teljes képernyős módban fusson a testre szabott felhasználói élményt.

      Ezekről a lehetőségekről további információkért lásd: [központi telepítése a Microsoft Edge-ben teljes képernyős mód](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Ez a beállítás lehetővé teszi, hogy a Microsoft Edge böngésző az eszközön. A Microsoft Edge-specifikus beállításokat, hozzon létre eszközkonfigurációs profil (**eszközkonfiguráció** > **profilok** > **profillétrehozása**  >  **Windows 10-es** tartozó platform > **Eszközkorlátozások** >  **a Microsoft Edge böngésző**). [A Microsoft Edge böngésző](device-restrictions-windows-10.md#microsoft-edge-browser) , és az elérhető beállításokat ismerteti.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Adja hozzá a teljes képernyős böngésző**: Ezek a beállítások vezérlik a böngészőalkalmazást kioszkmódban. Böngészőalkalmazást a kioszkmódban lévő eszközökön az [ügyfélalkalmazások](apps-add.md) használatával kell üzembe helyeznie.

      Adja meg a következő beállításokat:

      - **Alapértelmezett kezdőlap URL-címe**: Adja meg az alapértelmezett URL-cím jelenik meg, amikor a teljes képernyős böngésző megnyitja a, vagy ha a böngésző újraindítása. Például írja be a következőt: `http://bing.com` vagy `http://www.contoso.com`.

      - **Kezdőlap gombjának**: **Megjelenítés** vagy **elrejtése** a teljes képernyős böngésző home gombra. Alapértelmezés szerint a gomb nem jelenik meg.

      - **Navigációs gombok**: **Megjelenítés** vagy **elrejtése** az előre és vissza gomb. A navigációs gombok alapértelmezés szerint nem jelennek meg.

      - **Záró munkamenet gomb**: **Megjelenítés** vagy **elrejtése** a teljes munkamenet gombra. Ha a gomb látható, és a felhasználó kiválasztja, akkor az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot (cookie-k, gyorsítótár stb.) töröl, majd megnyitja az alapértelmezett URL-címet. Alapértelmezés szerint a gomb nem jelenik meg.

      - **Üresjárati idő után frissítse a böngészőt**: Adja meg az üresjárati idő (1-1440 perc) mindaddig, amíg a teljes képernyős böngésző friss állapotban indul újra. Az üresjárati idő az utolsó felhasználói beavatkozás óta eltelt percek száma. Alapértelmezés szerint az érték üres, ami azt jelenti, hogy a nincs üresjárati időkorlát.

      - **Engedélyezett webhelyek**: Használja ezt a beállítást, hogy az adott webhely megnyitásához. Más szóval, ezzel a beállítással korlátozhatja vagy megakadályozhatja a webhelyek megjelenítését az eszközön. Például engedélyezheti a `contoso.com*` összes webhelyének megnyitását. Alapértelmezés szerint az összes webhely engedélyezett.

        Adott webhelyek engedélyezéséhez töltse fel az engedélyezett webhelyek listáját tartalmazó .csv-fájlt. Ha nem ad hozzá .csv-fájlt, az összes webhely használata engedélyezve lesz.

      Válassza ki **OK** a módosítások mentéséhez.

  - **Alkalmazások**

    - **Áruházbeli alkalmazás hozzáadása**: Alkalmazás hozzáadása a Microsoft Store vállalatoknak. Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md). Például a teljes képernyős böngészőt, az Excelt, a OneNote-ot és egyéb alkalmazásokat is hozzáadhat.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Win32-alkalmazás hozzáadása**: A Win32-alkalmazás egy hagyományos asztali alkalmazás, például a Visual Studio Code-ot vagy a Google Chrome. Adja meg a következő tulajdonságokat:

      - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
      - **Helyi elérési út**: Kötelező. Adja meg a végrehajtható fájl elérési útját, például `C:\Program Files (x86)\Microsoft VS Code\Code.exe` vagy `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Adja meg a Win32-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Ez a beállítás meghatározza a csempe kezdő elrendezését az asztalon. Ez az azonosító lekéréséhez lásd: [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

      Válassza ki **OK** a módosítások mentéséhez.

    - **Hozzáadása AUMID alapján**: Ezt a beállítást használja a Beérkezett fájlok Windows-alkalmazások, például a Jegyzettömbbel vagy a Számológép hozzáadása. Adja meg a következő tulajdonságokat:

      - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
      - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Csempe méretének**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

  > [!TIP]
  > Miután hozzáadta az összes alkalmazást, kattintással és húzással módosíthatja a megjelenítés sorrendjét az alkalmazások listájában.  

- **Használat alternatív Start elrendezésének**: Válasszon **Igen** , adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a start menüben, beleértve az alkalmazások sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

- **Windows-tálcán**: Válassza ki a **megjelenítése** vagy **elrejtése** a tálcán. Alapértelmezés szerint a tálca nem jelenik meg. Ikonok, például a Wi-Fi ikon látható, de a beállítások nem módosíthatók a végfelhasználók számára.

Válassza ki **OK** a módosítások mentéséhez.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Teljes képernyős profilok is létrehozhat [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), és [Windows Holographic for Business](kiosk-settings-holographic.md) eszközök.

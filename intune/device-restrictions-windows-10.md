---
title: Eszközkorlátozási beállítások Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Megjelenítheti az összes beállítás és a hozzájuk tartozó leírások létrehozásához eszközkorlátozások Windows 10 és újabb rendszerű eszközök listáját. A konfigurációs profil ezek a beállítások segítségével szabályozhatja a képernyőfelvételt, jelszókövetelmények, a kioszkmód, a tárolóban, a Microsoft Edge böngészőt, a Windows defender-alkalmazások, a felhőbe, a start menüben, és több Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: e297169757f1bcc703ce698302ce6f7129104827
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "55230120"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>A Windows 10 (és újabb) eszközbeállítások engedélyezett vagy korlátozott funkciók az Intune-nal

Ez a cikk és ismerteti a különböző beállításokkal szabályozhatja a Windows 10-es és újabb eszközökön. A mobileszköz-felügyelet (MDM) megoldás részeként használatával ezek a beállítások lehetővé teszik vagy szolgáltatásokat tilthat le, jelszószabályok beállítása, a zárolási képernyő testreszabása, használja a Windows Defender és a további.

Ezek a beállítások hozzá egy eszközkonfigurációs profilt az Intune-ban, és ezután hozzárendelt vagy a Windows 10-es eszközökre telepített.

> [!Note]
> Nem minden lehetőség áll rendelkezésre a Windows összes kiadásában

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](device-restrictions-configure.md).

## <a name="app-store"></a>Alkalmazásáruház

- **Alkalmazás-áruház (csak mobil)**: Engedélyezi vagy letiltja az alkalmazásáruházat a Windows 10 Mobile-eszközök használatát.
- **Áruházból származó alkalmazások automatikus frissítése**: Lehetővé teszi, hogy a Microsoft Store automatikusan frissíteni kell a telepített alkalmazások.
- **Megbízható alkalmazás telepítése**: Lehetővé teszi az alkalmazások közvetlen telepítését a megbízható tanúsítvánnyal aláírt.
- **Fejlesztői zárolás feloldása**: Lehetővé teszi a Windows fejlesztői beállításait, például lehetővé teszi a végfelhasználók által módosítható a közvetlenül telepített alkalmazások.
- **Megosztott felhasználói alkalmazásadatok**: Lehetővé teszi az alkalmazások közötti különböző felhasználók ugyanazon az eszközön.
- **Csak privát áruház használata**: Engedélyezze a kizárólag a végfelhasználók számára a privát áruházból származó alkalmazásokat tölthetik le.
- **Store származó alkalmazások indítása**: Minden alkalmazás, amely előre telepítve az eszközön, vagy letölthető a Microsoft Store a letiltására szolgál.
- **Alkalmazásadatok telepítése a rendszerköteten**: Leállítja az alkalmazások adatokat tároljanak az eszköz a rendszerköteten.
- **Alkalmazások telepítése a rendszermeghajtón**: Leállítja az alkalmazások adatokat tároljanak az eszköz rendszermeghajtóján.
- **Játékvideó-rögzítő (csak asztali verzióban)**: Annak konfigurálása, rögzítése és közvetítése játékok engedélyezett-e.
- **Csak áruházból származó alkalmazások**: Konfigurálja, hogy a felhasználók telepíthetnek alkalmazásokat az app store intézményeknek portálon kívülről származó.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Mobilhálózati adatcsatorna**: Állítsa le a felhasználók adathasználatát, például a webböngészést, amikor mobilhálózati elérését sem. 
- **Adatroaming**: Hálózatok közötti barangolás engedélyezése adatok elérése közben.
- **Mobilhálózati VPN**: Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.
- **A mobilhálózati barangolás VPN**: Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming esetén.
- **Bluetooth**: Azt szabályozza, hogy a felhasználó engedélyezése és az eszköz Bluetooth konfigurálásához.
- **Bluetooth-észlelhetőség**: Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.
- **Előzetes bluetooth-párosítás**: Lehetővé teszi meghatározott Bluetooth-eszközök automatikus párosítását párosításuk konfigurálását.
- **Bluetooth-hirdetés**: Lehetővé teszi az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.
- **Csatlakoztatott eszközök szolgáltatás**: Döntse el, hogy a csatlakoztatott eszközök szolgáltatást, amely lehetővé teszi más Bluetooth-eszközök észlelését és lehetővé teszi lehetővé.
- **NFC**: Lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja a szolgáltatások közelében mező kommunikáció (NFC) az eszközön.
- **Wi-Fi**: Lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja a Wi-Fi (csak Windows 10 Mobile esetén) az eszközön.
- **Automatikus csatlakozás Wi-Fi elérési pontokhoz**: Az ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadásának engedélyezése az eszközön.
- **Manuális Wi-Fi konfigurációs**: Azt szabályozza, a felhasználó konfigurálhat-e saját Wi-Fi kapcsolatokat, vagy lehet, ha csak egy Wi-Fi profil (csak Windows 10 Mobile esetén) által konfigurált kapcsolatokat használhatja azokat.
- **Wi-Fi-ellenőrzési időköz**: Adja meg, hogy milyen gyakran eszközök Wi-Fi-hálózatok keresése. Adjon meg egy 1 (leggyakoribb) és 500 (legritkább) közötti értéket.
- **Bluetooth-engedélyezett szolgáltatások**: Adja meg hexadecimális karakterláncok, az engedélyezett Bluetooth-szolgáltatások és a profilok listáját.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Microsoft-fiók**: Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.
- **Nem Microsoft-fiók**: Lehetővé teszi, hogy a felhasználók e-mail fiókokat vegyen fel az eszközön, amelyek nem Microsoft-fiókhoz társítva.
- **Microsoft-fiók beállításszinkronizálása**: Eszköz- és Alkalmazásbeállítások szinkronizálását az eszközök között Microsoft-fiókkal társított engedélyezése.

## <a name="cloud-printer"></a>Felhőbeli nyomtató

- **Nyomtató-felderítési URL-cím**: Adja meg az URL-cím keresése a felhőbeli nyomtatók.
- **Nyomtató hozzáférés szolgáltató URL-címe**: Adja meg a hitelesítési végpont URL-címe, az OAuth-jogkivonatok beolvasásához. Például: `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Azure-beli natív ügyfélalkalmazás GUID**: Adja meg a szolgáltatótól OAuth-jogkivonatok kérhető ügyfélalkalmazás GUID-ja.
- **Nyomtatási szolgáltatás erőforrás-URI**: Adja meg a nyomtatási szolgáltatás az Azure Portal webhelyen konfigurált OAuth erőforrás URI azonosítója. Például: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **(Csak mobil) lekérdezendő nyomtatók maximális száma**: Adja meg a lekérdezni kívánt nyomtatók maximális száma. Például írja be a következőt: `10`.
- **Nyomtatófelderítési szolgáltatás erőforrás URI**: Adja meg az OAuth-erőforrás URI-nyomtató discovery szolgáltatás beállítása az Azure Portalon. Például: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Miután beállította a [Windows Serverhez a hibrid felhőnyomtatást](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), konfigurálhatja ezeket a beállításokat, majd telepítheti Windows rendszerű eszközökre.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

- **Gépház alkalmazás**: A Windows gépház alkalmazás elérésének letiltása.
  - **Rendszer**: Blokkolja a hozzáférést a gépház alkalmazás rendszer területéhez.
    - **Energiagazdálkodási és alvási beállítások módosítása (csak asztali verzióban)**: Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz energiagazdálkodási és alvási beállításait.
  - **eszközök**: Blokkolja a hozzáférést a gépház alkalmazás eszközök területéhez.
  - **Hálózat és Internet**: Blokkolja a hozzáférést a gépház alkalmazás hálózat és internet területéhez.
  - **Személyre szabás**: Blokkolja a hozzáférést a gépház alkalmazás személyre szabás területéhez.
  - **Fiókok**: Blokkolja a hozzáférést a gépház alkalmazás fiókok területéhez.
  - **Idő és nyelv**: Blokkolja a hozzáférést a gépház alkalmazás idő és nyelv területéhez.
    - **Rendszeridő módosítása**: Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz rendszeridejét.
    - **Területi beállítások módosítása (csak asztali verzióban)**: Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz területi beállításait.
    - **Nyelvi beállítások módosítása (csak asztali verzióban)**: E funkció felhasználó általi módosításának a nyelvi beállításokat az eszközön.
  - **Játékok**: Blokkolja a hozzáférést a beállítások alkalmazás játékok területéhez.
  - **Könnyű elérés**: Blokkolja az területén hozzáférést a gépház alkalmazás könnyű való hozzáférést.
  - **Adatvédelmi**: Blokkolja a hozzáférést a gépház alkalmazás adatvédelem területéhez.
  - **Frissítés és biztonság**: Blokkolja a hozzáférést a frissítés és biztonság területéhez a gépház alkalmazásban.

## <a name="display"></a>Megjelenítés

- **GDI-méretezés bekapcsolása az alkalmazásoknál**
- **GDI-méretezés kikapcsolása az alkalmazásoknál**

  A GDI DPI-méretezés lehetővé teszi, hogy alkalmazásokat, amelyek a nem DPI figyelembe /-figyelő DPI tisztában lesz. Adja meg az örökölt alkalmazásokat, a GDI DPI-méretezés van kapcsolva. A GDI DPI-méretezés bekapcsolása és kikapcsolása alkalmazás konfigurálva, a méretezés ki van kapcsolva az alkalmazáshoz.

## <a name="general"></a>Általános

- **Képernyőfelvétel (csak mobil)**: Lehetővé teszi, hogy a felhasználó rögzítheti képként a képernyőn.
- **Másolás és beillesztés (csak mobileszköz)**: Másolás és Beillesztés engedélyezése az eszközön lévő alkalmazások közötti.
- **Regisztráció manuális törlésének**: Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
  - A rendszer nem alkalmazza ezt a szabályzatbeállítást, ha a számítógép az Azure AD-hoz van csatlakoztatva, és engedélyezve van az automatikus regisztráció. 
  - A szabályzatbeállítás a Windows 10 Home rendszerű számítógépekre nem vonatkozik.
- **Főtanúsítvány manuális telepítése (csak mobil)**: Megakadályozza a felhasználó legfelső szintű tanúsítványok és köztes szolgáltatói tanúsítványok manuális telepítése.

- **Kamera**: Engedélyezi vagy letiltja az eszköz kamerájának használatát.
- **OneDrive-fájlszinkronizálás**: Letiltja az eszközt, szinkronizálja a fájlokat a onedrive-bA.
- **Cserélhető tároló**: Itt adhatja meg, hogy használható-e külső tárolóeszköz, például SD-kártya az eszközzel.
- **Földrajzi hely meghatározásának**: Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.
- **Internetkapcsolat megosztása**: Az internetmegosztás engedélyezése az eszközön.
- **Telefon alaphelyzetbe állítása**: Szabályozza, hogy a felhasználó visszaállíthatja-e a törlést az eszközön.
- **USB-kapcsolat (csak mobil)**: Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.
- **Lopásgátló üzemmód (csak mobil)**: Annak beállítása, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.
- **Cortana**: A Cortana beszédfelismerési asszisztens engedélyezése vagy letiltása.
- **Hangrögzítés (csak mobil)**: Engedélyezheti vagy letilthatja az eszköz hangrögzítőjét.
- **Eszköznév módosításának**: Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz nevét (csak Windows 10 Mobile esetén)
- **Kiépítési csomagok hozzáadása**: Letiltja a konfigurációs ügynök kiépítési csomagokat, amelyek a kiépítési csomagokat telepítsen.
- **Kiépítési csomagok eltávolítása**: Letiltja a konfigurációs ügynök kiépítési csomagokat, amely eltávolítja a kiépítési csomagokat.
- **Eszközfelderítés**: Letiltja az eszköz más eszközök általi felderíthetőségét.
- **Feladatváltó (csak mobil)**: Letiltja a feladatváltót az eszközön.
- **SIM kártya hibát jelző párbeszédpanele (csak mobil)**: Hibaüzenet megjelenítésének letiltása az eszközön, ha észlelhető SIM-kártya nem blokkolja.
- **Szabadkézi munkaterület**: Letiltása a felhasználók hozzáférjenek a szabadkézi munkaterülethez. **Nincs konfigurálva** bekapcsolja az ink-munkaterületen, és a felhasználó számára engedélyezett, a zárolási képernyőn.
- **Automatikus újbóli üzembe helyezés**: Lehetővé teszi, hogy törli az összes felhasználói adatot és beállítást rendszergazdai jogosultságokkal rendelkező felhasználóknak **CTRL + Win + R** , az eszköz zárolási képernyőjén. Ennek hatására automatikusan megtörténik az eszköz újbóli konfigurálása és regisztrálása felügyeletre.
- **Csatlakozzon a hálózathoz (csak Windows Insider) eszköz telepítése során, hogy a felhasználók**: Válasszon **megkövetelése** , az eszköz csatlakozik a hálózathoz, mielőtt folytatná a hálózat lap korábbi Windows 10-es telepítés során. Amíg ez a funkció előzetes verziójú, a beállítás használatához a Windows Insider 1809-es buildje, vagy annál újabb verzió szükséges.
- **Folyamatait a Feladatkezelőben**: Ez a beállítás meghatározza, hogy e nem rendszergazdák teljes feladat Feladatkezelő használható. **Blokk** általános jogú felhasználók (nem rendszergazda) megakadályozza, hogy egy folyamat vagy feladat az eszköz befejezi a Feladatkezelő használatát. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi, hogy a folyamat leállítása, vagy a feladat a Feladatkezelő használatát általános jogú felhasználók.

## <a name="kiosk-preview---obsolete"></a>Kioszk (Előzetes) – Elavult

Ezek a beállítások csak olvashatók, és nem módosíthatók. A kioszkmód a [Kioszkbeállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával konfigurálható.

A kioszkeszközök jellemzően egyetlen alkalmazást futtatnak, vagy az alkalmazások egy előre meghatározott készletét. A rendszer megakadályozza más funkcióinak és az eszköz hozzáférését.

- **Teljes képernyős mód**: A szabályzat által támogatott teljes képernyős mód típusát jelöli. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezett): A szabályzat nem teszi lehetővé az eszköz kioszkmódjában.
  - **Egyalkalmazásos kioszk**: A profil engedélyezi az eszköznek csak egyetlen alkalmazás futtatását. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk**: A profil engedélyezi az eszköz számos alkalmazás futtatásához. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amely csak a szükséges alkalmazások elérését engedélyezi, a többi alkalmazást pedig elrejti a felhasználó elől.

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk

Adja meg a következő beállításokat:

- **Felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiók, egy AD-tartományi fiók vagy a teljes képernyős alkalmazáshoz társított Azure AD-fiókkal.
  - Helyi fiók: Adjon meg `devicename\accountname`, `.\accountname`, vagy `accountname`
  - Tartományi fiók: Adjon meg `domain\accountname`
  - Azure AD-fiók: Adjon meg `AzureAD\emailaddress`. Ügyeljen rá, hogy „AzureAD”-ként adja meg, mivel ez egy rögzített tartománynév. Ezt követően adja meg az Azure AD e-mail-címét. Például írja be a következőt: `AzureAD\user@contoso.onmicrosoft.com`.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha kioszk módhoz Azure AD-fiókot használ, ügyeljen rá, hogy ezt írja be: `AzureAD\user@yourorganization.com`.

- **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID) alkalmazás**: Adja meg a teljes képernyős alkalmazás alkalmazásfelhasználói modellben használt AZONOSÍTÓJÁT. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

A [többalkalmazásos kioszkeszközök](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) olyan kioszkkonfigurációt használnak, amely más beállítások mellett tartalmazza az engedélyezett alkalmazások listáját. 

Hozzon létre egy kioszkkonfigurációt a **Hozzáadás** gomb használatával (vagy válasszon egy meglévőt). Ezután adja meg a következő beállításokat:

- **Kioszkkonfiguráció neve**: Adja meg a konfiguráció azonosítására szolgáló felhasználóbarát nevet.

- **Teljes képernyős alkalmazás**: Adja meg a Start menüben elérhető alkalmazásokat. A felhasználó kizárólag a megadott alkalmazásokat fogja tudni elérni.

  - **Alkalmazás típusa**: Válassza ki a teljes képernyős alkalmazás típusát:
    - **Win32 App**: Hagyományos asztali alkalmazás. A futtatható fájlnak az eszközön érvényes teljes elérési útja szükséges.
    - **UWP-alkalmazás**: Egy univerzális Windows-alkalmazás. [Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) szükséges.

  - **Azonosító**: A végrehajtható fájl (Win32-alkalmazás), adja meg a teljes elérési útjával, vagy a [alkalmazás AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-alkalmazások).

- **Tálca**: Válassza ki a **engedélyezése** (show) a tálcán vagy hagyja **nincs konfigurálva** kioszkeszközön való elrejtéséhez.

- **Start menü elrendezése**: Adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

  [Alkalmazások futtatása Windows 10 rendszerű kioszk létrehozása](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) használatával és XML-fájlok létrehozásáról további információt talál.

- **Hozzárendelt felhasználók**: Adjon hozzá egy vagy több felhasználói fiókok, amelyek használhatják a hozzáadott alkalmazások. A fiókkal való bejelentkezéskor csak a konfigurációban meghatározott alkalmazások érhetők el. Ez lehet egy helyi fiók az eszközön, vagy egy Azure AD-fiók, amely a teljes képernyős alkalmazáshoz van társítva.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `domain\user@tenant.com` formátumot.

## <a name="locked-screen-experience"></a>Zárolási képernyő felülete

- **Műveletközpont értesítései (csak mobil)**: Engedélyezi a Műveletközpont értesítéseinek megjelenését az eszköz zárolási képernyőjén (csak Windows 10 Mobile esetén).
- **Zárolt képernyőn kép URL-címe (csak asztali verzióban)**: Adja meg a Windows zárolási képernyőjének háttérképeként használt JPEG formátumú kép URL. Felhasználók nem módosíthatják ezt a beállítást.
- **Felhasználó által konfigurálható képernyő-időkorlát (csak mobil)**: Lehetővé teszi a felhasználóknak idő beállítása 
- **Cortana zárolt képernyőn (csak asztali verzióban)**: Nem engedélyezi a felhasználó interakcióba Cortana, ha az eszköz zárolási képernyőjén (csak Windows 10 asztali verzió).
- **Bejelentési értesítések zárolt képernyőn**: Az eszköz zárolási képernyőjén ábrázoló értesítési üzeneteit letiltása.
- **Képernyő időkorlátja (csak mobil)**: Megadja az idő másodpercben a képernyő zárolása után, ha ki fog kapcsolni.

## <a name="messaging"></a>Üzenetkezelés

- **Üzenetszinkronizálás (csak mobil)**: Tiltsa le az üzenetek mindenhol és a szöveges üzenetek biztonsági mentése és visszaállítása.
- **MMS (csak mobilon)**: Az eszközön az MMS küldése/fogadása funkció letiltása.
- **RCS (csak mobil)**: Az eszközön a gazdag kommunikációs szolgáltatások küldése/fogadása funkció letiltása.

## <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző

### <a name="start-experience"></a>Indítsa el a felhasználói élményt

- **Indítsa el a Microsoft Edge**: Válassza ki, hogy mely lapok megnyitása a Microsoft Edge indításakor. A választható lehetőségek:
  - **Indítsa el a lapok**: A Microsoft Edge az alapértelmezett start lap az operációs rendszer által definiált
  - **Új lap**: A Microsoft Edge betöltése akármilyen területen is definiálva van a **új lap URL-címe** beállítás
  - **Utolsó munkamenet oldal**: A Microsoft Edge betölti az utolsó munkamenet lap 
  - **Egyéni kezdőlap**: A Microsoft Edge betölti a rendszergazda által meghatározott úvodní stránku
- **A felhasználó megváltoztathatja a kezdőlapokat**: **Lehetővé teszi** lehetővé teszi a felhasználók megváltoztassák az. A rendszergazdák használhatják a `EdgeHomepageUrls` , adja meg azon kezdőlapok, amelyeket a felhasználók alapértelmezés szerint amikor megnyitja a Microsoft Edge. **Nincs konfigurálva** letiltja a felhasználók módosítsák a kezdőlapokat.
- **Új lap URL-címe**: Adja meg az URL-cím, az új lap megnyitásához. Például írja be a következőt: `https://www.bing.com`.
- **Nyissa meg az új lapon jelenik meg a webes tartalom**: Válasszon **blokk** leállítani a Microsoft Edge megnyisson egy webhelyet egy új lapon. Le van tiltva, ha üres megnyitása új lapon. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést az eszközön, amelyen lehetséges, hogy a felhasználók megjelenítendő elemek.
- **Kezdőlap gombjának**: Válassza ki, mi történik, ha a kezdőképernyő gombra van kiválasztva. A választható lehetőségek:
  - **Indítsa el a lapok**: A kiválasztott lehetőség a **indítsa el a Microsoft Edge-** megnyílik beállítása
  - **Új lap**: A kiválasztott lehetőség a **új lap URL-címe** megnyílik beállítása
  - **Egyéni kezdőlap gombot URL-cím**: A kiválasztott lehetőség a **gomb URL-cím otthoni** megnyílik beállítása
  - **Elrejtése kezdőképernyő gombra**: A kezdőlap gombjának elrejtése
- **A felhasználó megváltoztathatja a kezdőképernyő gombra**: **Lehetővé teszi** lehetővé teszi a felhasználóknak, módosítsa a home gombra. A felhasználó módosításait felülbírálása bármely rendszergazdai beállításait a home gombra. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést az eszközön, amelyek blokkolhatják a felhasználók nem módosíthatják, hogy a rendszergazda konfigurált home gombra.
- **Első futtatás élmény lap megjelenítése**: **Blokk** leállítja a bemutató lap megjelenítését az első alkalommal futtatása a Microsoft Edge. Ez a funkció lehetővé teszi a vállalatok – például regisztrált nulla kibocsátási konfigurációkban blokkolja ezen a lapon. **Nincs konfigurálva** a bevezetés oldalt mutatja.
  - **Először futtassa a felhasználói élményt URL-cím**: Adja meg az oldal URL-cím megjelenítéséhez egy felhasználó első alkalommal futtatja az Microsoft Edge (csak Windows 10 Mobile esetén).
- **Előugró ablakok**: Válasszon **blokk** leállítani az előugró ablakokat a böngészőben. Csak a Windows 10 asztali verzióra vonatkozik. **Nincs konfigurálva** lehetővé teszi, hogy az előugró ablakokat a böngészőben.
- **Intranetes adatforgalom küldését az Internet Explorer**: **Lehetővé teszi** lehetővé teszi a felhasználóknak az intranetes webhelyek megnyitását az Internet Explorer helyett a Microsoft Edge (csak Windows 10 asztali verzió). **Nincs konfigurálva** lehetővé teszi a felhasználóknak a Microsoft Edge használni.
- **Vállalati üzemmód webhelylistájának helye**: Adja meg az URL-cím, amely tartalmazza a vállalati üzemmódban megnyíló webhelyek listája. Felhasználók nem módosíthatják ezt a listát. Csak a Windows 10 asztali verzióra vonatkozik.
- **Üzenet megnyitásakor webhelyek az Internet Explorer**: Ez a beállítás segítségével konfigurálhatja a Microsoft Edge az értesítések megjelenítése, mielőtt egy webhely megnyitása az Internet Explorer 11. A választható lehetőségek:
  - **Nincs konfigurálva**: Az operációs rendszer alapértelmezett viselkedést szolgál, amely előfordulhat, hogy jelenjen meg egy üzenet.
  - **A Microsoft Edge-ben nyissa meg a helyek beállítás nélkül üzenet megjelenítése**: Az üzenet megjelenítése, ha az IE. Nyissa meg a helyek Internet Explorer. Nem lehet beállítani a Microsoft Edge-ben nyissa meg a helyeket.
  - **Microsoft Edge-ben helyek üzenet megnyitásakor megjelenítése**: Az üzenet megjelenítése, ha az IE. Az üzenet tartalmaz egy **folytathatja a munkát a Microsoft Edge-ben** hivatkozást, így a felhasználók eldönthetik, a Microsoft Edge helyett az Internet Explorer.

  > [!IMPORTANT]
  > Ez a beállítás megköveteli, hogy engedélyezze a **konfigurálása a vállalati üzemmód Webhelylistájának** beállítást, a **küldése az összes intranetes webhelyek az Internet Explorer 11** beállítás, vagy mindkét beállítást.

- **Microsoft kompatibilitási listájának**: **Blokk** megakadályozza, hogy a Microsoft Edge-ben a Microsoft kompatibilitási listájának. A Microsoft ezen listája segítségével a Microsoft Edge megfelelően tudja megjeleníteni az ismert kompatibilitási problémákkal rendelkező webhelyeket. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft kompatibilitási lista használatával.
- **Az előzetes betöltés kezdőlapokat és új lapot**: Válasszon **blokk** megakadályozza, hogy a Microsoft Edge konfigurálások kezdőlapokat és az új lapon. Betöltését minimalizálja a Microsoft Edge elindításához, és a egy új lap betöltése. **Nincs konfigurálva** az operációs rendszer alapértelmezett viselkedést, ezek az oldalak betöltésére, akkor használja.
- **Prelaunch kezdőlapokat és új lapot**: Válasszon **blokk** megakadályozza, hogy a Microsoft Edge előre indítása a kezdőlapokat és új lapon. Előre indítása segít a Microsoft Edge teljesítményét, és minimálisra csökkenti a Microsoft Edge indításához szükséges időt. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést, a prelaunch, akkor ezeket az oldalakat.

### <a name="favorites-and-search"></a>Kedvencek és keresés

- **Kedvencek sáv**: Válassza ki, mi történik a Kedvencek sávra, bármely Microsoft Edge lapján. A választható lehetőségek:
  - **Nincs konfigurálva**: Az operációs rendszer alapértelmezett viselkedést, a Kedvencek sáv összes oldalán elrejtheti, akkor használja. Felhasználók módosíthatják ezt a beállítást.
  - **Elrejtése**: Elrejti a Kedvencek sáv minden oldalon. Felhasználó nem módosíthatja ezt a beállítást.
  - **Megjelenítés**: Az összes a Kedvencek sáv mutatja. Felhasználó nem módosíthatja ezt a beállítást.
- **Kedvencek lista**: Adja hozzá az URL-címek listáját a Kedvencek fájl. Hozzáadhat például `http://contoso.com/favorites.html`.
- **Kedvencek módosításának korlátozása**: **Blokk** , hogy a felhasználók hozzáadása, importálás, rendezés vagy szerkesztését a Kedvencek listájához. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy lehetővé teszi a felhasználóknak, hogy a listában.
- **Microsoft-böngészők között (csak asztali verzióban) Kedvencek szinkronizálása**: **Szükséges** arra kényszeríti a Windows Internet Explorer és Microsoft Edge között a Kedvencek szinkronizálása. Kiegészítést, törlést, a módosítások és a sorrend változásait böngészők között vannak megosztva.  **Nincs konfigurálva** használ az operációs rendszer alapértelmezett, amelyet is biztosíthat a felhasználók számára a kiválasztott Kedvencek szinkronizálása a böngészők között.
- **Alapértelmezett keresőmotor**: Válassza ki az eszközön az alapértelmezett keresőmotort. A végfelhasználók ezt az értéket bármikor módosíthatják. A választható lehetőségek:
  - Alapértelmezett
  - A Bing
  - Google
  - Yahoo
  - Egyéni érték
- **Keresési javaslatok**: **Nincs konfigurálva** lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása címet a címsorba. **Blokk** megakadályozza, hogy ez a funkció.

### <a name="privacy-and-security"></a>Adatvédelem és biztonság

- **InPrivate-böngészés**: **Blokk** megakadályozza, hogy a végfelhasználók InPrivate-böngészési munkamenetet nyissanak. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **Mentse a böngészési előzmények**: **Blokk** megakadályozza, hogy a Microsoft Edge mentése folyamatban van a böngészési előzményeket. **Nincs konfigurálva** a böngészési előzményeket mentésének engedélyezése.
- **Böngészési adatok kilépéskori (csak asztali verzióban) törlése**: **Szükséges** előzmények és böngészési adatok, amikor a felhasználó bezárja a Microsoft Edge törli. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy gyorsítótárazza a böngészési adatok.
- **Szinkronizálja a böngésző beállításai között a felhasználó eszközei**: Válassza ki, hogyan szeretné böngésző beállítások eszközök közötti szinkronizálása. A választható lehetőségek:
  - **Lehetővé teszi**: A Microsoft Edge böngésző beállításai között a felhasználó-eszköz szinkronizálása engedélyezése
  - **Letiltása és engedélyezése a felhasználó felülbírálás**: Letiltása a Microsoft Edge böngésző beállításai között a felhasználó-eszköz szinkronizálása. Ezzel a beállítással a felhasználók felülbírálhatják.
  - **Blokk**: Letiltása a Microsoft Edge böngésző beállítás felhasználó eszközök közötti szinkronizálását. Felhasználók nem bírálja felül ezt a beállítást.
- **Jelszókezelő**: **Blokk** letiltja a Microsoft Edge böngésző jelszókezelő szolgáltatását. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **A cookie-k**: Válassza ki, hogyan kezelje a böngésző cookie-kat. A választható lehetőségek:
  - **Lehetővé teszi**: A cookie-k tárolódnak az eszközön.
  - **Az összes cookie blokkolása**: A cookie-k sehol nincsenek tárolva az eszközön.
  - **Csak harmadik féltől származó cookie blokkolása**: Harmadik féltől származó, vagy partner cookie-k sehol nincsenek tárolva az eszközön.
- **Automatikus kitöltés**: **Blokk** letiltja az automatikus kitöltés funkciót az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára a böngésző (csak Windows 10 asztali verzió) automatikus kiegészítési funkciója beállításainak módosítását.
- **"Do not track" fejlécek küldése**: **Nincs konfigurálva** megköveteli az eszköz "do not track" fejlécek küldése (ajánlott) követési információkat kérő webhelyeknek. Válasszon **blokk** megakadályozza, hogy az eszköz küldése ezeket a fejléceket, amely lehetővé teszi a webhelyek nyomon követhetik a felhasználót.
- **WebRtc localhost IP-cím**: **Blokk** megakadályozza, hogy a felhasználók localhost IP-cím jelenik meg a webes RTC protokoll telefonhívások kezdeményezésekor. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók localhost IP-cím jelennek meg a protokollt használó telefonhívások kezdeményezésekor.
- **Adatgyűjtés élő Csempéhez**: Válasszon **blokk** Windows leállítja az adatgyűjtés a hely rögzítve van élő Csempét a start menüben, a Microsoft Edge-ből. **Nincs konfigurálva** lehetővé teszi, hogy ezt az információt kell gyűjteni.
- **Felhasználó felülbírálhatja a tanúsítványhibákat**: **Blokk** megakadályozza, hogy a felhasználók hozzáférjenek a webhelyeket, amelyeket az SSL vagy TLS hibásak. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók hozzáférhessenek az ezeken a webhelyeken.

### <a name="additional"></a>További

- **A Microsoft Edge böngészőben (csak mobil)**: Válasszon **blokk** , hogy a Microsoft Edge használata az eszközön. Ha letiltja a Microsoft Edge, az egyes beállítások csak asztali vonatkoznak. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft Edge böngésző az eszközön.
- **(Csak asztali verzióban) legördülő címsor**: **Blokk** bemutató javaslatok listáját egy legördülő listában, amikor beírja a Microsoft Edge leáll. A funkció lehetővé teszi, hogy minimalizálja a Microsoft Edge és a Microsoft-szolgáltatások közötti hálózati sávszélességet. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft Edge a javaslatok listájának megtekintéséhez.
- **Teljes képernyős**: Válasszon **blokk** csak a webes tartalom megjelenítése és elrejtése a Microsoft Edge (teljes képernyős mód) a Microsoft Edge elkerülése érdekében. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely lehetővé teszi, hogy a Microsoft Edge teljes képernyős mód használatára.
- **About: flags laphoz**: **Blokk** megakadályozza, hogy a végfelhasználók hozzáférjenek a `about:flags` oldal, amely a fejlesztői és kísérleti beállításokat tartalmazza a Microsoft Edge-ben. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett, így fér hozzá a `about:flags` lapot.
- **Fejlesztői eszközök**: **Blokk** megakadályozza, hogy a végfelhasználók megnyitása a Microsoft Edge fejlesztői eszközeit. **Nincs konfigurálva** lehetővé teszi a felhasználóknak nyissa meg a fejlesztői eszközöket.
- **Bővítmények**: **Nincs konfigurálva** lehetővé teszi, hogy a végfelhasználók számára, hogy a Microsoft Edge-bővítményeket telepítsenek az eszközön. **Blokk** meggátolja a telepítést.
- **Közvetlen telepítési developer extensions**: **Blokk** megakadályozza, hogy a Microsoft Edge közvetlen telepítést, amely telepíti és futtatja a nem ellenőrzött bővítmények használatával a **bővítmények betöltése** funkció. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely közvetlen telepítést lehetővé teheti.
- **Bővítmények szükséges**: Válassza ki, hogy mely bővítmények a Microsoft Edge-ben a végfelhasználók számára nem kapcsolható ki. Adja meg a csomagcsaládok nevéről, és válassza ki **Hozzáadás**. [Keresse meg a csomagcsalád nevének (pfn Megkeresése)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) listák nyújt útmutatást.

  Emellett **importálás** CSV-fájl, amely tartalmazza a csomagcsaládok nevéről.

- **A JavaScript**: Válasszon **blokk** megakadályozza, hogy a Java-parancsfájlok a böngésző az eszközön. **Nincs konfigurálva** parancsprogramok, például Javascript, a Microsoft Edge böngészőben.

## <a name="network-proxy"></a>Hálózati proxy

- **Proxybeállítások automatikus észlelése**: Ha engedélyezve van, az eszköz megpróbálja megkeresni egy PAC-szkript elérési útját.
- **Proxyparancsfájl használata**: Válassza ki ezt a beállítást, adja meg egy elérési útját a proxykiszolgáló konfigurálása PAC-szkript.
  - **Beállítási parancsfájl URL-címe**: Adja meg a proxykiszolgáló konfigurálásához használni kívánt PAC-szkript URL-CÍMÉT.
- **Manuális proxykiszolgáló használata**: Válassza ki az ezzel a beállítással manuálisan adja meg a proxykiszolgálóra vonatkozó információkat.
  - **Cím**: Adja meg a nevét, vagy a proxykiszolgáló IP-címét.
  - **Portszám**: Adja meg a proxykiszolgáló portszámát.
  - **Proxyhasználat alóli kivételek**: Adjon meg semmilyen URL, amelyek nem használhatják a proxykiszolgálót. Az egyes címeket pontosvesszővel választhatja el egymástól.
  - **Proxykiszolgáló kihagyása helyi cím esetén**: A proxykiszolgáló használata az intranet helyi címeinél nem szeretné, ha engedélyezi ezt a beállítást.

## <a name="password"></a>Windows 10

- **Jelszó**: Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
  - **Kötelező jelszótípus**: Meghatározza, hogy a jelszót kell numerikus csak, vagy számokat és.
  - **Jelszó minimális hossza**: Csak a Windows 10 Mobile verzióra vonatkozik.
  - **Bejelentkezési hibák eszköz törlése előtt**: A Windows 10 rendszerű eszközökhöz: Ha a BitLocker engedélyezve van az eszközön, azt van a BitLocker helyreállítási módjába jelentkezzen be a megadott számú sikertelen kísérlet után. Ha az eszköz nincs engedélyezve a BitLocker, ez a beállítás nem vonatkozik. Windows 10 Mobile rendszerű eszközökhöz: Jelentkezzen be, hogy hányszor adja meg, hogy nem sikerül, miután a rendszer törölné az eszközt.
  - **Ennyi perc inaktivitás képernyőzárolás**: Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.
  - **Jelszó érvényessége (napokban)**: Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót.
  - **Korábbi jelszavak újbóli használatának tiltása**: Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg.
  - **Jelszó kérése, ha az eszköz visszatér inaktív állapotból (csak mobil)**: Azt adja meg, hogy köteles-e a felhasználó jelszót megadnia az eszköz feloldásához (csak Windows 10 Mobile esetén).
  - **Egyszerű jelszavak**: Lehetővé teszi egyszerű jelszavak, például 1111 vagy 1234 használatának engedélyezése. Ez a beállítás a Windows-képjelszavak használatát is engedélyezi vagy letiltja.
- **Titkosítási**: Titkosítás engedélyezése a megcélzott eszközökön.

## <a name="per-app-privacy-exceptions"></a>Alkalmazásonkénti adatvédelmi kivételek

Az egyes alkalmazásokhoz beállíthat az alapértelmezett adatvédelmi beállításoktól eltérő adatvédelmi működést.

- **Csomag neve**: Alkalmazás csomagcsaládjának neve.
- **Alkalmazásnév**: Az alkalmazás neve.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok**: Adja meg, hogy az alkalmazás hozzáférhet-e a felhasználónév, képéhez és egyéb kapcsolattartási adataihoz.
- **Háttérben futó alkalmazások**: Adja meg, hogy az alkalmazás futtatható-e a háttérben.
- **Naptár**: Adja meg, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista**: Adja meg, hogy az alkalmazás hozzáférhet-e a hívási előzményekhez.
- **Kamera**: Adja meg, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek**: Adja meg, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **e-mailek**: Adja meg, hogy ez az alkalmazás hozzáférhessen-e-mailt.
- **Hely**: Adja meg, hogy az alkalmazás hozzáférhet-e a helyadatokhoz.
- **Üzenetküldési**: Határozza meg, hogy az alkalmazás olvashasson és küldhessen a szöveges vagy MMS-üzenetek.
- **Mikrofon**: Adja meg az alkalmazás használhatja-e a mikrofont.
- **Mozgásérzékelő**: Adja meg, hogy az alkalmazás hozzáférhet-e eszköz mozgáskövetési adataihoz.
- **Értesítések**: Határozza meg, hogy az alkalmazás hozzáférhet-e értesítéseket.
- **Telefonos**: Adja meg, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennákhoz való**: Egyes alkalmazások rádiófrekvenciás (például Bluetooth) az eszköz küldhet és fogadhat adatokat, és ezeket a rádiófrekvenciás kapcsolatokat kapcsolhatja be és ki kell. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok**: Adja meg, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök**: Válassza ki, ha az alkalmazás használhat megbízható eszközök már csatlakoztatott hardverre vagy hardver, az eszköz. Például használja televízióra, projektorokat stb, megbízható eszközként.
- **Visszajelzés és diagnosztika**: Határozza meg, hogy az alkalmazás hozzáférhet-e diagnosztikai adatokat.
- **Szinkronizálás eszközökkel**: Válassza ki, ha az alkalmazás automatikusan megoszthatja és szinkronizálhat-e olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az eszköz az adatokat.

## <a name="personalization"></a>Személyre szabás

- **Asztali háttérkép URL-címe (csak asztali verzióban)**: Adja meg a Windows asztali háttérképeként használandó JPEG formátumú kép URL-CÍMÉT. A felhasználók nem módosíthatják a képet.

## <a name="printer"></a>Nyomtató

- **Nyomtatók**: Hozzáadott helyi nyomtatók listája.
- **Alapértelmezett nyomtató**: Az alapértelmezett nyomtató beállítása.
- **Felhasználói hozzáférés új nyomtatók hozzáadásához**: Engedélyezi vagy letiltja a helyi nyomtatók használatának.

## <a name="privacy"></a>Személyes adatok védelme

- **Bemenet személyre szabása**: Nem a Cortanához, diktáláshoz vagy a Microsoft Store apps felhőalapú beszédszolgáltatások használatának engedélyezése. Ha engedélyezi ezeket a szolgáltatásokat, a Microsoft hangadatokat gyűjthet a szolgáltatás fejlesztéséhez.
- **A társításra és adatvédelemre vonatkozó felhasználói beleegyezést kérő automatikus elfogadása**: Lehetővé teszi a Windows automatikusan elfogadja a társítási és adatvédelmi beleegyezést kérő üzeneteket az alkalmazások futtatása közben.
- **Felhasználói tevékenységek közzététele**: **Blokk** megakadályozza, hogy a megosztott élmények és a feladatváltóban nemrég használt erőforrások.
- **Csak a helyi tevékenységek**: **Blokk** megakadályozza, hogy a megosztott élmények és a legutóbb használt erőforrások a feladatváltóban, csak a helyi tevékenység alapján.

Beállíthatja, hogy az eszközön lévő összes alkalmazás által elérhető információkat. Definiálhat kivételeket alkalmazásonként az **Alkalmazásonkénti adatvédelmi kivételek** segítségével.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok**: Adja meg, hogy az alkalmazás hozzáférhet-e a felhasználónév, képéhez és egyéb kapcsolattartási adataihoz.
- **Háttérben futó alkalmazások**: Adja meg, hogy az alkalmazás futtatható-e a háttérben.
- **Naptár**: Adja meg, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista**: Adja meg, hogy az alkalmazás hozzáférhet-e a hívási előzményekhez.
- **Kamera**: Adja meg, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek**: Adja meg, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **e-mailek**: Adja meg, hogy ez az alkalmazás hozzáférhessen-e-mailt.
- **Hely**: Adja meg, hogy az alkalmazás hozzáférhet-e a helyadatokhoz.
- **Üzenetküldési**: Határozza meg, hogy az alkalmazás olvashasson és küldhessen a szöveges vagy MMS-üzenetek.
- **Mikrofon**: Adja meg az alkalmazás használhatja-e a mikrofont.
- **Mozgásérzékelő**: Adja meg, hogy az alkalmazás hozzáférhet-e eszköz mozgáskövetési adataihoz.
- **Értesítések**: Határozza meg, hogy az alkalmazás hozzáférhet-e értesítéseket.
- **Telefonos**: Adja meg, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennákhoz való**: Egyes alkalmazások rádiófrekvenciás (például Bluetooth) az eszköz küldhet és fogadhat adatokat, és ezeket a rádiófrekvenciás kapcsolatokat kapcsolhatja be és ki kell. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok**: Adja meg, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök**: Válassza ki, ha az alkalmazás használhat-e megbízható eszközöket. Megbízható eszközök már csatlakoztatott hardverre, vagy a hardver, az az eszköz. Ha például használja televízióra, kivetítőkről, és így tovább megbízható eszközként.
- **Visszajelzés és diagnosztika**: Válassza ki, ha az alkalmazás hozzáférhet-e diagnosztikai adatokat.
- **Szinkronizálás eszközökkel** – Megadhatja, hogy az alkalmazás oszthat-e meg és szinkronizálhat-e adatokat automatikusan olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az adott PC-vel, táblagéppel vagy telefonnal.

## <a name="projection"></a>Kivetítés

- **Felhasználói bevitel vezeték nélküli kijelzők vevőegységeiről**: Blokkok felhasználói bevitel vezeték nélküli kijelzők vevőegységeiről.
- **Kivetítés erre a számítógépre**: Leállítja a Számítógépet kivetítéshez találjanak más eszközök.
- **PIN-kód kérése párosításhoz**: A PIN-kód megkövetelése vetítőeszközhöz való csatlakozáskor

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása**: Válassza ki a diagnosztikai adatok beküldése szintet. A választható lehetőségek:
  - Biztonság
  - Alapszintű
  - Továbbfejlesztett
  - Összes
- **Böngészési adatok Microsoft 365 Analytics a Microsoft Edge küldése**: Ez a funkció használatához állítsa a **használati adatok megosztása** beállítások **bővített** vagy **teljes**. Ez a funkció szabályozza, mely adatok Microsoft Edge Microsoft 365 Analytics küld a vállalati eszközöknél a beállított kereskedelmi azonosítót. A választható lehetőségek:
  - **Nincs konfigurálva**: Az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy ne küldjön böngészési előzmények adatokat használ.
  - **Csak az intranetes adatok küldése**: A rendszergazda az intranetes adatok előzményei küldése
  - **Csak internetes adatküldés**: Lehetővé teszi a rendszergazdák küldése az internet-adatok előzményei
  - **Intranetes és internetes adatküldés**: A rendszergazda az intranetes és internetes adatok előzményei küldése
- **Telemetria proxykiszolgálója**: Adja meg a teljesen minősített tartománynevét (FQDN) vagy az összekapcsolt felhasználói élmények és Telemetria kérelmek, a Secure Sockets Layer (SSL)-kapcsolat használatával továbbítsa a proxykiszolgáló IP-címét. a következő formátumban: *kiszolgáló*:*port*. Ha az elnevezett proxy meghibásodik, vagy ha ez a szabályzat engedélyezve van a megadott proxy nem létezik, az összekapcsolt felhasználói élmények és Telemetria-adatokat nem érkezik meg, és a helyi eszközön marad.

  Példák a formátumra:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Keresés

- **Biztonságos keresés (csak mobil)**: Szabályozhatja, hogy Cortana hogyan szűrje a felnőtt tartalmat a keresési eredményekben. A megadható értékek a **Szigorú** és a **Közepes**, vagy engedélyezhető, hogy a végfelhasználó állítsa be az értékét.
- **Keresés webes eredményeinek megjelenítése**: Webes találatokat, az eszközön kereséskor engedélyező vagy blokkoló.

## <a name="start"></a>Indítás

- **Start menü elrendezése**: Testre szabhatja a start menüje olyan asztali eszközökön, tölthet fel, amely tartalmazza a testreszabásokat, többek között a sorrendben, az alkalmazások szerepelnek, és több XML-fájl. Felhasználók nem módosíthatják a Start menü elrendezése, adja meg.
- **Rögzítheti a csempéket a webhelyek a Start menü**: Olyan képek importálását, amely a Windows Start menü asztali eszközök hivatkozásokként jelennek meg a Microsoft Edge-ből.
- **Levétele a tálcáról alkalmazások**: Válasszon **blokk** leállítja a felhasználó alkalmazásokat távolítson a tálcáról.
- **Gyors felhasználóváltás**: Válasszon **blokk** egyidejűleg bejelentkezett kijelentkezés nélküli felhasználók közötti váltás elkerülése érdekében.
- **Legtöbbet használt alkalmazások**: Válasszon **letiltása** elrejtése megjelenítése a start menüben a leggyakrabban használt alkalmazásokat. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Nemrég hozzáadott alkalmazások**: Válasszon **blokk** megjelenítése a start menüből a nemrégiben hozzáadott alkalmazásokat elrejtéséhez. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Kezdőképernyő módja**: Válassza ki, hogyan jelenik meg a kezdőképernyőn. Választhat a **Teljes képernyős** vagy a **Nem teljes képernyős** üzemmód között.
- **A legutóbb megnyitott elemek a Gyorslistákban**: Válasszon **blokk** legutóbbi jump listák nem jelenik meg a start menüben és tálcán elrejtéséhez. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Alkalmazáslista**: Válassza ki, hogyan jelenik meg a gépház alkalmazásban. A választható lehetőségek: 
  - Összecsukás
  - A Gépház alkalmazás összecsukása és letiltása 
  - A Gépház alkalmazás eltávolítása és letiltása
- **Főkapcsoló**: Válasszon **blokk** való megjelenítése a start menü főkapcsoló elrejtése.
- **Felhasználói csempe**: Válasszon **blokk** elrejtése a megjelenítése a start menü felhasználói csempéjén.
  - **Zárolási**: Válasszon **blokk** elrejtése a `Lock` lehetőséget a start menü felhasználói csempéjén megjeleníthető.
  - **Kijelentkezés**: Válasszon **blokk** elrejtése a `Sign out` lehetőséget a start menü felhasználói csempéjén megjeleníthető.
- **Állítsa le**: Válasszon **letiltása** elrejtése a `Update and shut down` és `Shut down` megjelenítése a start menü főkapcsoló elérhető beállításait.
- **Alvó állapotba**: Válasszon **blokk** elrejtése a `Sleep` megjelenítése a start menü főkapcsoló lehetőségét.
- **Hibernálásra**: Válasszon **blokk** elrejtése a `Hibernate` megjelenítése a start menü főkapcsoló lehetőségét.
- **Váltás másik fiókra**: Válasszon **blokk** elrejtése a `Switch account` csempére a felhasználók megjelenítése a start menüben.
- **Újraindítási lehetőségek**:  Válasszon **letiltása** elrejtése a `Update and restart` és `Restart` megjelenítése a start menü főkapcsoló elérhető beállításait.
- **Dokumentumok a Start menüben**: A Windows Start menüjében a dokumentumok mappájának megjelenítése vagy elrejtése.
- **Letöltések a Start menüben**: A Windows Start menü letöltések mappájának megjelenítése vagy elrejtése.
- **Fájlkezelő a Start**: A Windows Start menüjében a fájlkezelő alkalmazás megjelenítése vagy elrejtése.
- **Otthoni csoport a Start**: A Windows Start menü otthoni csoport mappájának megjelenítése vagy elrejtése.
- **Zene a Start menüben**: A Windows Start menü zene mappájának megjelenítése vagy elrejtése.
- **Hálózat a Start menüben**: A hálózati mappát a Windows Start menü megjelenítése vagy elrejtése.
- **Személyes mappa a Start menüben**: A Windows Start menü személyes mappájának megjelenítése vagy elrejtése.
- **Képek a Start menüben**: A Windows Start menü képeket a mappa megjelenítése vagy elrejtése.
- **Gépház a Start menüben**: A beállítási alkalmazást a Windows Start menü megjelenítése vagy elrejtése.
- **Videók a Start menüben**: A Windows Start menü videókat tartalmazó mappájának megjelenítése vagy elrejtése.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **A Microsoft Edge SmartScreen**: Engedélyezze a Microsoft Edge SmartScreen webhely- és fájlletöltésekhez eléréséhez.
- **Rosszindulatú webhelyelérés**: Felhasználók megakadályozása abban a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja a webhelyére.
- **Ellenőrizetlen fájlletöltés**: Felhasználók megakadályozása abban a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja az ellenőrizetlen fájlok letöltésére.

## <a name="windows-spotlight"></a>Windows Reflektorfény

- **Windows reflektorfény**: Ez a beállítás segítségével az összes Windows reflektorfény-funkciót a Windows 10 rendszerű eszközökön. Ha letiltja ezt a beállítást, a következő beállítások nem érhetők el:
  - **Windows reflektorfény a zárolási képernyőn**: Állítsa le a Windows reflektorfény információt jelenítsen meg az eszköz zárolási képernyőjén a.
  - **Harmadik féltől származó javaslatok a Windows Reflektorfényben**: Állítsa le a Windows reflektorfény a nem Microsoft által közzétett tartalom javasol.
  - **Fogyasztói funkciók**: Letilthatja az olyan fogyasztói funkciókat, mint a Start menü javaslatai vagy a tagsági értesítések.
  - **Windows-tippek**: Blokkolja az előugró tippek megjelenítését Windows teszi lehetővé.
  - **Windows reflektorfény a Műveletközpontban**: Blokk Windows reflektorfény-javaslatok, például új alkalmazást vagy biztonsági tartalom Windows Műveletközpontban parancsot.
  - **Windows reflektorfény személyre szabása**: Leállítja a Windows reflektorfény személyre szabja az eredményeket az eszköz használata alapján.
  - **Windows-üdvözlőképernyőn**: Tiltsa le a Windows üdvözlőprogramjának, amely az új vagy frissített funkciók felhasználói információkat tekinthet meg.

## <a name="windows-defender-antivirus"></a>Windows Defender víruskereső

- **Valós idejű figyelés**: Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű vizsgálatát.
- **Viselkedésfigyelés engedélyezése**: Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.
- **Hálózatvizsgáló rendszer (NIS) hálózati**: NIS segít megvédeni az eszközöket a hálózatalapú biztonsági rések ellen. A Microsoft Endpoint Protection-központból származó ismert sebezhető pontok mintázatai alapján segít észlelni és blokkolni a rosszindulatú hálózati forgalmat.
- **Minden letöltött fájl vizsgálata**: Meghatározza, hogy a Defender az internetről letöltött összes fájlt megvizsgálja-e.
- **Microsoft-webböngészőkben betöltött szkriptek vizsgálata**: Engedélyezi a Defender számára az Internet Explorer által használt parancsfájlok vizsgálatát.
- **Végfelhasználói hozzáférés a Defenderhez**: Azt szabályozza, hogy a Windows Defender kezelőfelülete rejtett legyen-e a végfelhasználók számára. Módosítás esetén a beállítás a felhasználó számítógépének következő újraindításakor lép érvénybe.
- **Aláírás-frissítési időköz (óra)**: Adja meg, melyik Defender ellenőrzi időközönként keressen új aláírásfájlokat.
- **Fájl- és programtevékenység figyelése**: Engedélyezi a Defender számára az eszközökön zajló a fájl- és programtevékenységet.
- **Ennyi nap után törlődjenek karanténba zárt kártevők**: A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok száma **0**, kártevő a karanténban marad, és nem törlődik automatikusan.
- **CPU-használati korlát ellenőrzés közben**: Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**-től **100**-ig).
- **Archív fájlok ellenőrzése**: Engedélyezi a Defender számára az archív fájlok – például ZIP- vagy CAB-fájlok – vizsgálatát.
- **A bejövő e-mailek vizsgálata**: Engedélyezi a Defender számára az eszközre érkező e-mailek azonnal vizsgálatát.
- **Cserélhető adathordozók vizsgálata teljes vizsgálat során**: Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát.
- **Csatlakoztatott hálózati meghajtók vizsgálata teljes vizsgálat során**: Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon tárolt fájlok vizsgálatát.
  Ha a meghajtó a fájlok írásvédettek, a Defender nem távolítható el a bennük talált kártevőket.
- **Hálózati mappákból megnyitott fájlok vizsgálata**: Lehetővé teszi, hogy a Defender számára a megosztott hálózati meghajtókon (például az egy UNC elérési útvonalon megnyitott fájlokat) fájlok vizsgálatát. Ha a meghajtó a fájlok írásvédettek, a Defender nem távolítható el a bennük talált kártevőket.
- **A felhő védelmi**: Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.
- **Rákérdezés a mintaküldés előtt**: E vélhetően kártevő fájlokat, előfordulhat, hogy amelyeken további vizsgálat szükséges vezérlők a rendszer automatikusan elküldje a Microsoftnak.
- **Napi Gyorsvizsgálat időpontja**: Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé.
- **Rendszervizsgálat típusa**: Rendszervizsgálat ütemezése van futtatott vizsgálata szintjét adja meg.
- **Vélhetően nemkívánatos alkalmazások észlelése**: Válassza a védelem szintjét, amikor a Windows észleli a vélhetően nemkívánatos alkalmazások:
  - **Tiltás**
  - **Naplózási** vélhetően nemkívánatos alkalmazásokkal kapcsolatos további információkért lásd: [észlelése és a blokk vélhetően nemkívánatos alkalmazások](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Kártevők észlelése műveletek**: Ez a beállítás segítségével válassza ki a műveleteket, amelyeket a Defender milyen fenyegetési szinteken (alacsony, közepes, magas és súlyos) észlel. A választható lehetőségek:
  - **Tisztítás**
  - **Karantén**
  - **Eltávolítás**
  - **Engedélyezés**
  - **Felhasználó által definiált**
  - **Tiltás**

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender víruskereső – kizárások

- **Fájlok és mappák kizárása a vizsgálatokból és a valós idejű védelem**: A kívánt fájlok és mappák – például **C:\Elérési_út** vagy **%ProgramFiles%\Elérési_út\fájlnév.exe** – felvétele a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.
- **A vizsgálatokból és a valós idejű védelemből kizárandó fájlkiterjesztések**: Vegye fel a kívánt fájlkiterjesztéseket – például **jpg** vagy **txt** – a kivételek listájára. A valós idejű és ütemezett vizsgálatok során nem vizsgálja az ilyen kiterjesztésű fájlokat.
- **A vizsgálatokból és a valós idejű védelemből kizárandó folyamatok**: Vegye fel a kívánt típusú folyamatokat – **.exe**, **.com** vagy **.scr** – a kivételek listájára. A valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.

## <a name="next-steps"></a>További lépések

További technikai részleteket az egyes beállításokról és a Windows támogatott kiadásairól a [Windows 10 szabályzatkonfigurációs szolgáltatói referenciájában](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) talál.

---
title: Előzetes kiadása – Microsoft Intune
titlesuffix: ''
description: A Microsoft Intune előzetes kiadása
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 18cb2c6f9d43ee58f1289c754c16d5b87bcb8139
ms.sourcegitcommit: c84e1845b854704c4b048832e365dd381c7f3754
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54122655"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>A előzetes kiadása – január 2019 a Microsoft Intune

> [!Note]
> NDA-értesítés: A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az itt, nagyon szűk körben megosztott információkra titoktartási szerződés vonatkozik. Az információk egy részletét se tegye közzé közösségi médiában vagy nyilvános webhelyeken, például Twitteren, UserVoice-on, Redditen vagy hasonlón. 

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza, titoktartási szerződés hatálya alatt. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Az információkat ne tweetelje, ne tegye közzé a UserVoice-on, és más módon se ossza meg a vállalatán kívül. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Androidos vállalati alkalmazások <!-- 1352553  -->
Sikerült törölni a felügyelt Google Play-alkalmazások Microsoft Intune-ból fogja. Törli a felügyelt Google Play-alkalmazást, megnyílik a Microsoft Intune az Azure Portalon, és válassza a **ügyfélalkalmazás** > **alkalmazások**. Az alkalmazáslistáról meg, kattintson a három pontra (...) jobb oldalán a felügyelt Google Play-alkalmazást, majd válassza **törlése** a megjelenő listából. Ha egy felügyelt Google Play-alkalmazást töröl alkalmazásokat az alkalmazáslistából, a felügyelt Google Play alkalmazás automatikusan jóvá nem hagyott.

### <a name="managed-google-play-app-type----1352580---"></a>Felügyelt Google Play alkalmazás típusa <!-- 1352580 -->
A **felügyelt Google Play** alkalmazástípus lehetővé teszi, hogy kifejezetten [felügyelt Google Play-alkalmazások](https://play.google.com/work/search?q=microsoft&c=apps) az Intune-hoz. Az Intune rendszergazdájaként Ön fogja tudni most Tallózás, keresése, hagyja jóvá, szinkronizálása és jóváhagyott a felügyelt Google Play-alkalmazások Intune-ban hozzárendelése. Már nem kell külön tallózással keresse meg a felügyelt Google Play konzolon, és többé nem lesz újból hitelesítésre. Válassza ki az Intune-ban **ügyfélalkalmazás** > **alkalmazások** > **Hozzáadás**. Az a **alkalmazástípus** listáról válassza ki **felügyelt Google Play** az alkalmazás típusaként.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>A vállalat által birtokolt, teljes körűen felügyelt Android-eszközök támogatása előzetes verzió <!-- 1574342  -->
Az Intune támogatni fogja a teljes körűen felügyelt Android-eszközök a vállalat által birtokolt "eszköz tulajdonosa" forgatókönyv, ahol eszközök szorosan által felügyelt IT és a rendszer az egyes felhasználókkal kapcsolódó. Ez lehetővé teszi a rendszergazdák számára a teljes eszköz kezelése, egy kiterjesztett tartomány nem érhető el a munkahelyi profilok házirend-vezérlők kényszerítésére, és korlátozza a felhasználók, alkalmazások telepítése csak a felügyelt Google Play áruházból. Beállítása az Android a teljes körűen felügyelt eszközök, hogy halad át **eszközregisztráció** > **Android-eszközök regisztrálási** > **vállalat által birtokolt, teljes körűen felügyelt felhasználói eszközök** . Ne feledje, hogy ez a funkció előzetes verzióban érhető el. Az Intune bizonyos funkciók, például a tanúsítványok, megfelelőségi és feltételes hozzáférés, nem érhetők el jelenleg az Android a teljes körűen felügyelt felhasználói eszközök.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Online licenccel rendelkező Microsoft Store az üzleti alkalmazások telepítése <!-- 1672660  -->
Rendelje hozzá a szükséges online licenccel rendelkező Microsoft Store for Business-alkalmazások az eszköz a környezetben lehet. Központi telepítése a Microsoft Store for Business app így lehetővé teszi az alkalmazásnak, hogy az eszköz összes felhasználójához telepíthetők. Ez a tulajdonság csak a Windows 10 RS4 + asztali eszközökön alkalmazható. Az ügyfélalkalmazások hozzárendelés lapon találhat MSFB Online licencelt alkalmazások telepítésére, az eszköz a környezetben érhető el.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Profil konfigurálása egyes képernyők kihagyásához a beállítási asszisztens működése során <!-- 2276470  -->
A macOS létrehozásakor beléptetési profil lesz konfigurálja úgy, hogy hagyja ki az összes alábbi képernyőt, amikor egy felhasználó halad végig a beállítási asszisztens:
- Android-áttelepítés
- Hang megjelenítése
- Személyes adatok védelme
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Autopilot-profilok hozzárendelése a Minden eszköz virtuális csoporthoz <!--2715522  -->
Autopilot-profilokat rendelhet hozzá a Minden eszköz virtuális csoporthoz. Ehhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** elemet > válasszon egy profilt > **Hozzárendelések** > a **Hozzárendelés a következőhöz** elemnél válassza a **Minden eszköz** lehetőséget. Az Autopilot-profilokról a [Windows-eszközök regisztrálása a Windows AutoPilot használatával](enrollment-autopilot.md) című cikkben tájékozódhat.

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Eszközkonfigurációs profil használatával felügyelt iOS-eszközök tapétáját testreszabása <!-- 2809324  -->
Amikor létrehoz egy eszközkonfigurációs profilt az iOS-eszközök, engedélyezése és az egyes beállítások korlátozása fogja **eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **iOS** tartozó platform > **eszközkorlátozások** profiltípus. A frissítés tartalmaz új **háttérkép** beállítások, amelyek lehetővé teszik a rendszergazdáknak egy .png, .jpg vagy JPEG-kép, háttérképeként használandó a képet, és a felhasználók nem módosíthatják a háttérkép. A háttér beállításokat csak a felügyelt eszközökre vonatkoznak. A jelenlegi beállítások listájáért lásd: [iOS-eszközök korlátozásaira vonatkozó beállítások](device-restrictions-ios.md).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Bejelentési értesítések Win32-alkalmazások <!-- 3136566   -->
Bemutató végfelhasználói bejelentési értesítések egy alkalmazás-hozzárendelés le tudják. Az Intune-ból, válassza ki a **ügyfélalkalmazás** > **alkalmazások** > Válassza ki az alkalmazást > **Assignemnts** > **csoportokhozközétartozik**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Bluetooth-névjegyek megosztása eltávolítják az Eszközkorlátozások > Android Enterprise eszköz tulajdonosa <!-- 3598396 -->
Az Android Enterprise-eszközöket egy eszközkorlátozási profilt hoz létre, ha van egy **forduljon megosztása Bluetooth használatával** beállítás. Ebben a frissítésben a **forduljon megosztása Bluetooth használatával** beállítást eltávolítja (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android Enterprise** tartozó platform > **Eszközkorlátozások > eszköz tulajdonosa** profiltípus >  **Általános**). 

A **forduljon megosztása Bluetooth használatával** beállítás nem támogatott az Android vállalati eszköz tulajdonosa management. Ezzel a beállítással a rendszer eltávolítja, ha ez nem érinti az bármely eszköz vagy a bérlők, akkor is, ha ez a beállítás engedélyezve van, és konfigurálva a környezetben.

Beállítások aktuális listájának megtekintéséhez, keresse fel a [engedélyezi, vagy korlátozhatja a funkciókat Android Enterprise-eszközbeállítások](device-restrictions-android-for-work.md).

A következőkre vonatkozik: Androidos vállalati eszköz tulajdonosa

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise-alkalmazás – hogy az alkalmazás üzembe helyezése <!-- 1171203 -->
Android-eszközökhöz a egy nem regisztrált alkalmazás alkalmazásvédelmi szabályzat regisztráció nélkül (alkalmazás-TUDJUK) a telepítési forgatókönyvben is elérheti, használja a felügyelt Google Play áruházbeli alkalmazások telepítése és ÜZLETÁGI alkalmazások a felhasználók számára. Pontosabban, az informatikai részleg már nem igényel a végfelhasználók számára, hogy lazábbá tehető az eszközeik biztonsági irányelvei, tiltják azáltal, hogy telepítések az ismeretlen forrásból származó alkalmazás katalógus és telepítési élményt nyújt a végfelhasználók számára. Emellett ebben a telepítési forgatókönyvben egy jobb végfelhasználói élményt biztosít.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Automatikus csatlakozás és szabályok továbbra is fennáll, DNS-beállítások használata a Windows 10-es és újabb rendszerű eszközök esetén új beállítások <!-- 1333665, 2999078 -->
Windows 10 és újabb rendszerű eszközök lesz képes feloldani a tartományok, mint a contoso.com DNS-kiszolgálók listáját tartalmazó VPN konfigurációs profil létrehozásához. Ez magában foglalja a névfeloldáshoz új beállítások (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > kiválasztása **Windows 10-es és újabb verziók** tartozó platform > Válasszon **VPN** profiltípus > **DNS-beállítások** >**Hozzáadás**): 

- **Automatikus csatlakozás**: Amikor **engedélyezve**, az eszköz automatikusan csatlakozik a VPN-t, amikor egy eszköz kapcsolatba lép az ad meg, például a contoso.com tartományhoz.
- **Állandó**: Alapértelmezés szerint minden névfeloldási házirend táblája (NRPT) szabályok aktívak, amíg az eszköz csatlakoztatva van, a VPN-profil használatával. Ha a beállítás értéke **engedélyezve** az NRPT-szabály, a szabály aktív marad az eszközön, akkor is, ha a VPN bontja a kapcsolatot. A szabály marad, amíg a VPN-profil eltávolítása, vagy manuálisan eltávolítását a szabályt, amely végezhető PowerShell használatával.

[A Windows 10-es VPN-beállítások](vpn-settings-windows-10.md) ismerteti a jelenlegi beállítások listájában. 

### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user----1333642---"></a>Titkosítása és aláírás egy felhasználó több eszközt, az S/MIME használata <!-- 1333642 -->
S/MIME e-mail titkosításának importált tanúsítványprofillal is támogatott lesz (**eszközkonfiguráció** > **profilok** > **profillétrehozása** > Válassza ki a platformot > **importált PKCS-tanúsítvány** profil típusa). Az Intune-ban a tanúsítványok PFX formátumban importálhatók. Az Intune képes ugyanazokat a tanúsítványokat az egy felhasználó által regisztrált több eszközre is telepíteni. Ez a következőket is magában foglalja:

- A natív iOS-es e-mail-profil támogatja az S/MIME titkosítás PFX formátumú importált tanúsítványok használatával történő engedélyezését.
- A Windows Phone 10 rendszerű eszközök natív levelezőalkalmazása automatikusan az S/MIME tanúsítványt használja.
- A privát tanúsítványok több platformon is telepíthetők. A S/MIME-ot azonban nem minden e-mail-alkalmazás támogatja.
- Más platformokon az S/MIME engedélyezéséhez szükség lehet a levelező alkalmazás manuális konfigurálására.  
- Az S/MIME titkosítást támogató e-mail-alkalmazások esetleg az MDM által nem támogatható módon kezelik az S/MIME e-mail-titkosításhoz szükséges tanúsítványok fogadását, például a közzétevőjük tanúsítványtárából olvassák ki azokat.

Támogatott a következő rendszereken: Windows, Windows Phone 10-es, macOS, iOS, Android

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Súgó és támogatás lapjáról a Windows céges portál alkalmazásban <!-- 1488939 -->
Egy új lapot a rendszer felveszi a Windows céges portál alkalmazásba. A Súgó és támogatási oldallal biztosítja a segélyszolgálat kapcsolattartási adatait. A végfelhasználók is tud küldeni a céges portál naplózza, abban az esetben, ha problémái vannak lesz. Az oldal is tartalmaz, amelyek segítik a végfelhasználók számára egy gyakori kérdésekkel foglalkozó szakaszban.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Használja a megbízható hálózatok észlelése a Windows 10-es eszközök VPN-profilokhoz <!-- 1500165 -->
Megbízható hálózatok észlelése használatakor lesz képes megakadályozni, hogy a VPN-profilok automatikusan hozzon létre egy VPN-kapcsolatot, amikor a felhasználó már szerepel a megbízható hálózat. Fogja tudni hozzáadni a DNS-utótagok engedélyezése a Windows 10 rendszerű eszközökre a megbízható hálózatok észlelése és újabb verziók (**eszközkonfiguráció** > **profilok**  >   **Profil létrehozása** > **Windows 10 és újabb** tartozó platform > **VPN** profiltípus).
[A Windows 10-es VPN-beállítások](vpn-settings-windows-10.md) sorolja fel az aktuális VPN-beállításokat.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Az Intune App SDK támogatni fogja a 256 bites titkosítási kulcsok <!-- 1832174 -->
Az Androidhoz készült Intune App SDK 256 bites titkosítási kulcsok fogja használni, ha az alkalmazásvédelmi szabályzatok engedélyezve van a titkosítási. Az SDK továbbra is támogatja a 128 bites kulcsok tartalmat és a régebbi SDK-t használó alkalmazások kompatibilitását.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917-1063203---"></a>Engedélyezve van a megosztott számítógép-beállítások az Intune-profil <!-- 1907917, 1063203 -->
Jelenleg konfigurálhatja a megosztott PC-beállítások Windows 10 rendszerű asztali eszközökön egy egyéni OMA-URI beállítás használatával. Új profil megjelenik a megosztott PC-beállítások konfigurálása (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10 és újabb** > **megosztott több felhasználó-eszköz**).

A következőkre vonatkozik: A Windows 10 és újabb verziók, Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-házirendek frissítése a hitelesítési módszert, és a vállalati portál alkalmazás telepítése  <!-- 1927359 -->
A beállítási asszisztenssel keresztül egy Apple vállalati tulajdonú eszközök regisztrálási módszerei már regisztrált eszközök, az Intune már nem támogatja a vállalati portál manuális telepítés a végfelhasználók az app store áruházból. Ez a változás csak akkor jelentősége, amikor Ön az Apple beállítási asszisztens regisztráció során hitelesítsék magukat. Ez a változás csak is hatással van a regisztrált iOS-eszközöket:  
* Az Apple configuratorral
* Apple üzleti vezető
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Ha a felhasználók a vállalati portál alkalmazást az App store áruházból telepítik, és próbálja meg, ezek eszközöket regisztrálni, akkor egy hibaüzenetet fog kapni. Ezek az eszközök csak céges portál használatához, amikor, a leküldött, automatikusan, az Intune-regisztráció során vár. Regisztrációs profilok az Intune-ban az Azure Portalon is frissülnek, így megadhatja, hogy miképpen hitelesítik eszközök, és ha kapnak a vállalati portál alkalmazást. Ha azt szeretné, hogy a DEP-eszközök felhasználói szeretné, hogy a vállalati portálon, szüksége lesz a beállítások megadása egy regisztrációs profilt. Emellett a **az eszköz azonosítására** a céges portál alkalmazás képernyőjén hamarosan elavulttá válnak.  
Is telepíthetik a vállalati portált a DEP-eszközökön már regisztrált, nyissa meg az Intune-nak frissítenie > ügyfélalkalmazások, és küldje le az alkalmazás-konfigurációs házirendek segítségével felügyelt alkalmazásként. A jövőbeli docs részletei elvégezheti ezeket a lépéseket ismerteti.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>A nem rendszergazdák engedélyezhetik a BitLocker az Azure AD-csatlakoztatott Windows 10 rendszerű eszközökön<!-- 2147379 -->
Ha engedélyezi a BitLocker-beállítások Windows 10 rendszerű eszközökön (**eszközkonfiguráció** > **profilok** > **profil létrehozása**  >  **Windows 10 és újabb** tartozó platform > **az Endpoint protection** profiltípus > **Windows titkosítási**), akkor adja hozzá a BitLocker-beállítások. A frissítés tartalmaz egy új BitLocker beállítását, hogy általános jogú felhasználók (nem rendszergazda), engedélyezheti a titkosítást. A jelenlegi beállítások megtekintéséhez lásd: [Endpoint protection-beállítások Windows 10-es](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-app-pin----2298397---"></a>Intune az alkalmazás <!-- 2298397 -->
A rendszergazdáknak, fogja tudni tartalomvédelemre konfigurálni a végfelhasználók úgy megvárhatja, amíg Intune az alkalmazáshoz tartozó PIN-kódot kell módosítani a napok számát. Az új beállítás lesz elérhető az Azure Portalon válassza **Intune** > **ügyfélalkalmazás** > **alkalmazásvédelmi szabályzatok**  >  **Házirend létrehozása** > **beállítások** > **a hozzáférési követelmények**. Ez a funkció az iOS- és Android-eszközökön elérhető lesz. Ez a beállítás egy pozitív egész értéket támogatja.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Új Windows 10 frissítési beállítások <!-- 2626030 2512994 -->
A Windows 10-es frissítési körök, az lesz képes:
- visszaállítás az eredeti automatikus frissítési beállítások gépeken futó Windows 10-es gépen a *2018. október frissítése*
- Konfiguráljon egy új szoftverhasználat-frissítési beállítást, amely lehetővé teszi, hogy Ön blokkolhatja vagy engedélyezheti a felhasználók számára történő telepítésének felfüggesztése a *beállítások* gépek. 

### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS e-mail-profilok segítségével az S/MIME aláíráshoz és titkosításhoz <!-- 2662949 -->
Létrehozhat egy e-mail-profilt, amely tartalmazza a különböző beállításokkal lesz. Ez magában foglalja az S/MIME-beállítások, aláírása és titkosítása az iOS-eszközök e-mail-üzeneteket is használható (**eszközkonfiguráció** > **profilok**  >   **Profil létrehozása** > Válasszon **iOS** tartozó platform > **E-mail** profiltípus).

[iOS e-mail-konfigurációs beállítások](email-settings-ios.md) aktuális beállításokat sorolja fel.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>Hagyja ki a további beállítási asszisztens képernyők az iOS DEP-eszközökön <!-- 2687509 -->
A képernyők jelenleg kihagyhatja, mellett is elérheti beállítása az iOS DEP-eszközök a beállítási asszisztens képernyőinek kihagyásához amikor egy felhasználó regisztrálja az eszközt: Képviselő hangvételét, adatvédelmi, Android áttelepítési, kezdőlap gombot, iMessage & FaceTime, bevezetési, tekintse meg a Migrálási, megjelenését, képernyő idő, szoftverfrissítés, SIM telepítő megjelenítéséhez.
Válassza ki, amely a képernyők kihagyásához, lépjen a **eszközregisztráció** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** > Válasszon egy tokent > **Profilok** > Válasszon egy profilt > **tulajdonságok** > **beállítási asszisztens testreszabása** > Válasszon **elrejtése**  bármely képernyők kihagyásához a > **OK**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Néhány BitLocker-beállítások támogatja a Windows 10 Pro kiadás<!-- 2727036 -->
Hozzon létre egy konfigurációs profilt, amely beállítja az endpoint protection-beállítások Windows 10 rendszerű eszközökön, beleértve a BitLocker képes lesz. Ez támogat bizonyos BitLocker-beállítások Windows 10 Professional kiadást. A jelenlegi Windows 10 Kiadásfrissítési beállításainak megtekintéséhez lásd: [Endpoint protection-beállítások Windows 10-es](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-device-reporting-fields----2748738---"></a>Az Intune eszköz reporting mezők <!-- 2748738 -->
Jelentéskészítés területén, beleértve az alkalmazás regisztrációs azonosító, Android gyártója, modell, és biztonsági javítást, valamint IOS-es modell további eszköz az Intune biztosítja. Az Intune-ban, ezek a mezők lesz elérhető kiválasztásával **ügyfélalkalmazás** > **alkalmazásvédelem állapota** kiválasztása és **alkalmazásvédelmi jelentés: iOS, Android**. Emellett ezek a paraméterek segítségével konfigurálja a **engedélyezése** lista az eszköz gyártója (Android), a **engedélyezése** lista az eszköz modellje (Android és iOS) és a minimális Android biztonsági javítási szintnek verzió beállítását. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>Megosztott eszköz konfigurációja új üzenet a zárolási képernyőn iOS-eszközökhöz az Azure Portalon <!-- 2809362 -->
Ha iOS-eszközökhöz készült konfigurációs profilt hoz létre, adhat hozzá lesz **megosztott eszköz konfigurációja** beállításokat adott szöveg megjelenítése a zárolási képernyőn. Ez tartalmazza a következő módosításokat: 

- A **megosztott eszköz konfigurációja** beállítások az Azure Portalon a rendszer átnevezi "Üzenet a zárolási képernyőn (csak felügyelt)" (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > Válasszon **iOS** tartozó platform > Válasszon **eszközfunkciók** profiltípus > **zárolása Üzenet képernyőn**).
- Zárolási képernyőjén üzenetek hozzáadásakor beszúrhat sorozatszám, eszköz nevét, vagy egy másik eszköz-specifikus érték a változóként **eszközcímke-információ**. Beírhatja például `Device name: {{device name}}` vagy `Serial number is {{serial number}}` kapcsos zárójelek használatával. [iOS-jogkivonatok](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) felsorolja a rendelkezésre álló jogkivonatokat használhat.

[Beállításai üzenetek megjelenítéséhez a zárolási képernyőn](shared-device-settings-ios.md) aktuális beállításokat sorolja fel.

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Részletesebb regisztrációs korlátozási hiba üzenetkezelés <!-- 3111564-->
Részletes hibaüzenetek elérhető lesz, amikor a regisztrációs korlátozások nem teljesülnek. Tekintse meg ezeket az üzeneteket, lépjen a **Intune** > **hibaelhárítás** >, és ellenőrizze a regisztrációs hibák tábla.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Vállalati Android-eszköz tulajdonosa eszköz új értesítés, útmutatók és keyguard beállítások <!-- 3201839 3201843 -->
A frissítés számos új funkciót, a vállalati Android-eszköz tartalmaz az eszköz tulajdonosa futtatásakor. Ezeket a funkciókat használ, lépjen a **eszközkonfiguráció** > **profilok** > **profil létrehozása** > a **Platform**, válassza a **Android Enterprise** > a **profiltípus**, válassza a **csak az eszköz tulajdonosa** > **eszköz Korlátozások**.
Új funkciók: 
- Tiltsa le a megjelenítése, beleértve a bejövő hívások, a rendszer riasztásai, rendszerhibák és több rendszer értesítései
- Oktatóanyagok és útmutatók az első alkalommal megnyitott alkalmazások indítása kihagyása javasol.
- Speciális keyguard beállításait, például a kamera, értesítések, ujjlenyomattal történő Zárolásfeloldás letiltása és egyéb

A jelenlegi beállítások megtekintéséhez lépjen a [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Vállalati Android-eszköz tulajdonosa eszköz használhat a mindig bekapcsolva beállítású VPN-kapcsolatok <!-- 3202194 -->
Ebben a frissítésben mindig bekapcsolt VPN-kapcsolatok Android enterprise eszköz tulajdonosa eszközökön is használhatja. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
Engedélyezheti a mindig bekapcsolt VPN **eszközkonfiguráció** > **profilok** > **profil létrehozása**  >   **Android enterprise** tartozó platform > **eszközkorlátozások** az eszköz tulajdonosa csak > **kapcsolat** beállításait. A jelenlegi beállítások megtekintéséhez lépjen a [eszközkorlátozásokra vonatkozó beállítások az Android Enterprise](device-restrictions-android-for-work.md).

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Új beállítás az end folyamatok a Feladatkezelő Windows 10 rendszerű eszközökön <!-- 3285177 --> 
A frissítés tartalmaz egy új beállítás a Feladatkezelő használatát a Windows 10 rendszerű eszközökön folyamatait. Eszközkonfigurációs profil használatával (**eszközkonfiguráció** > **profilok** > **profil létrehozása** > a **Platform** , válassza a **Windows 10-es** > a **profiltípus**, válassza a **eszközkorlátozások** > **általános** beállítások), engedélyezése vagy tiltása, ezt a beállítást választja.
A jelenlegi beállítások megtekintéséhez lépjen a [Windows 10-es eszközkorlátozási beállítások](device-restrictions-windows-10.md).
A következőkre vonatkozik: Windows 10 és újabb

### <a name="additional-settings-for-outlook----3301182---"></a>Az Outlook további beállítások <!-- 3301182 -->
Mostantól konfigurálhatja az IOS rendszerhez készült Outlook és az Intune-nal Android további beállításokat.  A beállítások a következők:
- Csak a munkahelyi vagy iskolai fiókkal az Outlookban az iOS és Android rendszerhez használható engedélyezése
- Modern hitelesítéssel az Office 365 és a hibrid, modern hitelesítést a helyszíni fiókok telepítése
- Használat `SAMAccountName` az e-mail profilban, az egyszerű hitelesítés kijelölésekor a felhasználónév mező
- Lehetővé teszi az ügyfelek menteni
- Konfigurálja a külső címzetteknek e-mail tippek
- Konfigurálása **szűrt levelek**
- Biometrikai IOS rendszerhez készült Outlook eléréséhez szükséges 
- Külső képek letiltása

> [!NOTE]
> Ha az Intune alkalmazásvédelmi szabályzatokat használ a vállalati identitások kezelésére, érdemes lehet nem engedélyezi az **biometrika megkövetelése**. További információkért lásd: **vállalati hitelesítő adatok megkövetelése a hozzáféréshez** a [hozzáférési beállítások iOS](app-protection-policy-settings-ios.md#access-settings) és [Android-beállításokat](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és átkerülnek a saját konfigurációs profil <!-- 3322847 -->
Az Intune-ban a felügyeleti sablonok (**eszközkonfiguráció** > **felügyeleti sablonok**) jelenleg privát előzetes verzióban érhető el. Ez a frissítés: Felügyeleti sablonok az Intune-ban kezelheti körülbelül 300 beállításokat tartalmaz. Korábban ezek a beállítások csak megtalálható a Helyicsoportházirend-szerkesztő.
Felügyeleti sablonok érhetők el a nyilvános előzetes verzióban felügyeleti sablonok helyez át a **eszközkonfiguráció** > **felügyeleti sablonok** való **eszköz konfigurációs** > **profilok** >**profil létrehozása** > a **Platform**, válassza a  **Windows 10 és újabb**, a **profiltípus**, válassza a **felügyeleti sablonok**.
Jelentéskészítés engedélyezve van a következőkre vonatkozik: Windows 10 és újabb

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune-ban macOS céges portálra sötét üzemmód <!-- 3300524 -->
Az Intune-ban macOS céges portálra sötét mód mostantól támogatja a macOS-hez. Sötét üzemmód engedélyezésével 10.14 + macOS-eszközön, a céges portál lehetőség a megjelenését, színek a tükrözés mód.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>A Microsoft által ajánlott beállítások használata a biztonsági előírásokhoz <!-- 2055484 -->
Az Intune integrálható más, biztonsági célú szolgáltatásokkal, például a Windows Defender ATP-vel és az Office 365 ATP-vel. Az ügyfelek a Microsoft 365-szolgáltatásokon átívelő közös stratégiát és összefüggő, teljes körű biztonsági munkafolyamatokat kérnek. Célunk a stratégiák összehangolása és ezáltal olyan megoldások létrehozása, amelyek hidat képeznek a biztonsági műveletek és a gyakori felügyeleti feladatok között. Az Intune-ban ezen cél elérésére a Microsoft által ajánlott „biztonsági előírások” közzétételével törekszünk (**Intune** > **Biztonsági előírások**).  A rendszergazdák így képesek arra, hogy közvetlenül ezekből az előírásokból hozzanak létre biztonsági szabályzatokat, és üzembe helyezzék őket a felhasználók számára. Emellett testreszabhatják az ajánlott eljárásokat a szervezet igényeihez igazítva. Az Intune biztosítja, hogy az eszközök megfeleljenek ezeknek az előírásoknak, és értesíti a rendszergazdákat, ha egy felhasználó vagy eszköz nem felel meg.

### <a name="scope-tags-for-apps---1081941---"></a>Hatókörcímkék alkalmazásokhoz <!--1081941 -->
Hatókörcímkék létrehozásával korlátozhatja a hozzáférést az Intune erőforrásaihoz. Adjon hozzá hatókörcímkét egy szerepkör-hozzárendeléshez, majd adja hozzá a hatókörcímkét egy konfigurációs profilhoz. A szerepkör csak a megfelelő hatókörcímkével rendelkező (vagy hatókörcímke nélküli) erőforrásokhoz férhet hozzá.
Hatókörcímke hozzáadásához válassza az **Intune-szerepkörök** > **Hatókör (Címkék)** > **Létrehozás** lehetőséget.
Hatókörcímke szerepkör-hozzárendeléshez való hozzáadásához válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** > **Hatókör (Címkék)** lehetőséget.
Hatókörcímke konfigurációs profilhoz való hozzáadásához válassza az **Eszközkonfiguráció** > **Profilok** > válasszon egy profilt > **Tulajdonságok** > **Hatókör (Címkék)** lehetőséget.

### <a name="tenant-health-dashboard----1124854---"></a>Bérlőállapot-figyelő irányítópult <!-- 1124854 -->
Az Intune Bérlő állapota oldala egyetlen helyen nyújt információkat a bérlő állapotát illetően. Az oldal 4 szakaszból áll:  
- **Bérlő részletei**: Olyan információkat tartalmaz az MDM-szolgáltató, például az összes beléptetett eszközök esetén a bérlőben, és a licencek számát. Ebben a szakaszban található a bérlő jelenlegi szolgáltatáskiadása is.
- **Összekötő állapota**: A konfigurált összekötők, például az Apple VPP for Business, a Windows Store információkat tartalmaz, és a tanúsítvány-összekötőt. Az összekötők az aktuális állapotuk alapján *Kifogástalan*, *Figyelmeztetés* vagy *Nem kifogástalan* jelölést kapnak.
- **Az Intune szolgáltatás állapotát**: Aktív incidens által érintett vagy valamilyen okból kimaradás lép tartalmazza a bérlő számára. Az ebben a szakaszban szereplő információk közvetlenül az Office Üzenetközpontból ([https://portal.office.com](https://portal.office.com)) származnak.
- **Az Intune hírek**: Aktív üzenetek tartalmazza a bérlő, amelyek közé tartozik többek között az értesítéseket, hogy a bérlő megkapta-e a legújabb Intune-funkciók. Az ebben a szakaszban szereplő információk közvetlenül az Office Üzenetközpontból ([https://portal.office.com](https://portal.office.com)) származnak.


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Felhasználói regisztráció nélkül telepített WIP-szabályzatok <!-- 1434452 -->
Windows Information Protection- (WIP-) szabályzatok telepíthetők anélkül is, hogy a felhasználóknak regisztrálniuk kellene Windows 10 rendszerű eszközüket. Ez a konfiguráció lehetővé teszi, hogy a vállalatok biztosítsák a vállalati dokumentumok védelmét a WIP-konfiguráció alapján, miközben a felhasználó saját maga felügyelheti Windows-eszközeit. Ha a dokumentumok védve vannak WIP-szabályzattal, a védett adatokat az Intune-rendszergazdák szelektív módon törölhetik. Ehhez ki kell választaniuk a felhasználót és az eszközt, majd el kell küldeniük egy adattörlési kérést, amelynek hatására WIP-szabályzat által védett összes adat használhatatlanná válik. Ehhez az Azure Portal Intune részén válassza a **Mobilalkalmazás** > **Alkalmazás szelektív törlése** lehetőséget.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Az Alkalmazásvédelmi szabályzat (APP) beállításai webes adatokhoz <!-- 2662995 -->
A webes tartalmakra vonatkozó APP szabályzatok beállításait az Android- és iOS-eszközökön is frissítjük, hogy hatékonyabban kezelhetők legyenek a webes http- és https-hivatkozások, valamint az univerzális iOS-hivatkozásokon és Android-alkalmazáshivatkozásokon keresztüli adatátvitel.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Más MDM által használt Apple VPP-token <!-- 1488946 -->
Az Intune felismeri, ha egy Apple mennyiségi licencszerződés (VPP) keretében vásárolt tokent az Intune és egy másik MDM egyidejűleg használ, és megjeleníti az adatokat.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Elavult eszközök az eszközmegfelelőségi irányítópulton <!-- 1981119 -->
Egy jövőbeli frissítés eltávolítja az elavult eszközöket az eszközmegfelelőségi irányítópultról. Ez módosítani fogja a megfelelőségi számokat.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Változás a helyszíni összekötők frissítési folyamatában <!-- 2277554 -->
Felhasználói visszajelzések alapján megváltozik a helyszíni összekötők frissítésének folyamata. Miután elvégezte a helyszíni összekötő kezdeti telepítését, a frissítések automatikusan lezajlanak. Ez a változás először a Microsoft Intune-hoz készült új PFX-tanúsítvány-összekötőnél jelenik meg, majd a soron következő további helyszíni összekötőknél is. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>A Configuration Manager megfelelőségének ellenőrzése <!-- 2192052 -->
Egy későbbi frissítés része lesz a System Center Configuration Manager új megfelelőségi beállítása (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Windows 10**). A Configuration Manager megfelelőségi jeleket küldi az Intune-nak. Az Intune beállításával megkövetelhető, hogy minden Configuration Manager-jelre „megfelelő” legyen a válasz.

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ha az eszközön bármelyik program ismeretlen állapotban van, akkor az eszköz nem megfelelőnek fog minősülni az Intune-ban.

A Windows 10 és újabb verziókra vonatkozik



## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).




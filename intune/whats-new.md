---
title: Újdonságok a Microsoft Intune-ban – Azure | Microsoft Docs
titlesuffix: ''
description: Az Azure-beli Intune-portál újdonságai
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/14/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: 41c5af504bb65a661e55d09d735a78df780deb84
ms.sourcegitcommit: 698af815f6de2c4f003f6da428bbfb0680daafa0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43092175"
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a [jövőbeni változtatásokról](#whats-coming), a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi verziókról](whats-new-archive.md) is. Egyes funkciók bevezetése több hetet igénybe vehet, így előfordulhat, hogy nem elérhetők a felhasználók számára az első héten.

> [!Note]
> A mobileszköz-kezelés (MDM) új hibrid funkciójával kapcsolatos további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   


## <a name="week-of-august-27-2018"></a>2018. augusztus 27-i hét

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP eszközlicencek használata a Céges portál előzetes kiépítésére a DEP-regisztráció során <!-- 1608345 -->
Mostantól mennyiségi vásárlási program (Volume Purchase Program, VPP-) eszközlicencekkel előre is kiépítheti a Céges portált, amikor regisztrál a készülékregisztrációs programban (DEP-ben). Ehhez a [regisztrációs profil létrehozása vagy szerkesztése](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) során kell megadni a Céges portál telepítéséhez használni kívánt VPP-jogkivonatot. Fontos, hogy a jogkivonat ne járjon le, és hogy elég licenccel rendelkezzen a Céges portál alkalmazáshoz. Amennyiben a jogkivonat lejár vagy a licencei elfogynak, az Intune az App Store-beli Céges portált fogja leküldeni (ilyenkor a rendszer kéri az Apple-azonosítót).


## <a name="week-of-august-14-2018"></a>2018. augusztus 14-i hét

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS-támogatás az Apple Készülékregisztrációs programjában <!-- 747651 -->
Az Intune mostantól támogatja a macOS rendszerű eszközök regisztrálását az Apple készülékregisztrációs programjába (DEP). További információkért lásd: [macOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>2018. július 23-ai hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1895847 -->
A Microsoft Intune lehetővé teszi macOS üzletági alkalmazások **Kötelező** vagy **Regisztrációval elérhető** beállítással való üzembe helyezését. A végfelhasználók elvégezhetik az alkalmazások **Rendelkezésre álló** állapotban való üzembe helyezését a macOS-es céges portálon vagy a [Céges portál webhelyén](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>A Kioszk mód támogatása beépített iOS-alkalmazások számára <!-- 2051098 -->
iOS-eszközökön a Store-alkalmazások és a Felügyelt alkalmazások mellet mostantól a beépített alkalmazásoknál is (mint például a Safari) kiválasztható a Kioszk mód.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Az Office 365 Pro Plus alkalmazás üzemelő példányának szerkesztése <!-- 2150145 -->
Microsoft Intune-rendszergazdaként több lehetősége van saját Office 365 Pro Plus üzemelő példányainak szerkesztésére. Továbbá, ezentúl már nem szükséges törölni az üzemelő példányokat az alkalmazáscsomag tulajdonságainak megváltoztatásához. Az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazások** lehetőséget. Az alkalmazások listáján jelölje ki a saját Office 365 Pro Plus csomagot.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Már elérhető az Androidhoz használható frissített Intune App SDK <!-- 2744271-->

Elérhető az Androidhoz használható Intune App SDK frissített verziója, mely támogatja az Android P kiadását. Ha Ön alkalmazásfejlesztő, és az Intune App SDK-t használja Androidhoz, telepítenie kell az Intune App SDK frissített verzióját, hogy biztosíthassa az Intune megfelelő működését az alkalmazásainál Android P-eszközökön. Az Intune App SDK jelen frissített verziója tartalmaz egy beépülő modult, amely gondoskodik az SDK frissítéseiről. A már meglévő integrált kódokat nem szükséges újraírnia. További információt az [Intune App SDK Androidhoz](https://github.com/msintuneappsdk/ms-intune-app-sdk-android) című témakörben talál. Ha az Intune-hoz a régi megjelölő stílust használja, javasoljuk, hogy használja az aktatáska ikont. A márkajelzési részletekről [ebben a GitHub-adattárban](https://github.com/msintuneappsdk/intune-app-partner-badge) tájékozódhat.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>S/MIME használata titkosításhoz és aláíráshoz egy felhasználó több eszközén <!-- 1333642 -->
A frissítés része az új importált tanúsítványprofilt használó S/MIME e-mail-titkosítás (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > platform kiválasztása > **Importált PKCS-tanúsítvány** profiltípus). Az Intune-ban a tanúsítványok PFX formátumban importálhatók. Az Intune képes ugyanazokat a tanúsítványokat az egy felhasználó által regisztrált több eszközre is telepíteni. Ez a következőket is magában foglalja:

- A natív iOS-es e-mail-profil támogatja az S/MIME titkosítás PFX formátumú importált tanúsítványok használatával történő engedélyezését.
- A Windows Phone 10 rendszerű eszközök natív levelezőalkalmazása automatikusan az S/MIME tanúsítványt használja.
- A privát tanúsítványok több platformon is telepíthetők. A S/MIME-ot azonban nem minden e-mail-alkalmazás támogatja.
- Más platformokon az S/MIME engedélyezéséhez szükség lehet a levelező alkalmazás manuális konfigurálására.  
- Az S/MIME titkosítást támogató e-mail-alkalmazások esetleg az MDM által nem támogatható módon kezelik az S/MIME e-mail-titkosításhoz szükséges tanúsítványok fogadását, például a közzétevőjük tanúsítványtárából olvassák ki azokat.

Támogatott a következőkön: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Eszközmegfelelési szabályzat létrehozása macOS-eszközökön a tűzfalbeállítások használatával <!-- 1497640 -->
Amikor új macOS-es megfelelőségi szabályzatot hoz létre (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: macOS** > **Rendszerbiztonság**), a **Tűzfal** új beállításai válnak elérhetővé: 

- **Tűzfal**: Konfigurálhatja a bejövő kapcsolatok kezelését a környezetében.
- **Bejövő kapcsolatok**: **Letilthatja** az összes bejövő kapcsolatot az olyan alapvető internetes szolgáltatások kivételével, mint a DHCP, a Bonjour vagy az IPSec. Ez a beállítás letiltja az összes megosztási szolgáltatást is.
- **Rejtett üzemmód**: a rejtett üzemmód **engedélyezésével** megakadályozhatja, hogy a számítógép válaszoljon a bejövő kérelmekre. Az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre.

A macOS 10.12 és újabb verziókra vonatkozik

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Új Wi-Fi eszközkonfigurációs profil Windows 10 vagy újabb rendszerhez <!-- 1879077 -->
Wi-Fi profilok jelenleg XML-fájlok használatával importálhatók és exportálhatók. A frissítésnek köszönhetően a Wi-Fi eszközkonfigurációs profilok már közvetlenül az Intune-ban is létrehozhatóak, ahogyan néhány más platform esetében is.

A profil létrehozásához nyissa meg az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Wi-Fi** elemet. 

A Windows 10 és újabb verziókra vonatkozik.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998-eeready---"></a>A Kioszkmód – elavult lehetőség nem használható és nem módosítható <!-- 2149998 eeready -->
A [Kioszkmód funkció](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10 vagy újabb** > **Eszközkorlátozások**) elavult. Helyét a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) veszi át. A frissítés után a **Kioszkmód – Elavult** funkció már nem lesz kiválasztható, és a felhasználói felület nem módosítható és nem frissíthető. 

A kioszkmód a [Kioszk beállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával engedélyezhető.

Windows 10 vagy újabb, és a Windows Holographic for Business rendszerekre vonatkozik

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>Az API-k külső hitelesítésszolgáltatókat használnak <!-- 2184013 -->
A frissítés tartalmaz egy Java API-t, amely engedélyezi a külső hitelesítésszolgáltatók számára az Intune- és az SCEP-integrációt. A felhasználók így hozzáadhatják egy profilhoz az SCEP-tanúsítványt, és alkalmazhatják az MDM-et használó eszközökre.

Az Intune jelenleg az [Active Directory tanúsítványszolgáltatást használó SCEP-kérelmeket](certificates-scep-configure.md) támogatja.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>A Munkamenet befejezése gomb megjelenítése ki- és bekapcsolható a kioszkmódú böngészőkben <!-- 2455253 -->
Mostantól konfigurálható, hogy a kioszkmódú böngészőkben megjelenjen-e a Munkamenet vége gomb. A vezérlő az **Eszközkonfiguráció** > **Kioszkmód (előzetes verzió)** >  **kioszkmódú webböngésző** alatt található. Bekapcsolása esetén, ha a felhasználó a gombra kattint, az alkalmazás megerősítést kér a munkamenet befejezéséhez. Megerősítés után a böngésző minden böngészési adatot töröl, és visszatér az alapértelmezett URL-címre.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM mobilkonfigurációs profil létrehozása <!-- 2564077 -->
Az **Eszközkonfiguráció** alatt létre lehet hozni egy eSIM mobilprofilt. Importálható lesz egy fájl, amely a mobilszolgáltató által megadott mobiltelefon-aktiválási kódokat tartalmazza. Ezek a profilok aztán alkalmazhatók lesznek az eSIM LTE-t engedélyező Windows 10 rendszerű eszközökön, amilyen a Surface Pro LTE és más eSIM-képes eszközök.

Ellenőrizze, hogy [eszközei támogatják-e az eSIM-profilokat](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

A Windows 10 és újabb verziókra vonatkozik. 




### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>A Samsung Knox Mobile Enrollment használatával regisztrált Androidos eszközök automatikus megjelölése „cégesként”. <!-- 2404851 -->
A Samsung Knox Mobile Enrollment használatával regisztrált Androidos eszközök alapértelmezés szerint **céges** megjelölést kapnak az **Eszköz tulajdonosa** alatt. Ezentúl nincs szükség a céges eszközök IMEI- vagy sorozatszám alapján történő manuális azonosítására a Knox Mobile Enrollment használatával végzett regisztráció előtt.

### <a name="device-management"></a>Eszközkezelés

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Eszközök tömeges törlése az Eszközök panelen <!-- 1793693 -->

Az Eszközök panelen mostantól egyszerre több eszközt is törölhet. Válassza az **Eszközök** > **Minden eszköz** lehetőséget >jelölje ki a törölni kívánt eszközöket > válassza a **Törlés** lehetőséget. A nem törölhető eszközök esetében riasztás fog megjelenni.

## <a name="week-of-july-16-2018"></a>2018. július 16-ai hét  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>További szinkronizálási lehetőségek a windowsos Céges portál alkalmazásban  
A Windowsos Céges portál alkalmazás mostantól lehetővé teszi, hogy a szinkronizálási folyamatot közvetlenül a Windows tálcájáról vagy a Start menüből is elindíthassa. Ez a funkció abban az esetben igazán hasznos, ha csak szinkronizálni szeretné eszközeit, hogy utána hozzáférhessen a vállalati erőforrásokhoz. Az új funkció eléréséhez jobb gombbal kattintson a Céges portál alkalmazás ikonjára a tálcán vagy a Start menüben. A megjelenő menüpontok közül (azaz a gyorslistában) válassza **Az eszköz szinkronizálása** lehetőséget. Megnyílik a Céges portál alkalmazás **Beállítások** lapja és megkezdődik a szinkronizálás. Az új funkciók megtekintéséhez lásd: [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md)   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Új böngészési élmény a windowsos céges portál alkalmazásban  

Ha a windowsos Céges portál alkalmazásban alkalmazásokat böngész vagy keres, mostantól válthat a meglévő **Csempék** nézet és az újonnan hozzáadott **Részletek** nézet között. Az új nézet az alkalmazások adatait jeleníti meg, például a nevet, a kiadót, a kiadás dátumát és a telepítés állapotát.  

Az **Alkalmazások** lapon található egy **Telepítve** nézet is, amely a befejezett és a folyamatban lévő telepítések adatait jeleníti meg. Az új nézet megtekintéséhez lásd: [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md)  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>A céges portál alkalmazás továbbfejlesztett felhasználói élménye készülékregisztráció-kezelők használatakor  
Ha egy készülékregisztráció-kezelő (DEM) bejelentkezik a windowsos céges portál alkalmazásba, az alkalmazás csak a készülékregisztráció-kezelő jelenlegi, éppen futó eszközét jeleníti meg. Ennek a fejlesztésnek köszönhetően kevesebb olyan időtúllépés fog történni, amely korábban akkor jelentkezett, ha az alkalmazás megpróbálta megjeleníteni a kezelő által regisztrált összes eszközt.  


## <a name="week-of-july-9-2018"></a>2018. július 9-ei hét

### <a name="app-management"></a>Alkalmazáskezelés

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Alkalmazás-hozzáférés letiltása a nem jóváhagyott eszközgyártókon és -modelleken <!-- 1425689 ! -->
Az Intune rendszergazdái egy adott Android-gyártókat és/vagy iOS-modelleket tartalmazó listát kényszeríthetnek az Intune App Protection-szabályzatokkal. A rendszergazda egy pontosvesszőkkel elválasztott listában adhat meg gyártókat az Android-szabályzatokhoz, valamint eszközmodelleket az iOS-szabályzatokhoz. Az Intune App Protection-szabályzatok csak Android- és iOS-eszközökre vonatkoznak. A megadott listán két különálló művelet hajtható végre:
- Az alkalmazás-hozzáférés letiltása a nem megadott eszközökön,
- vagy a vállalati adatok szelektív törlése a nem megadott eszközökön. 

A felhasználó nem férhet hozzá a célalkalmazáshoz, ha az nem felel meg a szabályzat feltételeinek. A rendszer a beállítások alapján letilthatja a felhasználót, vagy szelektíven törölheti annak vállalati adatait az alkalmazáson belül. IOS-eszközökön a funkcióhoz az alkalmazásoknak (például WXP, Outlook, Managed Browser, Yammer) integrálniuk kell az Intune App SDK-t, hogy a megcélzott alkalmazásokon kötelezővé lehessen tennie ezt a funkciót. Ez az integráció fokozatosan történik, és az egyes alkalmazáscsapatoktól függ. Android-eszközökön ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség. 

A végfelhasználói eszközökön az Intune-ügyfél az Application Protection-szabályzatok Intune-panelén megadott egyszerű sztringegyezések alapján végez műveleteket. Ez teljes mértékben az eszköz által jelentett értéktől függ. Ennek fényében a rendszergazának kell ügyelnie arra, hogy a kívánt viselkedés az elvártnak megfelelően működjön. Ezt úgy lehet elérni, ha teszteli a beállítást különböző eszközgyártókkal és -modellekkel egy kisebb felhasználói csoportban. A Microsoft Intune-ban válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget az alkalmazásvédelmi szabályzatok megtekintéséhez és hozzáadásához. Az alkalmazásvédelmi szabályzatokkal kapcsolatos további információért lásd: [Mik azok az alkalmazásvédelmi szabályzatok](app-protection-policy.md) és [Szelektív adattörlés alkalmazásvédelmi szabályzatok hozzáférési műveleteivel az Intune-ban](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Hozzáférés a macOS Céges portáljának kiadás előtti buildjéhez <!-- 1734766 -->
A Microsoft AutoUpdate-tel regisztrálhat, hogy korábban megkapja a buildeket, ha csatlakozik az Insider programhoz. A regisztráció lehetővé teszi a frissített Céges portál használatát, még mielőtt az elérhetővé válna a végfelhasználók számára. További információért lásd a [Microsoft Intune blogját](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## <a name="week-of-july-2-2018"></a>2018. július 2-ai hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Az iOS-alkalmazáskonfigurációk figyelése minden egyes eszközön <!-- 880037 -->
A Microsoft Intune rendszergazdájaként minden egyes felügyelt eszközön nyomon követheti az iOS-alkalmazáskonfiguráció állapotát. Az Azure Portal **Microsoft Intune** oldalán kattintson az **Eszközök** > **Minden eszköz** lehetőségre. A felügyelt eszközök listáján az egyik eszközre kattintva nyissa meg a hozzá tartozó panelt. Az eszköz paneljén kattintson az **Alkalmazáskonfiguráció** elemre.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Az alkalmazásvédelmi szabályzatok műveleteinek elérése <!-- 1483510 -->
Konfigurálhatja az alkalmazásvédelmi szabályzatokat, hogy azokkal törölje, letiltsa vagy figyelmeztesse a nem megfelelő eszközöket. A *törlés* művelettel eltávolítja a vállalati adatokat az eszközről. Törlés esetén az eszköz felhasználója értesítést kap a törlés okáról és a lehetséges szervizelési lépésekről. Egyes beállítások – például az operációs rendszer minimális verziója – esetén több műveletet is alkalmazhat, például letiltás és törlés. Ne feledje, hogy ezek a műveletek az alkalmazás indításakor aktiválódnak.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Céges alkalmazásadatok szelektív törlése <!-- 1507030 -->
A rendszergazdák új műveletként konfigurálhatják a céges adatok szelektív törlését, ha az alkalmazásvédelmi szabályzatok (APP) hozzáférési beállításai nem teljesülnek.  Ez a funkció lehetővé teszi a rendszergazdák számára, hogy a céges adatokat automatikusan védjék vagy távolítsák el az előre konfigurált feltételeken alapuló alkalmazásokról.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Mennyiségi vásárlási program keretében beszerzett iOS-alkalmazás visszavonása <!-- 1777384 -->
A Microsoft Intune rendszergazdájaként visszavonhatja a mennyiségi vásárlási program (Volume Purchase Program, VPP) keretében vásárolt kiválasztott iOS-es alkalmazás összes licencét. Értesítheti a felhasználókat, amikor megszűnik egy felhasználói licenccel rendelkező alkalmazás hozzájuk rendelése. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. A visszavont licencek száma látható lesz az Intune **Alkalmazások** tevékenységcsoportján belüli **Licencelt alkalmazások** csomóponton. Az iOS-es VPP-alkalmazásokkal kapcsolatos további információkat a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakörben tekintheti meg.

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>A Céges portál alkalmazás meg nem felelésről szóló üzeneteinek frissítései <!-- 1832222 -->
Felülvizsgáltuk az üzeneteket, amelyeket az eszközök felhasználói akkor kapnak, ha az eszköz nem megfelelő. Az üzenetek eredeti jelentése megmaradt, de barátságosabb hangnemben, kevesebb szakzsargonnal fogalmaztuk át őket. Frissítettük a dokumentációra és a megoldási lépésekre mutató hivatkozásokat is, hogy naprakészek legyenek.
Az alábbi szöveg eredeti és átdolgozott változata a megjelenő üzenetek javítását példázza:
- **Eredeti**: *Az eszköz nem lépett kapcsolatba az Intune szolgáltatással a rendszergazda által megkövetelt meghatározott időszakban. A probléma megoldásához nyissa meg a Céges portál alkalmazást az eszközön, és kattintson a Megfelelőség ellenőrzése gombra.*
- **Átdolgozott**: *Az Ön eszköze már jó ideje nem jelentkezett be a vállalatánál. A kapcsolat újbóli felvételéhez nyissa meg a Céges portál alkalmazást az eszközön, és koppintson a Beállítások ellenőrzése lehetőségre.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP-alkalmazáslicenc visszavonása <!-- 1863797 -->
Rendszergazdaként visszavonhatja egy eszköz vagy egy felhasználó hozzárendelt iOS VPP-alkalmazáslicencét. Az iOS VPP-alkalmazás eltávolítása az alkalmazás licencének visszavonását is lehetővé teszi. Az alkalmazás eltávolítása előtt a felhasználót vagy az eszközt ki kell vonni az alkalmazás céljaként megadott csoportból. A felhasználó vagy az eszköz csoportból való eltávolításával elkerülhető az alkalmazás újratelepítése. Ezeknek a lépéseknek a követése után az alkalmazáslicencet hozzárendelheti egy másik felhasználóhoz vagy eszközhöz. Az iOS VPP-alkalmazáslicencekre vonatkozó további információkat az [iOS mennyiségi programban vásárolt alkalmazások kezelése a Microsoft Intune-ban](vpp-apps-ios.md) című témakörben tekintheti meg.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Eszközkategóriák kiválasztása a „Hozzáférés munkahelyi vagy iskolai rendszerhez” beállításokkal <!-- 1058963 eenotready --> 
Ha engedélyezte az [eszközcsoport-leképezést](https://docs.microsoft.com/en-us/intune/device-group-mapping), a Windows 10-felhasználókat felkéri a rendszer egy eszközkategória választására, miután regisztráltak a **Gépház** > **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** területen elérhető **Csatlakozás** gombbal. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>sAMAccountName használata fiókhoz tartozó felhasználónévként az e-mail profilokhoz <!-- 1500307 -->
Fiókhoz tartozó felhasználónévként használhatja a helyszíni **sAMAccountName** nevet az Android-, iOS- és Windows 10 rendszerű e-mail-profilokhoz. Használhatja az Azure Active Directory (Azure AD) `domain` vagy `ntdomain` attribútumából is a tartományt. Vagy adjon meg egy egyéni statikus tartományt.

A funkció használatához szinkronizálnia kell a(z) `sAMAccountName` attribútumot a helyszíni Active Directory-környezetből az Azure AD-ra.

[Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 és későbbi verziókra](email-settings-windows-10.md) vonatkozik.

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ütköző eszközkonfigurációs profilok kiemelése <!-- 1556983 -->
Az **Eszközkonfiguráció** alatt megjelenik a meglévő profilok listája. Ez a frissítés ezt egy újabb oszloppal bővíti, amely az ütköző profilokról közöl részleteket. Egy ütközést jelző sor kiválasztásával megjeleníthető az ütközést okozó beállítás és profil. 

További tudnivalók a [konfigurációs profilok kezeléséről](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Új eszközmegfelelőségi eszközállapotok <!-- 2308882 -->
A következő új állapotok lettek hozzáadva az **Eszközmegfelelőség** > **Szabályzatok** > egy szabályzat kijelölése > **Áttekintés** alatt:
- Sikerült
- Hiba
- Ütközés
- Függőben
- Nem alkalmazható Egy olyan kép is megjelenik, amely mutatja a más platformon lévő eszközszámot. Például egy iOS-profil megtekintése esetén a profilhoz rendelt, nem iOS rendszerű eszközök száma is látható lesz az új csempén. Lásd: [Eszközmegfelelési szabályzatok](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Az eszközmegfelelőség támogatja a harmadik féltől származó vírusvédelmi megoldásokat <!-- 2325484 -->
Eszközmegfelelőségi szabályzat létrehozásakor (**Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** > **Platform: Windows 10 és későbbi verziók** > **Beállítások** > **Rendszerbiztonság**), új **[Eszközbiztonsági](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** beállítások láthatók: 
- **Vírusvédelem**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centerben regisztrált vírusvédelmi megoldások (például Symantec és Windows Defender) használatával ellenőrizheti a megfelelőséget. 
- **Kémprogram-elhárító**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centerben regisztrált kémprogram-elhárító megoldások (például Symantec és Windows Defender) használatával ellenőrizheti a megfelelőséget. 

A Windows 10 és újabb verziókra vonatkozik 

### <a name="device-enrollment"></a>Eszközök beléptetése

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Profil nélküli eszközök oszlop a regisztrációs programtokenek listájában <!-- 1853904 -->
A regisztrációs program tokenlistájában van egy olyan új oszlop, amelyben a hozzárendelt profil nélküli eszközök száma látható. Ez lehetővé teszi, hogy a rendszergazdák profilokat rendeljenek hozzá ezekhez az eszközökhöz, mielőtt a felhasználóknak kiosztanák őket. Az új oszlop megtekintéséhez válassza az **Eszközök beléptetése** > **Apple-regisztráció** > **Készülékregisztrációs programbeli token** lehetőséget.

### <a name="device-management"></a>Eszközkezelés

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>A Google névváltoztatásai az Android for Work és a Play for Work kifejezéseknél <!--842873 -->
Az Intune a Google egyes márkaneveit érintő változtatásaihoz igazodva frissítette az „Android for Work” terminológiáját. Az „Android for Work” és a „Play for Work” kifejezések használata megszűnt. A szövegkörnyezettől függően eltérő terminológiát használunk:
- Az „Android Enterprise” az általános, korszerű androidos felügyeleti környezetre vonatkozik.
- A „Munkahelyi profil” vagy a „Profil tulajdonosa” kifejezés a munkahelyi profilokkal felügyelt hozott eszközökre (BYOD) vonatkozik.
- A „Felügyelt Google Play” kifejezés a Google Áruházra vonatkozik.

#### <a name="rules-for-removing-devices----1609459---"></a>Szabályok eszközeltávolításhoz <!-- 1609459 -->
Új szabályok érhetők el, melyekkel automatikusan eltávolíthatja azokat az eszközöket, amelyek nem jelentkeztek be az Ön által megadott számú napon keresztül. Az új szabály megtekintéséhez nyissa meg az **Intune** panelt, és válassza az **Eszközök**, majd az **Eszközök adattörlési szabályai** lehetőséget.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Egyetlen célra használható céges funkció támogatása Android-eszközökhöz <!-- 1630973 -->

Az Intune támogatja a gondosan felügyelt, zárolt, kioszkstílusú Android-eszközöket. Ez lehetővé teszi a rendszergazdák számára, hogy egyetlen alkalmazásra vagy kis alkalmazáskészletre szűkítsék az eszközhasználatot, és megakadályozzák, hogy a felhasználók más alkalmazásokat engedélyezzenek vagy más műveleteket hajtsanak végre az eszközön. Az Android-kioszk beállításához lépjen az Intune > **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** területre. További információért lásd: [Vállalati androidos kioszkeszközök regisztrálásának beállítása](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Feltöltött ismétlődő céges eszközazonosítók soronkénti áttekintése <!-- 2203794-->
A céges azonosítók feltöltésekor az Intune az ismétlődések listázásával most lehetőséget ad a döntésre, hogy cseréli vagy megtartja a meglévő információt. Az ismétlődések esetén készülő jelentés akkor jelenik meg, ha az **Eszközregisztráció** > **Céges eszközazonosítók** > **Azonosítók hozzáadása** lehetőséget választja. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Céges eszközazonosítók manuális hozzáadása <!-- 2203803 -->
Már hozzáadhatja manuálisan a céges eszközök azonosítóit. Válassza az **Eszközregisztráció** > **Céges eszközazonosítók** > **Hozzáadás** lehetőséget. 

## <a name="week-of-june-25-2018"></a>2018. június 25-i hét

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – Új mobileszköz-védelmi partner <!-- 1169249 -->

A Microsoft Intune-nal integrálható, Pradeo nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

## <a name="week-of-june-18-2018"></a>2018. június 18-i hét

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Edge-mobiltámogatás az Intune alkalmazásvédelmi szabályzataihoz <!-- 1817882 -->

A Microsoft Edge mobilböngésző mostantól támogatja az Intune-ban meghatározott alkalmazásvédelmi szabályzatokat.

## <a name="week-of-june-11-2018"></a>2018. június 11-i hét

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>A FIPS-mód használata az NDES tanúsítvány-összekötővel <!-- 1333688 -->
Ha az NDES tanúsítvány-összekötőt olyan számítógépre telepítették, amelyen a Federal Information Processing Standard (FIPS) üzemmód engedélyezve volt, a tanúsítványok kiadása és visszavonása nem az elvárható módon működött. Ettől a frissítéstől kezdve az NDES tanúsítvány-összekötőhöz FIPS-támogatás is tartozik. 

A frissítés a következőket is tartalmazza:

- Az NDES tanúsítvány-összekötő megköveteli a .NET-keretrendszer 4.5-ös verzióját, amely automatikusan része a Windows Server 2016 és Windows Server 2012 R2 rendszereknek. Korábban a .NET 3.5 keretrendszer volt a minimálisan elvárt verzió.
- Az NDES tanúsítvány-összekötő tartalmazza a TLS 1.2 támogatását. Ha tehát a kiszolgáló, amelyen az NDES tanúsítvány-összekötő telepítve van, támogatja a TLS 1.2-t, akkor a TLS 1.2 lesz használva. Amennyiben a kiszolgáló nem támogatja a TLS 1.2 verziót, a TLS 1.1 lesz használva. Az eszközök és a kiszolgáló közötti hitelesítéshez jelenleg a TLS 1.1 van használatban.

További információ: [SCEP-tanúsítványok konfigurálása és használata](certificates-scep-configure.md) és [PKCS-tanúsítványok konfigurálása és használata](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>2018. június 4-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Az alkalmazás alkalmazásfelhasználói modellben használt azonosítójának (AUMID) lekérése a Microsoft Store Vállalatoknak alkalmazásaihoz kioszkmódban <!-- 1560077 ! -->
Az Intune mostantól lekérheti az alkalmazás alkalmazásfelhasználói modellben használt azonosítóját (AUMID) a Microsoft Store Vállalatoknak alkalmazásaihoz, így hatékonyabb kioszkprofil-konfigurációt nyújt.

További információ a Microsoft Store Vállalatoknak alkalmazásairól: [A Microsoft Store Vállalatoknak áruházban vásárolt alkalmazások felügyelete](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Új védjegyzési lap a Céges portálon <!-- 1916370 -->
A Céges portál védjegyzési lapja új elrendezést, szövegtartalmat és elemleírásokat kapott.


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Palo Alto Networks GlobalProtect VPN-profilok támogatása <!-- 1333680 eeready ! -->
Ez a frissítés lehetővé teszi a Palo Alto Networks GlobalProtect szolgáltatás választását a VPN-kapcsolat típusaként az Intune-beli VPN-profilokban (**Eszközök konfigurálása** > **Profilok** > **Profil létrehozása** > **Profil típusa** > **VPN**). Ebben a kiadásban az alábbi platformok támogatottak: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>További helyi eszközbiztonsági beállítások <!-- 1403702 -->
További helyi eszközbiztonsági beállításokat adhat meg a Windows 10 rendszerű eszközökhöz. Ezek a további beállítások a következő területeken érhetők el: Microsoft hálózati ügyfél, Microsoft hálózati kiszolgáló, hálózati hozzáférés és biztonság, valamint interaktív bejelentkezés. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioszkmód engedélyezése Windows 10-eszközökön <!-- 1560072 ! -->
Windows 10-eszközökön létrehozhat egy konfigurációs profilt, és engedélyezheti a kioszkmódot (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > **Windows 10** > **Eszközkorlátozások** > **Kioszkmód**). Ebben a frissítésben a **Kioszk (előnézet)** beállítást **Kioszk (elavult)** névre neveztük át. A **Kioszk (elavult)** beállítás használata már nem javasolt, de a júliusi frissítésig még működik. A **Kioszk (elavult)** beállítást az új **Kioszkmód** profiltípus helyettesíti (**Profil létrehozása** > **Windows 10** > **Kioszk (előnézet)**), amely a kioszkok Windows 10 RS4-es és újabb verziós konfigurációjához tartalmaz beállításokat.

A Windows 10 és újabb verziókra vonatkozik.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Visszatért az eszközprofil grafikus felhasználói diagramja <!-- 2160133 -->
Az eszközprofil grafikus felhasználói diagramján megjelenített számok javításakor (**Eszközkonfiguráció** > **Profilok** > Válasszon ki egy meglévő profilt > **Áttekintés**) ideiglenesen eltávolítottuk a grafikus felhasználói diagramot.

Ezzel a frissítéssel visszatér a grafikus felhasználói diagram, amely az Azure Portalon jelenik meg.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Windows Autopilot-alapú beléptetés támogatása felhasználóhitelesítés nélkül <!-- 1165118 wnready -->
Az Intune mostantól támogatja a Windows Autopilot-alapú beléptetést felhasználóhitelesítés nélkül. Ez egy új funkcionalitás, melyet a Windows Autopilot beléptetési profilban érhet el úgy, hogy az „Autopilot Deployment mode” (Autopilot telepítési módja) beállítást „Self-Deploying” (Öntelepítés) értékre állítja.  Az ilyen típusú regisztráció sikeres elvégzéséhez az eszközön a Windows 10 Insider Preview Build 17672 vagy újabb verziónak kell futnia, és rendelkeznie kell egy TPM 2.0 lapkával. Mivel nem igényel felhasználóhitelesítést, ennek a lehetőségnek a használata csak olyan eszközökhöz javasolt, amelyekhez fizikailag is hozzáfér.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766-eeready---"></a>Új nyelv/terület beállítás automata OOBE konfigurálásakor <!-- 1821766 eeready -->
A kezdőélmény automata profiljaiban egy új konfigurációs beállítás érhető el, amellyel megadható a profilok nyelve és régiója. Az új beállítás eléréséhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** > **Telepítési mód** = **Öntelepítés** > **Konfigurált alapértelmezések** lehetőséget.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Új beállítás az eszköz billentyűzetének konfigurálásához <!-- 1821768 -->
A kezdőélmény automata profiljaiban egy új beállítás lesz elérhető, amellyel konfigurálható a billentyűzet. Az új beállítás eléréséhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** > **Profil létrehozása** > **Telepítési mód** = **Öntelepítés** > **Konfigurált alapértelmezések** lehetőséget.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Az Autopilot-profilok csoportokat fognak megcélozni <!-- 1877935 -->
Az AutoPilot Deployment-profilok AutoPilot-eszközöket tartalmazó Azure AD-csoportokhoz rendelhetők hozzá.

### <a name="device-management"></a>Eszközkezelés

#### <a name="set-compliance-by-device-location----851881----"></a>Megfelelőség beállítása az eszköz helye alapján <!-- 851881 ! -->
Bizonyos esetekben érdemes a vállalati erőforrásokhoz való hozzáférést egy adott helyre korlátozni, amelyet hálózati kapcsolattal ad meg. Hozhat létre mostantól megfelelőségi szabályzatot (**Eszközmegfelelőség** > **Helyek**) az eszköz IP-címe alapján. Ha az eszköz az IP-címtartományon kívülre kerül, akkor nem férhet hozzá a vállalati erőforrásokhoz.

A következőkre vonatkozik: Android 6.0-s és újabb eszközök frissített Céges portál alkalmazással

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Fogyasztói alkalmazások és funkciók használatának meggátolása a Windows 10 Enterprise RS4 rendszerű Autopilot-eszközökön<!-- 1621980 -->
Le fogja tudni tiltani a fogyasztói alkalmazások és funkciók telepítését a Windows 10 Enterprise RS4 rendszerű AutoPilot-eszközökön. A szolgáltatás eléréséhez válassza az **Intune** > **Eszközök konfigurálása** > **Profilok** > **Profil létrehozása** > **Platform** = **Windows 10 vagy újabb** > **Profiltípus** = **Eszközkorlátozások** > **Konfigurálás** > **Windows Reflektorfény** > **Fogyasztói funkciók** lehetőséget. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948-eeready---"></a>A Windows 10 legújabb szoftverfrissítéseinek eltávolítása <!-- 1732948 eeready -->
Ha kritikus problémát tapasztal a Windows 10 rendszerű gépein, akkor választhatja az utolsó funkciófrissítés vagy az utolsó minőségi frissítés eltávolítását (vagyis a korábbi verzió visszaállítását). A funkciófrissítések és minőségi frissítések eltávolításának lehetősége csak ahhoz a karbantartási csatornához érhető el, amelyhez az eszköz tartozik. Az eltávolítás aktivál egy szabályzatot, mely visszaállítja az előző frissítést a Windows 10 rendszerű gépein. A funkciófrissítések esetében korlátozhatja 2–60 napra a legújabb verzió eltávolításának lehetőségét. A szoftverfrissítés-eltávolítási beállítások megadásához válassza a **Szoftverfrissítések** lehetőséget az Azure Portal **Microsoft Intune** paneljén. Ezután a **Szoftverfrissítések** panelen válassza a **Windows 10-es frissítési körök** lehetőséget. Itt végül választhatja az **Áttekintés** szakaszban lévő **Eltávolítás** lehetőséget.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>IMEI- és sorozatszám keresése minden eszközön <!-- 1793685 -->
Mostantól kereshet IMEI- és sorozatszámokra a Minden eszköz panelen (az e-mail-cím, UPN, eszköznév és felügyeleti név lehetősége továbbra is elérhető). Válassza az Intune-ban az **Eszközök** > **Minden eszköz** lehetőséget, és írja be a kívánt keresési feltételt a keresőmezőbe.

#### <a name="management-name-field-will-be-editable----1875989---"></a>A Felügyeleti név mező szerkeszthető lesz <!-- 1875989 -->
Szerkesztheti a Felügyeleti név mezőt az eszköz **Tulajdonságok** panelén. A mező szerkesztéséhez válassza az **Eszközök** > **Minden eszköz** > Válassza ki az eszközt > **Tulajdonságok** lehetőségét. A Felügyeleti név mezővel egyéni módon azonosíthat egy eszközt.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Új szűrő a Minden eszköz listában: Eszközkategória <!-- 1878520 -->
Mostantól szűrheti a **Minden eszköz** listát eszközkategória szerint. Ehhez válassza az **Eszközök** > **Minden eszköz** > **Szűrő** > **Eszközkategória** lehetőséget.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS- és macOS-eszközök képernyőjének megosztása a TeamViewerrel <!-- 1985547 -->
A rendszergazdák ezentúl a [TeamViewerhez](device-profile-android-teamviewer.md) csatlakozva képernyőmegosztást kezdeményezhetnek iOS- és macOS-eszközökkel. Az iPhone-, iPad- és macOS-felhasználók valós időben megoszthatják a képernyőjüket bármilyen más asztali vagy mobileszközzel. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Több Exchange Connector támogatása <!-- 2070451 -->
Mostantól nemcsak egy Microsoft Intune Exchange Connectort használhat bérlőnként. Az Intune most már több Exchange Connector használatát is támogatja, hogy több helyszíni Exchange-szervezetnél állíthassa be az Intune feltételes hozzáférést.

A helyszíni Intune Exchange Connector segítségével annak alapján kezelheti az eszközök helyszíni Exchange-postafiókokhoz történő hozzáférését, hogy az adott eszköz regisztrálva van-e az Intune-ban, és megfelel-e az Intune eszközmegfelelőségi szabályzatainak. Az összekötő beállításához töltse le a helyszíni Intune Exchange Connectort az Azure Portalról, és telepítse egy Exchange-szervezeten belüli kiszolgálón. A Microsoft Intune irányítópultján válassza a **Helyszíni hozzáférés** lehetőséget, majd a **Telepítés** területen kattintson az **Exchange ActiveSync Connector** lehetőségre. Töltse le a helyszíni Exchange Connectort, és telepítse egy Exchange-szervezeten belüli kiszolgálón. Most, hogy már nem csupán egy Exchange Connectort használhat bérlőnként, ugyanezekkel a lépésekkel letöltheti és telepítheti az összekötőt minden további Exchange-szervezethez, ha vannak ilyenek.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Új eszközhardver-információ: CCID <!-- 2156657 -->
A Chip Card Interface Device (CCID) azonosító mostantól elérhető minden eszközhöz. A megtekintéséhez válassza az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Hardver** lehetőséget, és ellenőrizze a **Hálózati adatok** szakaszt.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Minden felhasználó és eszköz hozzárendelése hatókörcsoportokként <!-- 2196803 -->
Minden felhasználót, eszközt és a hatókörcsoportok felhasználóit és eszközeit hozzárendelheti. Ehhez válassza az **Intune-szerepkörök** > **Összes szerepkör** > **Szabályzat- és profilkezelő** > **Hozzárendelések** > kívánt hozzárendelés > **Hatókör (csoportok)** lehetőséget.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>Mostantól elérhető az UDID azonosító iOS- és macOS-eszközökhöz <!-- 2219806 wnready-->
Az iOS- és macOS-eszközök UDID (Unique Device Identifier) azonosítójának megtekintéséhez válassza az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Hardver** lehetőséget. Az UDID csak vállalati eszközökhöz érhető el (ezt az **Eszközök** > **Minden eszköz** > kívánt eszköz > **Tulajdonságok** > **Eszköz tulajdonjoga** lehetőséget választva állíthatja be).

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Továbbfejlesztett hibaelhárítás az alkalmazástelepítéshez <!-- 928990 -->
A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. Bevezetjük az alkalmazás-hibaelhárítási funkcióink nyilvános előzetes verzióját. Ennek keretében megjelenik egy új, **Kezelt alkalmazások** nevű csomópont minden egyedülálló eszköz alatt. Ez a Intune MDM-en keresztül szolgáltatott alkalmazások listáját tartalmazza. A csomóponton belül az alkalmazástelepítési állapotokat tekintheti meg. Ha kijelöl egy önálló alkalmazást, megnyithatja annak hibaelhárítási nézetét. A hibaelhárítási nézetben megtekintheti az alkalmazás végpontok közötti életciklusát, például a létrehozási, a módosítási, a célzási dátumot, valamint az alkalmazás egy eszközre való továbbításának dátumát. Továbbá ha az alkalmazás telepítése sikertelen volt, megjelenik egy hibakód, és egy hasznos üzenet a hiba okáról. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Intune-beli alkalmazásvédelmi szabályzatok és Microsoft Edge <!-- 1818968 -->
A Microsoft Edge mobilböngésző (iOS és Android) mostantól támogatja a Microsoft Intune alkalmazásvédelmi szabályzatait. Az Intune azokat a felhasználókat is védeni fogja, akik iOS- és Android-eszközön jelentkeznek be Azure AD-fiókjukkal az Edge alkalmazásba. iOS-eszközökön a **Require managed browser for web content** (Felügyelt böngésző megkövetelése a webes tartalmakhoz) szabályzat engedélyezi a felhasználóknak a hivatkozások felügyelt Edge-ben való megnyitását.

## <a name="week-of-may-14-2018"></a>2018. május 14-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítésének megkövetelése <!-- 1553555 -->

A rendszergazdák blokkolhatják a végfelhasználók számára a Windows 10 RS4 rendszer asztalának elérését, amíg az Intune el nem végzi a szabályzatok, alkalmazások, tanúsítványok és hálózati profilok telepítését az AutoPilot-eszközök beállításakor. További információért lásd: [Regisztrációs állapotlap beállítása](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Alkalmazásvédelmi szabályzatok konfigurálása <!-- 2144597 Part 2 -->

Az Azure Portalon, ahelyett hogy az Intune App Protection szolgáltatáspanelre lépne, mostantól elegendő egyszerűen az Intune-t megnyitnia. Most már az Intune egyetlen helyén érhetők csak el az alkalmazásvédelmi szabályzatok. Az összes alkalmazásvédelmi szabályzatát megtalálhatja az Intune **Mobilalkalmazás** paneljén, az **Alkalmazásvédelmi szabályzatok** területen. Ez az integráció leegyszerűsíti a felhőbeli szolgáltatások adminisztrációját. Ne feledje, hogy minden alkalmazásvédelmi szabályzat elérhető már az Intune-ban, és a korábban konfigurált összes szabályzatot módosíthatja. Az Intune App Policy Protection- (APP) és Conditional Access- (CA) szabályzatok mostantól a **Feltételes hozzáférés** területen érhetők el, mely a **Microsoft Intune** panel **Kezelés** szakaszában vagy az **Azure Active Directory** panel **Biztonság** szakaszában található meg. További információ a feltételes hozzáférési szabályzatokról: [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). További információ: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>2018. május 7-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Samsung Knox Mobile Enrollment-támogatás <!--1112863-->

A Intune a Samsung Knox Mobile Enrollmenttel (KME-vel) való használatával nagy mennyiségű céges tulajdonú Android-eszközt regisztrálhat. A Wi-Fi- és mobilhálózatok felhasználói az eszköz első bekapcsolása után csupán néhány érintéssel regisztrálhatnak. A Knox Deployment App használatával az eszközök Bluetooth vagy NFC segítségével regisztrálhatók. További információ: [Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Segítségkérés a Windows 10-es Céges portálban <!-- 1874137 -->

A Windows 10 Céges portál mostantól alkalmazáshasználati naplókat küld közvetlenül a Microsoftnak, ha egy felhasználó segítséget kér egy problémához. Így könnyebben háríthatók el és oldhatók meg a Microsoftnak továbbított problémák.

## <a name="week-of-april-23-2018"></a>2018. április 23-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>PIN-jelszó támogatása MAM PIN-ként Androidon<!-- 1438086 -->

Az Intune-rendszergazdák alkalmazásindítási követelményként állíthatnak be PIN-jelszót a numerikus MAM PIN-kód helyett. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune a PIN-jelszót a hagyományos, numerikus PIN-kódhoz hasonlóan támogatja: állíthat be minimális jelszóhosszt, és engedélyezheti a karakterek és sorozatok ismétlődését a felügyeleti konzolon. Ennek a funkciónak a használatához a Céges portál legújabb verziójára van szükség Android rendszerben. Ez a funkció már elérhető az iOS rendszerben.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1473977 -->
A Microsoft Intune támogatni fogja a macOS-hoz készült LOB-alkalmazások telepítését az Azure Portalról. Ezzel a funkcióval hozzáadhat egy macOS-hoz készült LOB-alkalmazást az Intune-hoz, miután azt előkészítette egy, a GitHubon elérhető eszközzel. Válassza az Azure Portalon az **Intune** panel **Mobilalkalmazások** elemét. A **Mobilalkalmazások** panelen válassza az **Alkalmazások** > **Hozzáadás** elemet. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Beépített Minden felhasználó és Minden eszköz csoport Android for Work- (AFW) alkalmazástársításokhoz <!-- 1813073 -->
Kihasználhatja a beépített **Minden felhasználó** és **Minden eszköz** csoportot az AFW-alapú alkalmazástársításokhoz. További információ: [Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Az Intune újratelepíti a felhasználók által eltávolított kötelező alkalmazásokat <!-- 1947010 -->
Ha egy végfelhasználó eltávolít egy kötelező alkalmazást, az Intune a 7 napos újraértékelési ciklus kivárása helyett 24 órán belül automatikusan újratelepíti az alkalmazást.

### <a name="device-configuration"></a>Eszközök konfigurálása

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Csoport minden eszközének megjelenítése az eszközprofil-diagramon és -állapotlistán <!-- 1449153 eeready -->
Eszközprofil konfigurálásakor (**Eszközök konfigurálása** > **Profilok**) kiválasztja az eszközprofilt, például iOS. Ezután hozzárendeli ezt a profilt egy csoporthoz, mely tartalmaz iOS- és nem iOS-eszközöket is. A grafikus diagramon lévő számlálón az látható, hogy a profil alkalmazva lett az iOS- *és* a nem iOS-eszközökre is (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**). Amikor a grafikus diagramot választva megjeleníti az **Áttekintés** lapot, az **Eszközállapot** terület felsorolja a csoport összes eszközét, nemcsak az iOS-eszközöket. 

A jelen frissítés megjelenése után a grafikus diagram (**Eszközök konfigurálása** > **Profilok** > meglévő profil > **Áttekintés**) csak az adott eszközprofil számlálóját jeleníti meg. Ha például az eszközprofil iOS-eszközökre van alkalmazva, akkor a diagram csak az iOS-eszközök számát jeleníti meg. A grafikus diagram választása és az **Eszközállapot** lista megnyitása esetén is csak az iOS-eszközök lesznek felsorolva.

A jelen frissítés elkészültéig a grafikus felhasználói diagramot ideiglenesen eltávolítottuk. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Mindig bekapcsolva VPN Windows 10-hez <!--1333666 -->

Jelenleg a [Minden bekapcsolva](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) trigger a Windows 10-eszközökön csak OMA-URI-val létrehozott egyéni VPN-profil segítségével használható.

A frissítés révén a rendszergazdák engedélyezhetik a Mindig bekapcsolva beállítást a Windows 10 VPN-profilokban közvetlenül az Azure Portalon elérhető Intune konzolról. A Mindig bekapcsolva beállítású VPN-profilok automatikusan csatlakoznak az alábbi esetekben:

- Felhasználói bejelentkezés az eszközre
- Hálózatváltozás az eszközön
- Az eszköz képernyője ismét bekapcsol, miután ki volt kapcsolva

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Új nyomtatóbeállítások az oktatási profilokban <!-- 1308900 -->

Az oktatási profilok új beállításai a **Nyomtatók** kategória **Nyomtatók**, **Alapértelmezett nyomtató**, **Új nyomtatók hozzáadása** területén érhetők el.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Hívóazonosító megjelenítése a személyes profilban – Android for Work <!--1098984 -->
Előfordulhat, hogy az eszközön személyes profilt használó végfelhasználók nem látják egy munkahelyi kapcsolat hívásazonosítójának részleteit. 

Ez a frissítés egy új beállítást jelenít meg az **Android for Work** > **Eszközkorlátozások** > **Munkahelyi profil beállításai** területen:
- Munkahelyi kapcsolat hívásazonosítójának megjelenítése a személyes profilban

Engedélyezése (konfigurálás nélkül) esetén a munkahelyi hívó részletei megjelennek a személyes profilban. Tiltása esetén a munkahelyi hívó részletei nem jelennek meg a személyes profilban. 

A következőkre vonatkozik: Android munkahelyi profilos eszközök Android v6.0 és újabb operációs rendszerekkel

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Új Windows Defender Credential Guard-beállítások az Endpoint Protection-beállításokban <!--1102252 --><!--from 1802 and 1804-->

Ezzel a frissítéssel a [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Eszközkonfiguráció** > **Profilok** > **Endpoint protection**) az alábbi beállításokkal bővült: 

- **Windows Defender Credential Guard**: Bekapcsolja a Credential Guardot virtualizálás-alapú biztonsággal. Ennek a funkciónak a bekapcsolása segít megvédeni a hitelesítő adatokat a következő újraindításkor, ha a **Platformbiztonsági szint a Biztonságos rendszerindítással** és a **Virtualizálás-alapú biztonság** egyaránt be van kapcsolva. A lehetőségek a következők:
  - **Letiltva**: Ha a Credential Guard előzőleg be volt kapcsolva az **Engedélyezve zárolással** lehetőséggel, akkor ez távolról kikapcsolja a Credential Guardot.

  - **Engedélyezve UEFI-zárolással**: Ezzel a beállítással biztosíthatja, hogy a Credential Guard ne lehessen letiltható egy beállításkulccsal vagy egy csoportházirenddel. Ha ennek a beállításnak a használata után le szeretné tiltani a Credential Guardot, akkor a Csoportházirendet „Letiltva” állapotra kell állítania. Ezt követően távolítsa el a biztonsági funkciót mindegyik számítógépen egy fizikailag jelen lévő felhasználóval. Ezekkel a lépésekkel törölhető az UEFI-ban megőrzött konfiguráció. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

  - **Engedélyezve zárolás nélkül**: Távolról letilthatja a Credential Guardot egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, legalább a Windows 10 1511-es verziójának kell futnia.

Az alábbi függő technológiák automatikusan engedélyezve lesznek a Credential Guard konfigurálásakor: 

  - **Virtualizálás-alapú biztonság (VBS) engedélyezése**: Bekapcsolja a virtualizálás-alapú biztonságot (VBS-t) a következő újraindításkor. A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz, és Biztonságos rendszerindítás szükséges hozzá.
  - **Biztonságos rendszerindítás közvetlen memóriaeléréssel (DMA-val)**: Bekapcsolja a VBS-t a biztonságos rendszerindítás és a közvetlen memóriaelérés funkcióival. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Egyéni tulajdonosnév használata SCEP-tanúsítványokban <!-- 2064190 -->
Használhatja az **OnPremisesSamAccountName** köznapi nevet egyéni tulajdonosként az SCEP-tanúsítványprofilokban. Így használhatja például a következőt: `CN={OnPremisesSamAccountName})`.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Kamera és képernyőkép rögzítésének blokkolása Android for Work rendszerben <!-- 1098977 eeready-->
Két új tulajdonság érhető el letiltásra, amikor az Android-eszközökhöz eszközkorlátozásokat állít be: 
- Kamera: Letiltja a hozzáférést az eszközön lévő összes kamerához
- Képernyőfelvétel: Letiltja a képernyőfelvételt, és megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön

Android for Work rendszerre érvényes.


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Új regisztrációs lépések a macOS High Sierra 10.13.2 és újabb rendszert futtató eszközök felhasználóinak <!--1734567 -->
A macOS High Sierra 10.13.2 rendszer bevezette a „felhasználó által jóváhagyott” mobileszköz-kezelési regisztrációt. A jóváhagyott regisztrációk lehetővé teszik az Intune-nak bizonyos biztonsági szempontból kényes beállítások kezelését. További információt az Apple támogatási dokumentumában találhat itt: https://support.apple.com/HT208019.

A macOS rendszerhez készült Céges portál alkalmazással regisztrált eszközök „felhasználó által nem jóváhagyott” állapotúként vannak minősítve, hacsak a felhasználó manuálisan jóváhagyást nem ad a Rendszerbeállítások menü megnyitásával. Emiatt a macOS rendszerhez készült Céges portál alkalmazás mostantól a regisztrációs folyamat végén átirányítja a macOS 10.13.2 és újabb rendszerek felhasználóit a regisztrációjuk manuális jóváhagyásához. Az Intune felügyeleti konzolja jelenti, ha egy regisztrált eszközt jóváhagyott a felhasználó.



### <a name="device-management"></a>Eszközkezelés

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>A veszélyforrások elleni fejlett védelem (ATP) és az Intune teljesen integrálva van <!-- EEready 1629303 -->

A [Komplex veszélyforrások elleni védelem](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) megállapítja a Windows 10 rendszerű eszközök kockázati szintjét. A Windows Defender biztonsági központban (ATP portál) kapcsolatot hozhat létre a Microsoft Intune-nal. Ennek létrehozása után egy Intune-megfelelőségi szabályzat alapján meg lesz határozva az elfogadható fenyegetettségi szint. Így a fenyegetettségi szint túllépése esetén egy Azure Active Directory-beli megfelelőségi szabályzat a vállalaton belül letilthatja néhány alkalmazás elérését.

Ez a funkció teszi lehetővé az ATP számára a fájlok vizsgálatát, a fenyegetések észlelését, és a Windows 10 rendszerű eszközöket érintő kockázatok jelentését.

Lásd: [Az ATP engedélyezése feltételes hozzáféréssel az Intune-ban](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Felhasználó nélküli eszközök támogatása <!-- 1637553 -->
Az Intune támogatja a megfelelőség kiértékelését a felhasználó nélküli eszközökön is, ideértve például a Microsoft Surface Hub eszközt. A megfelelőségi szabályzat alkalmazható közvetlenül eszközökre. Ezért a megfelelőség (vagy meg nem felelőség) megállapítható a társított felhasználó nélküli eszközök esetében is.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-eszközök törlése <!-- 1713650 -->
Az Intune-rendszergazdák [törölhetik az Autopilot-eszközöket](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Továbbfejlesztett eszköztörlési funkció <!--1832333 -->
Mostantól nem kell eltávolítania a céges adatokat vagy visszaállítania a gyári beállításokat, mielőtt [törölhetne egy eszközt az Intune-ból](devices-wipe.md#delete-devices-from-the-intune-portal).

Az új törlési funkció eléréséhez jelentkezzen be az Intune-ba, és válassza az **Eszközök** > **Minden eszköz** > eszköz neve > **Törlés** lehetőséget.

Ha továbbra is szeretné alaphelyzetbe állítani vagy kivonni az eszközöket, használhatja a megszokott **Céges adatok eltávolítása** és **Gyári beállítások visszaállítása** lehetőséget, mielőtt a **Törlés** lehetőséget választaná. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Hang lejátszása iOS rendszeren Elveszett üzemmódban <!-- 1947769 -->
Amikor egy felügyelt iOS-eszköz a mobileszköz-kezelés (MDM) [Elveszett üzemmódjában](device-lost-mode.md) van, [lejátszhat egy hangot](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Eszközök** > **Minden eszköz** > válasszon iOS-eszközt > **Áttekintés** > **Egyebek**). A hang lejátszása egészen addig folytatódik, amíg az eszköz ki nem lép az Elveszett üzemmódból, vagy a felhasználó le nem tiltja a hangot az eszközön. iOS 9.3-as és újabb rendszerű eszközökre érvényes.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Keresések webes találatainak letiltása vagy engedélyezése Intune-eszközön <!--1972804-->

A rendszergazdák mostantól letilthatják az eszközön a keresések webes eredményeit.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Javított hibaüzenet az Apple MDM Push-tanúsítvány feltöltési hibájához <!-- 2172331 -->

A hibaüzenet elmagyarázza, hogy ugyanazt az Apple ID-t kell használni egy meglévő MDM-tanúsítvány megújításakor.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>A macOS-hez készült Céges portál tesztelése virtuális gépeken <!-- 2216679 -->

Közzétettünk egy útmutatót IT-rendszergazdák számára, amelyben segítséget kapnak ahhoz, hogy a macOS-hez készült Céges portál alkalmazást teszteljék virtuális gépeken a Parallels Desktopban és a VMware Fusionben. További információt a [Virtuális macOS-gépek regisztrálása teszteléshez](macos-enroll.md#enroll-virtual-macos-machines-for-testing) című témakörben talál.


### <a name="user-interface"></a>Felhasználói felület

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Továbbfejlesztett eszközcsempék a Windows 10-es Céges portálban <!--2213364 -->

Frissítettük a csempéket, így most már jobban hozzáférhetőek a gyengén látó felhasználók számára is, és jobb teljesítményt nyújtanak a képernyőolvasó eszközök használatakor.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnosztikai jelentések küldése a macOS rendszerhez készült Céges portál alkalmazásban <!-- 2216677 -->
Frissült a macOS-eszközökhöz készült Céges portál alkalmazás, így jobb lehetőségeket nyújt a felhasználóknak az Intune-nal kapcsolatos hibák jelentésére. A dolgozói a Céges portál alkalmazásból a következőket tehetik meg:

- Diagnosztikai jelentések feltöltése közvetlenül a Microsoft fejlesztői csapatának.
- Incidensazonosító elküldése e-mailben a vállalata informatikai támogatási csoportjának.

További információt a [Néhány hiba macOS esetén](/intune-user-help/send-errors-macos) című témakörben talál.

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Az Intune támogatja a Fluent Design System használatát a Windows 10-hez készült Céges portál alkalmazásban <!-- 1195010 WNready -->
A Windows 10-es Intune Céges portál alkalmazást frissítettük a [Fluent Design System navigációs nézetével](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Az alkalmazás oldalán egy statikus, függőleges lista jelenik meg a legfelső szintű oldalakkal. A gyors megtekintéshez és az oldalak közötti váltáshoz kattintson bármelyik hivatkozásra. Egy frissítéssorozattal adaptív, kényelmesebb és ismerősebb Intune-élményt szeretnénk létrehozni. Ez a sorozat első frissítése. A frissített megjelenés megtekintésez lépjen [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) területre.

## <a name="week-of-april-16-2018"></a>2018. április 16-i hét

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Cisco AnyConnect ügyfél használata iOS-hez <!-- EEready 1333708 -->

Új VPN-profil iOS-hez történő létrehozásakor mostantól két lehetőség közül lehet választani: **Cisco AnyConnect** és **Cisco Legacy AnyConnect**. A Cisco AnyConnect-profilok a 4.0.7x és újabb verziókat támogatják. Meglévő iOS Cisco AnyConnect VPN-profiljai a **Cisco Legacy AnyConnect** nevet kapják, és továbbra is úgy működnek a Cisco AnyConnect 4.0.5x és régebbi verzióival, mint eddig.

> [!NOTE]
> Ez a módosítás csak az iOS-re vonatkozik. Az Android, az Android for Work és a macOS platformokhoz továbbra is csak egy Cisco AnyConnect-lehetőség érhető el.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>A Jamf-ban regisztrált macOS-eszközök már regisztrálhatnak az Intune-nal <!-- 2370684 -->

A macOS-es Céges portál 1.3 és 1.4 verziója nem regisztrálta sikeresen a Jamf-eszközöket az Intune-nal. A macOS portál 1.4.2 verziója kijavítja ezt a hibát.


## <a name="week-of-april-9-2018"></a>2018. április 9-i hét  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Frissített ügyféltámogatási élmény az Androidhoz készült Céges portál alkalmazásban <!-- 1631531 -->

Az Android platform ajánlott eljárásaihoz igazodva frissítettük az Androidhoz készült Céges portál alkalmazás Súgó funkcióját. Mostantól ha a felhasználók problémát észlelnek az alkalmazásban, a **Menü** > **Súgó** lehetőségre koppintva az alábbi tevékenységeket végezhetik:
- Diagnosztikai naplókat küldhetnek a Microsoftnak.
- Egy eseményazonosítót és a hibát ismertető e-mailt írhatnak a céges ügyfélszolgálatnak.  

A frissített ügyféltámogatást a [Naplók elküldése e-mailben](/intune-user-help/send-logs-to-your-it-admin-by-email-android) és a [Hibák elküldése a Microsoftnak](/intune-user-help/send-logs-to-microsoft-android) területen érheti el.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Új regisztrációs hibákat ábrázoló trenddiagram és hibaokokat tartalmazó táblázat <!-- 1471783 -->

A Regisztráció áttekintése lapon megtekintheti a regisztrációs hibák trendjét és az öt leggyakoribb hibaokot. A diagramra vagy a táblázatra kattintva hozzáférhet a részletesebb adatokhoz, valamint hibaelhárítási tanácsokat és szervizelési javaslatokat is találhat.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Az alkalmazásvédelmi szabályzatok konfigurálási helyének frissítése <!-- 2144597 -->

A Microsoft Intune-beli Azure Portalon ideiglenesen átirányítás lesz érvényben az **Intune App Protection** szolgáltatás paneljéről a **Mobilalkalmazás** panelre. Fontos megjegyezni, hogy már minden alkalmazásvédelmi szabályzat megtalálható az Intune **Mobilalkalmazás** paneljén, az alkalmazáskonfigurációban. Az Intune App Protection szolgáltatás megnyitása helyett csak az Intune-t kell majd megnyitnia. 2018. áprilisban megszüntetjük az átirányítást, és teljes mértékben eltávolítjuk az **Intune App Protection** szolgáltatás paneljét, így az Intune alkalmazásvédelmi szabályzatait ezentúl egyetlen helyen tekintheti meg. 

**Hogyan érint ez engem?**
Ez a változás a különálló Intune-t használó ügyfeleket és a hibrid (az Intune-t a Configuration Managerrel használó) ügyfeleket egyaránt érinti. Az integráció leegyszerűsíti a felhőfelügyelet adminisztrációját.

**Hogyan készüljek fel a változásra?**
Az **Intune App Protection** szolgáltatás panelje helyett az **Intune-t** jelölje meg kedvencként, és mindenképpen ismerkedjen meg az alkalmazásvédelmi szabályzatok munkafolyamatával az Intune **Mobilalkalmazás** paneljén. Egy rövid ideig átirányítás lesz érvényben, majd az **App Protection** panel el lesz távolítva. Ne feledje, hogy már minden alkalmazásvédelmi szabályzat elérhető az Intune-ban, és bármely feltételes hozzáférési szabályzatot módosíthatja. További információ a feltételes hozzáférési szabályzatokról: [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). További információ: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>2018. április 2-i hét

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Felhasználóiélmény-frissítés az iOS-hez készült Céges portál alkalmazásban <!--1412866 -->
Nagyszabású felhasználóiélmény-frissítést adtunk ki az iOS-es Céges portál alkalmazáshoz. A frissítéshez teljes vizuális átalakulás is tartozik, amely modernebb megjelenést és élményt biztosít. Az alkalmazás működését változatlanul hagytuk, használhatóságát és kezelhetőségét azonban fejlesztettük.  

Amit még tapasztalni fog:
- IPhone X támogatása.
- Gyorsabb alkalmazásindítás és betöltés, amellyel a felhasználók időt takarítanak meg.
- A felhasználóknak a legfrissebb állapotinformációkat nyújtó újabb folyamatjelző sávok.
- A felhasználói naplófeltöltés módjának fejlesztése, hogy a hibákat egyszerűbb legyen bejelenteni.  

A frissített megjelenés megtekintésez lépjen [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) területre.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Helyszíni Exchange-adatok védelme az Intune APP és a feltételes hozzáférés segítségével <!-- 1056954 -->
Mostantól a helyszíni Exchange-adatokhoz való Outlook Mobile-hozzáférést az Intune App Policy Protection (APP) és a feltételes hozzáférés segítségével védheti. Alkalmazásvédelmi szabályzat hozzáadásához vagy módosításához az Azure Portalon válassza a **Microsoft Intune** > **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget. A funkció használata előtt győződjön meg arról, hogy megfelel az [iOS-es és Androidos Outlook követelményeinek](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>2018. március 26-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Lejáró üzletági (LOB) iOS-alkalmazások figyelmeztetései a Microsoft Intune-ban <!-- 748789 -->

Az Intune az Azure Portalon keresztül értesítést küld a hamarosan lejáró üzletági iOS-alkalmazásokról. Az üzletági iOS-alkalmazás új verziójának letöltésekor az Intune eltávolítja a lejárati értesítést az alkalmazáslistáról. A lejárati értesítés csak az újonnan feltöltött üzletági iOS-alkalmazások esetében lesz aktív. Az üzletági iOS-alkalmazások kiépítési profiljának lejárata előtt 30 nappal egy figyelmeztetés jelenik meg. A lejárat után a figyelmeztetés Lejárt állapotúra módosul.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>A Céges portál témáinak testreszabása hexadecimális kódokkal <!--1049561 -->

Hexadecimális kódokkal testreszabhatja a témák színeit a Céges portál alkalmazásaiban. A hexadecimális kód megadásakor az Intune meghatározza a szövegszín és a háttérszín közötti legnagyobb kontrasztot eredményező szövegszínt. A szöveg színéről és a céges emblémáról is megtekinthet egy-egy előnézeti képet a **Mobilalkalmazások** > **Céges portál** területen.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Alkalmazástársítás belefoglalása vagy kizárása Android Enterprise-csoportok alapján <!-- 1813081 -->

Az Android Enterprise (korábbi nevén Android for Work) a befoglaló és kizáró csoportokat támogatja, de az előre létrehozott **Minden felhasználó** és **Minden eszköz** beépített csoportokat nem. További információ: [Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Eszközkezelés

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Új biztonsági fejlesztések az Intune szolgáltatásban  <!-- 1637539 -->   

Az Azure-beli Intune-on egy új váltógombot vezettünk be, amellyel az Intune különálló verziójának ügyfelei a szabályzattal nem rendelkező eszközöket **Megfelelőként** (kikapcsolt biztonsági funkció) vagy **Nem megfelelőként** (bekapcsolt biztonsági funkció) kezelhetik. Így meggyőződhetnek arról, hogy az erőforrások csak az eszközmegfelelőség értékelése után válnak elérhetővé.

Ez a funkció attól függően érinti Önt, hogy már hozzárendelt-e megfelelőségi szabályzatokat.

- Ha Ön új vagy meglévő fiókot használ, és az eszközeihez nincsenek hozzárendelve megfelelőségi szabályzatok, a váltógomb automatikusan a **Megfelelő** értékre lesz beállítva. A funkció a konzolon alapértelmezés szerint ki van kapcsolva. Ez nincs hatással a végfelhasználókra.
- Ha Ön új vagy meglévő fiókot használ, és vannak olyan eszközei, melyekhez van hozzárendelve megfelelőségi szabályzat, a váltógomb automatikusan a **Nem megfelelő** értékre lesz beállítva. A funkció alapértelmezés szerint be van kapcsolva a márciusi frissítés bevezetésekor.

Ha feltételes hozzáféréssel (CA) használ megfelelőségi szabályzatokat, és a funkció be van kapcsolva, a CA innentől fogva letilt minden olyan eszközt, amelyhez nincs hozzárendelve legalább egy megfelelőségi szabályzat. Az ezen eszközökhöz társított végfelhasználók, akik korábban hozzáférhettek a levelezéshez, elveszítik a hozzáférésüket, hacsak nem rendel hozzá legalább egy megfelelőségi szabályzatot minden eszközhöz.   

Megjegyzés: Bár a váltógomb alapértelmezett állapota megjelenik a felhasználói felületen az Intune szolgáltatás márciusi frissítése után, az állapot nincs azonnal kényszerítve. A váltógombon elvégzett módosítások nem lesznek hatással az eszközmegfelelőségre mindaddig, amíg nem ellenőrizzük a fiók működő váltógombját. A fiókja tesztelésének befejezéséről az Üzenetközpontban értesítjük. Ez a márciusi Intune-frissítések után néhány napot is igénybe vehet.

**További információ**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Függetlenítés (jailbreakelés) bővített észlelése <!-- 846515 -->

A függetlenítés (jailbreakelés) bővített észlelése egy új megfelelőségi beállítás, amelynek segítségével az Intune hatékonyabban értékelheti a feltört eszközöket. A beállítás révén az eszköznek gyakrabban, a helyalapú szolgáltatások és az akkumulátor fokozott használatával kell bejelentkeznie az Intune-ba.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Jelszavak visszaállítása Android O-eszközökön <!-- 1238299 -->
A munkahelyi profillal rendelkező, regisztrált Android 8.0-eszközökön visszaállíthatja a jelszavakat. Amikor egy „Jelszó visszaállítása” kérelmet küld egy Android 8.0-eszköznek, az egy új eszközfeloldó jelszót vagy egy kezelt profilra vonatkozó kérdést állít be az aktuális felhasználónak. A jelszó vagy a kérdés a küldés után azonnal életbe lép.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Megfelelőségi szabályzatok alkalmazása eszközcsoportokban lévő eszközökre <!--1307012 -->

A megfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználókra alkalmazhatja. Ezzel a frissítéssel a megfelelőségi szabályzatokat eszközcsoportokban lévő eszközökre alkalmazhatja. Az eszközcsoportok részeként szereplő eszközök nem kapnak megfelelőségi műveletet.

#### <a name="new-management-name-column----1333586---"></a>Új oszlop Felügyeleti név elnevezéssel <!-- 1333586 -->
 Az Eszközök panelen új oszlop érhető el, **Felügyeleti név** elnevezéssel. Ez egy automatikusan létrehozott, nem szerkeszthető név, amely az alábbi képlet alapján rendelődik hozzá az egyes eszközökhöz:
- Az összes eszköz alapértelmezett neve: <username><em><devicetype></em><enrollmenttimestamp>
- Tömegesen hozzáadott eszközökhöz: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Ez egy választható oszlop az Eszközök panelen. Alapértelmezés szerint nem érhető el, csak az Oszlopválasztó használatával lehet hozzáférni. Az új oszlop nincs hatással az eszköz nevére.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Az iOS-eszközöktől 15 percenként PIN-kódot kér a rendszer <!--1550837 -->
Miután megfelelőségi vagy konfigurációs szabályzatot alkalmazott egy iOS-eszközre, a felhasználóktól 15 percenként egy PIN-kódot kér a rendszer. A kérések mindaddig megjelennek, amíg a felhasználó nem ad meg egy PIN-kódot.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Az automatikus frissítések ütemezése <!--1805514 -->
Az Intune-nal igény szerint telepítheti az automatikus frissítéseket a [Windows frissítési köreinek beállításaival](windows-update-for-business-configure.md). Ezzel a frissítéssel ismétlődő frissítéseket ütemezhet, amelyek a hetet, a napot és az időt is tartalmazzák.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Teljesen megkülönböztető név használata az SCEP-tanúsítvány tulajdonosaként <!--2221763 -->
SCEP-tanúsítványprofil létrehozásakor meg kell adnia a tulajdonos nevét. Ezzel a frissítéssel használhatja a teljesen megkülönböztető nevet. A **Tulajdonos neve** területen válassza az **Egyéni** lehetőséget, majd írja be a következőt: `CN={{OnPrem_Distinguished_Name}}`. Az `{{OnPrem_Distinguished_Name}}` változó használatához ügyeljen rá, hogy az `onpremisesdistingishedname` felhasználói attribútumot szinkronizálja az Azure AD-vel az [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) segítségével.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Bluetooth-alapú névjegymegosztás – Android for Work <!--1098983 -->
Alapértelmezés szerint az Android megakadályozza a munkahelyi profil névjegyeinek Bluetooth-eszközökkel való szinkronizálását. Ennek eredményeképpen a munkahelyi profil névjegyei nem jelennek meg a hívóazonosítón a Bluetooth-eszközökön.

Ez a frissítés egy új beállítást jelenít meg az **Android for Work** > **Eszközkorlátozások** > **Munkahelyi profil beállításai** területen:
- Névjegyek megosztása Bluetooth-kapcsolattal

Az Intune-rendszergazda konfigurálhatja ezeket a beállításokat a megosztás engedélyezéséhez. Ez akkor hasznos, ha egy eszközt egy autóalapú Bluetooth-eszközzel szeretne párosítani, amely megjeleníti a hívóazonosítót a kihangosítós használat során. Ha a beállítás engedélyezve van, a munkahelyi profil névjegyei megjelennek. Ha a beállítás le van tiltva, a munkahelyi profil névjegyei nem jelennek meg.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Gatekeeper konfigurálása a macOS rendszerű alkalmazásletöltés-források szabályozásához <!-- 1690459 -->

Megvédheti eszközeit a kéretlen alkalmazásoktól a Gatekeeper konfigurálásával, amely szabályozza, hogy mely helyekről tölthetők le alkalmazások. A következő letöltésforrásokat konfigurálhatja: **Mac App Store**, **Mac App Store és azonosított fejlesztők**, vagy **Mindenhonnan**. Azt is beállíthatja, hogy a felhasználók telepíthetnek-e alkalmazásokat úgy. hogy a CTRL + kattintás segítségével felülírják a Gatekeeper szabályozásait.

Ezek a beállítások az **Eszközkonfiguráció** -> **Profil létrehozása** -> **macOS** -> **Endpoint protection** területen találhatók meg.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac-alkalmazástűzfal konfigurálása <!-- 1690461 -->

Konfigurálhatja a Mac-alkalmazástűzfalat. Ennek révén alkalmazásonként, és nem portonként szabályozhatja a kapcsolódásokat. Így könnyebb kihasználni a tűzfalvédelem előnyeit, és meggátolni, hogy kéretlen alkalmazások foglalják le az engedélyezett alkalmazások számára megnyitott hálózati portokat.

Ez a funkció az **Eszközkonfiguráció** -> **Profil létrehozása** -> **macOS** -> **Endpoint protection** területen található meg.

A Tűzfal beállítás engedélyezése után két stratégia szerint konfigurálhatja a tűzfalat:

- Minden bejövő kapcsolat letiltása

   A megcélzott eszközökön letilthat minden bejövő kapcsolatot. Ha emellett dönt, az összes alkalmazás számára le lesznek tiltva a bejövő kapcsolatok.

- Egyes alkalmazások engedélyezése vagy letiltása

   A megadott alkalmazások számára engedélyezheti vagy tilthatja a bejövő kapcsolatok fogadását. A rejtett üzemmód engedélyezésével megakadályozhatja a válaszadást az ellenőrzési kérelmekre.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Részletes hibakódok és -üzenetek <!-- 1376342 -->

A hibakódok és hibaüzenetek részletesebben megtekinthetők az Eszközkonfigurációban. A továbbfejlesztett jelentés bemutatja a beállításokat, azok állapotát és a hibakeresés részleteit.

##### <a name="more-information"></a>További információ

- Minden bejövő kapcsolat letiltása

   Ez a beállítás megakadályozza, hogy a megosztási szolgáltatások (például a fájlmegosztás és a képernyőmegosztás) bejövő kapcsolatokat fogadjanak. A következő rendszerszolgáltatások továbbra is fogadhatnak bejövő kapcsolatokat:
  - configd – DHCP és más hálózati konfigurációs szolgáltatások megvalósítása
  - mDNSResponder – Bonjour megvalósítása
  - racoon – IPSec megvalósítása

    Megosztási szolgáltatások használata előtt gondoskodjon róla, hogy a **Bejövő kapcsolatok** lehetőség a **Nincs konfigurálva** (és ne a **Letiltás**) értékre legyen beállítva.

- Rejtett üzemmód

   Ha ezt az üzemmódot engedélyezi, a számítógép nem fog válaszolni az ellenőrzési kérelmekre. A számítógép továbbra is válaszol az engedélyezett alkalmazásokhoz tartozó kérelmekre. Az olyan váratlan kérelmeket, mint az ICMP (ping), a rendszer figyelmen kívül hagyja.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Az eszköz újraindításakor végzett ellenőrzések letiltása <!--1805490 -->
Az Intune-nal [kezelheti a szoftverfrissítéseket]](windows-update-for-business-configure.md). Ezzel a frissítéssel elérhetővé válik és alapértelmezés szerint hozzá lesz adva az <strong>Újraindítási ellenőrzések</strong> tulajdonság. Az eszközök újraindításakor végzett (például az aktív felhasználókra vagy az akkumulátor szintjére vonatkozó) rendszeres ellenőrzések átugrásához válassza a <strong>Kihagyás</strong> lehetőséget.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Új Windows 10 Insider Preview-csatornák a telepítési körökhöz <!-- 1746293 -->
Mostantól az alábbi Windows 10 Insider Preview-szolgáltatáscsatornákat választhatja Windows 10-es telepítési körök létrehozásakor:
- Windows Insider build &#8208; gyors
- Windows Insider build &#8208; lassú
- A Windows Insider build kiadása 

További információ ezekről a csatornákról: [Az Insider Preview buildek kezelése](https://insider.windows.com/en-us/for-business-organization-admin/).   
További információ a telepítési csatornák Intune-beli létrehozásáról: [Szoftverfrissítések kezelése az Intune-ban](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>A Céges portálra történő regisztráció továbbfejlesztése <!-- 1874230 eeready-->
A Céges portálon az 1703-as vagy annál újabb verziójú Windows 10 rendszerrel eszközt regisztráló ügyfelek az alkalmazás elhagyása nélkül hajthatják végre a regisztráció első lépését.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>A HoloLens és a Surface Hub most megjelenik az eszközlistákban <!--1725868 -->
Az Androidhoz készült Céges portál alkalmazás már támogatja az Intune-ban regisztrált HoloLens- és Surface Hub-eszközök megjelenítését.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Mennyiségi vásárlási programon (VPP) belül beszerzett e-könyvekhez rendelhető egyéni könyvkategóriák <!-- 1488911 -->
Egyéni e-könyv-kategóriákat hozhat létre, majd hozzájuk rendelheti a mennyiségi vásárlási programon belüli e-könyveket. A végfelhasználók egyaránt látni fogják az újonnan létrehozott e-könyv-kategóriákat és a hozzájuk rendelt könyveket. További információ: [Mennyiségi programban vásárolt alkalmazások és könyvek kezelése a Microsoft Intune-nal](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>A Windows Céges portál támogatási változásai a visszajelzésküldési funkcióval kapcsolatban <!-- 2070166 -->
2018. április 30-tól a Windows Céges portál **Visszajelzés küldése** funkciója csak a Windows 10 évfordulós frissítését (1607) vagy újabb verziót futtató eszközökön érhető el. Visszajelzés nem küldhető a Windows Céges portál a következő verziókkal történő használatakor:  
- Windows 10, 1507-es kiadás  
- Windows 10, 1511-es kiadás  
- Windows Phone 8.1 

Ha az eszköze a Windows 10 RS1 és későbbi verziót futtatja, töltse le a Windows Céges portál legújabb verzióját az Áruházból. Ha egy nem támogatott verziót használ, az alábbi csatornákon keresztül küldhet visszajelzést: 
- A Visszajelzési központ alkalmazás Windows 10-en
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Új Windows Defender alkalmazásőr-beállítások <!-- 1631890 -->

- **Grafikus gyorsítás engedélyezése**: A rendszergazdák engedélyezhetik egy virtuális grafikai processzor használatát a Windows Defender alkalmazásőr számára. Ezzel a beállítással a CPU a vGPU-ra terhelheti a grafikai renderelést. Ez javíthatja a teljesítményt a magas grafikai igényű webhelyekkel történő munka, valamint a tárolón belüli videók megtekintése során.

- **SaveFilestoHost**: A rendszergazdák engedélyezhetik a tárolóban futó Microsoft Edge fájljainak a gazdafájlrendszerbe való áttérését. Ennek a beállításnak a bekapcsolásával a felhasználók letölthetik tárolóban futó Microsoft Edge-fájlokat a gazdafájlrendszerbe.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Felügyeleti állapoton alapuló, célzott MAM-alapú védelmi szabályzatok <!-- 1665993 -->
Célzott MAM-szabályzatokat hozhat létre az eszköz felügyeleti állapota alapján:
- **Android-eszközök** – nem felügyelt és Intune által felügyelt eszközöket, valamint Intune által felügyelt Android Enterprise- (korábban Android for Work-) profilokat célozhat meg.
- **iOS-eszközök** – nem felügyelt (csak MAM) vagy Intune által felügyelt eszközöket célozhat meg.

    > [!NOTE]
    > - A funkció iOS-támogatása 2018. áprilisban jelenik meg.

További információ: [Eszközkezelési állapottól függő alkalmazásvédelmi szabályzatok](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Nyelvi fejlesztések a Windowshoz készült Céges portál alkalmazásban <!-- 1683758 -->
Fejlesztettük a Windows 10-hez készült Céges portál nyelvét, hogy közérthetőbb és az Ön vállalatára jellemzőbb legyen. Ha meg szeretne tekinteni néhány mintát, lépjen a [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) oldalra.

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Új, felhasználói adatvédelemmel kapcsolatos dokumentumok <!-- 1440709 -->
Szeretnénk nagyobb irányítást adni a felhasználóknak az adataik védelmével kapcsolatban, így frissítettük a Céges portál a helyben tárolt adatok megtekintésére és eltávolítására vonatkozó leírásokat tartalmazó dokumentumokat. A frissítéseket itt tekintheti meg:

- **Android**: [Android-eszköz regisztrációjának törlése az Intune-ból](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, ha a felhasználó nem fogadta el a használati feltételeket**: [Az eszközkezelés eltávolítása, ha nem fogadta el a használati feltételeket](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [iOS-eszköz eltávolítása az Intune-ból](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Windows-eszköz eltávolítása az Intune-ból](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>2018. március 19-i hét

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Minden eszköz exportálása CSV-fájlokba IE, Edge vagy Chrome böngészőben <!-- 2258071 -->
Az **Eszközök** > **Minden eszköz** területen **exportálhatja** az eszközöket egy CSV formátumú listába. Az Internet Explorer (IE) 10000 eszköznél kevesebbel rendelkező felhasználói sikeresen exportálhatják a fájljaikat több fájlba. Minden fájl legfeljebb 10000 eszközt tartalmaz.

Az Edge és a Chrome 30000 eszköznél kevesebbel rendelkező felhasználói sikeresen exportálhatják a fájljaikat több fájlba. Minden fájl legfeljebb 30000 eszközt tartalmaz.

Az [Eszközkezelés](device-management.md) területen további részletek jelennek meg a kezelt eszközökkel végezhető műveletekről.

## <a name="week-of-march-12-2018"></a>2018. március 12-i hét

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->

Az Azure Active Directory (Azure AD) használatával korlátozhatja a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el. További információért lásd: [Hozzáférés-vezérlés az Azure Active Directory feltételes hozzáférési funkciójában](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Frissített vezérlők az Androidhoz készült Céges portálhoz <!--976944 -->

Az Android [Material Design](https://material.io/) irányelveihez igazodva frissítettük az Androidhoz készült Céges portál alkalmazást. Az új ikonok képét [Az alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) cikkben tekintheti meg.

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Új beállítások a Windows Defender – biztonsági rés kiaknázása elleni védelemhez <!-- 1631893 -->

Hat új <strong>Támadási felület csökkentése</strong> beállítás és bővített <strong>Mappahozzáférés felügyelete: Mappavédelem</strong> funkciók érhetők el. Ezeket a beállításokat az alábbi helyen találhatja meg: Eszközkonfiguráció\Profilok\
Profil létrehozása\Endpoint Protection\Windows Defender - biztonsági rés kiaknázása elleni védelem.

#### <a name="attack-surface-reduction"></a>Támadási felület csökkentése

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Zsarolóprogramok elleni speciális védelem|Engedélyezve, Naplózás, Nincs konfigurálva|Zsarolóprogramok elleni agresszív védelem.|
|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése|Engedélyezve, Naplózás, Nincs konfigurálva|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése (lsass.exe).|
|Folyamatlétrehozás a PSExec- és WMI-parancsokból|Tiltás, Naplózás, Nincs konfigurálva|A PSEx-ec és WMI-parancsokból eredő folyamatlétrehozások letiltása.|
|Nem megbízható és aláíratlan, USB-ről futó folyamatok|Tiltás, Naplózás, Nincs konfigurálva|Nem megbízható és aláíratlan, USB-ről futó folyamatok letiltása.|
|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok|Tiltás, Naplózás, Nincs konfigurálva|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok letiltása.|

#### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

|              Beállítás neve               |                                                              Beállítás lehetőségei                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mappavédelem (már implementálva) | Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> <strong>Új</strong><br>Lemezmódosítás letiltása, lemezmódosítás naplózása |             |

Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

## <a name="week-of-february-19-2018"></a>2018. február 19-ei hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 -->

Az Intune mostantól támogatja az eszközök regisztrációját akár 100 különböző [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) vagy [Apple School Manager](apple-school-manager-set-up-ios.md) típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Felhasználónkénti regisztrációs korlátozások megtekintése <!-- 1634444 eeready wnready -->
A **Hibaelhárítás** panelen a **Hozzárendelések** lista [Regisztrációs korlátozások](enrollment-restrictions-set.md) elemét választva megjeleníthetők az egyes felhasználókra vonatkozó **regisztrációs korlátozások**.

### <a name="device-management"></a>Eszközkezelés
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>A Windows Defender állapota és a fenyegetések állapotjelentései <!--854704 -->

A Windows Defender állapotának megértése kulcsfontosságú a Windows rendszerű számítógépek kezelésében.  Ezzel a frissítéssel az Intune új jelentéseket és tevékenységeket ad hozzá a Windows Defender ügynök állapotához. Ha összesített állapotjelentést használ, az [Eszközmegfelelőségi tevékenységprofil](compliance-policy-monitor.md) területen azok az eszközök lesznek láthatóak, amelyeknek a következő elemek egyikére van szüksége:
- aláírás-frissítés
- Újraindítás
- kézi beavatkozás
- teljes vizsgálat
- egyéb, beavatkozást igénylő ügynökállapotok

Az állapotkategóriákhoz tartozó részletes jelentések ismertetik a figyelmet igénylő, illetve a **tisztaként** jelentő számítógépeket.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Új adatvédelmi beállítások az eszközkorlátozások számára <!--1308926 -->
Az eszközök számára [két új adatvédelmi beállítás](device-restrictions-windows-10.md#privacy) érhető el:
- **Felhasználói tevékenységek közzététele**: A megosztott élmények és a feladatváltóban nemrég használt erőforrások megelőzéséhez ezt a beállítást **tiltsa le**.
- **Csak a helyi tevékenységek**: A csak a helyi tevékenységek alapján megosztott használat és a feladatváltóban nemrég használt erőforrások felderítésének megelőzéséhez ezt a beállítást **tiltsa le**.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>A Microsoft Edge böngésző új beállításai <!--1469166 -->
A Microsoft Edge böngészőt használó eszközök számára [két új beállítás](device-restrictions-windows-10.md#edge-browser) érhető el: **A kedvencek fájl elérési útja** és **A Kedvencek módosításai**.

### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Alkalmazások protokollkivételei <!--1035509 -->

Az Intune mobilalkalmazás-kezelésének (MAM) adatátviteli szabályzatában kivételeket hozhat létre, így megnyithat konkrét nem kezelt alkalmazásokat. Az ilyen alkalmazásoknak az informatikai részleg bizalmát kell élvezniük. A létrehozott kivételen kívül az adatátvitel továbbra is csak azokra az alkalmazásokra korlátozódik, amelyeket az Intune kezel, ha az adatátviteli szabályzat **csak felügyelt alkalmazásokhoz** van konfigurálva. Korlátozásokat protokollokkal (iOS) vagy csomagokkal hozhat létre (Android).

Például hozzáadhatja kivételként a Webex-csomagot az MAM adatátviteli szabályzatához. Ezzel lehetővé teszi a kezelt Outlook-emailek Webex-hivatkozásai számára, hogy közvetlenül a Webex alkalmazásban nyíljanak meg. Az adatátvitel továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban. További információt [Az adatátviteli szabályzat kivételei alkalmazások esetén](app-protection-policies-exception.md) című témakörben találhat.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows Information Protection (WIP) által titkosított adatok megjelenítése a Windows keresési találatai között <!-- 1469193 -->
A Windows Információvédelem (WIP) szabályzatban egy beállítás érhető el annak megadásához, hogy a WIP által titkosított adatok megjelenjenek-e a Windows keresési találatai között. Ezt az alkalmazásvédelmi szabályzatot a Windows Információvédelem szabályzatának **Speciális beállításai** között, a **Titkosított elemek keresésének engedélyezése a Windows Search szolgáltatás indexelőprogramjában** lehetőséggel állíthatja be. Az alkalmazásvédelmi szabályzatot a *Windows 10* platformhoz kell beállítani, az alkalmazásszabályzat **Regisztrációs állapot** értékeként pedig a **Regisztrációval** értéket kell megadni. További információ: [Titkosított elemek keresésének engedélyezése a Windows Search szolgáltatás indexelőprogramjában](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Egy önfrissítő MSI-mobilalkalmazás konfigurálása <!-- 1740840 -->
Az ismert önfrissítő MSI-mobilalkalmazásokat konfigurálhatja úgy, hogy figyelmen kívül hagyják a verzióellenőrzési folyamatot. Ez a funkció akkor hasznos, ha nem szeretne versenyhelyzetbe kerülni. Ilyen típusú versenyhelyzet például akkor fordulhat elő, ha az alkalmazást egyszerre frissíti automatikusan a fejlesztő és az Intune. Mindkettő megpróbálja kényszeríteni az alkalmazás egy verziójának használatát a Windows-ügyfélen, ami üközést eredményezhet. Az ilyen automatikusan frissített MSI-alkalmazások esetében konfigurálhatja az **Alkalmazásverzió figyelmen kívül hagyása** beállítást az **Alkalmazásadatok** panelen. Ha ezt a beállítást átállítja az **Igen** értékre, a Microsoft Intune nem veszi tekintetbe a Windows-ügyfélen telepített alkalmazás verzióját.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Kapcsolódó alkalmazáslicenc-készletek Intune-támogatása <!-- 1864117 -->
Az Azure Portalbeli Intune a felhasználói felület egyedülálló alkalmazáselemeként támogatja a kapcsolódó alkalmazáslicenc-készleteket. Ezenkívül a Vállalati Microsoft Áruházból szinkronizált, offline licencelt alkalmazások egyetlen alkalmazásbejegyzésben lesznek összesítve, az egyes csomagok üzembe helyezési részleteit pedig migráljuk az egyedülálló bejegyzésbe. Ha meg szeretné tekinteni a kapcsolódó alkalmazáslicenc-készleteket az Azure Portalon, válassza a **Mobilalkalmazások** panel **Alkalmazáslicencek** lehetőségét.

### <a name="device-configuration"></a>Eszközök konfigurálása
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Windows Információvédelem (WIP) fájlkiterjesztések az automatikus titkosításhoz <!-- 1463582 -->
A Windows Információvédelem (WIP) szabályzatának egy beállításával megadható, hogy milyen kiterjesztésű fájlok legyenek automatikusan titkosítva, ha Server Message Block (SMB) megosztásról másolják őket a vállalatnak a WIP-szabályzat alapján meghatározott területén belül.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Erőforrásfiók-beállítások konfigurálása a Surface Hubokban

A Surface Hubok erőforrásfiók-beállításai távolról konfigurálhatók.

A Surface Hub az erőforrásfiókkal hitelesíthető a Skype/Exchange felé, így bekapcsolódhat az értekezletbe.
Célszerű létrehozni egy egyedi erőforrásfiókot, hogy a Surface Hub konferenciateremként jelenjen meg az értekezletben.
Az erőforrásfiók megjelenhet például **Konferenciaterem B41/6233** néven.

> [!NOTE]
> - Ha üresen hagy egyes mezőket, azzal felülírja a korábban konfigurált eszközattribútumokat.
>
> - Az erőforrásfiók tulajdonságai dinamikusan változhatnak a Surface Hubon. Például ha be van kapcsolva a jelszóváltoztatás. Így előfordulhat, hogy az Azure-konzol értékei csak egy kis idő múlva jelennek meg valós értékekként az eszközön.
>
>   Ha meg szeretné tekinteni a Surface Hub aktuálisan konfigurált beállításait, az erőforrásfiók adatait belefoglalhatja a hardverleltárba (amely jelenleg egy 7 napos intervallummal bír), vagy megjelenítheti azokat írásvédett tulajdonságokként. A távoli művelet után a pontosság javítása érdekében lekérheti a paramétereket közvetlenül a művelet futtatása után, így frissítheti a Surface Hub fiókját vagy paramétereit.


##### <a name="attack-surface-reduction"></a>Támadási felület csökkentése


|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Jelszóval védett végrehajtható tartalom futtatása e-mailből|Tiltás, Naplózás, Nincs konfigurálva|E-mailből letöltött jelszóval védett végrehajtható fájlok futtatásának megakadályozása.|
|Zsarolóprogramok elleni speciális védelem|Engedélyezve, Naplózás, Nincs konfigurálva|Zsarolóprogramok elleni agresszív védelem.|
|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése|Engedélyezve, Naplózás, Nincs konfigurálva|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése (lsass.exe).|
|Folyamatlétrehozás a PSExec- és WMI-parancsokból|Tiltás, Naplózás, Nincs konfigurálva|A PSEx-ec és WMI-parancsokból eredő folyamatlétrehozások letiltása.|
|Nem megbízható és aláíratlan, USB-ről futó folyamatok|Tiltás, Naplózás, Nincs konfigurálva|Nem megbízható és aláíratlan, USB-ről futó folyamatok letiltása.|
|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok|Tiltás, Naplózás, Nincs konfigurálva|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok letiltása.|

##### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

|              Beállítás neve               |                                                              Beállítás lehetőségei                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mappavédelem (már implementálva) | Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> <strong>Új</strong><br>Lemezmódosítás letiltása, lemezmódosítás naplózása |             |

Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>A Windows 10 rendszerbiztonsági beállításainak és a későbbi megfelelőségi szabályzatok bővítése <!--1704133-->

Elérhető a Windows 10 megfelelőségi beállításainak bővítése, amely a tűzfalat és a Windows Defender víruskeresőt is kötelezővé teszi.


### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés
### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>A Vállalati Microsoft Áruházból származó offline alkalmazások támogatása <!--1222672-->
A Vállalati Microsoft Áruházban vásárolt offline alkalmazások mostantól szinkronizálhatók az Azure Portallal. Ezeket az alkalmazásokat eszközcsoportok vagy felhasználói csoportok számára telepítheti. Az offline alkalmazásokat az Intune, és nem az Áruház telepíti.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>A munkahelyi profilban található fiókok manuális hozzáadásának vagy eltávolításának letiltása a végfelhasználók számára <!-- 1728700 -->

A Gmail alkalmazás egy Android for Work-profilba történő telepítésekor az Android for Work Eszközkorlátozások profiljának **Fiók hozzáadása és eltávolítása** beállítása segítségével megakadályozható, hogy a végfelhasználók manuálisan fiókokat adjanak hozzá vagy távolítsanak el.

## <a name="week-of-february-5-2018"></a>2018. február 5-ei hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Új felhasználóhitelesítési lehetőség az Apple-eszközök tömeges regisztrálásakor <!-- 747625 eeready -->

> [!NOTE]
> Ez azonnal látható az új bérlők számára. A meglévő bérlők számára a áprilisban válik elérhetővé a funkció. A bevezetés befejezéséig elképzelhető, hogy nem lehet hozzáférni az új funkciókhoz.

Az Intune mostantól lehetővé teszi az eszközök Céges portál alkalmazással való hitelesítését az alábbi regisztrációs módszerek használatakor:

- Apple Készülékregisztrációs program
- Apple School Manager
- Apple Configurator-regisztráció

A Céges portál lehetőség használatakor kényszerítheti az Azure Active Directory többtényezős hitelesítését anélkül, hogy blokkolná ezen regisztrációs módszereket.

A Céges portál lehetőség választásakor az Intune kihagyja a felhasználóhitelesítést az iOS beállítási asszisztensben, és felhasználói affinitáson alapuló regisztrációt végez. Ez azt jelenti, hogy az eszköz kezdetben felhasználó nélküli eszközként lesz regisztrálva, így nem kapja meg a felhasználói csoportokhoz tartozó konfigurációkat és szabályzatokat. Ehelyett csak az eszközcsoportoktól kap konfigurációkat és szabályzatokat. Az Intune automatikusan telepíti a Céges portál alkalmazást az eszközön. A Céges portál alkalmazást elindító és abba bejelentkező első felhasználót társítja az Intune az eszközhöz. Ezen a ponton a felhasználó már megkapja a felhasználói csoporthoz tartozó konfigurációkat és szabályzatokat. Ezt a felhasználótársítást csak a regisztráció megismétlésével lehet megváltoztatni.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 eeready -->

Az Intune mostantól támogatja az eszközök regisztrációját akár 100 különböző Apple Device Enrollment Program (DEP) vagy Apple School Manager típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Távoli nyomtatás biztonságos hálózaton keresztül <!-- 1709994  -->
A PrinterOn vezeték nélküli nyomtatási megoldásaival a felhasználók távolról nyomtathatnak, bárhol és bármikor, egy biztonságos hálózaton keresztül. A PrinterOn integrálva lesz az Intune APP SDK-val mind az iOS, mind pedig az Android rendszerhez. Ehhez az alkalmazáshoz az Intune felügyeleti konzol **Alkalmazásvédelmi szabályzatok** paneljével társíthat alkalmazásvédelmi szabályzatokat. A végfelhasználók letölthetik a „PrinterOn for Microsoft” alkalmazást a Play Áruházból vagy az iTunes áruházból, és használhatják azt az Intune rendszerükben.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>A macOS-es Céges portál támogatja a Készülékregisztráció-kezelős regisztrációt <!-- 1352411 -->

A felhasználók a Készülékregisztráció-kezelővel regisztrálhatnak a macOS Céges portálra.

## <a name="week-of-january-29-2018"></a>2018. január 29-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Riasztás a lejárt és hamarosan lejáró tokenekről <!-- 1639263 -->
Az áttekintő lap mostantól riasztást jelenít meg a lejárt és hamarosan lejáró tokenekről. Az egyes tokenekhez tartozó riasztásra kattintva elérheti a token részleteinek lapját.  Ha több tokenről szóló riasztásra kattint, akkor a rendszer megjeleníti az adott állapotú tokenek listáját. A rendszergazdáknak meg kell újítaniuk a tokenjeiket, mielőtt lejárnának.

### <a name="device-management"></a>Eszközkezelés

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Távoli törlési parancs támogatása macOS rendszerű eszközökön <!-- 1438084 -->

A rendszergazdák távolról is kiadhatnak törlési parancsot a macOS rendszerű eszközökön.

> [!IMPORTANT]
> A törlési parancs nem vonható vissza, ezért legyen óvatos a használatakor.

A törlési parancs eltávolítja az összes adatot az eszközről, az operációs rendszert is ideértve. Emellett az Intune-ból is eltávolítja az eszközt. Nem jelenik meg figyelmeztetés a felhasználónak, és a törlés a parancs kiadása után azonnal megkezdődik.

Be kell állítania egy 6 számjegyből álló helyreállítási PIN-kódot. Ezzel a PIN-kóddal feloldhatja az eszköz zárolását a törlést követően, mely után megkezdődik az operációs rendszer újratelepítése. A törlés megkezdése után megjelenik a PIN-kód az eszköz Intune-beli áttekintő paneljén. A PIN-kód a törlés végrehajtása alatt végig látható marad. A törlés után az eszköz eltűnik az Intune rendszerből. Ne felejtse el feljegyezni ezt a helyreállítási PIN-kódot az eszköz helyreállítását végző személy számára.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>iOS Volume Purchasing Program-token licenceinek visszavonása <!-- 820870 -->
Visszavonhatja az adott VPP-tokenhez tartozó összes iOS Volume Purchasing Program-alkalmazás (VPP-alkalmazás) licencét.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS Volume Purchase Program-alkalmazások visszavonása  <!-- 820863 -->
Ha egy adott eszközhöz egy vagy több iOS Volume Purchase Program-alkalmazás is tartozik, akkor visszavonhatja az eszköztől az eszközalapú alkalmazáslicencet. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. További információért olvassa el a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakört.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Office 365-mobilalkalmazások hozzárendelése iOS- és Android-eszközökhöz a regisztrált alkalmazástípussal <!-- 1332318 -->
A **Beépített** alkalmazástípussal könnyebben hozhat létre és rendelhet Office 365-alkalmazásokat a felügyelt iOS- és Android-eszközeihez. Ezek az alkalmazások olyan 0365-alkalmazásokat tartalmaznak, mint a Word, az Excel, a PowerPoint és a OneDrive. Az alkalmazástípushoz konkrét alkalmazásokat rendelhet hozzá, valamint szerkesztheti az alkalmazásadatok konfigurációját.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Alkalmazástársítás belefoglalása vagy kizárása csoportok alapján <!-- 1406920 -->

Az alkalmazások társítása során, illetve a társítás típusának kiválasztása után megadhatja a belefoglalni, valamint a kizárni kívánt csoportokat.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>A hozzárendelések belefoglalásával és kizárásával alkalmazáskonfigurációs szabályzatot rendelhet a csoportokhoz  <!-- 1480316 -->

A hozzárendelések belefoglalásának és kizárásának kombinációjával alkalmazáskonfigurációs szabályzatot rendelhet a felhasználók és eszközök egy csoportjához. A hozzárendeléseket vagy egyénileg kijelölt csoportokként, vagy virtuális csoportként lehet kiválasztani. A virtuális csoportok a következőket tartalmazhatják: **Minden felhasználó**, **Minden eszköz**, és **Minden felhasználó és minden eszköz**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Támogatás a Windows 10-kiadások frissítési szabályzatához <!-- 903672(archived), 1119689 -->  
A Windows 10-hez létrehozhat olyan kiadásfrissítési szabályzatot, amely a Windows 10-es eszközöket az alábbi verziókra frissíti: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education és Windows 10 Professional Education N. A Windows 10 kiadásfrissítéseiről a [Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md) című témakörből tájékozódhat.

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Az Intune feltételes hozzáférési szabályzatai csak az Azure Portalon állnak rendelkezésre <!-- 1737088 1634311 -->

Ettől a kiadástól kezdődően feltételes hozzáférési szabályzatok konfigurálására és felügyeletére az [Azure Portal ](https://portal.azure.com) **Azure Active Directory** > **Feltételes hozzáférés** menüpontjában van lehetőség. A kényelmes használat céljából ez a panel az Intune-ban is elérhető az Azure Portal **Intune** > **Feltételes hozzáférés** menüpontjában.

#### <a name="updates-to-compliance-emails---1637547---"></a>Frissített megfelelőségi e-mailek <!--1637547 -->

A nem megfelelő eszközökről értesítő e-mailekben szerepelnek a nem megfelelő eszközök adatai.


## <a name="week-of-january-22-2018"></a>2018. január 22-i hét

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Új funkciók a „Feloldás” művelethez Android-eszközök esetén <!--1583480-->

Az Androidhoz készült Céges portál alkalmazás bővíti az **eszközbeállítások frissítése** esetén használható „Feloldás” műveletet az [eszköztitkosítási problémák](/intune-user-help/encrypt-your-device-android) megoldásához.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Elérhető a távoli zárolás a Windows 10-es Céges portál alkalmazásban<!--676506-->
A végfelhasználók mostantól távolról zárolhatják az eszközeiket a Windows 10-es Céges portál alkalmazásból. Ez nem jelenik meg a helyi eszközön, amit aktívan használnak.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Megfelelőségi problémák egyszerűbb megoldása a Windows 10 rendszerhez készült Céges portál alkalmazásban <!--676546-->
A Windows-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma.

## <a name="week-of-december-11-2017"></a>2017. december 11-i hét

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Új automatikus újratelepítési beállítás <!-- 1469168 -->
Az **Automatikus újbóli üzembe helyezés** beállítás lehetővé teszi a rendszergazdai jogosultságokkal rendelkező felhasználóknak, hogy az eszköz zárolási képernyőjén a **CTRL + Win + R** billentyűkombinációval törölhessék az összes felhasználói adatot és beállítást. Ennek hatására automatikusan megtörténik az eszköz újbóli konfigurálása és regisztrálása felügyeletre. A beállítás a Windows 10 > Eszközkorlátozások > Általános > Automatikus újbóli üzembe helyezés menüpontban található. További részletekért lásd: [Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Windows 10 esetén](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>További forráskiadások támogatása a Windows 10 kiadásfrissítési szabályzatában  <!-- 903672,  1119689 -->
Mostantól a Windows 10 kiadásfrissítési szabályzatával további Windows 10-kiadásokról is frissíthet (például Windows 10 Pro, Windows 10 Pro Education és Windows 10 Cloud). Korábban a támogatott kiadásfrissítési útvonalak korlátozottabbak voltak. További információért lásd: [A Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Új beállítások az eszközkonfigurációs profilban: Windows Defender biztonsági központ (WDSC)<!-- 1335507 -->

Az Intune eszközkonfigurációs profiljának beállításai új szakasszal bővültek. Ez a **Windows Defender biztonsági központ** néven szerepel az Endpoint Protection szakasznál. A rendszergazdák beállíthatják, hogy a Windows Defender biztonsági központ alkalmazás mely területei legyenek elérhetők a végfelhasználók számára. Ha a rendszergazda elrejti a Windows Defender biztonsági központ valamelyik területét, a felhasználó eszközén nem fognak megjelenni az adott területtel kapcsolatos értesítések.

A rendszergazdák a következő területeket rejthetik el a Windows Defender biztonsági központ eszközkonfigurációs profilbeállításai közül:
- Vírusok és veszélyforrások elleni védelem
- Eszközteljesítmény és -állapot
- Tűzfal és hálózatvédelem
- Alkalmazás- és böngészővezérlés
- Családi beállítások

A rendszergazdák azt is személyre szabhatják, hogy a felhasználók melyik értesítéseket kapják meg. Beállítható például, hogy a felhasználók a Windows Defender biztonsági központ összes látható területének értesítéseit megkapják, vagy csak a kritikus értesítéseket. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső rendszeres összefoglalói és a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül. Emellett testre is szabhatja az értesítések tartalmát, például a rendszergazda elérhetőségét beágyazhatja a felhasználók eszközein megjelenő értesítések szövegébe.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Több összekötő támogatása az SCEP- és a PFX-tanúsítványok kezeléshez <!-- 1361755 -->

Azok az ügyfeleink, akik helyszíni NDES-összekötővel kézbesítik a tanúsítványokat az eszközökre, mostantól több összekötőt is beállíthatnak egy bérlőben.

Ez az új funkció támogatja az alábbi forgatókönyvet:

- **Magas rendelkezésre állás**

Az egyes NDES-összekötők lekérik a tanúsítványkérelmeket az Intune-ból.  Ha az egyik NDES-összekötő offline állapotba kerül, a másik összekötő folytathatja a kérelmek feldolgozását.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Az ügyfelek tulajdonosnevében használható az AAD_DEVICE_ID változó  <!-- 1468599 -->

Az SCEP-tanúsítványprofilok Intune-ban való létrehozásakor mostantól használhatja az AAD_DEVICE_ID változót az egyéni tulajdonosnevek létrehozásakor.   Az ilyen SCEP-profillal való tanúsítványkéréskor a rendszer lecseréli a változót a tanúsítványkérelmező eszköz AAD-eszközazonosítójára.


### <a name="device-management"></a>Eszközkezelés

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>A Jamf-ban regisztrált macOS-eszközök kezelése az Intune eszközmegfelelőségi motorjával <!-- 1592747 -->
Mostantól a Jamf a macOS-eszközök eszközállapotát is elküldheti az Intune-nak, az pedig vizsgálni fogja, hogy megfelelnek-e az eszközök az Intune konzolban meghatározott szabályzatoknak. Az eszközmegfelelőségi állapot és más feltételek (például tartózkodási hely, felhasználói kockázat) vizsgálata alapján a feltételes hozzáférés megköveteli, hogy a macOS-eszközök megfeleljenek a szabályzatoknak, ha az Azure AD-hoz kapcsolt felhőalapú vagy helyszíni alkalmazásokat érnek el (az Office 365-öt is beleértve). Tudjon meg többet [a Jamf-integráció beállításáról](conditional-access-integrate-jamf.md) és [a Jamf által felügyelt eszközök megfelelőségének kényszerítéséről](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Új iOS-eszközművelet   <!-- 1424701 -->

Mostantól leállíthatja az iOS 10.3 rendszerű felügyelt eszközöket. Ez a művelet azonnal leállítja az eszközt, anélkül, hogy a végfelhasználót figyelmeztetné. A **Leállítás (csak felügyelt eszköz esetén)** műveletet az eszköztulajdonságoknál találhatja, amikor kiválaszt egy eszközt az **Eszköz** tevékenységprofilban.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Dátum- és időmódosítás letiltása Samsung Knox-eszközökön <!-- 1468103 -->

Bevezettünk egy új funkciót, melynek segítségével letilthatja a dátum- és időmódosítást a Samsung Knox-eszközökön. Ezt a következő területen találhatja meg: **Eszközkonfigurációs profilok** > **Eszközkorlátozások (Android)** > **Általános**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub-erőforrásfiókok támogatása <!-- 1566442  -->

Egy új eszközművelet segítségével mostantól a rendszergazdák megadhatják és frissíthetik a Surface Hubhoz társított erőforrásfiókot.

A Surface Hub az erőforrásfiókkal hitelesíthető a Skype/Exchange felé, így bekapcsolódhat az értekezletbe. Létrehozhat egy egyedi erőforrásfiókot, hogy a Surface Hub konferenciateremként jelenjen meg az értekezletben. Az erőforrásfiók megjelenhet például *Konferenciaterem B41/6233* néven. A Surface Hub-erőforrásfiókot (vagyis az eszközfiókot) általában a konferencia helyszínéhez kell beállítani akkor, amikor az erőforrásfiók egyéb paramétereit is meg kell változtatni.

Ha a rendszergazdák megpróbálják frissíteni az eszköz erőforrásfiókjának adatait, meg kell adniuk az eszközhöz rendelt Active Directory-beli/Azure Active Directory-beli hitelesítő adatokat. Ha az eszköznél jelszóváltoztatás van beállítva, a rendszergazdának az Azure Active Directoryban kell megkeresnie a jelszót.

> [!NOTE]
> A mezőket egy csomagban küldi el a rendszer, és az összes korábban beállított mező értékét felülírja. Az üres mezők is felülírják a meglévő mezőket.

A rendszergazdák a következő beállításokat konfigurálhatják:

- **Erőforrásfiók**
   - **Active Directory-felhasználó**

      Tartománynév\felhasználónév vagy egyszerű felhasználónév (UPN): user@domainname.com

   - **Jelszó**

- **További nem kötelezően kitöltendő erőforrásfiók-paraméterek**  (az adott erőforrásfiókkal kell beállítani)

   - **Jelszóváltoztatás gyakorisága**

     Gondoskodik róla, hogy a fiók jelszavát a Surface Hub biztonsági okokból minden héten automatikusan frissítse. A funkció bekapcsolását követően a további paraméterek beállításához új jelszót kell kérni a fiókhoz az Azure Active Directoryban.

   - **SIP-cím**

     Csak abban az esetben szükséges, ha az automatikus felfedezés sikertelen.

   - **Email**

     Az eszköz/erőforrásfiók e-mail-címe.

   - **Exchange-kiszolgáló**

     Csak abban az esetben szükséges, ha az automatikus felfedezés sikertelen.

   - **Naptár-szinkronizálás**

     A naptár-szinkronizálás és más Exchange Server-szolgáltatások engedélyezését teszi lehetővé. Például: értekezlet-szinkronizálás.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Office-alkalmazások telepítése macOS-eszközökre <!-- 1494311 -->
Mostantól macOS-eszközökre is telepíthetők az Office-alkalmazások. Az új alkalmazástípusnak köszönhetően telepíteni lehet a Word, az Excel, a PowerPoint, az Outlook és a OneNote alkalmazást. Az alkalmazások a Microsoft AutoUpdater (MAU) szolgáltatást is tartalmazzák, amely segít a biztonság megőrzésében és az alkalmazások folyamatos frissítésében.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>iOS Volume Purchasing Program-token törlése <!-- 820879 -->
A konzol segítségével törölheti az iOS Volume Purchasing Program (VPP) tokenjét. Ez akkor lehet szükséges, ha egy VPP-token több példányban van meg.

### <a name="intune-apps"></a>Intune-alkalmazások


### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Az Aktuális felhasználó nevű új entitásgyűjtemény a jelenleg aktív felhasználói adatokra korlátozódik <!-- 1667026 -->

A **Felhasználók** entitásgyűjtemény a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót tartalmazza. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. A felhasználó a jelentés időpontjában nincs jelen, de az adatok tartalmazzák a felhasználót és állapotát. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

Ezzel szemben az új **Aktuális felhasználó** entitásgyűjtemény csak azokat a felhasználókat tartalmazza, akiket nem távolítottak el. Az **Aktuális felhasználó** entitásgyűjtemény csak a jelenleg aktív felhasználókat tartalmazza. Az **Aktuális felhasználó** entitásgyűjteménnyel kapcsolatban az [Aktuális felhasználó típusú entitás referenciája](reports-ref-current-user.md) oldalon talál további információkat.


### <a name="updated-graph-apis----1736360---"></a>Frissített Graph API-k <!-- 1736360 -->

A jelen kiadásban frissítettük az Intune-hoz készült bétaverziós Graph API-k egy részét. További információt a [Graph API havi változásnaplójában](https://developer.microsoft.com/graph/docs/concepts/changelog) találhat.

## <a name="week-of-december-4-2017"></a>2017. december 4-i hét

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Az Intune támogatja a Windows Information Protection (WIP) által tiltott alkalmazásokat <!-- 1479103 -->
A tiltott alkalmazásokat az Intune-ban lehet meghatározni. Tiltás esetén az adott alkalmazás nem férhet hozzá vállalati információkhoz, ellentétben az engedélyezett listán lévő alkalmazásokkal. További információért lásd: [A Windows Information Protection ajánlott letiltási listája](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).



## <a name="notices"></a>Értesítések

### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Szükséges intézkedés: Kérjük, frissítse az Android eszközkorlátozási vagy megfelelőségi szabályzatának jelszóbeállításait az Intune-ban
Az Intune-ból eltávolítjuk az eszköz alapértelmezett jelszavaként szolgáló jelszótípust az Android 4.4-es és újabb eszközök esetében. Az Android-platformok és az eszközök alapértelmezett beállításainak eltérései miatt az eszközök ezt a szabályzatot gyakran opcionálisként kezelik. Annak érdekében, hogy ne okozzon zavart, ha egy Android készüléken ez a beállítás van kötelezőként megadva, egy következő kiadásban eltávolítjuk a beállítást a kezelőfelületről. 
#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
- Ha az a célja, hogy az eszközökön kötelező legyen megadni valamilyen jelszót, javasoljuk, hogy az „eszköz alapértelmezett jelszavának” használata helyett úgy szerkessze az Android-platformprofilokat, hogy azok egyértelműen leírják a kívánt jelszótípust.
- Ha azt szeretné, hogy a végfelhasználók szabadon eldönthessék, létre szeretnének-e hozni egy jelszót, válassza a „Nincs konfigurálva” lehetőséget. Ha még mindig az „eszköz alapértelmezett jelszava” beállítás van érvényben, amikor eltávolítjuk ezt a beállítást a felhasználói felületről, akkor a profil következő szerkesztésekor választania kell egy másik értéket.
Hogyan készüljek fel a változásra?
Tekintse át a jelszóbeállításokat az Android vállalati eszközkorlátozási és megfelelőségi szabályzataiban. A megfelelőségi szabályzatok a Rendszerbiztonság alatt, az eszközkorlátozási szabályzatok pedig az Eszközjelszó vagy a Munkaprofil alatt találhatók meg. A további információk között talál egy hivatkozást, amelyen keresztül további részleteket és képernyőképeket talál ezekkel a beállításokkal kapcsolatban.
####<a name="additional-information"></a>További információ
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Tervezett változtatás: Jelszóváltoztatás az Intune-hoz hozzáadott Next Authban <!-- 1873216 -->
Az Intune a szolgáltatás szeptemberi kiadásában az Apple újonnan kiadott **Jelszóváltoztatás a Next Authban** beállításának integrációját tervezi a macOS 10.13-as vagy újabb verzióját futtató eszközökhöz. Amíg ez a beállítás nincs jelen, az MDM-szolgáltatók nem tudják ellenőrizni, hogy az eszköz jelszavát megváltoztatták-e a megfelelőséghez. Az Intune konfigurációs és megfelelőségi szabályzatai csak azt ellenőrzik, hogy a jelszó a legközelebbi változtatáskor megfelelőként van-e jelölve. Az új Apple-funkció hozzáadása után a macOS-felhasználók akkor is felszólítást kapnak a jelszó megváltoztatására, ha a jelszó megfelelő.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ez olyan környezetekre vonatkozik, amelyek az Intune-t vagy hibrid MDM-et használó macOS rendszerű eszközök szabályzatait tartalmazzák. Most, hogy az Apple elérhetővé tette a **Jelszóváltoztatás a New Authban** beállítást, az Intune kikényszerítheti, hogy a felhasználók frissítsék a jelszót a jelszószabályzat leküldésekor. Ha Ön letiltja a céges erőforrásokat az eszköz megfelelőként jelöléséig, a végfelhasználók csak akkor férhetnek hozzá az olyan céges erőforrásokhoz, mint az e-mail vagy a SharePoint-webhelyek, ha már alaphelyzetbe állították a jelszót. A jövőben a konfigurációs és megfelelőségi jelszószabályzatok minden frissítése ki fogja kényszeríteni, hogy a megcélzott felhasználók jelszót változtassanak.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Értesítse a segélyszolgálatot. Ha nem szeretné kikényszeríteni ezt a macOS-es eszközszabályzatot, akkor a meglévő macOS-szabályzat hozzárendelése vagy törlése javasolt. Az ügyfelek körében végzett kutatás szerint a legtöbb ügyfelet nem érinti ez a változtatás. A végfelhasználók többsége a jelszavas bejelentkezésre való felszólítás után frissíti a jelszavát, vagy alaphelyzetbe állítja azt a megfelelőség megőrzéséhez.


### <a name="plan-for-change-intune-moving-to-support-ios-10-and-later-in-september----2454656---"></a>Tervezett módosítás: az Intune szeptembertől támogatni fogja az iOS 10-es vagy újabb verziót <!-- 2454656 -->
Szeptemberben az Apple várhatóan kiadja az iOS 12-es verzióját. Röviddel a kibocsátása után az Intune-beli regisztráció, a Céges portál és a felügyelt böngésző funkció támogatni fogja az iOS 10-es és újabb verzióját.  

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?  
Az Office 365 mobilalkalmazásai támogatottak az iOS 10-es és újabb eszközökön, tehát lehet, hogy már frissítette az operációs rendszert vagy az eszközöket. Ebben az esetben ez a változás Önt nem érinti.  

Ha azonban rendelkezik az alábbi eszközök közül valamelyikkel, vagy szeretné ezek közül valamelyiket regisztrálni, ne feledje, hogy azok csak az iOS 9-es vagy régebbi verziókat támogatják.  Az Intune Céges portál további eléréséhez szeptemberig ezeket az eszközöket olyanokra kell cserélnie, amelyek támogatják az iOS 10-es és újabb verzióit:  

* iPhone 4S  
* iPod Touch  
* iPad 2  
* iPad (3. generáció)  
* iPad Mini (1. generáció)  

Júliustól kezdődően azokon az MDM szolgáltatásban regisztrált eszközökön, amelyek iOS 9-es operációs rendszerrel és Céges portállal is rendelkeznek, az operációs rendszer vagy az eszköz frissítését kérő értesítés fog megjelenni. Alkalmazásvédelmi szabályzatok használata esetén a „Minimális iOS operációsrendszer-verzió megkövetelése (csak figyelmeztetés)” hozzáférési beállítást is megadhatja.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?   
Keressen a cégnél a változás által érintett eszközöket vagy felhasználókat. Az Azure Portalbeli Intune-ban lépjen az Eszközök > Minden eszköz területre, és adjon meg szűrőt az operációs rendszer alapján.  Kattintson az Oszlopok elemre a részletek, például az operációs rendszer verziójának megjelenítéséhez. Kérje meg a felhasználókat, hogy frissítsék eszközeiket egy támogatott operációsrendszer-verzióval rendelkezőre még szeptember előtt.  

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Tervezett változtatás: az Intune áttér a TLS 1.2 verzióra
2018. október 31-étől az Intune támogatni fogja a Transport Layer Security (TLS) protokoll 1.2 verzióját, hogy kategóriájában a legjobb titkosítást nyújtsa, biztosítsa a szolgáltatás jobb alapértelmezés szerinti biztonságát, és hogy illeszkedjen olyan más Microsoft-szolgáltatásokhoz, mint a Microsoft Office 365. Az Office ezt a változtatást az MC128929 közleményben jelentette be.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
2018. október 31-étől az Intune nem támogatja a TLS protokoll 1.0 és 1.1 verzióját. Az Intune-nal való problémamentes kapcsolat érdekében minden ügyfél-kiszolgáló és böngésző-kiszolgáló kombinációnak a TLS 1.2-es verzióját kell használnia. Lényeges, hogy ez a változás azokat a végfelhasználói eszközöket is érinti, amelyeket az Intune nem támogat többé, de továbbra is kapnak szabályzatokat az Intune-on keresztül, és nem alkalmasak a TLS 1.2 használatára. Ilyenek többek között az Android 4.3-as és régebbi verzióit futtató eszközök. Az érintett eszközök és böngészők listája alább, a További információk között található.

Ha 2018. október 31-e után egy régi TLS-verzió használatával kapcsolatos problémát tapasztal, akkor a megoldáshoz át kell térnie a TLS 1.2-re, vagy olyan eszköz használatára, amely támogatja a TLS 1.2-t.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ajánlott megelőző lépésként eltávolítani a TLS 1.0 és 1.1 verzióit és azok függőségeit a környezeteiből, és ahol ez lehetséges, az operációs rendszer szintjén letiltani a TLS 1.0 és 1.1 verziókat. Kezdje meg máris a TLS 1.2-re való áttérés megtervezését. Az alábbi támogatási blogbejegyzésben megtalálja azoknak az eszközöknek a listáját, amelyeket az Intune már nem támogat, de még mindig kaphatnak szabályzatokat, és amelyek nem képesek a TLS 1.2 verziójának használatával kommunikálni. Ezeket a végfelhasználókat szükséges lehet értesíteni arról, hogy a jövőben nem fogják tudni elérni a vállalati erőforrásokat.

**További információ**: [Az Intune áttér a TLS 1.2 használatára a titkosításhoz](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Tervezett módosítás: A Microsoft Intune App SDK for Cordova beépülő modul támogatásának változása
Az Intune 2018. május 1-ével befejezi a [Microsoft Intune App SDK Cordova beépülő modul](app-sdk-cordova.md) támogatását. Helyette az Intune App Wrapping Tool eszköz használatát javasoljuk a Cordova-alapú alkalmazások előkészítésére a kezelhetőség és a rendelkezésre állás érdekében az Intune-ban. A módosítás életbe lépését követően a Microsoft Intune APP SDK for Cordova beépülő modul támogatása megszűnik, és frissítést sem fog kapni. Az alkalmazásfejlesztők a továbbiakban nem használhatják ezt a beépülő modult. Az Intune azt tervezi, hogy továbbra is támogatja a Cordovával készített alkalmazásokat. A Microsoft Intune APP SDK for Cordova beépülő modullal készült alkalmazások azonban csökkentett funkcionalitással fognak működni az Intune-ban. Az Intune App Wrapping Tool eszközével elvégzett alkalmazásburkolást követően az alkalmazások ugyanúgy üzembe helyezhetők a végfelhasználók számára, mint a normál esetben. A Google Play Áruházban megjelent Cordova-alapú Android-alkalmazások esetén:
- Az alkalmazás első indításakor a végfelhasználóknak meg kell adniuk a hitelesítő adataikat, hogy megkapják az Intune-szabályzatot.
- Az alkalmazásokat az Intune-felhasználókat megcélozva kell közzétenni az alkalmazásáruházban. Példa: „Contoso alkalmazás Intune-hoz”.

További információk az alkalmazásburkoló eszközről: [iOS-hez készült alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md) és [Androidhoz készült alkalmazásburkoló eszköz](app-wrapper-prepare-android.md). Ha problémája vagy kérdése van, írjon az [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com) címre.

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Tervezett változtatás: Az Intune használata az Azure-on MDM-kezelésre <!-- 1227338 -->
Több mint egy évvel ezelőtt bejelentettük az [Azure Intune nyilvános előzetes verzióját](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/), hat hónapja pedig az [Intune új rendszergazdai felületének általános elérhetővé válását](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/). 2018. augusztus 31-étől kikapcsoljuk a hagyományos Silverlight-konzol mobileszköz-kezelését (MDM) azon ügyfelek számára, akik az Intune önálló verzióját használják. Ők ehelyett az [Azure Intune-t](https://aka.ms/Intune_on_Azure) használhatják a mobileszközök kezelésére. Ha még a hagyományos konzolt használja a mobileszköz-kezeléshez, ismerkedjen meg az Azure Intune-nal, és térjen át a használatára. Ez a módosítás várhatóan nem lesz hatással a végfelhasználókra. A hagyományos PC-kezelés továbbra is a Silverlightban marad. Erről a változásról, valamint annak hatásairól [itt](https://aka.ms/Intune_on_Azure_mdm) találhat további információt.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el az Azure Portal, javasoljuk, hogy hozzon létre egy próbafiókot az új felület kipróbálásához.

## <a name="whats-coming"></a>Mi várható?

### <a name="local-device-security-option-settings----1251887---"></a>Helyi eszközbiztonsági beállítások <!-- 1251887 -->
A Windows 10-eszközökön az új Helyi eszközbiztonsági beállításokkal adhat meg biztonsági beállításokat. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Új frissítés a felhasználói felülethez a Céges portál webhelyen <!--2000968-->

Augusztustól új felhasználói élményt vezetünk be a Céges portál webhelyén, melynek része a megújult felhasználói felület, az egyszerűsített műveletek és továbbfejlesztett akadálymentes felület. A felhasználóbarátabb élmény érdekében az ügyfelek által javasolt olyan fejlesztéseket valósítottunk meg, mint az alkalmazások megosztása és a teljesítmény javítása általában.
Ügyfeleink javaslatai alapján olyan új funkciókat is bevezettünk, amelyek jelentősen megnövelik a jelenlegi funkciók használhatóságát és működését:

* A webhely felhasználói felületének fejlesztései
* Alkalmazások közvetlen hivatkozásainak megoszthatósága
* Nagy méretű alkalmazáskatalógusok javított teljesítménye

A változás érvénybe lépéséhez Önnek semmit nem kell tennie. Értesíteni fogjuk Önt, ha elérhetővé válik a megújult Céges portál webhely. Arra azonban szükség lehet, hogy a végfelhasználói dokumentumokat az új képernyőképekkel frissítse. Emellett frissítést igényelhet az iOS-es Céges portál alkalmazás dokumentációja is, mivel az iOS-alkalmazás **Alkalmazások** szakasza a webhelyre támaszkodik. Ehhez egy képet is talál az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->
Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja. Az [Intune-támogatási blogon](https://aka.ms/compportalats) naprakész információkat közlünk.



## <a name="see-also"></a>Lásd még:
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/cloud-platform/roadmap)
* [A Céges portál felhasználói felületének újdonságai](whats-new-app-ui.md)
* [Korábbi hónapok újdonságai](whats-new-archive.md)

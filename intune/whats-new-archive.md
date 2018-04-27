---
title: A Microsoft Intune újdonságai a korábbi hónapokból – Azure | Microsoft Docs
titlesuffix: ''
description: Az Intune újdonságai oldalán korábban megjelenő információkat olvashatja
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f6e44c083e08e4b4d34e6f8f60365e0511fa148
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>A Microsoft Intune újdonságai – korábbi hónapok

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="october-2017"></a>2017. október

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Az üzletági iOS- és Android-alkalmazás verziószáma látható <!-- 1380712 -->

Az Intune alkalmazásai mostantól megjelenítik az üzletági iOS- és Android-alkalmazások verziószámait. A számok az Azure Portal alkalmazáslistáján, valamint az Alkalmazás áttekintése panelen jelennek meg. A végfelhasználók az alkalmazásszámot a céges portál alkalmazásban és a webportálon tekinthetik meg.

__Teljes verziószám:__ A teljes verziószám azonosítja az alkalmazás egy konkrét verzióját. A szám az alábbi formátumban jelenik meg: _Verzió_(_Build_). Például: 2.2(2.2.17560800)

A teljes verziószám két részből áll:

 - **Verzió**  
   A verziószám az alkalmazás természetes nyelven olvasható kiadási száma. A végfelhasználók ezzel azonosítják az alkalmazás különböző kiadásait.

 - **Buildszám**  
    A buildszám egy olyan belső szám, amelyet alkalmazásdetektáláshoz és az alkalmazások szoftveres felügyeletéhez használnak. A buildszám az alkalmazás olyan iterációira vonatkozik, amely a kód változásaira hivatkozik.

A verziószámokról és az üzletági alkalmazások fejlesztéséről további információt a [Bevezetés a Microsoft Intune App SDK használatába](app-sdk-get-started.md#line-of-business-app-version-numbers) című cikkben találhat.

### <a name="device-and-app-management-integration----677972---"></a>Az eszköz- és alkalmazáskezelés integrációja <!-- 677972 -->   
Mivel az Intune-alapú mobileszköz-kezelés (MDM) és a mobilalkalmazás-kezelés (MAM) most már egyaránt elérhető az Azure Portalról, az Intune elkezdte integrálni az alkalmazás- és az eszközkezelés rendszergazdai felületét. Ez a változás az eszköz- és az alkalmazáskezelés egyszerűsítését szolgálja.

Az MDM és a MAM változásairól az [Intune-ügyfélszolgálat blogjában](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) tájékozódhat.

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Új regisztrálási figyelmeztetések Apple-eszközökhöz <!-- 1471790 -->
A regisztrálás áttekintési oldalán hasznos figyelmeztetések jelennek meg a rendszergazdák számára az Apple-eszközök felügyeletével kapcsolatban. A figyelmeztetések akkor jelennek meg az Áttekintés lapon, amikor az Apple MDM leküldéses értesítései lejárnának vagy már lejártak, amikor a Készülékregisztrációs program lejárna vagy már lejárt, illetve akkor, amikor nem hozzárendelt eszközök vannak a Készülékregisztrációs programban.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Tokencsere támogatása alkalmazáskonfigurációhoz eszközregisztráció nélkül <!-- 1080364 -->

A tokeneket az alkalmazáskonfigurációk dinamikus értékeihez használhatja olyan eszközökön található alkalmazásokhoz, amelyek nincsenek regisztrálva. További információ: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközregisztráció nélkül](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Frissítések a Windows 10-es Céges portál alkalmazáshoz <!--1299474-->
Frissítettük a Windows 10-es Céges portál alkalmazás beállítások oldalát, hogy egységesebbek legyenek a beállítások és a beállításoknál elvégezhető felhasználói műveletek. Az elrendezését is átalakítottuk, hogy jobban igazodjon a többi Windows-alkalmazáséhoz. [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) oldalon talál előtte/utána összehasonlító képeket.

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Végfelhasználóknak szóló információ a Windows 10-es-eszközök megtekinthető adatairól <!--1337920-->
A Windows 10-es Céges portál alkalmazásban található Eszköz részletei képernyőhöz hozzáadtuk a **Tulajdonjog típusa** oldalt. A felhasználók így közvetlenül az Intune végfelhasználói dokumentáció ezen oldaláról tájékozódhatnak az adatvédelemről. Ezt az információt az **About** (Információk) képernyőről is elérhetik.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Felhasználói visszajelzések küldése az androidos Céges portál alkalmazásban <!--1165249-->
Az androidos Céges portál alkalmazás mostantól végfelhasználói visszajelzés küldésére szólít fel. A visszajelzés közvetlenül a Microsofthoz érkezik, és lehetőséget nyújt a végfelhasználók számára, hogy értékelhessék az alkalmazást a nyilvános Google Play Áruházban. A visszajelzés küldése nem kötelező, és a felhasználók könnyen bezárhatják a felszólítást, hogy folytathassák a munkát az alkalmazásban.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Segítségnyújtás a felhasználóknak az Androidhoz készült céges portál alkalmazás használatában <!-- 1573324, 1573150, 1558616, 1564878 -->

Az Androidhoz készült Céges portál alkalmazás olyan utasításokkal bővült, amelyekkel a végfelhasználók könnyebben megérthetik, és – ahol lehetséges – egyedül megoldhatják az új használati eseteket.
- A végfelhasználókat az alkalmazás az [Azure Active Directory Portalra](https://account.activedirectory.windowsazure.com/r/#/profile) irányítja, ahol eltávolíthatják az eszközöket, ha elérték a maximálisan hozzáadható eszközök számát.
- A végfelhasználók ekkor utasításokat kapnak, amelyekkel [kijavíthatják az aktiválási hibákat a Samsung Knox-eszközökön](https://go.microsoft.com/fwlink/?linkid=859718), vagy [kikapcsolhatják az energiatakarékos üzemmódot](/intune-user-help/power-saving-mode-android). Ha a megoldások egyike sem oldja meg a problémát, segítséget nyújtunk a [naplófájlok a Microsoftnak való küldéséhez](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Új „Feloldás” művelet az Android-eszközök számára <!-- 1583480 -->

Az Androidhoz készült céges portál alkalmazás egy új „Feloldás” műveletet vezet be az _Eszközbeállítások frissítése_ lapon. A beállítás kiválasztásával a végfelhasználó közvetlenül ahhoz a beállításhoz kerül, amely az eszköz nem megfelelőségét okozza. Az Androidhoz készült céges portál alkalmazás ezt a műveletet jelenleg az [eszköz PIN-kódja](/intune-user-help/set-your-pin-or-password-android), [az USB-hibakeresés](/intune-user-help/you-need-to-turn-off-usb-debugging-android) és az [Ismeretlen források](/intune-user-help/you-need-to-turn-off-unknown-sources-android) beállításokhoz támogatja.

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Eszköztelepítési állapotjelző az androidos Céges portálhoz <!-- 1565657 -->
Az androidos Céges portál alkalmazás egy telepítési állapotjelzőt jelenít meg a felhasználó számára az eszközregisztráció során. Az állapotjelző a következő új állapotokat jeleníti meg: „Az eszköz beállítása...”, ezután „Az eszköz regisztrálása...”, majd „Az eszköz regisztrációjának befejezése...”, végül „Az eszköz beállításának befejezése...”.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Támogatás tanúsítványalapú hitelesítéshez az iOS-es céges portálon <!--1029830-->
Mostantól támogatjuk a tanúsítványalapú hitelesítést (CBA) az iOS-es céges portál alkalmazásban. A CBA-hitelesítést használó felhasználóknak meg kell adniuk a felhasználónevüket, majd a „Bejelentkezés tanúsítvánnyal” hivatkozásra kell koppintaniuk. A CBA már eddig is támogatva volt az androidos és a windowsos céges portál alkalmazásban. További információt a [Bejelentkezés a céges portál alkalmazásba](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) oldalon talál.

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>A regisztrációval vagy anélkül is elérhető alkalmazások mostantól anélkül telepíthetőek, hogy a rendszer a regisztrálást kérné. <!-- 1334712 -->

Azok a céges alkalmazások, amelyek regisztrációval és anélkül is elérhetőek az Androidhoz készült Céges portál alkalmazásban, mostantól anélkül is telepíthetők, hogy a rendszer regisztrációt kérne.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>A Windows AutoPilot üzembe helyezési program támogatása a Microsoft Intune-ban <!-- 747617  -->
Mostantól használhatja az Intune-nal a Windows AutoPilot üzembe helyezési programot, amellyel lehetővé teheti, hogy a felhasználók az informatikai szolgálat közreműködése nélkül helyezzék üzembe vállalati eszközeiket. A kezdőélményt (OOBE) testre szabhatja, és útmutatást nyújthat a felhasználóknak ahhoz, hogy eszközeiket az Azure AD-hez csatlakoztassák, és azokta az Intune-ban regisztrálják. A Microsoft Intune és a Windows AutoPilot együttes használatával kiküszöbölhető az operációsrendszer-lemezképek üzembe helyezésének, fenntartásának és kezelésének feladatai. További részletekért lásd: [Windows-eszközök regisztrálása a Windows AutoPilot Deployment Program használatával](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="quick-start-for-device-enrollment-----1425655---"></a>Gyors üzembe helyezési útmutató az eszközregisztráláshoz <!-- 1425655 --> 
Az **Eszközregisztrálásnál** már elérhető a gyors üzembe helyezési útmutató, amelyben a platformkezeléssel és a regisztrációs folyamat konfigurálásával kapcsolatos információs táblázatot talál. Minden tételhez egy rövid leírás tartozik, valamint hivatkozások olyan forrásokra, amelyek lépésenkénti útmutatót és dokumentációt tartalmaznak, és amelyekkel leegyszerűsíthető a folyamat.

### <a name="device-categorization----1427491---"></a>Eszközök kategorizálása <!-- 1427491 -->
Az **Eszközök > Áttekintés** panelen található regisztrált eszközök platformdiagramja platformok szerint (Android, iOS, macOS, Windows és Windows Mobile) rendezi az eszközöket.  A másféle operációs rendszert futtató eszközök az „Egyéb” kategóriában találhatóak.  Ilyenek lehetnek például a Blackberry, a Nokia és más gyártók eszközei.  

A bérlőhöz tartozó érintett eszközök megtekintéséhez válassza a **Kezelés > Minden eszköz** elemet, majd használja a **Szűrőt** az **Operációs rendszer** mezőre.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Új mobileszköz-védelmi partner   <!-- 954681 -->  
A Microsoft Intune-nal integrálható, Zimperium által irányított, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

#### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció
A kockázatfelmérés a Zimperiumot futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Zimperium által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, amelyekkel az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>A Windows 10-es eszközkorlátozási profil új beállításai <!--- 978575, 1308849, -->  
A Windows Defender SmartScreen kategóriában új beállításokat adunk a Windows 10-es eszközkorlátozási profilhoz.

A Windows 10-es eszközkorlátozási profillal kapcsolatban lásd: [Windows 10-es és újabb eszközkorlátozási beállítások]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Távoli támogatás Windows és Windows Mobile rendszerű eszközökhöz <!-- 1070473 -->  
Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani a Windows és Windows Mobile rendszerű eszközök felhasználóinak.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Eszközök vizsgálata Windows Defenderrel <!-- 1280988  1280990   -->
Windows 10 rendszerű felügyelt eszközökön a Windows Defender víruskereső használható **gyorsvizsgálat** és **teljes vizsgálat** futtatására, valamint **aláírások frissítésére**. Az eszköz áttekintő paneljén válassza ki az eszközön futtatni kívánt műveletet. A rendszer megerősítést fog kérni, mielőtt a parancsot lefuttatná az eszközön. 

**Gyorsvizsgálat**: A gyorsvizsgálat azokat a helyeket vizsgálja meg, ahol a kártevő általában indításhoz lehet regisztrálva, például a beállításkulcsok és az ismert indítási Windows-mappák. A gyorsvizsgálat átlagosan öt percig tart. Az **Állandó valós idejű védelem** a fájlok megnyitásakor, bezárásakor és a mappa megjelenítésekor megvizsgálja a fájlokat. Ez a beállítás a gyorsvizsgálattal együtt segít kiszűrni azokat a kártevőket, amelyek akár a rendszert, akár a kernelt fertőzték meg. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Teljes vizsgálat**: Teljes vizsgálatot olyan eszközökön célszerű futtatni, amelyeken korábban kártevő-fenyegetést találtak, hogy feltárhatóak legyenek a kártevő esetleges inaktív komponensei mélyebb tisztítás érdekében, továbbá igény szerinti vizsgálatra is használható. A teljes vizsgálat körülbelül egy órát vehet igénybe. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Aláírások frissítése**: Az aláírások frissítése parancs frissíti a Windows Defender víruskereső kártevő-definícióit és aláírásait. Ezzel biztosítható, hogy a Windows Defender víruskereső hatékonyan észlelhesse a kártevőket. Ez a funkció csak a Windows 10 rendszert futtató eszközökön érhető el, és internetkapcsolat szükséges hozzá. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Az Azure-beli Intune-portál Intune-os hitelesítésszolgáltató oldaláról eltávolítottuk az Engedélyezés/Letiltás gombot <!-- 1400455 -->
 Az Intune-beli tanúsítvány-összekötő beállításánál egy lépést szükségtelenné teszünk. Jelenleg először le kell tölteni a tanúsítvány-összekötőt, és ezután engedélyezni kell azt az Intune-konzolon. Ha azonban letiltja az összekötőt az Intune-konzolon, az összekötő továbbra is kibocsát tanúsítványokat.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Októbertől az Engedélyezés/Letiltás gomb nem jelenik meg többé az Azure Portal Hitelesítésszolgáltató lapján. Az összekötő funkció továbbra is változatlan marad. Az Intune-ban regisztrált eszközökhöz továbbra is üzembe lesznek helyezve a tanúsítványok. A tanúsítvány-összekötőt továbbra is le lehet tölteni, és telepíteni is lehet. A tanúsítványok kibocsátásának leállítását azonban most már nem a tanúsítvány-összekötő letiltásával, hanem annak telepítésével lehet elérni.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha jelenleg letiltott állapotban van a tanúsítvány-összekötője, akkor azt el kell távolítania.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Új beállítások a Windows 10 Team eszközkorlátozási profiljához <!--- 1308838 -->
Az új kiadásban számos új beállítási lehetőséget tettünk elérhetővé a Windows 10 Team eszközkorlátozási profiljához, hogy hatékonyabban lehessen vezérelni a Surface Hub-eszközöket.

A profilról további információt a [Windows 10 Team eszközkorlátozási beállításai](device-restrictions-windows-10-teams.md) című témakörben talál.

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Annak megakadályozása, hogy a felhasználók megváltoztassák az eszköz rendszeridejét <!-- 1333292 -->
Egy [Androidos egyéni eszközszabályzat](custom-settings-android.md) használatával megakadályozható, hogy a felhasználó megváltoztassa az Android-eszköz rendszeridejét.

Ehhez hozzon létre egy egyéni Android-szabályzatot ezzel az URI-val: ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Állítsa **TRUE** (igaz) értékre, majd rendelje hozzá a kívánt csoportokhoz.

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker-eszközkonfiguráció <!-- 1397398 -->
A **Windowsos titkosítás > Alapbeállítások** területen elérhetővé a **Figyelmeztetés más lemeztitkosítás esetén** beállítás is, amellyel letilthatja azt a [figyelmeztetést](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption), amely akkor jelenik meg, ha az eszközön más lemeztitkosítás is használatban van.  A figyelmeztetés a végfelhasználó hozzájárulását kéri a BitLocker eszközön való beállításához, és a hozzájárulásig letiltja a BitLocker telepítését.  Az új beállítással letiltható a végfelhasználó számára megjelenő figyelmeztetés.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>A Volume Purchase Program for Business-alkalmazások mostantól szinkronizálva lesznek az Intune-bérlővel <!-- 800882 -->  
Az iTunes Connectben megadott, megfelelő jogosultságokkal rendelkező Volume Purchase Program (VPP) for Business-tagoknak külsős fejlesztők is terjeszthetik alkalmazásaikat. Ezek a VPP for Business-tagok be tudnak jelentkezni a Volume Purchase Program App Store áruházba, és ott meg tudják venni azokat az alkalmazásokat, amelyekre szükségük van.

Ebben a kiadásban a végfelhasználók által a VPP for Business keretében megvásárolt alkalmazások Intune-bérlőikkel szinkronizálják magukat.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Apple-áruház országának kiválasztása VPP-alkalmazások szinkronizálásához <!-- 1332311 -->  
VPP-token feltöltésénél lehetőség van a Mennyiségi vásárlási program (VPP) országának konfigurálására. Az Intune a megadott VPP-ország áruházából az összes területi beállításhoz tartozó VPP-alkalmazást szinkronizálja.

> [!NOTE]  
> Az Intune jelenleg egy adott VPP-ország áruházából csak azokat a VPP-alkalmazásokat szinkronizálja, amelyek megfelelnek annak a területi Intune-beállításnak, amelyben az Intune-bérlőt létrehozták.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>A munkahelyi és a személyes profilok közötti másolás és beillesztés letiltása Android for Work-eszközökön <!-- 1098994 -->
Ebben a kiadásban lehetséges úgy konfigurálni az Android for Work-profilt, hogy az letiltsa a munkahelyi és személyes fiókok közötti másolást és beillesztést. Az új beállítás a **Munkahelyi profil beállításai** között, az **Android for Work** platform **Eszközkorlátozások** területén található.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Regionális Apple App Store-ra korlátozott iOS-alkalmazások létrehozása <!-- 1281692 -->
Az Apple App Store által felügyelt alkalmazás létrehozásánál területi beállításként lehetőség lesz meghatározni az országot.

> [!Note]  
> Jelenleg csak olyan Apple App Store által felügyelt alkalmazásokat lehet létrehozni, amelyek az USA-beli áruházban érhetőek el.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS-es VPP-alkalmazások felhasználókhoz és eszközökhöz rendelt licenceinek frissítése <!-- 1305564 -->  
Az iOS-es VPP-token úgy is konfigurálható, hogy frissítse az összes olyan alkalmazást, amelyet az adott tokenhez vásároltak az Intune szolgáltatáson keresztül. Az Intune észlelni fogja, ha az adott VPP-alkalmazáshoz frissítés érhető el az alkalmazás-áruházban, és ezt követően automatikusan leküldi a frissítéseket az eszközre, amikor az legközelebb bejelentkezik.

A VPP-token beállításáról és az automatikus frissítésekről lásd: [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Felhasználók és eszközök társítási entitásgyűjteménye jelenik meg az Intune-adattárház adatmodelljében <!-- 1187917 -->
A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre. Az adatmodell a Power BI-fájlon (PBIX) keresztül érhető el az adattárház Intune-oldaláról az OData-végpont használatával vagy egyéni ügyfél létrehozásával.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Szabályzatmegfelelőség ellenőrzése Windows 10-es frissítési körökhöz <!-- 1067886 -->
A Windows 10-es frissítési körök szabályzatjelentéseit meg lehet majd tekinteni a Szoftverfrissítések > Frissítési körök telepítési állapota szerint területen. A szabályzatjelentés tartalmazza a konfigurált frissítési körök telepítési állapotát. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Új jelentés a régebbi iOS-verziójú iOS-eszközök listájával   <!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** munkaterületről lehet elérni. A jelentésben megtekintheti az iOS frissítési szabályzatok által megcélzott és elérhető frissítésekkel rendelkező felügyelt iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Alkalmazásvédelmi szabályzat-hozzárendelések megtekintése hibakereséshez <!--  1475003 -->
A következő kiadásban megjelenik az **Alkalmazásvédelmi szabályzat** lehetőség is a hibakeresési panelen elérhető **Hozzárendelések** legördülő listában. Az alkalmazásvédelmi szabályzatok lehetőség kiválasztásával megtekintheti a kiválasztott felhasználókhoz hozzárendelt alkalmazásvédelmi szabályzatokat.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>A Céges portál eszközbeállítási munkafolyamatával kapcsolatos újdonságok <!--1490692-->
Továbbfejlesztettük az androidos Céges portál alkalmazás eszközbeállítási munkafolyamatát. Nyelvezete felhasználóbarátabb, vállalatra szabottabb. Képernyőit – ahol lehetett – összevontuk. Az újításokat megtekintheti a [ felhasználói felület újdonságait](whats-new-app-ui.md#week-of-october-2-2017) bemutató oldalon.

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Az androidos eszközök kapcsolati információk elérésére irányuló kéréseinek továbbfejlesztett támogatása <!--1484985-->

Gyakran előfordul, hogy a felhasználóknak engedélyt kell adniuk az androidos Céges portál alkalmazásnak a Kapcsolatok használatára. Ha ezt egy végfelhasználó elutasítja, mostantól egy alkalmazásbeli értesítés fogja figyelmeztetni feltételes hozzáférési engedély megadására. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Biztonságos indítást támogató kockázatcsökkentés Android-eszközökhöz<!--1490712-->

Az Android-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>További leküldéses értesítések az Android Oreo rendszert használó végfelhasználóknak a Céges portál alkalmazásban <!--1475932-->

A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy az Android Oreo Céges portál alkalmazása mikor végez háttérműveleteket (például szabályzatok lekérése az Intune szolgáltatástól). Ez átláthatóbbá teszi a végfelhasználók számára a Céges portál az eszközeiken végzett felügyeleti feladatait. Ez a [Céges portál felhasználói felülete optimalizálásának](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) része, amelyet az Android Oreo rendszeren futó Céges portál alkalmazáshoz végzünk. 

Az Android Oreóban engedélyezett új felhasználóifelület-elemekhez további optimalizálások tartoznak.  A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy a Céges portál mikor végez háttérműveleteket, például szabályzatok lekérését az Intune szolgáltatástól.  Ez átláthatóbbá teszi a végfelhasználók számára, hogy a Céges portál mikor hajt végre felügyeleti feladatokat az eszközön.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Munkahelyi profillal rendelkező Androidhoz készült Céges portál alkalmazás új működési módja <!-- 1485783 -->

Android for Work-eszköz munkahelyi profillal történő regisztrálása után a munkahelyi profil Céges portál alkalmazása végzi el az eszközön a felügyeleti feladatokat. 

Hacsak nem használ MAM-használatot támogató alkalmazást a személyes profilban, az androidos Céges portál alkalmazásra már nincs szükség. Ezért a munkahelyi profil hatékony használhatósága érdekében a munkahelyi profil sikeres regisztrálása után az Intune elrejti a személyes Céges portál alkalmazást.

Az Androidhoz készült Céges portál alkalmazás a személyes profilban bármikor engedélyezhető. Ehhez keresse meg a [Céges portál alkalmazást a Play Áruházban](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal), és koppintson az **Engedélyezés** lehetőségre.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>A Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál fenntartási módba kerül <!--1428681-->

2017 októberétől a Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál alkalmazás fenntartási módba kerül. Ez azt jelenti, hogy ezeken a platformokon továbbra is jár támogatás az alkalmazásokhoz és a meglévő használati forgatókönyvekhez (például regisztrálás és megfelelőség). Az alkalmazások továbbra is letölthetők a meglévő kiadási csatornákon keresztül, például a Microsoft Áruházból. 

A fenntartási módban ezekhez az alkalmazásokhoz azonban már csak fontos biztonsági frissítések lesznek elérhetőek. Más típusú frissítések és új funkciók már nem jelennek meg ezekhez az alkalmazásokhoz. Ha az új funkciókat szeretné használni, azt javasoljuk, hogy frissítse az eszközt Windows 10 vagy Windows 10 Mobile rendszerre. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Nem támogatott Samsung Knox-eszközök regisztrációjának letiltása<!-- 1490695 -->

A Céges portál alkalmazás csak a támogatott Samsung Knox-eszközöket próbálja meg regisztrálni. Az MDM-regisztrációt megakadályozó Knox-aktiválási hibák elkerülése érdekében az alkalmazás csak a [Samsung által közzétett eszközlistán](https://www.samsungknox.com/knox-supported-devices/knox-workspace) szereplő eszközöket próbálja meg regisztrálni. Előfordulhat, hogy egy Samsung-eszköz bizonyos modelljei támogatják a Knox platformot, míg más modelljei nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse a viszonteladóval, hogy az eszköz Knox-kompatibilis-e. Az ellenőrzött eszközök teljes listáját megtalálhatja az [Android- és Samsung Knox Standard-eszközök konfigurációs szabályzatának beállításai](/intune/supported-devices-browsers.md#intune-supported-web-browsers) című témakörben.

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!-- 1171126, 1326920 -->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Decemberre az összes regisztrált eszköz ki lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Végfelhasználók tájékoztatása a regisztrált eszközök megtekinthető adatairól <!--1165314-->
A Céges portál alkalmazások Eszköz részletei képernyője kiegészül a **Tulajdonjog típusa** oldallal. Így a felhasználók közvetlenül a [Milyen adatok láthatók a cég számára?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) című cikkből fognak tudni tájékozódni az adatvédelmi kérdésekről. Ez terveink szerint az összes Céges portál alkalmazásban meg fog jelenni a közeljövőben. Az iOS kapcsán ezt a funkciót [szeptemberben](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) jelentettük be.

## <a name="september-2017"></a>2017. szeptember

### <a name="intune-supports-ios-11---1428975--"></a>Az Intune támogatja az iOS 11-et<!--1428975-->
Az Intune támogatja az iOS 11-et. Ezt korábban bejelentettük az [Intune támogatási blogjának](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) oldalán.

### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!-- 1164477 -->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>A Windows 10-es Céges portál alkalmazásban elérhetővé válik a Frissítés művelet <!--1132468-->
A Windows 10-es céges portál alkalmazásban lehetőség lesz az adatok frissítésére. Ezt lefelé húzással, vagy asztali gépeken az F5 billentyű megnyomásával lehet majd elvégezni.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Végfelhasználóknak szóló információ az iOS-eszközök megtekinthető adatairól <!--739894-->

Az iOS-alapú Céges portál alkalmazásban található Eszköz részletei képernyőhöz hozzáadtuk a **Tulajdonjog típusa** oldalt. A felhasználók így közvetlenül az Intune végfelhasználói dokumentáció ezen oldaláról tájékozódhatnak az adatvédelemről. A tudnivalókat az About (Információk) képernyőről is elérhetik.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Az Android rendszerre készült Céges portál alkalmazás regisztráció nélküli elérésének engedélyezése végfelhasználók számára <!---1169910--->

A végfelhasználóknak rövidesen mát nem kell regisztrálniuk az eszközüket az Android rendszerre készült Céges portál alkalmazás eléréséhez. Az alkalmazásvédelmi szabályzatokat használó szervezetek végfelhasználói többé nem fognak az eszközük regisztrálására felszólító figyelmeztetést kapni a Céges portál alkalmazás megnyitásakor. A végfelhasználók alkalmazásokat is tudnak majd telepíteni a Céges portálról az eszköz regisztrálása nélkül. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Egyszerűbb megfogalmazás az Androidhoz készült Céges portál alkalmazáshoz <!---1396349--->  

Egyszerűsítettük az Androidhoz készült Céges portál alkalmazás regisztrálási folyamatának leírását, hogy a végfelhasználók könnyebben tudják elvégezni a regisztrálást. Ha egyéni regisztrációs dokumentációval rendelkezik, frissítse az új képernyők megjelenítéséhez. Mintaképeket a [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-app-ui.md#week-of-september-11-2017) című oldalon találhat.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>A Windows Information Protection engedélyezési szabályzata a Windows 10-es Céges portál alkalmazással bővül <!-- 677129 -->

Frissítettük a Windows 10-es Céges portál alkalmazást, amely így támogatja a Windows Információvédelmet. Az alkalmazást hozzá lehet adni a WIP engedélyezési szabályzatához. A változásnak köszönhetően az alkalmazást a későbbiekben nem szükséges hozzáadni a **Kivételek** listához.


## <a name="august-2017"></a>2017. augusztus

### <a name="improvements-to-device-overview----1404453---"></a>Fejlesztések az eszközök áttekintésénél <!-- 1404453 -->  
A fejlesztéseknek köszönhetően az eszközök áttekintésében mostantól megjelennek a regisztrált eszközök, az Exchange ActiveSync által kezeltek viszont ki lesznek hagyva. Az Exchange ActiveSync által kezelt eszközök a regisztrált eszközökéitől eltérő felügyeleti beállításokkal rendelkeznek. A regisztrált eszközök számát összesítve és platform szerinti lebontásban is megtekintheti az Intune-ban az Azure Portal **Eszközök** > **Áttekintés** menüpontjában.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Az Intune által gyűjtött eszközleltár fejlesztései
<!-- 961134, 1104426, 1281327, 1333543 -->
Ebben a kiadásban a következő fejlesztések lettek végrehajtva a kezelt eszközök által gyűjtött leltáradatokkal kapcsolatban:
 
-   Mostantól Android-eszközök esetében hozzá lehet adni egy legutóbbi javítási szintet megjelenítő oszlopot az eszközleltárhoz. Ennek megtekintéséhez adja a **Security patch level** (Biztonsági javítási szint) oszlopot az eszközlistához.
-   Az eszközök szűrésénél most már az eszköz regisztrációjának dátuma alapján is szűrhet. Például megadhatja, hogy csak azok az eszközök jelenjenek meg, melyeket egy adott dátum után regisztráltak.
-   Fejlesztéseket hajtottunk végre a **Last Check-in Date** (Utolsó beadás dátuma) szűrőjén.
-   Az eszközlistában most már megjelenítheti a céges eszközök telefonszámát.
Továbbá, a szűrőablakban mostantól már telefonszám alapján is kereshet az eszközök között.
 
További információt az eszközleltárral kapcsolatban [Az Intune-eszközleltár megtekintése](device-inventory.md) című cikkben talál.

### <a name="conditional-access-support-for-macos-devices"></a>Feltételes hozzáférés támogatása macOS-eszközöknél 
<!-- 720172 -->
Mostantól beállítható a Mac-eszközök Intune-ba való regisztrálását és az eszközmegfelelőségi szabályzatoknak való megfelelését megkövetelő feltételes hozzáférési szabályzat. A felhasználók megtehetik például, hogy letöltik a macOS-re készült Intune Céges portál alkalmazást és regisztrálják Mac-eszközeiket az Intune-ba. Az Intune kiértékeli, hogy a Mac-eszköz eleget tesz vagy sem többek között a PIN-kódra, a titkosításra, az operációs rendszer verziójára és a rendszerintegritásra vonatkozó követelményeknek.

- További információ a [feltételes hozzáférés támogatásáról macOS-eszközöknél](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Nyilvános előzetes verzióban elérhető a macOS-hez készült Céges portál alkalmazás <!---1484796--->
Az Enterprise Mobility + Security-beli feltételes hozzáférés nyilvános előzetesének részeként előzetes verzióban elérhető a macOS-es Céges portál alkalmazás. Ez a kiadás a macOS 10.11-es és későbbi verzióit támogatja. Letöltés: [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Új Windows 10-es eszközkorlátozási beállítások    
<!--1063965, 1308850  -->
Ebben a kiadásban új beállítási lehetőségekkel bővült a [Windows 10-es eszközkorlátozási profil](/intune/device-restrictions-windows-10), a következő kategóriákban:

-   Windows Defender SmartScreen
-   Alkalmazás-áruház

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>A Windows 10-es Endpoint Protection-eszközprofil BitLocker-beállításainak frissítései
<!--1459533 -->    
Ebben a kiadásban a következő fejlesztéseket hajtottuk végre a Windows 10-es Endpoint Protection-eszközprofil BitLocker-beállításainak működésében:
 
Az **Operációsrendszer-meghajtók BitLocker-beállításaiban** a **BitLocker nem kompatibilis TPM-lapkával** beállításánál a **Letiltás** lehetőség választása korábban tévesen a BitLocker engedélyezését eredményezte. Javítottuk a beállítást, így kiválasztás esetén most már letiltja a BitLockert.
Az **Operációsrendszer-meghajtók BitLocker-beállításaiban** a **Tanúsítványalapú adat-helyreállítási ügynök** beállításnál mostantól letilthatja a tanúsítványalapú adat-helyreállítási ügynököt. Az ügynök ugyanakkor alapértelmezés szerint engedélyezve van.
A **Rögzített adatmeghajtók BitLocker-beállításai** között az **Adat-helyreállítási ügynök** beállításnál mostantól letilthatja az adat-helyreállítási ügynököt.
További információ: [Endpoint Protection-beállítások Windows 10 és újabb rendszerű eszközökön](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Új lehetőségek az Androidhoz készült Céges portál és az alkalmazásvédelmi szabályzat bejelentkezett felhasználóinak <!-- 621669 -->
A végfelhasználók az Androidhoz készült Céges portál használatával most már az Android rendszerű eszköz regisztrációja nélkül is böngészhetnek az alkalmazások között, felügyelhetnek eszközöket, valamint megtekinthetik az informatikai részleg elérhetőségeit. Ezenkívül ha egy végfelhasználó már egy, az Intune alkalmazásvédelmi szabályzata által védett alkalmazást használ, és elindítja az Androidhoz készült Céges portált, már nem kap felszólítást az eszköz regisztrációjára.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Új beállítás az akkumulátor-optimalizálás ki- és bekapcsolásához az Androidhoz készült Céges portál alkalmazásban<!--1405990-->
Az Androidhoz készült Céges portál alkalmazás **Beállítások** oldala új beállítással bővült, amellyel a felhasználók könnyen kikapcsolhatják az akkumulátor-optimalizálást a Céges portál és a Microsoft Authenticator alkalmazásokhoz. A beállításon látható alkalmazásnév attól függően változik, hogy melyik alkalmazás kezeli a munkahelyi fiókot. Az e-mailek és adatok szinkronizálását végző munkahelyi alkalmazások teljesítménynövelése érdekében az akkumulátor-optimalizálás kikapcsolását javasoljuk. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Többszörös identitás támogatása az iOS-hez készült OneNote-ban      <!-- 1234281 -->
A felhasználók mostantól több fiókot (munkahelyit és személyeset) is használhatnak az iOS-hez készült Microsoft OneNote-ban. Anélkül alkalmazhatók alkalmazásvédelmi szabályzatok a munkahelyi jegyzetfüzetekben található céges adatokra, hogy ez hatással lenne a személyes jegyzetfüzetekre. A szabályzat azt például lehetővé teszi, hogy a felhasználó adatokat kereshessen a céges jegyzetfüzetekben, azt viszont megakadályozza, hogy azokat kimásolja onnan, és beillessze egy személyes jegyzetfüzetbe.
 
- További információ azon alkalmazásokról, amelyek támogatják az [alkalmazásvédelmet és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Új beállítások alkalmazások engedélyezéséhez és letiltásához Samsung Knox Standard-eszközökön
<!-- 1305423 822899-->  
Ebben a kiadásban új [eszközkorlátozási beállítások](device-restrictions-android.md) jelennek meg, amelyekkel megadhatók a következő alkalmazáslisták:
 
- Felhasználók által telepíthető alkalmazások
- Felhasználók által nem futtatható alkalmazások
- Az eszközön a felhasználó elől rejtett alkalmazások
 
Az alkalmazás megadható URL-cím vagy csomagnév alapján, vagy kiválasztható a felügyelt alkalmazások listájából.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Hivatkozás az új Azure AD alkalmazásalapú feltételes hozzáférési szabályzat felhasználói felületére az Intune-ból
<!-- 1016201 -->
Az Azure AD tevékenységprofiljában található új feltételes hozzáférési szabályzat felhasználói felületéről a rendszergazdák alkalmazásalapú feltételes szabályzatokat állíthatnak be. Az Azure Intune App Protection szakasz alkalmazásalapú feltételes hozzáférése egyelőre a helyén marad, és a kikényszerítése párhuzamosan zajlik le. Ezekhez adódik hozzá az a kényelmi hivatkozás, amely az Intune tevékenységprofilban található új feltételes hozzáférési szabályzat felhasználói felületére mutat.

- További tudnivalók az [Azure AD-beli alkalmazásalapú feltételes hozzáférésről](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>2017. július

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android- és iOS-eszköz regisztrálásának korlátozása operációsrendszer-verzió alapján <!--- 1333256,  1245463 --->
Az Intune támogatja az iOS- és Android-eszközök regisztrálásának operációsrendszer-verziószám alapján történő korlátozását. Az **Eszköztípuskorlát** szakaszban az adminisztrátor a platformkonfiguráció megadásával korlátozhatja a regisztrálást egy minimális és maximális operációsrendszer-verziószám között. Az Android operációsrendszer-verzióit főverzió.alverzió.build.javítás formában kell megadni, ahol az alverzió, a build és a javítás megadása nem kötelező. Az iOS-verziókat főverzió.alverzió.build formában kell megadni, ahol az alverzió és a build megadása nem kötelező. További információ [az eszköz regisztrációs korlátozásokról](enrollment-restrictions-set.md).

>[!NOTE]
>Nem korlátozza az Apple készülékregisztrációs programok vagy az Apple Configuratoron keresztül végzett regisztrációt.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Személyes tulajdonban lévő Android, iOS és macOS rendszerű eszközök regisztrálásának korlátozása  <!--- 1333272,  1333275, 1245709 --->
Az Intune korlátozhatja a személyes eszközök regisztrációját a céges eszközök IMEI-számait tartalmazó engedélyezési lista alapján. Ez a szolgáltatás most már iOS, Android, és macOS rendszereken is elérhető az Intune-ban az eszközök sorozatszámainak használatával. A sorozatszámot az Intune-ba feltöltve előre bejelenthető, hogy az eszköz vállalati tulajdonban van. A regisztrációs korlátozásokkal letilthatók a személyes tulajdonban lévő (BYOD) eszközök, így csak vállalati tulajdonú eszközök regisztrációja lesz engedélyezett. További információ [az eszköz regisztrációs korlátozásokról](enrollment-restrictions-set.md).

Sorozatszámok úgy tölthetők fel, hogy az **Eszközregisztráció** > **Céges készülékazonosítók** szakaszban a **Hozzáadás** gombra kattint, majd feltölt egy .CSV fájlt (fejléc nélkül, két oszloppal a sorozatszámoknak és más részleteknek, például az IMEI-számoknak).  A személyes tulajdonban lévő eszközök letiltásához válassza az **Eszközregisztráció** > **Regisztrációs korlátozások** lehetőséget. Az **Eszköztípus-korlátozások** szakaszban válassza az **Alapértelmezés** majd a **Platformkonfigurációk** lehetőséget. **Engedélyezheti** vagy **Tilthatja** a személyes tulajdonban lévő iOS, Android, és macOS rendszerű eszközöket. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Új eszközművelet az eszközök Intune-nal való szinkronizálásának kikényszerítésére <!-- 711369 -->
Ebben a kiadásban új eszközműveletet vezettünk be, amely a választott eszköz azonnali bejelentkezését kényszeríti ki az Intune-nál. Bejelentkezéskor az eszköz azonnal fogadja az hozzárendelt összes függőben lévő műveletet vagy szabályzatot.  Ez a művelet segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.
További információkért lásd: [Eszköz szinkronizálása](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>A legújabb elérhető szoftverfrissítés automatikus telepítésének kikényszerítése felügyelt iOS-eszközöknél <!-- 777100 -->
Új szabályzat érhető el a Szoftverfrissítések munkaterületen, amellyel kikényszeríthető a legújabb elérhető szoftverfrissítés automatikus telepítése a felügyelt iOS-eszközöknél. További információt az [iOS-es frissítési szabályzatok konfigurálása](/intune/software-updates-ios) című cikkben talál.

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – Új mobileszköz-védelmi partner  <!-- 954651, 1172027 -->
A Microsoft Intune-nal integrálható, Skycure nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

#### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció?
A kockázatfelmérés a Checkpoint SandBlast Mobile-t futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Checkpoint SandBlast Mobile által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. Az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Vállalati Microsoft Áruházbeli alkalmazások telepítése elérhető alkalmazásként <!-- 748101 -->
Ettől a kiadástól kezdve a rendszergazdák a Vállalati Microsoft Áruházat is beállíthatják elérhetőként. Ha ez elérhetőként van beállítva, a felhasználók az alkalmazást anélkül telepíthetik a Céges portál alkalmazásból vagy weboldalról, hogy átirányítanák őket a Microsoft Áruházba.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 1-->
A [Céges portál webhely](https://portal.manage.microsoft.com) felhasználói felületén számos frissítést hajtottunk végre a végfelhasználói élmény javítása érdekében.

- __Továbbfejlesztett alkalmazáscsempék__ Az alkalmazásikonok mostantól automatikusan generált háttérrel jelennek meg az ikon meghatározó színe alapján (amennyiben az érzékelhető). Amennyiben alkalmazható a funkció az ikonra, ez a háttér felváltja a szürke kontúrt, amely eddig keretezte az ikonokat az alkalmazáscsempén.

    Egy hamarosan megjelenő kiadástól kezdve a Céges portál webhely a nagyméretű ikonokat fogja megjeleníteni, amennyiben lehetséges. Javasoljuk, hogy a rendszergazdák minimum 120x120 pixeles, nagy felbontású ikonokkal tegyék közzé az alkalmazásokat. 

- __Navigációs változások__ A navigációs sáv elemei a bal felső sarokban látható hamburger menübe kerültek át. A Kategóriák lap el lett távolítva. A felhasználók mostantól böngészés közben szűrhetik kategória szerint a tartalmat.

- __Kiemelt alkalmazások frissítései__ A webhelyhez hozzáadtunk egy új oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszának felhasználói felületén.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>iBooks-támogatás a Céges portál webhelyén <!--1231841-->
Egy dedikált oldalt adtunk hozzá a Céges portál webhelyéhez, ahol a felhasználók böngészhetik és letölthetik az iBooks szolgáltatás e-könyveit. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>További hibaelhárítási adatok a segélyszolgálat számára <!---  Applies to 1263399, 1326964, 1341642 --->
Az Intune-ban frissült a hibaelhárítási adatok megjelenítésének módja, és bővültek a rendszergazdák és segélyszolgálati munkatársak számára biztosított információk. Az új verzióban egy **Hozzárendelések** nevű táblázat foglalja össze a felhasználó összes, csoporttagságok alapján meglévő hozzárendelését. A lista a következőket tartalmazza:
- Mobilalkalmazásokban
- Megfelelőségi szabályzatok
- Konfigurációs profilok
 
Ezenkívül az **Eszközök** táblázat kiegészült az **Azure AD-csatlakozás típusa** és az **Azure AD-kompatibilis** oszloppal. További információt a [Segítség a felhasználóknak a problémák elhárításában](help-desk-operators.md) című cikkben talál.



### <a name="intune-data-warehouse-public-preview"></a>Intune-adattárház (nyilvános előzetes verzió)
Az Intune-adattárház napi adatgyűjtéssel dokumentálja a bérlő állapotelőzményeit. Az adatokat egy Power BI-fájl (PBIX), egy sok elemzőeszközzel kompatibilis OData-hivatkozás, vagy a REST API használatával is elérheti. További információt [Az Intune-adattárház használata](reports-nav-create-intune-reports.md) című témakörben talál.


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Világos és sötét üzemmód választható a Windows 10 rendszerre készült Céges portál alkalmazáshoz <!---676547--->
A végfelhasználók kiválaszthatják a Windows 10 rendszerre készült Céges portál alkalmazás színhasználatát. Ezt a felhasználó a Céges portál alkalmazás Beállítások szakaszában változtathatja meg. A változás az után jelenik meg, hogy a felhasználó újraindítja az alkalmazást. A Windows 10 1607-es és újabb verziói esetén az alkalmazás alapértelmezés szerint a rendszer beállításait használja. A Windows 10 1511-es és korábbi verziói esetén az alkalmazás alapértelmezés szerint a világos üzemmódot használja.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>A végfelhasználók megjelölhetik saját eszközcsoportjukat a Windows 10 rendszerre készült Céges portál alkalmazásban <!---807046-->
A végfelhasználók mostantól közvetlenül a Windows 10 rendszerhez készült Céges portál alkalmazásban címkézhetik meg az eszközt, hogy kiválasszák, melyik eszközcsoporthoz tartozik.



## <a name="june-2017"></a>2017. június

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Új, szerepköralapú adminisztrációs hozzáférés Intune-rendszergazdáknak <!-- 1099990 -->  
Új, feltételes hozzáférésű rendszergazdai szerepkört vezetünk be az Azure AD feltételes hozzáférési szabályzatainak megtekintéséhez, létrehozásához, módosításához és törléséhez. Korábban csak a globális rendszergazdák és a biztonsági rendszergazdák rendelkeztek ilyen engedéllyel. Mostantól az Intune-rendszergazdák is megkaphatják ezt a szerepköri engedélyt, így ők is hozzáférhetnek a feltételes hozzáférési szabályzatokhoz.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Céges tulajdonú eszközök címkézése sorozatszámmal <!-- 1215070 -->  
Az Intune már támogatja az iOS-, a macOS- és az Android-sorozatszámok feltöltését céges eszközazonosítókként. Jelenleg nem lehet a sorozatszámokat személyes eszközök regisztrálásból való kitiltására használni, mert a rendszer nem ellenőrzi a sorozatszámokat a regisztrálás során. A személyes eszközök sorozatszám alapján történő blokkolása a közeljövőben válik elérhetővé.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Új távoli műveletek iOS-eszközökhöz <!-- 854689 -->
Ebben a kiadásban két új műveletet tettünk elérhetővé az Apple Osztályterem alkalmazást kezelő megosztott iPad-eszközökkel kapcsolatban:

-   [Aktuális felhasználó kijelentkeztetése](device-logout-user.md) – Kijelentkezteti a kiválasztott iOS-eszköz aktuális felhasználóját.
-   [Felhasználó eltávolítása](device-remove-user.md) – Eltávolítja a kiválasztott felhasználót egy iOS-eszköz helyi gyorsítótárából.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>A megosztott iPadek támogatása az iOS-es Osztályterem alkalmazással <!-- 1044681 -->
Ebben a kiadásban kibővült az iOS-es Osztályterem alkalmazás felügyeletének támogatása, így olyan diákok felügyeletére is van lehetőség, akik a megosztott iPadekre saját felügyelt Apple ID-val jelentkeznek be.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Beépített Intune-alkalmazásokkal kapcsolatos változások <!-- 1332306 -->
Korábban az Intune számos beépített alkalmazást tartalmazott, melyeket hamar hozzá lehetett rendelni egy kategóriához. A visszajelzések alapján azonban eltávolítottuk ezt a listát, és többé már nem jelennek meg beépített alkalmazások.
Ugyanakkor ha vannak olyan beépített alkalmazások, melyeket korábban már hozzárendelt valamelyik kategóriához, azok továbbra is meg fognak jelenni az alkalmazások listáján. Ezek az alkalmazások szükség szerint továbbra is hozzárendelhetők.
Terveink szerint egy későbbi kiadásban elérhetővé teszünk majd egy egyszerűbb módszert a beépített alkalmazások Azure Portalról történő kiválasztására és hozzárendelésére.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365-alkalmazások egyszerűbb telepítése <!--- 1121362 --->
Az új **Office 365 ProPlus** alkalmazástípus megkönnyíti Office 365 ProPlus 2016-alkalmazásoknak a felügyelt, a Windows 10 legújabb verzióját futtató eszközökhöz rendelését. Emellett lehetőség nyílik a Microsoft Project és a Microsoft Visio telepítésére is, ha rendelkezik hozzájuk való saját licencekkel. A kívánt alkalmazásokat a rendszer összecsomagolja, és azok egyetlen alkalmazásként jelennek meg az Intune-konzol alkalmazáslistájában.
További információt a [Office 365-alkalmazások hozzáadása Windows 10 esetén](apps-add-office365.md) című témakörben talál.


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>A Vállalati Microsoft Áruházból származó offline alkalmazások támogatása <!--- 777044 --->
A Vállalati Microsoft Áruházban vásárolt offline alkalmazások mostantól szinkronizálhatók az Azure Portallal. Ezeket az alkalmazásokat eszközcsoportok vagy felhasználói csoportok számára telepítheti. Az offline alkalmazásokat az Intune, és nem az Áruház telepíti.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>A Microsoft Teams mostantól szerepel a jóváhagyott alkalmazások alkalmazásalapú feltételes hozzáférési listáján   <!-- 1257019 -->
Az iOS és Android rendszerű Microsoft Teams mostantól az Exchange és a SharePoint Online alkalmazásalapú feltételes szabályzataihoz tartozó jóváhagyott alkalmazások közé tartozik. Az alkalmazás az Intune App Protection panelen keresztül konfigurálható az Azure Portalon a jelenleg alkalmazásalapú feltételes hozzáférést használó összes bérlőre vonatkozóan.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser- (felügyelt böngésző) és alkalmazásproxy-integráció <!-- 1287310 -->
Az Intune Managed Browser integrálható az Azure AD alkalmazásproxy szolgáltatásával így az éppen távolról dolgozó felhasználók is elérhetik a belső webhelyeket. A felhasználók a szokásos módon egyszerűen beírják a hely URL-címét a böngésző címsorába, a Managed Browser pedig átirányítja a kérést az alkalmazásproxy webátjárójára. További információ: [Az internet-hozzáférés kezelése felügyelt böngészőszabályzatokkal](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Új alkalmazáskonfigurációs beállítások az Intune Managed Browser alkalmazáshoz <!-- 682951 -->
Ebben a kiadásban további konfigurációs lehetőségekkel bővült az iOS és Android rendszerű Intune Managed Browser alkalmazás. A böngésző alapértelmezett kezdőlapjának és könyvjelzőinek beállítása alkalmazáskonfigurációs szabályzattal is lehetséges.
További információ: [Az internet-hozzáférés kezelése felügyelt böngészőszabályzatokkal](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>BitLocker-beállítások a Windows 10-hez  <!-- 951707 -->
A Windows 10 rendszerű eszközök BitLocker-beállításai már új Intune-eszközprofillal is konfigurálhatók. Megkövetelheti például az eszközök titkosítását, és megadhat további, a BitLocker bekapcsolásakor alkalmazandó beállításokat is.
További információ: [Endpoint Protection-beállítások Windows 10 és újabb rendszerű eszközökön](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>A Windows 10-es eszközkorlátozási profil új beállításai <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Ebben a kiadásban új beállítási lehetőségekkel bővült a Windows 10-es eszközkorlátozási profil, a következő kategóriákban:

-  Windows Defender
-  Mobilhálózati és egyéb kapcsolatok
-  Zárolási képernyő felülete
-  Személyes adatok védelme
-  Keresés
-  Windows Reflektorfény
-  Microsoft Edge böngésző

További információ a Windows 10 beállításairól: [Windows 10 és újabb rendszerek eszközkorlátozási beállításai](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Az Androidhoz készült Céges portál alkalmazás mostantól új felhasználói felületet nyújt az alkalmazásvédelmi szabályzatokhoz <!--1305217-->
A felhasználók visszajelzései alapján úgy módosítottuk az Androidhoz készült Céges portál alkalmazást, hogy egy **Céges tartalom elérése** gombot is hozzáadtunk. Ez mentesíti a végfelhasználót attól, hogy az egész regisztrációs folyamaton végig kelljen mennie, ha csak olyan alkalmazásokat kíván elérni, amelyek az Intune mobilalkalmazás-felügyelet egyik funkcióját, az alkalmazásvédelmi szabályzatokat támogatják. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Új menüművelet a Céges portál egyszerű eltávolításához <!--1164569-->
Felhasználói visszajelzések alapján az androidos Céges portál alkalmazásban új menüművelet jelent meg, amellyel a Céges portál eszközről való eltávolítása kezdeményezhető. A művelet megszünteti az eszköz Intune-felügyeletét, így a felhasználó az alkalmazást is eltávolíthatja az eszközről. Ezekről a változtatásokról bővebb információt talál az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) és [Az Android végfelhasználói dokumentációja](/intune-user-help/unenroll-your-device-from-intune-android) témakörökben.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>A Windows 10 alkotói frissítésével való alkalmazás-szinkronizálás fejlesztései <!--676505-->
A Windows 10-es Céges portál alkalmazás automatikusan kezdeményez szinkronizálást alkalmazástelepítési kérésekhez Windows 10 alkotói frissítést (1703-as verziót) futtató eszközök esetén. Ez csökkenti a függőben lévő szinkronizálás során feltorlódó alkalmazástelepítési műveletek számát. Emellett a felhasználók manuálisan is kezdeményezhetnek szinkronizálást az alkalmazásban. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Új interaktív felület a Windows 10-es Céges portálhoz<!---1058938--->
A Windows 10-es Céges portál alkalmazás tartalmazni fog egy interaktív Intune-útmutatót a nem azonosított vagy regisztrált eszközökhöz. Az új útmutató olyan részletes utasításokat tartalmaz, amelyek végigvezetik a felhasználókat a feltételes hozzáférési funkciók azonosításához szükséges Azure Active Directory-regisztrálás és az eszközkezelési funkciókhoz szükséges MDM-regisztrálás lépésein. Az útmutató a Céges portál kezdőlapján lesz elérhető. A felhasználók akkor is használhatják az alkalmazást, ha nem végezték el a regisztrálást és a beléptetést, de így korlátozottan használhatják csak a funkciókat.

Ez a frissítés csak a Windows 10 évfordulós frissítést (1607-es) vagy újabb verziókat futtató eszközökön látható. A változásokat áttekintheti az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Általánosan elérhető a Microsoft Intune-konzol és a feltételes hozzáférés rendszergazdai konzolja
Már általánosan elérhető az új Azure Portalbeli Intune rendszergazdai konzolja, valamint a feltételes hozzáférés rendszergazdai konzolja is. Az Azure Portalbeli Intune-nal most már egyetlen és egységes rendszergazdai felületen kezelhető az összes Intune-beli MAM- és MDM-funkció, és mindemellett az Azure AD csoportosítási és célzási képességei is kihasználhatók. Az Azure-beli feltételes hozzáférés az Azure AD és az Intune sokoldalú képességeit teszi elérhetővé egyetlen közös konzolon. Felügyeleti szempontból lényeges, hogy az Azure-platformra való váltásnak köszönhetően most már modern böngészők is használhatók.

A portal.azure.com webhelyen elérhető Azure Portalon az Intune mostantól az **előzetes** címke nélkül jelenik meg.

Meglévő ügyfeleinknek jelenleg nincs ezzel kapcsolatos teendője, kivéve, ha olyan üzeneteket kaptak az üzenetközpontban, amelyek a csoportok migrálása érdekében bizonyos műveletek elvégzésére kérik őket. Előfordulhat, hogy az üzenetközpontban értesítés tájékoztatja arról, hogy a migrálás hosszabb időt vehet igénybe a mi oldalunkon jelentkező hibák miatt. Továbbra is intenzíven dolgozunk az érintett ügyfelek migrálásának befejezése érdekében.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Továbbfejlesztett alkalmazáscsempék az iOS-es Céges portál alkalmazásban
Frissítettük a kezdőlapon található alkalmazáscsempék megjelenését annak érdekében, hogy a Céges portálhoz beállított márkaszínek jelenjenek meg rajtuk. További információt az [alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) témakörben talál.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Az iOS-es Céges portál alkalmazásban elérhető a fiókválasztó
Akik iOS-es eszközt használnak, a Céges portálba való bejelentkezés után az új fiókválasztót is látni fogják, ha más Microsoft-alkalmazásokba is munkahelyi vagy iskolai fiókjukkal jelentkeznek be. További információt az [alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) témakörben talál.

## <a name="may-2017"></a>2017. május

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Az MDM-szolgáltató módosítása a felügyelt eszközök regisztrációjának törlése nélkül <!--1103950-->
Már anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. A Configuration Manager-konzolon [módosíthatja az MDM-szolgáltatót](/sccm/mdm/deploy-use/change-mdm-authority) a Configuration Manager (hibrid) beállításról Microsoft Intune (önálló) beállításra, vagy fordítva.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Továbbfejlesztett értesítés a Samsung Knox indítási PIN-kódjaihoz <!--1087143-->
Amikor a végfelhasználóknak a titkosítási megfelelőség céljából be kell állítaniuk egy indítási PIN-kódot a Samsung Knox rendszerű eszközeiken, a megjelenített értesítés átirányítja őket a Gépház alkalmazás megfelelő menüjébe az értesítésre való koppintáskor.  Korábban az értesítésre való koppintással a végfelhasználó a jelszómódosítási képernyőre került.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Az Apple School Manager (ASM) támogatása megosztott iPadek esetén <!-- 748864, 770395-->

Az Apple készülékregisztrációs programja helyett az Intune az Apple School Manager (ASM) használatával támogatja az iOS-es eszközök alapértelmezett regisztrációját. ASM típusú beléptetésre van szükség a megosztott iPadek Osztályterem alkalmazásának használatához, valamint az adatok Microsoft School Data Sync (SDS) szolgáltatáson keresztüli szinkronizálásához az ASM és az Azure Active Directory között. További információ: [iOS-eszközök regisztrációjának engedélyezése az Apple School Manager-ben](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Ahhoz, hogy megosztott iPadeket konfigurálhasson az Osztályterem alkalmazáshoz, szükség van az iOS oktatási funkcióinak konfigurálására, ami jelenleg nem elérhető az Azure-ban.  Ezt a funkciót hamarosan elérhetővé tesszük.

### <a name="device-management"></a>Eszközkezelés

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Távsegítség Android-eszközökhöz a TeamViewerrel <!-- 675418 -->

Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani az androidos eszközök felhasználóinak. További információt a [Távsegítség nyújtása az Intune által felügyelt Android-eszközökhöz](device-profile-android-teamviewer.md) témakörben talál.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>A MAM szolgáltatás alkalmazásvédelmi szabályzatainak új feltételei <!-- 679864 -->

A nem regisztrált felhasználókra vonatkozóan olyan követelményeket állíthat be a MAM szolgáltatásban, amely az alábbiakat írja elő:

- Az alkalmazás minimális verziószáma
- Az operációs rendszer minimális verziószáma
- A megcélzott alkalmazás minimális Intune App SDK-verziószáma (csak iOS)

A funkció Androidon és iOS-en egyaránt elérhető. Az Intune támogatja az operációs rendszerek, az alkalmazások és az Intune App SDK minimális verziószámának kényszerítését. Az integrált SDK-val rendelkező iOS-es alkalmazások az SDK szintjén állíthatják be a minimális verziószám kényszerítését. A felhasználó nem fog tudni hozzáférni a megcélzott alkalmazáshoz, ha az alkalmazásvédelmi szabályzat minimális követelményei a fenti három szinten nem teljesülnek. Ilyenkor a felhasználó eltávolíthatja a fiókját (többszörös identitást használó alkalmazások esetén), bezárhatja az alkalmazást, vagy frissítheti az operációs rendszert vagy az alkalmazást.

További beállítások konfigurálásával nem zavaró értesítésben lehet javasolni a felhasználóknak az operációs rendszer vagy az alkalmazás frissítését. Az ilyen értesítéseket be lehet zárni, és az alkalmazás a megszokott módon használható.

További információt [Az iOS-es alkalmazásfelügyeleti szabályzat beállításai](app-protection-policy-settings-ios.md) és [Alkalmazásvédelmi szabályzatok androidos beállításai](app-protection-policy-settings-android.md) témakörökben talál.

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Alkalmazáskonfigurációk beállítása az Android for Workhöz <!-- 621621 -->
Néhány áruházból származó androidos alkalmazás támogatja a felügyelt konfigurációs lehetőséget is, amellyel a rendszergazda meghatározhatja, hogyan fusson az alkalmazás a munkahelyi profilban. Az Intune most már lehetővé teszi, hogy megnézhesse az alkalmazás által támogatott konfigurációs lehetőségeket, amelyeket az Azure Portalon egy konfigurációtervezővel vagy JSON-szerkesztővel meg is változtathat. További információt az [Alkalmazáskonfigurációk használata Android for Workhöz](app-configuration-policies-use-android.md) témakörben talál.

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Új alkalmazáskonfigurációs lehetőség a regisztráció nélküli MAM-hoz <!-- 677969 -->
Mostantól a regisztráció nélküli MAM csatornáján keresztül is létrehozhat alkalmazáskonfigurációs szabályzatokat. Ez a funkció megegyezik a mobileszköz-kezelési (MDM) alkalmazáskonfigurációnál elérhető alkalmazáskonfigurációs szabályzatok funkciójával. A regisztráció nélküli MAM-ot használó alkalmazáskonfigurációra [Az internet-hozzáférés Managed Browser-szabályzatokkal való kezelése a Microsoft Intune-ban](app-configuration-managed-browser.md) című témakörben talál példát.

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Engedélyezett és letiltott URL-címek meghatározása a Managed Browser számára <!-- 682960 -->
Mostantól konfigurálható engedélyezett és letiltott alkalmazások URL-jeinek listája az Intune Managed Browser számára. Ehhez az Azure Portal alkalmazáskonfigurációs beállításait használhatja. Ezt a beállítást attól függetlenül lehet konfigurálni, hogy az felügyelt vagy nem felügyelt eszközön van-e használatban. További információkért lásd: [Az internet-hozzáférés kezelése Managed Browser-szabályzatokkal a Microsoft Intune-ban](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Alkalmazásvédelmi szabályzatok segélyszolgálati megtekintése <!-- 1069473 -->
Az informatikai segélyszolgálat felhasználói mostantól a Hibaelhárítás panelen ellenőrizhetik a felhasználói licencek állapotát és felhasználókhoz rendelt és alkalmazásvédelmi szabályzatokkal kezelt alkalmazások állapotát. További részleteket a [Hibaelhárítás](./help-desk-operators.md) témakörben talál.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Webhelylátogatások felügyelete iOS-eszközökön <!-- 723832 -->
Mostantól az alábbi két módszer valamelyikével szabályozhatja, hogy az iOS-es eszközök felhasználói mely webhelyeket nyithatják meg:

- Engedélyezett és letiltott URL-ek megadása az Apple beépített webtartalomszűrőjével

- Csak a megadott webhelyek elérésének engedélyezése a Safari böngészőnek. Minden megadott webhelyhez könyvjelző jön létre a Safariban.

További információt a [Webtartalomszűrő beállításai iOS-eszközökön](web-content-filter-settings-ios.md) témakörben talál.

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Az Android for Work-alkalmazások eszközengedélyeinek előzetes konfigurálása <!-- 621614 -->
Az Android for Work-eszközök munkahelyi profiljába telepített alkalmazások esetén konfigurálni lehet az egyes alkalmazások engedélyezési állapotát.  Alapértelmezés szerint az eszközengedélyeket (például hozzáférés a tartózkodási hely adataihoz vagy az eszköz kamerájához) megkövetelő androidos alkalmazások felszólítják a felhasználókat az engedélyek elfogadására vagy elutasítására.  Például ha egy alkalmazás az eszköz mikrofonját használja, a rendszer felszólítja a végfelhasználót, hogy adjon engedélyt az alkalmazásnak a mikrofon használatára. Ezzel a funkcióval engedélyeket határozhat meg a végfelhasználó nevében.  Az engedélyeket háromféleképpen konfigurálhatja: a) automatikus elutasítás a felhasználó értesítése nélkül, b) automatikus jóváhagyás a felhasználó értesítése nélkül, valamint c) a felhasználó elfogadásra vagy elutasításra való felszólítása. További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Alkalmazásspecifikus PIN-kód meghatározása Android for Work-eszközökön <!-- 728976, 1102534 -->
A munkahelyi profillal rendelkező, Android for Work-eszközként kezelt Android 7.0 vagy újabb rendszerű eszközök esetén a rendszergazda meghatározhat egy olyan PIN-kód-szabályzatot, amely csak a munkahelyi profilba telepített alkalmazásokra vonatkozik.  A lehetőségek a következők:

- Eszközre érvényes PIN-kód-szabályzat meghatározása – a felhasználónak ezt a PIN-kódot kell használnia az eszköz feloldására.
- Munkahelyi profilra érvényes PIN-kód-szabályzat meghatározása – a rendszer a PIN-kód megadását kéri a felhasználótól a munkahelyi profilban található bármely alkalmazás megnyitásakor.
- Eszközre és munkahelyi profilra egyaránt érvényes szabályzat meghatározása – a rendszergazdának lehetősége van eszközre és munkahelyi profilra egyaránt érvényes, különböző erősségű PIN-kód-szabályzat meghatározására (például 4 számjegyből álló PIN-kód az eszköz feloldásához, illetve 6 számjegyből álló PIN-kód a munkahelyi alkalmazások megnyitásához).

További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

> [!NOTE]
> Ez a funkció csak Android 7.0 vagy újabb rendszereken érhető el.  Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy dönthet úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használja.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Új beállítások Windows 10-es eszközök esetén <!-- 978585 -->
Újabb [windowsos eszközkorlátozási beállításokat](device-restrictions-windows-10.md) vezettünk be, amelyek a vezeték nélküli kijelzőkhöz, az eszközfelderítéshez, a feladatváltáshoz vagy a SIM-kártyák hibaüzeneteihez hasonló szolgáltatásokat szabályoznak.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Újdonságok a tanúsítványkonfigurációban <!-- 918991 and 823198 -->
SCEP-tanúsítványprofil létrehozásakor iOS, Android és Windows-eszközök esetén a <strong>Tulajdonos nevének formátuma</strong> beállításnál az<strong>Egyéni</strong> lehetőség is választható. A jelen frissítés előtt az <strong>Egyéni</strong> mező csak iOS-eszközök esetén volt elérhető. További információ: [SCEP-tanúsítványprofil létrehozása](certificates-scep-configure.md#create-a-scep-certificate-profile).

PKCS-tanúsítványprofil létrehozásakor a **Tulajdonos alternatív neve** értékeként az **Egyéni Azure Ad-attribútum** lehetőség is választható. Az **Egyéni Azure Ad-attribútum** kiválasztásakor a **Részleg** lehetőség is megjelenik. További információt [a PKCS-tanúsítványprofilok létrehozásáról](certficates-pfx-configure.md#create-a-device-configuration-profile) szóló útmutatóban talál.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Több alkalmazás konfigurálásra teljes képernyős módban való futtatáshoz Android-eszközön <!-- 662059 -->
Korábban csak egy alkalmazást lehetett úgy konfigurálni, hogy az Android-eszközön teljes képernyős módban fusson. Mostantól több alkalmazás is konfigurálható így az alkalmazásazonosító vagy az áruházi URL-cím használatával, de kiválasztható egy már felügyelt Android-alkalmazás is. További információt [A teljes képernyős mód beállításai](device-restrictions-android.md#kiosk) témakörben talál.



## <a name="april-2017"></a>2017. április

### <a name="support-for-managing-the-apple-classroom-app"></a>Támogatás az Apple Osztályterem alkalmazás felügyeletéhez
Az iOS-es Osztályterem alkalmazás mostantól felügyelhető iPad eszközökön. Miután telepítette az Osztályterem alkalmazást a tanári iPad-en a megfelelő osztály- és tanulói adatokkal, majd beállította az osztályhoz rendelt tanulói iPad-eket, az alkalmazás segítségével a tanári iPad-ről vezérelheti őket.
További információt [Az iOS oktatási funkcióinak konfigurálása](education-settings-configure-ios.md) című cikkben talál.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Felügyelt konfigurációs lehetőségek támogatása androidos alkalmazásokhoz <!-- 621621 -->
A Play áruházban lévő, felügyelt konfigurációs lehetőségeket támogató androidos alkalmazásokat az Intune-nal is lehet konfigurálni.  Ezzel a funkcióval az IT-részleg megnézheti az egyes alkalmazásokban használható konfigurációs értékek listáját, és útmutatásokkal ellátott, kiváló felhasználói felületen konfigurálhatják ezeket az értékeket.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Új androidos szabályzat komplex PIN-kódokhoz <!-- 722069 -->
5.0-s vagy újabb Android rendszerű eszközökhöz tartozó androidos eszközprofilban meg lehet adni a Komplex numerikus értéket kötelező [jelszótípusként](device-restrictions-android.md#password).  Ezzel a beállítással lehet megakadályozni, hogy a felhasználók ismétlődő vagy egymást követő számokból álló PIN-kódot (például 1111 vagy 1234) válasszanak.

### <a name="additional-support-for-android-for-work-devices"></a>Kibővített támogatás Android for Work-eszközökhöz
- **Jelszó- és munkahelyiprofil-beállítások kezelése** <!-- 612808 -->

  Az új Android for Work-eszközkorlátozási szabályzattal kezelhetők a felügyelt Android for Work-eszközök jelszó- és munkahelyiprofil-beállításai.

- **A munkahelyi és a személyes profilok közötti adatmegosztás engedélyezése** <!-- 1045102 -->

Az Android for Work-eszközkorlátozási szabályzat új lehetőségekkel segíti a munkahelyi és személyes profil közötti adatmegosztás konfigurálását.

- **A munkahelyi és a személyes profilok közötti másolás és beillesztés korlátozása** <!-- 1046094 -->

  Az Android for Work-eszközökhöz készült új egyéni eszközprofillal megszabhatja, hogy engedélyezi-e a munkahelyi és a személyes profilok közötti másolást és beillesztést.

További információt az [Eszközkorlátozások az Android for Work esetén](device-restrictions-android-for-work.md) című témakörben talál.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Üzletági alkalmazások hozzárendelése iOS-es és androidos eszközökhöz <!-- 1057568 -->
Az [iOS-re](lob-apps-ios.md) (.ipa-fájlok) és [Androidra](lob-apps-android.md) (.apk-fájlok) készült üzletági (LOB) alkalmazásokat felhasználókhoz vagy eszközökhöz rendelheti hozzá.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Új eszközszabályzatok iOS rendszerhez <!-- 723774, 723815, 723826, 723830 -->
- **A kezdőképernyőn látható alkalmazások** – Azt határozza meg, mely alkalmazásokat láthatják a felhasználók [iOS-es eszközeik kezdőképernyőjén](home-screen-settings-ios.md). Ez a szabályzat megváltoztatja a Kezdőképernyő elrendezését, de nem helyez üzembe semmilyen alkalmazást.

- **Kapcsolódás AirPrint-eszközökhöz** – Azt határozza meg, hogy mely [AirPrint-eszközökhöz](air-print-settings-ios-macos.md) (hálózati nyomtatókhoz) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Kapcsolódás AirPlay-eszközökhöz** – Azt határozza meg, hogy mely [AirPlay-eszközökhöz](airplay-settings-ios.md) (például Apple TV-hez) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Egyéni üzenet a zárolási képernyőn** – Az alapértelmezett helyett egyéni üzenetet állíthat be az iOS-es eszköz zárolási képernyőjére. További információt az [Elveszett eszköz mód aktiválása iOS-eszközökön](device-lost-mode.md) témakörben talál

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS-alkalmazások leküldéses értesítéseinek korlátozása <!-- 723767 -->
Az Intune-os eszközkorlátozási profilokban már a következő [értesítési beállításokat](app-notification-settings-ios.md) is konfigurálhatja iOS-es eszközökhöz:

- Adott alkalmazás értesítéseinek teljes körű be- vagy kikapcsolása
- Adott alkalmazás értesítési központban megjelenő értesítéseinek be- vagy kikapcsolása
- Riasztástípus megadása (**None** – Nincs, **Banner** – Szalag vagy **Modal Alert** – Modális riasztás)
- Jelvények engedélyezése az alkalmazásnak
- Értesítési hangok engedélyezése az alkalmazásnak.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-alkalmazások konfigurálása autonóm egyalkalmazásos módhoz <!-- 737837 -->
Intune-eszközprofillal mostantól konfigurálhatja az iOS-es eszközöket megadott alkalmazások [autonóm egyalkalmazásos módban](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only) való futtatására. Ha ez a mód konfigurálva van, és az alkalmazást elindítják, az eszközön nem lehet másik alkalmazást futtatni. Célszerű például így konfigurálni az olyan alkalmazásokat, amelyekkel a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Megbízható tartományok konfigurálása levelezéshez és böngészéshez iOS-es eszközökön <!-- 723765 -->
Az iOS-es eszközkorlátozási profilokban a következő [tartománybeállításokat](device-restrictions-ios.md#domains) konfigurálhatja:

- **Jelöletlen levelezési tartományok** – a felhasználó által az itt megadottól különböző tartománnyal küldött vagy fogadott e-mailek meg lesznek jelölve nem megbízhatóként.

- **Felügyelt webtartományok** – az itt megadott URL-címekről letöltött dokumentumok felügyeltnek minősülnek (csak a Safari esetében).  

- **Jelszavak automatikus kitöltése a Safariban** – a felhasználók csak olyan URL-eken menthetik jelszavaikat a Safariban, amelyek egyeznek az itt megadott mintákkal. Ez a beállítás csak felügyelt módú, többfelhasználós konfigurációval nem rendelkező eszközön használható. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>A VPP-alkalmazások elérhetőek az iOS-es Céges portálon <!-- 748782 -->
A mennyiségi vásárlási program (VPP) keretében vásárolt iOS-es alkalmazásokat **Elérhető** telepítésként hozzárendelheti végfelhasználókhoz, akik Apple Store-fiókkal telepíthetik az alkalmazást.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>E-könyvek szinkronizálása az Apple VPP Store-ból <!-- 800878 -->
Az Apple mennyiségi vásárlásra szolgáló áruházából vásárolt [könyvek szinkronizálhatók](vpp-apps-ios.md) az Intune-nal, és kioszthatók felhasználóknak.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Többfelhasználós felügyelet a Samsung Knox Standard-eszközökön <!-- 971988 -->
A Samsung Knox Standard rendszerű eszközökön mostantól használható az Intune [többfelhasználós felügyelete](android-enroll.md). Ilyenkor a felhasználók Azure Active Directory-beli hitelesítő adataikkal jelentkezhetnek be és ki az eszközön, de az központi felügyelet alatt marad, akár használatban van, akár nem.  A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

### <a name="additional-windows-device-restriction-settings----818566---"></a>További windowsos eszközkorlátozási beállítások <!-- 818566 -->
További [windowsos eszközkorlátozási beállításokat](device-restrictions-windows-10.md) tettünk elérhetővé, például bővült az Edge böngésző támogatása, testre szabható az eszközök zárolási képernyője és Start menüje, szabályozható a Windows Reflektorfény háttérképkészlete, illetve a proxybeállítások.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Többfelhasználós támogatás a Windows 10 alkotói frissítéséhez <!-- 822547 -->
A [többfelhasználós felügyelet](windows-enroll.md) támogatását kiterjesztettük a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökre. Ez azt jelenti, hogy az eszközre minden egyes, Azure AD-s hitelesítő adataival bejelentkező általános jogú felhasználó a saját felhasználónevéhez rendelt alkalmazásokat és szabályzatokat kapja meg. A felhasználók jelenleg nem használhatják a Céges portált önkiszolgálói forgatókönyvek esetén (például alkalmazások telepítése).

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Újrakezdés művelet Windows 10-es PC-khez<!-- 1004830 -->
A Windows 10-es PC-ken már elérhető az új [Újrakezdés eszközművelet](device-fresh-start.md).  amely eltávolítja a PC-re telepített alkalmazásokat, és automatikusan a Windows legújabb verziójára frissíti a gépet. Így egyszerűbben eltávolíthatók az új gépeken gyakran előtelepítve megtalálható számítógépgyártói (OEM) alkalmazások. A konfigurációval meg lehet adni, hogy a művelet a felhasználói adatokat is eltávolítsa-e.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>További Windows 10-es frissítési útvonalak <!-- 903672 -->
Mostantól olyan [kiadásfrissítési szabályzatok](edition-upgrade-configure-windows-10.md) is létrehozhatók, amelyekkel az alábbi Windows 10-kiadásokra frissíthetők az eszközök:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-es eszközök tömeges regisztrálása <!-- 747607 -->
Mostantól a Windows Configuration Designer (WCD) használatával a Windows 10 alkotói frissítéssel rendelkező nagy számú eszközt csatlakoztathat az Azure Active Directoryhez és az Intune-hoz. Ha Azure AD-bérlőhöz be szeretné kapcsolni a [tömeges MDM-regisztrálást](windows-bulk-enroll.md), a Windows Configuration Designerrel hozzon létre olyan kiépítési csomagot, amely csatlakoztatja az eszközöket az Azure AD-bérlőhöz, majd alkalmazza a csomagot a csoportosan regisztrálni és felügyelni kívánt vállalati tulajdonú eszközökre. A csomagok alkalmazását követően az eszközök csatlakoznak az Azure AD-hez, regisztrálnak az Intune-ban, és készen állnak az Azure AD-felhasználók bejelentkezésére.  Az Azure AD-felhasználók általános jogú felhasználók ezeken az eszközökön, akik megkapják majd a kijelölt szabályzatokat és a kötelező alkalmazásokat. Az önkiszolgáló és a Céges portált használó módszer jelenleg nincs támogatva.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Új MAM-beállítások a PIN-kódhoz és a felügyelt tárolóhelyekhez <!-- 581122, 736644 -->
Két új alkalmazásbeállítás segíti a mobileszköz-felügyeletet (MAM):

- **Disable app PIN when device PIN is managed** (Alkalmazás PIN-kódjának letiltása felügyelt eszköz-PIN-kód esetén) – a rendszer észleli, hogy van-e eszköz-PIN-kód a regisztrált eszközön, és ha van, mentesíti a felhasználót az alkalmazásvédelmi szabályzatok által megkövetelt alkalmazás-PIN-kód megadása alól, ily módon kevesebbszer kell PIN-kódot megadni a regisztrált eszközökön a MAM-mal védett alkalmazások megnyitásakor. A funkció Androidon és iOS-en egyaránt elérhető.

- **A társzolgáltatások kijelölése, melyekbe menthetők a vállalati adatok** – itt lehet megadni, hogy mely tárolóhelyekre mentse a rendszer a vállalati adatokat. A felhasználók csak a kijelölt tárolóhelyekre menthetnek, a fel nem sorolt tárolóhelyek tehát le lesznek tiltva.

  A támogatott tárhelyszolgáltatások:

  - OneDrive
  - Vállalati SharePoint Online
  - Helyi tárhely

### <a name="help-desk-troubleshooting-portal----907448---"></a>Ügyfélszolgálati hibaelhárítási portál <!-- 907448 -->
Az új [hibaelhárítási portálon](help-desk-operators.md) az ügyfélszolgálati munkatársak és az Intune-rendszergazdák áttekinthetik a felhasználók és eszközeik listáját, és az Intune technikai problémáinak elhárítását is elvégezhetik.

## <a name="march-2017"></a>2017. március

### <a name="support-for-ios-lost-mode---431695--"></a>Az iOS-es elveszett mód támogatása <!--431695-->
Az iOS 9.3 és újabb verziói esetében az Intune már az **Elveszett módot** is támogatja. Ezzel letiltható az eszközön minden tevékenység, a zárolási képernyőn pedig üzenet és kapcsolatfelvételhez használható telefonszám jelenik meg.

A végfelhasználó csak akkor tudja feloldani az eszközt, ha a rendszergazda kikapcsolja az Elveszett módot. Ha az Elveszett mód be van kapcsolva, az Intune-konzolon az **Eszköz megkeresése** művelet használatával megjelenítheti az eszköz tartózkodási helyét egy térképen.

A funkció csak felügyelt módban lévő, DEP-pel regisztrált, céges tulajdonban lévő iOS-eszközökön használható.

További információt [A Microsoft Intune-eszközfelügyelet ismertetése](device-management.md) című témakörben talál.

### <a name="improvements-to-device-actions-report---677150--"></a>Fejlesztések az eszközműveleti jelentéseknél <!--677150-->
A jobb teljesítmény érdekében fejlesztéseket végeztünk az eszközműveleti jelentéseknél. A jelentéseken ezen kívül állapot szerinti szűrések is végezhetők. Például olyan módon is szűrhetőek a jelentések, hogy csak a végrehajtott eszközműveletek jelenjenek meg.”

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Üzletági alkalmazások hozzárendelése nem regisztrált eszközökkel rendelkező felhasználókhoz <!--748823-->
Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Céges portál alkalmazás helyett a Céges portál webhelyen telepíthetik az alkalmazást.

### <a name="new-compliance-reports---846671--"></a>Új megfelelőségi jelentések <!--846671-->
A megfelelőségi jelentések megmutatják a cég eszközeinek megfelelőségi helyzetét, így lehetővé válik a felhasználók által tapasztalt megfelelőségi problémák gyors elhárítása. Az alábbi információkat tekintheti meg:

- Az eszközök összesített megfelelőségi állapota
- Az egyes beállítások megfelelőségi állapota
- Az egyes szabályzatok megfelelőségi állapota

A jelentések segítségével egy-egy eszköz részletesebben is megvizsgálható, és ellenőrizhető, hogy mely beállítások és szabályzatok vonatkoznak rá.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak az Azure Portalon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.


## <a name="february-2017"></a>2017. február

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>A mobileszköz-regisztrálás korlátozásának képessége <!--747600, 795782-->
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.

* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.  
* Csak az iOS és az Android esetében van még egy lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Az összes művelet megtekintése a felügyelt eszközökön<!--677150-->
Az új __Eszközműveletek__ jelentés megmutatja, hogy mely felhasználó hajtott végre távoli műveleteket az eszközön (például gyári alaphelyzetbe állítás), valamint megjeleníti az adott művelet állapotát is. Lásd: [Mi az eszközfelügyelet?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->
A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](apps-add.md).

### <a name="display-device-categories---814654--"></a>Eszközkategóriák megjelenítése <!--814654-->
Mostantól az eszközkategória külön oszlopként jelenik meg az eszközlistában. A kategória módosítására szintén van lehetőség az Eszköztulajdonságok panel Tulajdonságok szakaszában. Lásd: [Alkalmazás hozzáadása az Intune-hoz](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>A Vállalati Windows Update beállításainak konfigurálása <!--776716-->

A Windows 10 frissítéseinek biztosítására a jövőben a szolgáltatásként nyújtott Windows használható. A Windows 10-től kezdődően minden új funkció- és minőségi frissítés magában foglalja valamennyi korábbi frissítés tartalmát. Ennek köszönhetően a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 eszközök teljesen naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.

A Vállalati Windows Update használatával egyszerűbbé válik a frissítések kezelése, így nem szükséges külön jóváhagyni az egyes frissítéseket az eszközcsoportokhoz. A különböző környezetekben továbbra is kezelhető a kockázat egy frissítéstelepítési stratégia konfigurálásával, és a Windows Update gondoskodik a frissítések megfelelő időpontban történő telepítéséről. A Microsoft Intune lehetővé teszi a frissítési beállítások konfigurálását az eszközökön és a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A **Windows 10 frissítési körök** az Intune használatával konfigurálhatók és kezelhetők. A frissítési kör olyan beállításokat tartalmaz, amelyek a Windows 10 frissítések telepítésének ütemezését és mikéntjét konfigurálják. További információt [A Vállalati Windows Update beállításainak konfigurálása](windows-update-for-business-configure.md) című témakörben talál.

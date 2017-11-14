---
title: "Előzetes kiadás"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7cc595655950ef1bf2586e939b6f02e270e7afc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>A Microsoft Intune előzetes kiadása – 2017. November

Ez az **előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Az információkat szűk körben bocsátjuk rendelkezésre, és a későbbiekben változhatnak. Ne ossza meg ezeket az információkat cégen kívüli személyekkel. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel forduljon a Microsoft-termékcsoport kapcsolattartójához.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
>A következő változtatások vannak fejlesztés alatt az Intune-hoz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Office 365-mobilalkalmazások hozzárendelése iOS- és Android-eszközökhöz a regisztrált alkalmazástípussal <!-- 1332318 -->
A **Beépített** alkalmazástípussal könnyebben hozhat létre és rendelhet Office 365-alkalmazásokat a felügyelt iOS- és Android-eszközeihez. Ezek az alkalmazások olyan 0365-alkalmazásokat tartalmaznak, mint a Word, az Excel, a PowerPoint és a OneDrive. Az alkalmazástípushoz konkrét alkalmazásokat rendelhet hozzá, valamint szerkesztheti az alkalmazásadatok konfigurációját.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Egyszeri bejelentkezés támogatása iOS-en <!-- 1333645 -->  
Az iOS-felhasználók is használhatják az egyszeri bejelentkezést. Azok az iOS-alkalmazások, amelyek az egyszeri bejelentkezés hasznos forgalmában található felhasználói hitelesítő adatok keresésére vannak kódolva, ezzel a hasznosforgalom-konfigurációs frissítéssel fognak működni. Emellett az egyszerű felhasználónévvel és az Intune-eszközazonosítóval is konfigurálhatja az egyszerű nevet és a tartományt.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>iOS 11 alkalmazásleltár-API a Mobil fenyegetésészleléshez <!-- 1391759 -->
Az Intune mind a személyes, mind a vállalati tulajdonban lévő eszközöktől alkalmazásleltár-adatokat gyűjt, amelyeket elérhetővé tesz a Mobil fenyegetésészlelés szolgáltatói, például a Lookout for Work számára. Az alkalmazásleltárakat az iOS 11 vagy újabb operációs rendszerrel rendelkező felhasználóktól gyűjtheti be.

**Alkalmazásleltár**  
Az Intune mind a személyes, mind a vállalati tulajdonban lévő, iOS 11 vagy újabb operációs rendszerű eszközöktől alkalmazásleltár-adatokat küld az Ön Mobil fenyegetésészlelés-szolgáltatójának. Az alkalmazásleltár adatai az alábbiakat tartalmazzák:

 - Alkalmazásazonosító
 - Alkalmazásverzió
 - Alkalmazás rövid verziója
 - Alkalmazásnév
 - Alkalmazás csomagjának mérete
 - Alkalmazás dinamikus mérete
 - Az alkalmazás ellenőrzési állapota
 - Az alkalmazás felügyeleti állapota

### <a name="audit-updates----1412961---"></a>Naplózási frissítések <!-- 1412961 -->  
Az Intune-naplózás az Intune-hoz kapcsolódó változtatási műveletekről szolgáltat információt.  Minden létrehozási, frissítési, törlési és távoli feladatműveletet rögzít és egy évig megőriz.  Az Azure Portalon megtekintheti az elmúlt 30 nap naplózási adatait számítási feladatonként, szűrhető állapotban.  Egy kapcsolódó Graph API segítségével lekérheti az elmúlt egy év tárolt naplózási adatait. 

A naplózás funkció a **FIGYELÉS** csoportban érhető el. A csoportban minden számítási feladathoz tartozik egy **Naplók** menüpont.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Engedélyezett szövegprotokoll a felügyelt alkalmazásokból <!-- 1414050  -->
Az Intune App SDK által felügyelt alkalmazások SMS-eket küldhetnek.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-eszköz távoli újraindítása (csak felügyelt eszközök esetén) <!-- 1424595 -->
Egy eszközművelettel újraindíthat egy felügyelt, iOS 10.3 vagy újabb operációs rendszerű eszközt. További információ az eszköz-újraindítás műveletről: [Az eszközök távoli újraindítása az Intune-nal](device-restart.md).

> [!Note]  
> Ehhez a parancshoz felügyelt eszközökre és az **Eszközzárolás** hozzáférési jogosultságra van szükség. Az eszköz azonnal újraindul. A PIN-kóddal zárolt iOS-eszközök nem csatlakoznak újra a Wi-Fi-hálózatokra az újraindítás után, így előfordulhat, hogy ilyen esetekben nem tudnak kommunikálni a kiszolgálóval.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Felügyelt macOS-eszközök távoli zárolása az Intune-nal <!-- 1437691 -->
Zárolhatja elveszett macOS-eszközét, és beállíthat egy hat számjegyű jelszó-helyreállító PIN-kódot. A zárolt eszköz **Az eszköz áttekintése** panelén megjelenik a PIN-kód mindaddig, amíg az eszköznek nem kell egy másik műveletet végrehajtania.

További információ: [Felügyelt eszközök távoli zárolása az Intune-nal](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>A Windows Defender Komplex veszélyforrások elleni védelem jelentéseinek gyakorisága  <!--- 1455974  --->
A Windows Defender Komplex veszélyforrások elleni védelem (WDATP) szolgáltatással a rendszergazdák kezelhetik a felügyelt eszközök jelentéseinek gyakoriságát. Az új **Telemetriai jelentések gyakoriságának növelése** beállítással a WDATP gyakrabban gyűjt adatokat és méri fel a kockázatokat. A jelentések alapértelmezett beállítása optimalizálja a sebességet és a teljesítményt. A jelentések gyakoriságának növelése értékes lehet a magas fokú kockázattal bíró eszközök esetében. Ez a beállítás a **Windows Defender ATP** profilban, az **Eszközkonfigurációk** területen érhető el.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>A hozzárendelésbeli ütközések feloldása megváltozott az áruházból származó iOS-alkalmazások számára <!-- 1480316 -->
A végfelhasználók változást tapasztalhatnak az áruházbeli iOS-alkalmazások elérhetőségében. Az olyan alkalmazások, amelyek két, **Kötelező és elérhető** és **Nem alkalmazható** között ütköző csoporthoz vannak rendelve, a **Kötelező és elérhető** beállítással oldódnak fel. A módosításnak köszönhetően az ilyen ütközéseket tapasztaló alkalmazások a **Nem alkalmazható** beállítással oldódnak fel.

Ez a módosítás azt a zavart hivatott feloldani, amely akkor keletkezhetett, ha egy alkalmazás több, különböző alkalmazásszándékkal rendelkező csoporthoz volt rendelve.

Ha szeretné, hogy az alkalmazása elérhető legyen az Information Worker Portalon, valamint a céges portálon a novemberi kiadás előtt, két opció közül választhat:

1. Távolítsa el a **Nem alkalmazható** hozzárendelést a csoportból.
2. Hozzon létre egy új csoportot, amely nem tartalmaz **Kötelező és elérhető** hozzárendelt szándékot, majd rendelje a csoporthoz a **Nem alkalmazható** beállítást.

További információ: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md).

> [!Note]
> A megjelenés után nem tekintheti meg vagy módosíthatja a mobileszköz-kezelés alkalmazás-hozzárendeléseit a klasszikus Intune-konzolon. Az Azure-konzollal vagy az Intune Graph API-val azonban elvégezheti az alkalmazás-hozzárendeléseket.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Android for Work-eszközök kezelése függetlenül az Android-eszközöktől <!-- 1490731 -->
Az Intune támogatja az Android for Work-eszközök regisztrációjának az Android-platformtól független kezelését. Ezek a beállítások az **Eszközregisztráció** > **Regisztrációs korlátozások** > **Eszköztípus-korlátozások** területen kezelhetők. (Korábban az **Eszközregisztráció** > **Android for Work-regisztráció** > **Az Android for Work regisztrációs beállításai** területen voltak elérhetők.)

Alapértelmezés szerint az Android for Work-eszközök beállításai ugyanazok, mint az Android-eszközöké. Az Android for Work-beállítások módosítása után ez azonban már nem lesz így.
 
Ha letiltja a személyes Android for Work-regisztrációt, csak a vállalati Android-eszközök regisztrálhatók Android for Work-eszközként.

Az új beállításokkal való munka során vegye figyelembe a következőket:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Ha még soha nem végzett előkészítést Android for Work-regisztrációhoz
Az új Android for Work-platform le van tiltva az alapértelmezett Eszköztípus-korlátozások beállításban. A funkció előkészítése után engedélyezheti az eszközök számára az Android for Work-regisztrációt. Ehhez meg kell változtatnia az alapértelmezett korlátozást, vagy létre kell hoznia egy új eszköztípus-korlátozást, amely felülírja az alapértelmezett eszköztípus-korlátozást.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Ha már végzett előkészítést Android for Work-regisztrációhoz
Ha már korábban végzett előkészítést, a további lépések a választott beállításoktól függnek:

| Beállítás | Az Android for Work állapota az alapértelmezett Eszköztípus-korlátozás beállításban | Megjegyzések |
| --- | --- | --- |
| **Minden eszköz felügyelete Android-eszközként** | Blokkolva | Minden Android-eszköznek regisztrálnia kell az Android for Work nélkül. |
| **Minden támogatott eszköz felügyelete Android for Work-eszközként** | Engedélyezett | Minden, az Android for Worköt támogató Android-eszközt regisztrálni kell az Android for Workkel. |
| **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** | Blokkolva | Létrejött egy különálló eszköztípus-regisztrációs szabályzat, amely felülírja az alapértelmezettet. Ez a szabályzat határozza meg a korábban az Android for Work-beléptetés engedélyezéséhez kiválasztott csoportokat. A kiválasztott csoportok felhasználói továbbra is regisztrálhatják az Android for Work-eszközeiket. A többi felhasználó nem regisztrálhat eszközöket az Android for Workkel. |

A kívánt szabály minden esetben megmarad. Önnek nem kell semmilyen további lépést végeznie a környezetében az Android for Work globális vagy csoportonkénti engedélyezésének fenntartásához.

A módosítások a novemberi frissítésben jelennek meg, azonban időbe telhet, míg végbemennek a fiókjában. Az Office 365 portálon értesítést kap arról, ha a módosítások életbe léptek a fiókjában.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Támogatás több NDES-összekötőhöz<!-- 1528104 -->
A hálózati eszközök tanúsítványigénylési szolgáltatása (NDES) lehetővé teszi a mobileszközökön tartományi hitelesítő adatok nélkül futó szoftverek számára, hogy az egyszerű tanúsítványigénylési protokoll (SCEP) alapján tanúsítványokat szerezzenek be. Ez a frissítés több NDES-összekötő támogatását teszi lehetővé.

### <a name="new-scep-profile-details-supported----1559808---"></a>Új támogatott SCEP-profiladatok <!-- 1559808 -->
A rendszergazdák további beállításokat adhatnak meg a SCEP-profilok létrehozásakor Windows-, iOS-, macOS- és Android-platformokon.  A rendszergazdák a tárgy névformátumának IMEI-t, sorozatszámot vagy köznapi nevet adhatnak meg, beleértve az e-mail-címeket.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS-alkalmazások PIN-kódjának konfigurálása <!-- 1586774 -->
Hamarosan kérhet PIN-kódot a kívánt iOS-alkalmazások használatához. A PIN-kód megkövetelését és napokban megadott lejárati idejét az Azure Portalon konfigurálhatja. Amikor szükséges, a felhasználóknak új PIN-kódot kell beállítaniuk, ha hozzá szeretnének férni egy iOS-alkalmazáshoz. Ezt a funkciót csak az Intune App SDK alkalmazásvédelmével ellátott iOS-alkalmazások támogatják.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Adatok megőrzése a gyári beállítások visszaállításakor <!-- 1588489 -->
Egy új funkció támogatásával bővítjük a Windows gyári beállításainak visszaállítását. A rendszergazdák mostantól megszabhatják, hogy az eszközregisztráció és egyéb kiépített adatok megmaradjanak-e az eszközökön a gyári beállítások visszaállítása után. 
 
A következő adatok maradnak meg az eszközön a gyári beállítások visszaállításakor:
- Az eszközhöz társított felhasználói fiókok
- A gép állapota (tartományhoz való csatlakozás, AADJ)
- MDM-regisztráció
- Az eredeti berendezésgyártók által telepített alkalmazások (áruház és Win32-alkalmazások)
- Felhasználói profil
- A felhasználói profilon kívüli felhasználói adatok
- Felhasználói automatikus bejelentkezés
 
Az alábbi adatok nem őrződnek meg:
- Felhasználói fájlok
- A felhasználók által telepített alkalmazások (áruház és Win32-alkalmazások)
- Nem alapértelmezett eszközbeállítások 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Az alkalmazás telepítési állapotjelentése mostantól egy sávdiagram <!-- 1249446 -->  
Az **Alkalmazástelepítés állapota** jelentés, amely a **Mobilalkalmazások** terület **Alkalmazás** listájában tekinthető meg minden alkalmazáshoz, hamarosan sávdiagramként jelenik meg.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Az „iPhone keresése” alkalmazás hozzáadása személyes eszközökhöz <!--1427287-->
Megtekintheti, hogy az iOS-eszközökön be van-e kapcsolva az aktiválási zár. Ez a szolgáltatás korábban a klasszikus Intune-portálon volt elérhető.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Csoportregisztrációs korlátozások <!-- 747598 -->
Intune-rendszergazdaként létrehozhat egyéni, eszköztípusra és eszközkorlátra vonatkozó regisztrációs korlátozásokat a felhasználói csoportok számára.
 
Az Intune Azure Portalon akár 25 példányt hozhat létre az egyes korlátozástípusokból, amelyeket aztán felhasználói csoportokhoz rendelhet. A csoportkorlátozások felülírják az alapértelmezett korlátozásokat.
 
Egy korlátozástípus minden példánya egy szigorúan rendezett listában található. Ez a sorrend határozza meg az ütközések feloldásának prioritási értékét. Azokra a felhasználókra, akiket egynél több korlátozáspéldány érint, csak a legmagasabb prioritási értékkel rendelkező példány korlátozása vonatkozik. Egy adott példány prioritását a listán való húzással módosíthatja. 
 
Ez a funkció az Android for Work-beállítások az Android for Work-regisztráció menüjéből a Regisztrációs korlátozások menübe való migrálásának során jelenik meg. Mivel a migrálás több napig is eltarthat, előfordulhat, hogy a fiókja a novemberi kiadás többi részére vonatkozóan frissül, a Regisztrációs korlátozások csoport-hozzárendelés funkciója azonban még nem jelenik meg.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>A Windows 10 frissítési kör hozzárendelései megjelennek <!-- 1621837 -->
**Hibaelhárítás** során az éppen megtekintett felhasználónál láthatja a Windows 10 frissítési körének hozzárendeléseit.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->   
Az Azure Active Directory (Azure AD) használatával korlátozhatja majd a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Regisztrálással kapcsolatos problémák elhárítása <!--- 746324 --->  
A Hibaelhárítás munkaterületen megtalálhatók lesznek a felhasználói regisztrálással kapcsolatos problémák. A hiba adatai és a megoldáshoz javasolt lépések segítséget nyújtanak a rendszergazdának és az ügyfélszolgálati munkatársaknak a hibalehárításban. A rendszer nem jegyez fel minden regisztrálási hibát, és bizonyos hibáknál nem kínál fel megoldási javaslatokat.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Támogatás a Windows 10-kiadások frissítési szabályzatához <!-- 903672(archived), 1119689 -->  
A Windows 10-hez létrehozhat olyan kiadásfrissítési szabályzatot, amely a Windows 10-es eszközöket az alábbi verziókra frissíti: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education és Windows 10 Professional Education N. A Windows 10 kiadásfrissítéseiről a [Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md) című témakörből tájékozódhat.




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Az Android for Work Lookout-támogatása <!-- 1087312 -->   
A Lookouttal rendelkező Intune-összekötők támogatni fogják az Android for Work rendszerű eszközöket a Lookout for Work alkalmazás használatakor. A Lookout alkalmazást a tárolón kívül vagy belül egyaránt telepítheti.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection és Citrix MDX fejlesztői eszközök <!-- 709185 -->
Az eszközöket és az alkalmazásokat a Citrix XenMobile MDX és a Microsoft Intune kombinációjával is kezelheti. Így az eszközök kezelésénél egyaránt igénybe veheti az Intune alkalmazásvédelmi szabályzatát és a Citrix mVPN-technológiáját.

Hozzáférhet egy kódtárhoz, amely a Citrix MDX mVPN-technológiával integráltan tartalmazza az Intune iOS és Android rendszerhez készült alkalmazásburkoló eszközét és az Intune App SDK-t.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása  <!-- 676614 -->   
A helyszíni Exchange Connector használatához több ügyfél-hozzáférési kiszolgálói (CAS) szerepkörrel is rendelkezhet. A fő CAS kiesése esetén például az Exchange Connector kap egy kérelmet, hogy térjen vissza más ügyfél-hozzáférési kiszolgálókhoz. Ez a funkció biztosítja, hogy a szolgáltatás ne szakadjon meg.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager felügyeleti csomag az Exchange Connectorhoz <!-- 885457 -->   
A System Center Operations Manager Exchange Connectorhoz készült felügyeleti csomagja segíteni fog az Exchange Connector naplófájljainak elemzésében. Ez a felügyeleti csomag számos megoldást nyújt az Intune monitorozására hibaelhárítás esetén.





## <a name="intune-apps"></a>Intune-alkalmazások

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Segítségnyújtás a felhasználóknak az Androidhoz készült céges portál alkalmazás használatában <!---1573324, 1573150, 1558616, 1564878--->
Az Androidhoz készült céges portál alkalmazás olyan utasításokkal bővül, amelyekkel a végfelhasználók könnyebben megérthetik, és – ahol lehetséges – egyedül megoldhatják az új használati eseteket. 

- Egy új üzenet jelenik meg, amely tudatja a felhasználóval, hogy egy titkosítási megfelelőségi szabályzat lépett életbe, az [eszköz gyártója azonban nem titkosítja az eszközt](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) a [Google javasolt irányelveinek megfelelően](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- A végfelhasználókat a program az (Azure Active Directory portálra irányítja) [https://account.activedirectory.windowsazure.com/r/#/profile], ahol eltávolíthatják az eszközöket, ha elérték a maximálisan hozzáadható eszközök számát. 
- A végfelhasználók ekkor utasításokat kapnak, amelyekkel [kijavíthatják az aktiválási hibákat a Samsung KNOX-eszközökön](https://go.microsoft.com/fwlink/?linkid=859718), vagy [kikapcsolhatják az energiatakarékos üzemmódot](/intune-user-help/power-saving-mode-android). Ha a megoldások egyike sem oldja meg a problémát, segítséget nyújtunk a [naplófájlok a Microsoftnak való küldéséhez](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Új „Feloldás” művelet az Android-eszközök számára <!---1583480--->
Az Androidhoz készült céges portál alkalmazás egy új „Feloldás” műveletet vezet be az _Eszközbeállítások frissítése_ lapon. A beállítás kiválasztásával a végfelhasználó közvetlenül ahhoz a beállításhoz kerül, amely az eszköz nem megfelelőségét okozza. Az Androidhoz készült céges portál alkalmazás ezt a műveletet jelenleg az [eszköz PIN-kódja](/intune-user-help/set-your-pin-or-password-android), [az eszköztitkosítás](/intune-user-help/encrypt-your-device-android), [az USB-hibakeresés](/intune-user-help/you-need-to-turn-off-usb-debugging-android) és az [Ismeretlen források](/intune-user-help/you-need-to-turn-off-unknown-sources-android) beállításokhoz támogatja. 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS-felhasználók átirányítása az új Céges portál alkalmazáshoz <!--1380728-->   
Ha egy végfelhasználó bejelentkezik a Céges portál webhelyre, hogy regisztrálja macOS-eszközét, átirányítjuk az új macOS-es Céges portál alkalmazás letöltési oldalára, hogy azzal fejezhesse be a folyamatot. Ez azoknál a macOS-eszközöknél történik meg, amelyek az OS X El Capitan 10.11-es vagy újabb verzióit futtatják. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>A regisztrációval vagy anélkül is elérhető alkalmazások mostantól anélkül telepíthetőek, hogy a rendszer a regisztrálást kérné. <!-- 1334712 -->
Azok a céges alkalmazások, amelyek regisztrációval és anélkül is elérhetőek az Androidhoz készült Céges portál alkalmazásban, anélkül is telepíthetők lesznek, hogy a rendszer a regisztrálást kérné.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Intune Managed Browser-támogatás iOS és Android rendszerű eszközök számára <!-- 1374196 -->
2017 októberétől az Intune Managed Browser alkalmazás Androidon kizárólag az Android 4.4 vagy újabb rendszerű eszközöket fogja támogatni. Az Intune Managed Browser alkalmazás iOS-en kizárólag az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
A végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”




## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.




### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).

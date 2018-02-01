---
title: "Előzetes kiadás"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4bcabc4d1af4554a3e3bea875be45f9376b4ef7
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>A Microsoft Intune előzetes kiadása – 2018. február

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


<!-- 1802 start -->


### <a name="app-protection-policies-----679615---"></a>Alkalmazásvédelmi szabályzatok  <!-- 679615 -->
Az Intune alkalmazásvédelmi szabályzatai lehetőséget nyújtanak globális szintű alapértelmezett szabályzatok létrehozására, amelyekkel gyorsan beállítható a megfelelő védelem a teljes bérlő összes felhasználója számára.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 -->

Az Intune támogatni fogja az eszközök regisztrációját akár 100 különböző Apple Device Enrollment Program (DEP) vagy Apple School Manager típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>A Windows Defender állapota és a fenyegetések állapotjelentései <!--854704 -->

A Windows Defender állapotának megértése kulcsfontosságú a Windows rendszerű számítógépek kezelésében.  Az Intune új jelentéseket és műveleteket ad a Windows Defender-ügynök állapotához. Ha egy összesített állapotjelentést használ az eszközmegfelelőségi számítási feladatban, megtekintheti azokat az eszközöket, amelyeknek a következő elemek egyikére van szüksége:

- aláírás-frissítés
- újraindítás
- kézi beavatkozás
- teljes vizsgálat
- egyéb, beavatkozást igénylő ügynökállapotok

Bizonyos esetekben távoli szervizműveleteket is alkalmazhat, például elindíthatja az aláírás-frissítést.  A jelentés a **tisztaként** jelentő számítógépek számát is megjeleníti.

Az állapotkategóriákhoz tartozó részletes jelentések ismertetik a figyelmet igénylő, illetve a **tisztaként** jelentő számítógépeket.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Alkalmazások protokollkivételei <!--1035509 eeready-->

Az Intune mobilalkalmazás-kezelésének (MAM) adatátviteli szabályzatában kivételeket hozhat létre, így megnyithat konkrét nem kezelt alkalmazásokat. Az ilyen alkalmazásoknak az informatikai részleg bizalmát kell élvezniük. A létrehozott kivételen kívül az adatátvitel továbbra is csak azokra az alkalmazásokra korlátozódik, amelyeket az Intune kezel, ha az adatátviteli szabályzat **csak felügyelt alkalmazásokhoz** van konfigurálva. Korlátozásokat protokollokkal (iOS) vagy csomagokkal hozhat létre (Android).

Például hozzáadhatja kivételként a Webex-csomagot az MAM adatátviteli szabályzatához. Ezzel lehetővé teszi a kezelt Outlook-emailek Webex-hivatkozásai számára, hogy közvetlenül a Webex alkalmazásban nyíljanak meg. Az adatátvitel továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>A Céges portál témáinak testreszabása hexadecimális kódokkal <!--1049561 eeready-->

Hexadecimális kódokkal testreszabhatja a témák színeit a Céges portál alkalmazásaiban. A hexadecimális kód megadásakor az Intune meghatározza a szövegszín és a háttérszín közötti legnagyobb kontrasztot eredményező szövegszínt a [WCAG 2.0 szabványok](http://www.w3.org/TR/WCAG20) alapján. A szöveg színéről és a céges emblémáról is megtekinthet egy-egy előnézeti képet a **Mobilalkalmazások** > **Céges portál** területen. 

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Eszközkategóriák kiválasztása a „Hozzáférés munkahelyi vagy iskolai rendszerhez” beállításokkal <!-- 1058963 --> 
Ha engedélyezte az [eszközcsoport-leképezést](https://docs.microsoft.com/en-us/intune/device-group-mapping), a Windows 10-felhasználókat felkéri a rendszer egy eszközkategória választására, miután regisztráltak a **Gépház** > **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** területen elérhető **Csatlakozás** gombbal, vagy a kezdőélmény során.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Új Windows Defender Credential Guard-beállítások az Endpoint Protection-beállításokban <!--1102252 --> 

Az új [Windows Defender Credential Guard] (https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] beállítások az **Eszközkonfiguráció** > **Profilok** > **Endpoint Protection** területén találhatók meg. A következő beállítások lesznek hozzáadva: 

- Platformbiztonsági szint: megadhatja, hogy engedélyezve legyen-e a platformbiztonsági szint a következő újraindításkor. A virtualizálás-alapú biztonsághoz biztonságos rendszerindítás szükséges. A virtualizálás-alapú biztonságot igény szerint a közvetlen memória-hozzáférés (DMA) védelmi funkcióinak használatakor is engedélyezheti. A DMA-védelemhez hardveres támogatás szükséges, és csak a megfelelően konfigurált eszközökön alkalmazható.
- Virtualizálás-alapú biztonság: megadhatja, hogy engedélyezve legyen-e a virtualizálás-alapú biztonság a következő újraindításkor. 
- Windows Defender Credential Guard: a Credential Guard a virtualizálás-alapú biztonsággal történő együttes bekapcsolásával megvédheti a hitelesítő adatokat a következő újraindításnál, ha a platformszintű biztonság engedélyezve van a biztonságos újraindítás és a virtualizálás-alapú biztonság funkciókkal. Elérhető beállítások: **Letiltva**, **Engedélyezve UEFI-zárolással**, **Engedélyezve zárolás nélkül**, és **Nincs konfigurálva**. 
  - A „Letiltva” beállítás távolról kikapcsolja a Credential Guardot, ha azt korábban bekapcsolta az „Engedélyezve zárolás nélkül” funkcióval.

  - Az „Engedélyezve UEFI-zárolással” beállítással biztosíthatja, hogy a Credential Guard ne legyen letiltható egy beállításkulccsal vagy egy csoportházirenddel. A beállítás használata után a Credential Guard letiltásához a csoportházirendet „Letiltva” állapotra kell állítania, és el kell távolítania a biztonsági funkciókat a jelen lévő felhasználókkal rendelkező számítógépekről a UEFI-ben megőrzött konfigurációk törléséhez. Amíg megvannak a UEFI-konfigurációk, a Credential Guard engedélyezve marad.

  - Az „Engedélyezve zárolás nélkül” beállítással távolról letilthatja a Credential Guardot egy csoportházirenddel. Azokon az eszközökön, amelyek ezt a beállítást használják, legalább a Windows 10 1511-es verziójának kell futnia.

  - A „Nincs konfigurálva” beállítás nem definiálja a szabályzatbeállítást. A csoportházirend nem írja a szabályzatbeállítást a beállításjegyzékbe, így ez nincs hatással a számítógépekre vagy a felhasználókra. Ha már meg van adva egy beállítás a beállításjegyzékben, az nem módosul.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>A ritkított csomagolású Vállalati Windows Áruház-alkalmazások szinkronizálása és üzembe helyezése <!--1222672 -->
A Vállalati Windows Áruházban vásárolt offline alkalmazások szinkronizálhatók az Intune-portállal. Ezeket az alkalmazásokat eszközcsoportok vagy felhasználói csoportok számára telepítheti. Az offline alkalmazásokat az Intune, és nem az Áruház telepíti.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Jelszavak visszaállítása Android O-eszközökön <!-- 1238299 -->
A regisztrált Android O-eszközökön visszaállíthatja a jelszavakat. Amikor egy „Jelszó visszaállítása” kérelmet küld egy Android O-eszköznek, az egy új eszközfeloldó jelszót vagy egy kezelt profilra vonatkozó kérdést állít be az aktuális felhasználónak. A jelszó vagy a kérdés attól függ, hogy az eszköz rendelkezik-e profiltulajdonossal vagy eszköztulajdonossal, és azonnal életbe lép.

### <a name="local-device-security-option-settings----1251887---"></a>Helyi eszközbiztonsági beállítások <!-- 1251887 -->
A Windows 10-eszközökön az új Helyi eszközbiztonsági beállításokkal adhat meg biztonsági beállításokat. Ezeket a beállításokat az Endpoint Protection kategóriában érheti el, amikor létrehoz egy Windows 10-es eszközkonfigurációs szabályzatot.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Új nyomtatóbeállítások az oktatási profilokban <!-- 1308900 -->

Az oktatási profilok új beállításai a **Nyomtatók** kategória **Nyomtatók**, **Alapértelmezett nyomtató**, **Új nyomtatók hozzáadása** területén érhetők el. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Új adatvédelmi beállítások az eszközkorlátozások számára <!--1308926 -->

Az eszközök számára két új adatvédelmi beállítás érhető el:

- **Felhasználói tevékenységek közzététele**: A megosztott élmények és a feladatváltóban nemrég használt erőforrások megelőzéséhez ezt a beállítást **tiltsa le**.

- **Csak a helyi tevékenységek**: A csak a helyi tevékenységek alapján megosztott használat és a feladatváltóban nemrég használt erőforrások felderítésének megelőzéséhez ezt a beállítást **tiltsa le**.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>A macOS-es Céges portál támogatja a Készülékregisztráció-kezelős regisztrációt <!-- 1352411 -->

A felhasználók a Készülékregisztráció-kezelővel regisztrálhatnak a macOS Céges portálra.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Az Edge böngésző új beállításai <!--1469166 -->

Az Edge böngészőt használó eszközök számára két új beállítás érhető el: **A kedvencek fájl elérési útja** és **A Kedvencek módosításai**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows Information Protection (WIP) által titkosított adatok megjelenítése a Windows keresési találatai között <!-- 1469193 -->

A Windows Information Protection (WIP) szabályzatban egy új beállítás érhető el annak megadásához, hogy a WIP által titkosított adatok megjelenjenek-e a Windows keresési találatai között.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS – üzletági (LOB) alkalmazások támogatása <!-- 1473977 -->
Az Intune macOS-es LOB alkalmazások telepítésével bővíti a funkcióit. Az LOB alkalmazások olyan alkalmazások, amelyek esetén Önnek kell letöltenie a telepítőfájlt, amelyet az Intune-nal telepít az eszközre. A macOS LOB alkalmazástámogatásának részeként a macOS-es LOB alkalmazások előfeldolgozásához a Microsoft Intune macOS alkalmazásburkoló eszközét kell használnia.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Erőforrásfiók-beállítások konfigurálása a Surface Hubokban <!-- 1475674 -->

Távolról konfigurálhatja a Surface Hubok erőforrásfiók-beállításait.

A Surface Hub az erőforrásfiókkal hitelesíthető a Skype/Exchange felé, így bekapcsolódhat az értekezletbe. Célszerű létrehozni egy egyedi erőforrásfiókot, hogy a Surface Hub konferenciateremként jelenjen meg az értekezletben. Az erőforrásfiók megjelenhet például **Konferenciaterem B41/6233** néven.

> [!NOTE]
> - Ha üresen hagy egyes mezőket, azzal felülírja a korábban konfigurált eszközattribútumokat.
>
> - Az erőforrásfiók tulajdonságai dinamikusan változhatnak a Surface Hubon. Például ha be van kapcsolva a jelszóváltoztatás. Így előfordulhat, hogy az Azure-konzol értékei csak egy kis idő múlva jelennek meg valós értékekként az eszközön. 
>
>   Ha meg szeretné tekinteni a Surface Hub aktuálisan konfigurált beállításait, az erőforrásfiók adatait belefoglalhatja a hardverleltárba (amely jelenleg egy 7 napos intervallummal bír), vagy megjelenítheti azokat írásvédett tulajdonságokként. A távoli művelet után a pontosság javítása érdekében lekérheti a paramétereket közvetlenül a művelet futtatása után, így frissítheti a Surface Hub fiókját vagy paramétereit.

### <a name="ios-app-provisioning-configuration----1581650---"></a>iOS-es alkalmazáskiépítési konfiguráció <!-- 1581650 -->
iOS-es alkalmazáskiépítési profilok hozzárendelésével, illetve biztonsági csoportok alkalmazásával vagy kizárásával megelőzheti, hogy lejárjanak az alkalmazásai.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Új beállítások a Windows Defender – biztonsági rés kiaknázása elleni védelemhez <!-- 631893 -->

Hat új **Támadási felület csökkentése** beállítás és bővített **Mappahozzáférés felügyelete: Mappavédelem** funkciók érhetők el. Ezeket a beállításokat az alábbi helyen találhatja meg: Eszközkonfiguráció\Profilok\
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

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Mappavédelem (már implementálva)|Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> **Új**<br>Lemezmódosítás letiltása, lemezmódosítás naplózása|
Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Új Windows Defender alkalmazásőr-beállítások <!-- 1631890 -->

- **Grafikus gyorsítás engedélyezése**

A rendszergazdák engedélyezhetik egy virtuális grafikai processzor használatát a Windows Defender alkalmazásőr számára. Ezzel a beállítással a CPU a vGPU-ra terhelheti a grafikai renderelést. Ez javíthatja a teljesítményt a magas grafikai igényű webhelyekkel történő munka, valamint a tárolón belüli videók megtekintése során.

- **SaveFilestoHost**

A rendszergazdák engedélyezhetik a tárolóban futó Microsoft Edge fájljainak a gazdafájlrendszerbe való áttérését. Ennek a beállításnak a bekapcsolásával a felhasználók letölthetik tárolóban futó Microsoft Edge-fájlokat a gazdafájlrendszerbe.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Felhasználónkénti regisztrációs korlátozások megtekintése <!-- 1634444 -->
A hibaelhárítási panelen megtekintheti az egyes felhasználókra vonatkozó regisztrációs korlátozásokat.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Egy önfrissítő MSI-mobilalkalmazás konfigurálása <!-- 1740840 -->
Az önfrissítő MSI-mobilalkalmazásokat úgy konfigurálhatja, hogy azok figyelmen kívül hagyják a verzióellenőrzési folyamatot. Ez a funkció akkor hasznos, ha nem szeretne versenyhelyzetbe kerülni. Ilyen például akkor fordulhat elő, ha az alkalmazást egyszerre frissíti automatikusan a fejlesztő és az Intune. Mindkettő megpróbálja a Windows-ügyfélen kényszeríteni az alkalmazásverziót, ami üközést eredményezhet.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>A Windows 10 rendszerbiztonsági beállításainak és a későbbi megfelelőségi szabályzatok bővítése <!--1704133 -->

Hamarosan elérhető a Windows 10 megfelelőségi beállításainak bővítése, amely a tűzfalat és a Windows Defender víruskeresőt is kötelezővé teszi.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Alkalmazástársítás belefoglalása vagy kizárása Android Enterprise-csoportok alapján <!-- 1813081 -->
Az alkalmazás-hozzárendelések során és a hozzárendelés típusának kiválasztása után az Android Enterprise (korábbi nevén Android for Work) támogatja a kizárás funkciót.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Kapcsolódó alkalmazáslicenc-készletek Intune-támogatása <!-- 1864117 -->
Az Azure Portalbeli Intune hamarosan a felhasználói felület egyedülálló alkalmazáselemeként támogatja a kapcsolódó alkalmazáslicenc-készleteket. Ezenkívül a Vállalati Microsoft Áruházból szinkronizált, offline licencelt alkalmazások egyetlen alkalmazásbejegyzésben lesznek összesítve, az egyes csomagok üzembe helyezési részleteit pedig migráljuk az egyedülálló bejegyzésbe. Ha meg szeretné tekinteni a kapcsolódó alkalmazáslicenc-készleteket az Azure Portalon, válassza a **Mobilalkalmazások** panel **Alkalmazáslicencek** lehetőségét.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Új felhasználóhitelesítési lehetőség az Apple-eszközök tömeges regisztrálásakor <!-- 747625 -->
Az Intune mostantól lehetővé teszi az eszközök Céges portál alkalmazással való hitelesítését az alábbi regisztrációs módszerek használatakor:

- Apple Készülékregisztrációs program
- Apple School Manager
- Apple Configurator-regisztráció

A Céges portál lehetőség használatakor kényszerítheti az Azure Active Directory többtényezős hitelesítését anélkül, hogy blokkolná ezen regisztrációs módszereket.

A Céges portál lehetőség választásakor az Intune kihagyja a felhasználóhitelesítést az iOS beállítási asszisztensben, és felhasználói affinitáson alapuló regisztrációt végez. Ez azt jelenti, hogy az eszköz kezdetben felhasználó nélküli eszközként lesz regisztrálva, így nem fogja megkapni a felhasználói csoportokhoz tartozó konfigurációkat és szabályzatokat. Ehelyett csak az eszközcsoportoktól fog konfigurációkat és szabályzatokat kapni. Az Intune automatikusan telepíti a Céges portál alkalmazást az eszközön. A Céges portál alkalmazást elindító és abba bejelentkező első felhasználót társítja az Intune az eszközhöz. Ezen a ponton a felhasználó már megkapja a felhasználói csoporthoz tartozó konfigurációkat és szabályzatokat. Ezt a felhasználótársítást csak a regisztráció megismétlésével lehet megváltoztatni.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 -->
Az Intune támogatni fogja az eszközök regisztrációját akár 100 különböző Apple Device Enrollment Program (DEP) vagy Apple School Manager típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Eszközkategóriák kiválasztása a „Hozzáférés munkahelyi vagy iskolai rendszerhez” beállításokkal <!-- 1058963 -->
Ha engedélyezte az [eszközcsoport-leképezést](https://docs.microsoft.com/en-us/intune/device-group-mapping), a Windows 10-felhasználókat felkéri a rendszer egy eszközkategória választására, miután regisztráltak a **Gépház** > **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** területen elérhető **Csatlakozás** gombbal, vagy a kezdőélmény során.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Megfelelőségi szabályzatok alkalmazása eszközcsoportokban lévő eszközökre <!--1307012 -->

Alkalmazhatja majd a megfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználókra. Alkalmazhatja majd a megfelelőségi szabályzatokat eszközcsoportokban lévő eszközökre.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Alkalmazástársítás belefoglalása vagy kizárása csoportok alapján <!-- 1406920 -->

Az alkalmazások társítása során, illetve a társítás típusának kiválasztása után megadhatja a belefoglalni, valamint a kizárni kívánt csoportokat.

### <a name="remote-erase-command-support----1438084---"></a>Távoli törlési parancs támogatása <!-- 1438084 -->

A rendszergazdák távolról is adhatnak majd ki törlési parancsot.

> [!IMPORTANT]
> A törlési parancs nem vonható vissza, ezért legyen óvatos a használatakor.

A törlési parancs eltávolítja az összes adatot az eszközről, az operációs rendszert is ideértve. Emellett az Intune-ból is eltávolítja az eszközt. Nem jelenik meg figyelmeztetés a felhasználónak, és a törlés a parancs kiadása után azonnal megkezdődik.

Beállíthat egy 6 számjegyből álló helyreállítási PIN-kódot. Ezzel a PIN-kóddal feloldhatja az eszköz zárolását a törlést követően, mely után megkezdődik az operációs rendszer újratelepítése. A törlés megkezdése után megjelenik a PIN-kód az eszköz Intune-beli áttekintő paneljén. A PIN-kód a törlés végrehajtása alatt végig látható marad. A törlés után az eszköz eltűnik az Intune rendszerből. Ne felejtse el feljegyezni ezt a helyreállítási PIN-kódot az eszköz helyreállítását végző személy számára.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows Information Protection (WIP) által titkosított adatok megjelenítése a Windows keresési találatai között <!-- 1469193 -->

A Windows Information Protection (WIP) szabályzatban egy új beállítás érhető el annak megadásához, hogy a WIP által titkosított adatok megjelenjenek-e a Windows keresési találatai között.

### <a name="website-learning-mode----1631908---"></a>Webhelytanulási mód <!-- 1631908 -->

Hamarosan megjelenik egy bővítmény az Intune-ban a Windows Information Protection (WIP) Learning módhoz. A WIP szolgáltatással együttműködő alkalmazások adatainak megtekintése mellett hamarosan megtekintheti a webhelyekkel munkahelyi adatokat megosztó eszközök összegzését is. Ezen adatok alapján megállapíthatja, hogy mely webhelyeket kell hozzáadnia a csoportszabályzatokhoz és a WIP-szabályzatokhoz.

### <a name="updates-to-compliance-emails---1637547---"></a>Frissített megfelelőségi e-mailek <!--1637547 -->

Láthatók lesznek a nem megfelelő eszközökről értesítő e-mailekben a nem megfelelő eszközök adatai. A következő cikket frissítjük majd ennek a változásnak megfelelően: [Meg nem felelés esetén végrehajtandó műveletek automatizálása](#actions-for-noncompliance).

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Riasztás a lejárt és hamarosan lejáró tokenekről <!-- 1639263 -->
Az áttekintő lap meg fog jeleníteni egy riasztást a lejárt és hamarosan lejáró tokenekről. Az egyes tokenekhez tartozó riasztásra kattintva elérheti a token részleteinek lapját.  Ha több tokenről szóló riasztásra kattint, akkor a rendszer megjeleníti az adott állapotú tokenek listáját. A rendszergazdáknak meg kell újítaniuk a tokenjeiket, mielőtt lejárnának.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Távoli nyomtatás biztonságos hálózaton keresztül <!-- 1709994  -->
A PrinterOn vezeték nélküli nyomtatási megoldásaival a felhasználók távolról nyomtathatnak, bárhol és bármikor, egy biztonságos hálózaton keresztül. A PrinterOn integrálva lesz az Intune APP SDK-val mind az iOS, mind pedig az Android rendszerhez. Ehhez az alkalmazáshoz az Intune felügyeleti konzol **Alkalmazásvédelmi szabályzatok** paneljével társíthat alkalmazásvédelmi szabályzatokat. A végfelhasználók letölthetik a „PrinterOn for Microsoft” alkalmazást a Play Áruházból vagy az iTunes áruházból, és használhatják azt az Intune rendszerükben.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>A Céges portál alkalmazás jóváhagyása Android for Work rendszerhez <!--1797090 -->
Ha a cég használ Android for Work rendszert, manuálisan jóvá kell hagynia a Céges portál alkalmazást Androidhoz annak érdekében, hogy az továbbra is fogadni tudja az automatikus frissítéseket a felügyelt Google Play Áruházból.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID iOS-eszközökön<!-- 1807377 -->
Az Intune alkalmazásvédelmi szabályzatai mostantól támogatják az iOS-eszközök FaceID-vezérlő beállítását. Ez a beállítás a FaceID funkciót támogató eszközökre vonatkozik (jelenleg csak az iPhone X). Ez a beállítás nem azonos a jelenleg támogatott TouchID-vezérlőkkel. A szervezetek kiválaszthatják, hogy megbízhatónak találják-e a PIN-kérésekhez a FaceID-technológiát a TouchID helyett.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Microsoft Graph API Intune-hoz – Általános elérhetőség <!-- 1833289 -->
Az Microsoft Graph szolgáltatás Intune-hoz készült API-jai programozott hozzáférést nyújtanak olyan adatokhoz és metódusokhoz, amelyekkel automatizálhatja az Intune szolgáltatásban elvégezhető felügyeleti műveleteket.  Most, hogy ezek az API-k **általánosan elérhetővé válnak**, az ügyfelek, partnerek és fejlesztők a segítségükkel integrálhatják azokat a belső fejlesztésű vagy kereskedelmi megoldásaikat, amelyek az Intune-hoz vagy a Microsoft Graphon keresztül elérhető más Microsoft-szolgáltatásokhoz kapcsolódnak vagy azok támogatását igénylik.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Alkalmazásvédelmi szabályzatok  <!-- 679615 -->
Az Intune alkalmazásvédelmi szabályzatai lehetőséget nyújtanak globális szintű alapértelmezett szabályzatok létrehozására, amelyekkel gyorsan beállítható a megfelelő védelem a teljes bérlő összes felhasználója számára.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS Volume Purchase Program-alkalmazások visszavonása  <!-- 820863 -->
Ha egy adott eszközhöz egy vagy több iOS Volume Purchase Program-alkalmazás is tartozik, akkor ezentúl visszavonható az eszköztől az eszközalapú alkalmazáslicenc. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. További információért olvassa el a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakört.

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>iOS Volume Purchasing Program-token licenceinek visszavonása <!-- 820870 -->
Visszavonható lesz az egy adott VPP-tokenhez tartozó összes iOS Volume Purchasing Program-alkalmazás (VPP-alkalmazás) licence.

### <a name="new-ios-device-action------1244701---"></a>Új iOS-eszközművelet   <!-- 1244701 -->
Leállíthatja az iOS 10.3 rendszerű felügyelt eszközöket. Ez a művelet azonnal leállítja az eszközt, anélkül, hogy a végfelhasználót figyelmeztetné. A **Leállítás (csak felügyelt eszköz esetén)** műveletet az eszköztulajdonságoknál találhatja, amikor kiválaszt egy eszközt az **Eszköz** tevékenységprofilban.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Elérhető az Intune-ban a Fiók áthelyezése művelet  <!-- 1573558, 1579830 -->
A **Fiók áthelyezése** művelettel egy bérlőt az egyik Azure skálázási egységből a másikba telepíthet át. A **Fiók áthelyezése** műveletet a felhasználó is kezdeményezheti, amikor az Intune támogatási csoportjához fordul és áthelyezést kér, és a Microsoft is használhatja, ha a szolgáltatás háttérhálózatának módosítása szükségessé válik. A **Fiók áthelyezése** során a bérlő csak olvasható (ROM) módban érhető el. A ROM-mód idején az eszközregisztráció, az eszközök átnevezése, a megfelelőségi állapot frissítése és a hasonló szolgáltatási műveletek sikertelenek lesznek.



<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Office 365-mobilalkalmazások hozzárendelése iOS- és Android-eszközökhöz a regisztrált alkalmazástípussal <!-- 1332318 -->
A **Beépített** alkalmazástípussal könnyebben hozhat létre és rendelhet Office 365-alkalmazásokat a felügyelt iOS- és Android-eszközeihez. Ezek az alkalmazások olyan 0365-alkalmazásokat tartalmaznak, mint a Word, az Excel, a PowerPoint és a OneDrive. Az alkalmazástípushoz konkrét alkalmazásokat rendelhet hozzá, valamint szerkesztheti az alkalmazásadatok konfigurációját.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>A hozzárendelésbeli ütközések feloldása megváltozott az áruházból származó iOS-alkalmazások számára <!-- 1480316 -->
A végfelhasználók változást tapasztalhatnak az áruházbeli iOS-alkalmazások elérhetőségében. Az olyan alkalmazások, amelyek két, **Kötelező és elérhető** és **Nem alkalmazható** között ütköző csoporthoz vannak rendelve, a **Kötelező és elérhető** beállítással oldódnak fel. A módosításnak köszönhetően az ilyen ütközéseket tapasztaló alkalmazások a **Nem alkalmazható** beállítással oldódnak fel.

Ez a módosítás azt a zavart hivatott feloldani, amely akkor keletkezhetett, ha egy alkalmazás több, különböző alkalmazásszándékkal rendelkező csoporthoz volt rendelve.

Ha szeretné, hogy az alkalmazása elérhető legyen az Information Worker Portalon, valamint a céges portálon a novemberi kiadás előtt, két opció közül választhat:

1. Távolítsa el a **Nem alkalmazható** hozzárendelést a csoportból.
2. Hozzon létre egy új csoportot, amely nem tartalmaz **Kötelező és elérhető** hozzárendelt szándékot, majd rendelje a csoporthoz a **Nem alkalmazható** beállítást.

További információ: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md).

> [!Note]
> A megjelenés után nem tekintheti meg vagy módosíthatja a mobileszköz-kezelés alkalmazás-hozzárendeléseit a klasszikus Intune-konzolon. Az Azure-konzollal vagy az Intune Graph API-val azonban elvégezheti az alkalmazás-hozzárendeléseket.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS-alkalmazások PIN-kódjának konfigurálása <!-- 1586774 -->
Hamarosan kérhet PIN-kódot a kívánt iOS-alkalmazások használatához. A PIN-kód megkövetelését és napokban megadott lejárati idejét az Azure Portalon konfigurálhatja. Amikor szükséges, a felhasználóknak új PIN-kódot kell beállítaniuk, ha hozzá szeretnének férni egy iOS-alkalmazáshoz. Ezt a funkciót csak az Intune App SDK alkalmazásvédelmével ellátott iOS-alkalmazások támogatják.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Felhasználóiélmény-frissítés az iOS-hez készült Céges portál alkalmazásban <!--1412866-->

Egy nagyszabású felhasználóiélmény-frissítést adunk ki az iOS-es Céges portál alkalmazáshoz. A frissítés teljes mértékben átalakítja az alkalmazás látványát, modernebb külsőt, valamint könnyebb használhatóságot és elérhetőséget nyújtva. Az iOS-es Céges portál minden funkciója továbbra is ugyanúgy működik.

A frissített, iOS-es Céges portál alkalmazás előzetes verziója elérhető az Apple TestFlight programjában, amelynek keretében kipróbálhatja az alkalmazást, és visszajelzést küldhet róla. Regisztráció a TestFlight-hozzáféréshez: https://aka.ms/intune_ios_cp_testflight. 

![előzetes képek az új ios-es céges portál alkalmazáshoz](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->   
Az Azure Active Directory (Azure AD) használatával korlátozhatja majd a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS-felhasználók átirányítása az új Céges portál alkalmazáshoz <!--1380728-->   
Ha egy végfelhasználó bejelentkezik a Céges portál webhelyre, hogy regisztrálja macOS-eszközét, átirányítjuk az új macOS-es Céges portál alkalmazás letöltési oldalára, hogy azzal fejezhesse be a folyamatot. Ez azoknál a macOS-eszközöknél történik meg, amelyek az OS X El Capitan 10.11-es vagy újabb verzióit futtatják. 


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Intune Managed Browser-támogatás iOS és Android rendszerű eszközök számára <!-- 1374196 -->
2017 októberétől az Intune Managed Browser alkalmazás Androidon kizárólag az Android 4.4 vagy újabb rendszerű eszközöket fogja támogatni. Az Intune Managed Browser alkalmazás iOS-en kizárólag az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
Az Android-eszközt használó végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”



## <a name="notices"></a>Értesítések

Jelenleg nincsenek aktív értesítések.



### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).



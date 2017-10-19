---
title: "Előzetes kiadás"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: abb5612545174e3fd134c38fb763e02d379b50d0
ms.sourcegitcommit: b330045a4f9a807e6e2772c4ed4e1e1148e1f1f9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>A Microsoft Intune előzetes kiadása – 2017. október

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

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Az Azure Active Directory-webhelyekhez szükség lehet az Intune Managed Browser alkalmazásra, és az egyszeri bejelentkezés támogatására is a Managed Browserhez (nyilvános előzetes verzió) <!-- 710595 -->   
Az Azure Active Directory (Azure AD) használatával korlátozhatja majd a webhelyekhez való hozzáférést mobileszközökön az Intune Managed Browser alkalmazással. A felügyelt böngészőben a webhelyadatok biztonságosan lesznek tárolva, és elkülönülnek a felhasználók személyes adataitól. A Managed Browser ezen kívül az Azure AD által védett helyek esetén támogatni fogja az egyszeri bejelentkezést is. A Managed Browserbe való bejelentkezés után, vagy ha a Managed Browsert az Intune által kezelt más alkalmazással használják, lehetővé válik, hogy a Managed Browser használatával anélkül lehessen elérni az Azure AD által védett vállalati helyeket, hogy a felhasználónak meg kellene adnia a hitelesítő adatait. Ez a funkció olyan helyeknél érhető el, mint az Outlook Web Access (OWA) vagy a SharePoint Online, továbbá olyan helyek esetén (például intranet), amelyek az Azure alkalmazásproxyn keresztül érhetőek el.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Regisztrálással kapcsolatos problémák elhárítása <!--- 746324 --->  
A Hibaelhárítás munkaterületen megtalálhatók lesznek a felhasználói regisztrálással kapcsolatos problémák. A hiba adatai és a megoldáshoz javasolt lépések segítséget nyújtanak a rendszergazdának és az ügyfélszolgálati munkatársaknak a hibalehárításban. A rendszer nem jegyez fel minden regisztrálási hibát, és bizonyos hibáknál nem kínál fel megoldási javaslatokat.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Eszközkonfigurációs profilt használó eszközök esetén a rendszergazdák most már konfigurálhatják a tűzfalbeállításokat <!-- 951708 -->   
A rendszergazdák bekapcsolhatják a tűzfalat az eszközökhöz, és különféle protokollokat konfigurálhatnak tartományhoz, valamint privát és nyilvános hálózathoz.  Ezek a tűzfalbeállítások az „Endpoint Protection” profilban találhatók.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>A Windows Defender Application Guard segít megvédeni az eszközöket a szervezet által meghatározott nem megbízható webhelyektől <!-- 958257 -->   
A rendszergazdák az egyes helyeket a Windows Information Protection munkafolyamattal, vagy az eszközkonfiguráció alatt található új „Hálózathatár” (Network boundary) profil használatával jelölhetik meg „megbízható” (trusted) vagy „vállalati” (corporate) típusúként. Ha olyan helyet néznek meg a Microsoft Edge böngészőben, amely nem szerepel a 64-bites Windows 10-es eszköz megbízhatónak jelölt hálózathatárok listáján, akkor az egy Hyper-V virtuális számítógép böngészőjében fog megnyílni.

Az Application Guard az eszközkonfigurációs profilok között, az „Endpoint Protection” profilban található. A rendszergazdák ott konfigurálhatják a virtualizált böngésző és a gazdagép közötti és a nem megbízható és megbízható helyek közötti interakciót, valamint a virtualizált böngészőben generált adatok tárolását. Ahhoz hogy az Application Guard használható legyen egy eszközön, először konfigurálni kell egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>A Windows Defender Application Guard lehetővé teszi Windows 10 Enterprise rendszeren, hogy csak a jogosultsággal rendelkező alkalmazások minősüljenek megbízhatónak <!-- 1031096 -->    
Ma már naponta több ezer rosszindulatú fájlt hoznak létre, így az aláírás-alapú felderítést használó víruskereső használata már nem nyújt elegendő biztonságot a kártevők elleni védelemben, hiszen újabb és újabb típusú támadások jelennek meg. A Windows 10 Enterprise rendszeren használható Windows Defender Application Guard használatával különféle eszközkonfigurációs módokat lehet beállítani, többek között olyat, amelynél az alkalmazások megbízhatónak minősülnek mindaddig, amíg egy víruskereső vagy más biztonsági megoldás le nem tiltotta őket, vagy olyat, amelynél az operációs rendszer csak a vállalat által engedélyezett alkalmazásokat tekinti megbízhatónak. Az alkalmazások megbízhatósága a Windows Defender Application Guardban állítható be.

Az Intune-ban az alkalmazásvezérlési szabályzatok beállíthatók „csak naplózási” vagy kötelező módban is. „Naplózási módban” az alkalmazások nem lesznek letiltva. A „naplózási mód” minden eseményt egy ügyfélnaplóban rögzít. Az is beállítható, hogy csak a Windows-összetevők és a Windows Áruházbeli alkalmazások futtatása legyen engedélyezve, de az Intelligent Security Graphban megbízhatóként meghatározott további alkalmazások futtatása is engedélyezhető.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Új regisztrálási állapot oldal a Windows 10-es regisztrálásokhoz <!--1063201-->    
Most már konfigurálható egy olyan üdvözlő oldal, amely a Windows 10-es eszközök regisztrálását követően jelenik meg a felhasználóknak. A **Regisztrálási állapot képernyője** területen állítható be az az egyéni üzenet és hivatkozás, amely a felhasználónak jelenik meg, amikor regisztrálja Windows 10-es eszközét.  A **Regisztrálási állapot képernyőjén** a felhasználók azt is láthatják, hogy mely szabályzatbeállítások alkalmazása milyen állapotban van az eszközükön.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>A Windows Defender Exploit Guard új behatolásmegelőzési képességeket tartalmazó készlet Windows 10 rendszerhez <!-- 1063615 -->   
A Windows Defender Exploit Guard olyan szabályokat tartalmaz, amelyekkel csökkenthető az alkalmazások rosszindulatú kihasználása, megelőzhetőek a makró- és parancsfájl-fenyegetések, automatikusan letilthatók a nem megbízhatónak tekintett IP-címek, és biztosítható az adatok védelme a zsarolóprogramok és az ismeretlen fenyegetések ellen. A Windows Defender Exploit Guard az alábbi összetevőket tartalmazza:

- A **Támadási felület csökkentése (ASR)** a makró-, parancsfájl- és e-mail-fenyegetések megelőzésére szolgáló szabályokat tartalmaz.
- A **Felügyelt mappahozzáférés** automatikusan letiltja a védett mappák tartalmához való hozzáférést.
- A **Hálózati szűrő** minden alkalmazás esetében letiltja az alacsony megbízhatóságú IP-címek vagy tartományok felé irányuló kimenő adatforgalmat
- A **Biztonsági rések elleni védelem** a memóriára, a vezérlésfolyamra és a szabályzatokra vonatkozó korlátozásokat tartalmaz, amelyekkel megvédhetők az alkalmazások a biztonsági résektől.

### <a name="app-conditional-launch-support----1193313---"></a>Alkalmazásfüggő indítás támogatása <!-- 1193313 -->
A rendszergazdák most már beállíthatnak egy követelményt az Azure felügyeleti portálján, amely a mobilalkalmazás-kezelésen (MAM) keresztül PIN-jelszót követel meg numerikus PIN-kód helyett, amikor az alkalmazás elindul. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune jelen kiadása ezt a funkciót **csak iOS** esetén támogatja. Az Intune a PIN-jelszót a PIN-kódhoz hasonlóan támogatja minimális jelszóhossz megkövetelésével és karakterek és sorozatok ismétlődésének engedélyezésével. A funkció működéséhez az is szükséges, hogy az alkalmazások (vagyis a WXP, az Outlook, a Managed Browser és a Yammer) az Intune App SDK-t integrálják ennek a funkciónak a kódjával, hogy a megcélzott alkalmazásoknál kötelezővé lehessen tenni a PIN-jelszóbeállításokat.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Üzleti alkalmazás verziószáma az eszköz telepítési állapotjelentésében <!-- 1233999 -->  
Az eszköz telepítési állapotjelentése megjeleníti az iOS-es és androidos üzleti alkalmazások verziószámát. A verziószám hasznos lehet az alkalmazás hibakeresésénél, vagy ha olyan eszközöket szeretne megtalálni, amelyek elavult verziószámú alkalmazásokat futtatnak.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Windows 10-es eszközök közös felügyelete <!-- 124445 -->
A közös felügyelet olyan megoldás, amely a hagyományos és a modern felügyelet között teremt átjárhatóságot, és lehetővé teszi a fokozatos áttérést. Közös felügyelet esetén a Windows 10-es eszközöket együttesen felügyeli a Configuration Manager és a Microsoft Intune, és emellett az Azure Active Directoryhoz (AD) és az Azure Active Directoryhoz (Azure AD) is csatlakoztatva vannak.  Ez a konfiguráció lehetővé teszi, hogy idővel át lehessen térni a modern megoldásra, de elegendő időt hagy a vállalatnak, ha pillanatnyilag nincs mód az azonnali áttérésre.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Alkalmazásokhoz való hozzáférés beállítása az eszközön telepített Android biztonsági javítás minimum szintje alapján <!-- 1278463 -->   
A rendszergazdának lehetősége lesz meghatározni, hogy az eszközön milyen minimális szintű Android biztonsági javításnak kell telepítve lennie ahhoz, hogy felügyelt fiók esetén hozzáférést kapjon a felügyelt alkalmazásokhoz.

> [!Note]  
> Ez a funkció csak azokat a biztonsági javítási szinteket határozza meg, amelyeket a Google az Android 6.0 vagy újabb verzióihoz tesz közzé.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Új eszközkorlátozási beállítások Windows 10-hez      <!-- 1308850 -->
-    Üzenetek (csak mobil) – szöveges vagy MMS-üzenetek letiltása
-    Jelszó – beállítások FIPS engedélyezésére, valamint Windows Hello-eszközök és másodlagos eszközök hitelesítéshez való használatára 
-    Képernyő – beállítások GDI-méretezés ki- és bekapcsolására régebbi alkalmazások esetén


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Eszközkorlátozás Windows 10-es teljes képernyős mód esetén <!-- 1308872 -->   
Windows 10-es eszközök esetén lehetőség lesz a teljes képernyős mód kötelezővé tételére, ami a felhasználók számára egy előre meghatározott alkalmazáscsoportot tesz csak elérhetővé.  Ehhez egy Windows 10-es eszközkorlátozási profilt kell létrehozni, és meg kell adni a teljes képernyős beállításokat.

A teljes képernyős mód két lehetőséget támogat: az **egyetlen alkalmazás** módot (csak egy alkalmazás futtatható), és a **több alkalmazás** módot (alkalmazások egy csoportja érhető el).  Önnek kell meghatároznia a felhasználói fiókot és az eszköznevet, amely meghatározza a támogatott alkalmazásokat).  Bejelentkezés után a felhasználó csak a meghatározott alkalmazásokhoz férhet hozzá.  További információt az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) témakörben talál. 

A teljes képernyős módhoz az alábbiak szükségesek:

- MDM-szolgáltatóként az Intune-t kell beállítani.
- A céleszközön már telepítve kell lenniük az alkalmazásoknak.
- Az eszköznek [megfelelően kiépített](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) állapotban kell lennie.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Új eszközkonfigurációs profil hálózathatárok létrehozásához <!-- 1311967 -->   
Létrehoztunk egy **Hálózathatár** nevű eszközkonfigurációs profilt, amely a többi eszközkonfigurációs profil között található. Ezzel a profillal olyan online erőforrásokat határozhat meg, amelyeket vállalatiként és megbízhatóként szeretne definiálni. Ahhoz, hogy az eszközön használható legyen a Windows Defender Application Guard és a Windows Information Protection vagy más funkciók, *először* definiálnia kell az eszközhöz egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.

Definiálhat felhőbeli erőforrásokat, IP-címtartományokat és belső proxykiszolgálókat is, amelyeket megbízhatóként szeretne megjelölni. Definiálás után a hálózathatárt más funkciók is felhasználhatják, például a Windows Defender Application Guard vagy a Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Két további beállítás a Windows Defender víruskeresőhöz <!-- 1338409 -->  
**Fájlblokkolási szint**

| | |
|---|---|
| Nincs konfigurálva | A **Nincs konfigurálva** beállítás a Windows Defender víruskereső alapértelmezett blokkolási szintjét használja, és erős szintű észlelést végez anélkül, hogy a kockázatmentes fájlok észlelésének kockázatát növelné. |
| Magas | A **Magas** beállítás erős szintű észlelést eredményez.
| Magas +  | A **Magas +** beállítás a Magas szintet további védelmi funkciókkal bővíti ki, ami hatással lehet az ügyfélteljesítményre.
| Zéró tolerancia  | A **Zéró tolerancia** minden ismeretlen végrehajtható állományt letilt. |

Noha valószínűtlen, hogy megtörténik, elképzelhető, hogy a **Magas** beállításnál egyes kockázatmentes fájlok is észlelve lesznek.
Javasoljuk, hogy a fájlblokkolás szintjénél az alapértelmezés szerinti **Nincs konfigurálva** beállítást alkalmazza.

**Időtúllépési bővítmény felhőalapú fájlvizsgálathoz**  

| | |
|--|--|
| Másodpercek száma (0-50) | Adja meg azt a maximális időt, ameddig a Windows Defender víruskeresőnek blokkolnia kell a fájlt, amíg meg nem érkezik az eredmény a felhőből. Az alapértelmezett érték 10 másodperc. Az itt megadott érték (legfeljebb 50 másodperc) hozzáadódik ehhez a 10 másodperchez. A vizsgálat a legtöbb esetben a maximális időnél jelentősen rövidebb ideig tart. Az idő növelésével azonban elegendő időt biztosíthat ahhoz, hogy a felhő alaposan megvizsgálja a gyanús fájlokat. Javasoljuk, hogy engedélyezze ezt a beállítást, és értékeként legalább 20 másodpercet adjon meg. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Támogatás a Symantec Cloud Certification Authorityhez (CA)  <!-- 1333638 -->    
Az Intune mostantól támogatást nyújt a Symantec Cloud CA-hez, amely lehetővé teszi, hogy az Intune Tanúsítvány-összekötő a Symantec Cloud CA-től származó PKCS-tanúsítványokat bocsásson ki az Intune által felügyelt eszközökhöz. Ha már használja az Intune Tanúsítvány-összekötőt a Microsoft hitelesítésszolgáltatóval (CA), akkor az Intune Tanúsítvány-összekötő telepítésénél hozzáadhatja a Symantec CA-támogatást is.


### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>A Céges portál eszközbeállítási munkafolyamatával kapcsolatos újdonságok <!--1490692-->  
Továbbfejlesztjük az androidos céges portál alkalmazás eszközbeállítási munkafolyamatát. Nyelvezete felhasználóbarátabb, vállalatra szabottabb lesz. Képernyőit – ahol lehet – összevonjuk. 

### <a name="block-unsupported-samsung-knox-device-activation------1490695----"></a>Nem támogatott Samsung Knox-eszközök aktiválásának letiltása <!--- 1490695 --->  
Az MDM-regisztráció során a Céges portál alkalmazás csak akkor kísérli meg a Samsung KNOX-aktiválást, ha az eszköz szerepel a [támogatott KNOX-eszközök listáján](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Ezzel a korlátozással elkerülhetők az MDM-regisztrációt megakadályozó KNOX-aktiválási hibák. Azokat az eszközöket, melyek nem támogatják a Samsung KNOX-aktiválást, szabványos Android-eszközként regisztrálja a rendszer. Előfordulhat, hogy egy Samsung eszköz néhány modellje támogatja a KNOX platformot, míg mások nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse az eszköz viszonteladójával, hogy kompatibilis-e a KNOX-szal.

Az alábbi Samsung eszközök nem támogatják a KNOX platformot, így ezeket az androidos Céges portál alkalmazás natív Android-eszközként fogja regisztrálni:

| **Eszköz neve** | **Eszköz modellszáma** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN Windows 10-ez eszközökhöz <!-- 1512457 -->  
Windows 10-es rendszerű eszközökhöz Citrix VPN konfigurálható. A Citrix VPN az **Alapszintű VPN** panelen, a *Kapcsolat típusának kiválasztása* listában választható ki a Windows 10 VPN-konfigurálásakor vagy később.

> [!Note]
> A Citrix-konfiguráció iOS és Android rendszerekhez már korábban is elérhető volt.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Google Play Protect-támogatás Androidon <!-- 908720  -->  
Az Android Oreo megjelenésétől kezdve a Google egy új védelmi funkciót vezetett be Google Play Protect néven, amely lehetővé teszi, hogy a felhasználók és a szervezetek biztonságos alkalmazásokat és biztonságos Android-rendszerképeket futtassanak. Az Intune támogatást fog nyújtani a Google Play Protect-funkciókhoz, például a SafetyNet távoli igazoláshoz.  A rendszergazdák olyan megfelelőségi szabályzatokat állíthatnak be, amelyek megkövetelik a Google Play Protect konfigurálását és biztonságos állapotát. A **SafetyNet eszközigazolás** beállítás azt követeli meg, hogy az eszköz kapcsolódjon egy Google-szolgáltatáshoz, amely igazolja, hogy az eszköz a biztonságot tekintve kifogástalan állapotban van. Android for Work esetén a rendszergazda megadhat egy olyan konfigurációs profilbeállítást is, amely megköveteli, hogy a telepített alkalmazások állapotát Google Play-szolgáltatások ellenőrizzék.  A feltételes hozzáférés meg is akadályozhatja, hogy a felhasználó hozzáférjen a vállalati erőforrásokhoz, amennyiben az eszköz nem felel meg a Google Play Protect követelményeinek. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Annak megakadályozása, hogy a felhasználók megváltoztassák az eszköz rendszeridejét <!-- 1333292 -->
Egy [Androidos egyéni eszközszabályzat](custom-settings-android.md) használatával megakadályozható, hogy a felhasználó megváltoztassa az Android-eszköz rendszeridejét.
Ehhez hozzon létre egy egyéni Android-szabályzatot ezzel az URI-val: ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange, állítsa **TRUE** (igaz) értékre, majd rendelje hozzá a kívánt csoportokhoz.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Alkalmazásvédelmi szabályzat-hozzárendelések megtekintése hibakereséshez <!--  1475003 -->
A következő kiadásban megjelenik az **Alkalmazásvédelmi szabályzat** lehetőség is a hibakeresési panelen elérhető **Hozzárendelések** legördülő listában. Az alkalmazásvédelmi szabályzatok lehetőség kiválasztásával megtekintheti a kiválasztott felhasználókhoz hozzárendelt alkalmazásvédelmi szabályzatokat.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Regionális Apple App Store-ra korlátozott iOS-alkalmazások létrehozása <!-- 1281692 -->
Az Apple App Store által felügyelt alkalmazás létrehozásánál területi beállításként lehetőség lesz meghatározni az országot.

> [!NOTE]  
> Jelenleg csak olyan Apple App Store által felügyelt alkalmazásokat lehet létrehozni, amelyek az USA-beli áruházban érhetőek el.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Apple-áruház országának kiválasztása VPP-alkalmazások szinkronizálásához <!-- 1332311 -->  
VPP-token feltöltésénél lesz lehetőség a Mennyiségi vásárlási program (VPP) országának konfigurálására. Az Intune a megadott VPP-ország áruházából az összes területi beállításhoz tartozó VPP-alkalmazást szinkronizálja.

> [!NOTE]  
> Az Intune jelenleg egy adott VPP-ország áruházából csak azokat a VPP-alkalmazásokat szinkronizálja, amelyek megfelelnek annak a területi Intune-beállításnak, amelyben az Intune-bérlőt létrehozták.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS-es VPP-alkalmazások felhasználókhoz és eszközökhöz rendelt licenceinek frissítése <!-- 1305564 -->  
Az iOS-es VPP-token úgy is konfigurálható, hogy frissítse az összes olyan alkalmazást, amelyet az adott tokenhez vásároltak az Intune szolgáltatáson keresztül. Az Intune észlelni fogja, ha az adott VPP-alkalmazáshoz frissítés érhető el az alkalmazás-áruházban, és ezt követően automatikusan leküldi a frissítéseket az eszközre, amikor az legközelebb bejelentkezik.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Új beállítások a Windows 10 Team eszközkorlátozási profiljához <!--- 1308838  -->
Számos új beállítási lehetőséget teszünk elérhetővé a Windows 10 Team eszközkorlátozási profiljához, hogy hatékonyabban lehessen vezérelni a Surface Hub-eszközöket.
A profilról további információt a [Windows 10 Team eszközkorlátozási beállításai](device-restrictions-windows-10-teams.md) című témakörben talál.

### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Támogatás a Windows 10-kiadások frissítési szabályzatához <!-- 903672(archived), 1119689 -->  
A Windows 10-hez létrehozhat olyan kiadásfrissítési szabályzatot, amely a Windows 10-es eszközöket az alábbi verziókra frissíti: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education és Windows 10 Professional Education N. A Windows 10 kiadásfrissítéseiről a [Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md) című témakörből tájékozódhat.

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Távoli támogatás Windows és Windows Mobile rendszerű eszközökhöz <!-- 1070473 -->    
Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani a Windows és Windows Mobile rendszerű eszközök felhasználóinak.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Eszközök vizsgálata Windows Defenderrel <!-- 1280988  1280990   -->
Windows 10 rendszerű felügyelt eszközökön a Windows Defender víruskereső használható lesz **gyorsvizsgálat** és **teljes vizsgálat** futtatására, valamint **aláírások frissítésére**. Az eszköz áttekintő paneljén válassza ki az eszközön futtatni kívánt műveletet. A rendszer megerősítést fog kérni, mielőtt a parancsot lefuttatná az eszközön. 

**Gyorsvizsgálat**: A gyorsvizsgálat azokat a helyeket vizsgálja meg, ahol a kártevő általában indításhoz lehet regisztrálva, például a beállításkulcsok és az ismert indítási Windows-mappák. A gyorsvizsgálat átlagosan öt percig tart. Az **Állandó valós idejű védelem** a fájlok megnyitásakor, bezárásakor és a mappa megjelenítésekor megvizsgálja a fájlokat. Ez a beállítás a gyorsvizsgálattal együtt segít kiszűrni azokat a kártevőket, amelyek akár a rendszert, akár a kernelt fertőzték meg. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Teljes vizsgálat**: Teljes vizsgálatot olyan eszközökön célszerű futtatni, amelyeken korábban kártevő-fenyegetést találtak, hogy feltárhatóak legyenek a kártevő esetleges inaktív komponensei mélyebb tisztítás érdekében, továbbá igény szerinti vizsgálatra is használható. A teljes vizsgálat körülbelül egy órát vehet igénybe. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Aláírások frissítése**: Az aláírások frissítése parancs frissíti a Windows Defender víruskereső kártevő-definícióit és aláírásait. Ezzel biztosítható, hogy a Windows Defender víruskereső hatékonyan észlelhesse a kártevőket. Ez a funkció csak a Windows 10 rendszert futtató eszközökön érhető el, és internetkapcsolat szükséges hozzá. 

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker-eszközkonfiguráció <!-- 1397398 -->  
A **Windowsos titkosítás > Alapbeállítások** területen elérhetővé válik a **Figyelmeztetés más lemeztitkosítás esetén** beállítás is, amellyel letilthatja azt a [figyelmeztetést](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption), amely akkor jelenik meg, ha az eszközön más lemeztitkosítás is használatban van.  A figyelmeztetés a felhasználó hozzájárulását kéri a BitLocker eszközön való beállításához, és a hozzájárulásig letiltja a BitLocker telepítését.  Az új beállítással letiltható a végfelhasználó számára megjelenő figyelmeztetés.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>A Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál fenntartási módba kerül <!--1428681-->
2017 októberétől a Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál alkalmazás fenntartási módba kerül. Ez azt jelenti, hogy ezeken a platformokon továbbra is jár támogatás az alkalmazásokhoz és a meglévő használati forgatókönyvekhez (például regisztrálás és megfelelőség). Az alkalmazások továbbra is letölthetők a meglévő kiadási csatornákon keresztül, például a Microsoft Áruházból. 

A fenntartási módban ezekhez az alkalmazásokhoz azonban már csak fontos biztonsági frissítések lesznek elérhetőek. Más típusú frissítések és új funkciók már nem jelennek meg ezekhez az alkalmazásokhoz. Ha az új funkciókat szeretné használni, azt javasoljuk, hogy frissítse az eszközt Windows 10 vagy Windows 10 Mobile rendszerre. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>A munkahelyi és a személyes profilok közötti másolás és beillesztés letiltása Android for Work-eszközökön <!-- 1098994 -->   
Lehetséges lesz úgy konfigurálni az Android for Work-profilt, hogy az letiltsa a munkahelyi és személyes fiókok közötti másolást és beillesztést. Az új beállítás a **Munkahelyi profil beállításai** között, az **Android for Work** platform **Eszközkorlátozások** területén található.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Munkahelyi profillal rendelkező Androidhoz készült Céges portál alkalmazás új működési módja <!---1485783--->
Android for Work-eszköz munkahelyi profillal történő regisztrálása után a munkahelyi profil Céges portál alkalmazása végzi el az eszközön a felügyeleti feladatokat. Hacsak nem használ MAM-használatot támogató alkalmazást a személyes profilban, az androidos Céges portál alkalmazásra már nincs szükség. Ezért a munkahelyi profil hatékony használhatósága érdekében a munkahelyi profil sikeres regisztrálása után az Intune elrejti a személyes Céges portál alkalmazást.

Az Androidhoz készült Céges portál alkalmazás a személyes profilban bármikor engedélyezhető. Ehhez keresse meg a [Céges portál alkalmazást a Play Áruházban](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal), és koppintson az **Engedélyezés** lehetőségre.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Bővítmények az Intune MAM-hez és az androidos Outlookhoz <!-- 1450688 -->
Az Office-csapat néhány hét múlva jelenti be az Androidhoz készült Outlookhoz használható bővítmények megjelenését. A bővítménykészlet már most is elérhető az Outlookhoz Windows és iOS rendszereken, valamint weben és Mac gépeken. Mivel a bővítmények felügyelete az Exchange-en keresztül történik, a felhasználók másolhatnak és megoszthatnak adatokat és üzeneteket az Outlook és a nem felügyelt bővítményalkalmazások között, kivéve ha az Exchange-adminisztrátor kikapcsolta a bővítményekhez való hozzáférést. 

A bővítmények felhasználói hozzáférését az Exchange-adminisztrátorral együttműködve kezelheti, biztosítva, hogy a MAM adatvédelmi szabályzatok érvényesek legyenek a bővítményekre is.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ha az Exchange-szabályzatok már megakadályozzák a bővítmények telepítését vagy közvetlen telepítését, akkor nincs további teendője. A MAM-szabályzatok a várakozásoknak megfelelően lesznek alkalmazva. Ha azonban megadott olyan MAM-szabályzatokat, amelyek korlátozzák az androidos Outlookban a kivágási, másolási és beillesztési műveleteket, de az Exchange-ben nem állított be bővítményszabályzatot, akkor számítani kell rá, hogy a felhasználók alapértelmezés szerint telepíthetnek az Outlookhoz bővítményeket. Ezek a bővítmények hozzáférhetnek az üzenetek törzséhez, tárgyához és más tulajdonságaihoz. Ha szeretné megakadályozni, hogy a felhasználó bővítményeket telepíthessen, kérje meg az Exchange-adminisztrátort, hogy távolítsa el a „Saját Marketplace-alkalmazások” és a „Saját egyéni alkalmazások” szerepköröket.

Az Exchange-beállítás változása érinteni fogja az Outlookot Windows és iOS rendszeren, a weben, Mac gépen és mobileszközön is. 

#### <a name="what-do-i-need-to-do"></a>Mit kell tennem?
Minél hamarabb ellenőrizze az Exchange-szabályzatot. Tájékoztassa az informatikai és támogató munkatársakat. Ha bármilyen konkrét kérdése van, forduljon támogatási szolgálatunkhoz. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Felhasználók és eszközök társítási entitásgyűjteménye jelenik meg az Intune-adattárház adatmodelljében <!-- 1187917 -->
A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre. Az adatmodell a Power BI-fájlon (PBIX) keresztül érhető el az adattárház Intune-oldaláról az OData-végpont használatával vagy egyéni ügyfél létrehozásával.




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266  846515 -->     
A *Meg nem felelés esetén végrehajtandó műveletek* a megfelelési szabályzatokkal kapcsolatos új funkció, amellyel a nem megfelelő eszközökön lehet műveleteket végezni. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Új jelentés a régebbi iOS-verziójú iOS-eszközök listájával   <!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** munkaterületről lehet majd elérni. A jelentésben megtekintheti az iOS frissítési szabályzatok által megcélzott és elérhető frissítésekkel rendelkező felügyelt iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>A Windows 10-es eszközkorlátozási profil új beállításai
<!--- 978575, 1308849, -->
A Windows Defender SmartScreen kategóriában új beállításokat adunk a Windows 10-es eszközkorlátozási profilhoz.

A Windows 10-es eszközkorlátozási profillal kapcsolatban lásd: [Windows 10-es és újabb eszközkorlátozási beállítások]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Az Android for Work Lookout-támogatása <!-- 1087312 -->   
A Lookouttal rendelkező Intune-összekötők támogatni fogják az Android for Work rendszerű eszközöket a Lookout for Work alkalmazás használatakor. A Lookout alkalmazást a tárolón kívül vagy belül egyaránt telepítheti.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune App Protection és Citrix MDX fejlesztői eszközök <!-- 709185 -->
Az eszközöket és az alkalmazásokat a Citrix XenMobile MDX és a Microsoft Intune kombinációjával is kezelheti. Így az eszközök kezelésénél egyaránt igénybe veheti az Intune alkalmazásvédelmi szabályzatát és a Citrix mVPN-technológiáját.

Hozzáférhet egy kódtárhoz, amely a Citrix MDX mVPN-technológiával integráltan tartalmazza az Intune iOS és Android rendszerhez készült alkalmazásburkoló eszközét és az Intune App SDK-t.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Új mobileszköz-védelmi partner   <!-- 954681 -->
A Microsoft Intune-nal integrálható, Zimperium által irányított, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

#### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció?
A kockázatfelmérés a Zimperiumot futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Zimperium által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, amelyekkel az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása  <!-- 676614 -->   
A helyszíni Exchange Connector használatához több ügyfél-hozzáférési kiszolgálói (CAS) szerepkörrel is rendelkezhet. A fő CAS kiesése esetén például az Exchange Connector kap egy kérelmet, hogy térjen vissza más ügyfél-hozzáférési kiszolgálókhoz. Ez a funkció biztosítja, hogy a szolgáltatás ne szakadjon meg.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager felügyeleti csomag az Exchange Connectorhoz <!-- 885457 -->   
A System Center Operations Manager Exchange Connectorhoz készült felügyeleti csomagja segíteni fog az Exchange Connector naplófájljainak elemzésében. Ez a felügyeleti csomag számos megoldást nyújt az Intune monitorozására hibaelhárítás esetén.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171127, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még október eleje előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. Decemberre az összes regisztrált eszköz ki lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.


## <a name="intune-apps"></a>Intune-alkalmazások

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Az androidos eszközök kapcsolati információk elérésére irányuló kéréseinek továbbfejlesztett támogatása <!--1484985-->   
Gyakran előfordul, hogy a felhasználóknak engedélyt kell adniuk az androidos Céges portál alkalmazásnak a Kapcsolatok használatára. Ha ezt egy végfelhasználó elutasítja, egy alkalmazásbeli értesítés fogja figyelmeztetni feltételes hozzáférési engedély megadására.

### <a name="secure-startup-remediation-for-android---1490712--"></a>Biztonságos indítást támogató kockázatcsökkentés Android-eszközökhöz<!--1490712-->     
Az Android-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma.


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS-felhasználók átirányítása az új Céges portál alkalmazáshoz <!--1380728-->   
Ha egy végfelhasználó bejelentkezik a Céges portál webhelyre, hogy regisztrálja macOS-eszközét, átirányítjuk az új macOS-es Céges portál alkalmazás letöltési oldalára, hogy azzal fejezhesse be a folyamatot. Ez azoknál a macOS-eszközöknél történik meg, amelyek az OS X El Capitan 10.11-es vagy újabb verzióit futtatják. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Támogatás tanúsítványalapú hitelesítéshez az iOS-es céges portálon <!--1029830-->
Mostantól támogatjuk a tanúsítványalapú hitelesítést (CBA) az iOS-es céges portál alkalmazásban. A CBA-hitelesítést használó felhasználóknak meg kell adniuk a felhasználónevüket, majd a „Bejelentkezés tanúsítvánnyal” hivatkozásra kell koppintaniuk. A CBA már eddig is támogatva volt az androidos és a windowsos céges portál alkalmazásban. További információt a [Bejelentkezés a céges portál alkalmazásba](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) oldalon talál.

<!-- the following are present prior to 1710 -->

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a>Újdonságok a Céges portál kereső funkcióiban<!--1331697-->  
Továbbfejlesztjük az alkalmazáskeresési lehetőségeket, első lépésben a [Céges portál weboldalról](https://portal.manage.microsoft.com) elérhetőket. A keresések a Név és a Leírás mezőben megadott információkon túl az alkalmazáskategóriák megadásával finomíthatók. Az eredményeket alapértelmezés szerint relevancia alapján állítja sorrendbe a rendszer. 

Ezeket a változtatásokat az iOS-es felhasználók is észlelni fogják, mert a Céges portál weboldal része az iOS-es Céges portál alkalmazásnak. Az androidos és windowsos Céges portál alkalmazásokba az elkövetkező hónapokban lesznek bevezetve hasonló újítások.

A relevancia megállapításának finomításán még dolgozunk, ezért várjuk a tapasztalatokkal kapcsolatos visszajelzéseket, melyek a Céges portál weboldalának alján található „Visszajelzés” hivatkozást használva küldhetők el.

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>A Windows 10-es Céges portál alkalmazásban elérhetővé válik a Frissítés művelet <!--1132468-->  
A Windows 10-es céges portál alkalmazásban lehetőség lesz az adatok frissítésére. Ezt vagy lefelé húzással, vagy asztali gépeken az F5 billentyű megnyomásával lehet majd elvégezni.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>A regisztrációval vagy anélkül is elérhető alkalmazások mostantól anélkül telepíthetőek, hogy a rendszer a regisztrálást kérné. <!-- 1334712 -->
Azok a céges alkalmazások, amelyek regisztrációval és anélkül is elérhetőek az Androidhoz készült Céges portál alkalmazásban, anélkül is telepíthetők lesznek, hogy a rendszer a regisztrálást kérné.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Nagy méretű ikonok megjelenítése az iOS-es Céges portálhoz <!-- 1454593 -->
Elhárítottunk egy ismert problémát azzal kapcsolatban, ahogyan az iOS-es Céges portál ikonokat jelenít meg az alkalmazás címében. A 120x120 pixeles vagy nagyobb méretű feltöltött ikonok most már teljes méretben jelennek meg az alkalmazás címében a [Céges portál webhelyén] (https://portal.manage.microsoft.com) és az iOS-es Céges portál alkalmazás oldalain.

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Intune Managed Browser-támogatás iOS és Android rendszerű eszközök számára <!-- 1374196 -->
2017 októberétől az Intune Managed Browser alkalmazás Androidon kizárólag az Android 4.4 vagy újabb rendszerű eszközöket fogja támogatni. Az Intune Managed Browser alkalmazás iOS-en kizárólag az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. Az Managed Browser továbbra is használható lesz korábbi verziójú Android vagy iOS rendszerű eszközökön, de az alkalmazás újabb verziói nem lesznek telepíthetők, és előfordulhat, hogy az alkalmazás bizonyos képességei nem lesznek hozzáférhetők. Javasoljuk, hogy frissítse az ilyen eszközök operációs rendszerét egy támogatott verzióra.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Javított hibaüzenet, ha a felhasználó elérte a regisztrálható eszközök engedélyezett maximális számát <!-- 1270370 -->
A végfelhasználók az általános hibaüzenet helyett a következő barátságos és praktikus hibaüzenetet kapják: „Elérte a regisztrálható eszközök rendszergazda által engedélyezett maximális számát. Távolítson el egy regisztrált eszközt, vagy kérjen segítséget a rendszergazdától.”




## <a name="notices"></a>Értesítések

### <a name="device-and-app-management-integration----677972---"></a>Az eszköz- és alkalmazáskezelés integrációja <!-- 677972 -->   
Mivel az Intune-alapú mobileszköz-kezelés (MDM) és a mobilalkalmazás-kezelés (MAM) most már egyaránt elérhető az Azure Portalról, az Intune elkezdte integrálni az alkalmazás- és az eszközkezelés rendszergazdai felületét. Ez a változás az eszköz- és az alkalmazáskezelés egyszerűsítését szolgálja.

Az MDM és a MAM változásairól az [Intune-ügyfélszolgálat blogjában](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) tájékozódhat.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->   
Az Apple bejelentette, hogy 2017 tavaszától bizonyos követelményeket ír elő az Application Transport Security (ATS, alkalmazás átviteli biztonsága) esetében. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.


### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>A felügyelt eszközök új elérési útja a Graph API-ban <!-- 1586728 -->  
Az Intune októberi kiadásában megváltoznak a felügyelt eszközök eléréséhez a Graph API béta verziójában használható útvonalak.

| | |
|--|--|
| Jelenlegi útvonal |  https://graph.microsoft.com/beta/managedDevices |
| Új elérési út | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Október folyamán még mindkét útvonal használható lesz. Az októberi kiadás után azonban csak az új útvonal lesz használható.  Ha a Graph API-t használja felügyelt eszközök elérésére, frissítse a parancsfájlokat és az alkalmazásokat az új útvonallal, és ellenőrizze azok megfelelő működését. A további változásokról a [Graph API változásnaplójában](https://developer.microsoft.com/en-us/graph/docs/concepts/changelog) tájékozódhat.

### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).

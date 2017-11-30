---
title: "Újdonságok a Microsoft Intune-ban"
titlesuffix: Azure portal
description: "Az Azure-beli Intune-portál újdonságai"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/18/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f3f9832a643628cf18aee6131b9c8a43843e94d
ms.sourcegitcommit: 71e6e80b7370024624ce2e5fad1ca5b372975748
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a [jövőbeni változtatásokról](#whats-coming), a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi verziókról](whats-new-archive.md) is.

> [!Note]
> Idővel ezeknek a funkcióknak egy jelentős része Configuration Managerrel végzett hibrid telepítések esetén is támogatott lesz. Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-november-13-2017"></a>2017. november 13-i hét

### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Elérhető a macOS-hez készült Céges portál alkalmazás <!--1541700-->
A macOS-hez készült Intune Céges portál frissített felhasználói felületet kapott, és ezentúl átláthatóbban jeleníti meg a regisztrált eszközökkel kapcsolatos, felhasználók számára szükséges információkat és megfelelőségi értesítéseket. És ha az Intune Céges portál már telepítve van az eszközre, a macOS-hez készült Microsoft AutoUpdate gondoskodni fog a frissítéséről is. Az új, macOS-hez készült Intune Céges portál alkalmazást az Intune Céges portál webhelyről, macOS-eszközzel bejelentkezve töltheti le.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>A Microsoft Planner mostantól a mobilalkalmazás-kezelési MAM-lista engedélyezett alkalmazásai közé tartozik  <!-- 1248473 -->
A Microsoft Planner alkalmazás iOS és Android rendszerű eszközök számára készült verziói a mobilalkalmazás-kezelési MAM-lista engedélyezett alkalmazásai közé tartoznak. Az alkalmazás az összes bérlőre vonatkozóan konfigurálható az Azure Portal Intune App Protection paneljén.
- További tudnivalók az [engedélyezett alkalmazások MAM-listájáról](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Az Alkalmazásonkénti VPN követelmény frissítési gyakorisága iOS-eszközök esetén   <!-- 1547061 -->  
A rendszergazdák mostantól eltávolíthatják az alkalmazásonkénti VPN követelményét az iOS-eszközökről. Az érintett eszközök állapota a következő Intune-bejelentkezés után frissül (ez általában 15 percen belül következik be).  

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Támogatás a System Center Operations Manager Exchange Connectorhoz készült felügyeleti csomagjához <!-- 885457 -->
A System Center Operations Manager (SCOM) mostantól elérhető, az Exchange Connectorhoz készült felügyeleti csomagja segít az Exchange Connector naplófájljainak elemzésében. Ez számos lehetőséget nyújt a szolgáltatás figyelésére hibaelhárítás esetén.

## <a name="week-of-november-6-2017"></a>2017. November 6-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Windows 10-es eszközök közös felügyelete <!-- 1243445 -->
A közös felügyelet olyan megoldás, amely a hagyományos és a modern felügyelet között teremt átjárhatóságot, és lehetővé teszi a fokozatos áttérést. Közös felügyelet esetén a Windows 10-es eszközöket együttesen felügyeli a Configuration Manager és a Microsoft Intune, és emellett az Azure Active Directoryhoz (AD) és az Azure Active Directoryhoz (Azure AD) is csatlakoztatva vannak.  Ez a konfiguráció lehetővé teszi, hogy idővel át lehessen térni a modern megoldásra, de elegendő időt hagy a vállalatnak, ha pillanatnyilag nincs mód az azonnali áttérésre.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Új regisztrálási állapot oldal a Windows 10-es regisztrálásokhoz <!--1063201-->    
Most már konfigurálható egy olyan üdvözlő oldal, amely a Windows 10-es eszközök regisztrálását követően jelenik meg a felhasználóknak. A **Regisztrálási állapot képernyője** területen állítható be az az egyéni üzenet és hivatkozás, amely a felhasználónak jelenik meg, amikor regisztrálja Windows 10-es eszközét.  A **Regisztrálási állapot képernyőjén** a felhasználók azt is láthatják, hogy mely szabályzatbeállítások alkalmazása milyen állapotban van az eszközükön.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>A Windows-regisztráció korlátozása az operációs rendszer verziója alapján <!-- 245498 -->
Az Intune-rendszergazdák mostantól megadhatják az eszközregisztrációhoz megkövetelt minimális és maximális Winows 10-verziót. Ezek a korlátozások a **Platformkonfigurációk** panelen állíthatók be.

Az Intune továbbra is támogatja Windows 8.1 rendszerű számítógépek és telefonok regisztrációját. Alsó és felső korlát azonban csak a Windows 10 verzióihoz állítható be. A 8.1-es eszközök regisztrációjának engedélyezéséhez az alsó korlátot üresen kell hagyni.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>A Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztások <!-- 1631236 -->
Új Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztás érhető el a **Microsoft Intune** > **Eszközregisztráció** > **Áttekintés** oldalon. Ez a riasztás azt mutatja meg, hogy az AutoPilot-programban hány eszközhöz nincs hozzárendelve AutoPilot Deployment-profil. A riasztás adatai alapján a profilok létrehozhatók és a hozzárendelés nélküli eszközökhöz rendelhetők. A riasztásra kattintva megjelenik a Windows AutoPilot-eszközök részletes adatokat is tartalmazó, teljes listája. További információt a [Windows-eszközök regisztrálása a Windows AutoPilot Deployment Program használatával](https://docs.microsoft.com/intune/enrollment-autopilot) című témakörben találhat.

### <a name="device-management"></a>Eszközkezelés

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Frissítés gomb az eszközök listájához <!-- 1333581 -->
Mivel az eszközlista nem frissül automatikusan, a listában megjelenő eszközök a Frissítés gombbal frissíthetők.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Támogatás a Symantec Cloud Certification Authorityhez (CA)  <!-- 1333638 -->    
Az Intune mostantól támogatást nyújt a Symantec Cloud CA-hez, amely lehetővé teszi, hogy az Intune Tanúsítvány-összekötő a Symantec Cloud CA-től származó PKCS-tanúsítványokat bocsásson ki az Intune által felügyelt eszközökhöz. Ha már használja az Intune Tanúsítvány-összekötőt a Microsoft hitelesítésszolgáltatóval (CA), akkor az Intune Tanúsítvány-összekötő telepítésénél hozzáadhatja a Symantec CA-támogatást is.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Új elemek az eszközleltárban <!--1404455 -->
Ebben a kiadásban a következő új elemek jelentek meg a [regisztrált eszközök által rögzített leltárban](device-inventory.md):

- Wi-Fi MAC-címe
- Teljes tárterület
- Összes szabad terület
- MEID
- Előfizető szolgáltatója


### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Alkalmazásokhoz való hozzáférés beállítása az eszközön telepített Android biztonsági javítás minimum szintje alapján <!-- 1278463 -->   
A rendszergazdának lehetősége lesz meghatározni, hogy az eszközön milyen minimális szintű Android biztonsági javításnak kell telepítve lennie ahhoz, hogy felügyelt fiók esetén hozzáférést kapjon a felügyelt alkalmazásokhoz.

> [!Note]  
> Ez a funkció csak azokat a biztonsági javítási szinteket határozza meg, amelyeket a Google az Android 6.0 vagy újabb verzióihoz tesz közzé.

#### <a name="app-conditional-launch-support----1193313---"></a>Alkalmazásfüggő indítás támogatása <!-- 1193313 -->
A rendszergazdák most már beállíthatnak egy követelményt az Azure felügyeleti portálján, amely a mobilalkalmazás-kezelésen (MAM) keresztül PIN-jelszót követel meg numerikus PIN-kód helyett, amikor az alkalmazás elindul. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune jelen kiadása ezt a funkciót **csak iOS** esetén támogatja. Az Intune a PIN-jelszót a PIN-kódhoz hasonlóan támogatja minimális jelszóhossz megkövetelésével és karakterek és sorozatok ismétlődésének engedélyezésével. A funkcióhoz az alkalmazásoknak (például WXP, Outlook, Managed Browser, Yammer) integrálniuk kell az Intune App SDK-t ennek a funkciónak a kódjával, hogy a megcélzott alkalmazásoknál kötelezővé lehessen tenni a PIN-jelszóbeállításokat.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Üzleti alkalmazás verziószáma az eszköz telepítési állapotjelentésében <!-- 1233999 -->
Ettől a kiadástól kezdve az eszköz telepítési állapotjelentése megjeleníti az iOS-es és androidos üzletági alkalmazások verziószámát. A verziószám hasznos lehet az alkalmazás hibakeresésénél, vagy ha olyan eszközöket szeretne megtalálni, amelyek elavult verziószámú alkalmazásokat futtatnak.


### <a name="device-configuration"></a>Eszközök konfigurálása
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Eszközkonfigurációs profilt használó eszközök esetén a rendszergazdák most már konfigurálhatják a tűzfalbeállításokat <!-- 951708 -->   
A rendszergazdák bekapcsolhatják a tűzfalat az eszközökhöz, és különféle protokollokat konfigurálhatnak tartományhoz, valamint privát és nyilvános hálózathoz.  Ezek a tűzfalbeállítások az „Endpoint Protection” profilban találhatók.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>A Windows Defender Application Guard segít megvédeni az eszközöket a szervezet által meghatározott nem megbízható webhelyektől <!-- 958257 -->   
A rendszergazdák az egyes helyeket a Windows Information Protection munkafolyamattal, vagy az eszközkonfiguráció alatt található új „Hálózathatár” (Network boundary) profil használatával jelölhetik meg „megbízható” (trusted) vagy „vállalati” (corporate) típusúként. Ha olyan helyet néznek meg a Microsoft Edge böngészőben, amely nem szerepel a 64-bites Windows 10-es eszköz megbízhatónak jelölt hálózathatárok listáján, akkor az egy Hyper-V virtuális számítógép böngészőjében fog megnyílni.

Az Application Guard az eszközkonfigurációs profilok között, az „Endpoint Protection” profilban található. A rendszergazdák ott konfigurálhatják a virtualizált böngésző és a gazdagép közötti és a nem megbízható és megbízható helyek közötti interakciót, valamint a virtualizált böngészőben generált adatok tárolását. Ahhoz hogy az Application Guard használható legyen egy eszközön, először konfigurálni kell egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.  

#### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>A Windows Defender Application Guard lehetővé teszi Windows 10 Enterprise rendszeren, hogy csak a jogosultsággal rendelkező alkalmazások minősüljenek megbízhatónak <!-- 1031096 -->    
Ma már naponta több ezer rosszindulatú fájlt hoznak létre, így az aláírás-alapú felderítést használó víruskereső használata már nem nyújt elegendő biztonságot a kártevők elleni védelemben, hiszen újabb és újabb típusú támadások jelennek meg. A Windows 10 Enterprise rendszeren használható Windows Defender Application Guard használatával különféle eszközkonfigurációs módokat lehet beállítani, többek között olyat, amelynél az alkalmazások megbízhatónak minősülnek mindaddig, amíg egy víruskereső vagy más biztonsági megoldás le nem tiltotta őket, vagy olyat, amelynél az operációs rendszer csak a vállalat által engedélyezett alkalmazásokat tekinti megbízhatónak. Az alkalmazások megbízhatósága a Windows Defender Application Guardban állítható be.

Az Intune-ban az alkalmazásvezérlési szabályzatok beállíthatók „csak naplózási” vagy kötelező módban is. „Naplózási módban” az alkalmazások nem lesznek letiltva. A „naplózási mód” minden eseményt egy ügyfélnaplóban rögzít. Az is beállítható, hogy csak a Windows-összetevők és a Windows Áruházbeli alkalmazások futtatása legyen engedélyezve, de az Intelligent Security Graphban megbízhatóként meghatározott további alkalmazások futtatása is engedélyezhető.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>A Windows Defender Exploit Guard új behatolásmegelőzési képességeket tartalmazó készlet Windows 10 rendszerhez <!-- 1063615 -->   
A Windows Defender Exploit Guard olyan szabályokat tartalmaz, amelyekkel csökkenthető az alkalmazások rosszindulatú kihasználása, megelőzhetőek a makró- és parancsfájl-fenyegetések, automatikusan letilthatók a nem megbízhatónak tekintett IP-címek, és biztosítható az adatok védelme a zsarolóprogramok és az ismeretlen fenyegetések ellen. A Windows Defender Exploit Guard az alábbi összetevőket tartalmazza:

- A **Támadási felület csökkentése (ASR)** a makró-, parancsfájl- és e-mail-fenyegetések megelőzésére szolgáló szabályokat tartalmaz.
- A **Felügyelt mappahozzáférés** automatikusan letiltja a védett mappák tartalmához való hozzáférést.
- A **Hálózati szűrő** minden alkalmazás esetében letiltja az alacsony megbízhatóságú IP-címek vagy tartományok felé irányuló kimenő adatforgalmat
- A **Biztonsági rések elleni védelem** a memóriára, a vezérlésfolyamra és a szabályzatokra vonatkozó korlátozásokat tartalmaz, amelyekkel megvédhetők az alkalmazások a biztonsági résektől.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén <!-- 790537 -->

Az Intune felügyeleti bővítményével Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat tölthet fel az Intune-ba. A bővítmény kiegészíti a Windows 10 mobileszköz-kezelési (MDM-) funkcióit, és könnyebbé teszi a modern felügyeletre való váltást. További részleteket a [PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén](intune-management-extension.md) című témakörben találhat.

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Új eszközkorlátozási beállítások Windows 10-hez      <!-- 1308850 -->
-    Üzenetek (csak mobil) – szöveges vagy MMS-üzenetek letiltása
-    Jelszó – beállítások FIPS engedélyezésére, valamint Windows Hello-eszközök és másodlagos eszközök hitelesítéshez való használatára 
-    Képernyő – beállítások GDI-méretezés ki- és bekapcsolására régebbi alkalmazások esetén

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Eszközkorlátozás Windows 10-es teljes képernyős mód esetén <!-- 1308872 -->   
Windows 10-es eszközök esetén lehetséges a teljes képernyős mód kötelezővé tétele, ami a felhasználók számára egy előre meghatározott alkalmazáscsoportot tesz csak elérhetővé.  Ehhez egy Windows 10-es eszközkorlátozási profilt kell létrehozni, és meg kell adni a teljes képernyős beállításokat.

A teljes képernyős mód két lehetőséget támogat: az **egyetlen alkalmazás** módot (csak egy alkalmazás futtatható), és a **több alkalmazás** módot (alkalmazások egy csoportja érhető el).  Önnek kell meghatároznia a felhasználói fiókot és az eszköznevet, amely meghatározza a támogatott alkalmazásokat).  Bejelentkezés után a felhasználó csak a meghatározott alkalmazásokhoz férhet hozzá.  További információt az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) témakörben talál. 

A teljes képernyős módhoz az alábbiak szükségesek:

- MDM-szolgáltatóként az Intune-t kell beállítani.
- A céleszközön már telepítve kell lenniük az alkalmazásoknak.
- Az eszköznek [megfelelően kiépített](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) állapotban kell lennie.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Új eszközkonfigurációs profil hálózathatárok létrehozásához <!-- 1311967 -->   
Létrehoztunk egy **Hálózathatár** nevű eszközkonfigurációs profilt, amely a többi eszközkonfigurációs profil között található. Ezzel a profillal olyan online erőforrásokat határozhat meg, amelyeket vállalatiként és megbízhatóként szeretne definiálni. Ahhoz, hogy az eszközön használható legyen a Windows Defender Application Guard és a Windows Information Protection vagy más funkciók, *először* definiálnia kell az eszközhöz egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.

Definiálhat felhőbeli erőforrásokat, IP-címtartományokat és belső proxykiszolgálókat is, amelyeket megbízhatóként szeretne megjelölni. Definiálás után a hálózathatárt más funkciók is felhasználhatják, például a Windows Defender Application Guard vagy a Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Két további beállítás a Windows Defender víruskeresőhöz <!-- 1338409 -->  
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

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN Windows 10-ez eszközökhöz <!-- 1512457 -->  
A Citrix VPN konfigurálható Windows 10 rendszerű eszközökhöz. A Citrix VPN az **Alapszintű VPN** panelen, a *Kapcsolat típusának kiválasztása* listában választható ki a Windows 10 VPN-konfigurálásakor vagy később.

> [!Note]
> A Citrix-konfiguráció iOS és Android rendszerekhez már korábban is elérhető volt.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>A Wi-Fi-kapcsolatok támogatják az előmegosztott kulcsok használatát iOS rendszer esetén <!-- 1550823 -->
Az ügyfelek konfigurálhatják a Wi-Fi-profilokat úgy, hogy azok előmegosztott kulcsokat (PSK) használjanak a WPA/WPA2-Personal-kapcsolatokhoz iOS-eszközökön. Ezek a profilok akkor lesznek leküldve a felhasználó eszközére, amikor regisztrálja az eszközt az Intune-ban.

A profilnak az eszközre való leküldése után a következő lépés a profil konfigurációjától függ.  Ha automatikus csatlakozásra van beállítva, akkor ezt teszi, amikor a hálózatra legközelebb szükség lesz.  Manuálisan csatlakozó profil esetén a felhasználónak kell aktiválnia a kapcsolatot.  

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>A felügyelt alkalmazások naplóinak elérése iOS rendszeren <!-- 1469920 -->
Azon végfelhasználók, akiknél telepítve van a Managed Browser alkalmazás, a Microsoft által közzétett valamennyi alkalmazás felügyeleti állapotát láthatják és naplófájlokat küldhetnek a felügyelt iOS-alkalmazásaik hibaelhárításához.

A Managed Browser hibaelhárítási módjának iOS-eszközökön való engedélyezéséről [A felügyelt alkalmazások naplóinak elérése a Managed Browser használatával iOS rendszeren](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) című témakörben találhat további információt.

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Újdonságok az iOS rendszerre készült Céges portál 2.9.0-s verziójának eszközbeállítási munkafolyamatával kapcsolatban <!---1417174--->

Továbbfejlesztettük az iOS rendszerre készült Céges portál alkalmazás eszközbeállítási munkafolyamatát. Nyelvezete felhasználóbarátabb lett, képernyőit – ahol lehetett – összevontuk. Ezenkívül a nyelvezetet cégéhez igazítottuk, ezért az Ön cégének neve jelenik meg a telepítés során látható szövegekben. A frissített munkafolyamatot a  [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-app-ui.md) oldalon tekintheti meg.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>A felhasználói entitás tartalmazza a legújabb felhasználói adatokat az adattárház adatmodelljében <!-- 1544273 -->
Az Intune-adattárház adatmodelljének első verziója csak a legújabb Intune-előzményadatokat tartalmazta. A jelentéskészítők így nem tudták felmérni a felhasználók aktuális állapotát. Ebben a frissítésben a **Felhasználói entitás** a legújabb felhasználói adatokkal lesz feltöltve.


## <a name="week-of-october-30-2017"></a>2017. október 30-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Az üzletági iOS- és Android-alkalmazás verziószáma látható <!-- 1380712 -->

Az Intune alkalmazásai mostantól megjelenítik az üzletági iOS- és Android-alkalmazások verziószámait. A számok az Azure Portal alkalmazáslistáján, valamint az Alkalmazás áttekintése panelen jelennek meg. A végfelhasználók az alkalmazásszámot a céges portál alkalmazásban és a webportálon tekinthetik meg.

__Teljes verziószám:__ A teljes verziószám azonosítja az alkalmazás egy konkrét verzióját. A szám az alábbi formátumban jelenik meg: _Verzió_(_Build_). Például: 2.2(2.2.17560800)

A teljes verziószám két részből áll:

 - **Verzió**  
   A verziószám az alkalmazás természetes nyelven olvasható kiadási száma. A végfelhasználók ezzel azonosítják az alkalmazás különböző kiadásait.

 - **Buildszám**  
    A buildszám egy olyan belső szám, amelyet alkalmazásdetektáláshoz és az alkalmazások szoftveres felügyeletéhez használnak. A buildszám az alkalmazás olyan iterációira vonatkozik, amely a kód változásaira hivatkozik.

A verziószámokról és az üzletági alkalmazások fejlesztéséről további információt a [Bevezetés a Microsoft Intune App SDK használatába](app-sdk-get-started.md#line-of-business-app-version-numbers) című cikkben találhat.

#### <a name="device-and-app-management-integration----677972---"></a>Az eszköz- és alkalmazáskezelés integrációja <!-- 677972 -->   
Mivel az Intune-alapú mobileszköz-kezelés (MDM) és a mobilalkalmazás-kezelés (MAM) most már egyaránt elérhető az Azure Portalról, az Intune elkezdte integrálni az alkalmazás- és az eszközkezelés rendszergazdai felületét. Ez a változás az eszköz- és az alkalmazáskezelés egyszerűsítését szolgálja.

Az MDM és a MAM változásairól az [Intune-ügyfélszolgálat blogjában](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) tájékozódhat.

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Új regisztrálási figyelmeztetések Apple-eszközökhöz <!-- 1471790 -->
A regisztrálás áttekintési oldalán hasznos figyelmeztetések jelennek meg a rendszergazdák számára az Apple-eszközök felügyeletével kapcsolatban. A figyelmeztetések akkor jelennek meg az Áttekintés lapon, amikor az Apple MDM leküldéses értesítései lejárnának vagy már lejártak, amikor a Készülékregisztrációs program lejárna vagy már lejárt, illetve akkor, amikor nem hozzárendelt eszközök vannak a Készülékregisztrációs programban.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Tokencsere támogatása alkalmazáskonfigurációhoz eszközregisztráció nélkül <!-- 1080364 -->

A tokeneket az alkalmazáskonfigurációk dinamikus értékeihez használhatja olyan eszközökön található alkalmazásokhoz, amelyek nincsenek regisztrálva. További információ: [Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközregisztráció nélkül](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Frissítések a Windows 10-es Céges portál alkalmazáshoz <!--1299474-->
Frissítettük a Windows 10-es Céges portál alkalmazás beállítások oldalát, hogy egységesebbek legyenek a beállítások és a beállításoknál elvégezhető felhasználói műveletek. Az elrendezését is átalakítottuk, hogy jobban igazodjon a többi Windows-alkalmazáséhoz. [Az alkalmazásfelhasználói felület újdonságai](whats-new-app-ui.md) oldalon talál előtte/utána összehasonlító képeket.

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Végfelhasználóknak szóló információ a Windows 10-es-eszközök megtekinthető adatairól <!--1337920-->
A Windows 10-es Céges portál alkalmazásban található Eszköz részletei képernyőhöz hozzáadtuk a **Tulajdonjog típusa** oldalt. A felhasználók így közvetlenül az Intune végfelhasználói dokumentáció ezen oldaláról tájékozódhatnak az adatvédelemről. Ezt az információt az **About** (Információk) képernyőről is elérhetik.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Felhasználói visszajelzések küldése az androidos Céges portál alkalmazásban <!--1165249-->
Az androidos Céges portál alkalmazás mostantól végfelhasználói visszajelzés küldésére szólít fel. A visszajelzés közvetlenül a Microsofthoz érkezik, és lehetőséget nyújt a végfelhasználók számára, hogy értékelhessék az alkalmazást a nyilvános Google Play Áruházban. A visszajelzés küldése nem kötelező, és a felhasználók könnyen bezárhatják a felszólítást, hogy folytathassák a munkát az alkalmazásban.

#### <a name="update-to-what-device-details-an-organization-can-see---1616825--"></a>Frissítettük, hogy a szervezet az eszköz részleteinek mely adatait láthatja <!--1616825-->
Az androidos Céges portál alkalmazás mostantól geokerítések használatával is védheti a vállalati erőforrásokhoz történő hozzáférést. A rendszer a hálózati adatok, mint például az IP-cím, az alapértelmezett átjáró és a tartománynévrendszer (DNS) adatai alapján dönti el, hogy biztosít-e hozzáférést a vállalati erőforrásokhoz.

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Segítségnyújtás a felhasználóknak az Androidhoz készült céges portál alkalmazás használatában <!---1573324, 1573150, 1558616, 1564878--->

Az Androidhoz készült Céges portál alkalmazás olyan utasításokkal bővült, amelyekkel a végfelhasználók könnyebben megérthetik, és – ahol lehetséges – egyedül megoldhatják az új használati eseteket.
- A végfelhasználókat a program az (Azure Active Directory portálra irányítja) [https://account.activedirectory.windowsazure.com/r/#/profile], ahol eltávolíthatják az eszközöket, ha elérték a maximálisan hozzáadható eszközök számát.
- A végfelhasználók ekkor utasításokat kapnak, amelyekkel [kijavíthatják az aktiválási hibákat a Samsung KNOX-eszközökön](https://go.microsoft.com/fwlink/?linkid=859718), vagy [kikapcsolhatják az energiatakarékos üzemmódot](/intune-user-help/power-saving-mode-android). Ha a megoldások egyike sem oldja meg a problémát, segítséget nyújtunk a [naplófájlok a Microsoftnak való küldéséhez](/intune-user-help/send-logs-to-microsoft-ios).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Új „Feloldás” művelet az Android-eszközök számára <!---1583480--->

Az Androidhoz készült céges portál alkalmazás egy új „Feloldás” műveletet vezet be az _Eszközbeállítások frissítése_ lapon. A beállítás kiválasztásával a végfelhasználó közvetlenül ahhoz a beállításhoz kerül, amely az eszköz nem megfelelőségét okozza. Az Androidhoz készült céges portál alkalmazás ezt a műveletet jelenleg az [eszköz PIN-kódja](/intune-user-help/set-your-pin-or-password-android), [az USB-hibakeresés](/intune-user-help/you-need-to-turn-off-usb-debugging-android) és az [Ismeretlen források](/intune-user-help/you-need-to-turn-off-unknown-sources-android) beállításokhoz támogatja.

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Eszköztelepítési állapotjelző az androidos Céges portálhoz <!---1565657--->
Az androidos Céges portál alkalmazás egy telepítési állapotjelzőt jelenít meg a felhasználó számára az eszközregisztráció során. Az állapotjelző a következő új állapotokat jeleníti meg: „Az eszköz beállítása...”, ezután „Az eszköz regisztrálása...”, majd „Az eszköz regisztrációjának befejezése...”, végül „Az eszköz beállításának befejezése...”.

## <a name="week-of-october-23-2017"></a>2017. október 23-i hét

### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Támogatás tanúsítványalapú hitelesítéshez az iOS-es céges portálon <!--1029830-->
Mostantól támogatjuk a tanúsítványalapú hitelesítést (CBA) az iOS-es céges portál alkalmazásban. A CBA-hitelesítést használó felhasználóknak meg kell adniuk a felhasználónevüket, majd a „Bejelentkezés tanúsítvánnyal” hivatkozásra kell koppintaniuk. A CBA már eddig is támogatva volt az androidos és a windowsos céges portál alkalmazásban. További információt a [Bejelentkezés a céges portál alkalmazásba](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) oldalon talál.

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>A regisztrációval vagy anélkül is elérhető alkalmazások mostantól anélkül telepíthetőek, hogy a rendszer a regisztrálást kérné. <!-- 1334712 -->

Azok a céges alkalmazások, amelyek regisztrációval és anélkül is elérhetőek az Androidhoz készült Céges portál alkalmazásban, mostantól anélkül is telepíthetők, hogy a rendszer regisztrációt kérne.

## <a name="week-of-october-16-2017"></a>2017. október 16-i hét
### <a name="device-enrollment"></a>Eszközök beléptetése
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>A Windows AutoPilot üzembe helyezési program támogatása a Microsoft Intune-ban <!-- 747617  -->
Mostantól használhatja az Intune-nal a Windows AutoPilot üzembe helyezési programot, amellyel lehetővé teheti, hogy a felhasználók az informatikai szolgálat közreműködése nélkül helyezzék üzembe vállalati eszközeiket. A kezdőélményt (OOBE) testre szabhatja, és útmutatást nyújthat a felhasználóknak ahhoz, hogy eszközeiket az Azure AD-hez csatlakoztassák, és azokta az Intune-ban regisztrálják. A Microsoft Intune és a Windows AutoPilot együttes használatával kiküszöbölhető az operációsrendszer-lemezképek üzembe helyezésének, fenntartásának és kezelésének feladatai. További részletekért lásd: [Windows-eszközök regisztrálása a Windows AutoPilot Deployment Program használatával](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Gyors üzembe helyezési útmutató az eszközregisztráláshoz <!-- 1425655 --> 
Az **Eszközregisztrálásnál** már elérhető a gyors üzembe helyezési útmutató, amelyben a platformkezeléssel és a regisztrációs folyamat konfigurálásával kapcsolatos információs táblázatot talál. Minden tételhez egy rövid leírás tartozik, valamint hivatkozások olyan forrásokra, amelyek lépésenkénti útmutatót és dokumentációt tartalmaznak, és amelyekkel leegyszerűsíthető a folyamat.

#### <a name="device-categorization----1427491---"></a>Eszközök kategorizálása <!-- 1427491 -->
Az **Eszközök > Áttekintés** panelen található regisztrált eszközök platformdiagramja platformok szerint (Android, iOS, macOS, Windows és Windows Mobile) rendezi az eszközöket.  A másféle operációs rendszert futtató eszközök az „Egyéb” kategóriában találhatóak.  Ilyenek lehetnek például a Blackberry, a Nokia és más gyártók eszközei.  

A bérlőhöz tartozó érintett eszközök megtekintéséhez válassza a **Kezelés > Minden eszköz** elemet, majd használja a **Szűrőt** az **Operációs rendszer** mezőre.

### <a name="device-management"></a>Eszközkezelés
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Új mobileszköz-védelmi partner   <!-- 954681 -->  
A Microsoft Intune-nal integrálható, Zimperium által irányított, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése.

##### <a name="how-integration-with-intune-works"></a>Hogyan működik az Intune-nal való integráció
A kockázatfelmérés a Zimperiumot futtató eszközökről gyűjtött telemetriai adatokon alapul. Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Zimperium által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, amelyekkel az észlelt fenyegetések alapján engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>A Windows 10-es eszközkorlátozási profil új beállításai <!--- 978575, 1308849, -->  
A Windows Defender SmartScreen kategóriában új beállításokat adunk a Windows 10-es eszközkorlátozási profilhoz.

A Windows 10-es eszközkorlátozási profillal kapcsolatban lásd: [Windows 10-es és újabb eszközkorlátozási beállítások]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Távoli támogatás Windows és Windows Mobile rendszerű eszközökhöz <!-- 1070473 -->  
Az Intune-ból a külön megvásárolható [TeamViewer](https://www.teamviewer.com) szoftverrel lehet távsegítséget nyújtani a Windows és Windows Mobile rendszerű eszközök felhasználóinak.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Eszközök vizsgálata Windows Defenderrel <!-- 1280988  1280990   -->
Windows 10 rendszerű felügyelt eszközökön a Windows Defender víruskereső használható **gyorsvizsgálat** és **teljes vizsgálat** futtatására, valamint **aláírások frissítésére**. Az eszköz áttekintő paneljén válassza ki az eszközön futtatni kívánt műveletet. A rendszer megerősítést fog kérni, mielőtt a parancsot lefuttatná az eszközön. 

**Gyorsvizsgálat**: A gyorsvizsgálat azokat a helyeket vizsgálja meg, ahol a kártevő általában indításhoz lehet regisztrálva, például a beállításkulcsok és az ismert indítási Windows-mappák. A gyorsvizsgálat átlagosan öt percig tart. Az **Állandó valós idejű védelem** a fájlok megnyitásakor, bezárásakor és a mappa megjelenítésekor megvizsgálja a fájlokat. Ez a beállítás a gyorsvizsgálattal együtt segít kiszűrni azokat a kártevőket, amelyek akár a rendszert, akár a kernelt fertőzték meg. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Teljes vizsgálat**: Teljes vizsgálatot olyan eszközökön célszerű futtatni, amelyeken korábban kártevő-fenyegetést találtak, hogy feltárhatóak legyenek a kártevő esetleges inaktív komponensei mélyebb tisztítás érdekében, továbbá igény szerinti vizsgálatra is használható. A teljes vizsgálat körülbelül egy órát vehet igénybe. A vizsgálat végén a felhasználók saját eszközeiken nézhetik meg a vizsgálat eredményeit. 

**Aláírások frissítése**: Az aláírások frissítése parancs frissíti a Windows Defender víruskereső kártevő-definícióit és aláírásait. Ezzel biztosítható, hogy a Windows Defender víruskereső hatékonyan észlelhesse a kártevőket. Ez a funkció csak a Windows 10 rendszert futtató eszközökön érhető el, és internetkapcsolat szükséges hozzá. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Az Azure-beli Intune-portál Intune-os hitelesítésszolgáltató oldaláról eltávolítottuk az Engedélyezés/Letiltás gombot <!-- 1400455 -->
 Az Intune-beli tanúsítvány-összekötő beállításánál egy lépést szükségtelenné teszünk. Jelenleg először le kell tölteni a tanúsítvány-összekötőt, és ezután engedélyezni kell azt az Intune-konzolon. Ha azonban letiltja az összekötőt az Intune-konzolon, az összekötő továbbra is kibocsát tanúsítványokat.

##### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Októbertől az Engedélyezés/Letiltás gomb nem jelenik meg többé az Azure Portal Hitelesítésszolgáltató lapján. Az összekötő funkció továbbra is változatlan marad. Az Intune-ban regisztrált eszközökhöz továbbra is üzembe lesznek helyezve a tanúsítványok. A tanúsítvány-összekötőt továbbra is le lehet tölteni, és telepíteni is lehet. A tanúsítványok kibocsátásának leállítását azonban most már nem a tanúsítvány-összekötő letiltásával, hanem annak telepítésével lehet elérni.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Ha jelenleg letiltott állapotban van a tanúsítvány-összekötője, akkor azt el kell távolítania.

### <a name="device-configuration"></a>Eszközök konfigurálása
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Új beállítások a Windows 10 Team eszközkorlátozási profiljához <!--- 1308838 -->
Az új kiadásban számos új beállítási lehetőséget tettünk elérhetővé a Windows 10 Team eszközkorlátozási profiljához, hogy hatékonyabban lehessen vezérelni a Surface Hub-eszközöket.

A profilról további információt a [Windows 10 Team eszközkorlátozási beállításai](device-restrictions-windows-10-teams.md) című témakörben talál.

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Annak megakadályozása, hogy a felhasználók megváltoztassák az eszköz rendszeridejét <!-- 1333292 -->
Egy [Androidos egyéni eszközszabályzat](custom-settings-android.md) használatával megakadályozható, hogy a felhasználó megváltoztassa az Android-eszköz rendszeridejét.

Ehhez hozzon létre egy egyéni Android-szabályzatot ezzel az URI-val: ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Állítsa **TRUE** (igaz) értékre, majd rendelje hozzá a kívánt csoportokhoz.

#### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker-eszközkonfiguráció <!-- 1397398 -->
A **Windowsos titkosítás > Alapbeállítások** területen elérhetővé a **Figyelmeztetés más lemeztitkosítás esetén** beállítás is, amellyel letilthatja azt a [figyelmeztetést](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption), amely akkor jelenik meg, ha az eszközön más lemeztitkosítás is használatban van.  A figyelmeztetés a végfelhasználó hozzájárulását kéri a BitLocker eszközön való beállításához, és a hozzájárulásig letiltja a BitLocker telepítését.  Az új beállítással letiltható a végfelhasználó számára megjelenő figyelmeztetés.


### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>A Volume Purchase Program for Business-alkalmazások mostantól szinkronizálva lesznek az Intune-bérlővel <!-- 800882 -->  
Az iTunes Connectben megadott, megfelelő jogosultságokkal rendelkező Volume Purchase Program (VPP) for Business-tagoknak külsős fejlesztők is terjeszthetik alkalmazásaikat. Ezek a VPP for Business-tagok be tudnak jelentkezni a Volume Purchase Program App Store áruházba, és ott meg tudják venni azokat az alkalmazásokat, amelyekre szükségük van.

Ebben a kiadásban a végfelhasználók által a VPP for Business keretében megvásárolt alkalmazások Intune-bérlőikkel szinkronizálják magukat.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Apple-áruház országának kiválasztása VPP-alkalmazások szinkronizálásához <!-- 1332311 -->  
VPP-token feltöltésénél lehetőség van a Mennyiségi vásárlási program (VPP) országának konfigurálására. Az Intune a megadott VPP-ország áruházából az összes területi beállításhoz tartozó VPP-alkalmazást szinkronizálja.

> [!NOTE]  
> Az Intune jelenleg egy adott VPP-ország áruházából csak azokat a VPP-alkalmazásokat szinkronizálja, amelyek megfelelnek annak a területi Intune-beállításnak, amelyben az Intune-bérlőt létrehozták.


### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>A munkahelyi és a személyes profilok közötti másolás és beillesztés letiltása Android for Work-eszközökön <!-- 1098994 -->
Ebben a kiadásban lehetséges úgy konfigurálni az Android for Work-profilt, hogy az letiltsa a munkahelyi és személyes fiókok közötti másolást és beillesztést. Az új beállítás a **Munkahelyi profil beállításai** között, az **Android for Work** platform **Eszközkorlátozások** területén található.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Regionális Apple App Store-ra korlátozott iOS-alkalmazások létrehozása <!-- 1281692 -->
Az Apple App Store által felügyelt alkalmazás létrehozásánál területi beállításként lehetőség lesz meghatározni az országot.

> [!Note]  
> Jelenleg csak olyan Apple App Store által felügyelt alkalmazásokat lehet létrehozni, amelyek az USA-beli áruházban érhetőek el.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS-es VPP-alkalmazások felhasználókhoz és eszközökhöz rendelt licenceinek frissítése <!-- 1305564 -->  
Az iOS-es VPP-token úgy is konfigurálható, hogy frissítse az összes olyan alkalmazást, amelyet az adott tokenhez vásároltak az Intune szolgáltatáson keresztül. Az Intune észlelni fogja, ha az adott VPP-alkalmazáshoz frissítés érhető el az alkalmazás-áruházban, és ezt követően automatikusan leküldi a frissítéseket az eszközre, amikor az legközelebb bejelentkezik.

A VPP-token beállításáról és az automatikus frissítésekről lásd: [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal] (/intune/vpp-apps-ios).


### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Felhasználók és eszközök társítási entitásgyűjteménye jelenik meg az Intune-adattárház adatmodelljében <!-- 1187917 -->
A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre. Az adatmodell a Power BI-fájlon (PBIX) keresztül érhető el az adattárház Intune-oldaláról az OData-végpont használatával vagy egyéni ügyfél létrehozásával.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Szabályzatmegfelelőség ellenőrzése Windows 10-es frissítési körökhöz <!-- 1067886 -->
A Windows 10-es frissítési körök szabályzatjelentéseit meg lehet majd tekinteni a Szoftverfrissítések > Frissítési körök telepítési állapota szerint területen. A szabályzatjelentés tartalmazza a konfigurált frissítési körök telepítési állapotát. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Új jelentés a régebbi iOS-verziójú iOS-eszközök listájával   <!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** munkaterületről lehet elérni. A jelentésben megtekintheti az iOS frissítési szabályzatok által megcélzott és elérhető frissítésekkel rendelkező felügyelt iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Alkalmazásvédelmi szabályzat-hozzárendelések megtekintése hibakereséshez <!--  1475003 -->
A következő kiadásban megjelenik az **Alkalmazásvédelmi szabályzat** lehetőség is a hibakeresési panelen elérhető **Hozzárendelések** legördülő listában. Az alkalmazásvédelmi szabályzatok lehetőség kiválasztásával megtekintheti a kiválasztott felhasználókhoz hozzárendelt alkalmazásvédelmi szabályzatokat.



## <a name="week-of-october-2-2017"></a>2017. október 2-i hét
### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>A Céges portál eszközbeállítási munkafolyamatával kapcsolatos újdonságok <!--1490692-->
Továbbfejlesztettük az androidos Céges portál alkalmazás eszközbeállítási munkafolyamatát. Nyelvezete felhasználóbarátabb, vállalatra szabottabb. Képernyőit – ahol lehetett – összevontuk. Az újításokat megtekintheti a [ felhasználói felület újdonságait](whats-new-app-ui.md#week-of-october-2-2017) bemutató oldalon.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Az androidos eszközök kapcsolati információk elérésére irányuló kéréseinek továbbfejlesztett támogatása <!--1484985-->

Gyakran előfordul, hogy a felhasználóknak engedélyt kell adniuk az androidos Céges portál alkalmazásnak a Kapcsolatok használatára. Ha ezt egy végfelhasználó elutasítja, mostantól egy alkalmazásbeli értesítés fogja figyelmeztetni feltételes hozzáférési engedély megadására. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Biztonságos indítást támogató kockázatcsökkentés Android-eszközökhöz<!--1490712-->

Az Android-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>További leküldéses értesítések az Android Oreo rendszert használó végfelhasználóknak a Céges portál alkalmazásban <!--1475932-->

A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy az Android Oreo Céges portál alkalmazása mikor végez háttérműveleteket (például szabályzatok lekérése az Intune szolgáltatástól). Ez átláthatóbbá teszi a végfelhasználók számára a Céges portál az eszközeiken végzett felügyeleti feladatait. Ez a [Céges portál felhasználói felülete optimalizálásának](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) része, amelyet az Android Oreo rendszeren futó Céges portál alkalmazáshoz végzünk. 

Az Android Oreóban engedélyezett új felhasználóifelület-elemekhez további optimalizálások tartoznak.  A végfelhasználók számára további értesítések jelennek meg, amelyek jelzik, hogy a Céges portál mikor végez háttérműveleteket, például szabályzatok lekérését az Intune szolgáltatástól.  Ez átláthatóbbá teszi a végfelhasználók számára, hogy a Céges portál mikor hajt végre felügyeleti feladatokat az eszközön.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Munkahelyi profillal rendelkező Androidhoz készült Céges portál alkalmazás új működési módja <!---1485783--->

Android for Work-eszköz munkahelyi profillal történő regisztrálása után a munkahelyi profil Céges portál alkalmazása végzi el az eszközön a felügyeleti feladatokat. 

Hacsak nem használ MAM-használatot támogató alkalmazást a személyes profilban, az androidos Céges portál alkalmazásra már nincs szükség. Ezért a munkahelyi profil hatékony használhatósága érdekében a munkahelyi profil sikeres regisztrálása után az Intune elrejti a személyes Céges portál alkalmazást.

Az Androidhoz készült Céges portál alkalmazás a személyes profilban bármikor engedélyezhető. Ehhez keresse meg a [Céges portál alkalmazást a Play Áruházban](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal), és koppintson az **Engedélyezés** lehetőségre.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>A Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál fenntartási módba kerül <!--1428681-->

2017 októberétől a Windows 8.1 és Windows Phone 8.1 rendszerekhez készült Céges portál alkalmazás fenntartási módba kerül. Ez azt jelenti, hogy ezeken a platformokon továbbra is jár támogatás az alkalmazásokhoz és a meglévő használati forgatókönyvekhez (például regisztrálás és megfelelőség). Az alkalmazások továbbra is letölthetők a meglévő kiadási csatornákon keresztül, például a Microsoft Áruházból. 

A fenntartási módban ezekhez az alkalmazásokhoz azonban már csak fontos biztonsági frissítések lesznek elérhetőek. Más típusú frissítések és új funkciók már nem jelennek meg ezekhez az alkalmazásokhoz. Ha az új funkciókat szeretné használni, azt javasoljuk, hogy frissítse az eszközt Windows 10 vagy Windows 10 Mobile rendszerre. 


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Nem támogatott Samsung Knox-eszközök regisztrációjának letiltása<!--- 1490695 --->

A Céges portál alkalmazás csak a támogatott Samsung Knox-eszközöket próbálja meg regisztrálni. Az MDM-regisztrációt megakadályozó KNOX-aktiválási hibák elkerülése érdekében az alkalmazás csak a [Samsung által közétett eszközlistán](https://www.samsungknox.com/knox-supported-devices/knox-workspace) szereplő eszközöket próbálja meg regisztrálni. Előfordulhat, hogy egy Samsung-eszköz bizonyos modelljei támogatják a KNOX platformot, míg más modelljei nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse a viszonteladóval, hogy az eszköz Knox-kompatibilis-e. Az ellenőrzött eszközök teljes listája megtalálható az [Android és Samsung KNOX Standard-eszközök konfigurációs szabályzatának beállításai](/intune/supported-devices-browsers.md#intune-supported-devices) témánál.

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Az Android 4.3-as és korábbi verzióinak támogatása lejár <!---1171126, 1326920 --->
A felügyelt alkalmazások és az Androidra készült Céges portál alkalmazás esetén az Android 4.4-es vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Decemberre az összes regisztrált eszköz kiv lesz vonva, így elveszti hozzáférését a vállalati erőforrásokhoz. Ha MDM nélküli alkalmazásvédelmi szabályzatokat használ, akkor az alkalmazások nem jutnak hozzá a frissítésekhez és a használhatóságuk idővel romlani kezd.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Végfelhasználók tájékoztatása a regisztrált eszközök megtekinthető adatairól <!--1165314-->
A Céges portál alkalmazások Eszköz részletei képernyője kiegészül a **Tulajdonjog típusa** oldallal. Így a felhasználók közvetlenül a [Milyen adatok láthatók a cég számára?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) című cikkből fognak tudni tájékozódni az adatvédelmi kérdésekről. Ez terveink szerint az összes Céges portál alkalmazásban meg fog jelenni a közeljövőben. Az iOS kapcsán ezt a funkciót [szeptemberben](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) jelentettük be.


## <a name="week-of-september-25-2017"></a>2017. szeptember 25-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="intune-supports-ios-11---1428975--"></a>Az Intune támogatja az iOS 11-et<!--1428975-->
Az Intune támogatja az iOS 11-et. Ezt korábban bejelentettük az [Intune támogatási blogjának](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) oldalán.

#### <a name="end-of-support-for-ios-80----1164477---"></a>Az iOS 8.0-s verzió támogatása lejár <!---1164477--->
A felügyelt alkalmazások és az iOS-re készült Céges portál alkalmazás esetén az iOS 9.0-s vagy újabb verziója követelmény lesz a vállalati erőforrások eléréséhez. Azok az eszközök, amelyeket nem frissítenek még szeptember előtt, többé nem fognak hozzáférni a Céges portálhoz vagy azokhoz az alkalmazásokhoz. 

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>A Windows 10-es Céges portál alkalmazásban elérhetővé válik a Frissítés művelet <!--1132468-->
A Windows 10-es céges portál alkalmazásban lehetőség lesz az adatok frissítésére. Ezt lefelé húzással, vagy asztali gépeken az F5 billentyű megnyomásával lehet majd elvégezni.



## <a name="notices"></a>Értesítések

### <a name="deprecating-support-for-os-x-yosemite-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Az OS X Yosemite 10.10 és a macOS régebbi verziói támogatásának kivezetése <!--1489263, plan for change for 1802-->

Bejelentjük, hogy 2018 februárjában megkezdjük az OS X Yosemite 10.10-et és a macOS régebbi verzióit futtató eszközök regisztrációjának kivezetését. Az Intune teljes körűen támogatja az OS X El Capitan 10.11-es és újabb verzióit.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>A felügyelt eszközök új elérési útja a Graph API-ban <!-- 1586728 -->
Megváltoznak a felügyelt eszközök eléréséhez a Graph API béta verziójában használható útvonalak. 

| | |
|--|--|
| Jelenlegi útvonal |  https://graph.microsoft.com/beta/managedDevices |
| Új elérési út | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Október folyamán még mindkét útvonal használható lesz. Az októberi kiadás után azonban csak az új útvonal lesz használható.  Ha a Graph API-t használja felügyelt eszközök elérésére, frissítse a parancsfájlokat és az alkalmazásokat az új útvonallal, és ellenőrizze azok megfelelő működését. A további változásokról a [Graph API változásnaplójában](https://developer.microsoft.com/graph/docs/concepts/changelog) tájékozódhat.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el az Azure Portal, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök
A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat az új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune/role-based-access-control).



## <a name="whats-coming"></a>Mi várható?

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>A Jamf-ban regisztrált macOS-eszközök kezelése az Intune eszközmegfelelőségi motorjával <!---1592747--->
A 2018-as év korai szakaszától kezdődően a Jamf a macOS-eszközök eszközállapotát is el fogja küldeni az Intune-nak, az pedig vizsgálni fogja, hogy megfelelnek-e az eszközök az Intune konzolban meghatározott szabályzatoknak. Az eszközmegfelelőségi állapot és más feltételek (például tartózkodási hely, felhasználói kockázat) vizsgálata alapján a feltételes hozzáférés megköveteli, hogy a macOS-eszközök megfeleljenek a szabályzatoknak, ha az Azure AD-hoz kapcsolt felhőalapú vagy helyszíni alkalmazásokat érnek el (az Office 365-öt is beleértve).

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Az Intune iOS-es Vállalati portál alkalmazás támogatásának változásai  <!-- 1164474  -->
A közeljövőben megjelenik az iOS-es Microsoft Intune Vállalati portál alkalmazás egy új verziója, amely csak az iOS 9.0-s vagy újabb rendszerű eszközöket fogja támogatni. A Vállalati portál iOS 8-at támogató verziója nagyon rövid ideig még elérhető marad. Ugyanakkor ha MAM-használatot támogató iOS-alkalmazásokat is használ, vegye figyelembe, hogy csak az iOS 9.0-s és újabb verzióit támogatjuk, ezért ajánlatos gondoskodni róla, hogy a végfelhasználók a legfrissebb operációs rendszert használják. 

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Mindezt azért tudatjuk előre a pontos dátumok ismerete nélkül, hogy legyen ideje tervet készíteni. Gondoskodjon róla, hogy a felhasználók frissítsenek legalább az iOS 9.0-s verziójára, és kérje meg őket, hogy a Céges portál alkalmazást is frissítsék, amikor az megjelenik.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Javasolja a felhasználóinak, hogy az Intune új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 9.0 rendszerre.  Javasolja a felhasználóknak a Vállalati portál új verziójának telepítését, hogy kihasználhassák az általa kínált új funkciókat.

Nyissa meg az Intune-t az Azure Portalon, és az Eszközök -> Minden eszköz alatt az iOS verziójára szűrve gyűjtse ki az iOS 9-nél korábbi operációs rendszert futtató eszközöket.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->
Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja.

Az új ATS-követelményeket érvényesítő Apple TestFlight alkalmazásban elérhetővé vált a Céges portál alkalmazás iOS rendszerű verziója. Ha szeretné kipróbálni az alkalmazást az ATS-megfelelőség tesztelése céljából, küldje el a kereszt- és vezetéknevét, az e-mail-címét és a munkahelye nevét a <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> e-mail-címre. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

## <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [A Céges portál felhasználói felületének újdonságai](whats-new-app-ui.md)
* [Korábbi hónapok újdonságai](whats-new-archive.md)

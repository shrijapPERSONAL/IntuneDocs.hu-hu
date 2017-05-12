---
title: "A Microsoft Intune előzetesének újdonságai"
titleSuffix: Intune Azure preview
description: "Ismerkedjen meg az Azure-beli Intune előzetesének újdonságaival"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: b9f56099c1f102472ba7f6c6a67b16cf29649365
ms.openlocfilehash: 255b36b0c4473ff2450bf6f9a2db920c731bddc1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/01/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>A Microsoft Intune előzetesének újdonságai

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A nyilvános előzetes fejlődése során egyre több funkcióval bővül, mi pedig értesítjük Önt ezekről.

> [!Note]
> Az itt felsorolt változások hamarosan megjelennek az Azure Portal előzetes verziójában. Azonban az Intune szolgáltatás frissítési módja miatt elképzelhető, hogy a változások nem azonnal érhetők el.  A Portal új funkcióinak megjelenése előtt a szolgáltatás többféle összetevőjének egymás utáni frissítésére van szükség. Ezek a változások fokozatosan jelennek meg ebben a hónapban.

## <a name="april-2017"></a>2017. április

### <a name="support-for-managing-the-apple-classroom-app"></a>Támogatás az Apple Osztályterem alkalmazás felügyeletéhez

Az iOS-es Osztályterem alkalmazás mostantól felügyelhető iPad eszközökön. Miután telepítette az Osztályterem alkalmazást a tanári iPad-en a megfelelő osztály- és tanulói adatokkal, majd beállította az osztályhoz rendelt tanulói iPad-eket, az alkalmazás segítségével a tanári iPad-ről vezérelheti őket.
További információt [Az iOS oktatási funkcióinak konfigurálása](/intune-azure/configure-devices/how-to-configure-ios-edu-settings) című cikkben talál.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Felügyelt konfigurációs lehetőségek támogatása androidos alkalmazásokhoz <!-- 621621 -->

A Play áruházban lévő, felügyelt konfigurációs lehetőségeket támogató androidos alkalmazásokat az Intune-nal is lehet konfigurálni.  Ezzel a funkcióval az IT-részleg megnézheti az egyes alkalmazásokban használható konfigurációs értékek listáját, és útmutatásokkal ellátott, kiváló felhasználói felületen konfigurálhatják ezeket az értékeket.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Új androidos szabályzat komplex PIN-kódokhoz <!-- 722069 -->

5.0-s vagy újabb Android rendszerű eszközökhöz tartozó androidos eszközprofilban meg lehet adni a Komplex numerikus értéket kötelező [jelszótípusként](/intune-azure/configure-devices/device-restrictions-for-android#password).  Ezzel a beállítással lehet megakadályozni, hogy a felhasználók ismétlődő vagy egymást követő számokból álló PIN-kódot (például 1111 vagy 1234) válasszanak.

### <a name="additional-support-for-android-for-work-devices"></a>Kibővített támogatás Android for Work-eszközökhöz

- **Jelszó- és munkahelyiprofil-beállítások kezelése** <!-- 612808 -->

  Az új Android for Work-eszközkorlátozási szabályzattal kezelhetők a felügyelt Android for Work-eszközök jelszó- és munkahelyiprofil-beállításai.

- **A munkahelyi és a személyes profilok közötti adatmegosztás engedélyezése** <!-- 1045102 -->

Az Android for Work-eszközkorlátozási szabályzat új lehetőségekkel segíti a munkahelyi és személyes profil közötti adatmegosztás konfigurálását.

- **A munkahelyi és a személyes profilok közötti másolás és beillesztés korlátozása** <!-- 1046094 -->

  Az Android for Work-eszközökhöz készült új egyéni eszközprofillal megszabhatja, hogy engedélyezi-e a munkahelyi és a személyes profilok közötti másolást és beillesztést.

További információt az [Eszközkorlátozások az Android for Work esetén](/intune-azure/configure-devices/device-restrictions-for-afw) című témakörben talál.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Üzletági alkalmazások hozzárendelése iOS-es és androidos eszközökhöz <!-- 1057568 -->

Az [iOS-re](/intune-azure/manage-apps/ios-lob-app) (.ipa-fájlok) és [Androidra](/intune-azure/manage-apps/android-lob-app) (.apk-fájlok) készült üzletági (LOB) alkalmazásokat felhasználókhoz vagy eszközökhöz rendelheti hozzá.

###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Új eszközszabályzatok iOS rendszerhez <!-- 723774, 723815, 723826, 723830 -->

- **A kezdőképernyőn látható alkalmazások** – Azt határozza meg, mely alkalmazásokat láthatják a felhasználók [iOS-es eszközeik kezdőképernyőjén](/intune-azure/configure-devices/home-screen-settings-for-ios). Ez a szabályzat módosítja a kezdőképernyő elrendezését, de nem telepíti a megadott, de nem telepített alkalmazásokat.

- **Kapcsolódás AirPrint-eszközökhöz** – Azt határozza meg, hogy mely [AirPrint-eszközökhöz](/intune-azure/configure-devices/air-print-settings-for-ios-and-macos) (hálózati nyomtatókhoz) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Kapcsolódás AirPlay-eszközökhöz** – Azt határozza meg, hogy mely [AirPlay-eszközökhöz](/intune-azure/configure-devices/airplay-settings-for-ios-devices) (például Apple TV-hez) kapcsolódhatnak az adott iOS-es eszköz végfelhasználói.

- **Egyéni üzenet a zárolási képernyőn** – Az alapértelmezett helyett egyéni üzenetet állíthat be az iOS-es eszköz zárolási képernyőjére. További információt az [Elérhető eszközműveletek](/intune-azure/manage-devices/what-is#available-device-actions) című témakörben talál


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS-alkalmazások leküldéses értesítéseinek korlátozása <!-- 723767 -->

Az Intune-os eszközkorlátozási profilokban már a következő [értesítési beállításokat](/intune-azure/configure-devices/app-notification-settings-for-ios) is konfigurálhatja iOS-es eszközökhöz:

- Adott alkalmazás értesítéseinek teljes körű be- vagy kikapcsolása
- Adott alkalmazás értesítési központban megjelenő értesítéseinek be- vagy kikapcsolása
- Riasztástípus megadása (**None** – Nincs, **Banner** – Szalag vagy **Modal Alert** – Modális riasztás)
- Jelvények engedélyezése az alkalmazásnak
- Értesítési hangok engedélyezése az alkalmazásnak.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-alkalmazások konfigurálása autonóm egyalkalmazásos módhoz <!-- 737837 -->

Intune-eszközprofillal mostantól konfigurálhatja az iOS-es eszközöket megadott alkalmazások [autonóm egyalkalmazásos módban](/intune-azure/configure-devices/device-restrictions-for-ios#autonomous-single-app-mode-supervised-only) való futtatására. Ha ez a mód konfigurálva van, és az alkalmazást elindítják, az eszközön nem lehet másik alkalmazást futtatni. Célszerű például így konfigurálni az olyan alkalmazásokat, amelyekkel a felhasználók vizsgázhatnak az eszközön. Az alkalmazás használatának befejezésekor vagy a szabályzat eltávolításakor az eszköz visszatér a szokásos állapotába.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Megbízható tartományok konfigurálása levelezéshez és böngészéshez iOS-es eszközökön <!-- 723765 -->

Az iOS-es eszközkorlátozási profilokban a következő [tartománybeállításokat](/intune-azure/configure-devices/device-restrictions-for-ios#domains) konfigurálhatja:

- **Jelöletlen levelezési tartományok** – a felhasználó által az itt megadottól különböző tartománnyal küldött vagy fogadott e-mailek meg lesznek jelölve nem megbízhatóként.

- **Felügyelt webtartományok** – az itt megadott URL-címekről letöltött dokumentumok felügyeltnek minősülnek (csak a Safari esetében).  

- **Jelszavak automatikus kitöltése a Safariban** – a felhasználók csak olyan URL-eken menthetik jelszavaikat a Safariban, amelyek egyeznek az itt megadott mintákkal. Ez a beállítás csak felügyelt módú, többfelhasználós konfigurációval nem rendelkező eszközön használható. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>A VPP-alkalmazások elérhetőek az iOS-es Céges portálon <!-- 748782 -->

A mennyiségi vásárlási program (VPP) keretében vásárolt iOS-es alkalmazásokat **Elérhető** telepítésként hozzárendelheti végfelhasználókhoz, akik Apple Store-fiókkal telepíthetik az alkalmazást.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>E-könyvek szinkronizálása az Apple VPP Store-ból <!-- 800878 -->

Az Apple mennyiségi vásárlásra szolgáló áruházából vásárolt [könyvek szinkronizálhatók](/intune-azure/manage-apps/ios-vpp-apps) az Intune-nal, és kioszthatók felhasználóknak.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Többfelhasználós felügyelet a Samsung KNOX Standard-eszközökön <!-- 971988 -->

A Samsung KNOX Standard rendszerű eszközökön mostantól használható az Intune [többfelhasználós felügyelete](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices). Ilyenkor a felhasználók Azure Active Directory-beli hitelesítő adataikkal jelentkezhetnek be és ki az eszközön, de az központi felügyelet alatt marad, akár használatban van, akár nem.  A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

### <a name="additional-windows-device-restriction-settings----818566---"></a>További windowsos eszközkorlátozási beállítások <!-- 818566 -->

További [windowsos eszközkorlátozási beállításokat](/intune-azure/configure-devices/device-restrictions-for-windows-10) tettünk elérhetővé, például bővült az Edge böngésző támogatása, testre szabható az eszközök zárolási képernyője és Start menüje, szabályozható a Windows Reflektorfény háttérképkészlete, illetve a proxybeállítások.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Többfelhasználós támogatás a Windows 10 alkotói frissítéséhez <!-- 822547 -->

A [többfelhasználós felügyelet](/intune-azure/enroll-devices/enroll-windows-devices) támogatását kiterjesztettük a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökre. Az eszközre minden egyes, Azure AD-s hitelesítő adataival bejelentkező általános jogú felhasználó a saját felhasználónevéhez rendelt alkalmazásokat és szabályzatokat kapja meg. A felhasználók jelenleg nem használhatják a Céges portált önkiszolgálói forgatókönyvek esetén (például alkalmazások telepítése).

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Újrakezdés művelet Windows 10-es PC-khez<!-- 1004830 -->

A Windows 10-es PC-ken már elérhető az új [Újrakezdés eszközművelet](/intune-azure/manage-devices/what-is#available-device-actions).  amely eltávolítja a PC-re telepített alkalmazásokat, és automatikusan a Windows legújabb verziójára frissíti a gépet. Így egyszerűbben eltávolíthatók az új gépeken gyakran előtelepítve megtalálható számítógépgyártói (OEM) alkalmazások. A konfigurációval meg lehet adni, hogy a művelet a felhasználói adatokat is eltávolítsa-e.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>További Windows 10-es frissítési útvonalak <!-- 903672 -->

Mostantól olyan [kiadásfrissítési szabályzatok](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade) is létrehozhatók, amelyekkel az alábbi Windows 10-kiadásokra frissíthetők az eszközök:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-es eszközök tömeges regisztrálása <!-- 747607 -->

Mostantól a Windows Configuration Designer (WCD) használatával a Windows 10 alkotói frissítéssel rendelkező nagy számú eszközt csatlakoztathat az Azure Active Directoryhez és az Intune-hoz. Ha Azure AD-bérlőhöz be szeretné kapcsolni a [tömeges MDM-regisztrálást](/intune-azure/enroll-devices/bulk-enroll-windows), a Windows Configuration Designerrel hozzon létre olyan kiépítési csomagot, amely csatlakoztatja az eszközöket az Azure AD-bérlőhöz, majd alkalmazza a csomagot a csoportosan regisztrálni és felügyelni kívánt vállalati tulajdonú eszközökre. A csomagok alkalmazását követően az eszközök csatlakoznak az Azure AD-hez, regisztrálnak az Intune-ban, és készen állnak az Azure AD-felhasználók bejelentkezésére.  Az Azure AD-felhasználók általános jogú felhasználók ezeken az eszközökön, akik megkapják majd a kijelölt szabályzatokat és a kötelező alkalmazásokat. Az önkiszolgáló és a Céges portált használó forgatókönyvek jelenleg nem támogatottak.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Új MAM-beállítások a PIN-kódhoz és a felügyelt tárolóhelyekhez <!-- 581122, 736644 -->

Két új alkalmazásbeállítás segíti a mobileszköz-felügyeletet (MAM):

- **Disable app PIN when device PIN is managed** (Alkalmazás PIN-kódjának letiltása felügyelt eszköz-PIN-kód esetén) – a rendszer észleli, hogy van-e eszköz-PIN-kód a regisztrált eszközön, és ha van, mentesíti a felhasználót az alkalmazásvédelmi szabályzatok által megkövetelt alkalmazás-PIN-kód megadása alól, ily módon kevesebbszer kell PIN-kódot megadni a regisztrált eszközökön a MAM-mal védett alkalmazások megnyitásakor. A funkció Androidon és iOS-en egyaránt elérhető.

- **A társzolgáltatások kijelölése, melyekbe menthetők a vállalati adatok** – itt lehet megadni, hogy mely tárolóhelyekre mentse a rendszer a vállalati adatokat. A felhasználók csak a kijelölt tárolóhelyekre menthetnek, a fel nem sorolt tárolóhelyek tehát le lesznek tiltva.

  A támogatott tárhelyszolgáltatások:

  - OneDrive
  - Vállalati SharePoint Online
  - Helyi tárhely

### <a name="help-desk-troubleshooting-portal----907448---"></a>Ügyfélszolgálati hibaelhárítási portál <!-- 907448 -->

Az új [hibaelhárítási portálon](/intune-azure/manage-users/help-desk) az ügyfélszolgálati munkatársak és az Intune-rendszergazdák áttekinthetik a felhasználók és eszközeik listáját, és az Intune technikai problémáinak elhárítását is elvégezhetik.

## <a name="march-2017"></a>2017. március

### <a name="support-for-ios-lost-mode---431695--"></a>Az iOS-es elveszett mód támogatása <!--431695-->

Az iOS 9.3 és újabb verziói esetében az Intune már az **Elveszett módot** is támogatja. Ezzel letiltható az eszközön minden tevékenység, a zárolási képernyőn pedig üzenet és kapcsolatfelvételhez használható telefonszám jelenik meg.

A végfelhasználó csak akkor tudja feloldani az eszközt, ha a rendszergazda kikapcsolja az Elveszett módot. Ha az Elveszett mód be van kapcsolva, az Intune-konzolon az **Eszköz megkeresése** művelet használatával megjelenítheti az eszköz tartózkodási helyét egy térképen.

A funkció csak felügyelt módban lévő, DEP-pel regisztrált, céges tulajdonban lévő iOS-eszközökön használható.

További információt [A Microsoft Intune-eszközfelügyelet ismertetése](/intune-azure/manage-devices/what-is) című témakörben talál.

### <a name="improvements-to-device-actions-report---677150--"></a>Fejlesztések az eszközműveleti jelentéseknél <!--677150-->

A jobb teljesítmény érdekében fejlesztéseket végeztünk az eszközműveleti jelentéseknél. A jelentéseken ezen kívül állapot szerinti szűrések is végezhetők. Például olyan módon is szűrhetőek a jelentések, hogy csak a végrehajtott eszközműveletek jelenjenek meg.”

### <a name="actions-for-non-compliance---730266--"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266-->

A **Meg nem felelés esetén végrehajtandó műveletek** a megfelelési szabályzatokkal kapcsolatos új funkció, amellyel a nem megfelelő eszközökön lehet műveleteket végezni. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->

Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

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

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.


## <a name="february-2017"></a>2017. február

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>A mobileszköz-regisztrálás korlátozásának képessége <!--747600, 795782-->
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.

* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.  
* Csak az iOS és az Android esetében van még egy lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Az összes művelet megtekintése a felügyelt eszközökön<!--677150-->
Az új __Eszközműveletek__ jelentés megmutatja, hogy mely felhasználó hajtott végre távoli műveleteket az eszközön (például gyári alaphelyzetbe állítás), valamint megjeleníti az adott művelet állapotát is. Lásd: [Mi az eszközfelügyelet?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->
A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Eszközkategóriák megjelenítése <!--814654-->
Mostantól az eszközkategória külön oszlopként jelenik meg az eszközlistában. A kategória módosítására szintén van lehetőség az Eszköztulajdonságok panel Tulajdonságok szakaszában. Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>A Vállalati Windows Update beállításainak konfigurálása <!--776716-->

A Windows 10 frissítéseinek biztosítására a jövőben a szolgáltatásként nyújtott Windows használható. A Windows 10-től kezdődően minden új funkció- és minőségi frissítés magában foglalja valamennyi korábbi frissítés tartalmát. Ennek köszönhetően a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 eszközök teljesen naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.

A Vállalati Windows Update használatával egyszerűbbé válik a frissítések kezelése, így nem szükséges külön jóváhagyni az egyes frissítéseket az eszközcsoportokhoz. A különböző környezetekben továbbra is kezelhető a kockázat egy frissítéstelepítési stratégia konfigurálásával, és a Windows Update gondoskodik a frissítések megfelelő időpontban történő telepítéséről. A Microsoft Intune lehetővé teszi a frissítési beállítások konfigurálását az eszközökön és a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. A **Windows 10 frissítési körök** az Intune használatával konfigurálhatók és kezelhetők. A frissítési kör olyan beállításokat tartalmaz, amelyek a Windows 10 frissítések telepítésének ütemezését és mikéntjét konfigurálják. További információt [A Vállalati Windows Update beállításainak konfigurálása](/intune-azure/configure-devices/how-to-configure-windows-update-for-business) című témakörben talál.

## <a name="january-2017"></a>2017. január

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Üzletági alkalmazások kiosztása nem regisztrált eszközökre is <!--748823-->
Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Munkahelyi portál alkalmazás helyett a Munkahelyi portál webhelyen telepíthetik az alkalmazást. Lásd: [Mi az alkalmazáskezelés?](/intune-azure/manage-apps/what-is-app-management)

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>A következő probléma elhárítása: Az iOS-eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük
Ha a felhasználói eszközök elveszítik a kapcsolatot az Intune-nal, új hibaelhárítási lépések átadásával segítheti a felhasználókat a vállalati erőforrásokhoz való hozzáférés visszaszerzésében. Lásd: [Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>2016. december (eredeti kiadás)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Áruházból származó alkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Üzletági (LOB) alkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Mennyiségi konstrukcióban vásárolt alkalmazások telepítése és felügyelete iOS-es és windowsos eszközökön
- Webalkalmazások telepítése és felügyelete iOS-es, androidos és windowsos eszközökön
- Konfigurációs profilok felügyelt iOS-es alkalmazásokhoz
- Alkalmazásvédelmi szabályzatok konfigurálása és üzletági alkalmazások telepítése az Intune-ban nem regisztrált eszközökre
- VPN-profilok, alkalmazásonkénti VPN-, Wi-Fi-, e-mail- és tanúsítványprofilok
- Megfelelőségi szabályzatok
- Feltételes hozzáférés Azure AD-re
- Feltételes hozzáférés helyszíni Exchange-re
- Eszközök beléptetése
- Szerepköralapú hozzáférés-vezérlés

## <a name="deprecated-features-in-the-azure-portal"></a>Az Azure Portal elavult szolgáltatásai

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Hardverazonosítók soronkénti átnézésének támogatása
Az Azure Portalon nem lehetséges soronként átnézni az IMEI-számokból és az Apple-sorozatszámokból álló hardverazonosítókat. A klasszikus Intune-konzolon lehetőség van rá, hogy csv-fájlból importálja a részleteket, és felülírja az egyes hardverazonosítók korábbi részleteit. Az Azure Portal egységes, hatékony módszert kínál, amely automatikusan felülírja az összes hardverazonosító részleteit, vagy figyelmen kívül hagyja a korábbi azonosítók új részleteit.

#### <a name="how-this-affects-you"></a>Mit jelent ez az Ön számára?
Az Azure Portalon nem fog tudni soronként dönteni arról, hogy mely IMEI-számmal ellátott eszközöket szeretné módosítani. A klasszikus Intune-konzolon továbbra is elérhető lesz ez a lehetőség.

#### <a name="how-to-get-ready-for-this-change"></a>Felkészülés a változásra
Ezt az információt azért bocsátjuk közre előzetesen, hogy amennyiben Önt is érinti, értesíteni tudja róla az illetékes adminisztrátorokat. A változás az Azure Portalra való költözéssel egy időben, várhatólag 2017 első felében lép életbe.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Céges eszközregisztrációs profilok támogatása az Apple DEP-ben
Az Azure Portal az Apple Készülékregisztrációs program (DEP) eszköz-sorozatszámai esetében nem támogatja az alapértelmezett céges eszközregisztrációs profilt. A klasszikus Intune-konzol ezen funkcióját megszüntetjük, a profilok szándékolatlan hozzárendelését megelőzendő. Az Azure Portalon az Apple DEP-fiókokból szinkronizált sorozatszámokhoz a rendszer nem rendel alapértelmezett céges eszközregisztrációs profilt.

#### <a name="how-this-affects-you"></a>Mit jelent ez az Ön számára?
Az Azure Portalon nem fog tudni az összes Apple-eszközhöz alapértelmezett profilszabályzatot megadni. A klasszikus Intune-konzolon továbbra is elérhető lesz ez a lehetőség.

#### <a name="how-to-get-ready-for-this-change"></a>Felkészülés a változásra
Ezt az információt azért bocsátjuk közre előzetesen, hogy amennyiben Önt is érinti, értesíteni tudja róla az illetékes adminisztrátorokat. A változás az Azure Portalra való költözéssel egy időben, várhatólag 2017 első felében lép életbe.


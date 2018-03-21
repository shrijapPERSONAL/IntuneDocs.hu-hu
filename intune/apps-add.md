---
title: "Alkalmazások hozzáadása a Microsoft Intune-hoz"
titlesuffix: 
description: "Információ arról, hogyan lehet a Microsoft Intune-hoz alkalmazásokat hozzáadni, majd az alkalmazásokat felhasználókhoz és eszközökhöz rendelni. Az Intune számos különböző alkalmazástípust támogat."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 407a332e170497dbb618a2915bba6b794c4a720f
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Alkalmazás hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az alkalmazások hozzárendelése, figyelése, konfigurálása és védelme előtt hozzá kell adnia őket a Microsoft Intune-hoz.

Az alkalmazások és eszközök céges felhasználói (a munkaerő) több alkalmazáskövetelménnyel rendelkezhetnek. Mielőtt alkalmazásokat adna hozzá az Intune-hoz, ezzel elérhetővé téve azokat a munkaerő számára, célszerű felmérnie és megértenie néhány alkalmazásokkal kapcsolatos alapvetést. Ismernie kell az Intune-ban elérhető különböző alkalmazástípusokat. Fel kell mérnie az alkalmazáskövetelményeket, így a munkaerő számára szükséges platformokat és funkciókat. Emellett meg kell határoznia, hogy az Intune-nal kezeli-e az eszközöket (és azok alkalmazásait), vagy az Intune-nal kezeli az alkalmazásokat, az eszközöket azonban nem. El kell döntenie, hogy a munkaerő mely tagjainak lesz szüksége különböző alkalmazásokra különböző funkciókkal. A cikkben nyújtott információk segítenek az első lépésekben.

## <a name="app-types-in-microsoft-intune"></a>Alkalmazástípusok a Microsoft Intune-ban

Az Intune számos különböző alkalmazástípust támogat. Az elérhető beállítások minden alkalmazástípus esetében eltérőek. Az Intune a következő típusú alkalmazások hozzáadását és hozzárendelését teszi lehetővé:

| **Alkalmazástípusok**                                     | **Telepítés**                                                                  | **Frissítések**                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Áruházbeli alkalmazások          | Az Intune telepíti az alkalmazást az eszközön                                       | Az alkalmazások frissítése automatikus     |
| Belső fejlesztésű (üzletági) alkalmazások  | Az Intune telepíti az alkalmazást az eszközön (a telepítőfájlt Önnek kell letöltenie)    | Frissítenie kell az alkalmazást       |
| Beépített alkalmazások    | Az Intune telepíti az alkalmazást az eszközön                                       | Az alkalmazások frissítése automatikus     |
| Alkalmazások a weben (webes hivatkozás)                | Az Intune létrehoz egy parancsikont a webalkalmazáshoz az eszköz kezdőképernyőjén          | Az alkalmazások frissítése automatikus     |

### <a name="specific-app-type-details"></a>Alkalmazástípusok konkrét részletei
 
A következő táblázatban megtekintheti a konkrét alkalmazástípusokat és azok hozzáadásának módját a Microsoft Intune **Alkalmazás hozzáadása** panelén:

| **Alkalmazásspecifikus típus**                         | **Általános típus**             | **Alkalmazásspecifikus eljárások**                                                                                                                                                 |
|---------------------------------------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Androidos áruházbeli alkalmazások                        | Áruházbeli alkalmazás                  | Válassza az **Android** lehetőséget az **alkalmazás típusa** területen, majd adja meg a Google Play áruház az alkalmazáshoz tartozó URL-címét.                                                                                       |
| iOS-es áruházbeli alkalmazások                            | Áruházbeli alkalmazás                  | Válassza az **iOS** lehetőséget az **alkalmazás típusa** területen, keresse meg az alkalmazást, majd válassza ki az alkalmazást az Intune-ban.                                                                                     |
| Windows Phone 8.1-es áruházbeli alkalmazások              | Áruházbeli alkalmazás                  | Válassza a **Windows Phone 8.1** lehetőséget az **alkalmazás típusa** területen, majd adja meg a Microsoft Áruház az alkalmazáshoz tartozó URL-címét.                                                                               |
| Microsoft Áruházbeli alkalmazások                      | Áruházbeli alkalmazás                  | Válassza a **Windows** lehetőséget az **alkalmazás típusa** területen, majd adja meg a Microsoft Áruház az alkalmazáshoz tartozó URL-címét.                                                                                         |
| Android for Work-alkalmazások                     | Áruházbeli alkalmazás                  | Keresse meg és hagyja jóvá az Android for Work-alkalmazást a Google Play for Work Áruházban.                                                                                        |
| Windows 10-es Office 365-alkalmazások            | Áruházbeli alkalmazás (Office 365)     | Válassza a **Windows 10** lehetőséget az **Office 365 csomag** területen, az **alkalmazás típusa** részen, majd válassza ki a telepíteni kívánt Office 365-alkalmazást.                                                |
| macOS-es Office 365-alkalmazások                 | Áruházbeli alkalmazás (Office 365)     | Válassza a **macOS** lehetőséget az **Office 365 csomag** területen, az **alkalmazás típusa** részen, majd válassza ki az Office 365 csomagot.                                                                     |
| Androidos üzletági (LOB) alkalmazások       | Üzletági (LOB) alkalmazás | Válassza az **Üzletági alkalmazás** lehetőséget az **alkalmazás típusa** területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy **.apk** kiterjesztésű Androidos telepítőfájlt.                    |
| iOS-es üzletági (LOB) alkalmazások           | Üzletági (LOB) alkalmazás | Válassza az **Üzletági alkalmazás** lehetőséget az **alkalmazás típusa** területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy **.ipa** kiterjesztésű iOS-es telepítőfájlt.                        |
| Windows Phone rendszerű üzletági (LOB) alkalmazások | Üzletági (LOB) alkalmazás | Válassza az **Üzletági alkalmazás** lehetőséget az **alkalmazás típusa** területen, válassza az **Alkalmazáscsomag-fájl** elemet, majd adjon meg egy **.xap** kiterjesztésű iOS-es telepítőfájlt.                        |
| Windowsos üzletági (LOB) alkalmazások       | Üzletági (LOB) alkalmazás | Válassza az Üzletági alkalmazás lehetőséget az alkalmazás típusa területen, válassza az Alkalmazáscsomag-fájl elemet, majd adjon meg egy **.msi**, **.appx** vagy **.appxbundle** kiterjesztésű iOS-es telepítőfájlt. |
| Beépített iOS-alkalmazás                          | Beépített alkalmazás               | Válassza a **Beépített alkalmazás** lehetőséget az **alkalmazás típusa** területen, majd válasszon ki egy beépített alkalmazást az elérhető alkalmazások listájából.                                                                  |
| Beépített Android-alkalmazás                      | Beépített alkalmazás               | Válassza a **Beépített alkalmazás** lehetőséget az **alkalmazás típusa** területen, majd válasszon ki egy beépített alkalmazást az elérhető alkalmazások listájából.                                                                  |
| Webalkalmazások                                  | Webalkalmazás                    | Válassza a **Webes hivatkozás** lehetőséget az **alkalmazás típusa** majd adjon meg egy érvényes, a webalkalmazásra mutató URL-címet.                                                                                        |

   
A **Mobilalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséggel hozzáadhat egy alkalmazást a Microsoft Intune-hoz. Megjelenik az **Alkalmazás hozzáadása** panel, ahol kiválaszthatja az **alkalmazás típusát**. 

>[!TIP]
> Az üzletági (LOB) alkalmazásokat egy alkalmazástelepítő fájlból adja hozzá. Egy iOS LOB alkalmazás telepítéséhez például az **Alkalmazás hozzáadása** panel **Alkalmazás típusa** részén az **Üzletági alkalmazás** beállítás megadásával adhatja hozzá az alkalmazást. Ezután válassza ki az alkalmazáscsomag fájlját (.ipa kiterjesztés). Az ilyen típusú alkalmazások általában belső fejlesztésűek.

## <a name="assess-app-requirements"></a>Alkalmazáskövetelmények értékelése
Rendszergazdaként nemcsak azt kell meghatároznia, hogy mely alkalmazásokra lesz szüksége a csapatának, hanem azt is, hogy az egyes csoportoknak és alcsoportoknak milyen funkciókra lesz szükségük. Minden alkalmazáshoz meg kell határoznia a szükséges platformokat, az alkalmazásra igényt tartó felhasználói csoportokat, a csoportokra alkalmazandó konfigurációs szabályzatokat és az alkalmazandó védelmi szabályzatokat.  

Emellett meg kell határoznia, hogy szükséges-e a mobileszköz-kezeléssel (MDM) foglalkoznia, vagy elegendő a mobilalkalmazás-kezeléssel (MAM). Az Intune-nal történő eszközkezelés (MDM) a következő esetekben hasznos:
- A felhasználóknak vállalati Wi-Fi- vagy VPN-csatlakozási profilra van szükségük a produktív munkához.
- A felhasználóknak egy, az eszközükre leküldött alkalmazáscsomagra van szükségük.
- A szervezetének meg kell felelnie azoknak a szabályozási és más házirendeknek, amelyek konkrét mobileszköz-kezelési vezérlést írnak elő, például biztonságra vagy titkosításra vonatkozó előírásokat.

Az Intune-nal történő alkalmazáskezelés (MAM) az eszköz kezelése nélkül a következő esetekben hasznos:
- A felhasználók használhatják a saját eszközeiket (BYOD).
- A folyamatos eszközszintű értesítések helyett egy egyszeri felugró üzenettel szeretné tudatni a felhasználókkal, hogy életbe lépett a MAM-védelem.
- Olyan szabályzatoknak kell megfelelnie, amelyek alacsonyabb fokú felügyeleti képességeket írnak elő a személyes eszközökhöz. Például az alkalmazások céges adatait szeretné kezelni, nem az eszközön található minden céges adatot.

További információ: [Az MDM és az MAM összehasonlítása](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Az alkalmazás használóinak meghatározása

A munkaerő számára szükséges alkalmazások meghatározásakor vegye figyelembe, hogy különböző felhasználói csoportok különböző alkalmazásokat használnak. A csoportok ismerete az alkalmazások hozzáadása után is hasznos. Miután hozzáadta az alkalmazást, hozzárendelhet egy felhasználói csoportot, akik használhatják az alkalmazást. Elsőként az alkalmazás adatainak bizalmassági szintje alapján meg kell határoznia, hogy ki tartozzon az alkalmazáshoz hozzáférők csoportjába. Előfordulhat, hogy bizonyos szerepköröket ki kell zárnia a hozzáférésből. Például előfordulhat, hogy az értékesítési csoportnak csak bizonyos LOB alkalmazásokra van szüksége, míg a mérnöki, a pénzügyi, a HR vagy a jogi osztálynak nincs szüksége ezekre. Emellett előfordulhat, hogy az értékesítési csoportnak további adatvédelemre, valamint a belső vállalati szolgáltatások elérésére van szüksége a mobileszközein. Önnek kell meghatároznia, hogy hogyan csatlakozhat az adott csoport az erőforrásokhoz az alkalmazás használatával. Az alkalmazással elért adatok a felhőben vagy a helyszínen legyenek tárolva? Hogyan csatlakozhatnak a felhasználók az erőforrásokhoz az alkalmazással? Az Intune támogatja az olyan mobilalkalmazások hozzáférésének biztosítását is, amelyek biztonságos hozzáférést igényelnek a helyszíni adatokhoz, mint például az üzleti alkalmazások kiszolgálói. Ez a hozzáféréstípus általában az [Intune által kezelt, hozzáférés-vezérlésre használt tanúsítványokkal](certificates-configure.md), valamint a szegélyhálózatban található szabványos VPN-átjáróval vagy proxyval, például a Microsoft Azure Active Directory-alkalmazásproxyval oldható meg. Az Intune [alkalmazásburkoló eszközével és az App SDK-val](apps-prepare-mobile-application-management.md) az elért adatok az üzleti alkalmazáson belül tarthatók, hogy az alkalmazás ne tudja átadni a vállalati adatokat a fogyasztói alkalmazásoknak vagy szolgáltatásoknak.

Az [Intune az üzembe helyezésének tervezésével, kialakításával és kivitelezésével](planning-guide.md) meghatározhatja, hogy hogyan azonosíthatja az egyes alkalmazáshasználati esetekhez és alesetekhez tartozó szervezeti csoportokat. További információ az alkalmazások csoportokhoz rendeléséről: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md).

### <a name="determine-the-type-of-app-for-your-solution"></a>A saját megoldáshoz tartozó alkalmazás meghatározása

A következő alkalmazástípusok közül választhat:
- **Áruházbeli alkalmazások** – Az áruházbeli alkalmazások olyan alkalmazások, amelyeket a Microsoft, az iOS vagy az Android áruházába töltöttek fel. Az áruházbeli alkalmazás szolgáltatója tartja karban és frissíti az alkalmazást. Az áruház listájából Ön választja ki az alkalmazást, és teszi elérhetővé a felhasználói számára az Intune segítségével.
- **Belső fejlesztésű (üzletági) alkalmazások** – A belső fejlesztésű alkalmazások üzletági (LOB) alkalmazások. Az ilyen típusú alkalmazásokat az Intune által támogatott platformok egyikére hoztuk létre, például a Windows, az iOS vagy az Android rendszerre. A cége egy külön fájlként hozza létre és teszi elérhetővé Ön számára a frissítéseket. Az alkalmazás frissítéseit a felhasználók számára az Intune-nal teheti elérhetővé.
- **Webes alkalmazások** – A webalkalmazások ügyfél-kiszolgáló alkalmazások. A kiszolgáló szolgáltatja a webalkalmazást, amely tartalmazza a felhasználói felületet, a tartalmat és a funkciókat. A modern webszolgáltatási platformok emellett gyakran kínálnak biztonsági, terheléselosztási és egyéb szolgáltatásokat. Az ilyen típusú alkalmazásokat külön, a weben kezelik. Ehhez az alkalmazástípushoz az Intune-t kell használnia. Azt is Ön dönti el, hogy mely felhasználói csoportok férhetnek hozzá az alkalmazáshoz. Vegye figyelembe, hogy az Android nem támogatja a webalkalmazásokat.

A szervezet alkalmazásigényének felmérésekor vegye figyelembe, hogy ezek az alkalmazások hogyan integrálhatók felhőszolgáltatásokkal, milyen adatokhoz férhetnek hozzá, elérhetők-e BYOD-felhasználók számára, valamint szükség van-e hozzájuk internet-hozzáférésre.

További információt a cégnél használni kívánt alkalmazástípusokról a [Terv létrehozása](planning-guide-design.md#feature-requirements) terület **Funkciókövetelmények** szakaszának **Alkalmazások** részén találhat.

### <a name="understanding-app-management-and-protection-policies"></a>Az alkalmazáskezelési és -védelmi szabályzatok megértése
Az Intune-nal módosíthatja a telepített alkalmazások funkcióit, hogy azok összhangban legyenek a vállalat megfelelőségi és biztonsági szabályzataival. Ennek köszönhetően megadhatja, hogyan legyenek védve a céges adatok. Az Intune által kezelt alkalmazások széles körű mobilalkalmazás-védelmi szabályzatokkal rendelkeznek, például:

- A másolás és beillesztés, valamint a mentés másként funkció korlátozása
- A webes hivatkozások konfigurálása, hogy azok az Intune Managed Browser alkalmazásban nyíljanak meg
- Több identitás, valamint az alkalmazásszintű feltételes hozzáférés használatának engedélyezése

Az Intune által kezelt alkalmazások regisztráció nélkül nyújtanak alkalmazásvédelmet, így Ön a felhasználói eszköz kezelése nélkül alkalmazhat adatszivárgás-megelőzési szabályzatokat. Emellett az Intune alkalmazás szoftverfejlesztői készletével és alkalmazásburkoló eszközével beépítheti a mobilalkalmazás-kezelést az üzletági és mobilalkalmazásaiba. További információ ezekről az eszközökről: [Az Intune App SDK áttekintése](app-sdk.md).

### <a name="understanding-licensed-apps"></a>A licencelt alkalmazások megértése
A webes, az áruházbeli és az üzletági alkalmazásokon kívül érdemes tisztában lennie a Volume Purchase Program alkalmazásainak és a licencelt alkalmazások sajátosságaival, például:     
- **Vállalati Apple Volume Purchasing Program (iOS és MacOS)** – Az iOS App Store áruháza lehetővé teszi, hogy több licencet is vásároljon a vállalatnál használni kívánt alkalmazásokhoz. Több licenc vásárlásával hatékonyabban kezelhetők a vállalaton belüli alkalmazások. További információ: [Mennyiségi programban vásárolt iOS-alkalmazások felügyelete](vpp-apps-ios.md).
- **Android for Work (Android)** – Az alkalmazások Android for Work-eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Minden olyan alkalmazás, amelyet az Android for Work részeként telepít, a Google Play for Work áruházból szerezhető be. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazásokat, majd hagyja jóvá a választást. Az alkalmazás ezt követően a Licencelt alkalmazások csomópontban jelenik meg az Azure Portal webhelyen. Ezen a felületen kezelheti az alkalmazások hozzárendelését, ami ugyanúgy zajlik, mint a hagyományos alkalmazásoknál.
- **Vállalati Microsoft Áruház (Windows 10)** – A Vállalati Microsoft Áruház az a hely, ahol alkalmazásokat vásárolhat a szervezete számára egyenként vagy mennyiségi program keretében. Az áruházat a Microsoft Intune-nal összekapcsolva a mennyiségi programban vásárolt alkalmazásokat az Azure Portalról kezelheti. További információ: [A Microsoft Store Vállalatoknak áruházban vásárolt alkalmazások felügyelete](windows-store-for-business.md).

## <a name="before-you-add-apps"></a>Mielőtt hozzáadna alkalmazásokat
Mielőtt elkezdené az alkalmazások hozzáadását és hozzárendelését, vegye figyelembe a következőket.

- Ha áruházból végzi az alkalmazások felvételét és hozzárendelését, a végfelhasználók csak akkor tudják telepíteni az alkalmazásokat, ha rendelkeznek fiókkal az adott áruházban.
- Előfordulhat, hogy egyes hozzárendelendő alkalmazások beépített iOS-alkalmazásoktól függenek. Ha például egy könyv iOS-es áruházból való hozzárendelését végzi, az eszközön elérhetőnek kell lennie az iBooks alkalmazásnak. Ha eltávolította a beépített iBooks alkalmazást, azt az Intune használatával nem tudja újratelepíteni.

## <a name="cloud-storage-space"></a>Felhőtárhely
A szoftvertelepítő típusú telepítéssel létrehozott összes alkalmazást (például az üzletági alkalmazásokat) a rendszer becsomagolja és feltölti az Intune felhőtárhelyére. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A teljes előfizetés 20 GB tárterületet tartalmaz.

Az eredeti vásárlási móddal vásárolhat további tárterületet az Intune számára. Ha számla ellenében vagy hitelkártyával fizetett, keresse fel az [Előfizetés-kezelési portált](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions). Más esetben forduljon vállalatának partnercégéhez vagy értékesítési kapcsolattartójához.

A felhőtárhelyre vonatkozó követelmények az alábbiak:

-   Az összes alkalmazás telepítési fájljainak ugyanabban a mappában kell lenniük.
-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Alkalmazáskategóriák létrehozása és szerkesztése

Az alkalmazáskategóriák segítségével úgy rendezheti az alkalmazásokat, hogy a felhasználók könnyebben találják meg őket a céges portálon. Egy alkalmazáshoz több kategóriát is hozzárendelhet (például **Fejlesztői alkalmazások** és **Kommunikációs alkalmazások**).
Amikor hozzáad egy alkalmazást az Intune-hoz, kiválaszthatja a kívánt kategóriát. Az alkalmazások felvételéről és a kategóriák hozzárendeléséről az egyes platformokra vonatkozó témakörökből tájékozódhat. Saját kategóriáit a következő eljárással hozhatja létre és szerkesztheti:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** terület **Beállítás** szakaszában válassza az **Alkalmazáskategóriák** lehetőséget. 
5. Az **Alkalmazáskategóriák** panelen látható az aktuális kategóriák listája. Válasszon a következő lehetőségek közül:
    - **Új kategória létrehozása** – A **Hozzáadás** lehetőségre kattintva nyissa meg a **Kategória létrehozása** panelt, majd adjon meg egy nevet az új kategóriának. A neveket csak egy nyelven lehet megadni, és az Intune nem fordítja le őket. Ha végzett, kattintson a **Létrehozás** gombra.
    - **Kategória szerkesztése** – Bármelyik, a listán szereplő kategóriánál válassza a **...** elemet. Ez a lehetőség egy felugró menüt jelenít meg, amelyben **rögzítheti az irányítópulton** vagy **törölheti** a kategóriát.

## <a name="apps-added-automatically-by-intune"></a>Az Intune által automatikusan hozzáadott alkalmazások

Korábban az Intune számos beépített alkalmazást tartalmazott, melyeket hamar hozzá lehetett rendelni egy kategóriához. A visszajelzések alapján azonban eltávolítottuk ezt a listát, és többé már nem jelennek meg beépített alkalmazások.
Ugyanakkor ha vannak olyan beépített alkalmazások, melyeket korábban már hozzárendelt valamelyik kategóriához, azok továbbra is meg fognak jelenni az alkalmazások listáján. Ezek az alkalmazások szükség szerint továbbra is hozzárendelhetők.

## <a name="next-steps"></a>További lépések

Az alábbi témakörök ismertetik az egyes platformok alkalmazásainak felvételét az Intune-ba:

- [Androidos áruházbeli alkalmazások](store-apps-android.md)
- [Androidos üzletági alkalmazások](lob-apps-android.md)
- [iOS rendszerhez készült áruházbeli alkalmazások](store-apps-ios.md)
- [iOS-es üzletági alkalmazások](lob-apps-ios.md)
- [Webalkalmazások (az összes platformra)](web-app.md)
- [Windows Phone 8.1-es áruházbeli alkalmazások](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB-alkalmazások](lob-apps-windows-phone.md)
- [Microsoft Áruházbeli alkalmazások](store-apps-windows.md)
- [Windows LOB-alkalmazás](lob-apps-windows.md)
- [Windows 10-es Office 365-alkalmazások](apps-add-office365.md)
- [macOS-es Office 365-alkalmazások](apps-add-office365-macos.md)
- [Beépített alkalmazások](apps-add-built-in.md)

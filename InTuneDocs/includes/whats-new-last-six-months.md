## <a name="november-2016"></a>2016. november

### <a name="new-capabilities"></a>Új képességek

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Az új Munkahelyi Microsoft Intune-portál elérhető a Windows 10-es eszközökhöz__ A Microsoft új [Munkahelyi Microsoft Intune-portál alkalmazást adott ki Windows 10-es eszközökhöz](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Az új univerzális Windows 10 formátumot használó alkalmazás frissített, egységes felhasználói felületet nyújt az alkalmazáson belül és az összes Windows 10-es eszközön, számítógépen, illetve mobileszközön, miközben a jelenlegi funkcionalitása is megmarad.

Az új alkalmazással a felhasználók további platformszolgáltatásokat érhetnek majd el, mint például az egyszeri bejelentkezést (SSO) és tanúsítványalapú hitelesítést Windows 10-es eszközökön. Az alkalmazás a meglévő Windows 8.1 Vállalati portál frissítéseként lesz elérhető , amelyet a Windows Phone 8.1-es Vállalati portál telepít a Windows Áruházból. További részletekért látogasson el az [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) oldalra.

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Az Intune és az Android for Work használatával kapcsolatos tájékoztató__

> Az Android for Work-alkalmazásokat telepítheti a __Szükséges__ művelettel, azonban az __Elérhető__ művelettel csak akkor telepítheti az alkalmazásokat, ha az Intune-csoportok át lettek telepítve az új Azure AD csoportkezelési rendszerbe.

__Az Intune App SDK for Cordova beépülő modul most már támogatja a regisztráció nélküli MAM-ot__ Az alkalmazásfejlesztők mostantól az eszközök regisztrálása nélkül használhatják az Intune App SDK for Cordova beépülő modult a mobilalkalmazás-felügyeleti funkciók engedélyezéséhez az Android- és az iOS-rendszerhez készült, Cordova-alapú saját alkalmazásokban. Az Intune App SDK for Cordova beépülő modul [itt](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) található.

__Az Intune App SDK Xamarin összetevő most már támogatja a regisztráció nélküli MAM-ot__ Az alkalmazásfejlesztők mostantól az eszközök regisztrálása nélkül használhatják az Intune App SDK Xamarin összetevőt a mobilalkalmazás-felügyeleti funkciók engedélyezéséhez az Android- és az iOS-rendszerhez készült, Xamarin-alapú saját alkalmazásokban. Az Intune App SDK Xamarin összetevő [itt](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) található.

### <a name="notices"></a>Értesítések

__A Symantec aláíró tanúsítványának feltöltéséhez most már nincs szükség az aláírt Windows Phone 8 Munkahelyi portálra__ A Symantec aláíró tanúsítványának feltöltéséhez mostantól nincs szükség az aláírt Windows Phone 8 Munkahelyi portál alkalmazásra. A tanúsítványt függetlenül fel lehet tölteni.

###<a name="deprecations"></a>Elavulások

__A Windows Phone 8 Munkahelyi portál támogatása__ A Windows Phone 8 Munkahelyi portál támogatását kivezetjük. A Windows Phone 8 és WinRT platform támogatását 2016 októberében kivezettük. Egyúttal a Windows 8 vállalati portál támogatását is elavulttá minősítettük 2016 októberével.

## <a name="october-2016"></a>2016. október

### <a name="conditional-access-for-mobile-application-management"></a>Feltételes hozzáférés a mobilalkalmazás-kezeléshez
Lehetősége nyílik az Exchange Online-hoz való hozzáférés korlátozására, hogy az csak az Intune mobilalkalmazás-felügyeleti szabályzatokat támogató alkalmazások, például Outlook számára legyen elérhető. [Ez az új funkció](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) kiválóan együtt használható az Intune mobilalkalmazás-felügyeleti (MAM-) szabályzataival, mivel letilthatja vele a hozzáférést a beépített e-mail-ügyfélprogramokhoz vagy más alkalmazásokhoz, amelyek nincsenek még konfigurálva Intune MAM-szabályzatokkal. Ezzel biztosítható, hogy a felhasználók csak olyan alkalmazásokkal férhessenek hozzá a vállalati adatokhoz, amelyeket az Intune MAM használatával védenek. Az Intune mobilalkalmazás-felügyelettel az Azure-portálon ismerkedhet meg. Ehhez keresse a „Beállítások” panelen az új Feltételes hozzáférés szakaszt.

### <a name="conditional-access-for-windows-pcs"></a>Feltételes hozzáférés Windows rendszerű számítógépeken
Mostantól feltételes hozzáférési szabályzatokat hozhat létre az Intune felügyeleti konzoljával. Ezekkel megakadályozhatja, hogy a Windows rendszerű számítógépek elérjék az [Exchange Online-t](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) és a [SharePoint Online-t](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Olyan feltételes hozzáférési szabályzatokat is létrehozhat, amelyekkel az Office asztali és univerzális alkalmazásainak elérését gátolhatja meg.

### <a name="android-for-work-support"></a>Android for Work-támogatás

> [!IMPORTANT]

> Az Android for Work-alkalmazásokat telepítheti a __Szükséges__ művelettel, az __Elérhető__ művelettel azonban csak akkor telepítheti az alkalmazásokat, ha az Intune-csoportok lettek áttelepítve az új Azure AD csoportkezelési rendszerbe.

Az Intune immár része az Android for Work (AfW) programnak. Az AfW funkcióinak támogatását ebben a hónapban kezdjük bevezetni, és elkövetkező néhány hónapban pedig folytatjuk a bevezetésüket. Felhívjuk figyelmét, hogy az AfW telepítésre elérhető verziója már az új csoportosítási és célzási felületet használja. Az újonnan létrehozott Intune-szolgáltatásfiókok használhatják ezt a funkciót, amint az AfW elérhető számukra.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Olvassa el a Microsoft közleményét az Intune Android for Work-támogatásáról](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

A következő Intune témakörök új, vagy az Android for Workre vonatkozó, frissített információkat tartalmaznak:

Informatikai szakemberek számára:
- [Az Android for Work beállítása](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Az Exchange Online-hoz és az új dedikált Exchange Online-hoz való e-mail-hozzáférés korlátozása](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [A helyszíni Exchange-hez és az örökölt dedikált Exchange Online-hoz való e-mail-hozzáférés korlátozása](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work-alapú megfelelőségi szabályzatok beállításai](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work-alkalmazások telepítése](/intune/deploy-use/android-for-work-apps)
- [Android for Work-alkalmazások konfigurálása mobilalkalmazás-konfigurációs szabályzatok segítségével](/intune/deploy-use/afw-app-configuration-policy)
- [Az Android for Work szabályzatbeállításai](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Végfelhasználók számára:
- [Mi történik munkahelyi profil létrehozásakor?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Munkahelyi profil létrehozása és eszköz regisztrálása az Intune-ban](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Lookout-integráció iOS-eszközök védelméhez
Októbertől a Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az iOS- mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő iOS-eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást eszközükön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a vállalati adatokhoz való hozzáféréshez. Olvassa el a [Lookout for Work alkalmazások konfigurálása és telepítése](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) című témakört.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Intune-alkalmazásburkoló Android rendszerhez
Az Intune alkalmazásburkoló eszközével engedélyezheti, hogy az alkalmazások Intune-alapú mobilalkalmazás-felügyeleti (MAM-) szabályzatokat használjanak. Az Intune mobilalkalmazás-felügyeleti szabályzatai már az eszköz regisztrálása nélkül is támogatottak.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>A MAM-szabályzatokat használó felügyelt alkalmazásokból történő nyomtatás kezelése
Immár megakadályozhatja a vállalati adatok kinyomtatását a MAM-szabályzatokkal rendelkező alkalmazásokból. Ez a beállítás az [Azure-portálon](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) érhető el, és [iOS](/Intune/deploy-use/ios-mam-policy-settings) [Android](/Intune/deploy-use/android-mam-policy-settings) operációs rendszereket futtató eszközön egyaránt támogatott.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Ujjlenyomat-kezelés támogatása androidos eszközökön
Az androidos mobilalkalmazás-kezelési (MAM) szabályzatok mostantól lehetővé teszik a felhasználók számára, hogy ne a PIN-kódjuk beírásával, hanem az ujjlenyomatukkal érjenek el egy alkalmazást. [Ebben a témakörben megismerkedhet ezzel és a többi androidos mobilalkalmazás-kezelési szabályzat beállításaival](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Értesítések

__Android Samsung KNOX-kompatibilitás az Intune-nal__ Egyes Samsung Galaxy Ace-modelleket az Intune nem képes Samsung KNOX-eszközként kezelni. Amikor belépteti ezeket az eszközöket Intune-ba, azok csak szabványos Android-eszközként kezelhetők.

Az alábbi modellek érintettek:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Önnek és végfelhasználóinak ezzel kapcsolatban nincs semmilyen teendője. További információért látogasson el a [Samsung KNOX](https://www.samsungknox.com) webhelyre.

__A Windows 8-hoz készült Munkahelyi portál alkalmazás elavult; a Windows Phone 8 és a Windows RT platformok támogatását kivezetjük__ 2016 októberétől kivezetjük a Windows 8 Munkahelyi portál támogatását a Microsoft Intune-ban. Egyúttal a Windows Phone 8 és Windows RT platform Microsoft Intune-beli támogatását is kivezetjük. Ennek következményeképpen nem fog tudni Windows Phone 8 vagy Windows RT rendszerű eszközöket regisztrálni vagy frissíteni.

A már regisztrált Windows Phone 8, Windows RT és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.

2016 novemberétől megszüntetjük a Windows Phone 8 Vállalati portál támogatását.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Mi várható?

__Az új Munkahelyi Microsoft Intune-portál elérhető a Windows 10-es eszközökhöz__ A Microsoft új Munkahelyi Microsoft Intune-portált ad ki Windows 10-es eszközökhöz. Az új univerzális Windows 10 formátumot használó alkalmazás frissített, egységes felhasználói felületet nyújt az alkalmazáson belül és az összes Windows 10-es eszközön, számítógépen, illetve mobileszközön, miközben a jelenlegi funkcionalitása is megmarad.

Az új alkalmazással a felhasználók további platformszolgáltatásokat érhetnek majd el, mint például az egyszeri bejelentkezést (SSO) és tanúsítványalapú hitelesítést Windows 10-es eszközökön. Az alkalmazás a meglévő Windows 8.1 Vállalati portál frissítéseként lesz elérhető , amelyet a Windows Phone 8.1-es Vállalati portál telepít a Windows Áruházból. További részletekért látogasson el az [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) oldalra.
<!--TFS 1016502-->

## <a name="september-2016"></a>2016. szeptember
### <a name="new-features-announcements-and-information"></a>Új funkciók, bejelentések és információk
* [Windows feltételes hozzáférés](#windows-conditional-access)
* [iOS 10-támogatás](#ios-10-support)
* [Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integráció Android-eszközök védelméhez](#lookout-integration-to-protect-android-devices)
* [A Vállalati portál frissítései Android, iOS és Windows rendszeren](#company-portal-updates)
* [Intune-szószedet](#intune-glossary)
* [Mi várható?](#whats-coming)

### <a name="windows-conditional-access"></a>Windows feltételes hozzáférés
Mostantól feltételes hozzáférési szabályzatokat hozhat létre az Intune felügyeleti konzollal. Ezekkel megakadályozhatja, hogy a Windows rendszerű számítógépek elérjék az Exchange Online-t és a SharePoint Online-t. Olyan feltételes hozzáférési szabályzatokat is létrehozhat, amelyekkel az Office asztali és univerzális alkalmazásainak elérését gátolhatja meg.

### <a name="ios-10-support"></a>iOS 10-támogatás
A meglévő Intune MDM- és MAM-forgatókönyvek kompatibilisek az iOS 10 rendszerrel. Az [Intune támogatási csapatának blogjában](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/) tippeket olvashat.

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Az alkalmazásburkoló eszköz eszközregisztráció nélküli is lehetővé teszi a MAM használatát Android és iOS rendszereken
Az Intune alkalmazásburkoló eszköz egy parancssori eszköz, amellyel az Intune MAM üzleti (LOB) alkalmazások esetében is használható iOS és Android rendszereken. Ez a legegyszerűbb módja annak, hogy az Intune MAM SDK-t az alkalmazásba integrálja, így az alkalmazás kikényszerítheti az Intune-ban üzembe helyezett MAM-szabályzatokat. A MAM-szabályzatokkal lehetősége van:

1. Alkalmazásadatok titkosítására.
2. Megkövetelni, hogy az infómunkás PIN-kódot adjon meg az alkalmazás indításához.
3. Előírni, hogy az alkalmazás csak felügyelt alkalmazások számára továbbíthasson adatokat.
4. Letiltani, hogy az alkalmazás adatokat mentsen az Android, iTunes vagy iCloud rendszerekbe.
5. Előírni, hogy a kivágás, másolás és beillesztés műveleteket csak felügyelt alkalmazások között lehessen végrehajtani.

A frissített Intune alkalmazásburkoló eszköz nyilvános előzetes verziója már eszközregisztráció nélküli MAM-támogatást is nyújt az iOS és Android rendszereken futó belső üzleti alkalmazásokhoz. Ez azt jelenti, hogy a felhasználóknak nem szükséges regisztrálni az eszközeiket az Intune-ban a MAM által kezelt üzleti alkalmazások használatához.

A szoftver nyilvános előzetes verzióját bárki tesztelheti, és a GitHub msintuneappsdk oldalain hasznos dokumentáció is található hozzá:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

A Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásának telepítése előtt:

* Tekintse át a Microsoft licencfeltételeit a Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásához
* Nyomtassa ki és őrizze meg a licencfeltételeket. A Microsoft licencfeltételeit a Microsoft Intune alkalmazásburkoló Android és iOS rendszerekhez előzetes kiadásának letöltésével és használatával Ön elfogadja ezeket a licencfeltételeket. Amennyiben a feltételeket nem fogadja el, ne használja a szoftvert.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Az Intune-csoportok szeptembertől helyeződnek át az Azure Active Directory-ba
Egyes új Intune-fiókok az Intune felhasználói csoportok helyett Azure Active Directory-alapú biztonsági csoportokat fognak használni. Azt, hogy biztonsági csoportokkal dolgozik-e, onnan lehet tudni, hogy az Intune-portál csoportok lapján egy hivatkozás irányítja majd át az Azure felügyeli portáljára.

### <a name="lookout-integration-to-protect-android-devices"></a>Lookout-integráció Android-eszközök védelméhez
A Microsoft a Lookout-integrációt használja annak érdekében, hogy lehetővé váljon a kártevők, a kockázatos alkalmazások és más fenyegetések felderítése, és ezzel az Androidos mobileszközök védelme. A Lookout megoldásával megállapítható a fenyegetés szintje, amely konfigurálható is. Az Intune-ban létrehozhat egy megfelelőségi szabályzatot, amely a Lookout által elvégzett kockázatelemzés alapján megállapítja az eszköz megfelelőségét. A feltételes hozzáférési szabályzatokkal az eszköz megfelelőségének alapján engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz.

A nem megfelelő eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást az Android-eszközön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a hozzáférés biztosításához. További információ: [Hozzáférés korlátozása eszközök, hálózat és alkalmazáskockázat alapján](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>A Vállalati portál újdonságai

__Android__

<p style="margin-left: 40px">**„Értesítések” bevezetése a Munkahelyi portál androidos verziójában**<br/>
<p style="margin-left: 40px">A Munkahelyi portál androidos verziójában a kezdőlapon az „Értesítéseknek” új ikonja van. Az ikonra koppintva megnyílik az Értesítések lap, amely megjeleníti a végfelhasználók számára az összes figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Az iOS-alapú Munkahelyi portál alkalmazásban már elérhető ez az értesítési funkció. Az új Értesítések lap eredményeképpen, ha az eszköz már regisztrálva van, a Munkahelyi hozzáférés beállítása képernyő nem jelenik meg a Munkahelyi portál androidos verziójának minden egyes elindításakor vagy használatának folytatásakor. Ha létrehozza saját végfelhasználói útmutatóját, frissítse dokumentációját ezen változásnak megfelelően. A frissített képernyőképeket [itt](https://aka.ms/androidcpupdate) találja.  

__iOS__
<p style="margin-left: 40px">**Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
<p style="margin-left: 40px">Az iOS rendszerhez készült Microsoft Intune vállalati portál alkalmazás minden felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók már csak a legújabb verziót tudják letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem tudják használni a vállalati portált, és regisztrálni sem tudnak, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is frissíteniük kell a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Fejlesztések azzal kapcsolatban, hogy az iOS-végfelhasználók hogyan kapják meg az alkalmazásaikat**<br/>
<p style="margin-left: 40px">A következő változásokra került sor az iOS-es Vállalati portál alkalmazás alkalmazáscsempéivel kapcsolatban annak érdekében, hogy a felhasználók valamennyi alkalmazásukat egyetlen helyen, a Vállalati portál webhelyen láthassák különböző nézetekben. Az Apple korlátozásai tiltják az üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban; ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk.

<p style="margin-left: 40px">A **Vállalati alkalmazások** csempe korábban az összes alkalmazás listájára mutatott a Vállalati portál webhely ÖSSZES lapján, és ez a jövőben is így marad. A csempe neve **Minden alkalmazás**-ra változott.

<p style="margin-left: 40px">Az **Egyéb alkalmazások** csempe korábban a Vállalati portál alkalmazás azon alkalmazásokat listázó nézetére mutatott, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. A csempe neve **Kiemelt alkalmazások**-ra változott, és rákoppintás esetén a felhasználót a Vállalati portál webhely KIEMELT lapjára irányítja.

<p style="margin-left: 40px">A **Kategóriák** csempe korábban egy olyan nézetre mutatott a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza. A csempe neve nem változott, most azonban a Vállalati portál webhely KATEGÓRIÁK nézetére mutat. [Itt](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) talál frissített képernyőképeket.
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Felszólítás az iOS-es Managed Browser alkalmazás telepítésére, ha az informatikai részleg beállította ezt a követelményt az alkalmazás számára**<br/>
<p style="margin-left: 40px">Ha egy webklipet úgy konfigurált, hogy csak a felügyelt böngészőben nyíljon meg, de a felügyelt böngésző nincs telepítve az eszközön, akkor az eszközön futó Vállalati portál alkalmazás felszólítja a felhasználót, hogy a webklip telepítése előtt telepítse a felügyelt böngészőt.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**A Windows Phone 8.1-es Munkahelyi portál alkalmazás visszajelzési gombbal egészült ki**<br/>
<p style="margin-left: 40px">A Windows Phone 8.1-es Munkahelyi portál alkalmazás lehetővé teszi, hogy a végfelhasználók az új „visszajelzés küldése” gombbal visszajelzést küldjenek az alkalmazásról. A gomb megtalálásához koppintson a Munkahelyi portál alkalmazás képernyőjén alul jobbra látható „három pont” menüre, majd koppintson a **visszajelzés küldése** lehetőségre. Az anonimizált formában összegyűjtött visszajelzéseket a Microsoft a Munkahelyi portál alkalmazás nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Intune-szószedet</br>
A könyvtárban elhelyeztünk egy új, a [szószedetet tartalmazó témakört](https://docs.microsoft.com/intune/understand-explore/intune-glossary), hogy segítsünk megérteni az Intune termékben használat fogalmakat.

## <a name="august-2016"></a>2016. augusztus
### <a name="app-management"></a>Alkalmazáskezelés
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Rejtett és megjelenített alkalmazások iOS 9.3 alatt__ Az iOS 9.3-at vagy annál újabb verziójú operációs rendszert futtató eszközök esetében az iOS-es általános konfigurációs szabályzat rejtett és megjelenített alkalmazásokat tartalmazó listája segítségével:
- Megadhatja a felhasználók elől elrejtett alkalmazások listáját. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
- Megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.

Az így megadott alkalmazások egyaránt lehetnek Ön által telepített, illetve olyan beépített iOS-alkalmazások, mint az Üzenetek és a Megjegyzések. Részletekért lásd: [iOS-szabályzatbeállítások a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
__Engedélyezett és letiltott alkalmazások házirendje Samsung KNOX-eszközökhöz__ Mostantól egyedi szabályzatot konfigurálhat Samsung KNOX-eszközökhöz, amely lehetővé teszi az alábbiak egyikének létrehozását:
- Az eszközön nem futtatható alkalmazások listája. A tiltólistán szereplő alkalmazások nem aktiválhatók az eszközön, még ha telepítve is vannak.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung KNOX-ot futtató eszközökön használhatók.
Részletekért lásd: [Egyéni szabályzat használata alkalmazások engedélyezéséhez és tiltásához Samsung KNOX-eszközökön](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__A mobilalkalmazás-kezelési (MAM) szabályzatokkal kompatibilis új alkalmazások__ [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) és [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) operációs rendszer alatt a Yammer-alkalmazás már kompatibilis az [Intune mobilalkalmazás-kezelési (MAM) szabályzatokkal](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), függetlenül attól, hogy az eszköz regisztrálva van-e vagy sem.

A MAM-kompatibilis alkalmazások teljes listáját lásd a [Microsoft Intune-alkalmazáspartnerek](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) webhelyén.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune Viewer-alkalmazások__ Az új RMS-megosztó alkalmazás megjelenésével 2016 augusztusától kezdve megszüntetjük a következő Intune Viewer-alkalmazásokat:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer Android-eszközökre a Google Play Áruházból

Az Intune Viewer-alkalmazások használata helyett javasoljuk az új androidos [Rights Management alkalmazás (RMS-megosztó alkalmazás)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) használatát, amelynek segítségével három különálló alkalmazás helyett elég egyetlen alkalmazást telepítenie a vállalati fájlok Android-eszközökön való biztonságos megtekintéséhez. Onnantól kezdve, hogy az Intune Viewer alkalmazás már nem lesz támogatott, eltávolítjuk a Google Store áruházból, és nem lesz elérhető további használatra.

### <a name="device-management"></a>Eszközkezelés
__Android 7.0-támogatás__ Az Intune azonnali támogatást nyújt a hamarosan megjelenő Android 7.0 operációs rendszerhez mobileszközökön.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Az új jelszó távolról történő kérésének Google általi megszüntetése Android 7.0 rendszerű eszközökön
A Google megszünteti azt a lehetőséget, hogy a rendszergazdák és a végfelhasználók távolról új jelszót kérhessenek Android 7.0 rendszerű eszközükhöz. Korábban a rendszergazdák távolról új jelszót állíthattak be a felhasználók számára, a felhasználók pedig a Vállalati portálról tehették meg ugyanezt.



### <a name="company-portal-updates"></a>A Vállalati portál újdonságai
__Munkahelyi portál webhely__
- **Visszajelzési hivatkozás a Munkahelyi portálról a Microsofthoz** <br/>
A Vállalati portál webhelyen az oldal alján található új „Visszajelzés” hivatkozásra koppintva a felhasználók visszajelzést küldhetnek a Microsoftnak a webhellyel kapcsolatos tapasztalataikról. A névtelenített formában összegyűjtött visszajelzéseket a Microsoft a Vállalati portál nyújtotta felhasználói élmény tökéletesítésére használja fel.
<!--- TFS 1313657 checked--->

__iOS__
- **A Managed Browser iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
A Microsoft Intune Managed Browser alkalmazás iOS-verziója frissítve lett, és már támogatja az iOS 8.0-s vagy újabb rendszerű eszközöket. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható a jelenlegi Managed Browser alkalmazás, kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Mi várható?
__Az Intune-csoportok 2016 szeptemberétől Azure Active Directory-csoportokká alakulnak__ Az Intune egy új csoportkezelési megoldást vezet be, amely Azure Active Directory- (AAD-) biztonsági csoportokat használ felhasználói és eszközcsoportokként az Intune-ban. **Az új, Azure-alapú Intune felügyeleti portál bemutatása után** e csoportok használatával történik majd minden csoportfelügyeleti, valamint szabályzat- és profillétesítési művelet.

Az új felhasználói élmény kiküszöböli a csoportok szolgáltatások közti duplikálásának szükségességét, **hozzáférést nyújt néhány új Prémium szintű Azure Active Directory- (AADP-) csoportszolgáltatáshoz**, és bővíthetőséget tesz lehetővé a PowerShell és a Graph használatával. Emellett vállalati mobileszköz-felügyeleti szinten egyesíteni fogja a csoportfelügyeleti élményt.

A biztonsági csoportokra való áttérés lehetővé tételének érdekében a **jelenlegi felügyeleti konzol** felhasználói élménye is változni fog. **Az ezt érintő változtatások, valamint az AAD-biztonságicsoportok használata az Intune-dokumentációban lesznek rögzítve**.

Az Intune új felhasználói **a biztonsági csoportokat érintő egyes változásokkal előbb szembesülnek majd, mint a jelenlegi bérlők**.

A csoportfelügyelettel kapcsolatos változtatások mellett **a következő funkciók megszűnnek**:
- Tagok vagy csoportok kihagyása egy új csoport létrehozásakor
- **Nem csoportosított felhasználók** és **Nem csoportosított eszközök** csoportjai
- **Csoportok kezelése** a szolgáltatásadminisztrátori szerepkörben
- Egyéni, csoportalapú riasztások az értesítési szabályokkal kapcsolatban
- Pivotálás csoportokkal a jelentésekben
<!--- TFS 1295329--->

__„Értesítések” bevezetése a Vállalati portál Android-verziójában__ Szeptemberben egy frissítést adunk ki a Vállalati portál Android-verziójához, amely bevezet egy új **Értesítések** ikont a kezdőlapon. Az ikonra koppintva megnyílik az **Értesítések** oldal, amely megjeleníti a végfelhasználó számára az összes, figyelmet igénylő elemet, például az eszközök megfelelőségi problémáit, a regisztrációs frissítéseket és a regisztrációk aktiválását. Ha az iOS rendszerű Vállalati portál alkalmazást is használja, akkor már ismerheti az Értesítések nyújtotta felhasználói élményt. Az **Értesítések** lap bevezetésével nem fog a Vállalati portál Android-verziójának minden egyes elindításakor vagy folytatásakor megjelenni a **Vállalati hozzáférés beállítása** képernyő, ha az eszköz már regisztrálva van. Tisztában vagyunk azzal, hogy sokan hoztak létre végfelhasználói útmutatókat, és nagy hasznát veszik az előzetes értesítéseknek, amikor az útmutatók vagy a képernyőképek frissítésére lehet szükség. Kérjük, frissítsék a dokumentációkat, hogy azok tükrözzék a felhasználói élménnyel kapcsolatos közelgő változásokat. A frissített képernyőképek itt találhatók: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Szolgáltatások érvénytelenítése
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
Szeptembertől iOS operációs rendszer alatt a Microsoft Intune Vállalati portál alkalmazás valamennyi felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

- **A Managed Browser iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
Augusztusban az Intune egy olyan frissítést ad ki a Microsoft Intune Managed Browser alkalmazás iOS-verziójához, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket támogatja. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható lesz a jelenlegi Managed Browser alkalmazás, de kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253--->

- **A Windows 8 és a Windows Phone 8 Munkahelyi portál alkalmazásai 2016 szeptemberétől elavulttá válnak** <br/>
2016 szeptemberétől a Microsoft Intune nem támogatja tovább a Microsoft Intune Vállalati portál Windows Phone 8 és Windows 8 platformra készült alkalmazásait. Frissítése az eszközöket a Windows 8.1 és a Windows Phone 8.1 rendszerekre, és használja a megfelelő Windows 8.1 és Windows Phone 8.1 vállalati portál alkalmazásokat az alkalmazásoknak ezekre az eszközökre történő további terjesztésére.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>2016. július
### <a name="app-management"></a>Alkalmazáskezelés

__Az alkalmazáslétesítési profilok frissítéseivel kapcsolatos felhasználói élmény javítása__ Az Apple iOS üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.

Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában 3 évig érvényes. A létesítési profil viszont 1 év után lejár. Ettől a frissítéstől kezdve az Intune biztosítja azokat az eszközöket, amelyekkel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak. További információk: [iOS mobil létesítésiprofil-házirendek használata az üzletági alkalmazások naprakészen tartására](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Az Intune-hoz készült Xamarin SDK már elérhető__ Az Intune App SDK Xamarin összetevőjével engedélyezheti az Intune mobilalkalmazás-felügyeleti funkciókat a Xamarinnal készült, iOS vagy Android rendszerű alkalmazásokban. Az összetevőt a [Xamarin áruházban](https://components.xamarin.com/view/Microsoft.Intune.MAM) vagy a [Microsoft Intune GitHub-oldalon](https://github.com/msintuneappsdk) érheti el.
<!--- TFS 1061478 --->

### <a name="device-management"></a>Eszközkezelés
__Megnövelt eszközregisztrációs limit__ Az Intune a konfigurálható eszközök regisztrációs korlátját felhasználónként 5 eszközről 15-re növelte.
<!---TFS 1289896 --->

__Az Intune ügyfélszoftvert futtató Windows-számítógépeken érvénybe léptethető__
[TeamViewer](https://www.teamviewer.com)-integráció segítségével távsegítség-munkameneteket indíthat más Windows-számítógépekkel, ami jelentős előnyt jelent a végfelhasználói ügyfélszolgálat számára. Ez a lehetőség a Windows 7, 8, 8.1 és Windows 10 rendszerekre egyaránt kiterjed. Részletekért lásd: [A Windows rendszerű számítógépek a Microsoft Intune számítógépügyféllel való felügyeletének általános feladatai](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>A Vállalati portál újdonságai

__Munkahelyi portál webhely__
- **Továbbfejlesztett végfelhasználói élmény Windows-eszközök regisztrálásakor**<br/>
Egyértelműbbek lettek a feltételes hozzáféréses regisztráció lépései a Windows 8.1, valamint a Windows 10 asztali verzió és Windows 10 Mobile rendszerekhez készült Vállalati portálon. A felhasználók mostantól különálló „Eszközök regisztrációja” és „Munkahelyi csatlakoztatás” lépéseket látnak majd, ami megkönnyíti számukra az eszköz állapotának megállapítását, és a folyamat befejezését a Munkahelyi csatlakoztatás esetleges meghiúsulása után. A különálló lépések várhatóan a rendszergazdák számára is megkönnyítik majd a hibák felderítését és elhárítását. Korábban, ha a végfelhasználó regisztrációt és Munkahelyi csatlakozást próbált végezni, és a regisztráció sikeres volt, de a Munkahelyi csatlakoztatás meghiúsult, akkor a regisztrált eszköz nem jelent meg a felhasználók által azonosítható eszközök listáján, ami problémákat eredményezhetett.

__Android__
- **Androidos Munkahelyi portál alkalmazás**<br/>
Ha Android-végfelhasználók egy hibaüzenetet kapnak arról, hogy az eszközről hiányzik egy szükséges tanúsítvány, a „Probléma megoldása” gombra koppintva megtudhatják, milyen [lépésekkel](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) végezhetik el a hiányzó tanúsítvány telepítését. Ha a felhasználók elvégezték a lépéseket, de továbbra is egy „hiányzó tanúsítvány” hibaüzenetet kapnak, a rendszer megkéri őket, hogy adják meg a rendszergazdájuknak ezt a [hivatkozást](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), amely leírja azokat a lépéseket, amelyekkel a rendszergazda elháríthatja a tanúsítvánnyal kapcsolatos problémát.

- **Az alkalmazások közvetlen telepíthetőségének korlátozása regisztrált eszközökön**<br/>
Az Android rendszerű eszközökre mostantól nem lehet a Vállalati portál webhelyen keresztül alkalmazásokat telepíteni, ha az eszközök nincsenek regisztrálva az Intune-ban az Intune Vállalati portál alkalmazás Android-verziójával.
<!---TFS 1299082--->

__iOS__
- **Változások a készülékregisztráció-kezelői fiókokban az iOS-es Munkahelyi portál alkalmazásban**<br/>
A jobb teljesítmény és méretezhetőség érdekében az Intune mostantól nem jeleníti meg az összes készülékregisztráció-kezelő (DEM) eszközt az iOS-es Vállalati portál alkalmazás **Saját eszközök** panelén. Csak az alkalmazást futtató helyi eszköz fog megjelenni, és csak abban az esetben, ha azt korábban már regisztrálták a Vállalati portálon.

A DEM-felhasználó a helyi eszközön elvégezheti a kapcsolódó műveleteket, de a további regisztrált eszközök távoli felügyeleti teendői csak az Intune felügyeleti konzolon hajthatók végre. Emellett az Intune-ból kivezettük a DEM-fiókoknak az Apple Device Enrollment Programmal és az Apple Configurator eszközzel való használatát. Ezek a regisztrálási módszerek alapértelmezés szerint támogatják a megosztott iOS-eszközök felhasználó nélküli regisztrálását.

Csak akkor használjon DEM-fiókot, ha a megosztott eszközök felhasználó nélküli regisztrálása nem lehetséges. További információ: [Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Windows-szolgáltatások névváltozásai
- A [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) mostantól **Windows Hello for Business** néven érhető el.
- A [Vállalati adatvédelem](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) mostantól **Windows információvédelem** ismert.

## <a name="june-2016"></a>2016. június
### <a name="intune-service-health"></a>Az Intune szolgáltatás állapota
Az Intune-ra vonatkozó szolgáltatásállapot-adatok átkerültek a központi, a többi Microsoft-szolgáltatásról is információt nyújtó helyre. Ezt az információt mostantól az Office 365 felügyeleti portál Szolgáltatás állapota menüjében találja meg. További információkat [ebben a blogban](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) talál.

### <a name="app-management"></a>Alkalmazáskezelés
- **Továbbfejlesztett konfigurációs felület a Windows 10 vállalati adatkezelési szabályzatához.** Továbbfejlesztettük a Windows 10 vállalati adatkezelési házirendjének konfigurációs felületét az alkalmazásszabályok létrehozása, a hálózathatár-definíciók megadása és más vállalati adatvédelmi beállítások tekintetében. További tudnivalók: [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Enterprise Data Protection-házirend létrehozása a Microsoft Intune-nal).


### <a name="device-management"></a>Eszközkezelés
- **Windows Defender szabályzatbeállítás a vélhetően nemkívánatos alkalmazások elleni védelem biztosításához.** A Windows Defender egy új, **Potentially Unwanted Application Detection** (Vélhetően nemkívánatos alkalmazás észlelése) nevű beállításával bővült a Windows 10 asztali és mobil verziójának általános konfigurációs házirendje. Ezzel a beállítással biztosíthatja a regisztrált Windows rendszerű asztali számítógépek védelmét a Windows Defender által a vélhetően nemkívánatos osztályba sorolt szoftverek futtatása ellen. Biztosíthatja a védelmet ezen alkalmazások futtatása ellen, vagy a vizsgálati üzemmóddal jelentést készíthet a vélhetően nemkívánatos alkalmazások telepítéséről. További információ: [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) (A Windows 10 házirendbeállításai a Microsoft Intune-ban).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Feltételes hozzáférés
- **Cisco ISE-hálózati hozzáférés-vezérlési szabályzat az Intune-hoz.**  Azok az ügyfelek, akik a Cisco Identity Service Engine (ISE) 2.1 szolgáltatást, illetve a Microsoft Intune-t is használják, a hálózati hozzáférés-vezérlési szabályzatot beállíthatják az ISE szolgáltatásban.

    Ezen szabályzat használatakor azoknak az eszközöknek, melyeknek Wi-Fi vagy VPN használatával kell kapcsolódniuk a hálózathoz, meg kell felelniük a következő feltételeknek a hozzáférésük engedélyezéséhez:

    * Az Intune által felügyeltnek kell lenniük
    * Meg kell felelniük az Intune összes telepített megfelelőségi szabályzatának

 A nem megfelelő eszközökkel rendelkező végfelhasználókat kérni fogja a rendszer, hogy regisztráljanak, és hárítsák el a megfelelőségi problémákat, hogy hozzáférést kapjanak.
- **Feltételes hozzáférés böngészőhöz.** Feltételes hozzáférési házirendet állíthat be az [Exchange Online-hoz](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) és a [SharePoint Online-hoz](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), így azok csak a felügyelt és a szabályozásoknak megfelelő iOS- és Android-eszközök támogatott webböngészőiről érhetők majd el. Az Outlook Web Accessbe (OWA) és a SharePoint-webhelyekre iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a rendszer a bejelentkezés előtt kérni fogja az eszköz Intune-beli regisztrálását, valamint az esetleges szabályozási hiányosságok elhárítását.
<!---TFS 1175844--->

- **A Dynamics CRM Online támogatja a feltételes hozzáférést.** Feltételes hozzáférési házirendet állíthat be a [Dynamics CRM Online-hoz](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), hogy csak a felügyelt és a szabályozásnak megfelelő iOS- és Android-eszközök érhessék el. A Dynamics CRM mobilalkalmazásba iOS- vagy Android-eszközön bejelentkezni próbáló végfelhasználóktól a bejelentkezés végrehajtása előtt a rendszer kérni fogja a regisztrálást az Intune-ba, valamint a meg nem felelést okozó problémák megszüntetését.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Az Intune Munkahelyi portál újdonságai

__Androidos Munkahelyi portál alkalmazás__

- Ha a rendszergazdák az új „Az eszközök tiltsák le az ismeretlen forrásból származó alkalmazások telepítését (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az ismeretlen forrásokból származó alkalmazások telepítését le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Biztonság** menüben ki kell kapcsolniuk az **Ismeretlen források** lehetőséget. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.0+)” házirendet alkalmazzák, az Android 4.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Futtasson biztonsági fenyegetés elleni keresést az eszközön” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Google** > **Biztonság** menüben be kell kapcsolniuk a **Biztonsági fenyegetések keresése az eszközön** beállítást. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak az üzenetről és a beállítás bekapcsolásának okáról.

- Ha a rendszergazdák az új „Az USB-hibakeresés letiltásának megkövetelése (Android 4.2+)” házirendet alkalmazzák, az Android 4.2-vel és későbbi verziókkal rendelkező végfelhasználók számára „Az USB-hibakeresést le kell tiltani” üzenet jelenik meg. A felhasználóknak ekkor a **Beállítások** > **Fejlesztői beállítások** menüben ki kell kapcsolniuk az **USB-hibakeresést**. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) ad a felhasználóknak az üzenetről és a beállítás kikapcsolásának okáról.

- Ha a rendszergazdák az új „Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0+)” házirendet alkalmazzák, az Android 6.0-val és későbbi verziókkal rendelkező végfelhasználók számára „Az eszköz nem éri el a minimális Android biztonsági javítási szintet” üzenet jelenik meg. A felhasználóknak ekkor telepíteniük kell a szükséges biztonsági javítási szintet. A megfelelőségi üzenet tartalmaz egy hivatkozást, amely további [tájékoztatást](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) ad a felhasználóknak a biztonsági javítás telepítéséről és arról, hogy jelenleg melyik biztonsági javítási verzióval rendelkeznek.

__iOS rendszerű Munkahelyi portál alkalmazás__

- A végfelhasználó számára az üzleti alkalmazások telepítésekor egy továbbfejlesztett környezet jelenik meg. Ha az alkalmazás telepítése hosszú ideig tart, a felhasználók manuálisan szinkronizálhatják az eszközt a szinkronizálási folyamat kényszerített folytatásához. A végfelhasználói lépéseket [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Az iOS-eszköz manuális szinkronizálása) című szakaszban tekintheti meg.

- Az iOS rendszerhez készült Microsoft Intune Vállalati portál alkalmazás frissült, így már támogatja az iOS 8.0-s és újabb verzióit. A frissítés eredményeként a végfelhasználók csak akkor tudják telepíteni a Vállalati portál alkalmazást, és regisztrálni új eszközöket az Intune-ban, ha az eszközön az iOS 8.0-s vagy újabb verziója fut. Az iOS nem támogatott verzióját futtató eszközöket korábban regisztrált felhasználók továbbra is használhatják az eszközükön lévő Vállalati portál alkalmazást.


<!--HONumber=Jan17_HO1-->



# <a name="february-2017"></a>2017. február

## <a name="new-capabilities"></a>Új képességek

### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](/intune/whats-new/media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és -szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel. A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

## <a name="notices"></a>Értesítések

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A csoportmigráláshoz nem lesz szükség az iOS-eszközök csoportjainak vagy szabályzatainak frissítésére <!--898837-->
A vállalati eszközbeléptetési profil által előre hozzárendelt összes Intune-beli eszközcsoport esetében és az Azure Active Directory-eszközcsoportokba történő migrálás során a rendszer egy megfelelő dinamikus eszközcsoportot hoz létre az AAD-ben a vállalati eszközbeléptetési profil neve alapján. A rendszer ezzel biztosítja azt, hogy az eszközök a regisztráció során automatikusan bekerüljenek a megfelelő csoportba, valamint hogy ugyanazokat a szabályzatokat és alkalmazásokat kapják meg, mint az eredeti Intune-csoport.

Amint egy bérlő belép a csoportosítást és célcsoport-kezelést szolgáló migrálási folyamatba, az Intune automatikusan létrehoz egy dinamikus AAD-csoportot, amely igazodik a vállalati eszközbeléptetési profil által célzott Intune-csoporthoz. A célzott Intune-csoport Intune-rendszergazdai törlésével a megfelelő dinamikus AD-csoport törlése nem történik meg. A rendszer eltávolítja ugyan a csoporttagokat és a dinamikus lekérdezést, de maga a csoport addig megmarad, amíg a rendszergazda el nem távolítja azt az AAD portálon keresztül.

Hasonlóképpen, ha a rendszergazda módosítja a vállalati eszközbeléptetési profil által célzott Intune-csoportot, az Intune egy új dinamikus csoportot hoz létre az új profil-hozzárendelésnek megfelelően, de nem távolítja el a régi hozzárendeléshez létrehozott dinamikus csoportot.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak. A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows-eszközök új MDM-kiszolgálói címe <!--893007-->
Azok a Windows- és Windows Phone-felhasználók, akik megkísérelnek beléptetni egy eszközt, és a __manage.microsoft.com__ címet adják meg MDM-kiszolgálói címként (ha a rendszer kéri), hibaüzenetet kapnak. Az MDM-kiszolgálói cím __manage.microsoft.com__ címről __enrollment.manage.microsoft.com__ címre változik. Értesítse a felhasználókat, hogy ha a rendszer kéri, az __enrollment.manage.microsoft.com__ címet használják MDM-kiszolgálói címként egy Windows- vagy Windows Phone-eszköz regisztrációjakor. A CNAME felépítésében nincs szükség változtatásokra. A fenti változásról további információt az [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) weboldalon kaphat.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->
Márciustól kezdve az Androidhoz készült Céges portál alkalmazásban a [material design irányelveinek](https://material.io/guidelines/material-design/introduction.html) követésével gondoskodunk a még modernebb megjelenésről és működésről. A jobb felhasználói élményt többek között az alábbiak alkotják:

* __Színek__: a lapfejlécek színét módosítani lehet az egyéni színpaletta alapján.
* __Felület__: az Alkalmazások lapon frissítettük a Kiemelt alkalmazások és a Minden alkalmazás gombokat. A Keresés gomb mostantól lebegő műveletgombként jelenik meg.
* __Navigáció__: a Minden alkalmazás gomb lapnézetben jeleníti meg a kiemelt alkalmazásokat, az összes alkalmazást és a kategóriákat, így a navigálás egyszerűbb.
* __Szolgáltatás__: a Saját eszközök és az IT-csoport elérhetősége lapok olvashatósága javult.

A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Több felügyeleti eszköz társítása a Vállalati Windows Áruházhoz <!--926135-->
Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel). A részleteket lásd: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Az Intune Azure-beli előzetes verziójának újdonságait [Ide kattintva](https://docs.microsoft.com/intune-azure/introduction/whats-new) tekintheti meg.

## <a name="january-2017"></a>2017. január

### <a name="new-capabilities"></a>Új képességek

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>MAM-jelentések a konzolon a nem regisztrált eszközökről <!--677961-->
Új alkalmazásvédelmi jelentések érhetők el mind a regisztrált, mind a nem regisztrált eszközökkel kapcsolatban. További információ [a mobilalkalmazás-felügyeleti szabályzatok Intune-nal történő figyeléséről](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)

#### <a name="android-711-support---694397--"></a>Android 7.1.1-támogatás <!--694397-->
Az Intune mostantól teljes mértékben támogatja és képes felügyelni az Android 7.1.1-es verzióját.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>A következő probléma elhárítása: Az iOS-eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük <!--unknown-->
Ha a felhasználói eszközök elveszítik a kapcsolatot az Intune-nal, új hibaelhárítási lépések átadásával segítheti a felhasználókat a vállalati erőforrásokhoz való hozzáférés visszaszerzésében. Lásd: [Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Értesítések

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak.

A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

#### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely februártól kezdve támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![Céges portál webhely „hamburger” menüje](/Intune/whats-new/media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel. A korábbi és az új megjelenést mutató képernyőképeket [Az Intune alkalmazás felhasználói felületének újdonságai lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) találja.

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Új dokumentáció az alkalmazásvédelmi szabályzatokhoz <!--583398-->
Frissítettük a dokumentációnkat azon rendszergazdákra és alkalmazásfejlesztőkre gondolva, akik az Intune App Wrapping Tool eszközzel vagy az Intune App SDK-val szeretnék iOS-es és androidos alkalmazásaikban elérhetővé tenni az alkalmazásvédelmi szabályzatokat (más néven MAM-szabályzatokat).

A következő cikkek frissültek:

* [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Bevezetés a Microsoft Intune App SDK használatába](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [iOS-hoz készült Intune App SDK – fejlesztői útmutató](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

A következő cikkek most jelentek meg a dokumentumtárban:

* [Intune App SDK Cordova beépülő modul](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin összetevő](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Folyamatjelző sáv a Munkahelyi portál indításakor iOS-en <!--665978-->
Az iOS-re készült Munkahelyi portál alkalmazás indítóképernyőjén folyamatjelző sáv tájékoztatja a felhasználót a betöltési folyamatok menetéről. A számlálót fokozatosan váltja le a folyamatjelző sáv: bizonyos felhasználóknál már megjelenik, míg mások még a számlálót fogják látni.

## <a name="december-2016"></a>2016. december

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->
A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon. Mielőtt az összes Intune-bérlő számára elérhetővé tesszük a portált, a hónap második felében bizonyos kiválasztott bérlők számára előzetes hozzáférést biztosítunk az új felügyeleti megoldáshoz.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Addig is olvassa el az [új dokumentációt](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), amelyből megtudhatja, hogy miket tervezünk az Azure Portalon a Microsoft Intune szolgáltatásra vonatkozóan.

__Távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójában__ <!--747605--> Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Új képességek

__Többtényezős hitelesítés minden platformon__ <!--747590--> Mostantól többtényezős hitelesítést (MFA) írhat elő a felhasználók egy kiválasztott csoportja számára, ha iOS, Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközt regisztrálnak az Azure felügyeleti portálon. Ehhez konfigurálnia kell a többtényezős hitelesítést a Microsoft Intune regisztrációs alkalmazására vonatkozóan az Azure Active Directoryban.

__Lehetőség a mobileszközök regisztrációjának korlátozására__ <!--747596--> Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.
* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.
* Az iOS esetében fennáll egy további lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

### <a name="notices"></a>Értesítések

__Regisztráció többtényezős hitelesítésének áthelyezése az Azure-portálra__ <!--VSO 750545--> Korábban a rendszergazdák vagy az Intune-konzolban, vagy a Configuration Managerben (az 2016. októberinél korábbi kiadásokban) állították be a többtényezős hitelesítést az Intune-beli regisztrációra vonatkozóan. A funkció átdolgozásának köszönhetően mostantól a [Microsoft Azure Portalra](https://manage.windowsazure.com) kell bejelentkezni az Intune-beli hitelesítő adatokkal, és az Azure AD-ben lehet konfigurálni a többtényezős hitelesítést. Erről [itt](https://aka.ms/mfa_ad) olvashat részletesebb tájékoztatást.

__Az Androidon futó Company Portal alkalmazás már Kínában is elérhető__ <!--VSO 658093--> Az Androidon futó Company Portal alkalmazást Kínában is letölthetően tettük közzé. Kínában nem érhető el a Google Play áruház, ezért az androidos eszközöknek kínai alkalmazásáruházakból kell beszerezniük az alkalmazásokat. Az androidos Munkahelyi portál alkalmazás a következő áruházakból is letölthető lesz:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

A Munkahelyi portál alkalmazás androidos verziója a Google Play szolgáltatások segítségével kommunikál a Microsoft Intune szolgáltatással. A Google Play szolgáltatások egyelőre nem érhetők el Kínában, ezért a következő műveletek bármelyike akár 8 órát is igénybe vehet. 

|Intune felügyeleti konzol| Intune Munkahelyi portál alkalmazás Androidhoz |Intune Munkahelyi portál webhely|   
|---|---|---|
|Teljes törlés| Távoli eszköz eltávolítása| Eszköz eltávolítása (helyi és távoli)|
|Szelektív törlés| Eszköz alaphelyzetbe állítása| Eszköz alaphelyzetbe állítása|
|Új vagy frissített alkalmazás telepítése| Rendelkezésre álló üzleti alkalmazások telepítése| Eszköz PIN-kódjának alaphelyzetbe állítása|
|Távoli zárolás|||
|PIN-kód alaphelyzetbe állítása|||

### <a name="deprecations"></a>Elavulások

__A Firefox többé nem támogatja a Silverlightot__ <!--VSO TBA-->A Mozilla a [Firefox böngésző](https://www.mozilla.org/firefox) 2017 márciusában megjelenő 52-es verziójával kezdve megszünteti a Silverlight támogatását. Ez azt jelenti, hogy a Firefox 51-esnél újabb verzióiban nem fog tudni bejelentkezni a meglévő Intune-konzolba. Azt javasoljuk, hogy használja az Internet Explorer 10-es vagy 11-es verzióját, illetve a [Firefox 52-es előtti valamelyik verzióját](https://ftp.mozilla.org/pub/firefox/releases/) a felügyeleti konzol eléréséhez. Amikor az Intune átáll az Azure Portal használatára, számos [modern böngésző](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) használata fog elérhetővé válni, mivel többé nem lesz szükség a Silverlightra.

__Az Exchange Online mobilpostaláda-szabályzatainak eltávolítása__ <!--770687--> Decembertől kezdve a rendszergazdák sem megtekinteni, sem konfigurálni nem tudják az Exchange Online (EAS) mobilpostaláda-szabályzatait az Intune konzolban. Ez a változás december és január során folyamatosan terjed ki minden Intune-bérlőre. Minden meglévő szabályzat konfigurálva marad. Új szabályzatokat az Exchange Management Shell-lel lehet konfigurálni. További tájékoztatás [itt](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx) olvasható.

__Az Intune AV Player, Image Viewer, és PDF Viewer alkalmazások támogatása megszűnik az Android eszközökön__ <!--747553--> 2016 decemberének közepétől a felhasználók nem használhatják többé az Intune AV Player, Image Viewer, és PDF Viewer alkalmazásokat. Ezeket az alkalmazásokat felváltotta az Azure Information Protection alkalmazás. Az Azure Information Protection alkalmazásról [itt](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) olvashat további tájékoztatást.

## <a name="november-2016"></a>2016. november

### <a name="new-capabilities"></a>Új képességek

__Az új Munkahelyi Microsoft Intune-portál elérhető a Windows 10-es eszközökhöz__ A Microsoft új [Munkahelyi Microsoft Intune-portál alkalmazást adott ki Windows 10-es eszközökhöz](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Az új univerzális Windows 10 formátumot használó alkalmazás frissített, egységes felhasználói felületet nyújt az alkalmazáson belül és az összes Windows 10-es eszközön, számítógépen, illetve mobileszközön, miközben a jelenlegi funkcionalitása is megmarad.

Az új alkalmazással a felhasználók további platformszolgáltatásokat érhetnek majd el, mint például az egyszeri bejelentkezést (SSO) és tanúsítványalapú hitelesítést Windows 10-es eszközökön. Az alkalmazás a meglévő Windows 8.1 Vállalati portál frissítéseként lesz elérhető , amelyet a Windows Phone 8.1-es Vállalati portál telepít a Windows Áruházból. További részletekért látogasson el az [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) oldalra.

> [!IMPORTANT]
> __Az Intune és az Android for Work használatával kapcsolatos tájékoztató:__ Bár az Android for Work-alkalmazásokat telepítheti a __Szükséges__ művelettel, az __Elérhető__ művelettel csak akkor telepíthet alkalmazásokat, ha az Intune-csoportok át lettek telepítve az új Azure AD csoportkezelési rendszerbe.

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

[Olvassa el a Microsoft közleményét az Intune Android for Work-támogatásáról](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

A következő Intune témakörök új, vagy az Android for Workre vonatkozó, frissített információkat tartalmaznak:

Informatikai szakemberek számára:
- [Az Android for Work beállítása](/intune/deploy-use/set-up-android-for-work)
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

A nem megfelelő eszközök végfelhasználóit az eszköz regisztrálására fogja kérni a rendszer, amihez telepíteniük és aktiválniuk kell a Lookout for Work alkalmazást az Android-eszközön, valamint el kell hárítaniuk a Lookout for Work által jelentett fenyegetéseket a hozzáférés biztosításához. További információ: [Hozzáférés korlátozása eszközök, hálózat és alkalmazáskockázat alapján](https://docs.microsoft.com/en-us/intune/deploy-use/device-threat-protection).


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

- **Az iOS-es Vállalati portál alkalmazás támogatására vonatkozó módosítások**<br/>
Szeptembertől iOS operációs rendszer alatt a Microsoft Intune Vállalati portál alkalmazás valamennyi felhasználójának az alkalmazás legújabb verzióját kell használnia. Az új felhasználók csak a legújabb verziót fogják tudni letölteni, a jelenlegi felhasználóknak pedig frissíteniük kell erre a verzióra. A vállalati portál legújabb verziójához iOS 8.0-s vagy újabb operációs rendszer szükséges, ezért a régebbi iOS-verziót futtató eszközök felhasználói nem fogják tudni használni a vállalati portált, sem pedig regisztrálni, amíg nem frissítik az eszközt iOS 8.0-s vagy újabb verzióra, majd ezt követően a vállalati portál alkalmazást is a legújabb verzióra. Az iOS 8.0-s verziójánál régebbi verziót futtató regisztrált eszközök továbbra is láthatóak és felügyelhetőek lesznek az Intune felügyeleti konzolján.  

- **A Managed Browser iOS-verziójához legalább iOS 8.0 használata szükséges**<br/>
Augusztusban az Intune egy olyan frissítést ad ki a Microsoft Intune Managed Browser alkalmazás iOS-verziójához, amely csak az iOS 8.0-s vagy újabb rendszerű eszközöket támogatja. Bár az iOS 7.1 rendszerű eszközökön továbbra is használható lesz a jelenlegi Managed Browser alkalmazás, de kérjük, javasolja a felhasználóinak, hogy a Managed Browser új funkcióinak teljes körű kihasználása érdekében frissítsenek legalább iOS 8.0-s rendszerre.  
<!---TFS 1313253--->

- **A Windows 8 és a Windows Phone 8 Munkahelyi portál alkalmazásai 2016 szeptemberétől elavulttá válnak** <br/>
2016 szeptemberétől a Microsoft Intune nem támogatja tovább a Microsoft Intune Vállalati portál Windows Phone 8 és Windows 8 platformra készült alkalmazásait. Frissítése az eszközöket a Windows 8.1 és a Windows Phone 8.1 rendszerekre, és használja a megfelelő Windows 8.1 és Windows Phone 8.1 vállalati portál alkalmazásokat az alkalmazásoknak ezekre az eszközökre történő további terjesztésére.
<!---TFS 1255391--->

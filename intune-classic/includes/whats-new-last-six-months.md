## <a name="april-2017"></a>2017. április

### <a name="new-capabilities"></a>Új képességek

#### <a name="myapps-available-for-managed-browser---822308-822303--"></a>A MyApps elérhető a Felügyelt böngészőhöz is <!--822308, 822303-->

A Microsoft MyApps mostantól jobban működik a Felügyelt böngészőben. A Felügyelt böngésző felügyeletre ki nem jelölt felhasználói közvetlenül a MyApps szolgáltatásba kerülnek, ahol elérhetik a rendszergazda által nekik kiosztott SaaS-alkalmazásokat. Az Intune-felügyeletre kijelölt felhasználók továbbra is a Felügyelt böngésző beépített könyvjelzőjével érhetik el a MyApps szolgáltatást.

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Új ikonok a Felügyelt böngészőhöz és a Céges portálhoz <!--918433, 918431, 971473-->

A Managed Browser androidos és iOS-es verziója egyaránt megújult ikont kap. Ezen az Intune új jelvénye szerepel, így egységesebb lesz az Enterprise Mobility + Security (EM+S) programcsomag alkalmazásainak arculata. A Managed Browser új ikonját megnézheti az [Újdonságok az Intune-alkalmazás felhasználói felületén](/intune/whats-new-app-ui) oldalon.

A Céges portál androidos, iOS-es és windowsos verziója is új ikont kap az EM+S többi alkalmazásával való összhang jegyében. Ezek az ikonok fokozatosan jelennek majd meg az egyes platformokon áprilistól május végéig.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Bejelentkezési folyamatjelző az androidos Céges portálhoz <!--953374-->

Az androidos Céges portál alkalmazás frissítésének köszönhetően bejelentkezési folyamatjelző jelenik meg, ha a felhasználó elindítja az alkalmazást vagy folytatja a használatát. A folyamatjelző új állapotokon halad végig, ezek időrendben a következők: „Csatlakozás...”, „Bejelentkezés...” és „Biztonsági követelmények keresése...” – a felhasználó ezt követően fér hozzá az alkalmazáshoz. Az Androidhoz készült Céges portál alkalmazás új képernyőképei az [Újdonságok az Intune-alkalmazás felhasználói felületén](/intune/whats-new-app-ui) oldalon láthatók.

#### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Alkalmazások hozzáférésének letiltása a SharePoint Online-hoz <!-- 679339 -->

Most már lehetséges a [SharePoint Online-on](/intune-classic/deploy-use/mam-ca-for-sharepoint-online) keresztül létrehozni olyan alkalmazásalapú feltételes hozzáférési szabályzatokat olyan alkalmazások letiltásához, amelyekre nem vonatkozik alkalmazásvédelmi szabályzat. Az alkalmazásalapú feltételes hozzáférési forgatókönyv esetében az Azure Portal használatával meghatározhatja, hogy mely alkalmazásoknak legyen hozzáférése a SharePoint Online-hoz.

#### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Egyszeri bejelentkezés az iOS-es Céges portál alkalmazásból az iOS-re készült Outlookba <!--834012-->
Az iOS-es Céges portál alkalmazásba bejelentkezett felhasználóknak már nem kell ugyanazon az eszközön, ugyanazzal a fiókkal bejelentkezniük az Outlook alkalmazásba is. Az Outlook indításakor kiválaszthatják a fiókjukat, és automatikusan bejelentkezhetnek. Ezt a funkciót igyekszünk további Microsoft-alkalmazásokba is beépíteni.

#### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Jobb állapotjelentések az iOS-es Céges portál alkalmazásban <!--744866-->
Az iOS-es Céges portál alkalmazásban mostantól új, konkrétabb hibaüzenetek nyújtanak kézzelfoghatóbb információt arról, hogy mi történik az eszközökön. Ezek a hibaesetek korábban egy általános, „A Munkahelyi portál átmenetileg nem érhető el” című hibaüzenetet váltottak ki. Ha pedig valaki internetkapcsolat nélkül indítja el a Céges portál alkalmazást iOS-en, akkor a kezdőlapon tartósan látható marad a „Nincs internetkapcsolat” feliratú állapotsáv.

#### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Jobb telepítésiállapot-megjelenítés a Windows 10-es Céges portál alkalmazásban <!--676495-->

A Windows 10-es Céges portál alkalmazásban elindított alkalmazástelepítések új fejlesztései az alábbiakat tartalmazzák:
-   Gyorsabb jelentéskészítés az MSI-csomagok folyamatban lévő telepítéséhez
-   Gyorsabb jelentéskészítés a Windows 10 évfordulós frissítését és újabb kiadásait futtató eszközök modern alkalmazásainak folyamatban lévő telepítéséhez
-   Új folyamatjelző sáv a Windows 10 évfordulós frissítését és újabb kiadásait futtató eszközök modern alkalmazásainak telepítéséhez

Az új folyamatjelző sávot megnézheti az [Újdonságok az Intune-alkalmazás felhasználói felületén](/intune/whats-new-app-ui) oldalon.

#### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-es eszközök tömeges regisztrálása <!-- 747607 -->

Mostantól a Windows Configuration Designer (WCD) használatával a Windows 10 alkotói frissítéssel rendelkező nagy számú eszközt csatlakoztathat az Azure Active Directoryhez és az Intune-hoz. Ha Azure AD-bérlőhöz be szeretné kapcsolni a [tömeges MDM-regisztrálást](/intune-classic/deploy-use/bulk-enroll-windows), a Windows Configuration Designerrel hozzon létre olyan kiépítési csomagot, amely csatlakoztatja az eszközöket az Azure AD-bérlőhöz, majd alkalmazza a csomagot a csoportosan regisztrálni és felügyelni kívánt vállalati tulajdonú eszközökre. A csomagok alkalmazását követően az eszközök csatlakoznak az Azure AD-hez, regisztrálnak az Intune-ban, és készen állnak az Azure AD-felhasználók bejelentkezésére.  Az Azure AD-felhasználók általános jogú felhasználók ezeken az eszközökön, akik megkapják majd a kijelölt szabályzatokat és a kötelező alkalmazásokat. Az önkiszolgáló és a Céges portált használó módszer jelenleg nincs támogatva.

### <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](/intune/whats-new).

Az Intune Azure-beli előzetes verziójának újdonságait [Ide kattintva](/intune/whats-new) tekintheti meg.

### <a name="notices"></a>Értesítések

#### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

#### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Appx-változások az Azure-beli Intune-ban <!-- 1000270 -->

Az Intune Azure-ra való migrálásának keretében három appx-változást vezetünk be:

1. Új, kizárólag MDM-be regisztrált eszközökre telepíthető appx-alkalmazástípus a klasszikus Intune-konzolon.
2. A korábbi appx-alkalmazástípussal mostantól csak a PC-s Intune-ügynökkel felügyelt PC-ket lehet célozni.
3. A migráció során az összes korábbi appx MDM-es appx-re konvertálódik.

##### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

A változás nincs hatással a PC-s Intune-ügynökkel felügyelt eszközökön telepített példányokra. A migráció után azonban a migrált appx-eket nem lehet további, a PC-s Intune-ügynökkel felügyelt és korábban nem célzott eszközökre telepíteni.

##### <a name="what-action-do-i-need-to-take"></a>Mi a teendőm?

A migrálás után töltse fel újból az appx-et PC-s appx-ként, ha újabb PC-s telepítésekre készül. További tájékoztatást az Intune-ügyfélszolgálat blogján, az [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-változások az Azure-beli Intune-ban) című angol nyelvű bejegyzésben olvashat.  

#### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök

A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat ezen új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune/role-based-access-control).

### <a name="whats-coming"></a>Mi várható?

#### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Jobb bejelentkezési élmény a Céges portál alkalmazásokhoz minden platformon <!--User Story 1132123-->

Egy olyan változást jelentünk most be, amely a következő néhány hónapban érkezik, és amellyel javulni fog a bejelentkezési élmény az Intune Céges portál Android, iOS és Windows rendszerű alkalmazásaiban. A Céges portál alkalmazásnál az új felhasználói élmény automatikusan megjelenik minden platformon, miután az Azure AD-ban megjelenik a változtatás. Ezen kívül a felhasználók egy másik eszközről is bejelentkezhetnek a Céges portálba egy egyszeri használtra generált kóddal. Ez különösen akkor hasznos, ha a felhasználónak hitelesítő adatok nélkül kell bejelentkeznie.

Az [Újdonságok az alkalmazás felhasználói felületén](/intune/whats-new-app-ui) lapon képernyőképeket láthat a korábbi bejelentkezési módról, a hitelesítő adatokat használó új bejelentkezési élményről, és a másik eszközről történő bejelentkezési folyamatról.

#### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Készüljön fel a változásra: megváltozik az Intune Partner Portal <!-- 1050016 -->

A 2017. május közepén esedékes szolgáltatásfrissítés keretében eltávolítjuk az Intune Partner lapot manage.microsoft.com-ról.  

Ha Ön partneradminisztrátor, akkor a továbbiakban nem lesz lehetősége az Intune Partner lapon megnézni partnereit és intézkedni a nevükben. Ehelyett a Microsoft két másik partnerportáljának valamelyikére kell majd bejelentkeznie.

A [Microsoft Partnerközpontban](https://partnercenter.microsoft.com/) és a [Microsoft Office 365 Felügyeleti partnerközpontban](https://portal.office.com/) egyaránt bejelentkezhet az Ön által felügyelt ügyfélfiókokba. A továbbiakban partnerként ezeken a webhelyeken felügyelheti ügyfeleit.


#### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->

Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja.

Az új ATS-követelményeket érvényesítő Apple TestFlight alkalmazásban elérhetővé vált a Céges portál alkalmazás iOS rendszerű verziója. Ha szeretné kipróbálni az alkalmazást az ATS-megfelelőség tesztelése céljából, küldje el a kereszt- és vezetéknevét, az e-mail-címét és a munkahelye nevét a <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> e-mail-címre. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

## <a name="march-2017"></a>2017. március

### <a name="new-capabilities"></a>Új képességek

#### <a name="support-for-skycure"></a>A Skycure támogatása

A Microsoft Intune-nal mostantól már integrálható, Skycure nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Skycure által az eszközökről gyűjtött telemetriai adatokon alapul, például:

- Fizikai védelem
- Hálózatvédelem
- Alkalmazásvédelem
- Biztonsági rések elleni védelem

Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Skycure által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. Ezen szabályzatok használatával engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz az észlelt fenyegetések alapján. További információ: [Skycure Mobile Threat Defense-összekötő](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->

Az Androidhoz készült Céges portál alkalmazás új, modern megjelenésű és jobb élményt biztosító felhasználói felületet kap. Fontosabb frissítések:

- Színek: a Céges portál lapfejléceinek színe meghatározható az informatikai részleg által.
- Alkalmazások: az **Alkalmazások** lapon frissítettük a **Kiemelt alkalmazások** és a **Minden alkalmazás** gombokat.
- Keresés: az **Alkalmazások** lapon a **Keresés** gomb lebegő műveletgombként jelenik meg.
- Navigáció az alkalmazások között: a **Minden alkalmazás** gomb lapnézetben jeleníti meg a **Kiemelt alkalmazásokat**, az **Összes alkalmazást** és a **Kategóriákat**, így a navigálás egyszerűbb.
- Támogatás: a **Saját eszközök** és az **IT-csoport elérhetősége** lapok olvashatósága javult.

A változásokkal kapcsolatos további részletekért lásd: [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](/intune/whats-new-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->

A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>A Windows 10-es Céges portálhoz készült aláírási szkript <!--941642-->

A Windows 10-es Céges portál alkalmazás letöltésekor és közvetlen telepítésekor mostantól rendelkezésre áll egy olyan szkript, amely egyszerűbbé és hatékonyabbá teszi az alkalmazások aláírását a munkahelyen.   A szkript letöltéséhez és használati útmutatójához tekintse meg a [Windows 10-es Céges portálhoz készült Microsoft Intune aláírási szkriptet](https://aka.ms/win10cpscript) a TechNet gyűjteményében. A bejelentéssel kapcsolatos további részletekért olvassa el [A Windows 10-es Céges portál alkalmazás frissítése](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) című bejegyzést az Intune ügyfélszolgálati csapat blogján.


### <a name="notices"></a>Értesítések

#### <a name="support-for-ios-103"></a>Az iOS 10.3 támogatása

Az iOS 10.3-as kiadása 2017. március 27-től jelent meg az iOS felhasználók számára. Minden meglévő Intune MDM- és MAM-forgatókönyv kompatibilis a legújabb verziójú Apple operációs rendszerrel. Várakozásaink szerint a jelenleg rendelkezésre álló iOS-eszközökhöz elérhető összes meglévő Intune-szolgáltatás továbbra is működni fog, amikor a felhasználók az iOS 10.3-as verzióra frissítik az eszközeiket és az alkalmazásaikat.

Jelenleg nem tudunk ismert problémáról. Ha problémákat tapasztal az iOS 10.3-ban, forduljon [Intune támogatási csapatunkhoz](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Megújult támogatás az Android rendszert Kínában használó ügyfelek számára <!--720444-->

Kínában nem érhető el a Google Play Áruház, ezért az androidos eszközöknek kínai áruházakból kell beszerezniük az alkalmazásokat. A Céges portál alkalmazás ezt azzal segíti, hogy az Android rendszert Kínában használó ügyfeleket a Céges portál és az Outlook alkalmazások letöltéséhez helyi alkalmazásáruházakba irányítja át. Ezzel javul a mobileszköz-felügyelet és a mobilalkalmazás-felügyelet felhasználói élményének minősége, ha a feltételes hozzáférési szabályzatok engedélyezve vannak. Az androidos Céges portál és Outlook alkalmazások az alábbi kínai alkalmazásáruházakból tölthetők le:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Ajánlott eljárás: Gondoskodjon arról, hogy a Céges portál alkalmazásai naprakészek legyenek <!--879465-->

2016 decemberében kiadtunk egy olyan frissítést, amely lehetővé tette a többtényezős hitelesítés kényszerítését a felhasználók egy adott csoportjában Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközök regisztrációjakor. Ez a szolgáltatás nem működik az Androidhoz és az iOS-hez készült Céges portál alkalmazás bizonyos alapverziói nélkül (Android: v5.0.3419.0+ és iOS: v2.1.17+).

A Microsoft folyamatosan fejleszti az Intune-t, és az összes támogatott platformon új szolgáltatásokat vezet be a konzolhoz és a Céges portál alkalmazásokhoz kapcsolódóan. Ennek eredményeként a Microsoft csak olyan hibák javításait teszi közzé, amelyek a Céges portál alkalmazás jelenlegi verziójában találhatók meg. Javasoljuk, hogy az optimális felhasználói élmény érdekében a Céges portál alkalmazásainak legújabb verzióit használja.

>[!Tip]
> Gondoskodjon arról, hogy a felhasználók beállítsák az eszközeiket az alkalmazások megfelelő áruházból történő automatikus frissítésére. Ha az androidos Céges portál alkalmazást hálózati megosztáson tette elérhetővé, a legújabb verziót a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=49140) töltheti le.

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>A Microsoft Teams mostantól engedélyezve van az iOS és az Android rendszerű mobilalkalmazás-kezelés esetén

A Microsoft bejelentette a Microsoft Teams szolgáltatás általános rendelkezésre állását. Az iOS és az Android rendszerű frissített Microsoft Teams alkalmazások mostantól támogatják az Intune-beli mobilalkalmazás-kezelési képességeket, így a különböző csoportok mostantól többféle eszközön dolgozhatnak szabadon. A beszélgetések és a vállalati adatok védelme minden egyes ponton garantált. A [Microsoft Teams bejelentésével](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) kapcsolatos részleteket az Enterprise Mobility + Security blogon találja.


## <a name="february-2017"></a>2017. február

### <a name="new-capabilities"></a>Új képességek

### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](/intune/whats-new-app-ui).

### <a name="notices"></a>Értesítések

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A csoportmigráláshoz nem lesz szükség az iOS-eszközök csoportjainak vagy szabályzatainak frissítésére <!--898837-->
A vállalati eszközbeléptetési profil által előre hozzárendelt összes Intune-beli eszközcsoport esetében és az Azure Active Directory-eszközcsoportokba történő migrálás során a rendszer egy megfelelő dinamikus eszközcsoportot hoz létre az AAD-ben a vállalati eszközbeléptetési profil neve alapján. A rendszer ezzel biztosítja azt, hogy az eszközök a regisztráció során automatikusan bekerüljenek a megfelelő csoportba, valamint hogy ugyanazokat a szabályzatokat és alkalmazásokat kapják meg, mint az eredeti Intune-csoport.

Amint egy bérlő belép a csoportosítást és célcsoport-kezelést szolgáló migrálási folyamatba, az Intune automatikusan létrehoz egy dinamikus AAD-csoportot, amely igazodik a vállalati eszközbeléptetési profil által célzott Intune-csoporthoz. A célzott Intune-csoport Intune-rendszergazdai törlésével a megfelelő dinamikus AD-csoport törlése nem történik meg. A rendszer eltávolítja ugyan a csoporttagokat és a dinamikus lekérdezést, de maga a csoport addig megmarad, amíg a rendszergazda el nem távolítja azt az AAD portálon keresztül.

Hasonlóképpen, ha a rendszergazda módosítja a vállalati eszközbeléptetési profil által célzott Intune-csoportot, az Intune egy új dinamikus csoportot hoz létre az új profil-hozzárendelésnek megfelelően, de nem távolítja el a régi hozzárendeléshez létrehozott dinamikus csoportot.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak. A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows-eszközök új MDM-kiszolgálói címe <!--893007-->
Azok a Windows- és Windows Phone-felhasználók, akik megkísérelnek beléptetni egy eszközt, és a __manage.microsoft.com__ címet adják meg MDM-kiszolgálói címként (ha a rendszer kéri), hibaüzenetet kapnak. Az MDM-kiszolgálói cím __manage.microsoft.com__ címről __enrollment.manage.microsoft.com__ címre változik. Értesítse a felhasználókat, hogy ha a rendszer kéri, az __enrollment.manage.microsoft.com__ címet használják MDM-kiszolgálói címként egy Windows- vagy Windows Phone-eszköz regisztrációjakor. A CNAME felépítésében nincs szükség változtatásokra. A fenti változásról további információt az [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) weboldalon kaphat.

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->
Márciustól kezdve az Androidhoz készült Céges portál alkalmazásban a [material design irányelveinek](https://material.io/guidelines/material-design/introduction.html) követésével gondoskodunk a még modernebb megjelenésről és működésről. A jobb felhasználói élményt többek között az alábbiak alkotják:

* __Színek__: a lapfejlécek színét módosítani lehet az egyéni színpaletta alapján.
* __Felület__: az Alkalmazások lapon frissítettük a Kiemelt alkalmazások és a Minden alkalmazás gombokat. A Keresés gomb mostantól lebegő műveletgombként jelenik meg.
* __Navigáció__: a Minden alkalmazás gomb lapnézetben jeleníti meg a kiemelt alkalmazásokat, az összes alkalmazást és a kategóriákat, így a navigálás egyszerűbb.
* __Szolgáltatás__: a Saját eszközök és az IT-csoport elérhetősége lapok olvashatósága javult.

A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](/intune/whats-new-app-ui) érhetők el.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Több felügyeleti eszköz társítása a Vállalati Windows Áruházhoz <!--926135-->
Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel). A részleteket lásd: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](/intune/whats-new).

Az Intune Azure-beli előzetes verziójának újdonságait [Ide kattintva](/intune/whats-new) tekintheti meg.

## <a name="january-2017"></a>2017. január

### <a name="new-capabilities"></a>Új képességek

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>MAM-jelentések a konzolon a nem regisztrált eszközökről <!--677961-->
Új alkalmazásvédelmi jelentések érhetők el mind a regisztrált, mind a nem regisztrált eszközökkel kapcsolatban. További információ [a mobilalkalmazás-felügyeleti szabályzatok Intune-nal történő figyeléséről](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)

#### <a name="android-711-support---694397--"></a>Android 7.1.1-támogatás <!--694397-->
Az Intune mostantól teljes mértékben támogatja és képes felügyelni az Android 7.1.1-es verzióját.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>A következő probléma elhárítása: Az iOS-eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük <!--unknown-->
Ha a felhasználói eszközök elveszítik a kapcsolatot az Intune-nal, új hibaelhárítási lépések átadásával segítheti a felhasználókat a vállalati erőforrásokhoz való hozzáférés visszaszerzésében. Lásd: [Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Értesítések

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak.

A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

#### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely februártól kezdve támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A Céges portál webhely „hamburger” menüje](/intune/whats-new-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Új dokumentáció az alkalmazásvédelmi szabályzatokhoz <!--583398-->
Frissítettük a dokumentációnkat azon rendszergazdákra és alkalmazásfejlesztőkre gondolva, akik az Intune App Wrapping Tool eszközzel vagy az Intune App SDK-val szeretnék iOS-es és androidos alkalmazásaikban elérhetővé tenni az alkalmazásvédelmi szabályzatokat (más néven MAM-szabályzatokat).

A következő cikkek frissültek:

* [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](/intune/apps-prepare-mobile-application-management)
* [iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel](/intune/app-wrapper-prepare-ios)
* [Bevezetés a Microsoft Intune App SDK használatába](/intune/app-sdk-get-started)
* [iOS-hoz készült Intune App SDK – fejlesztői útmutató](/intune/app-sdk-ios)

A következő cikkek most jelentek meg a dokumentumtárban:

* [Intune App SDK Cordova beépülő modul](/intune/app-sdk-cordova)
* [Intune App SDK Xamarin összetevő](/intune/app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Folyamatjelző sáv a Munkahelyi portál indításakor iOS-en <!--665978-->
Az iOS-re készült Munkahelyi portál alkalmazás indítóképernyőjén folyamatjelző sáv tájékoztatja a felhasználót a betöltési folyamatok menetéről. A számlálót fokozatosan váltja le a folyamatjelző sáv: bizonyos felhasználóknál már megjelenik, míg mások még a számlálót fogják látni.

## <a name="december-2016"></a>2016. december

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->
A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon. Mielőtt az összes Intune-bérlő számára elérhetővé tesszük a portált, a hónap második felében bizonyos kiválasztott bérlők számára előzetes hozzáférést biztosítunk az új felügyeleti megoldáshoz.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Addig is olvassa el az [új dokumentációt](/intune/what-is-intune), amelyből megtudhatja, hogy miket tervezünk az Azure Portalon a Microsoft Intune szolgáltatásra vonatkozóan.

__Távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójában__ <!--747605--> Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com/) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Új képességek

__Többtényezős hitelesítés minden platformon__ <!--747590--> Mostantól többtényezős hitelesítést (MFA) írhat elő a felhasználók egy kiválasztott csoportja számára, ha iOS, Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközt regisztrálnak az Azure felügyeleti portálon. Ehhez konfigurálnia kell a többtényezős hitelesítést a Microsoft Intune regisztrációs alkalmazására vonatkozóan az Azure Active Directoryban.

__Lehetőség a mobileszközök regisztrációjának korlátozására__ <!--747596--> Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.
* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.
* Az iOS esetében fennáll egy további lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](/intune-classic/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.

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

__A Firefox többé nem támogatja a Silverlightot__ <!--VSO TBA-->A Mozilla a [Firefox böngésző](https://www.mozilla.org/firefox) 2017 márciusában megjelenő 52-es verziójával kezdve megszünteti a Silverlight támogatását. Ez azt jelenti, hogy a Firefox 51-esnél újabb verzióiban nem fog tudni bejelentkezni a meglévő Intune-konzolba. Azt javasoljuk, hogy használja az Internet Explorer 10-es vagy 11-es verzióját, illetve a [Firefox 52-es előtti valamelyik verzióját](https://ftp.mozilla.org/pub/firefox/releases/) a felügyeleti konzol eléréséhez. Amikor az Intune átáll az Azure Portal használatára, számos [modern böngésző](/azure/azure-preview-portal-supported-browsers-devices) használata fog elérhetővé válni, mivel többé nem lesz szükség a Silverlightra.

__Az Exchange Online mobilpostaláda-szabályzatainak eltávolítása__ <!--770687--> Decembertől kezdve a rendszergazdák sem megtekinteni, sem konfigurálni nem tudják az Exchange Online (EAS) mobilpostaláda-szabályzatait az Intune konzolban. Ez a változás december és január során folyamatosan terjed ki minden Intune-bérlőre. Minden meglévő szabályzat konfigurálva marad. Új szabályzatokat az Exchange Management Shell-lel lehet konfigurálni. További tájékoztatás [itt](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx) olvasható.

__Az Intune AV Player, Image Viewer, és PDF Viewer alkalmazások támogatása megszűnik az Android eszközökön__ <!--747553--> 2016 decemberének közepétől a felhasználók nem használhatják többé az Intune AV Player, Image Viewer, és PDF Viewer alkalmazásokat. Ezeket az alkalmazásokat felváltotta az Azure Information Protection alkalmazás. Az Azure Information Protection alkalmazásról [itt](/information-protection/rms-client/mobile-app-faq) olvashat további tájékoztatást.

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
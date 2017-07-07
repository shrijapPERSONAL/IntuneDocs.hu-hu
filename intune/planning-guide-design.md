---
title: "Terv létrehozása"
description: "Ez a cikk segít tervet kidolgozni a kizárólag felhőalapú Microsoft Intune-környezet megtervezéséhez és implementációjához."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fdd75bd2b96eb20e0e73b7f8f76cf1a5cc035011
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="create-a-design"></a>Terv létrehozása

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

A cikket a 2. szakasz többi témakörével párhuzamosan célszerű feldolgozni, A terv az útmutató korábbi szakaszainak követése közben gyűjtött adatokon és meghozott döntéseken alapul. A tervezési szakaszban az önálló Intune-ra fogunk összpontosítani, amely a Microsoft felhőalapú szolgáltatása.

Ugyan a helyszíni infrastruktúrával kapcsolatban csak minimális mennyiségű követelményt támasztunk, mégis érdemes felkészülni a tervkészítésre, hogy biztosan a saját céljainak és követelményeinek megfelelő mobileszköz-felügyeleti megoldás legyen a végeredmény.

Ezenfelül gyakorta előfordul, hogy az implementálási vagy a tesztelési fázisban módosítani kell a terven, és ezeket a módosításokat nagyon fontos az indokaikkal együtt azonnal dokumentálni. A terv a következő területeket tartalmazza:

-   Aktuális környezet

-   Intune-telepítési lehetőségek

-   Külső függőségek identitáskövetelményei

-   Eszközplatformmal kapcsolatos szempontok

-   Teljesítendő követelmények  

Vizsgáljuk meg ezeket a területeket részletesebben. 

## <a name="record-your-environment"></a>A munkakörnyezet dokumentálása

A terv elkészítését megelőző első lépés az aktuális munkakörnyezet dokumentálása. Ez a környezet ugyanis befolyásolhatja a tervezési döntéseket, ezért dokumentálni kell, és figyelembe kell venni a többi Intune-tervezési döntés meghozatalakor. Alább néhány, az aktuális környezet dokumentálásával kapcsolatos példát olvashat:

-   **Felhőbeli identitás**

    -   Használják-e a DirSync vagy az Azure Active Directory (Azure AD) Connect szoftvert?

    -   Összevont-e a környezet?

    -   Használható-e többtényezős hitelesítés?

-   **E-mail-környezet**

    -   Használnak-e Exchange-et, és ha igen, helyszíni vagy felhőbeli megoldásban?

    -   Folyamatban van-e az Exchange felhőbe való migrálása?

-   **Aktuális MDM-megoldás**

    -   Használnak-e jelenleg más MDM-megoldásokat?

    -   Milyen MDM-megoldást használnak a vállalati, illetve a dolgozói tulajdonban lévő eszközök esetében?

    -   Milyen képességeket használnak (pl. alkalmazások eszközbeállításai, Wi-Fi-konfigurációk stb.)?

    -   Milyen eszközplatformokat támogatnak?

    -   Hány felhasználó használja az MDM-megoldást, és milyen csoportokra vannak tagolva?

-   **Tanúsítványmegoldás**

    -   Van-e használatban tanúsítványmegoldás?

    -   Milyen típusú tanúsítványokat használnak?

-   **Rendszerfelügyelet**

    -   Hogyan felügyelik a PC-s és a kiszolgálói környezetet?

    -   Használják-e a System Center Configuration Managert? Használnak-e külső gyártótól származó rendszerfelügyeleti platformot?

-   **VPN-megoldás**

    -   Milyen VPN-megoldást használnak?

    -   A vállalati, illetve a dolgozói tulajdonban lévő eszközök esetében is használják?

Az aktuális MDM-környezet dokumentálásakor mindenképpen jegyezze fel azokat a projekteket és más érvényben lévő terveket, amelyek hatással lehetnek a környezetre. Alább egy példával szemléltetjük, hogyan lehet az Intune-terv elkészítéséhez hasznos módon dokumentálni az aktuális környezetet:

| **Megoldásterület** | **Aktuális környezet** | **Megjegyzések** |
|:---:|:---:|:---:|
| **Identitás** | Azure AD, Azure AD Connect, nem összevont, nincs MFA | Folyamatban lévő projekt: MFA megvalósítása az év végéig |                 
| **E-mail-környezet** | Helyszíni Exchange, online Exchange | Folyamatban van a migrálás a helyszíni Exchange-ről az online-ra. A postafiókok 75%-át már migráltuk, és a maradék 25% migrálása is lezajlik az Intune-próbaüzem megkezdése előtt. |                
| **SharePoint** | Helyszíni SharePoint | Nem tervezzük a SharePoint felhőbe költöztetését |  
| **Aktuális MDM** | Exchange ActiveSync |  |
| **Tanúsítványmegoldás** | Microsoft Server 2012 R2, AD tanúsítványszolgáltatások | Csak nyilvános kulcsú infrastruktúrát használunk a webhelykiszolgálókhoz |
| **Rendszerfelügyelet** | System Center Configuration Manager CB 1606 | Meg szeretnénk vizsgálni a hibrid Intune-megoldás lehetőségét |
| **VPN-megoldás** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Intune-telepítési lehetőség választása

Az Intune kétféle telepítési lehetőséget kínál, ezek az önálló és a hibrid. Önnek kell eldöntenie, melyik illik jobban az üzleti követelményeikhez. Önálló telepítés esetén az Intune szolgáltatás a felhőben fut, hibrid telepítés esetén pedig az Intune integrálva van a System Center Configuration Managerrel.

- További információ [az önálló Microsoft Intune és a System Center Configuration Managerrel integrált hibrid mobileszköz-felügyelet közötti választáshoz](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Az Intune-bérlő földrajzi helye

A globálisan jelen lévő vállalatoknak a szolgáltatásra való előfizetéskor célszerű megtervezniük, hogy hol tartják a bérlőjüket. Az ország az első Intune-előfizetésre való regisztráláskor lesz definiálva, és az alább felsorolt régiókban helyezkedhet el:

-   Észak-Amerika

-   Európa, Közel-Kelet és Afrika

-   Ázsia és a Csendes-óceáni térség

>[!IMPORTANT]
> Az országot és a bérlő helyét később nem lehet módosítani.

## <a name="external-dependencies"></a>Külső függőségek

A külső függőségek olyan szolgáltatások és termékek, amelyek ugyan nem részei az Intune-nak, de vagy követelményei, vagy integrálódhatnak vele. Fontos feltérképezni az esetleges külső függőségekkel kapcsolatos követelményeket és konfigurációs sajátságokat. Az alábbiakban néhány gyakoribb külső függőséget sorolunk fel:

-   Identitás

-   Felhasználói és eszközcsoportok

-   Nyilvános kulcsú infrastruktúra

Vizsgáljuk meg részletesebben ezeket a gyakori külső függőségeket

### <a name="identity"></a>Identitás

A szervezethez tartozó, eszközt regisztráló felhasználókat az identitásuk révén azonosítjuk. Az Intune-hoz az Azure Active Directoryt (Azure AD) kell használni identitásszolgáltatóként. Ha már ezt a szolgáltatást használják, akkor ki lehet használni a máris a felhőben lévő identitásokat. A helyszíni felhasználói identitások és a Microsoft felhőszolgáltatásai közötti szinkronizálást pedig az Azure AD Connect eszközzel ajánlott elvégezni. Ha a szervezet már használja az Office 365-öt, akkor fontos, hogy az Intune is ugyanazt az Azure Active Directory-környezetet használja.

Az Intune identitással kapcsolatos követelményeiről alább olvashat bővebben.

-   További tudnivalók [az identitással kapcsolatos követelményekről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   További tudnivalók [a címtár-szinkronizálás követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   További tudnivalók [a többtényezős hitelesítés követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

### <a name="user-and-device-groups"></a>Felhasználói és eszközcsoportok

A felhasználói és eszközcsoportok határozzák meg a telepített környezet célterületét. A telepítés célozhat többek között szabályzatokat, alkalmazásokat vagy profilokat. A csak a felhőben üzemelő Intune támogatja a felhasználói és eszközcsoportokat – Önnek kell megadnia, hogy milyen felhasználói és eszközcsoportokra lesz szükség. Célszerű a helyszíni Active Directoryban létrehozott összes csoportot szinkronizálni az Azure Active Directoryba. A felhasználói és eszközcsoportok megtervezéséről és létrehozásáról alább olvashat bővebben.

-   További tudnivalók [a felhasználói és eszközcsoportok megtervezéséről](/intune-classic/deploy-use/plan-your-user-and-device-groups)

-   Útmutató [a felhasználói és eszközcsoportok létrehozásához](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)

### <a name="public-key-infrastructure-pki"></a>Nyilvános kulcsú infrastruktúra (PKI)

A nyilvános kulcsú infrastruktúra tanúsítványokat szolgáltat, amelyekkel az eszközök vagy a felhasználók biztonságosan hitelesíthetik magukat egy szolgáltatásban. Az Intune a Microsoft PKI-infrastruktúráit támogatja. A mobileszközökhöz a tanúsítványalapú hitelesítés követelményeinek való megfelelés érdekében felhasználói és eszköztanúsítványokat is ki lehet bocsátani. A tanúsítványhasználat implementálása előtt meg kell állapítani, hogy szükség van-e tanúsítványokra, a hálózati infrastruktúra támogatja-e a tanúsítványalapú hitelesítést, és hogy a jelenlegi környezetben használnak-e tanúsítványokat.

Ha az Intune VPN-, Wi-Fi- vagy e-mail-profiljaihoz tanúsítványokat tervez használni, bizonyosodjon meg róla, hogy a szervezetnél már ki van alakítva a tanúsítványprofilok létrehozására és üzembe helyezésére kész, támogatott [PKI-infrastruktúra](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles).

Továbbá ha SCEP-tanúsítványokat fognak kibocsátani, akkor el kell dönteni, hogy melyik kiszolgálón fog üzemelni a Hálózati eszközök tanúsítványigénylési szolgáltatása (NDES), és hogyan fog zajlani a kommunikáció.

További tudnivalók az Intune-ban történő tanúsítványkonfigurálásról:

-   [SCEP-tanúsítványinfrastruktúra konfigurálása](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)

-   [PFX-tanúsítványinfrastruktúra konfigurálása](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Intune-tanúsítványprofilok konfigurálása](/intune-classic/deploy-use/configure-intune-certificate-profiles)

-   [Erőforrás-hozzáférési szabályzatok konfigurálása](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)

## <a name="device-platform-considerations"></a>Eszközplatformmal kapcsolatos szempontok

Csak az eszközök alaposabb ismeretében lehet jól megérteni helyes konfigurálásuk mikéntjét.

-   A támogatott eszközplatformok meghatározása

-   Eszközök

-   Az eszközök tulajdonjoga

-   Tömeges regisztrálás

Vizsgáljuk meg ezeket a területeket részletesebben.

### <a name="determine-supported-device-platforms"></a>A támogatott eszközplatformok meghatározása

A terv kidolgozásakor tudnia kell, hogy milyen eszközök lesznek a környezetben, és ellenőrizni kell, hogy ezeket az Intune támogatja-e. Az Intune az iOS, az Android és a Windows platformot támogatja.

-   További tudnivalók [az Intune által támogatott eszközökről](/intune-classic/get-started/supported-mobile-devices-and-computers)

### <a name="devices"></a>Eszközök

Az Intune a mobileszközök felügyelete révén védi a vállalati adatokat és teszi lehetővé, hogy a végfelhasználók több helyszínen is dolgozhassanak. A szolgáltatás több eszközplatformot is támogat, ezért javasolt a szervezet tervében dokumentálni a támogatni tervezett eszközöket és OS-platformokat. Itt lehet részletezni a Használati esetek követelményeinek meghatározása című szakaszban létrehozott eszköz- és platformfelsorolást.

Célszerű a verziókat is feljegyezni, hogy a lista használható legyen az eszközképességek OS-platform és -verzió szerinti keresésekor. Például:

| **Eszközplatform** | **Operációsrendszer-verziók** |
|:---:|:---:|
| iOS – iPhone | 9.0+ |                
| iOS – iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10-es táblagépek | 10+ |

### <a name="device-ownership"></a>Az eszközök tulajdonjoga

Az Intune mind a vállalati, mind a dolgozói tulajdonban lévő eszközöket képes kezelni. Azok az eszköz minősülnek vállalati tulajdonúnak, amelyeket egy eszközregisztráció-kezelő vagy egy készülékregisztrációs program (DEP) regisztrál. Ilyen lehet egy, az Apple DEP által regisztrált eszköz, amelyet megjelölnek vállalati tulajdonúként, és egy olyan eszközcsoportba helyezik, amely célzott vállalati szabályzatokat és alkalmazásokat kap.

A vállalati és a dolgozói tulajdonban lévő eszközökkel kapcsolatos használati esetekről a [3. szakasz: Használatieset-forgatókönyvek követelményeinek meghatározása](planning-guide-requirements.md) nyújt további tájékoztatást.

### <a name="bulk-enrollment"></a>Tömeges regisztrálás

A vállalati portálon történő önkiszolgáló regisztráción kívül még több más módon is lehet eszközöket regisztrálni az Intune-ban. A tömeges regisztrálás a platformtól függően többféleképpen történhet. Ha tömeges regisztrálásra lesz szükség, akkor döntsön annak módjáról, és a tervet ennek megfelelően dolgozza ki. A tömeges regisztrálás különféle módjairól alább olvashat bővebben.

-   További tudnivalók [a tömeges regisztrálásról](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Funkciókövetelmények

Ezekben a szakaszokban a következő, a használatieset-forgatókönyvek követelményeihez kapcsolódó funkciókat és képességeket vizsgáljuk meg:

-   Használati feltételekkel kapcsolatos szabályzatok

-   Konfigurációs szabályzatok

-   Erőforrás-profilok

-   Alkalmazások

-   Megfelelőségi szabályzat

-   Feltételes hozzáférés

Vizsgáljuk meg ezeket a területeket részletesebben.

### <a name="terms-and-conditions-policies"></a>Használati feltételekkel kapcsolatos szabályzatok

A használati feltételekben lehet feltüntetni azokat a szabályzatokat vagy kikötéseket, amelyeket a regisztrálás előtt a felhasználónak el kell fogadnia. Az Intune-ban több használati feltételekkel kapcsolatos szabályzatot is fel lehet venni és üzembe lehet helyezni a felhasználói csoportok számára. Önnek kell eldöntenie, hogy van-e szükség használati feltételekkel kapcsolatos szabályzatokra, illetve ha igen, akkor a szervezetben kinek a feladata ezeket kidolgozni.

-   Útmutató [használati feltételekkel kapcsolatos szabályzatok létrehozásához](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) az Intune-ban. Alább láthat egy példát a használati feltételekkel kapcsolatos szabályzatok dokumentálására.

| **Feltételek és kikötések neve** | **Használati eset** | **Célcsoport** |
|:---:|:---:|:---:|
| Vállalati feltételek | Vállalati | Vállalati felhasználók |                 
| BYOD-feltételek | BYOD | BYOD-felhasználók |                

### <a name="configuration-policies"></a>Konfigurációs szabályzatok

A konfigurációs szabályzatok az eszközök biztonsági beállításainak és szolgáltatásainak kezelésére használhatók. A konfigurációs szabályzatok megtervezésekor a használati esetek követelményeit taglaló szakasz alapján határozza meg az Intune-eszközökhöz szükséges konfigurációkat. Dokumentálja, hogy mely beállításokat és hogyan kell konfigurálni, továbbá hogy ezek mely felhasználói vagy eszközcsoportokra vonatkoznak.

Platformonként legalább egy konfigurációs szabályzatot célszerű létrehozni, de szükség esetén többet is lehet. Az alábbi példában négy különféle konfigurációs szabályzat látható, különböző platformokhoz és használatieset-forgatókönyvekhez.

| **Szabályzat neve** | **Eszközplatform** | **Beállítások** | **Célcsoport** |   
|:---:|:---:|:---:|:---:|
| Vállalati – iOS | iOS | PIN-kód szükséges, Hossz: 6, Felhőbeli biztonsági mentés korlátozása | Vállalati eszközök |                                                           
| Vállalati – Android | Android | PIN-kód szükséges, Hossz: 6, Felhőbeli biztonsági mentés korlátozása | Vállalati eszközök |                                                           
| BYOD – iOS  | iOS | PIN-kód szükséges. Hossz: 4 | BYOD-eszközök |
| BYOD – Android  | Android | PIN-kód szükséges. Hossz: 4 | BYOD-eszközök |

### <a name="profiles"></a>Profilok

A végfelhasználók profilok segítségével kapcsolódnak a vállalati adatokhoz. Az Intune számos profiltípust támogat. A [profilok](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune) konfigurálásával kapcsolatos döntéseket a használati esetek és követelményeik alapján hozza meg. Az eszközprofilok platformtípusok szerint vannak kategóriákba sorolva, és célszerű belefoglalni őket a tervdokumentációba.

-   Tanúsítványprofilok

-   Wi-Fi profil

-   VPN-profil

-   E-mail profil

Vizsgáljuk meg ezeket a profiltípusokat részletesebben.

##### <a name="certificate-profiles"></a>Tanúsítványprofilok

Az Intune a tanúsítványprofilok alapján bocsát ki tanúsítványokat a felhasználók és eszközök számára. Az Intune a következő típusokat támogatja:

-   SCEP protokoll

-   Megbízható főtanúsítvány

-   PFX-tanúsítvány

Ajánlott dokumentálni, hogy mely felhasználói csoportoknak van szüksége tanúsítványra, hány tanúsítványprofilra lesz szükség, és mely felhasználói csoportokhoz kell őket telepíteni.

>[!NOTE]
> Ne feledje, hogy a SCEP-tanúsítványokhoz megbízható főtanúsítvány is szükséges. Ezért gondoskodjon róla, hogy minden SCEP-tanúsítványt kapó felhasználó kapjon megbízható főtanúsítványt is. Ha SCEP-tanúsítványokra van szükség, tervezze meg és dokumentálja a szükséges SCEP-tanúsítványsablonokat.

Az alábbi példa szemlélteti, hogyan lehet dokumentálni a tanúsítványokat a tervezés folyamán:

| **Típus** | **Profilnév** | **Eszközplatform** | **Használati esetek** |   
|:---:|:---:|:---:|:---:|
| Legfelső szintű hitelesítésszolgáltató | Vállalati legfelső szintű hitelesítésszolgáltató | Android, iOS, Windows Mobile | Vállalati, BYOD  |                                                           
| SCEP | Felhasználói tanúsítvány | Android, iOS, Windows Mobile | Vállalati, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Wi-Fi-profil

A Wi-Fi-profilok révén a mobileszközök automatikusan csatlakozhatnak a vezeték nélküli hálózatokhoz. Az Intune-ban az összes támogatott platformhoz lehet Wi-Fi-profilt üzembe helyezni.

-   További tudnivalók [az Intune Wi-Fi-profiltámogatásáról.](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)

Az alábbi példa a Wi-Fi-profilok tervezését szemlélteti:

| **Típus** | **Profilnév** | **Eszközplatform** | **Használati esetek** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Ázsiai Wi-Fi-profil | Android | Vállalati, BYOD, ázsiai régió|                                                           
| Wi-Fi | Észak-amerikai Wi-Fi-profil | Android, iOS, Windows 10 Mobile | Vállalati, BYOD, észak-amerikai régió |                                                           

##### <a name="vpn-profile"></a>VPN-profil

A VPN-profilok révén a felhasználók biztonságosan érhetik el a vállalati hálózatot távolról. Az Intune egyaránt támogatja a natív mobil VPN-kapcsolatokon alapuló és a külső gyártók által készített VPN-profilokat.

-   További tudnivalók [a VPN-profilokról és az Intune által támogatott gyártókról](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune).

Az alábbi példában egy VPN-profil dokumentálását szemléltetjük.

| **Típus** | **Profilnév** | **Eszközplatform** | **Használati esetek** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN, Cisco, bármilyen csatlakozási profil | Android, iOS, Windows 10 Mobile | Vállalati, BYOD, Észak-Amerika és Németország|                                                           
| VPN | Pulse Secure | Android | Vállalati, BYOD, ázsiai régió |                                                           

##### <a name="email-profile"></a>E-mail-profil

Az e-mail-profilokkal a levelezőprogramokban automatikusan be lehet állítani a kapcsolati adatokat és az e-mail-konfigurációt. Az Intune csak bizonyos eszközökön támogatja az e-mail-profilokat.

-   További tudnivalók az [e-mail-profilokról](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) és a támogatott platformokról.

Az alábbi példában az e-mail-profilok dokumentálását szemléltetjük:

| **Típus** | **Profilnév** | **Eszközplatform** | **Használati esetek** |   
|:---:|:---:|:---:|:---:|
| E-mail-profil | iOS-es e-mail-profil | iOS | Vállalati – Infómunkás BYOD |                                                           
| E-mail-profil | Android Knox e-mail-profil | Android Knox | BYOD |

### <a name="apps"></a>Alkalmazások

Az Intune-nal többféleképpen is el lehet juttatni alkalmazásokat a felhasználókhoz vagy az eszközökre. Az eljuttatott alkalmazás lehet szoftvertelepítő, nyilvános alkalmazás-áruházból származó vagy külső hivatkozással elérhető alkalmazás, vagy felügyelt iOS-alkalmazás. Az egyesével történő alkalmazástelepítésen kívül a mennyiségi licencelésű alkalmazásokat az iOS és a Windows mennyiségi licencelési programjai keretében is lehet felügyelni és telepíteni. Alább találhat további tájékoztatást az alkalmazások és a mennyiségi licencelésű programok Intune-támogatásáról.

-   További tudnivalók [az alkalmazástípusokról](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

-   További tudnivalók [az iOS Volume Purchase Program for Business (VPP) programról](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   További tudnivalók [a Vállalati Windows Áruházról](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)

#### <a name="app-type-requirements"></a>Alkalmazástípusok követelményei

Mivel az alkalmazásokat felhasználók és eszközök számára is lehet telepíteni, célszerű eldönteni, hogy mely alkalmazásokat fogja felügyelni az Intune. A lista összeállításakor igyekezzen megválaszolni a következő kérdéseket:

-   Igényelnek-e az alkalmazások integrációt a felhőszolgáltatásokkal?

-   Minden alkalmazás elérhető lesz a BYOD-felhasználók számára?

-   Milyen telepítési lehetőségek állnak rendelkezésre az alkalmazásokhoz?

-   Kell-e a vállalatnak szolgáltatottszoftver-adatokhoz hozzáférést biztosítania a partnerek számára?

-   Igényelnek-e az alkalmazások internet-hozzáférést a felhasználói eszközökön?

-   Nyilvánosan elérhetők-e az alkalmazások valamilyen alkalmazás-áruházban, vagy egyedi üzletági alkalmazások?


>[!TIP]
> Tekintse át [az Intune által támogatott különféle alkalmazástípusokat](/intune-classic/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

Az alkalmazásvédelmi szabályzatok azt definiálják, hogyan kezelheti egy alkalmazás a vállalati adatokat, így minimalizálják az adatvesztést. Az Intune minden mobilalkalmazás-felügyelettel kompatibilis alkalmazás esetén támogatja az alkalmazásvédelmi szabályzatok használatát. Az alkalmazásvédelmi szabályzat kialakításakor meg kell határoznia, hogy az adott alkalmazásban hogyan korlátozza a vállalati adatok elérését. Célszerű előtt megismerkedni az [alkalmazásvédelmi szabályzatok](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) működésével. Az alábbi példával a meglévő alkalmazások és a szükséges védelem dokumentálását mutatjuk be.

| **Alkalmazás** | **Rendeltetés** | **Platformok** | **Használati eset** | **Alkalmazásvédelmi szabályzat** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Elérhető | iOS | Vállalati – Vezetők | Nem lehet jailbreakelni, fájlok titkosítása |                                                         
| Word | Elérhető | iOS, Android – Samsung Knox, nem Knox, Windows 10 Mobile | Vállalati, BYOD | Nem lehet jailbreakelni, fájlok titkosítása |                                                         

#### <a name="compliance-policies"></a>Megfelelőségi szabályzatok

A megfelelőségi szabályzatok határozzák meg, hogy egy adott eszköz megfelel-e bizonyos követelményeknek. Az Intune megfelelőségi szabályzatokkal határozza meg, hogy az eszközök megfelelőnek minősülnek-e, vagy sem. Ezt követően a megfelelőségi állapot alapján lehet korlátozni a vállalati erőforrások elérését. Ha feltételes hozzáférés szükséges, érdemes [eszközmegfelelőségi szabályzatot](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) tervezni. A követelmények és a használati esetek alapján döntse el, hogy hány eszközmegfelelőségi szabályzatra van szükség, és hogy ezek mely felhasználói csoportokra fognak vonatkozni. Ezenkívül azt is meg kell határozni, hogy mennyi ideig lehet egy eszköz offline állapotban, mielőtt nem megfelelőnek minősülne.

Az alábbi példa egy megfelelőségi szabályzat tervezését szemlélteti:

| **Szabályzat neve** | **Eszközplatform** | **Beállítások** | **Célcsoport** |   
|:---:|:---:|:---:|:---:|
| Megfelelőségi szabályzat | iOS, Android – Samsung Knox, nem Knox, Windows 10 Mobile | PIN-kód szükséges, nem lehet jailbreakelni | Vállalati, BYOD |

#### <a name="conditional-access-policies"></a>Feltételes hozzáférési szabályzatok

A Feltételes hozzáférés csak a megfelelő eszközök számára engedélyezi a vállalati erőforrások elérését. Az Intune a teljes Enterprise Mobility + Security (EMS) csomaggal együttműködve szabályozza a vállalati erőforrások elérését. El kell döntenie, hogy van-e szükség feltételes hozzáférésre, és hogy az mit fog védeni.

-   További tudnivalók [a feltételes hozzáférésről](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)

Online elérés esetén határozza meg, hogy mely platformokra és felhasználói csoportokra fog vonatkozni feltételes hozzáférési szabályzat.

Ezenkívül azt is el kell dönteni, hogy kell-e telepíteni/konfigurálni az Intune szolgáltatás-összekötőt az Exchange Online-hoz vagy a helyszíni Exchange-hez.

További tudnivalók az Intune szolgáltatás-összekötők telepítéséről és konfigurálásáról:

-   [Exchange Online](/intune-classic/deploy-use/intune-service-to-service-exchange-connector)

-   [Helyszíni Exchange](/intune-classic/deploy-use/intune-on-premises-exchange-connector)

Az alábbi példa a feltételes hozzáférési szabályzatok dokumentálását szemlélteti:

| **Szolgáltatás** | **Modern hitelesítési platformok** | **Egyszerű hitelesítés** | **Használati esetek** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | A nem megfelelő eszközök letiltása az Intune által támogatott platformokon | Vállalati, BYOD |
| SharePoint Online | iOS, Android |  | Vállalati, BYOD |

## <a name="next-section"></a>Következő szakasz

A következő szakasz [az Intune implementálási folyamatához](planning-guide-onboarding.md) nyújt útmutatást.

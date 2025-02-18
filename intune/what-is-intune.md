---
title: Mi az a Microsoft Intune?
description: Ismerkedjen meg a Microsoft Intune, a mobileszköz-felügyelet (MDM) és mobilalkalmazás-kezelés (MAM) összetevő, az Enterprise Mobility + Security megoldás segítséget nyújt a vállalati adatok védelme érdekében.
keywords: Mi az az Intune?
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/26/2019
ms.topic: overview
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 511e672193ec609f817c10572c99ac73831c54ae
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460580"
---
# <a name="what-is-microsoft-intune"></a>Mi az a Microsoft Intune?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

A Microsoft Intune egy felhőalapú szolgáltatás, a nagyvállalati mobilitási felügyeleti (EMM) területet, amely segítséget nyújt a munkatársak hatékonyságának a vállalati adatok védelmének megőrzése mellett a rendszer. A Microsoft Intune a többi Azure-szolgáltatáshoz hasonlóan az Azure Portalon érhető el. Az Intune-nal a következőkre nyílik lehetősége:
* Kezelheti a mobileszközöket és számítógépeket, a munkatársak által használt céges adatok elérésére.
* Felügyelheti a munkatársak által használt alkalmazásokat.
* Megóvhatja vállalati adatokat, szabályozva azt, ahogyan a munkatársak elérik és megosztják őket.
* Gondoskodhat arról, hogy az eszközök és az alkalmazások megfeleljenek a vállalat biztonsági követelményeinek.

## <a name="common-business-problems-that-intune-helps-solve"></a>Az Intune segítségével megoldható gyakori üzleti problémák

* [A helyszíni e-mailek és adatok védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Az Office 365 e-mailjeinek és adatainak védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Vállalati tulajdonú telefonok kiadása az informatikai dolgozóknak](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [„Saját eszközök használata” (BYOD) vagy „személyes eszközök” program ajánlása az összes dolgozónak](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Az Office 365 nem felügyelt nyilvános kioszkból történő biztonságos elérésének engedélyezése a dolgozók számára](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Korlátozott használatú megosztott táblagépek kiadása adott feladattal foglalkozó dolgozóknak](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Hogyan működik az Intune?
Intune-nal, a Microsoft Enterprise Mobility + Security (EMS) csomag, amely felügyeli a mobileszközök és alkalmazások összetevője. Szorosan együttműködik más EMS-összetevőkkel, így az identitáskezelés és a hozzáférés-vezérlés terén az Azure Active Directoryval (Azure AD), valamint az adatvédelem terén az Azure Information Protectionnel. Az Office 365-tel együttesen használva lehetővé teszi, hogy a dolgozók minden eszközükön hatékonyan dolgozzanak, emellett gondoskodik a cég adatainak biztonságáról is.

![Kép az Intune architektúrájáról](./media/intunearch_sm.png)

Az Intune architektúráját szemléltető diagramot [nagyobb méretben](./media/intunearchitecture.svg) is megnézheti.

Az Intune eszköz- és alkalmazásfelügyeleti funkcióinak és az EMS adatvédelmének alkalmazási módja a [megoldani kívánt üzleti problémától](#common-business-problems-that-intune-helps-solve) függ. Példa:
* Az eszközfelügyeletet igen hasznosnak fogja találni, ha olyan eszközök készletét alakítja ki, amelyeket közösen használnak egyetlen célra egy kiskereskedelmi bolt több műszakban dolgozó alkalmazottai.
* Az alkalmazásfelügyeletre támaszkodhat, ha engedélyezni kívánja a dolgozóknak a saját eszközeik használatát (BYOD) a céges adatok elérésére.  
* Ha pedig céges telefonokat bocsát az infomunkások rendelkezésére, akkor mindkét technológiát alkalmaznia kell.

## <a name="intune-device-management-explained"></a>Az Intune eszközfelügyeleti funkcióinak ismertetése
Az Intune-alapú eszközfelügyelet a mobil operációs rendszerekben elérhető protokollok vagy API-k használatával működik. Ezzel a szolgáltatással például a következő feladatokat hajthatja végre:
* Az eszközöket regisztrálhatja felügyeletre, hogy az informatikai részleg összeállíthassa a céges szolgáltatásokhoz hozzáférő eszközök nyilvántartását.
* Konfigurálhatja az eszközöket, hogy megfeleljenek a vállalat biztonságra és rendszerállapotra vonatkozó előírásainak.
* Tanúsítványokat és Wi-Fi-/VPN-profilokat biztosíthat a vállalati szolgáltatások eléréséhez.
* Jelentéseket készíthet arról, illetve mérheti, hogy az eszközök mennyire felelnek meg a vállalati előírásoknak.
* Eltávolíthatja a vállalati adatokat a felügyelt eszközökről.  

Vannak, akik szerint **céges adatokhoz való hozzáférés vezérlése** az Eszközfelügyelet egyik funkciója. Mi ezt nem így gondoljuk, mert ez nem olyan funkció, amelyet a mobil operációs rendszer biztosít. Ez inkább az identitásszolgáltató feladata. Esetünkben az identitásszolgáltató az Azure Active Directory (Azure AD), a Microsoft identitás- és hozzáférés-felügyeleti rendszere.  

Az Intune az Azure AD-vel együttműködve a hozzáférés-vezérlési forgatókönyvek széles választékát teszi elérhetővé. Így például Ön megkövetelheti, hogy egy mobileszköz megfeleljen az Intune-ban meghatározott céges előírásoknak, mielőtt hozzáférhetne az olyan céges szolgáltatásokhoz, mint az Exchange. Ehhez hasonlóan megadhat olyan korlátozást, amely csak meghatározott mobilalkalmazásoknak engedélyezi a vállalati szolgáltatások elérését. Előírhatja például, hogy csak az Outlook vagy az Outlook Mobile férhessen hozzá az Exchange Online-hoz.

## <a name="intune-app-management-explained"></a>Az Intune alkalmazásfelügyeleti funkcióinak ismertetése
Alkalmazásfelügyelet alatt a következőket értjük:
* Mobilalkalmazások kiosztása a dolgozók számára
* Az alkalmazás futtatásakor alkalmazandó egységes beállítások konfigurálása
* Előírhatják, hogyan használhatók és oszthatók meg a vállalati adatok a mobilalkalmazásokban.
* Eltávolíthatják a vállalati adatokat a mobilalkalmazásokból.   
* Alkalmazások frissítése
* Nyilvántarthatják a használt mobilalkalmazásokat.
* Nyomon követhetik a mobilalkalmazások használatát.

Tapasztalataink szerint a „mobilalkalmazás-felügyelet” (MAM) kifejezést úgy is szokták használni, hogy csak külön utal a fent felsorolt tevékenységek valamelyikére, vagy a tevékenységek valamilyen kombinációjára. Különösen fontos hogy kombinálja az alkalmazáskonfiguráció fogalmát a céges adatok mobilalkalmazásokon belüli fogalmát. Ez azzal magyarázható, hogy egyes mobilalkalmazások olyan beállításokat is tartalmaznak, amelyekkel az adatvédelmi funkciók konfigurálhatók.

Amikor az alkalmazások konfigurálása és az Intune összefüggésében használjuk a fogalmat, konkrétan olyan technológiákra gondolunk, mint [a felügyelt alkalmazások konfigurálása az iOS-ben](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Ha az Intune-t használja az EMS más szolgáltatásaival, akkor a mobil operációs rendszer és a mobilalkalmazások saját alkalmazáskonfigurációs lehetőségei által nyújtottnál magasabb szintű mobilalkalmazás-védelmet biztosíthat a szervezet számára. Az EMS használatával felügyelt alkalmazás hozzáfér a mobilalkalmazások és az adatvédelmi funkciók szélesebb köréhez férhetnek, amely tartalmazza:

* [Egyszeri bejelentkezés](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Többtényezős hitelesítés](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Alkalmazás feltételes hozzáférése – hozzáférés engedélyezése, ha a mobilalkalmazás vállalati adatokat tartalmaz](app-based-conditional-access-intune.md)
* [A vállalati adatok és a személyes adatok elkülönítése alkalmazáson belül](app-protection-policy.md)
* [Alkalmazásvédelmi szabályzat (PIN-kód, titkosítás, mentés másként, vágólap stb.)](app-protection-policies.md)
* [Vállalati adatok törlése a mobilalkalmazásokból](apps-selective-wipe.md)
* [Tartalomvédelem támogatása](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Az alkalmazásfelügyelet adatvédelmi szintjeit bemutató ábra](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>Az Intune alkalmazásbiztonsági funkciói
Az alkalmazások biztonságáról való gondoskodás az alkalmazásfelügyelet része, és az Intune-ban a mobilalkalmazások biztonsága alatt a következőket értjük:
* A személyes adatok elkülönítése a vállalat informatikai rendszerétől
* A felhasználók által a vállalati adatokkal végrehajtható műveletek (például másolás, kivágás és beillesztés, mentés és megtekintés) korlátozása
* A vállalati adatok eltávolítása a mobilalkalmazásokból (más elnevezéssel: szelektív törlés vagy vállalati törlés)

Egyik módja az Intune kínál keresztül van mobilalkalmazás-védelmet a **alkalmazásvédelmi szabályzat** funkció. Az alkalmazásvédelmi szabályzat az Azure AD identitásvédelmi szolgáltatását használja a vállalati adatok és a személyes adatok elkülönítéséhez. Vállalati hitelesítő adatok használatával elérhető adatok további vállalati szintű védelmet kapnak.

Például amikor egy felhasználó bejelentkezik az eszközt a vállalati hitelesítő adataikkal, a céges identitása lehetővé teszi számukra, hogy a személyes identitásával megtagadva hozzá adatokhoz. A céges adatok használata során az alkalmazásvédelmi szabályzatok határozzák meg, hogy az adatok miként menthetők, illetve oszthatók meg. Ezek a védelmi funkciók sem lépnek érvénybe, amikor a felhasználó bejelentkezik a személyes identitásával eszköz elért adatokat. Ezzel a módszerrel informatikai vállalati adatok szabályozzák, amíg tart fenn és biztonságának a végfelhasználó személyes adataik felett.

## <a name="emm-with-and-without-device-enrollment"></a>Nagyvállalati mobileszköz-felügyelet az eszközök regisztrálásával és anélkül
A legtöbb nagyvállalati mobilitási felügyeleti megoldás támogatja az alapvető mobileszköz- és mobilalkalmazás-felügyeleti technológiákat. Ezek általában a cég mobileszköz-felügyeleti (MDM-) megoldásában regisztrált eszközökhöz kapcsolódnak. Az Intune támogatja ezeket a forgatókönyveket, és emellett számos „regisztráció nélküli” forgatókönyvet is.  

A szervezetek különböző mértékben alkalmazzák a „regisztráció nélküli” forgatókönyveket. Egyes szervezetek egységesen ezeket alkalmazzák. Más szervezetek a kiegészítő eszközökhöz, például a személyes táblagépekhez használják. Megint más szervezetek egyáltalán nem támogatják. Még akkor is, ez utóbbi esetben előírják minden munkatárs számára az eszközöknek a mobileszköz-felügyeleti, általában támogatják a "regisztráció nélküli" forgatókönyveket alvállalkozók, a szállítók és a meghatározott mentességgel rendelkező egyéb eszközök számára.

Az Intune „regisztráció nélküli” technológiáját akár még a regisztrált eszközökhöz is használhatja. Az MDM-ben regisztrált eszközöknek például lehet a mobil operációs rendszer által biztosított megnyitásvédelmük. "Megnyitás a következőben" védelmi funkciója biztosítja, hogy a dokumentum megnyitása egy alkalmazásból, például az Outlook, egy másik alkalmazásba, például a Word, kivéve, ha mindkét alkalmazásnak ugyanabban az MDM-szolgáltató kezeli az Apple IOS-es. Ezenkívül informatikai érvényesek az alkalmazásvédelmi szabályzatot az ellenőrzési mentse az EMS által kezelt mobilalkalmazások-szerint, vagy a multi-factor Authentication hitelesítés.

Függetlenül attól, hogy a szervezet milyen helyzetben van a regisztrált és a nem regisztrált mobileszközök és -alkalmazások terén, az Intune az EMS részeként rendelkezik azokkal az eszközökkel, amelyekkel növelhető a munkatársak hatékonysága a vállalati adatok védelmének fenntartásával párhuzamosan.

## <a name="microsoft-intune-in-the-azure-portal"></a>A Microsoft Intune az Azure Portalon

A Microsoft Intune szolgáltatást az [Azure Portalon](https://portal.azure.com) találhatja meg.

A Microsoft Intune Azure Portalbeli használatának néhány fontos pontja:

- Integrált konzol az Enterprise Mobility + Security (EMS) összes biztonsági összetevőjéhez
- Webes szabványokra épülő HTML-alapú konzol
- Microsoft Graph API-támogatás számos művelet automatizálásához
- Azure Active Directory- (AD-)csoportok az Azure-os alkalmazások közötti kompatibilitás érdekében
- A legtöbb modern böngésző támogatása

A [Bevezetés az Intune használatába az Azure Portalon](get-started-azure.md) című cikkben segítséget kaphat a portál használatának beállításához.

> [!NOTE]
> Ha a Microsoft Intune egy korábbi verzióját már használta, akkor az alábbi információt hasznosnak fogja találni:
> * A [Hová kerültek a szolgáltatások az Azure-ban?](ui-changes.md) hivatkozással megjelenítheti az adott, az Azure-ra való átálláskor módosított munkafolyamatokat és felhasználóifelület-elemeket.
> * A [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md) ismerteti a csoportok kezelésében az Azure Active Directory biztonsági csoportokra való áttérés hatásait.

### <a name="before-you-start"></a>Előkészületek

Az Azure Portalon az Intune használatához Intune-os rendszergazdai és bérlői fiókkal kell rendelkeznie. Ha még nincs fiókja, [regisztráljon](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

### <a name="supported-web-browsers-for-the-azure-portal"></a>Támogatott webböngészők az Azure portálon

Az Azure Portal működik a legtöbb modern PC-n, Mac-en és táblagépen. Mobiltelefonok használata nem támogatott.
Jelenleg a következő böngészők támogatottak:

- Microsoft Edge (legújabb verzió)
- Microsoft Internet Explorer 11
- Safari (csak Mac, legújabb verzió)
- Chrome (legújabb verzió)
- Firefox (legújabb verzió)

A támogatott böngészőkről az [Azure Portalon](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) találja a legfrissebb információt.

## <a name="next-steps"></a>További lépések
* Tájékozódjon az [Intune gyakori használati módjairól](common-scenarios.md).
* Ismerkedjen meg a termékkel egy [30 napos Intune-próbaverzió](free-trial-sign-up.md) révén.
* Mélyedjen el az Intune [műszaki követelményeiben és képességeiben](supported-devices-browsers.md).

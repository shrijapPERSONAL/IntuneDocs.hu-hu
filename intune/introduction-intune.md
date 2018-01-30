---
title: Mi az a Microsoft Intune?
description: "Ismerkedjen meg az Intune-nal, az Enterprise Mobility + Security megoldás mobileszköz-felügyeleti (MDM-) és mobilalkalmazás-felügyeleti (MAM-) összetevőjével, amely segítségét nyújt a céges adatok védelméhez."
keywords: Mi az az Intune?
author: Lindavr
ms.author: lindavr
manager: dougeby
ms.date: 07/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 64fd5e506d0c2fdfa5d99e6ac96d6e12c886fcbe
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-intune"></a>Mi az az Intune?

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Az Intune egy felhőalapú nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltatás, amely segítséget nyújt a munkatársak hatékonyságának fenntartásához a céges adatok védelmének megőrzése mellett. Az Intune-nal a következőkre nyílik lehetősége:
* Felügyelheti a munkatársak által a vállalati adatok elérésére használt mobileszközöket.
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
Az Intune az Enterprise Mobility + Security (EMS) megoldás mobileszköz- és mobilalkalmazás-felügyeletért felelős összetevője. Szorosan együttműködik más EMS-összetevőkkel, így az identitáskezelés és a hozzáférés-vezérlés terén az Azure Active Directoryval (Azure AD), valamint az adatvédelem terén az Azure Information Protectionnel. Az Office 365-tel együttesen használva lehetővé teszi, hogy a dolgozók minden eszközükön hatékonyan dolgozzanak, emellett gondoskodik a cég adatainak biztonságáról is.

![Kép az Intune architektúrájáról](./media/intunearch_sm.png)

Az Intune architektúráját szemléltető diagramot [nagyobb méretben](./media/intunearchitecture.svg) is megnézheti.

Az Intune eszköz- és alkalmazásfelügyeleti funkcióinak és az EMS adatvédelmének alkalmazási módja a [megoldani kívánt üzleti problémától](#common-business-problems-that-intune-helps-solve) függ. Például:
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

Vannak, akik szerint a **céges adatokhoz való hozzáférés vezérlése** az eszközfelügyelet egyik funkciója. Mi ezt nem így gondoljuk, mert ez nem olyan funkció, amelyet a mobil operációs rendszer biztosít. Ez inkább az identitásszolgáltató feladata. Esetünkben az identitásszolgáltató az Azure Active Directory (Azure AD), a Microsoft identitás- és hozzáférés-felügyeleti rendszere.  

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

Tapasztalataink szerint a „mobilalkalmazás-felügyelet” (MAM) kifejezést úgy is szokták használni, hogy csak külön utal a fent felsorolt tevékenységek valamelyikére, vagy a tevékenységek valamilyen kombinációjára. Gyakran előfordul például, hogy a felhasználók összevonják az alkalmazások konfigurálásának fogalmát a céges adatok mobilalkalmazásokon belüli védelmével. Ez azzal magyarázható, hogy egyes mobilalkalmazások olyan beállításokat is tartalmaznak, amelyekkel az adatvédelmi funkciók konfigurálhatók.

Amikor az alkalmazások konfigurálása és az Intune összefüggésében használjuk a fogalmat, konkrétan olyan technológiákra gondolunk, mint [a felügyelt alkalmazások konfigurálása az iOS-ben](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Ha az Intune-t használja az EMS más szolgáltatásaival, akkor a mobil operációs rendszer és a mobilalkalmazások saját alkalmazáskonfigurációs lehetőségei által nyújtottnál magasabb szintű mobilalkalmazás-védelmet biztosíthat a szervezet számára. Az EMS használatával felügyelt alkalmazások a mobilalkalmazások és az adatvédelmi funkciók szélesebb köréhez férhetnek hozzá. Ide tartoznak például a következők:

* [Egyszeri bejelentkezés](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Többtényezős hitelesítés](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
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

Az Intune mobilalkalmazás-védelmének egy formája az **alkalmazásvédelmi szabályzat** funkciója. Az alkalmazásvédelmi szabályzat az Azure AD identitásvédelmi szolgáltatását használja a vállalati adatok és a személyes adatok elkülönítéséhez. A vállalati hitelesítő adatok használatával elérhető adatok további vállalati szintű védelmet kapnak.

Amikor például egy felhasználó bejelentkezik az eszközén a céges hitelesítő adataival, a céges identitása lehetővé teszi számára az olyan adatok elérését, amelyekhez a személyes identitásával nem férhet hozzá. A céges adatok használata során az alkalmazásvédelmi szabályzatok határozzák meg, hogy az adatok miként menthetők, illetve oszthatók meg. Ezek a védelmi funkciók nem lesznek alkalmazva azokra az adatokra, amelyekhez a felhasználó akkor fér hozzá, amikor a személyes identitásával jelentkezik be az eszközre. Ezzel a módszerrel a vállalati adatok az informatikai részleg felügyelete alatt állnak, míg a személyes adatok védelmének és biztonságának fenntartása a végfelhasználó feladata.

## <a name="emm-with-and-without-device-enrollment"></a>Nagyvállalati mobileszköz-felügyelet az eszközök regisztrálásával és anélkül
A legtöbb nagyvállalati mobilitási felügyeleti megoldás támogatja az alapvető mobileszköz- és mobilalkalmazás-felügyeleti technológiákat. Ezek általában a cég mobileszköz-felügyeleti (MDM-) megoldásában regisztrált eszközökhöz kapcsolódnak. Az Intune támogatja ezeket a forgatókönyveket, és emellett számos „regisztráció nélküli” forgatókönyvet is.  

A szervezetek különböző mértékben alkalmazzák a „regisztráció nélküli” forgatókönyveket. Egyes szervezetek egységesen ezeket alkalmazzák. Más szervezetek a kiegészítő eszközökhöz, például a személyes táblagépekhez használják. Megint más szervezetek egyáltalán nem támogatják. Ebben az utolsó esetben is előfordul azonban „regisztráció nélküli” forgatókönyv, főleg az olyan cégeknél, amelyek előírják minden munkatárs számára az eszközöknek a mobileszköz-felügyeleti megoldásban történő regisztrálását. Ezek a cégek jellemzően az alvállalkozók, a szállítók és a meghatározott mentességgel rendelkező egyéb eszközök esetében alkalmaznak ilyen forgatókönyvet.

Az Intune „regisztráció nélküli” technológiáját akár még a regisztrált eszközökhöz is használhatja. Az MDM-ben regisztrált eszközöknek például lehet a mobil operációs rendszer által biztosított megnyitásvédelmük. A megnyitásvédelem az iOS szolgáltatása, amely biztosítja, hogy egy alkalmazásból, például az Outlookból származó dokumentumot csak akkor lehessen másik alkalmazással, például a Worddel megnyitni, ha mindkét alkalmazást az MDM-szolgáltató felügyeli. Ezenkívül az informatikai részleg előírhatja az alkalmazásvédelmi szabályzat használatát az EMS által felügyelt mobilalkalmazásokhoz azért, hogy szabályozza a „mentés másként” funkciót, vagy kötelezővé tegye a többtényezős hitelesítést.

Függetlenül attól, hogy a szervezet milyen helyzetben van a regisztrált és a nem regisztrált mobileszközök és -alkalmazások terén, az Intune az EMS részeként rendelkezik azokkal az eszközökkel, amelyekkel növelhető a munkatársak hatékonysága a vállalati adatok védelmének fenntartásával párhuzamosan.



### <a name="next-steps"></a>További lépések
* Tájékozódjon az [Intune gyakori használati módjairól](common-scenarios.md).
* Ismerkedjen meg a termékkel egy [30 napos Intune-próbaverzió](free-trial-sign-up.md) révén.
* Mélyedjen el az Intune [műszaki követelményeiben és képességeiben](supported-devices-browsers.md).

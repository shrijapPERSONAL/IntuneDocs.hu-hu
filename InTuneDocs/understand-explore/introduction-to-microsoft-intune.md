---
title: Mi az a Microsoft Intune? | Microsoft Docs
description: "Ismerkedjen meg az Intune-nal, az Enterprise Mobility + Security megoldás mobileszköz-felügyeleti összetevőjével, amely segítségét nyújt a vállalati adatok védelméhez."
keywords: Mi az az Intune?
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 2552f84dc38c4453851167cd1570143c7a9820c2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/04/2017


---

# <a name="what-is-intune"></a>Mi az az Intune?

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune egy felhőalapú nagyvállalati mobileszköz-felügyeleti (EMM) szolgáltatás, amely segítséget nyújt a munkatársak hatékonyságának fenntartásához a vállalati adatok védelmének megőrzése mellett. Az Intune-nal a következőkre nyílik lehetősége:
* Felügyelheti a munkatársak által a vállalati adatok elérésére használt mobileszközöket.
* Felügyelheti a munkatársak által használt alkalmazásokat.
* Megóvhatja vállalati adatokat, szabályozva azt, ahogyan a munkatársak elérik és megosztják őket.
* Gondoskodhat arról, hogy az eszközök és az alkalmazások megfeleljenek a vállalat biztonsági követelményeinek.

Az Intune szorosan együttműködik az identitáskezelés és a hozzáférés-vezérlés terén az Azure Active Directoryval (Azure AD), valamint az adatvédelem terén az Azure Information Protectionnel.

Az Office 365 és az EMS együttesen lehetővé teszi, hogy a dolgozók minden eszközükön hatékonyan dolgozzanak, emellett óvja a szervezet adatait is. Az Office 365 és az EMS a nagyvállalati mobilitás teljes, integrált csomagját kínálja, amelynek részét alkotják az irodai alkalmazások, az identitáskezelés, a hozzáférés-vezérlés, a felügyelet és az adatvédelem. Hatékony módot biztosít egy mobilitási megoldás üzembe helyezéséhez és üzemeltetéséhez a szervezetében.

## <a name="how-does-intune-work"></a>Hogyan működik az Intune?
Az Intune mobileszköz-felügyeletet (MDM) és mobilalkalmazás-felügyeletet (MAM) biztosít. Az Intune MDM és MAM szolgáltatása alkalmazható az EMS adatvédelmi és megfelelőségi forgatókönyveihez is.  

Az Intune MDM és MAM szolgáltatásának és az EMS adatvédelmének alkalmazási módja a [megoldani kívánt üzleti problémától](#common-business-problems-that-intune-helps-solve) függ. Példa:
* A mobileszköz-felügyeletet igen hasznosnak fogja találni, ha olyan eszközök készletét alakítja ki, amelyeket közösen használnak egyetlen célra egy kiskereskedelmi bolt több műszakban dolgozó alkalmazottai.
* A mobilalkalmazás-felügyeletre támaszkodhat, ha engedélyezni kívánja a dolgozóknak a saját eszközeik használatát (BYOD) a vállalati adatok elérésére.  
* Ha pedig vállalati telefonokat bocsát az infomunkások rendelkezésére, akkor mindkét technológiát alkalmaznia kell.

## <a name="intune-mobile-device-management-mdm-explained"></a>Az Intune mobileszköz-felügyeletének (MDM) ismertetése
Az MDM a mobil operációs rendszerekben elérhető protokollok vagy API-k használatával működik. Ezzel a szolgáltatással például a következő feladatokat hajthatja végre:
* Az eszközöket regisztrálhatja felügyeletre, hogy az informatikai részleg összeállíthassa a vállalati szolgáltatásokhoz hozzáférő eszközök nyilvántartását.
* Konfigurálhatja az eszközöket, hogy megfeleljenek a vállalat biztonságra és rendszerállapotra vonatkozó előírásainak.
* Tanúsítványokat és Wi-Fi-/VPN-profilokat biztosíthat a vállalati szolgáltatások eléréséhez.
* Jelentéseket készíthet arról, illetve mérheti, hogy az eszközök mennyire felelnek meg a vállalati előírásoknak.
* Eltávolíthatja a vállalati adatokat a felügyelt eszközökről.  

Vannak, akik szerint a **vállalati adatok hozzáférés-vezérlése** az MDM egyik funkciója. Mi ezt nem így gondoljuk, mert ez nem olyan funkció, amelyet a mobil operációs rendszer biztosít. Ez inkább az identitásszolgáltató feladata. Esetünkben az identitásszolgáltató az Azure Active Directory (Azure AD), a Microsoft identitás- és hozzáférés-felügyeleti rendszere.  

Az Intune az Azure AD-vel együttműködve a hozzáférés-vezérlési forgatókönyvek széles választékát teszi elérhetővé. Így például Ön megkövetelheti, hogy egy mobileszköz megfeleljen a vállalati előírásoknak az Intune-ban megadottak szerint, mielőtt hozzáférne az olyan vállalati szolgáltatásokhoz, mint az Exchange. Ehhez hasonlóan megadhat olyan korlátozást, amely csak meghatározott mobilalkalmazásoknak engedélyezi a vállalati szolgáltatások elérését. Előírhatja például, hogy csak az Outlook vagy az Outlook Mobile férhessen hozzá az Exchange Online-hoz.

## <a name="intune-mobile-app-management-mam-explained"></a>Az Intune mobilalkalmazás-felügyeletének (MAM) ismertetése
Az MAM kapcsán azokról a dolgokról beszélünk, amelyekre az informatikusoknak lehetőségük nyílik a megoldásaink felhasználásával. Például:
* Közzétehetik a mobilalkalmazásokat a dolgozók számára.
* Konfigurálhatják az alkalmazásokat.
* Előírhatják, hogyan használhatók és oszthatók meg a vállalati adatok a mobilalkalmazásokban.
* Eltávolíthatják a vállalati adatokat a mobilalkalmazásokból.   
* Frissíthetik a mobilalkalmazásokat.
* Nyilvántarthatják a használt mobilalkalmazásokat.
* Nyomon követhetik a mobilalkalmazások használatát.

Tapasztalataink szerint a „mobilalkalmazás-felügyelet” kifejezést úgy is szokták használni, hogy csak külön utal valamelyik felsorolt tevékenységre, vagy a tevékenységek valamilyen kombinációjára. Gyakran előfordul például, hogy a felhasználók összevonják az alkalmazások konfigurálásának fogalmát (vagyis az olyan technológiák használatát, mint a [felügyelt alkalmazáskonfiguráció az iOS rendszerben](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) a vállalati adatok mobilalkalmazásokon belüli védelmével. Ez azzal magyarázható, hogy egyes mobilalkalmazások olyan beállításokat is tartalmaznak, amelyekkel az adatvédelmi funkciók konfigurálhatók.

Ez az operációs rendszer adatvédelmi szolgáltatásaival (például az olyan MDM-funkciókkal, mint a Windows Információvédelem a Windows 10-ben) együtt elég nagy mértékű védelmet biztosít a mobileszközökön található adatok számára.

Ha az Intune-t használja az EMS más szolgáltatásaival, akkor a mobil operációs rendszer és a mobilalkalmazások saját alkalmazáskonfigurációs lehetőségei által nyújtottnál magasabb szintű mobilalkalmazás-védelmet biztosíthat a szervezet számára. Az EMS használatával felügyelt alkalmazások a mobilalkalmazások és az adatvédelmi funkciók szélesebb köréhez férhetnek hozzá. Ide tartoznak például a következők:

* [Egyszeri bejelentkezés](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*    [Többtényezős hitelesítés](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
* [Alkalmazás feltételes hozzáférése (hozzáférés engedélyezése, ha a mobilalkalmazás vállalati adatokat tartalmaz)](https://docs.microsoft.com/intune/deploy-use/allow-policy-managed-apps-access-to-o365)
* [A vállalati adatok és a személyes adatok elkülönítése alkalmazáson belül](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Alkalmazásvédelmi szabályzat (PIN-kód, titkosítás, mentés másként, vágólap stb.)](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Vállalati adatok törlése a mobilalkalmazásokból](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Tartalomvédelem támogatása](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Az alkalmazásfelügyelet adatvédelmi szintjeit bemutató ábra](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Az Intune mobilalkalmazás-védelme
Az alkalmazások védelmének biztosítása az MAM része, és az Intune-ban a mobilalkalmazások védelme alatt a következőket értjük:
* A személyes adatok elkülönítése a vállalat informatikai rendszerétől
* A felhasználók által a vállalati adatokkal végrehajtható műveletek (például másolás, kivágás és beillesztés, mentés és megtekintés) korlátozása
* A vállalati adatok eltávolítása a mobilalkalmazásokból (más elnevezéssel: szelektív törlés vagy vállalati törlés)

Az Intune mobilalkalmazás-védelmének egy formája az **alkalmazásvédelmi szabályzat** funkciója. Az alkalmazásvédelmi szabályzat az Azure AD identitásvédelmi szolgáltatását használja a vállalati adatok és a személyes adatok elkülönítéséhez. A vállalati hitelesítő adatok használatával elérhető adatok további vállalati szintű védelmet kapnak.

Amikor egy felhasználó bejelentkezik az eszközén a vállalati hitelesítő adataival, a vállalati identitása engedélyezi számára az olyan adatok elérését, amelyekhez a személyes identitásával nem férhet hozzá. A vállalati adatok használata közben az Intune és az EMS más technológiái meghatározzák, hogy ezek az adatok hogyan menthetők és hogyan oszthatók meg. Ezek a védelmi funkciók nem lesznek alkalmazva azokra az adatokra, amelyekhez a felhasználó akkor fér hozzá, amikor a személyes identitásával jelentkezik be az eszközre. Ezzel a módszerrel a vállalati adatok az informatikai részleg felügyelete alatt állnak, míg a személyes adatok védelmének és biztonságának fenntartása a végfelhasználó feladata.

## <a name="emm-with-and-without-device-enrollment"></a>Nagyvállalati mobileszköz-felügyelet az eszközök regisztrálásával és anélkül
A legtöbb nagyvállalati mobilitási felügyeleti megoldás támogatja az alapvető mobileszköz- és mobilalkalmazás-felügyeleti technológiákat. Ezek általában a szervezet MDM-megoldásában regisztrált eszközökhöz kapcsolódnak. Az Intune támogatja ezeket a forgatókönyveket, és emellett számos „regisztráció nélküli” forgatókönyvet is.  

A szervezetek különböző mértékben alkalmazzák a „regisztráció nélküli” forgatókönyveket. Egyes szervezetek egységesen ezeket alkalmazzák. Más szervezetek a kiegészítő eszközökhöz, például a személyes táblagépekhez használják. Megint más szervezetek egyáltalán nem támogatják. Ebben az utolsó esetben is előfordul azonban „regisztráció nélküli” forgatókönyv, főleg az olyan szervezeteknél, amelyek előírják minden munkatárs számára az eszközöknek a mobileszköz-felügyeleti megoldásban történő regisztrálását. Ezek a szervezetek jellemzően az alvállalkozók, a szállítók és a meghatározott mentességgel rendelkező egyéb eszközök esetében alkalmaznak ilyen forgatókönyvet.

Az Intune „regisztráció nélküli” technológiáját akár még a regisztrált eszközökhöz is használhatja. Az MDM-ben regisztrált eszközöknek például lehet a mobil operációs rendszer által biztosított „megnyitás a következővel” típusú védelmük. (A megnyitás-védelem az iOS szolgáltatása, amely biztosítja, hogy egy alkalmazásból, például az Outlookból származó dokumentumot csak akkor lehessen másik alkalmazással, például Worddel megnyitni, ha mindkét alkalmazást az MDM-szolgáltató felügyeli.) Ezenkívül az informatikai részleg előírhatja az alkalmazásvédelmi szabályzat használatát az EMS által felügyelt mobilalkalmazásokhoz azért, hogy szabályozza a „mentés másként” funkciót, vagy kötelezővé tegye a többtényezős hitelesítést.

Függetlenül attól, hogy a szervezet milyen helyzetben van a regisztrált és a nem regisztrált mobileszközök és -alkalmazások terén, az Intune az EMS részeként rendelkezik azokkal az eszközökkel, amelyekkel növelhető a munkatársak hatékonysága a vállalati adatok védelmének fenntartásával párhuzamosan.

## <a name="common-business-problems-that-intune-helps-solve"></a>Az Intune segítségével megoldható gyakori üzleti problémák
Az alábbi listában szereplő üzleti problémák hivatkozására kattintva kaphat részletesebb tájékoztatást a megoldásainkról. Csak az utolsó elem igényli a MDM-beli regisztrációt a megoldás részeként:

* [A helyszíni e-mailek és adatok védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-ways-to-use-intune.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Az Office 365 e-mailjeinek és adatainak védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez](common-ways-to-use-intune.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Vállalati tulajdonú telefonok kiadása az informatikai dolgozóknak](common-ways-to-use-intune.md#issue-corporate-owned-phones-to-your-information-workers)
* [„Saját eszközök használata” (BYOD) vagy „személyes eszközök” program ajánlása az összes dolgozónak](common-ways-to-use-intune.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Az Office 365 nem felügyelt nyilvános kioszkból történő biztonságos elérésének engedélyezése a dolgozók számára](common-ways-to-use-intune.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Korlátozott használatú megosztott táblagépek kiadása adott feladattal foglalkozó dolgozóknak](common-ways-to-use-intune.md#issue-limited-use-shared-tablets-to-your-task-workers)

### <a name="next-steps"></a>További lépések
* Tájékozódjon az [Intune gyakori használati módjairól](common-ways-to-use-intune.md).
* Ismerkedjen meg a termékkel egy [30 napos Intune-próbaverzió](get-started-with-a-30-day-trial-of-microsoft-intune.md) révén.
* Mélyedjen el az Intune [műszaki követelményeiben és képességeiben](/intune/get-started/what-to-know-before-you-start-microsoft-intune).


---
title: "Az iOS-es MAM-szabályzat beállításai | Microsoft Docs"
description: "Ez a témakör bemutatja a mobilalkalmazás-felügyeleti szabályzat beállításait iOS-eszközökhöz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 03f53e6ec9f934eb40415434a60213bc839f6afe
ms.lasthandoff: 04/14/2017


---

#  <a name="ios-mobile-app-protection-policy-settings"></a>iOS-es mobilalkalmazás-védelmi szabályzat-beállításai

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A jelen témakörben ismertetett szabályzatbeállításokat az Azure Portal **Az összes beállítás** paneljén lehet [konfigurálni](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) az alkalmazásvédelmi szabályzatokhoz.

A szabályzatbeállításoknak két kategóriájuk van: adatáthelyezési beállítások és hozzáférési beállítások. Ebben a témakörben a _**szabályzattal felügyelt**_ alkalmazások kifejezés olyan alkalmazásokra utal, amelyekhez alkalmazásvédelmi szabályzatot állítottak be.

##  <a name="data-relocation-settings"></a>Adatáthelyezési beállítások

| Beállítás | Használat | Alapértelmezett érték |
|------|------|------|
| **Tunes- és iCloud-alapú biztonsági mentések tiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás a munkahelyi vagy iskolai adatokról biztonsági mentést készítsen az iTunesban és az iCloudban. Ha a **Nem** gombot választja, a rendszer engedélyezi, hogy az alkalmazás a munkahelyi vagy iskolai adatokról biztonsági mentést készítsen az iTunesban és az iCloudban.| Igen |
| **Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások kaphatnak adatokat ettől az alkalmazástól: <ul><li> **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak más, szabályzattal felügyelt alkalmazásokba engedélyezett.</li> <li>**Minden alkalmazás**: Az adatátvitel engedélyezett minden alkalmazásnál. </li> <li>**Nincs**: Minden alkalmazásba tiltott az adatátvitel., ideértve a szabályzat által felügyelt többi alkalmazást is.</li></ul> A **Szabályzat által felügyelt alkalmazások** vagy a **Nincs** beállítás alkalmazása esetén le lesz tiltva az iOS 9 rendszer azon funkciója, amely lehetővé teszi, hogy a Spotlight-kereső adatokat kereshessen az alkalmazásokon belül. <br><br> Vannak kivételt képező alkalmazások és szolgáltatások, amelyek felé az Intune engedélyezheti az adatátvitelt. Az alkalmazások és a szolgáltatások teljes listája az [Adatátviteli kivételek](#Data-transfer-exemptions) című szakaszban olvasható. | Minden alkalmazás |
| **Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások küldhetnek adatokat ebbe az alkalmazásba: <ul><li>**Szabályzattal felügyelt alkalmazások**: Az átvitel csak más, szabályzattal felügyelt alkalmazásokból engedélyezett.</li><li>**Minden alkalmazás**: Az adatátvitel minden alkalmazásból engedélyezett.</li><li>**Nincs**: Minden alkalmazásból tiltott az adatátvitel, ideértve a szabályzat által felügyelt többi alkalmazást is.</li></ul> Vannak kivételt képező alkalmazások és szolgáltatások, amelyek felől az Intune engedélyezheti az adatátvitelt. Az alkalmazások és a szolgáltatások teljes listája az [Adatátviteli kivételek](#Data-transfer-exemptions) című szakaszban olvasható.  | Minden alkalmazás |
| **A „Mentés másként” művelet letiltása** | Az **Igen** gombot választva letilthatja a Mentés másként lehetőség használatát ebben az alkalmazásban. A **Nem** gombot választva engedélyezheti a Mentés másként funkció használatát. | Nem |
| **Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal** | Itt adhatja meg, hogy mikor használhatók a kivágási, másolási és beillesztési műveletek az alkalmazásban. A következő lehetőségek közül választhat: <ul><li>**Letiltva**:  A kivágási, másolási és beillesztési műveletek letiltása az alkalmazás és más alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások**: A kivágási, másolási és beillesztési műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**: A kivágási és másolási műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között. Adatok beillesztésének engedélyezése bármely alkalmazásból ebbe az alkalmazásba.</li><li>**Bármely alkalmazás**: Az alkalmazások közötti kivágási, másolási és beillesztési műveletek nem korlátozottak. | Bármely alkalmazás |
|**A Managed Browser (felügyelt böngésző) alkalmazásban megjelenítendő webes tartalom korlátozása** | Ha az **Igen** gombot választja, a rendszer kényszeríti az alkalmazásban lévő webes hivatkozások Managed Browser alkalmazásban való megnyitását. <br><br> Az Intune-ban nem regisztrált eszközök esetében a szabályzat által felügyelt alkalmazások webhivatkozásai kizárólag a Managed Browser alkalmazásban nyílnak meg. <br><br> Ha az Intune-t használja az eszközök kezeléséhez, olvassa el [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](manage-internet-access-using-managed-browser-policies.md) című témakört. | Nem |
| **Alkalmazásadatok titkosítása** | A szabályzat által felügyelt alkalmazások esetén a rendszer az iOS által biztosított eszközszintű titkosítási séma használatával titkosítja az inaktív adatokat. Ha PIN-kódra van szükség, az adattitkosítás az alkalmazásvédelmi szabályzatban megadott beállítások szerint történik. <br><br> Nyissa meg a hivatalos Apple-dokumentációt, amelyet [itt](https://support.apple.com/HT202739) talál, és tekintse meg, hogy az iOS mely titkosítási moduljai a FIPS 140-2 szerint tanúsítottak, és mely moduloknak van a FIPS 140-2 szerinti tanúsítása függőben. <br><br> Itt adhatja meg hogy mikor titkosítsa az alkalmazásban lévő munkahelyi vagy iskolai adatokat a rendszer. A következő lehetőségek közül választhat: <ul><li>**Ha az eszköz zárolva van:** A rendszer a szabályzathoz társított összes alkalmazásadatot titkosítja az eszköz zárolt állapotában.</li><li>**Amikor az eszköz zárolva van és vannak rajta megnyitott fájlok**: A rendszer a szabályzathoz társított összes alkalmazásadatot titkosítja az eszköz zárolt állapotában, kivéve az alkalmazásban éppen megnyitott fájlok adatait.</li><li>**Az eszköz újraindítása után**: A rendszer az eszköz újraindításakor a szabályzathoz társított összes alkalmazásadatot titkosítja, amíg fel nem oldják a zárolást az eszközön.</li><li>**Eszközbeállítások használata:** A rendszer az eszköz alapértelmezett beállításai alapján titkosítja az alkalmazásadatokat. Ha engedélyezi ezt a beállítást, a felhasználónak PIN-kódot kell beállítania és használnia az eszköz eléréséhez.  Ha nincs beállítva PIN-kód, nem indulnak el az alkalmazások, és a felhasználót egy üzenet értesíti arról, hogy a munkahely követelményei szerint PIN-kód beállítása szükséges az adott alkalmazás eléréséhez. </li></ul> | Amikor az eszköz zárolva van |
| **Névjegy-szinkronizálás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. Ha a **Nem** gombot választja, a rendszer engedélyezi, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. <br><br>Ha szelektív törléssel távolítja el a munkahelyi vagy iskolai adatokat az alkalmazásból, akkor a közvetlenül az alkalmazásból a natív névjegykezelő alkalmazásba szinkronizált névjegyek törlődnek. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes. | Nem |
| **Nyomtatás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás munkahelyi vagy iskolai adatokat nyomtasson. | Nem |


> [!NOTE]
> Az iOS-eszközökön egyik adatáthelyezési beállítás sem szabályozza az Apple által felügyelt Megnyitás a következőben funkciót. Az Apple-eszközök Megnyitás a következőben funkciójának felügyeletéről az [iOS-alkalmazások közti adatátvitel felügyelete a Microsoft Intune-nal](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) című cikkben olvashat.

## <a name="data-transfer-exemptions"></a>Adatátviteli kivételek

Egyes alkalmazások és platformszolgáltatások kivételt képeznek, és az Intune alkalmazásvédelmi szabályzata bizonyos helyzetekben engedélyezheti számukra, hogy adatokat küldjenek és fogadjanak. Ez a lista idővel változhat. Azok a szolgáltatások és alkalmazások szerepelnek rajta, amelyek megítélésünk szerint biztonságosan segítik a hatékony munkát.

| Alkalmazás/szolgáltatás neve(i) | Leírás |
| ---- | --- |
|tel; telprompt | Natív telefonalkalmazás |
| skype | Skype |
| app-settings | Eszközbeállítások |
| itms; itmss; itms-apps; itms-appss; itms-services | Alkalmazásáruház |
| calshow | Natív naptár |




## <a name="access-settings"></a>Hozzáférési beállítások

| Beállítás | Használat | Alapértelmezett érték |
|------|------|------|
| **PIN-kód megkövetelése a hozzáféréshez** | Ha az **Igen** gombot választja, a rendszer PIN-kódot kér az alkalmazás használatához. Ha a felhasználó első alkalommal futtatja az alkalmazást munkahelyi vagy iskolai környezetben, a rendszer a PIN-kód beállítására kéri. Alapértelmezett érték = **Igen**.<br><br> A PIN-kód erősségéhez az alábbi beállításokat konfigurálhatja: <ul><li>**Próbálkozások száma a PIN kód alaphelyzetbe állítása előtt**: Megadhatja, hogy a PIN-kód hányadik sikeres bevitele után kell a felhasználónak új PIN-kódot beállítania. Alapértelmezett érték = **5**.</li><li> **Egyszerű PIN-kód engedélyezése**: Az **Igen** gombot választva a felhasználó használhat egyszerű PIN-kódokat (például 1234 vagy 1111). Ha a **Nem** gombot választja, a rendszer megakadályozza az egyszerű kódok használatát. Alapértelmezett érték = **Igen**. </li><li> **PIN-kód hossza**: Itt adhatja meg, hogy legalább hány számjegyből álljon a PIN-kód. Alapértelmezett érték = **4**. </li><li> **Ujjlenyomat használatának engedélyezése PIN kód helyett (iOS 8.0+)**: válassza az **Igen** lehetőséget, ha azt szeretné, hogy az alkalmazás PIN-kód helyett [Touch ID](https://support.apple.com/HT201371) használatával is elérhető legyen. Alapértelmezett érték: **Igen**</li></ul> Az iOS-eszközökön a felhasználó használhatja a [Touch ID-t](https://support.apple.com/HT201371) a személyazonossága igazolására PIN-kód megadása helyett. Ha a felhasználó a munkahelyi vagy iskolai fiókjával próbálja használni az alkalmazást, a rendszer a PIN-kód megadása helyett ujjlenyomat-azonosítót fog kérni. Ha ez a beállítás engedélyezve van, az alkalmazásváltó funkció betekintő képe is homályos lesz, ha az alkalmazást munkahelyi vagy iskolai fiókkal használják. </li></ul>| PIN-kód megkövetelése: Igen <br><br> PIN-zárolás előtti kísérletek száma: 5 <br><br> Egyszerű PIN-kód engedélyezése: Igen <br><br> PIN-kód hossza: 4 <br><br> Ujjlenyomat engedélyezése: Igen |
| **Vállalati hitelesítő adatok szükségesek a hozzáféréshez** | Ha az **Igen** gombot választja, a felhasználónak az alkalmazás eléréséhez a munkahelyi vagy az iskolai fiókjával kell bejelentkeznie PIN-kód megadása helyett. Az **Igen** érték megadásával a rendszer felülírja a PIN-kóddal vagy az ujjlenyomatos azonosítással kapcsolatos követelményeket.  | Nem |
| **A felügyelt alkalmazások futásának letiltása a jaibreakelt vagy rootolással feltört eszközökön** |  Ha az **Igen** gombot választja, a rendszer megakadályozza az alkalmazás futtatását jailbreakelt vagy rootolt eszközökön. A felhasználó továbbra is használhatja az alkalmazást személyes feladatokra, de az alkalmazásban lévő munkahelyi vagy iskolai adatok eléréséhez másik eszközt kell használnia. | Igen |
| **A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)** | Adja meg a következő beállításokat: <ul><li>**Időtúllépés**: ennyi perc elteltével ellenőrzi újra a rendszer a (korábban a szabályzatban definiált) hozzáférési követelményeket. Ha például a rendszergazda a szabályzatban bekapcsolja a PIN-kódot, a felhasználóknak a MAM-alkalmazások megnyitásakor PIN-kódot kell megadniuk. Ezen beállítás használata esetén a felhasználónak (alapértelmezés szerint) további **30 percig** nem kell a PIN-kódját beírnia más MAM-alkalmazások eléréséhez.</li><li>**Offline türelmi időszak**: ennyi percig futhatnak offline állapotban a MAM-alkalmazások, itt adható meg (percben), hogy mikor ellenőrizze a rendszer újra az alkalmazás hozzáférési követelményeit. Alapértelmezett érték = **720** perc (12 óra). Az időszak lejárta után az alkalmazás további futásához AAD-s felhasználói hitelesítés szükséges.</li></ul>| Időkorlát: 30 <br><br> Offline: 720 |
| **Offline időtartam (nap) az alkalmazásadatok törlése előtt** | Ennyi (a rendszergazda által megadott számú) napnyi offline működés után hajt végre az alkalmazás szelektív törlést. Ez ugyanaz a művelet, mint amelyet a rendszergazda kezdeményezhet a MAM törlési munkafolyamatában. <br><br> | 90 nap |

##  <a name="add-ins-for-outlook-app"></a>Bővítmények az Outlook alkalmazáshoz

Nemrég olyan bővítmények jelentek meg az Outlook iOS-es változatához, amelyekkel népszerű alkalmazásokat lehet integrálni a levelezőprogramba. A bővítmények a webes, a windowsos, a Mac-es és az iOS-es Outlookhoz érhetők el. Mivel a bővítmények felügyelete a Microsoft Exchange-en keresztül történik, a felhasználók megoszthatnak adatokat és üzeneteket az Outlook és a nem felügyelt bővítményalkalmazások között, kivéve ha az adott felhasználónál ki vannak kapcsolva a bővítmények az Exchange-ben.

Ha szeretné beszüntetni a végfelhasználók számára az Outlook-bővítmények elérését és telepítését (ez hatással van az összes Outlook-ügyfélre), az Exchange felügyeleti központban végezze el a következő szerepkör-módosításokat:

- Az Office Áruház bővítményeinek telepítését úgy gátolhatja meg, hogy a felhasználóktól megvonja a My Marketplace (Saját piactér) szerepkört.
- A bővítményeinek közvetlen telepítését úgy gátolhatja meg, hogy a felhasználóktól megvonja a My Custom Apps (Saját egyéni alkalmazások) szerepkört.
- Amennyiben az összes bővítmény telepítését meg szeretné akadályozni a felhasználók számára, mind a Saját egyéni alkalmazások, mind a Saját piactér szerepkört távolítsa el.

Ezek az utasítások a következőkre vonatkoznak: Office 365, Exchange 2016, Exchange 2013 Webes Outlook használatával, Windows, Mac és mobil.

- További információ [az Outlook bővítményeiről](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- További információ arról, [hogyan lehet kijelölni azokat a rendszergazdákat és felhasználókat, akik Outlook-bővítményeket telepíthetnek és kezelhetnek](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).


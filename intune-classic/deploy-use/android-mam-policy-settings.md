---
title: Android MAM-szabályzatbeállítások
description: Ez a témakör bemutatja a mobilalkalmazás-felügyeleti szabályzat beállításait Android-eszközökhöz.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 04/18/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ca72391720023720cec43234d599e23888e1cc59
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Android-eszközök alkalmazásvédelmi szabályzatainak beállításai a Microsoft Intune-ban

> [!IMPORTANT]
Az oldal tartalma nagyrészt elévült, mivel az Intune alkalmazásvédelmi szabályzatait teljes mértékben az Azure Portalra migráltuk. További információ az [Intune az Azure Portalon elérhető Androidos alkalmazásvédelmi szabályzatairól](https://docs.microsoft.com/intune/app-protection-policy-settings-android).

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az ebben a témakörben ismertetett szabályzatbeállításokat az Azure Portal **Beállítások** paneljén lehet [konfigurálni](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).
A szabályzatbeállításoknak két kategóriájuk van: adatáthelyezési beállítások és hozzáférési beállítások. Ebben a témakörben a _**szabályzattal felügyelt**_ alkalmazások kifejezés olyan alkalmazásokra utal, amelyekhez alkalmazásvédelmi szabályzatot állítottak be.

##  <a name="data-relocation-settings"></a>Adatáthelyezési beállítások

| Beállítás | Használat | Alapértelmezett érték(ek) |
|------|------|------|
| **Android-alapú biztonsági mentések tiltása** | **Igen** érték esetén az alkalmazás nem készít biztonsági másolatot a munkahelyi vagy iskolai adatokról az [Android Backup Service](https://developer.android.com/google/backup/index.html) szolgáltatásba, **Nem** érték esetén megteszi.| Igen |
| **Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások kaphatnak adatokat ettől az alkalmazástól: <ul><li> **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak más, szabályzattal felügyelt alkalmazásokba engedélyezett.</li> <li>**Minden alkalmazás**: Az adatátvitel engedélyezett minden alkalmazásnál. </li> <li>**Nincs**: Minden alkalmazásba tiltott az adatátvitel., ideértve a szabályzat által felügyelt többi alkalmazást is.</li></ul> <p>Vannak kivételt képező alkalmazások és szolgáltatások, amelyek felé az Intune engedélyezheti az adatátvitelt. Az alkalmazások és a szolgáltatások teljes listája az [Adatátviteli kivételek](#Data-transfer-exemptions) című szakaszban olvasható.| Minden alkalmazás |
| **Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások küldhetnek adatokat ebbe az alkalmazásba: <ul><li>**Szabályzattal felügyelt alkalmazások**: Az átvitel csak más, szabályzattal felügyelt alkalmazásokból engedélyezett.</li><li>**Minden alkalmazás**: Az adatátvitel minden alkalmazásból engedélyezett.</li><li>**Nincs**: Minden alkalmazásból tiltott az adatátvitel, ideértve a szabályzat által felügyelt többi alkalmazást is. </li></ul> <p>Vannak kivételt képező alkalmazások és szolgáltatások, amelyek felől az Intune engedélyezheti az adatátvitelt. Az alkalmazások és a szolgáltatások teljes listája az [Adatátviteli kivételek](#Data-transfer-exemptions) című szakaszban olvasható. | Minden alkalmazás |
| **A „Mentés másként” művelet letiltása** | Az **Igen** gombot választva letilthatja a Mentés másként lehetőség használatát ebben az alkalmazásban. A **Nem** gombot választva engedélyezheti a Mentés másként funkció használatát. <p><br>**A társzolgáltatások kijelölése, melyekbe menthetők a vállalati adatok** <br>A felhasználók a kijelölt szolgáltatásokba nem tudnak menteni (OneDrive vállalati verzió, SharePoint és Helyi tárhely). Minden más szolgáltatás tiltva lesz.</p> | Nem <br><br> 0 kijelölve |
| **Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal** | Itt adhatja meg, hogy mikor használhatók a kivágási, másolási és beillesztési műveletek az alkalmazásban. A következő lehetőségek közül választhat: <ul><li>**Letiltva**:  A kivágási, másolási és beillesztési műveletek letiltása az alkalmazás és más alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások**: A kivágási, másolási és beillesztési műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**: A kivágási és másolási műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között. Adatok beillesztésének engedélyezése bármely alkalmazásból ebbe az alkalmazásba.</li><li>**Bármely alkalmazás**: Az alkalmazások közötti kivágási, másolási és beillesztési műveletek nem korlátozottak. | Bármely alkalmazás |
|**A Managed Browser (felügyelt böngésző) alkalmazásban megjelenítendő webes tartalom korlátozása** | Ha az **Igen** gombot választja, a rendszer kényszeríti az alkalmazásban lévő webes hivatkozások Managed Browser alkalmazásban való megnyitását. <br><br> Az Intune-ban nem regisztrált eszközök esetében a szabályzat által felügyelt alkalmazások webhivatkozásai kizárólag a Managed Browser alkalmazásban nyílnak meg. <br><br> Ha az Intune-t használja az eszközök kezeléséhez, olvassa el [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](manage-internet-access-using-managed-browser-policies.md) című témakört. | Nem |
| **Alkalmazásadatok titkosítása** | Az **Igen** lehetőséggel engedélyezheti a munkahelyi vagy iskolai adatok titkosítását az alkalmazásban. Az Intune az Android Keystore rendszerrel és OpenSSL 128 bites AES titkosítási sémával titkosítja biztonságosan az alkalmazásadatokat. A rendszer szinkron módon titkosítja az adatokat a fájlok írási és olvasási műveletei során. Az eszköz tárhelyén található tartalom mindig titkosított marad. <br><br> A titkosítási módszer **nem** FIPS 140-2 minősítésű.  | Igen |
| **Névjegy-szinkronizálás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. Ha a **Nem** gombot választja, a rendszer engedélyezi, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. <br><br>Ha szelektív törléssel távolítja el a munkahelyi vagy iskolai adatokat az alkalmazásból, akkor a közvetlenül az alkalmazásból a natív névjegykezelő alkalmazásba szinkronizált névjegyek törlődnek. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes. | Nem |
| **Nyomtatás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás munkahelyi vagy iskolai adatokat nyomtasson. | Nem |

  >[!NOTE]
  >Az **Alkalmazásadatok titkosítása** beállítás titkosítási módszere **nem** FIPS 140-2 minősítésű.


  ## <a name="data-transfer-exemptions"></a>Adatátviteli kivételek

  Egyes alkalmazások és platformszolgáltatások kivételt képeznek, és az Intune alkalmazásvédelmi szabályzata engedélyezheti számukra, hogy adatokat küldjenek és fogadjanak. Például az összes Intune által kezelt Androidos alkalmazásnak képesnek kell lennie a Google Szövegfelolvasóval történő adatforgalmazásra, hogy a rendszer fel tudja olvasni a mobileszköz képernyőjén látható szöveget. Ez a lista idővel változhat. Azok a szolgáltatások és alkalmazások szerepelnek rajta, amelyek megítélésünk szerint biztonságosan segítik a hatékony munkát.

  ### <a name="full-exemptions"></a>Teljes kivételek

  Ezek az alkalmazások teljes mértékben jogosultak arra, hogy adatokat küldjenek az Intune által felügyelt alkalmazásoknak, és adatokat fogadjanak tőlük.

  |Alkalmazás/szolgáltatás neve | Description |
  | ------ | ---- |
  | com.android.phone | Natív telefonalkalmazás
  | com.android.vending | Google Play Áruház |
  | com.android.documentsui | Az Android dokumentumválasztója|
  | com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html) (sok más alkalmazás mellett az Outlook számára is szükséges) |
  | com.android.webview |[WebView](https://developer.android.com/reference/android/webkit/WebView.html) (sok más alkalmazás mellett az Outlook számára is szükséges)|
  | com.google.android.tts | Google Szövegfelolvasó |
  | com.android.providers.settings | Az Android rendszerbeállításai |
  | com.azure.authenticator | Azure Authenticator alkalmazás (sokféle helyzetben szükséges a sikeres hitelesítéshez) |
  | com.microsoft.windowsintune.companyportal | Intune Vállalati portál|

  ### <a name="conditional-exemptions"></a>Feltételes kivételek
  Ezek az alkalmazások csak bizonyos feltételek teljesülése esetén kapnak engedélyt arra, hogy adatokat küldjenek az Intune által felügyelt alkalmazásoknak, és adatokat fogadjanak tőlük.

  |Alkalmazás/szolgáltatás neve | Description | A kivétel feltétele|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome böngésző | Az Android 7.0-s és újabb verziói a Chrome-ot használják bizonyos WebView-összetevőkhöz, és a böngésző sosincs elrejtve. Az alkalmazásból és részére küldött adatforgalom azonban mindig korlátozás alá esik.
  | com.skype.raider | Skype | A Skype alkalmazás csak egyes olyan műveletek esetére van engedélyezve, amelyek telefonhívást eredményezhetnek. |
  | com.android.providers.media | Android médiatartalom-szolgáltató | A médiatartalom-szolgáltató csak a csengőhang-kiválasztási művelet esetére van engedélyezve. |
  | com.google.android.gms; com.google.android.gsf | A Google Play-szolgáltatások csomagjai | Ezeknek a csomagoknak a Google Cloud Messaging műveletei, például a leküldéses értesítések esetére vannak engedélyei. |



##  <a name="access-settings"></a>Hozzáférési beállítások

| Beállítás | Használat | Alapértelmezett érték(ek) |
|------|------|------|
| **PIN-kód megkövetelése a hozzáféréshez** | Ha az **Igen** gombot választja, a rendszer PIN-kódot kér az alkalmazás használatához. Ha a felhasználó első alkalommal futtatja az alkalmazást munkahelyi vagy iskolai környezetben, a rendszer a PIN-kód beállítására kéri. Alapértelmezett érték = **Igen**.<br><br> A PIN-kód erősségéhez az alábbi beállításokat konfigurálhatja: <ul><li>**Próbálkozások száma a PIN kód alaphelyzetbe állítása előtt**: Megadhatja, hogy a PIN-kód hányadik sikeres bevitele után kell a felhasználónak új PIN-kódot beállítania. Alapértelmezett érték = **5**.</li><li> **Egyszerű PIN-kód engedélyezése**: Az **Igen** gombot választva a felhasználó használhat egyszerű PIN-kódokat (például 1234 vagy 1111). Ha a **Nem** gombot választja, a rendszer megakadályozza az egyszerű kódok használatát. Alapértelmezett érték = **Igen**. </li><li> **PIN-kód hossza**: Itt adhatja meg, hogy legalább hány számjegyből álljon a PIN-kód. Alapértelmezett érték = **4**. </li><li> **Ujjlenyomat használatának engedélyezése PIN-kód helyett (Android 6.0+)**: az **Igen** lehetőséget választva a felhasználó PIN-kód helyett [ujjlenyomat-alapú hitelesítést](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) is használhat az alkalmazás eléréséhez. Alapértelmezett érték = **Igen**.</li></ul> Androidos eszközökön engedélyezheti, hogy a felhasználó az [Android fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) ujjlenyomat-alapú hitelesítő szolgáltatást használja PIN-kód helyett. Ha a felhasználó a munkahelyi vagy iskolai fiókjával próbálja használni az alkalmazást, a rendszer PIN-kód helyett ujjlenyomat megadására fogja fog kérni. </li></ul>| PIN-kód megkövetelése: Igen <br><br> PIN-zárolás előtti kísérletek száma: 5 <br><br> Egyszerű PIN-kód engedélyezése: Igen <br><br> PIN-kód hossza: 4 <br><br> Ujjlenyomat engedélyezése: Igen |
| **Vállalati hitelesítő adatok szükségesek a hozzáféréshez** | Ha az **Igen** gombot választja, a felhasználónak az alkalmazás eléréséhez a munkahelyi vagy az iskolai fiókjával kell bejelentkeznie PIN-kód megadása helyett. Az **Igen** érték megadásával a rendszer felülírja a PIN-kóddal vagy az ujjlenyomatos azonosítással kapcsolatos követelményeket.  | Nem |
| **A felügyelt alkalmazások futásának letiltása a jaibreakelt vagy rootolással feltört eszközökön** |Ha az **Igen** gombot választja, a rendszer megakadályozza az alkalmazás futtatását jailbreakelt vagy rootolt eszközökön. A felhasználó továbbra is használhatja az alkalmazást személyes feladatokra, de az alkalmazásban lévő munkahelyi vagy iskolai adatok eléréséhez másik eszközt kell használnia. | Igen |
| **A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)** | Adja meg a következő beállításokat: <ul><li>**Időtúllépés**: ennyi perc elteltével ellenőrzi újra a rendszer a (korábban a szabályzatban definiált) hozzáférési követelményeket. Ha például a rendszergazda a szabályzatban bekapcsolja a PIN-kódot, a felhasználóknak a MAM-alkalmazások megnyitásakor PIN-kódot kell megadniuk. Ezen beállítás használata esetén a felhasználónak (alapértelmezés szerint) további **30 percig** nem kell a PIN-kódját beírnia más MAM-alkalmazások eléréséhez.</li><li>**Offline türelmi időszak**: ennyi percig futhatnak offline állapotban a MAM-alkalmazások, itt adható meg (percben), hogy mikor ellenőrizze a rendszer újra az alkalmazás hozzáférési követelményeit. Alapértelmezett érték = **720** perc (12 óra). Az időszak lejárta után az alkalmazás további futásához AAD-s felhasználói hitelesítés szükséges.</li></ul>| Időkorlát: 30 <br><br> Offline: 720 |
| **Offline időtartam (nap) az alkalmazásadatok törlése előtt** | Ennyi (a rendszergazda által megadott számú) napnyi offline működés után hajt végre az alkalmazás szelektív törlést. Ez ugyanaz a művelet, mint amelyet a rendszergazda kezdeményezhet a MAM törlési munkafolyamatában. <br><br> | 90 nap |
| **Képernyőfelvétel és az Android Assistant alkalmazás tiltása (Android 6.0+)** | Az **Igen** értéket választva letilthatja az eszköz képernyő-rögzítési lehetőségeit és az **Android Assistant** használatát az alkalmazás használatakor. Az **Igen** értéket választva az alkalmazásváltó funkció betekintő képe is homályos lesz, ha az alkalmazást munkahelyi vagy iskolai fiókkal használják. | Nem |
| **Alkalmazás PIN-kódjának letiltása, ha az eszköz PIN-kódja felügyelt** | Válassza az **Igen** beállítást, ha le szeretné tiltani az alkalmazás PIN-kódját, amikor a regisztrált eszközön eszközzárolást észlelt a rendszer. | Nem |

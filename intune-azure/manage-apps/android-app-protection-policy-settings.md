---
title: "Az alkalmazásvédelmi szabályzatok ellenőrzése | Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Ez a témakör az alkalmazásvédelmi szabályzatok androidos eszközökre vonatkozó beállításait ismerteti."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 6720c163e712e9d27319b16b0e1515e9e7f13ee8


---

# <a name="android-app-protection-policy-settings"></a>Alkalmazásvédelmi szabályzatok androidos beállításai
A jelen témakörben ismertetett szabályzatbeállításokat az Azure Portal **Beállítások** paneljén lehet [konfigurálni](app-protection-policies.md) az alkalmazásvédelmi szabályzatokhoz.
A szabályzatbeállításoknak két kategóriájuk van: adatáthelyezési beállítások és hozzáférési beállítások. A jelen témakörben a *szabályzattal felügyelt alkalmazások* kifejezés olyan alkalmazásokra utal, amelyekhez alkalmazásvédelmi szabályzatot állítottak be.

##  <a name="data-relocation-settings"></a>Adatáthelyezési beállítások

| Beállítás | Használat | Alapértelmezett érték(ek) |
|------|------|------|
| **Android-alapú biztonsági mentések tiltása** | **Igen** érték esetén az alkalmazás nem készít biztonsági másolatot a munkahelyi vagy iskolai adatokról az [Android Backup Service](https://developer.android.com/google/backup/index.html) szolgáltatásba, **Nem** érték esetén megteszi.| Igen |
| **Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások kaphatnak adatokat ettől az alkalmazástól: <ul><li> **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak más, szabályzattal felügyelt alkalmazásokba engedélyezett.</li> <li>**Minden alkalmazás**: Az adatátvitel engedélyezett minden alkalmazásnál. </li> <li>**Nincs**: Minden alkalmazásba tiltott az adatátvitel, ideértve a szabályzat által felügyelt többi alkalmazást is.</li></ul> | Minden alkalmazás |
| **Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak** | Itt adhatja meg, mely alkalmazások küldhetnek adatokat ebbe az alkalmazásba: <ul><li>**Szabályzattal felügyelt alkalmazások**: Az átvitel csak más, szabályzattal felügyelt alkalmazásokból engedélyezett.</li><li>**Minden alkalmazás**: Az adatátvitel minden alkalmazásból engedélyezett.</li><li>**Nincs**: Minden alkalmazásból tiltott az adatátvitel, ideértve a szabályzat által felügyelt többi alkalmazást is. | Minden alkalmazás |
| **A „Mentés másként” művelet letiltása** | Az **Igen** gombot választva letilthatja a Mentés másként lehetőség használatát ebben az alkalmazásban. A **Nem** gombot választva engedélyezheti a Mentés másként funkció használatát. | Nem |
| **Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal** | Itt adhatja meg, hogy mikor használhatók a kivágási, másolási és beillesztési műveletek az alkalmazásban. A következő lehetőségek közül választhat: <ul><li>**Letiltva**:  A kivágási, másolási és beillesztési műveletek letiltása az alkalmazás és más alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások**: A kivágási, másolási és beillesztési műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között.</li><li>**Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**: A kivágási és másolási műveletek engedélyezése az alkalmazás és más, szabályzattal felügyelt alkalmazások között. Adatok beillesztésének engedélyezése bármely alkalmazásból ebbe az alkalmazásba.</li><li>**Bármely alkalmazás**: Az alkalmazások közötti kivágási, másolási és beillesztési műveletek nem korlátozottak. | Bármely alkalmazás |
|**A Managed Browser (felügyelt böngésző) alkalmazásban megjelenítendő webes tartalom korlátozása** | Ha az **Igen** gombot választja, a rendszer kényszeríti az alkalmazásban lévő webes hivatkozások Managed Browser alkalmazásban való megnyitását. <br><br> Az Intune-ban nem regisztrált eszközök esetében a szabályzat által felügyelt alkalmazások webhivatkozásai kizárólag a Managed Browser alkalmazásban nyílnak meg. <br><br> Ha az Intune-t használja az eszközök kezeléséhez, olvassa el [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](https://docs.microsoft.com/intune/deploy-use/manage-internet-access-using-managed-browser-policies) című témakört. | Nem |
| **Alkalmazásadatok titkosítása** | Az **Igen** lehetőséggel engedélyezheti a munkahelyi vagy iskolai adatok titkosítását az alkalmazásban. Az Intune az Android Keystore rendszerrel és OpenSSL titkosítási sémával titkosítja biztonságosan az alkalmazásadatokat. A rendszer szinkron módon titkosítja az adatokat a fájlok írási és olvasási műveletei során. Az eszköz tárhelyén található tartalom mindig titkosított marad. <br><br> A titkosítási módszer **nem** FIPS 140-2 minősítésű.  | Igen |
| **Névjegy-szinkronizálás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. Ha a **Nem** gombot választja, a rendszer engedélyezi, hogy az alkalmazás a natív névjegykezelő alkalmazásba adatokat mentsen ezen az eszközön. <br><br>Ha szelektív törléssel távolítja el a munkahelyi vagy iskolai adatokat az alkalmazásból, akkor a közvetlenül az alkalmazásból a natív névjegykezelő alkalmazásba szinkronizált névjegyek törlődnek. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes. | Nem |
| **Nyomtatás letiltása** | Ha az **Igen** gombot választja, a rendszer megakadályozza, hogy az alkalmazás munkahelyi vagy iskolai adatokat nyomtasson. | Nem |


  >[!NOTE]
  >Az **Alkalmazásadatok titkosítása** beállítás titkosítási módszere **nem** FIPS 140-2 minősítésű.




##  <a name="access-settings"></a>Hozzáférési beállítások

| Beállítás | Használat | Alapértelmezett érték(ek) |
|------|------|------|
| **PIN-kód megkövetelése a hozzáféréshez** | Ha az **Igen** gombot választja, a rendszer PIN-kódot kér az alkalmazás használatához. Ha a felhasználó első alkalommal futtatja az alkalmazást munkahelyi vagy iskolai környezetben, a rendszer a PIN-kód beállítására kéri. Alapértelmezett érték = **Igen**.<br><br> A PIN-kód erősségéhez az alábbi beállításokat konfigurálhatja: <ul><li>**Próbálkozások száma a PIN kód alaphelyzetbe állítása előtt**: Megadhatja, hogy a PIN-kód hányadik sikeres bevitele után kell a felhasználónak új PIN-kódot beállítania. Alapértelmezett érték = **5**.</li><li> **Egyszerű PIN-kód engedélyezése**: Az **Igen** gombot választva a felhasználó használhat egyszerű PIN-kódokat (például 1234 vagy 1111). Ha a **Nem** gombot választja, a rendszer megakadályozza az egyszerű kódok használatát. Alapértelmezett érték = **Igen**. </li><li> **PIN-kód hossza**: Itt adhatja meg, hogy legalább hány számjegyből álljon a PIN-kód. Alapértelmezett érték = **4**. </li><li> **Ujjlenyomat használatának engedélyezése PIN-kód helyett (Android 6.0+)**: az **Igen** lehetőséget választva a felhasználó PIN-kód helyett [ujjlenyomat-alapú hitelesítést](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) is használhat az alkalmazás eléréséhez. Alapértelmezett érték = **Igen**.<br><br> Androidos eszközökön engedélyezheti, hogy a felhasználó az [Android fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) ujjlenyomat-alapú hitelesítő szolgáltatást használja PIN-kód helyett. Ha a felhasználó a munkahelyi vagy iskolai fiókjával próbálja használni az alkalmazást, a rendszer PIN-kód helyett ujjlenyomat megadására fogja fog kérni. </li></ul>| PIN-kód megkövetelése: Igen <br><br> PIN-zárolás előtti kísérletek száma: 5 <br><br> Egyszerű PIN-kód engedélyezése: Igen <br><br> PIN-kód hossza: 4 <br><br> Ujjlenyomat engedélyezése: Igen |
| **Vállalati hitelesítő adatok szükségesek a hozzáféréshez** | Ha az **Igen** gombot választja, a felhasználónak az alkalmazás eléréséhez a munkahelyi vagy az iskolai fiókjával kell bejelentkeznie PIN-kód megadása helyett. Az **Igen** érték megadásával a rendszer felülírja a PIN-kóddal vagy az ujjlenyomatos azonosítással kapcsolatos követelményeket.  | Nem |
| **A felügyelt alkalmazások futásának letiltása a jaibreakelt vagy rootolással feltört eszközökön** |  Ha az **Igen** gombot választja, a rendszer megakadályozza az alkalmazás futtatását jailbreakelt vagy rootolt eszközökön. A felhasználó továbbra is használhatja az alkalmazást személyes feladatokra, de az alkalmazásban lévő munkahelyi vagy iskolai adatok eléréséhez másik eszközt kell használnia. | Igen |
| **A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)** | Adja meg a következő beállításokat: <ul><li>**Időtúllépés**: Itt adhatja meg az alkalmazás hozzáférési követelményeinek újbóli ellenőrzéséig fennmaradó időt (percben). Alapértelmezett érték = **30** perc.</li><li>**Offline türelmi időszak**: Ennyi idő elteltével kerül sor újra az alkalmazás hozzáférési követelményeinek ismételt ellenőrzésére (percben), ha az eszköz offline állapotban van. Alapértelmezett érték = **720** perc (12 óra).</li></ul>| Időkorlát: 30 <br><br> Offline: 720 |
| **Offline időtartam (nap) az alkalmazásadatok törlése előtt** | Az alkalmazásban lévő munkahelyi vagy iskolai adatok törlődhetnek, ha az eszköz egy bizonyos időtartamnál tovább van offline állapotban. Itt adhatja meg, hány napig lehet az eszköz offline állapotban, mielőtt a rendszer eltávolítaná róla a munkahelyi vagy iskolai adatokat. <br><br> | 90 nap |
| **Képernyőfelvétel és az Android Assistant alkalmazás tiltása (Android 6.0+)** | Az **Igen** értéket választva letilthatja az eszköz képernyő-rögzítési lehetőségeit és az **Android Assistant** használatát az alkalmazás használatakor. Az **Igen** értéket választva az alkalmazásváltó funkció betekintő képe is homályos lesz, ha az alkalmazást munkahelyi vagy iskolai fiókkal használják. | Nem |



<!--HONumber=Feb17_HO1-->



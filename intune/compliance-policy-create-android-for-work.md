---
title: Android Enterprise-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Android Enterprise és munkahelyi profilos eszközök Microsoft Intune-eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása. Feltört eszközök választható engedélyezése, az elfogadható fenyegetettségi szint megadása, a Google Play Áruház ellenőrzése, minimális és maximális operációsrendszer-verzió megadása, jelszókövetelmények megválasztása és alkalmazások közvetlen telepítésének engedélyezése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff1f4f6a728fc041241371a413ce9d2dfdf89605
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236458"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Android Enterprise-eszközök eszközmegfelelőségi szabályzatának hozzáadása az Intune-ban

Az eszközmegfelelőségi szabályzatok használata kiemelten fontos, ha az Intune-t a vállalat erőforrásainak védelmére kívánja használni. Az Intune-ban olyan szabályokat és beállításokat hozhat létre, amelyekhez az eszközöknek feltétlenül igazodniuk kell a megfelelőséghez (például megszabhatja a jelszavak hosszát). Ha egy eszköz nem megfelelő, a [feltételes hozzáférés](conditional-access.md) segítségével blokkolhatja a hozzáférést az adatokhoz és erőforrásokhoz. 

Ezen kívül jelentéseket kérhet az eszközökről, elégtelen megfelelőség esetén pedig számos művelet áll rendelkezésére, például e-mailben figyelmeztetést küldhet az adott felhasználónak. A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

Ez a cikk az Android Enterprise-t futtató eszközök megfelelőségi szabályzatában használható beállításokat sorolja fel.

## <a name="non-compliance-and-conditional-access"></a>Meg nem felelés és feltételes hozzáférés

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

--------------------------

|**házirend-beállítás**| **Android Enterprise-profil** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** |  Karanténba helyezve |
| **Eszköztitkosítás** |  Karanténba helyezve |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás) |
| **e-mail profil** | Nem alkalmazható |
| **Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |
| **Windows-állapotigazolás** |Nem alkalmazható |

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. Például a felhasználó köteles lesz PIN-kódot beállítani.

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. Például az Android-eszközök nem követelik meg a felhasználótól, hogy titkosítsa az eszközt. Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

  - Ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik, a rendszer letiltja az eszközt.
  - A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. A **Platform** beállításban válassza a **Vállalati Android** lehetőséget. 
5. Válassza a **Beállítások konfigurálása** lehetőséget. Adja meg az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításait a cikkben leírtak szerint.

## <a name="device-health"></a>Device health

- **Rootolt eszközök**: Válassza a **Letiltás** lehetőséget a rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Maximálisan elérhető eszközfenyegetettségi szint használata**: Ezzel a beállítással a Lookout MTP-től származó kockázatbecslés lesz a megfelelőség feltétele. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a legbiztonságosabb beállítás. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként fogja értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő beállítás. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
- **A Google Play-szolgáltatások be van állítva**: **Kötelező** a Google Play-szolgáltatások alkalmazás telepítése és engedélyezése. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Naprakész biztonsági szolgáltató**: **Kötelező** egy naprakész biztonsági szolgáltatóval védeni az eszközöket az ismert biztonsági kockázatokkal szemben. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **SafetyNet eszközigazolás**: Megadható a [SafetyNet igazolás](https://developer.android.com/training/safetynet/attestation.html) elvárt szintje. A választható lehetőségek:
  - **Nincs konfigurálva** (alapértelmezett): A rendszer nem értékeli a beállítást a megfelelőség vagy meg nem felelőség megállapításához.
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

#### <a name="threat-scan-on-apps"></a>Alkalmazások fenyegetettségvizsgálata

Az Android Enterprise eszközöknél a **Alkalmazások fenyegetettségvizsgálata** beállítás egy konfigurációs szabályzat. Lásd: [Eszközkorlátozásokra vonatkozó beállítások Android Enterprise esetén](device-restrictions-android-for-work.md)

## <a name="device-properties-settings"></a>Eszköztulajdonságok beállításai

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ezután pedig hozzáfér a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az eszköz operációs rendszerének verzióját is.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Jelszó minimális hossza**: Meghatározhatja a felhasználó jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó megkövetelt típusa**: Megadható, hogy a jelszó csak számjegyeket, vagy számokat és más karaktereket vegyesen tartalmazzon. A választható lehetőségek:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok** (alapértelmezett)
  - **Komplex numerikus**
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány legutóbbi jelszó ne legyen újra felhasználható. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

### <a name="encryption"></a>Encryption

- **Adattároló titkosítása az eszközön**: A **Kötelező** lehetőséget választva az adattárolók titkosítva lesznek az eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. 

  Ezt a beállítást nem szükséges konfigurálni, mivel az androidos munkahelyi profilokkal rendelkező eszközök kikényszerítik a titkosítást.

### <a name="device-security"></a>Eszközbiztonság

- **Ismeretlen forrásból származó alkalmazások letiltása**: Választásával **letilthatók** a „Biztonság > Ismeretlen források” alatti forrásokat engedélyező eszközök (támogatott az Android 4.0 – Android 7.x. rendszereken, és nem támogatott az Android 8.0-s és újabb rendszereken). Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Alkalmazások közvetlen telepítéséhez az ismeretlen forrásokat engedélyezni kell. Ha nem telepít közvetlenül Android-alkalmazásokat, akkor a megfelelőségi szabályzat engedélyezéséhez adja meg a **Letiltás** beállítást ehhez a funkcióhoz. 

  > [!IMPORTANT]
  > Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen forrásból származó alkalmazások letiltása** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem telepít közvetlenül Android-alkalmazásokat az eszközökön.

  Ezt a beállítást nem szükséges konfigurálni, mivel az androidos munkahelyi profilokkal rendelkező eszközök mindig korlátozzák az ismeretlen forrásokból való telepítést.

- **A Céges portál alkalmazás futtatókörnyezetének integritása**: Válassza a **Kötelező** lehetőséget annak megerősítéséhez, hogy a Céges portál alkalmazás megfelel az összes alábbi követelménynek:

  - Telepítve van hozzá az alapértelmezett futtatókörnyezet
  - Megfelelően alá van írva
  - Nincs hibakeresési módban
  - Ismert forrásból telepítették

  Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

- **USB-hibakeresés letiltása az eszközön**: A **Letiltás** választásával megakadályozható az USB-hibakeresési funkció használata az eszközön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Ezt a beállítást nem szükséges konfigurálni, mivel az androidos munkahelyi profilokkal rendelkező eszközökön már le van tiltva az USB-hibakeresés.

- **Minimális biztonsági javítási szint**: Megadható a legrégebbi biztonsági javítás, amellyel az eszköz rendelkezhet. Az ennél régebbi javítási verzióval rendelkező eszközök nem megfelelőek. Az adatokat a következő formátumban kell megadni: *ÉÉÉÉ-HH-NN*.

Ha elkészült, a változások mentéséhez válassza az **OK** > **OK** lehetőségeket.

## <a name="actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek

Válassza a **Meg nem felelés esetén végrehajtandó műveletek** lehetőséget. Az alapértelmezett művelet azonnal nem megfelelőként jelöli meg az eszközt.

Módosíthatja az eszköz nem megfelelőként való megjelölésének ütemezését, megadhatja például, hogy egy nap elteltével jelölje a rendszer nem megfelelőnek az eszközt. Hozzáadhat egy második műveletet is, amely e-mailt küld a felhasználónak, ha az eszköz nem megfelelő.

A [Műveletek hozzáadása nem megfelelő eszközökhöz](actions-for-noncompliance.md) további információval szolgál, többek között arról, hogyan hozhat létre értesítési e-mailt a felhasználók számára.

## <a name="scope-tags"></a>Hatókörcímkék

A hatókörcímkék nagyszerű módot kínálnak egyes szabályzatok meghatározott csoportokhoz (például az értékesítési, a mérnöki vagy a HR-csoporthoz) való hozzárendeléséhez. A megfelelőségi szabályzatokhoz hatókörcímkéket adhat hozzá. Lásd: [Hatókörcímkék használata szabályzatok szűrésére](scope-tags.md). 

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A szabályzat a létrehozása után csak akkor lép működésbe, ha hozzárendeli egy csoporthoz. A szabályzat hozzárendelése: 

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)  
[Megfelelőségi szabályzat beállításai Androidhoz](compliance-policy-create-android.md)
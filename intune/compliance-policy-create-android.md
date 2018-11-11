---
title: Android-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Android-eszközök Microsoft Intune eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása. Feltört eszközök választható engedélyezése, az elfogadható fenyegetettségi szint megadása, a Google Play Áruház ellenőrzése, minimális és maximális operációsrendszer-verzió megadása, jelszókövetelmények megválasztása és alkalmazások közvetlen telepítésének engedélyezése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1108a208a324b5ed4c46248dc986dcf08e6293fe
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236543"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Android-eszközök eszközmegfelelőségi szabályzatának hozzáadása az Intune-ban

Az Android-eszközökhöz készült megfelelőségi szabályzatok meghatározzák az Android-eszközök megfelelőségéhez szükséges szabályokat és beállításokat. Ezeket a szabályzatokat [feltételes hozzáféréssel](conditional-access.md) használva megakadályozható vagy engedélyezhető a szervezeti erőforrásokhoz való hozzáférés. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. 

A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

Ez a témakör felsorolja az Android-eszközök megfelelőségi szabályzatában használható beállításokat.

## <a name="non-compliance-and-conditional-access"></a>Meg nem felelés és feltételes hozzáférés

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

--------------------

|**Szabályzat-beállítás**| **Android 4.0-s és újabb verziók, Samsung KNOX szabvány 4.0-s és újabb verziók** |
| --- | ----|
| **PIN-kód vagy jelszó konfigurálása** |  Karanténba helyezve |
| **Eszköztitkosítás** | Karanténba helyezve |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás) |
| **e-mail profil** | Nem alkalmazható |
| **Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** |   Karanténba helyezve |
| **Windows-állapotigazolás** | Nem alkalmazható |

--------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. Például a felhasználó köteles lesz PIN-kódot beállítani.

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását. Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

  - A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
  - A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. A **Platform** beállításban válassza az **Android** lehetőséget. 
5. Válassza a **Beállítások konfigurálása** lehetőséget. Adja meg az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításait, amint az ebben a cikkben szerepel.

## <a name="device-health"></a>Device health

- **Rootolt eszközök**: Válassza a **Letiltás** lehetőséget a rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Maximálisan elérhető eszközfenyegetettségi szint használata**: Ezzel a beállítással a Lookout MTP-től származó kockázatbecslés lesz a megfelelőség feltétele. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a legbiztonságosabb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő beállítás. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
- **A Google Play-szolgáltatások be van állítva**: **Kötelező** a Google Play-szolgáltatások alkalmazás telepítése és engedélyezése. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Naprakész biztonsági szolgáltató**: **Kötelező** egy naprakész biztonsági szolgáltatóval védeni az eszközöket az ismert biztonsági kockázatokkal szemben. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Alkalmazások fenyegetettségvizsgálata**: **Kötelező** az androidos **Alkalmazások ellenőrzése** szolgáltatás engedélyezése. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.

  > [!NOTE]
  > A régebbi Android platformon ez a szolgáltatás egy megfelelőségi beállítás. Az Intune csak azt tudja ellenőrizni, hogy eszközszinten engedélyezett-e ez a beállítás.

- **SafetyNet eszközigazolás**: Megadható a [SafetyNet igazolás](https://developer.android.com/training/safetynet/attestation.html) elvárt szintje. A választható lehetőségek:
  - **Nincs konfigurálva** (alapértelmezett): A rendszer nem értékeli a beállítást a megfelelőség vagy meg nem felelőség megállapításához.
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Jelszó minimális hossza**: Meghatározhatja a felhasználó jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó megkövetelt típusa**: Megadható, hogy a jelszó csak számjegyeket vagy számokat és más karaktereket vegyesen tartalmazzon. A választható lehetőségek:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok** (alapértelmezett)
  - **Komplex numerikus**: Nem lehet ismétlődő vagy egymást követő számokat megadni (például `1111` vagy `1234`).
  - **Legalább betűk** 
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után a felhasználónak újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány legutóbbi jelszó ne legyen újra felhasználható. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

### <a name="encryption"></a>Encryption

- **Adattároló titkosítása az eszközön** (Android 4.0 és újabb, vagy KNOX 4.0 és újabb): A **Kötelező** lehetőséget választva az adattárolók titkosítva lesznek az eszközökön. Az eszközök **A mobileszközök zárolásának feloldásához jelszó szükséges** beállítás használatával titkosíthatók. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.

### <a name="device-security"></a>Eszközbiztonság

- **Ismeretlen forrásból származó alkalmazások letiltása**: Választásával **letilthatók** a „Biztonság > Ismeretlen források” alatti forrásokat engedélyező eszközök (támogatott az Android 4.0 – Android 7.x. rendszereken, és nem támogatott az Android 8.0-s és újabb rendszereken). Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.

  Alkalmazások közvetlen telepítéséhez az ismeretlen forrásokat engedélyezni kell. Ha nem telepít közvetlenül Android-alkalmazásokat, akkor adja meg a **Letiltás** beállítást ehhez a funkcióhoz a megfelelőségi szabályzat engedélyezéséhez. 

  > [!IMPORTANT]
  > Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen forrásból származó alkalmazások letiltása** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem végzi Android-alkalmazások közvetlen telepítését az eszközökön.

- **A Céges portál alkalmazás futtatókörnyezetének integritása**: Válassza a **Kötelező** lehetőséget annak megerősítéséhez, hogy a Céges portál alkalmazás megfelel az összes alábbi követelménynek:

  - Telepítve van hozzá az alapértelmezett futtatókörnyezet
  - Megfelelően alá van írva
  - Nincs hibakeresési módban
  - Ismert forrásból telepítették

  Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.

- **USB-hibakeresés letiltása az eszközön** (Android 4.2 vagy újabb): a **Letiltás** választásával megakadályozható az eszközön az USB-hibakeresés funkció használata. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást veszi figyelembe a megfelelőség, meg nem felelőség megállapításához.
- **Minimális biztonsági javítási szint** (Android 6.0 vagy újabb): Megadható a legrégebbi biztonsági javítás, amellyel az eszköz rendelkezhet. Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot `YYYY-MM-DD` formátumban kell megadni.
- **Korlátozott alkalmazások**: Adja meg az **Alkalmazás neve** és az **Alkalmazásköteg-azonosító** adatot a korlátozni kívánt alkalmazásokhoz. Válassza a **Hozzáadás** lehetőséget. A legalább egy telepített korlátozott alkalmazással rendelkező eszközök megjelölése nem megfelelő.

Ha elkészült, a változások mentéséhez válassz az **OK** > **OK** gombot.

## <a name="locations"></a>Helyek

A saját szabályzaton belül válasszon a meglévő helyek közül. Még nem rendelkezik hellyel? A [Helyek (hálózati kerítés) használata az Intune-ban](use-network-locations.md) című cikkből tájékozódhat.

1. Válassza a **Helyek** lehetőséget.
2. A listán jelölje be a helyet, majd kattintson a **Kiválasztás** elemre.
3. **Mentse** a szabályzatot.

## <a name="actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek

Válassza a **Meg nem felelés esetén végrehajtandó műveletek** lehetőséget. Az alapértelmezett művelet azonnal nem megfelelőként jelöli meg az eszközt.

Módosíthatja az eszköz nem megfelelőként való megjelölésének ütemezését, megadhatja például, hogy egy nap elteltével. Hozzáadhat egy második műveletet is, amely e-mailt küld a felhasználónak, amikor az eszköz nem megfelelő.

A [Műveletek hozzáadása nem megfelelő eszközökhöz](actions-for-noncompliance.md) további információval szolgál, többek között értesítési e-mailt hozhat létre a felhasználók számára.

Például, a Helyek funkciót használja, és hozzáad egy helyet egy megfelelőségi szabályzatban. Az alapértelmezett meg nem felelési művelet alkalmazandó, ha kiválaszt legalább egy helyet. Ha az eszköz nem csatlakozik a megadott helyekhez, akkor azonnal nem megfelelőnek számít. Biztosíthat a felhasználóknak egy türelmi időszakot, például egy napot.

## <a name="scope-tags"></a>Hatókörcímkék

A hatókörcímkék nagyszerű módot kínálnak szabályzatok meghatározott csoportokhoz, például az értékesítési, a mérnöki vagy a HR-csoporthoz való hozzárendeléséhez. A megfelelőségi szabályzatokhoz hozzáadhat hatókörcímkéket. Lásd: [Hatókörcímkék használata szabályzatok szűrésére](scope-tags.md). 

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A szabályzat a létrehozása után csak akkor működik, ha hozzárendeli egy csoporthoz. A szabályzat hozzárendelése: 

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)  
[Az Android Enterprise megfelelőségi szabályzatainak beállításai](compliance-policy-create-android-for-work.md)

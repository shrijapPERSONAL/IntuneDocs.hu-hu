---
title: Android-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Android-eszközök Microsoft Intune eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása. Feltört eszközök választható engedélyezése, az elfogadható fenyegetettségi szint megadása, a Google Play Áruház ellenőrzése, minimális és maximális operációsrendszer-verzió megadása, jelszókövetelmények megválasztása és alkalmazások közvetlen telepítésének engedélyezése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 87fecc8b8c2d9bf408b622f6eaf8af1bbe011df0
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229564"
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

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. Például az Android-eszközök nem követelik meg a felhasználótól, hogy titkosítsa az eszközt. Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

  - A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
  - A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. A **Platform** beállításban válassza az **Android** lehetőséget. 
5. Válassza a **Beállítások konfigurálása** lehetőséget. Adja meg az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításait a cikkben leírtak szerint.

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Válasszon **blokk** az rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Az eszköz vagy az eszköz fenyegetettségi szintje alatt megkövetelése**: Ez a beállítás használatával igénybe vehet a kockázatelemzést Lookout MTP-megoldásból a megfelelőség feltétele. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a lehetőség akkor a legtöbb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként fogja értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a beállítás a legkevésbé biztonságos, és minden kockázati szintet. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
- **Google Play-szolgáltatások konfigurálva van**: **Szükséges** , hogy a Google Play szolgáltatások alkalmazás telepítve van és engedélyezett. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Naprakész biztonsági szolgáltató**: **Szükséges** , hogy egy naprakész biztonságszolgáltató képes védeni az eszközöket az ismert biztonsági rések. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Alkalmazások fenyegetettségvizsgálata**: **Szükséges** , amelyek az Android **alkalmazások ellenőrzése** szolgáltatás engedélyezve van. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  > [!NOTE]
  > A régebbi Android platformon ez a szolgáltatás egy megfelelőségi beállítás. Az Intune csak azt tudja ellenőrizni, hogy eszközszinten engedélyezett-e ez a beállítás.

- **SafetyNet eszközigazolás**: Adja meg a szintű [SafetyNet-igazolás](https://developer.android.com/training/safetynet/attestation.html) a teljesülniük kell. A választható lehetőségek:
  - **Nincs konfigurálva** (alapértelmezett): A beállítás a nem megfelelőség vagy a meg nem felelés értékeli ki.
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabályban megadott, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az eszköz operációs rendszerének verzióját is.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Jelszó minimális hossza**: Adja meg a felhasználó jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak számokat, vagy számokat többféle és más karaktereket tartalmaznia kell. A választható lehetőségek:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok** (alapértelmezett)
  - **Komplex numerikus**: Ismétlődő vagy egymást követő számokat, mint például `1111` vagy `1234`, nem engedélyezett.
  - **Legalább betűk** 
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és a felhasználó egy új jelszót kell létrehozni.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak nem használható fel újra. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

### <a name="encryption"></a>Encryption

- **Titkosítása az eszközön** (Android 4.0-s és újabb, vagy KNOX 4.0 és újabb): Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához. Az eszközök **A mobileszközök zárolásának feloldásához jelszó szükséges** beállítás használatával titkosíthatók. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

### <a name="device-security"></a>Eszközbiztonság

- **Ismeretlen forrásból származó alkalmazások letiltása**: Válassza ki a **blokk** "Biztonság > Ismeretlen források" eszközök engedélyezve van a forrásból (Android 4.0 – Android 7.x rendszeren támogatott; nem támogatott Android 8.0 és újabb verziók). Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Alkalmazások közvetlen telepítéséhez az ismeretlen forrásokat engedélyezni kell. Ha nem telepít közvetlenül Android-alkalmazásokat, akkor a megfelelőségi szabályzat engedélyezéséhez adja meg a **Letiltás** beállítást ehhez a funkcióhoz. 

  > [!IMPORTANT]
  > Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen forrásból származó alkalmazások letiltása** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem telepít közvetlenül Android-alkalmazásokat az eszközökön.

- **Céges portál alkalmazás futtatókörnyezetének integritása**: Válasszon **megkövetelése** , győződjön meg róla a vállalati portál alkalmazás megfelel-e az alábbi követelményeknek:

  - Telepítve van hozzá az alapértelmezett futtatókörnyezet
  - Megfelelően alá van írva
  - Nincs hibakeresési módban
  - Ismert forrásból telepítették

  Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

- **USB-hibakeresés letiltása az eszközön** (Android 4.2 vagy újabb): Válasszon **blokk** megakadályozza, hogy az eszközök az USB-hibakeresés funkció használata. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Minimális biztonsági javítási szint** (Android 6.0 vagy újabb): Válassza ki az eszköz minimális biztonsági javítási szintjének. Az ennél régebbi javítási verzióval rendelkező eszközök nem megfelelőek. A dátumot `YYYY-MM-DD` formátumban kell megadni.
- **Korlátozott alkalmazások**: Adja meg a **alkalmazásnév** és **alkalmazásköteg-azonosító** kell lennie a korlátozott alkalmazások esetében. Válassza a **Hozzáadás** lehetőséget. A legalább egy telepített korlátozott alkalmazással rendelkező eszközök megjelölése nem megfelelő.

Ha elkészült, a változások mentéséhez válassza az **OK** > **OK** lehetőségeket.

## <a name="locations"></a>Helyek

A saját szabályzaton belül válasszon a meglévő helyek közül. Még nem rendelkezik hellyel? A [Helyek (hálózati kerítés) használata az Intune-ban](use-network-locations.md) című cikkből tájékozódhat.

1. Válassza a **Helyek** lehetőséget.
2. A listán jelölje be a helyet, majd kattintson a **Kiválasztás** elemre.
3. **Mentse** a szabályzatot.

## <a name="actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek

Válassza a **Meg nem felelés esetén végrehajtandó műveletek** lehetőséget. Az alapértelmezett művelet azonnal nem megfelelőként jelöli meg az eszközt.

Módosíthatja az eszköz nem megfelelőként való megjelölésének ütemezését, megadhatja például, hogy egy nap elteltével jelölje a rendszer nem megfelelőnek az eszközt. Hozzáadhat egy második műveletet is, amely e-mailt küld a felhasználónak, ha az eszköz nem megfelelő.

A [Műveletek hozzáadása nem megfelelő eszközökhöz](actions-for-noncompliance.md) további információval szolgál, többek között értesítési e-mailt hozhat létre a felhasználók számára.

Például, a Helyek funkciót használja, és hozzáad egy helyet egy megfelelőségi szabályzatban. Az alapértelmezett meg nem felelési művelet alkalmazandó, ha kiválaszt legalább egy helyet. Ha az eszköz nem csatlakozik a megadott helyekhez, akkor azonnal nem megfelelőnek számít. Biztosíthat a felhasználóknak egy türelmi időszakot, például egy napot.

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
[Az Android Enterprise megfelelőségi szabályzatainak beállításai](compliance-policy-create-android-for-work.md)

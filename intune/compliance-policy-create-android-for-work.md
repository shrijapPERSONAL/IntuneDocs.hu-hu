---
title: Android Enterprise megfelelőségi beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Használhatja a Microsoft Intune-ban a vállalati Android-eszköz megfelelőségének beállításakor minden beállítások listájának megtekintéséhez. Jelszószabályok beállítása egy minimális és maximális operációsrendszer-verzió, adott alkalmazásokra korlátozhatja, és burkolóalkalmazások újbóli használata jelszó és egyéb megakadályozása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/15/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7a9a5ff686ce3cff8b60c2bd1c0c5d108d58760
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896887"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android Enterprise-beállítások eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és konfigurálhat vállalati Android-eszköz Intune-ban a különböző megfelelőségi beállításait ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat megjelölése nem megfelelőként rootolt (feltört) eszközöket, egy megengedett kockázati szintet, a Google Play Protect, és több.

Ez a funkció az alábbiakra vonatkozik:

- Vállalati Android

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

> [!IMPORTANT]
> Megfelelőségi szabályzatok dedikált vállalati Android-eszköz is érvényesek. Megfelelőségi szabályzat van rendelve egy dedikált eszközt, ha az eszközt előfordulhat, hogy megjelenítése **nem megfelelő**. Feltételes hozzáférés és a megfelelőség kényszerítése a dedikált eszközök érhető el. Győződjön meg arról, bármely feladatok vagy dedikált eszközök felelnek meg a hozzárendelt szabályzatok lekérése műveletek végrehajtásához.

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform**válassza **Android Enterprise**.

## <a name="device-owner"></a>Az eszköz tulajdonosa

### <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, a nem megfelelő rendszer jelenti. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és majd hozzáférni a szervezet erőforrásaihoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabály, a szervezeti erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak meg kell adnia, forduljon az IT-rendszergazdához. Egy szabályt, hogy az operációs rendszer verziója megváltozott, amíg az eszköz nem lehet hozzáférni a szervezet erőforrásaihoz.

### <a name="system-security"></a>Rendszerbiztonság

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Ez a beállítás az eszköz szintjén alkalmazzák. Ha csak a munkahelyi profil szintjén jelszót kell, használja a konfigurációs szabályzat. Lásd: [Android Enterprise eszköz konfigurációs beállításai](device-restrictions-android-for-work.md).

  - **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak számokat, vagy számokat többféle és más karaktereket tartalmaznia kell. A választható lehetőségek:
    - **Eszköz alapértelmezése**
    - **Jelszó szükséges, korlátozás nélkül**
    - **Biometrikus weak**: [Erős vagy egyszerű biometrikus](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android a webhely megnyitása)
    - **Numerikus**: Jelszó csak számokból kell, például `123456789`. Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
    - **Komplex numerikus**: Ismétlődő vagy egymást követő számokat, például az "1111" vagy "1234", nem engedélyezett. Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
    - **Alfabetikus**: Az ábécé betűit szükség. Számok és szimbólumok nem szükséges. Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
    - **Alphanumeric**: Nagybetűk, kisbetűk és numerikus karaktereket tartalmaz. Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
    - **Alfanumerikus karakterek és szimbólumok**: Nagybetűk, kisbetűk, számjegyekből, írásjelek és szimbólumokat tartalmaz. Ezt is adja meg:

      - **Jelszó minimális hossza**: Adja meg a jelszóban, 4 és 16 karakter között minimális hosszát.
      - **Hány karakterből kell állnia**: Adja meg az karakterek a jelszóban, 0 és 16 karakter között.
      - **Kötelező kisbetűs karakterek**: Itt adhatja meg a jelszóban kisbetűs karakterek, 0 és 16 karakter között.
      - **Nagybetűs karakterek számát**: Itt adhatja meg a jelszóban nagybetűs karakterek, 0 és 16 karakter között.
      - **Hány karakterből kell állnia nem a levelek**: Itt adhatja meg, nem-betűket (a szóközön kívül bármilyen az ábécé betűit), a jelszót kell rendelkeznie, 0 és 16 karakter között.
      - **Numerikus karakterek számát**: A numerikus karakterek számát adja meg (`1`, `2`, `3`, és így tovább) a jelszót kell rendelkeznie, 0 és 16 karakter között.
      - **Hány szimbólumnak szükséges**: Adja meg, hány szimbólumnak (`&`, `#`, `%`, és így tovább) a jelszót kell rendelkeznie, 0 és 16 karakter között.

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Hány nap elteltével jelszó lejár**: Adja meg a között eltelt napok számát, 1 – 365, elteltével kell megváltoztatni az eszköz jelszavát. Írja be például a jelszó módosításához 60 nap után `60`. Ha a jelszó lejár, a hozzon létre egy új jelszót a rendszer kéri a felhasználókat.
- **Hány jelszó szükséges felhasználói jelszót újra felhasználhatja**: Adja meg a korábban használt jelszavak nem használható fel újra, 1-24 közötti számát. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

- **Titkosítása az eszközön**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Nem konfigurálja ezt a beállítást, mert az Android Enterprise-eszközök megkövetelik a titkosítást kell.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="work-profile"></a>Munkahelyi profil

### <a name="device-health"></a>Device health

- **Feltört eszközök**: Válasszon **blokk** az rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Az eszköz vagy az eszköz fenyegetettségi szintje alatt megkövetelése**: Ez a beállítás használatával igénybe vehet a kockázatelemzést Lookout MTP-megoldásból a megfelelőség feltétele. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a beállítás a legbiztonságosabb, és azt jelenti, hogy az eszköz esetében semmilyen fenyegetés nem. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként fogja értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a lehetőség akkor a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

#### <a name="google-play-protect"></a>A Google Play védelme

- **Google Play-szolgáltatások konfigurálva van**: **Szükséges** , hogy a Google Play szolgáltatások alkalmazás telepítve van és engedélyezett. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Naprakész biztonsági szolgáltató**: **Szükséges** , hogy egy naprakész biztonságszolgáltató képes védeni az eszközöket az ismert biztonsági rések. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **SafetyNet eszközigazolás**: Adja meg a szintű [SafetyNet-igazolás](https://developer.android.com/training/safetynet/attestation.html) a teljesülniük kell. A választható lehetőségek:
  - **Nincs konfigurálva** (alapértelmezett): A beállítás a nem megfelelőség vagy a meg nem felelés értékeli ki.
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

> [!NOTE]
> A vállalati Android-eszköz **alkalmazások fenyegetettségvizsgálata** eszközkonfigurációs szabályzat van. Egy konfigurációs szabályzatot használja, a rendszergazdák a beállítás engedélyezésével az eszközön. Lásd: [Eszközkorlátozásokra vonatkozó beállítások Android Enterprise esetén](device-restrictions-android-for-work.md)

### <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, a nem megfelelő rendszer jelenti. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és majd hozzáférni a szervezet erőforrásaihoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabály, a szervezeti erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak meg kell adnia, forduljon az IT-rendszergazdához. Egy szabályt, hogy az operációs rendszer verziója megváltozott, amíg az eszköz nem lehet hozzáférni a szervezet erőforrásaihoz.

### <a name="system-security"></a>Rendszerbiztonság

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. Ez a beállítás az eszköz szintjén alkalmazzák. Ha csak a munkahelyi profil szintjén jelszót kell, használja a konfigurációs szabályzat. Lásd: [Android Enterprise eszköz konfigurációs beállításai](device-restrictions-android-for-work.md).
- **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak számokat, vagy számokat többféle és más karaktereket tartalmaznia kell. A választható lehetőségek:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok** (alapértelmezett): Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
  - **Komplex numerikus**: Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
  - **Legalább betűk**: Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
  - **Legalább alfanumerikus karakterek**: Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.
  - **Legalább alfanumerikus karakterek és szimbólumok**: Adja meg a **jelszó minimális hossza** a felhasználónak meg kell adnia, 4 és 16 karakter között.

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Hány nap elteltével jelszó lejár**: Válassza ki a hány nap elteltével a jelszó lejár, és a felhasználó egy új jelszót kell létrehozni.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak nem használható fel újra. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

#### <a name="encryption"></a>Encryption

- **Titkosítása az eszközön**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. 

  Nem konfigurálja ezt a beállítást, mert az Android Enterprise-eszközök megkövetelik a titkosítást kell.

#### <a name="device-security"></a>Eszközbiztonság

- **Ismeretlen forrásból származó alkalmazások letiltása**: Válassza ki a **letiltása** eszközök **biztonsági** > **ismeretlen források** források engedélyezve (támogatottak Android 4.0 – Android 7.x.; nem támogatott Android 8.0 és később). Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Alkalmazások közvetlen telepítéséhez az ismeretlen forrásokat engedélyezni kell. Ha nem telepít közvetlenül Android-alkalmazásokat, akkor a megfelelőségi szabályzat engedélyezéséhez adja meg a **Letiltás** beállítást ehhez a funkcióhoz.

  > [!IMPORTANT]
  > Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen forrásból származó alkalmazások letiltása** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem telepít közvetlenül Android-alkalmazásokat az eszközökön.

  Nem kell konfigurálni ezt a beállítást, mivel a vállalati Android-eszköz mindig korlátozzák az ismeretlen forrásból történő telepítést.

- **Céges portál alkalmazás futtatókörnyezetének integritása**: Válasszon **megkövetelése** , győződjön meg róla a vállalati portál alkalmazás megfelel-e az alábbi követelményeknek:

  - Telepítve van hozzá az alapértelmezett futtatókörnyezet
  - Megfelelően alá van írva
  - Nincs hibakeresési módban
  - Ismert forrásból telepítették

  Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

- **USB-hibakeresés letiltása az eszközön**: Válasszon **blokk** megakadályozza, hogy az eszközök az USB-hibakeresés funkció használata. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Nem konfigurálja ezt a beállítást, mert az USB-hibakeresés már le van tiltva a vállalati Android-eszköz kell.

- **Minimális biztonsági javítási szint**: Válassza ki az eszköz minimális biztonsági javítási szintjének. Az ennél régebbi javítási verzióval rendelkező eszközök nem megfelelőek. Az adatokat a következő formátumban kell megadni: *ÉÉÉÉ-HH-NN*.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések

- [Nem megfelelő eszközök műveletek hozzáadása a](actions-for-noncompliance.md) és [használja a szűrő házirendek hatókörcímkék](scope-tags.md).
- [Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).
- Tekintse meg a [megfelelőségi szabályzat beállításai androidhoz](compliance-policy-create-android.md) eszközök.

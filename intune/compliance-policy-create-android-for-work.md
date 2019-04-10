---
title: Android Enterprise megfelelőségi beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Használhatja a Microsoft Intune-ban a vállalati Android-eszköz megfelelőségének beállításakor minden beállítások listájának megtekintéséhez. Jelszószabályok beállítása egy minimális és maximális operációsrendszer-verzió, adott alkalmazásokra korlátozhatja, és burkolóalkalmazások újbóli használata jelszó és egyéb megakadályozása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
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
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423560"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android Enterprise-beállítások eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és konfigurálhat vállalati Android-eszköz Intune-ban a különböző megfelelőségi beállításait ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat megjelölése nem megfelelőként rootolt (feltört) eszközöket, egy megengedett kockázati szintet, a Google Play Protect, és több.

Ez a funkció az alábbiakra vonatkozik:

- Vállalati Android

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform**válassza **Android Enterprise**.

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Válasszon **blokk** az rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Az eszköz vagy az eszköz fenyegetettségi szintje alatt megkövetelése**: Ez a beállítás használatával igénybe vehet a kockázatelemzést Lookout MTP-megoldásból a megfelelőség feltétele. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a beállítás a legbiztonságosabb, és azt jelenti, hogy az eszköz esetében semmilyen fenyegetés nem. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként fogja értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a lehetőség akkor a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

### <a name="google-play-protect"></a>Google Play védelme

- **Google Play-szolgáltatások konfigurálva van**: **Szükséges** , hogy a Google Play szolgáltatások alkalmazás telepítve van és engedélyezett. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Naprakész biztonsági szolgáltató**: **Szükséges** , hogy egy naprakész biztonságszolgáltató képes védeni az eszközöket az ismert biztonsági rések. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **SafetyNet eszközigazolás**: Adja meg a szintű [SafetyNet-igazolás](https://developer.android.com/training/safetynet/attestation.html) a teljesülniük kell. A választható lehetőségek:
  - **Nincs konfigurálva** (alapértelmezett): A beállítás a nem megfelelőség vagy a meg nem felelés értékeli ki.
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

> [!NOTE]
> A vállalati Android-eszköz **alkalmazások fenyegetettségvizsgálata** eszközkonfigurációs szabályzat van. Egy konfigurációs szabályzatot használja, a rendszergazdák a beállítás engedélyezésével az eszközön. Lásd: [Eszközkorlátozásokra vonatkozó beállítások Android Enterprise esetén](device-restrictions-android-for-work.md)

## <a name="device-properties-settings"></a>Eszköztulajdonságok beállításai

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ezután pedig hozzáfér a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabály, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az eszköz operációs rendszerének verzióját is.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. Ez a beállítás az eszköz szintjén alkalmazzák. Ha csak a munkahelyi profil szintjén jelszót kell, használja a konfigurációs szabályzat. Lásd: [Android Enterprise eszköz konfigurációs beállításai](device-restrictions-android-for-work.md).
- **Jelszó minimális hossza**: Adja meg a számjegyek vagy karakterek rendelkeznie kell a jelszó minimális számát.
- **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak számokat, vagy számokat többféle és más karaktereket tartalmaznia kell. A választható lehetőségek:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok** (alapértelmezett)
  - **Komplex numerikus**
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak nem használható fel újra. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

### <a name="encryption"></a>Encryption

- **Titkosítása az eszközön**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. 

  Nem konfigurálja ezt a beállítást, mert az Android Enterprise-eszközök megkövetelik a titkosítást kell.

### <a name="device-security"></a>Eszközbiztonság

- **Ismeretlen forrásból származó alkalmazások letiltása**: Válassza ki a **blokk** "Biztonság > Ismeretlen források" eszközök engedélyezve van a forrásból (Android 4.0 – Android 7.x rendszeren támogatott; nem támogatott Android 8.0 és újabb verziók). Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

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

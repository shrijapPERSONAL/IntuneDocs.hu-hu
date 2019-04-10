---
title: iOS-es megfelelőségi beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Használhatja a Microsoft Intune-ban az iOS-eszközökre vonatkozó megfelelőségi beállításakor minden beállítások listájának megtekintéséhez. Szükséges egy e-mailt, ellenőrizze a függetlenített vagy feltört eszközökön, a minimális és maximális operációsrendszer-verzió beállítása, jelszókorlátozásoknak bármely, beleértve a jelszó hosszának és az eszköz inaktivitási, korlátozhatja az alkalmazások és más.
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
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec071622a2e0d49068864f8bfb47954f54c8ba4
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423611"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal iOS-beállítások

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk felsorolja és ismerteti a különböző megfelelőségi beállítások az Intune-ban iOS-eszközökön konfigurálható. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat egy e-mailt igényel, megjelölése nem megfelelőként rootolt (feltört) eszközöket, állítsa be egy megengedett kockázati szint, állítsa be a jelszavakat lejár, és több.

Ez a funkció az alábbiakra vonatkozik:

- iOS

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform** beállításnál adja meg az **iOS** értéket.

## <a name="email"></a>E-mail

- **Mobileszközök számára a felügyelt e-mail-profil**: Ha a beállítása **megkövetelése**, az Intune által felügyelt e-mail-profil nem rendelkező eszközök nem megfelelőnek minősülnek. Egy eszköz rendelkezhet felügyelt e-mail-profil nincs megfelelő célcsoportban, vagy ha a felhasználó manuálisan állítsa be az e-mail fiókot az eszközön. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.

  Az eszköz nem kompatibilis a következő esetekben tekinthető meg:

  - Az e-mail-profil hozzá van rendelve egy másik felhasználói csoportot, mint a megfelelőségi házirend által célzott felhasználói csoportra.
  - A felhasználó már beállított egy az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot. Az Intune nem írhatja felül a felhasználó által konfigurált profil, és az Intune nem tudja kezelni azt. Meg kell felelnie, hogy a végfelhasználónak el kell távolítania a meglévő e-mail beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.

- **Válassza ki az Intune-ban felügyelni kívánt levelezési profil**: Ha a **az Intune által felügyelt E-mail fiók** beállítás van kiválasztva, válassza a **kiválasztása** , adja meg az Intune levelezési profillal. Az e-mail-profil léteznie kell az eszközön.

E-mail profilokkal kapcsolatos részletekért lásd: [munkahelyi e-mail-cím e-mail-profilok használatával az Intune-nal való hozzáférés konfigurálása](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Válasszon **blokk** az rootolt (jailbreakelt) eszközök nem megfelelőként való megjelöléséhez. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához.
- **Az eszköz vagy az eszköz fenyegetettségi szintje alatt megkövetelése** (iOS 8.0 és újabb): Ez a beállítás segítségével a megfelelési feltételként kockázatbecslés igénybe vehet. Ha a **Nincs konfigurálva** (alapértelmezett) lehetőséget választja, a rendszer ezt a beállítást nem veszi figyelembe a megfelelőség, vagy meg nem felelőség megállapításához. A beállítás használatához válassza ki a megengedett kockázati szintet:
  - **Védett**: Ez a beállítás a legbiztonságosabb, és azt jelenti, hogy az eszköz esetében semmilyen fenyegetés nem. Az eszköz bármilyen szintű fenyegetés észlelése esetén nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz fennálló fenyegetések alacsony vagy közepes szintűek. Az eszköz magas szintű fenyegetés észlelése esetén azt állapította nem kompatibilis.
  - **Magas**: Ez a lehetőség akkor a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Operációs rendszer szükséges minimális verziója** (iOS 8.0 és újabb): Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, a nem megfelelő rendszer jelenti. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt választhat. Ezt követően hozzáférhet a munkahelyi erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió** (iOS 8.0 és újabb): Ha egy eszközön operációsrendszer-verziónál újabb fut, az a szabály, a szervezeti erőforrásokhoz való hozzáférés le van tiltva. A végfelhasználónak meg kell adnia, forduljon az IT-rendszergazdához. Az eszköz nem fér hozzá a munkahelyi erőforrásokhoz, amíg egy szabályt, hogy az operációs rendszer verzióját.
- **Minimális operációsrendszer-verziót hozzon létre** (iOS 8.0 és újabb): Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a minimális megengedett buildszám az eszközön.
- **Maximális operációsrendszer-verziót hozzon létre** (iOS 8.0 és újabb): Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a maximális megengedett buildszám az eszközön.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Windows 10

> [!NOTE]
> Miután megfelelőségi vagy konfigurációs szabályzatot alkalmazott egy iOS-eszközre, a felhasználóktól 15 percenként egy PIN-kódot kér a rendszer. A kérések mindaddig megjelennek, amíg a felhasználó meg nem ad egy PIN-kódot.

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. A jelszót használó iOS-eszközöket titkosítja a rendszer.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).
- **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg például a speciális karakterek minimális számát `&`, `#`, `%`, `!`, és így tovább, a jelszót kell működnie.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.

### <a name="device-security"></a>Eszközbiztonság

- **Korlátozott alkalmazások**: Alkalmazásokat úgy korlátozhat, hogy kötegazonosítójukat hozzáadja a szabályzathoz. Ha egy eszköz rendelkezik az alkalmazás telepítve van, az eszköz nem megfelelőként van megjelölve.

  - **Alkalmazásnév**: Adjon meg egy felhasználóbarát nevet segítségével azonosíthatja a kötegazonosítót.
  - **Alkalmazásköteg-azonosító**: Adja meg a az alkalmazás szolgáltatója által hozzárendelt egyedi csomagazonosítót. Az alkalmazáscsomag-Azonosítójának megkereséséhez lásd: [az alkalmazáscsomag-Azonosítójának megkeresése az iOS-alkalmazás](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (megnyílik egy másik Microsoft-webhely).  

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések

- [Nem megfelelő eszközök műveletek hozzáadása a](actions-for-noncompliance.md) és [használja a szűrő házirendek hatókörcímkék](scope-tags.md).
- [Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).
- Tekintse meg a [MacOS rendszerű megfelelőségi szabályzat beállításai](compliance-policy-create-mac-os.md) eszközök.

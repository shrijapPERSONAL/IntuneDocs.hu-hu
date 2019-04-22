---
title: macOS megfelelőségi beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a Microsoft Intune-ban a macOS-eszközökre vonatkozó megfelelőségi beállításakor használható beállításokról. Az Apple rendszerintegritás-védelem megkövetelése, jelszókorlátozásoknak, a tűzfal megkövetelése, lehetővé teszi a forgalomirányító és egyéb.
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
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3224e7400ad56f971488aba53bb073a0d33bb9d
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896660"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal macOS-beállítások

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk felsorolja és ismerteti a különböző megfelelőségi beállítások az Intune-ban macOS-eszközökön konfigurálható. A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások használatával állítsa be a minimális vagy maximális operációs rendszer verziója, beállítása jelszavakat lejár és további.

Ez a funkció az alábbiakra vonatkozik:

- macOS

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform** beállításnál adja meg a **macOS** értéket.

## <a name="device-health"></a>Eszközállapot

- **Rendszerintegritás-védelem megkövetelése**: **Szükséges** szeretné, hogy a macOS-eszközök [rendszerintegritás-védelem](https://support.apple.com/HT204899) (megnyílik az Apple webhelyén) engedélyezve van. Ha a beállítása **nincs konfigurálva** (alapértelmezett), ez a beállítás nem kerül kiértékelésre, megfelelőségi vagy meg nem felelés.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabályban megadott, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.
- **Minimális operációsrendszer-verziót hozzon létre**: Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a minimális megengedett buildszám az eszközön.
- **Maximális operációsrendszer-verziót hozzon létre**: Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a maximális megengedett buildszám az eszközön.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó típusa**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).
- **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg például a speciális karakterek minimális számát `&`, `#`, `%`, `!`, és így tovább, a jelszót kell működnie.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.

    > [!IMPORTANT]
    > Ha macOS-eszközön megváltozik a jelszóra vonatkozó követelmény, akkor az csak akkor lép érvénybe, amikor a felhasználó legközelebb megváltoztatja jelszavát. Ha például a jelszó kötelező minimális hosszát 8 számjegyűre állítja át, és a macOS-eszköz jelenlegi jelszava 6 számjegyű, az eszköz egészen addig megfelelőnek minősül, amíg a felhasználó legközelebb meg nem változtatja az eszköz jelszavát.

### <a name="encryption"></a>Encryption

- **Egy eszközön való adattárolás titkosításának**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához.

### <a name="device-security"></a>Eszközbiztonság

A tűzfal a jogosulatlan hálózati hozzáférés ellen védi az eszközöket. A tűzfal használatával a kapcsolatok alkalmazásonként szabályozhatók. 

- **Tűzfal**: Válassza ki **engedélyezése** eszközök jogosulatlan hozzáférés elleni védelme érdekében. A funkció engedélyezése után kezelni tudja a bejövő internetes kapcsolatokat, és használhatja a rejtett üzemmódot. Ha **Nincs konfigurálva** (alapértelmezés), akkor a tűzfal kikapcsolva marad, a hálózati forgalom pedig engedélyezve lesz (nem lesz letiltva).
- **A bejövő kapcsolatok**: **Blokk** , kivéve az összes bejövő hálózati kapcsolatok olyan alapvető internet-szolgáltatások, például a DHCP, Bonjour és az IPSec. Ez a beállítás letiltja a megosztási szolgáltatásokat, például az képernyőmegosztást, távelérési, iTunes zene megosztását is. Ha **Nincs konfigurálva** (alapértelmezés), akkor minden bejövő kapcsolat és megosztási szolgáltatás engedélyezve van.
- **Rejtett üzemmód**: **Engedélyezése** rejtett üzemmód kérelmekre, a rosszindulatú felhasználók teszik lehetővé az eszközök megakadályozása. Engedélyezése esetén az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre. Ha **Nincs konfigurálva** (alapértelmezés), akkor a rejtett üzemmód ki van kapcsolva.

### <a name="gatekeeper"></a>Forgalomirányító

További információkért lásd: [macOS rendszeren a forgalomirányító](https://support.apple.com/HT202491) (az Apple webhelyén nyílik meg).

**Alkalmazások ezen helyekről való letöltésének engedélyezése**: Lehetővé teszi a támogatott alkalmazások telepítését az eszközök különböző helyekről. Az Ön helybeállításai:

- **Nincs konfigurálva**: Default (Alapértelmezett): A forgalomirányító beállítást nem befolyásolja a megfelelőség vagy a meg nem felelés. 
- **Mac App Store**: Csak telepítse a Mac app store-alkalmazások. Nem lehet harmadik felektől és azonosított fejlesztőktől származó alkalmazásokat telepíteni. Ha egy felhasználó azt választja, hogy a forgalomirányító a Mac App Store-on kívüli alkalmazásokat telepítsen, akkor az eszköz nem megfelelőnek fog számítani.
- **Mac App Store és azonosított fejlesztők**: A Mac app store és azonosított fejlesztők alkalmazásokat telepíteni. A macOS ellenőrzi a fejlesztők identitását, és néhány egyéb ellenőrzést is végez az alkalmazás integritásának igazolásához. Ha egy felhasználó azt választja, hogy a forgalomirányító a megadott beállításokon kívüli alkalmazásokat telepítsen, akkor az eszköz nem megfelelőnek fog számítani.
- **Bárhol**: Alkalmazások telepíthetők a bárhol és bármilyen fejlesztőnek. Ez a beállítás a legkevésbé biztonságos.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="next-steps"></a>További lépések

- [Nem megfelelő eszközök műveletek hozzáadása a](actions-for-noncompliance.md) és [használja a szűrő házirendek hatókörcímkék](scope-tags.md).
- [Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).
- Tekintse meg a [megfelelőségi szabályzat beállításai iOS-es](compliance-policy-create-ios.md) eszközök.
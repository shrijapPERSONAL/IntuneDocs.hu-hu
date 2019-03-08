---
title: macOS-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: macOS-eszközök Microsoft Intune eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása a rendszerintegritás-védelem használatához, az operációs rendszer minimális és maximális verziójának megadásához, jelszókövetelmények kiválasztásához és adattárolók titkosításához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
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
ms.openlocfilehash: 21eca671d40f1ee2f2f9176a272cab5754140a26
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566607"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>macOS-es eszközök megfelelőségi szabályzatainak hozzáadása az Intune-nal

Az Intune macOS-eszközmegfelelőségi szabályzataival megszabhatja a macOS-eszközök megfelelőségéhez kötelezően szükséges szabályokat és beállításokat. Az eszközmegfelelőségi szabályzatokat a feltételes hozzáféréssel használva engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. Az Intune Azure Portalon minden platformhoz létrehozhat megfelelőségi szabályzatokat. A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják:

---------------------------

| Házirend-beállítás | macOS 10.11 és újabb verziók |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva |   
| **Eszköztitkosítás** | Kijavítva (PIN-kód beállításával) |
| **E-mail profil** | Karanténba helyezve |
|**Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |

---------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. Például a felhasználó köteles lesz PIN-kódot beállítani.

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. A **Platform** beállításnál adja meg a **macOS** értéket. 
5. Válassza a **beállítások konfigurálása**, és adja meg a **Eszközállapot**, **eszköztulajdonságok**, és **rendszerbiztonság** ismertetett beállítások Ez a cikk. Ha elkészült, válassza az **OK** majd a **Létrehozás** lehetőséget.

## <a name="device-health"></a>Eszközállapot

- **Rendszerintegritás-védelem megkövetelése**: **Szükséges** szeretné, hogy a macOS-eszközök [rendszerintegritás-védelem](https://support.apple.com/HT204899) engedélyezve van.

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
- **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg a speciális karakterek minimális számát (&, #, %,! stb) kell szerepelnie a jelszóban.

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

- **Tűzfal**: **Engedélyezése** eszközök jogosulatlan hozzáférés elleni védelme érdekében. A funkció engedélyezése után kezelni tudja a bejövő internetes kapcsolatokat, és használhatja a rejtett üzemmódot. Ha **Nincs konfigurálva** (alapértelmezés), akkor a tűzfal kikapcsolva marad, a hálózati forgalom pedig engedélyezve lesz (nem lesz letiltva).
- **A bejövő kapcsolatok**: **Blokk** az összes bejövő hálózati kapcsolatok, kivéve az alapvető internetes szolgáltatások, például a DHCP, Bonjour és az IPSec szükséges. Ez a beállítás letilt minden megosztási szolgáltatást, többek között a képernyőmegosztást, a távelérést, az iTunes-zenemegosztást is. Ha **Nincs konfigurálva** (alapértelmezés), akkor minden bejövő kapcsolat és megosztási szolgáltatás engedélyezve van. 
- **Rejtett üzemmód**: **Engedélyezése** rejtett üzemmód megakadályozza, hogy az eszköz válaszol a kérelmekre, a rosszindulatú felhasználók teszik lehetővé. Engedélyezése esetén az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre. Ha **Nincs konfigurálva** (alapértelmezés), akkor a rejtett üzemmód ki van kapcsolva.

### <a name="gatekeeper"></a>Forgalomirányító

**Alkalmazások ezen helyekről való letöltésének engedélyezése**: Lehetővé teszi a támogatott alkalmazások telepítését az eszközök különböző helyekről. Az Ön helybeállításai:

- **Nincs konfigurálva**: Default (Alapértelmezett): A forgalomirányító beállítást nem befolyásolja a megfelelőség vagy a meg nem felelés. 
- **Mac App Store**: Csak telepítse a Mac app store-alkalmazások. Nem lehet harmadik felektől és azonosított fejlesztőktől származó alkalmazásokat telepíteni. Ha egy felhasználó azt választja, hogy a forgalomirányító a Mac App Store-on kívüli alkalmazásokat telepítsen, akkor az eszköz nem megfelelőnek fog számítani.
- **Mac App Store és azonosított fejlesztők**: A Mac app store és azonosított fejlesztők alkalmazásokat telepíteni. A macOS ellenőrzi a fejlesztők identitását, és néhány egyéb ellenőrzést is végez az alkalmazás integritásának igazolásához. Ha egy felhasználó azt választja, hogy a forgalomirányító a megadott beállításokon kívüli alkalmazásokat telepítsen, akkor az eszköz nem megfelelőnek fog számítani.
- **Bárhol**: Alkalmazások telepíthetők a bárhol és bármilyen fejlesztőnek. Ez a beállítás a legkevésbé biztonságos.

Az Apple dokumentációjában elérhető további részletekért olvassa el a [forgalomirányítóról szóló cikket a macOS weblapján](https://support.apple.com/HT202491).

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

> [!TIP]
> Az eszközök alapértelmezés szerint nyolc óránként ellenőrzik a megfelelőséget. Az eljárást azonban a felhasználó is kikényszerítheti az Intune Céges portál alkalmazáson keresztül.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)

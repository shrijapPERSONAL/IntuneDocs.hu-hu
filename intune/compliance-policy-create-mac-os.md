---
title: macOS-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: macOS-eszközök Microsoft Intune eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása a rendszerintegritás-védelem használatához, az operációs rendszer minimális és maximális verziójának megadásához, jelszókövetelmények kiválasztásához és adattárolók titkosításához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6bbb09944db602b4b5a70c89e8089b1692c45223
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321441"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>macOS-es eszközök megfelelőségi szabályzatainak hozzáadása az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
5. A **Platform** beállításnál adja meg a **macOS** értéket. Válassza a **Beállítások konfigurálása** lehetőséget az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításainak megadásához. Ha elkészült, válassza az **OK** majd a **Létrehozás** lehetőséget.

## <a name="device-health"></a>Eszközállapot

- **Rendszerintegritás-védelem megkövetelése**: macOS-es eszközein **kötelező** engedélyezni a [rendszerintegritás-védelmet](https://support.apple.com/HT204899).

## <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez.
- **Egyszerű jelszavak**: Ha nem szeretné engedélyezni, hogy a felhasználók olyan egyszerű jelszavakat használhassanak, mint az **1234** vagy az **1111**, válassza a **Tiltás** lehetőséget. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Meghatározhatja a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó típusa**: Megadható, hogy a jelszó csak **számjegy** karaktereket vagy számjegy és más (**Alfanumerikus**) karaktereket vegyesen tartalmazzon.
- **Nem alfanumerikus karakterek száma a jelszóban**: Megadhatja, hogy hány speciális karakternek (például &, #, %, ! stb.) kell szerepelnie a jelszóban.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány korábbi jelszó ne legyen újra felhasználható.

    > [!IMPORTANT]
    > Ha macOS-eszközön megváltozik a jelszóra vonatkozó követelmény, akkor az csak akkor lép érvénybe, amikor a felhasználó legközelebb megváltoztatja jelszavát. Ha például a jelszó kötelező minimális hosszát 8 számjegyűre állítja át, és a macOS-eszköz jelenlegi jelszava 6 számjegyű, az eszköz egészen addig megfelelőnek minősül, amíg a felhasználó legközelebb meg nem változtatja az eszköz jelszavát.

### <a name="encryption"></a>Encryption

- **Adattároló titkosítása az eszközön**: A **Kötelező** lehetőséget választva az adattárolók titkosítva lesznek az eszközökön.

### <a name="device-security"></a>Eszközbiztonság
A tűzfal a jogosulatlan hálózati hozzáférés ellen védi az eszközöket. A tűzfal használatával a kapcsolatok alkalmazásonként szabályozhatók. 

- **Tűzfal**: **Engedélyezve** hozzájárul az eszköz jogosulatlan hozzáférés elleni védelméhez. A funkció engedélyezése után kezelni tudja a bejövő internetes kapcsolatokat, és használhatja a rejtett üzemmódot. Ha **Nincs konfigurálva** (alapértelmezés), akkor a tűzfal kikapcsolva marad, a hálózati forgalom pedig engedélyezve lesz (nem lesz letiltva).
- **Bejövő kapcsolatok**: **Letilthatja** az összes bejövő hálózati kapcsolatot az olyan alapvető internetes szolgáltatások kivételével, mint a DHCP, a Bonjour vagy az IPSec. Ez a beállítás letilt minden megosztási szolgáltatást, többek között a képernyőmegosztást, a távelérést, az iTunes-zenemegosztást is. Ha **Nincs konfigurálva** (alapértelmezés), akkor minden bejövő kapcsolat és megosztási szolgáltatás engedélyezve van. 
- **Rejtett üzemmód**: a rejtett üzemmód **engedélyezésével** megakadályozhatja, hogy a számítógép válaszoljon a bejövő kérelmekre, amelyeket rosszindulatú felhasználók is kezdeményezhetnek. Engedélyezése esetén az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre. Ha **Nincs konfigurálva** (alapértelmezés), akkor a rejtett üzemmód ki van kapcsolva.

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

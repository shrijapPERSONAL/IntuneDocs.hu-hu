---
title: Eszközmegfelelőségi szabályzatok figyelése az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az eszközmegfelelőségi irányítópulttal figyelheti az eszközmegfelelőségeket, jelentéseket tekinthet meg, valamint megtekintheti a szabályzatonkénti és beállításonkénti eszközmegfelelőségeket.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ce117f21c1ad78c2c977466398ce6d30989cc6a
ms.sourcegitcommit: a2bad7465422b98eb3c10f03dc5a24fd99cee78d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041296"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune-eszközmegfelelőségi szabályzatok figyelése

A megfelelőségi jelentések segítenek az eszközmegfelelőség áttekintésében, és a megfelelőséggel kapcsolatos problémák elhárításában a vállalatánál. Ezeknek a jelentéseknek a használatával a következőkről tekinthet meg információkat:

- Az eszközök összesített megfelelőségi állapota
- Az egyes beállítások megfelelőségi állapota
- Az egyes szabályzatok megfelelőségi állapota
- Egy eszköz részletes vizsgálatával megtekintheti az arra vonatkozó beállításokat és szabályzatokat

## <a name="open-the-compliance-dashboard"></a>A megfelelőségi irányítópult megnyitása

Nyissa meg az **Intune Eszközmegfelelőségi irányítópultját**:

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Válassza az **Eszközmegfelelőség** > **Áttekintés** elemet. Megnyílik az **Eszközmegfelelőségi irányítópult**.

> [!IMPORTANT]
> Az eszközmegfelelőségi szabályzatok csak akkor alkalmazhatók az eszközökre, ha azok regisztrálva vannak az Intune-ban.

## <a name="dashboard-overview"></a>Az irányítópult áttekintése

Az irányítópult megnyitásakor átfogó képet kap az összes megfelelőségi jelentésről. Ezekben a jelentésekben a következőket ellenőrizheti:

- Összesített eszközmegfelelőség
- Szabályzatok szerinti eszközmegfelelőség
- Beállítások szerinti eszközmegfelelőség
- Eszközvédelem állapota
- Fenyegetésfigyelő ügynök állapota

![Irányítópult képe az eszközmegfelelőségi irányítópulttal és a különböző jelentésekkel](./media/compliance-policy-monitor/idc-1.png)

A jelentések részletes vizsgálata során láthatja az adott eszközre vonatkozó megfelelőségi szabályzatokat és beállításokat is, köztük az egyes beállítások megfelelőségi állapotát.

### <a name="device-compliance-status-report"></a>Eszközmegfelelőségi állapotjelentés

A diagram megmutatja az összes Intune-ban regisztrált eszköz megfelelőségi állapotát. Az eszköz megfelelőségi állapotai két külön adatbázis tartják: Az Intune és az Azure Active Directoryban. 

> [!IMPORTANT]
> Intune az eszköz bejelentkezési ütemezés az összes megfelelőségi értékelést követi az eszközön. [További információ az eszköz bejelentkezési ütemezés](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

A különböző eszközmegfelelőségi szabályzatállapotok leírása:

- **Megfelelő**: Az eszköz egy vagy több eszközmegfelelőségi szabályzat beállításai sikeresen alkalmazva.

- **Türelmi időszak:** Az eszköz célként az egy vagy több eszközmegfelelőségi szabályzat beállításai. A felhasználó azonban még nem alkalmazta a szabályzatokat. Ez azt jelenti, hogy az eszköz nem megfelelő, de a rendszergazda által meghatározott türelmi időszakban van.

  - További információ a [nem megfelelő eszközökre alkalmazható műveletekről](actions-for-noncompliance.md).

- **Nem értékelt**: Kezdeti állapot azon újonnan regisztrált eszközök számára. Lehetséges okokat, ezt állapota a következők:

  - Eszközök, amelyek nincsenek hozzárendelve megfelelőségi szabályzat, és nem rendelkezik egy eseményindító a megfelelőség ellenőrzése
  - Eszközök, amelyek jelentkeztek be, mert a megfelelőségi szabályzat utolsó frissítés
  - Az eszköz nincs hozzárendelve egy adott felhasználó kapcsán, mint például:
    - iOS-eszközök az Apple eszköz beléptetési Program (DEP) keresztül vásárolt, amelyekhez nincs felhasználói affinitás
    - Androidos teljes képernyős vagy dedikált vállalati Android-eszköz
  - Egy eszközregisztráció-kezelői (DEM-) fiók-ban regisztrált eszközök

- **Nem megfelelő:** Az eszköz nem sikerült a alkalmazni egy vagy több eszközmegfelelőségi szabályzat beállításai. Lehetséges, hogy a felhasználó nem a szabályzatoknak megfelelően járt el.

- **Az eszköz nincs szinkronizálva:** Az eszköz nem sikerült jelenteni jelentette az eszközmegfelelőségi szabályzat állapotát, mert a következő okok egyike miatt:

  - **Ismeretlen**: Az eszköz offline állapotban van, vagy nem sikerült kapcsolatba lépniük az Intune-ban vagy Azure ad-ben más okok miatt.

  - **Hiba**: Az eszköz nem tudott kommunikálni az Intune és az Azure ad-ben, és üzenetben megkapta a hiba okát.

> [!IMPORTANT]
> A jelentésben a **Megfelelő** gyűjtőben szerepelnek azok az eszközök, amelyek regisztrálva vannak az Intune-ban, de nem vonatkozik rájuk eszközmegfelelőségi szabályzat.

#### <a name="drill-down-for-more-details"></a>További részletezés

Válasszon egy állapotot az **Eszközmegfelelőségi állapot** diagramon. Válassza például a **Nem megfelelő** állapotot:

![A nem megfelelő állapot kiválasztása](./media/compliance-policy-monitor/select-not-compliant-status.png)

Ezzel további részleteket jelenít meg az ebben az állapotban lévő eszközökről, köztük sok más mellett az operációsrendszer-platformot és az utolsó bejelentkezés időpontját. 

![Irányítópult képe az adott állapotú eszközöz további részleteivel](./media/compliance-policy-monitor/drill-down-details.png)

Ha egy adott felhasználó tulajdonában lévő összes eszközt látni szeretné, a felhasználó e-mail-címének begépelésével szűrni tudja a diagramot tartalmazó jelentést.

#### <a name="filter-and-columns"></a>Szűrő és oszlopok

![A diagramon ábrázolt eredmények módosítása a Szűrő és az Oszlopok lehetőség választásával](./media/compliance-policy-monitor/filter-columns.png)

A **Szűrő** gombot választva megnyílik a további lehetőségeket, köztük a megfelelőségi állapotot és a feltört eszközöket tartalmazó beúszó szűrőpanel. Az eredmények frissítéséhez válassza a Szűrő panelen az **Alkalmaz** lehetőséget.

A diagram-kimenet oszlopainak hozzáadásához és eltávolításához válassza az **Oszlopok** lehetőséget. Az **Egyszerű felhasználónév** például megmutathatja az eszközön regisztrált e-mail-címet. Az eredmények frissítéséhez válassza az Oszlopok panelen az **Alkalmaz** lehetőséget.

#### <a name="device-details"></a>Eszközadatok

Jelöljön ki egy eszközt a diagramon, majd válassza az **Eszközmegfelelőség** lehetőséget:

![Egy adott eszköz, majd az Eszközmegfelelőség kiválasztása az alkalmazott megfelelőségi szabályzatok megtekintéséhez](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Itt további információt talál az adott eszközön alkalmazott eszközmegfelelőségi szabályzat beállításairól. Az adott szabályzat kijelölésével megjelenik a szabályzat összes beállítása.

### <a name="devices-without-compliance-policy"></a>Megfelelőségi szabályzat nélküli eszközök
Az **Eszközmegfelelőség** > **Áttekintés** alatti jelentés azokat az eszközöket is megmutatja, amelyekhez nincs eszközmegfelelőségi szabályzat rendelve:

![Megfelelőségi szabályzat nélküli eszközök megtekintése](./media/compliance-policy-monitor/devices-without-policies.png)

Amikor kijelöli a csempét, minden megfelelőségi szabályzat nélküli eszköz megjelenik. Látható az eszköz felhasználója, a szabályzat érvénybe léptetésének állapota és az eszköz típusa is.

#### <a name="what-you-need-to-know"></a>Amit még tudnia kell

- A **Hozzárendelt megfelelőségi szabályzat nélküli eszközök megjelölése mint...** biztonsági beállítás mellett fontos azonosítani a megfelelőségi szabályzat nélküli eszközöket. Ezt követően hozzájuk rendelhet legalább egy megfelelőségi szabályzatot.

  Ez a biztonsági beállítás az Intune portálon konfigurálható. Válassza az **Eszközmegfelelőség** > **Megfelelőségi szabályzat beállításai** lehetőséget. A **Hozzárendelt megfelelőségi szabályzat nélküli eszközök megjelölése mint...** értékeként **Megfelelő** vagy **Nem megfelelő** állítható be. 

  Minderről többet olvashat a [Biztonsági fejlesztések az Intune szolgáltatásban](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/) című cikkben.

- Az olyan felhasználók, akikhez bármilyen megfelelőségi szabályzat van rendelve, nem jelennek meg a jelentésben, tekintet nélkül az eszközplatformra. Így például ha Windows megfelelőségi szabályzat van egy androidos eszközzel rendelkező felhasználóhoz rendelve, akkor az eszköz nem jelenik meg a jelentésben. Az Intune azonban nem megfelelőként kezeli ezt az androidos eszközt. A problémák elkerülése érdekében ajánlott külön szabályzatot létrehozni minden eszközplatformhoz és azokat minden felhasználóra érvényesíteni.

### <a name="per-policy-device-compliance-report"></a>Szabályzatok szerinti eszközmegfelelőségi jelentés

Az **Eszközmegfelelőség** > **Szabályzatoknak való megfelelőség** jelentésben láthatja a szabályzatokat, valamint a megfelelő és nem megfelelő eszközök számát. 

![A szabályzatok listája és az egyes szabályzatoknak megfelelő és nem megfelelő eszközök száma](./media/compliance-policy-monitor/idc-8.png)

Egy adott szabályzat kijelölésével megtekinthető a **megfelelőségi állapot**, a **felhasználói e-mail-alias**, az **eszköztípus** és a **hely** minden olyan eszközhöz, amelyre ez a megfelelőségi szabályzat vonatkozik.

## <a name="setting-compliance-report"></a>Beállításoknak való megfelelőségi jelentés

Az **Eszközmegfelelőség** > **Beállításoknak való megfelelőség** jelentés megfelelőségi beállításonként mutatja meg az egyes megfelelőségi állapotban lévő eszközök összesített számát. Bemutatja az összes megfelelőségi szabályzathoz tartozó eszközmegfelelőségi szabályzatbeállításokat, a platformokat, amelyekre a szabályzatbeállítások alkalmazva lettek és a nem megfelelő eszközök számát.

![A különböző szabályzatok összes beállításának listája](./media/compliance-policy-monitor/idc-10.png)

Egy adott beállítás kijelölésével megtekinthető a **megfelelőségi állapot**, a **felhasználói e-mail-alias**, az **eszköztípus** és a **hely** minden olyan eszközhöz, amelyre ez a beállítás vonatkozik.

> [!NOTE]
> Előfordulhat, hogy az Azure AD-hoz csatlakoztatott Windows 10-eszközök a Rendszerfiókot nem megfelelő felhasználóként érzékelik. Ez normális működés, amely az általános eszközmegfelelőséget nem befolyásolja. 

## <a name="view-status-of-device-policies"></a>Eszközszabályzatok állapotának megtekintése

A szabályzatok különböző állapotait platformonként ellenőrizheti. Tegyük fel, hogy van egy macOS-es megfelelőségi szabályzata. Szeretné megtekinteni a szabályzat által érintett eszközöket, és megtudni, hogy vannak-e ütközések vagy hibák.

Ezt a funkciót tartalmazza az eszköz állapotjelentése:

1. Válassza az **Eszközmegfelelőség** > **Szabályzatok** elemet. Megjelenik a szabályzatok listája, amely tartalmazza a platformot, hogy hozzá van-e rendelve a szabályzat, és további részleteket.
2. Válasszon ki egy szabályzatot > **Áttekintés**. Ebben a nézetben a szabályzat-hozzárendelés a következő állapotokat tartalmazza:

    - Sikeres: Szabályzat érvényes
    - Hiba: Nem sikerült alkalmazni a szabályzatot. Az üzenethez általában egy hibakód is tartozik, amely a hiba ismertetésére hivatkozik. 
    - Ütközés: Két beállítás ugyanazon az eszközön érvénybe lépnek, és az Intune nem rendezhető, az ütközést. Rendszergazdai ellenőrzés szükséges.
    - Függőben: Az eszköz még nem jelentkezett be az Intune-ban még megkapja a szabályzatot. 
    - Not applicable: Az eszköz nem megkapja a szabályzatot. A szabályzat például egy, az iOS 11.1-re vonatkozó beállítást frissít, az eszköz azonban az iOS 10-et használja. 

3. A szabályzatot használó eszközökön a részletek megtekintéséhez válassza ki a állapotok egyikét. Válassza például a **Sikeres** elemet. A következő ablakban megjelennek az eszköz adatai, például az eszköz neve és az üzembe helyezési állapot.

## <a name="how-intune-resolves-policy-conflicts"></a>Hogyan oldja fel az Intune az szabályzatütközéseket?
Szabályzatütközésről akkor beszélünk, hogy egy eszközre több Intune-szabályzat vonatkozik. Ha a szabályzatbeállítások közt átfedés van, az Intune a következő szabályok alkalmazásával oldja fel az ütközéseket:

- Ha az ütköző beállítások egy Intune konfigurációs szabályzatból és egy megfelelőségi szabályzatból kerülnek ki, akkor a megfelelőségi szabályzat beállításai érvényesülnek a konfigurációs szabályzatéival szemben. Ez még akkor is így van, ha a konfigurációs szabályzat beállításai biztonságosabbak.

- Ha több megfelelőségi szabályzatot telepített, akkor az Intune a legbiztonságosabbat alkalmazza ezek közül.

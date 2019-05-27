---
title: Naplók route - beli Microsoft Intune használatával az Azure monitor |} A Microsoft Docs
description: Diagnosztikai beállítások használatával vizsgálati naplók és a műveleti naplók küldése a Microsoft Intune-ban az Azure storage-fiók, az event hubs és a log analytics. Válassza ki, hogy mennyi ideig szeretné megőrizni az adatokat, és tekintse meg a különböző méretű bérlők néhány becsült költségei.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 803d556150d60d0a3d60ec03c029d65f0f935f67
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045296"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Napló adatokat küldeni a tárolási, az event hubs, vagy a log analytics az Intune-ban (előzetes verzió)

A Microsoft Intune tartalmazza a beépített naplók, amelyek a környezet információkkal. **Auditnaplók** részletek megjelenítése a különböző események vagy a feladatokat, amelyek az Intune-ban történik. **Műveleti naplók (előzetes verzió)** részletek megjelenítése a felhasználók és eszközök számára, hogy sikeresen (vagy sikertelen) szeretne regisztrálni, valamint a nem megfelelő eszközök részleteiért.

Ezek a naplók az Azure Monitor-szolgáltatások, beleértve a storage-fiókok, az event hubs és a log analytics is lehet küldeni. Pontosabban a következőket teheti:

* Megőrizni az adatokat, vagy archív tárolási szint esetében idő beállítása az Azure storage-fiókba az Intune naplókat archiválhatja.
* Stream az Intune az Azure event hub Analytics népszerű biztonságiadat- és eseménykezelés (SIEM) eszközökkel, például a Splunk és QRadar naplózza.
* Az Intune-naplók integrálása a saját egyéni napló megoldások streamelési őket egy eseményközpontba.
* Az Intune naplókat küld a Log Analytics látványos vizualizációkkal, figyelés, és a csatlakoztatott adatok riasztás engedélyezése.

Ezek a szolgáltatások részét képezik a **diagnosztikai beállítások** az Intune-ban.

Ez a cikk bemutatja, hogyan használható **diagnosztikai beállítások** napló adatokat küldeni a különböző szolgáltatásokat, példákat és a költségek becslése biztosít és választ ad néhány gyakran felmerülő kérdésre.

## <a name="prerequisites"></a>Előfeltételek

Ez a funkció használatához az alábbiak szükségesek:

* Azure-előfizetés: Ha nem rendelkezik Azure-előfizetéssel, akkor [regisztráljon egy ingyenes próbaverzióra](https://azure.microsoft.com/free/).
* A Microsoft Intune-környezet (bérlő) az Azure-ban
* A felhasználó ki van egy **globális rendszergazdai** vagy **Intune-Szolgáltatásadminisztrátor** az Intune-bérlőhöz.

Attól függően, hol szeretné irányítani a naplózási adatokat szükség az alábbi szolgáltatások egyikét:

* Egy [Azure storage-fiók](https://docs.microsoft.com/azure/storage/common/storage-account-overview) a *listkeys műveletének* engedélyeket. Azt javasoljuk, hogy egy általános célú tárfiók, és nem egy blob storage-fiókot használja. Tárolás díjszabási információk: a [Azure Storage díjkalkulátor](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* Egy [Azure event hubs-névtér](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) külső megoldások integrálására.
* Egy [Azure log analytics-munkaterület](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) naplók elküldése a Log Analytics szolgáltatásba.

## <a name="send-logs-to-azure-monitor"></a>Naplók elküldése az Azure monitor

1. Az a [az Azure portal](https://portal.azure.com/), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. A **figyelés**válassza **diagnosztikai beállítások**. Az első megnyitásakor, kapcsolja be:

    ![Kapcsolja be a diagnosztikai beállítások az Intune-ban az Azure Monitor naplók küldése](media/diagnostics-settings-turn-on.png)

3. Adja meg a következő tulajdonságokat:

    - **Név**: Adjon meg egy nevet a diagnosztikai beállításokat. Ez a beállítás azt adja meg az összes tulajdonság tartalmazza. Például írja be a következőt: `Route audit logs to storage account`.
    - **Archiválás tárfiókba**: A naplóadatok menti az Azure storage-fiók. Használja ezt a beállítást, ha azt szeretné, mentésére vagy archiválására az adatokat.

        1. Válassza ezt a lehetőséget > **konfigurálása**. 
        2. A listából válasszon egy meglévő tárfiókot > **OK**.

    - **Az eseményközpontok felé Stream**: A naplók egy Azure-eseményközpontba streameli. Ha azt szeretné, hogy az SIEM-eszközökkel, például Splunk és QRadar, naplóadatok analytics ezt a lehetőséget.

        1. Válassza ezt a lehetőséget > **konfigurálása**. 
        2. A listából válasszon egy meglévő eseményközpont-névtér és a házirend > **OK**.

    - **Küldés a Log Analyticsnek**: Az adatok küldése az Azure log analytics. Ha szeretné használni a vizualizációt, monitorozási és riasztási a naplókhoz, akkor válassza ezt a lehetőséget.

        1. Válassza ezt a lehetőséget > **konfigurálása**. 
        2. Hozzon létre egy új munkaterületet, és adja meg a munkaterület részletei. Vagy válasszon ki egy meglévő munkaterületet a lista > **OK**.

            [Az Azure log analytics-munkaterület](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) további részleteket ezeket a beállításokat.

    - **NAPLÓ** > **Adatmodelltáblához**: Ezzel a lehetőséggel küldése a [auditnaplók Intune](monitor-audit-logs.md) a storage-fiók, event hubs és a log analytics. A vizsgálati naplók megjelenítése előzményeit minden egyes feladathoz, amely létrehoz egy módosítása az Intune-ban, akik kész is beleértve, és mikor.

      A storage-fiókot választja, majd is adja meg szeretné megőrizni az adatokat (megőrzés), hogy hány nap. Örökre megőrizni az adatokat, állítsa **megőrzés (nap)** való `0` (nulla).

    - **NAPLÓ** > **OperationalLogs**: Műveleti naplók (előzetes verzió) a sikeres vagy sikertelen, a felhasználók és eszközök regisztrálása az Intune-ban, valamint a nem megfelelő eszközök részleteiért megjelenítése. Válassza ezt a beállítást, a beléptetési naplókat küld a tárfiókot, az eseményközpontok felé, vagy a log analytics.

      A storage-fiókot választja, majd is adja meg szeretné megőrizni az adatokat (megőrzés), hogy hány nap. Örökre megőrizni az adatokat, állítsa **megőrzés (nap)** való `0` (nulla).

      > [!NOTE]
      > Műveleti naplók előzetes verzióként érhetők el. Visszajelzést, például a műveleti naplókban szereplő információkat Ugrás [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (megnyílik egy új webhelyet).

    Amikor végzett, a beállítások a következőhöz hasonló, az alábbi beállításokat: 

    ![Képet, amely az Intune naplókat küld egy Azure storage-fiók](media/diagnostics-settings-example.png)

4. **Mentse** a változtatásokat. A beállítás akkor jelenik meg a listában. Miután létrejött, a beállítások kiválasztásával módosíthatja **beállítás szerkesztése** > **mentése**.

## <a name="use-audit-logs-throughout-intune"></a>Auditnaplók Intune teljes használata

Az auditnaplók Intune-ban, beleértve a regisztráció, megfelelőségi, konfigurációs, eszközök, ügyfélalkalmazások és több más részein is exportálhatja.

Például a naplózási exportálása naplók eszközmegfelelőség használatakor:

1. Az a [az Azure portal](https://portal.azure.com/), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki **eszközmegfelelőség** > **figyelő** > **Auditnaplók**:

    ![Auditnaplók Intune adatátirányításhoz Azure Monitor-tároló, események hubs vagy analytics kiválasztása](media/audit-logs-under-monitor-in-compliance.png)

3. Válassza ki **adatexportálási beállítások**. Ha nincs engedélyezve, bekapcsolhatja a **diagnosztikai beállítások**. Azt is beállíthatja, hova küldhetők a naplók leírtak szerint [naplókat küld az Azure monitor](#send-logs-to-azure-monitor) (a jelen cikkben).

## <a name="cost-considerations"></a>Költségekkel kapcsolatos szempontok

Ha már rendelkezik Microsoft Intune-licenc, a tárolási fiók és az eseményközpont beállítása Azure-előfizetéssel kell. Az Azure-előfizetés általában díjmentes. De, kell fizetnem az Azure-erőforrások, például a storage-fiók az archiválási és az event hubs streameléshez. Az adatok mennyisége és a költségeket a bérlő méretétől függően eltérőek lehetnek.

### <a name="storage-size-for-activity-logs"></a>Tevékenységi naplóit tároló mérete

Összes naplózási esemény naplózása körülbelül 2 KB-os adat tárolására használ. Egy 100 000 felhasználó bérlőt akkor előfordulhat, hogy körülbelül 1,5 millió esemény naponta. Körülbelül 3 GB adat tárolására naponta szükség lehet. Írási műveletek általában öt perces kötegekben fordulhat elő, mert várhatóan körülbelül 9000 írási művelet / hó.

Az alábbi táblázatokban a bérlő méretétől függően a költségbecslés. Ezenkívül egy általános célú v2-tárfiók az USA nyugati Régiójában az adatmegőrzési legalább egy évig. Becslés kérése a naplók várható adatmennyiség, használja a [az Azure storage díjkalkulátor](https://azure.microsoft.com/pricing/details/storage/blobs/).

**A 100 000 felhasználó auditnapló**

| | |
|---|---|
|Események száma naponta| 1,5 millió|
|Havi becsült adatmennyiség| 90 GB|
|Becsült költség (USD) havonta| $1.93|
|Becsült költség / év (USD)| $23.12|

**Az 1000 felhasználó auditnapló**

| | |
|---|---|
|Események száma naponta| 15,000|
|Havi becsült adatmennyiség| 900 MB|
|Becsült költség (USD) havonta| $0.02|
|Becsült költség / év (USD)| $0.24|

### <a name="event-hub-messages-for-activity-logs"></a>Event hub-üzenetek tevékenységeket tartalmazó naplók

Események általában öt perces időközzel kötegelni, és elküldése egy üzenet, hogy ebben az időkeretben összes eseményhez is. Az event hubs egy üzenetnek 256 KB-os maximális mérettel. Ha a időtartamon belül az üzenetek teljes mérete meghaladja a kötetet, majd több üzeneteket küldi el.

Körülbelül 18-eseményeinek második általában történik például a nagy méretű bérlő több mint 100 000 felhasználó. Ez állapotnak felel meg 5400 események öt percenként (300 másodperc x 18 események). Auditnaplók nagyjából 2 KB-os eseményenkénti hívásszám. Ez megfelel a 10.8 MB adatot. Tehát 43 üzeneteket küld az event hubs, hogy öt perces időközt.

Az alábbi táblázat tartalmaz egy alapszintű event hubs esemény adatok mennyiségétől függően az USA nyugati Régiójában, havi becsült költségekkel kell számolnia. A naplók várható adatmennyiség becsléséhez, használja a [az Event Hubs-díjkalkulátor](https://azure.microsoft.com/pricing/details/event-hubs/).

**A 100 000 felhasználó auditnapló**

| | |
|---|---|
|Események száma másodpercenként| 18|
|Öt perces intervallum események| 5,400|
|Az időközönkénti kötet| 10.8 MB|
|Üzenet időköz| 43|
|Üzenetek / hó| 371,520|
|Becsült költség (USD) havonta| $10.83|

**Az 1000 felhasználó auditnapló**

| | |
|---|---|
|Események száma másodpercenként|0,1 |
|Öt perces intervallum események| 52|
|Az időközönkénti kötet|104 KB |
|Üzenet időköz|1 |
|Üzenetek / hó|8,640 |
|Becsült költség (USD) havonta|$10.80 |

### <a name="log-analytics-cost-considerations"></a>A log Analytics költségvetési szempontok

A Log Analytics-munkaterület felügyeletével kapcsolatos költségek áttekintéséhez lásd: [költségek kezelése a Log Analytics és az adatmennyiség szabályozásával](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage).

## <a name="frequently-asked-questions"></a>Gyakori kérdések

Válaszok a gyakori kérdések, és olvassa el az Azure Monitor-naplók az Intune esetleges ismert problémáiról.

#### <a name="which-logs-are-included"></a>Mely naplók tartoznak?

Vizsgálati naplók és a működési (előzetes verzió) naplókat is mindkét lehetőség elérhető az továbbításához ezzel a funkcióval.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>A műveletet, miután amikor hajtsa végre a hozzá tartozó naplók jelennek meg az eseményközpont?

A naplók általában jelenik meg az eseményközpont a művelet elvégzése után néhány percen belül. [Mi az Azure Event Hubs? ](https://docs.microsoft.com/azure/event-hubs/) további információkat biztosít.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>A műveletet, miután amikor hajtsa végre a hozzá tartozó naplók meg a storage-fiókban?

Az Azure storage-fiókok esetében a késés az bárhol az 5. a művelet futtatása után a 15 perc.

#### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Mi történik, ha egy rendszergazda cseréli a diagnosztikai beállítást megőrzési időtartama?

Az új adatmegőrzési házirend módosítása után gyűjtött naplók vonatkozik. Összegyűjtött naplók, mielőtt szabályzatának módosítása nem érinti.

#### <a name="how-much-does-it-cost-to-store-my-data"></a>Ez mennyibe tárolja az adataimat?

A tárolási költségeket a naplók és a megőrzési időtartam választott méretétől függ. A becsült költségek a bérlőkkel, amelyek a naplózási kötetnek generált függenek, lásd: a [tevékenységi naplóit tároló mérete](#storage-size-for-activity-logs) (a jelen cikkben).

#### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Ez mennyibe továbbításához egy eseményközpontba adataimat?

A streamelési költségek percenkénti kapott üzenetek száma függenek. További információ a költségek kiszámítása és az üzenetek száma alapján költségekről: [Event hub-üzenetek tevékenységeket tartalmazó naplók](#event-hub-messages-for-activity-logs) (a jelen cikkben).

#### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Hogyan integrálhatja a Intune naplókat SIEM-rendszeremmel?

Az Azure Monitor az Event Hubs használatával naplók streamelése a SIEM rendszerhez. Először [egy eseményközpontba naplók streamelése](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). Ezt követően [állítsa be az SIEM-eszközével](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) és a beállított eseményközpont. 

#### <a name="what-siem-tools-are-currently-supported"></a>Milyen SIEM eszközöket jelenleg támogatottak?

Jelenleg az Azure Monitor által támogatott [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar, és [Sumo logikai](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (megnyílik egy új webhelyet). Az összekötők működése kapcsolatos további információkért lásd: [Stream Azure monitorozási adatok felhasználásra egy eseményközpontba egy külső eszközzel](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs).

#### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Érhetem el az adatokat az eseményközpontból külső SIEM eszköz használata nélkül?

Igen. A naplók elérését az alkalmazást, használhatja a [Event Hubs API](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph).

#### <a name="what-data-is-stored"></a>Milyen adata?

Az Intune nem tárolja az folyamat keresztül küldött adatok. Intune az Azure Monitor folyamat, a szolgáltató a bérlő adatok irányítja. További információkért lásd: [Azure Monitor áttekintése](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>További lépések

* [Archív tevékenységeket tartalmazó naplók tárfiókba](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Útvonal-Tevékenységnaplók eseményközpontba](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Tevékenység-naplók integrálása a Log Analytics használatával](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)

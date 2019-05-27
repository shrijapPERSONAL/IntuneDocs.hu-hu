---
title: Módosítások és a Microsoft Intune - Azure-ban események naplózása |} A Microsoft Docs
description: Útmutató a Microsoft Intune-tevékenységeket rögzítő auditnaplók áttekintéséhez.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9d01b1f745450785209bf289be5b6e36ac65cc2d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046306"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Auditnaplók használatát nyomon követése és figyelése a Microsoft Intune-ban események

Auditnaplók Microsoft Intune-ban változást előidéző tevékenységek közé tartozik. Létrehozási, frissítési (szerkesztési), delete, assign és távoli műveletek összes naplózási esemény rendszergazdák tekintheti át a legtöbb Intune-ban feladat létrehozása. Alapértelmezés szerint az naplózás engedélyezve van minden ügyfél számára. Nem lehet letiltani.

> [!NOTE]
> Naplózási események rögzítése a 2017 December funkciókat tartalmazó kiadások elindult. Korábbi események nem érhetők el.

## <a name="who-can-access-the-data"></a>Ki férhet hozzá az adatokhoz?

A következő engedélyekkel rendelkező felhasználók tekinthetik meg az auditnaplókat:

- Globális rendszergazda
- Intune-szolgáltatásadminisztrátor
- **Naplózási adatok** - **Olvasási** engedéllyel rendelkező, Intune-szerepkörhöz hozzárendelt rendszergazdák

## <a name="audit-logs-for-intune-workloads"></a>Intune-beli számítási feladatok auditnaplói

A monitorozási csoport minden Intune-tevékenységprofilban az auditnaplók tekinthetők át:

1. Az a [az Azure portal](https://portal.azure.com/), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki azt a munkaterhelést, amelyet el szeretne tekinteni az auditnaplóit. Válassza ki például **eszközök**.
3. A **figyelés**, válassza a **Auditnaplók**.

## <a name="route-logs-to-azure-monitor"></a>Az Azure monitornak útvonal-naplók

Vizsgálati naplók és a műveleti naplókban az Azure monitornak is irányíthatóak. A **Auditnaplók**válassza **beállítások exportálása**:

![Teljesítménynapló-adatok exportálása az Azure monitor exportálási beállítások kiválasztásával, az Intune-ban](./media/audit-logs-export-data-settings.png)

Ez a szolgáltatás további információkért lásd: [Teljesítménynapló-adatok küldése a tárolóhoz, az event hubs, vagy a log analytics](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Naplózási események áttekintése

![Válassza ki a naplókat az Intune-ban, műveleteket és a dátumokat, amikor az események bekövetkezésének](./media/monitor-audit-logs.png "naplók")

Az auditnaplók alapértelmezett listanézete a következő elemeket jeleníti meg:

- dátum és idő az előfordulás
- Kezdeményező (szereplő)
- Alkalmazásnév
- Tevékenység
- Cél(ok)
- Category
- Állapot

Egy esemény kapcsolatos további információk megtekintéséhez jelöljön ki egy elemet a listából:

![További információ a ki volt, mely a vizsgálati naplók, az Intune-ban](./media/monitor-audit-log-detail.png "Auditnapló adatainak")

> [!NOTE]
> **Kezdeményező (szereplő)** aki a feladat futott, és ahol futtatásának tartalmaz adatokat. Például, ha futtatja a tevékenységet az Intune-ban az Azure Portalon, majd **alkalmazás** mindig megjeleníti **a Microsoft Intune-portálbővítmény** és a **Alkalmazásazonosító** mindig használja az azonos GUID Azonosítóval.
> 
> A **cél(ok)** szakasz sorolja fel, több cél és a módosított tulajdonságokkal együtt.  

## <a name="filter-audit-events"></a>A naplózási események áttekintése

Minden számítási feladathoz tartozik egy menüpont, mely előzetesen szűri az adott panelhez társított naplózási események kategóriáját. Egy különálló szűrési lehetőséggel válthat más kategóriákra, illetve az adott kategóriába tartozó eseményműveletek adataira. Egyszerű felhasználónév, például a műveletet végrehajtó felhasználó kereshet. A dátumtartomány-szűrők 24 órás, 7 napos és 30 napos beállítás használatát teszik lehetővé. Alapértelmezés szerint az utolsó 30 napban naplózott események jelennek meg.

## <a name="use-graph-api-to-retrieve-audit-events"></a>A naplózott események beolvasása a Graph API-val

A graph API használatával legfeljebb egy évnyi naplózott esemény részletes ismertetéséért lásd: [listázásával listában](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>További lépések

[Napló adatokat küldeni a tárolási, az event hubs, vagy a log analytics](review-logs-using-azure-monitor.md).

[Ügyfelekre vonatkozó alkalmazásvédelmi naplók áttekintése](app-protection-policy-settings-log.md).

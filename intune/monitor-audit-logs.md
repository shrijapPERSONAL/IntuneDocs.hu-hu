---
title: "Auditnaplók Intune-tevékenységekhez"
description: "Útmutató az Intune-tevékenységeket rögzítő auditnaplók áttekintéséhez"
keywords: 
author: dougeby
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 9f514e6d2dec268efe99f682bc3ef4e63ec53c02
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2018
---
# <a name="audit-logs-for-intune-activities"></a>Auditnaplók Intune-tevékenységekhez
Az auditnaplókban a Microsoft Intune-ban változást előidéző tevékenységek jegyzéke érhető el. A létrehozási, frissítési (szerkesztési), törlési és hozzárendelési műveletek, illetve a távoli feladatok naplózott eseményeket generálnak, melyek megtekinthetők. A legtöbb Intune-beli számítási feladat auditnaplói megtekinthetők. A naplózás alapértelmezés szerint engedélyezve van az összes ügyfél számára, és nem tiltható le. A naplózási események 2017 decemberében, az új funkció megjelenésekor kezdődtek, az ezt megelőző események így nincsenek rögzítve.

## <a name="who-can-access-the-data"></a>Ki férhet hozzá az adatokhoz?
A következő engedélyekkel rendelkező felhasználók tekinthetik meg az auditnaplókat:
- Globális rendszergazda
- Intune-szolgáltatásadminisztrátor
- **Naplózási adatok** - **Olvasási** engedéllyel rendelkező, Intune-szerepkörhöz hozzárendelt rendszergazdák

## <a name="audit-logs-for-intune-workloads"></a>Intune-beli számítási feladatok auditnaplói
Az auditnaplók az egyes Intune-beli számítási feladatok Figyelés csoportjában tekinthetők meg.  
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza ki a számítási feladatot, melynek meg szeretné tekinteni az auditnaplóit.
4. A számítási feladat **Figyelés** csoportjában válassza a **Naplók** lehetőséget.

## <a name="review-audit-events"></a>Naplózási események áttekintése
![Naplók](./media/monitor-audit-logs.png "Naplók")

Az auditnaplók alapértelmezett listanézete a következő elemeket jeleníti meg:    

- az előfordulás dátuma és időpontja
- Kezdeményező (szereplő)
- Tevékenység
- Cél(ok)
- Kategória
- Állapot

A listanézet adott elemére kattintva megjelenítheti annak összes rendelkezésre álló adatát.

![Naplók](./media/monitor-audit-log-detail.png "Naplók")

> [!Note]    
> Az auditnapló adatainak **Kezdeményező (szereplő)** szakaszában azzal kapcsolatban találhatók információk, hogy ki és honnan hajtotta végre a tevékenységet. Ha például az Azure Portalon hajtja végre a tevékenységet az Intune-ben, az **Alkalmazás** szakaszban mindig a **Microsoft Intune-portálbővítmény** jelenik meg, az **Alkalmazásazonosító** pedig mindig ugyanaz a GUID azonosító. 
>    
> A **Cél(ok)** szakaszban több cél is szerepelhet, a módosított tulajdonságokkal együtt.  


## <a name="filter-audit-events"></a>A naplózási események áttekintése
Minden számítási feladathoz tartozik egy menüpont, mely előzetesen szűri az adott panelhez társított naplózási események kategóriáját. Egy különálló szűrési lehetőséggel válthat más kategóriákra, illetve az adott kategóriába tartozó eseményműveletek adataira. Kereshet egyszerű felhasználónév (például a műveletet végrehajtó felhasználó) alapján. A dátumtartomány-szűrők 24 órás, 7 napos és 30 napos beállítás használatát teszik lehetővé. Alapértelmezés szerint az elmúlt 30 napban naplózott események jelennek meg.

## <a name="use-graph-api-to-retrieve-audit-events"></a>A naplózott események beolvasása a Graph API-val
A legfeljebb egy évnyi naplózott esemény Graph API-val való beolvasásáról az [auditEvent objektumok listázásával](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list) foglalkozó témakörben olvashat bővebben.
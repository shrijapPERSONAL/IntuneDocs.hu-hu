---
title: Jelentés készítése az OData-adatcsatornából a Power BI használatával
titlesuffix: Microsoft Intune
description: Fatérkép-diagram létrehozása a Power BI Desktop használatával, az Intune-adattárház API-ból származó interaktív szűrővel.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c38b3f0656f6b285c38da39971f9f124b5448c14
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229513"
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Jelentés készítése az OData-adatcsatornából a Power BI használatával

Ez a cikk bemutatja, hogyan hozhat létre egy fatérkép-diagramot a Power BI Desktop használatával, az Intune-adattárház API-ból származó interaktív szűrővel. Előfordulhat például, hogy a pénzügyi igazgató azt szeretné tudni, hogy a teljes eszközállomány hogyan oszlik meg vállalati és személyes tulajdonúak között. A fatérkép-diagram megmutatja az eszköztípusok teljes számát. Látható benne, hogy hány iOS-es, hány androidos és hány windowsos eszköz van vállalati, és hány személyes tulajdonban.

### <a name="overview-of-creating-the-chart"></a>A diagram létrehozásának áttekintése

A diagram létrehozásához az alábbi lépéseket kell elvégeznie:
1. A Power BI Desktop telepítése, ha még nincs telepítve.
2. Csatlakozás az Intune-adattárház adatmodellhez, és a modell aktuális adatainak letöltése.
3. Az adatmodell kapcsolatainak létrehozása és kezelése.
4. Diagram létrehozása az **eszközök** tábla adataiból.
5. Interaktív szűrő létrehozása.
6. Az elkészült diagram megtekintése.

### <a name="a-note-about-tables-and-entities"></a>Megjegyzés a táblákhoz és az entitásokhoz

A Power BI-ban táblákkal kell dolgozni. A táblák adatmezőket tartalmaznak. Minden adatmező adott adattípussal rendelkezik. A mező kizárólag az adott adattípusba tartozó adatokat tartalmazhat. Az adattípus lehet szám, szöveg, dátum és így tovább. Miután betöltötte a modellt, a Power BI táblái feltöltődnek a bérlőből származó friss időbeli adatokkal. Noha a konkrét adat idővel megváltozhat, a táblaszerkezet nem változik, hacsak az alapul szolgáló adatmodellt nem frissítik.

Az _entitás_ és a _tábla_ kifejezések eleinte zavart okozhatnak. Az adatmodell egy OData-adatcsatornán keresztül érhető el. Azt a tárolót, amelyet az OData használatánál entitásnak nevezünk, a Power BI használatánál táblának hívjuk. Mindkét kifejezés arra a dologra vonatkozik, amely az adatokat tartalmazza.

## <a name="install-power-bi-desktop"></a>A Power BI Desktop telepítése

Telepítse a Power BI Desktop legújabb verzióját. A Power BI Desktop tölthető le: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Csatlakozás a bérlőhöz tartozó Intune-adattárház OData-adatcsatornájához

> [!Note]  
> Az Intune-beli **Jelentések** eléréséhez hozzáférési engedélyre van szükség. További információt az [Engedélyezés](reports-api-url.md) témakörben talál.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Nyissa meg az **Intune-adattárház** panelt.
4. Másolja az egyéni URL-címet. Például:`https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Nyissa meg a Power BI Desktop alkalmazást.
6. Válassza az **Adatok betöltése** > **OData-adatcsatorna** lehetőséget.
7. Illessze be az egyéni URL-címet az **OData-adatcsatorna** ablak URL mezőjébe.
8. Válassza az **Alapszintű** lehetőséget.

    ![OData-csatornáról az Intune Data warehouse-hoz a bérlő számára](media/reports-create-01-odatafeed.png)

9. Kattintson az **OK** gombra.
10. Válassza a **Szervezeti fiók** lehetőséget, és jelentkezzen be az Intune-hoz tartozó hitelesítő adataival.

    ![Szervezeti fiók hitelesítő adatai](media/reports-create-02-org-account.png)

11. Kattintson a **Csatlakozás** gombra. Ekkor megnyílik a Navigátor, és megjelenik rajta az Intune-adattárházban található táblák listája.

    ![A kezelő - a Data Warehouse-táblákat képernyőképe](media/reports-create-02-loadentities.png)

12. Válassza ki a **devices** (eszközök) és az **ownerTypes** (tulajdonostípusok) táblákat.  Válassza a **Betöltés** lehetőséget. A Power BI betölti az adatokat a modellbe.

## <a name="create-a-relationship"></a>Kapcsolat létrehozása

Nem csak egyetlen tábla adatait, de több táblát is importálhat, és így egyszerre több tábla összekapcsolt adatait is elemezheti.  A Power BI rendelkezik egy **automatikus felismerés** funkcióval, amely megpróbálja megkeresni és létrehozni a kapcsolatokat. Az Adattárház táblái úgy lettek kialakítva, hogy képesek legyenek együttműködni a Power BI automatikus felismerés funkciójával. Ha azonban a Power BI nem tudja automatikusan megtalálni a kapcsolatokat, manuális kezelésre is van lehetőség.

![Kapcsolódó adatok kapcsolatok kezelése a táblák között](media/reports-create-03-managerelationships.png)

1. Válassza a **Kapcsolatok kezelése** lehetőséget.
2. Ha a Power BI még nem észlelte a kapcsolatokat, válassza az **Automatikus észlelés...** lehetőséget.

A kapcsolatokat egy From (forrás) és egy To (cél) oszlopban láthatja. Ebben a példában az **eszközök** tábla **ownerTypeKey** adatmezőjéből indul kapcsolat az **ownerTypes** tábla **ownerTypeKey** mezőjébe. A kapcsolatok használatával az **eszközök** táblában kikeresheti az eszköztípusok kódjaihoz tartozó egyszerű neveket.

## <a name="create-a-treemap-visualization"></a>Fatérkép-diagram létrehozása

A fatrékép-diagram adatok hierarchikus viszonyát jeleníti meg négyzeteken belüli négyzetek formájában. A hierarchia minden ága egy négyzet, amely alágakat reprezentáló kisebb négyzeteket tartalmaz. A Power BI Desktoppal olyan fatérkép-diagramokat hozhat létre, amelyek megjenítheti az Intune-adatokat.

![Power BI-Vizualizációk fatérkép-diagram](media/reports-create-03-treemap.png)

1. Válassza ki a diagram típusát. Válassza a **Fatérkép-diagram** lehetőséget.
2. Az adatmodellben keresse meg a **devices** (eszközök) táblát.
3. Bontsa ki a **devices** (eszközök) táblát, és válassza a **manufacturer** (gyártó) adatmezőt a **Mezők** panelen.
4. A **manufacturer** (gyártók) adatmezőt húzza a jelentésvásznon lévő Fatérkép-diagramra.
5. A **devices** tábla **deviceKey** adatmezőjét húzza a **Vizualizációk** panelen található **Értékek** szakaszba, és tegye az **Ide húzza az adatmezőt** feliratú négyzetbe.  

Ezzel elkészített egy olyan vizualizációt, amely megmutatja, hogy milyen a szervezetben az eszközök gyártók szerinti eloszlása.

![Fatérkép diagram adatokkal - milyen eszközök gyártók szerinti eloszlása](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Szűrő hozzáadása

A fatérkép-diagramhoz szűrőt is hozzáadhat, hogy az további kérdésekre is választ tudjon adni az alkalmazással.


1. Szűrő hozzáadásához kattintson a jelentésvászonra, és válassza a **szeletelő ikon** (![fatérkép-diagram adatok modell és a támogatott kapcsolatok](media/reports-create-slicer.png)) alatt **Vizualizációk**.
2. Keresse meg az **ownerTypes** táblát, majd az **ownerTypeName** adatmezőt húzza a **Vizualizációk** panelen található **Szűrők** szakaszba.  

   Az eszközök táblában van egy **OwnerTypeKey** nevű adatmező, amely azt a kódot tartalmazza, amely azt jelzi, hogy az eszköz vállalati vagy személyes tulajdonú-e. Mivel ebben a szűrőben egyszerű neveket célszerű használni, keresse meg az **ownerTypes** táblát, és húzza el az **ownerTypeName** mezőt. Ebből a példából láthatja, hogyan támogatja az adatmodell a táblák közötti kapcsolatokat.

![Fatérkép-diagram szűrővel – támogatja a táblák közötti kapcsolatok](media/reports-create-08_ownertype.png)

Ezzel létrehozott egy olyan interaktív szűrőt, amelyben egyszerű váltással megtekinthetők a vállalati és a személyes tulajdonú eszközök. Ezzel a szűrővel megtekintheti az eloszlás változásait.

1. A **Vállalati** lehetőséget választva a vállalati eszközök eloszlása jeleníthető meg.
2. A **Személyes** lehetőséget választva a személyes tulajdonú eszközök tekinthetők meg.

## <a name="next-steps"></a>További lépések

 - Olvassa el a Power BI dokumentációjában, hogyan [hozhatók létre és hogyan kezelhetők kapcsolatok](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) a Power BI Desktopban.
 - Ismerkedjen meg az [Intune-adattárház modelljével](https://docs.microsoft.com/intune/reports-ref-data-model).

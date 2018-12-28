---
title: Intune-adattárház API-végpontja
titlesuffix: Microsoft Intune
description: A referencia-témakör ismerteti a Microsoft Intune Data Warehouse API URL-Címének szerkezete. Szűrő példák állnak rendelkezésre.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 58a78cee51a411c940d4510cd8498994c14129f0
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642744"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-adattárház API-végpontja

Az Intune-adattárház API-t az adott szerepköralapú hozzáférés-vezérlőkkel és Azure AD-beli hitelesítő adatokkal rendelkező fiókokkal használhatja. Ezután az OAuth 2.0 segítségével hitelesíti majd REST-ügyfelét az Azure AD szolgáltatással. Végül pedig megalkotja az adattárház-erőforrás hívására szolgáló beazonosítható URL-címet.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Engedélyezés

Az Azure Active Directory (Azure AD) az OAuth 2.0 használatával teszi lehetővé a webalkalmazásokhoz és webes API-khez való hozzáférés engedélyezését az Azure AD-bérlőben. Jelen útmutató nyelvektől független, és azt ismerteti, hogyan küldhetők és fogadhatók HTTP-üzenetek a nyílt forráskódú könyvtárak bármelyikének használata nélkül. Az OAuth 2.0 engedélyezési kódfolyamról bővebben az OAuth 2.0 ismertetőjének [4.1 szakaszában](https://tools.ietf.org/html/rfc6749#section-4.1) olvashat.

További információt az [Hozzáférés engedélyezése webes alkalmazásokhoz az OAuth 2.0 és az Azure Active Directory használatával](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) című témakörben talál.

## <a name="api-url-structure"></a>API URL-címének szerkezete

Az adattárház API-végpontjai az egyes készletekhez tartozó entitásokat olvassák. Az API támogatja a **GET** HTTP-parancsot, valamint a lekérdezési beállítások alkészletét.

Az Intune-hoz tartozó URL-cím a következő formátumot használja:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> A fenti URL-címben cserélje le a `{location}`, `{entity-collection}` és `{api-version}` értékeket az alábbi táblázatban szereplő információk alapján.

Az URL-cím a következő elemeket tartalmazza:

| Elem | Példa | Leírás |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Az alap URL-cím helye az Azure Portalon található adattárház API paneljén látható. |
| entitásgyűjtemény | dátumok | Az OData-entitásgyűjtemény neve. Az adatmodellben lévő gyűjteményekről és entitásokról további információt a [Adatmodell](reports-ref-data-model.md) című témakörben talál. |
| api-verzió | béta | Verzió alatt az elérni kívánt API verzióját értjük. További információt a [Verzió](#API-version-information) című témakörben talál. |
| maxhistorydays | 7 | (Nem kötelező) Az előzmények bejegyzéseinek maximális lekérési időtartama (napokban kifejezve). Ez a paraméter bármely gyűjteménnyel használható, de csak olyan gyűjteményeknél lép érvénybe, amelyek tartalmazzák a `dateKey` értéket a kulcstulajdonság részeként. További információk: [DateKey típusú tartományszűrők](reports-api-url.md#datekey-range-filters). |

## <a name="api-version-information"></a>Az API-verzióra vonatkozó információk

Az API jelenlegi verziója a következő: `beta`. 

## <a name="odata-query-options"></a>Az OData-lekérdezés beállításai

A jelenlegi verzió a következő OData-lekérdezésparamétereket támogatja: `$filter, $orderby, $select, $skip,` és `$top`.

## <a name="datekey-range-filters"></a>DateKey típusú tartományszűrők

A `DateKey` tartományszűrők az adatletöltés korlátozására használhatók a `dateKey` kulcstulajdonsággal rendelkező egyes gyűjtemények esetén. A `DateKey` szűrő a szolgáltatás teljesítményének optimalizálására használható az alábbi `$filter` lekérdezési paraméter megadásával:

1.  A `DateKey` önállóan a `$filter` szűrűben. Támogatja az `lt/le/eq/ge/gt` operátorokat és az `and` logikai operátort, amelyet a kezdő dátum és/vagy a záró dátum leképezéséhez lehet használni.
2.  A `maxhistorydays` egyéni lekérdezési lehetőségként van megadva.<br>

## <a name="filter-examples"></a>Példák a szűrőkre

> [!NOTE]
> A példaszűrők feltételezik, hogy a mai dátum 2018. február 21.

|                             Szűrés                             |           A teljesítmény optimalizálása           |                                          Leírás                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Összes                                      |    Olyan adatokat ad vissza, amelyekben a `DateKey` értéke 20180214 és 20180221 között van.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Összes                                      |    Olyan adatokat ad vissza, amelyekben a `DateKey` értéke megegyezik a 20180214 értékkel.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Összes                                      |    Olyan adatokat ad vissza, amelyekben a `DateKey` értéke 20180214 és 20180220 között van.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Részleges, az Id gt 1 nem lesz optimalizálva    |    Olyan adatokat ad vissza, amelyekben a `DateKey` értéke 20180214 és 20180221 között van, és az Id nagyobb, mint egy 1.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Összes                                      |    Olyan adatokat ad vissza, amelyekben a `DateKey` értéke megegyezik a 20180214 értékkel. A rendszer mellőzi a `maxhistorydays` értékét.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    None                                      |    Nem számít `DateKey` tartományszűrőnek, így nincs teljesítményfokozás.                              |
|    `$filter=DateKey ne 20180214`                                 |    None                                      |    Nem számít `DateKey` tartományszűrőnek, így nincs teljesítményfokozás.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    None                                      |    Nem számít `DateKey` tartományszűrőnek, így nincs teljesítményfokozás. A rendszer mellőzi a `maxhistorydays` értékét.    |

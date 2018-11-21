---
title: Alkalmazás
titlesuffix: Microsoft Intune
description: Referencia-témakör az Intune-adattárház API entitásgyűjteményeiben található Alkalmazás kategóriához.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 32f41e4f299af4802dd270ec4a46c0cf4d467bc9
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179133"
---
# <a name="reference-for-application-entities"></a>Alkalmazás-entitások referencia

Az **Alkalmazás** kategória mobileszközökhöz készült entitásokat tartalmaz, amelyek többek között az alábbi információkat követik nyomon:

  -  Az alkalmazás verziói
  -  Az alkalmazás telepítési forrása
  -  Az alkalmazást létrehozó fejlesztők típusai
  -  Az alkalmazáshoz tartozó felügyelt szoftverek típusa, például **sidecar** („oldalkocsis”) vagy **asztali**
  -  Az alkalmazás mennyiségi vásárlási programbeli (VPP) állapota

## <a name="apprevision"></a>AppRevision

Az **AppRevision** entitás listázza az alkalmazások összes verzióját.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| AppKey |Az alkalmazás egyedi azonosítója. |123 |
| ApplicationId |Az alkalmazás egyedi azonosítója – Az AppKey-hez hasonlít, de természetes kulcs. |b66bc706-ffff-7437-0340-032819502773 |
| Változat |A bináris feltöltése során a rendszergazda által említett verzió. |2 |
| Cím |Az alkalmazás címe. |Excel |
| Kiadó |Az alkalmazás kiadója. |Microsoft |
| UploadState |Az alkalmazás feltöltésének állapota. |1 |
| AppTypeKey |A következő szakaszban leírt AppType érték hivatkozása. | |
| VppProgramTypeKey |A következő szakaszban leírt VppProgramType érték hivatkozása. | |
| CreationTime |A jelen változat létrehozásának ideje. |2016.11.23. 12:00:00 |
| ModifiedTime |A legutóbbi, jelen változattal kapcsolatos bármilyen módosítás ideje. |2016.11.23. 12:00:00 |
| Méret |A bináris mérete. | |
| StartDateInclusiveUTC |A jelen változat adattárházban történő létrehozásának dátuma és időpontja (UTC). |2016.11.23. 12:00:00 |
| EndDateExclusiveUTC |A jelen változat elavulásának dátuma és időpontja (UTC). |2016.11.23. 12:00:00 |
| IsCurrent |Jelzi, hogy az alkalmazásverzió aktuális-e az adattárházban. |Igaz/hamis |
| RowLastModifiedDateTimeUTC |Az alkalmazásverzió legutóbbi módosításának dátuma és időpontja (UTC) az adattárházban. |2016.11.23. 12:00:00 |

## <a name="apptypes"></a>AppTypes

Az **AppTypes** entitás az alkalmazás telepítési forrásait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| AppTypeID |A típus azonosítója |
| AppTypeKey |A kulcs helyettes kulcsa |
| AppTypeName |Alkalmazás típusa |

### <a name="example"></a>Példa

| AppTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |Android store app | Android Áruházbeli alkalmazás. |
| 1 |Android LOB app | Üzletági Android-alkalmazás. |
| 2 |Managed Android store app (MAM) | Android Áruházbeli alkalmazás, amelyen engedélyezve van a felügyelet. |
| 3 |iOS store app | iOS Store-alkalmazás. |
| 4 |iOS LOB app | Üzletági iOS-alkalmazás. |
| 5 |Managed iOS store app (MAM?) | iOS-alkalmazás, amelyen engedélyezve van a felügyelet. |
| 6 |O365 Pro Plus Suite | A Windows 10-hez készült Office 365 Pro Plus Csomag. |
| 7 |Web app | Webes alkalmazás. |
| 8 |Windows Phone 8.1 store app | Windows Phone 8.1-es Áruházbeli alkalmazás. |
| 9 |Windows store app | Windows Áruházbeli alkalmazás. |
| 10 |Windows LOB apps | AppX-alapú üzletági Windows-alkalmazás. |
| 11 |Windows Mobile MSI | MSI-alapú üzletági alkalmazás. |
| 12 |Windows Phone LOB app | Üzletági Windows Phone-alkalmazás. |


## <a name="vppprogramtypes"></a>VppProgramTypes

A **VppProgramTypes** entitás az alkalmazás lehetséges VPP-programtípusait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| VppProgramTypeID | A típus azonosítója. |
| VppProgramTypeKey | A kulcs helyettes kulcsa. |
| VppProgramTypeName | A VPP program típusa. |

### <a name="example"></a>Példa

| VppProgramID  | Név | Leírás |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | A Microsoft VPP-programja. |
| 00000000-0000-0000-0000-000000000000 | Not Yet Available (Még nem érhető el) | Alapértelmezett érték, nincs VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Az Apple VPP-programja. |



## <a name="applicationinventory"></a>ApplicationInventory

Az **ApplicationInventory** entitás a leltárkészítés pillanatában az eszközön talált alkalmazásokat sorolja fel.

| Tulajdonság  | Leírás |
|---------|------------|
| DeviceKey | Az Intune-eszközazonosítót tartalmazó eszköztáblára mutató hivatkozás. |
| DateKey | A leltári napot megadó dátumtáblázat-hivatkozás. |
| ApplicationName | Az alkalmazás neve. |
| ApplicationVersion | Az alkalmazás verziója. |
| BundleSize | Az alkalmazás mérete bájtban. |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

A **MobileAppInstallState** entitás egy mobilalkalmazás telepítési állapotát jelöli, miután az hozzá lett rendelve egy eszközöket, felhasználókat vagy mindkettőt tartalmazó csoporthoz.

| Tulajdonság | Leírás |
|---|---|
| AppInstallStateKey | A fiókhoz tartozó alkalmazástelepítési állapot egyedi azonosítója. |
| AppInstallState | Az alkalmazástelepítési állapot felsorolásértéke. |
| AppInstallStateName | Az alkalmazástelepítési állapot neve. |

## <a name="mobileappdeviceuserinstallstatus"></a>MobileAppDeviceUserInstallStatus

A **MobileAppDeviceUserInstallStatus** a mobilalkalmazás telepítési állapotát jelöli egy adott eszközre és felhasználóra vonatkozóan.


|      Tulajdonság      |                                                         Leírás                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|
|      DateKey       |                                  Az alkalmazástelepítési állapot rögzítési dátumának kulcsa.                                  |
|       AppKey       |                             A mobilalkalmazás kulcsa, mely az AppRevision osztály egy példányát azonosítja.                              |
|     DeviceKey      |                              Egy céleszköz kulcsa, mely a Device osztály egy példányát azonosítja.                               |
|      UserKey       |                                Egy célfelhasználó kulcsa, mely a User osztály egy példányát azonosítja.                                 |
| AppInstallStateKey |                     Az alkalmazástelepítési állapot kulcsa, mely a MobileAppInstallState osztály egy példányát azonosítja.                     |
|     Hibakód      | Az alkalmazástelepítő, a mobilplatform vagy a szolgáltatás által az alkalmazás telepítésével kapcsolatban visszaadott hibakód. |


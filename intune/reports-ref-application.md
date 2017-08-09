---
title: "Alkalmazás | Microsoft Docs"
description: "Referencia-témakör az Intune-adattárház API entitásgyűjteményeiben található Alkalmazás kategóriához."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e12792445b36ba6657cbe6b2f6c924f6d97fe3c
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
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
| AppKey |Az alkalmazás egyedi azonosítója |123 |
| ApplicationId |Az alkalmazás egyedi azonosítója – Az AppKey-hez hasonlít, de természetes kulcs. |b66bc706-ffff-7437-0340-032819502773 |
| Változat |A bináris feltöltése során a rendszergazda által említett verzió |2 |
| Cím |Az alkalmazás címe |Excel |
| Kiadó |Az alkalmazás kiadója |Microsoft |
| UploadState |Az alkalmazás feltöltésének állapota |1 |
| AppTypeKey |A következő szakaszban leírt AppType érték hivatkozása. | |
| VppProgramTypeKey |A következő szakaszban leírt VppProgramType érték hivatkozása | |
| CreationTime |A jelen változat létrehozásának ideje |11/23/2016 12:00:00 AM |
| ModifiedTime |A legutóbbi, jelen változattal kapcsolatos bármilyen módosítás ideje |11/23/2016 12:00:00 AM |
| Méret |A bináris mérete | |
| StartDateInclusiveUTC |A jelen változat adattárházban történő létrehozásának dátuma és időpontja (UTC) |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |A jelen változat elavulásának dátuma és időpontja (UTC) |11/23/2016 12:00:00 AM |
| IsCurrent |Jelzi, hogy az alkalmazásverzió aktuális-e az adattárházban |Igaz/hamis |
| RowLastModifiedDateTimeUTC |Az alkalmazásverzió legutóbbi módosításának dátuma és időpontja (UTC) az adattárházban |11/23/2016 12:00:00 AM |

## <a name="appinstallertypes"></a>AppInstallerTypes

Az **AppInstallerTypes** entitás az alkalmazás telepítési forrásait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| AppTypeID |A típus azonosítója |
| AppTypeKey |A kulcs helyettes kulcsa |
| AppTypeName |Alkalmazás típusa |

## <a name="example"></a>Példa

| AppTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |Android store app |Android Áruházbeli alkalmazás |
| 1 |Android LOB app |Üzletági Android-alkalmazás |
| 2 |Managed Android store app (MAM) |Android Áruházbeli alkalmazás, amelyen engedélyezve van a felügyelet |
| 3 |iOS store app |iOS Store-alkalmazás |
| 4 |iOS LOB app |Üzletági iOS-alkalmazás |
| 5 |Managed iOS store app (MAM?) |iOS-alkalmazás, amelyen engedélyezve van a felügyelet |
| 6 |O365 Pro Plus Suite |A Windows 10-hez készült Office 365 Pro Plus Csomag |
| 7 |Web app |Webes alkalmazás |
| 8 |Windows Phone 8.1 store app |Windows Phone 8.1-es Áruházbeli alkalmazás |
| 9 |Windows store app |Windows Áruházbeli alkalmazás |
| 10 |Windows LOB apps |AppX-alapú üzletági Windows-alkalmazás |
| 11 |Windows Mobile MSI |MSI-alapú üzletági alkalmazás |
| 12 |Windows Phone LOB app |Üzletági Windows Phone-alkalmazás |

## <a name="applicationtypes"></a>ApplicationTypes

Az **ApplicationTypes** entitás az alkalmazás lehetséges típusait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| ApplicationTypeID |A típus azonosítója |
| ApplicationTypeKey |A kulcs helyettes kulcsa |
| ApplicationTypeName |Alkalmazás típusa |

## <a name="example"></a>Példa

| ApplicationTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |InHouse |Belső fejlesztésű alkalmazás |
| 1 |DeepLink |Alkalmazás-áruházban található alkalmazásra mutató hivatkozás |
| 2 |WebLink |Webalkalmazásra mutató hivatkozás |

## <a name="managedsoftwaretypes"></a>ManagedSoftwareTypes

A **ManagedSoftwareTypes** entitás az alkalmazás lehetséges felügyelt szoftvertípusait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| SoftwareTypeID |A típus azonosítója |
| SoftwareTypeKey |A kulcs helyettes kulcsa |
| SoftwareTypeName |A szoftver típusa |

## <a name="example"></a>Példa

| SoftwareTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |Asztali |Asztali alkalmazás |
| 2 |Frissítés |Ablakfrissítés |
| 5 |SideCarAgent | |
| 1 |Mobil |Mobilalkalmazás |
| 3 |WebLink |Webhivatkozás |
| 4 |VppDeepLink |Mennyiségi vásárlási programhoz (VPP) tartozó, alkalmazás-áruházbeli alkalmazásra mutató hivatkozás |

## <a name="vppprogramtypes"></a>VppProgramTypes

A **VppProgramTypes** entitás az alkalmazás lehetséges VPP-programtípusait listázza.

| Tulajdonság  | Leírás |
|---------|------------|
| VppProgramTypeID |A típus azonosítója |
| VppProgramTypeKey |A kulcs helyettes kulcsa |
| VppProgramTypeName |Mennyiségi vásárlási program (VPP) típusa |

## <a name="example"></a>Példa

| VppProgramID  | Név | Leírás |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |A Microsoft VPP-programja |
| 00000000-0000-0000-0000-000000000000 |Not Yet Available (Még nem érhető el) |Alapértelmezett érték, nincs VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Az Apple VPP-programja |

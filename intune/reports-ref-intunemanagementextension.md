---
title: IntuneManagementExtension entitás
titlesuffix: Microsoft Intune
description: Az Intune-adattárház API-ban található entitásgyűjtemények IntuneManagementExtension entitáskategóriájára vonatkozó referencia-témakör.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1cd36cba007b465d2100000c484ab6ef5eed2dd
ms.sourcegitcommit: c4258bb5824daf3f7e0ac3bb8afc539bde4d95da
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/16/2019
ms.locfileid: "57990948"
---
# <a name="reference-for-intune-management-extension"></a>Az Intune felügyeleti bővítmény referenciája

Az **IntuneManagementExtension** kategória mobileszközökhöz készült entitásokat tartalmaz, amelyek többek között az alábbi információkat követik nyomon:

  -  Egy IntuneManagementExtension verziói
  -  Egy IntuneManagementExtension telepítési állapota

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

Az **IntuneManagementExtensionVersion** entitás az IntuneManagementExtension által használt valamennyi verzió listáját tartalmazza.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| ExtensionVersionKey |Az IntuneManagementExtension verziójának egyedi azonosítója. | 1 |
| ExtensionVersion |A négyjegyű verziószám. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

Az **IntuneManagementExtensionHealthState** az IntuneManagementExtension valamennyi lehetséges állapotának listáját tartalmazza.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| ExtensionStateKey |Az állapot egyedi azonosítója. | 2 |
| ExtensionState |Az IntuneManagementExtension állapota. | Kifogástalan |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

Az **IntuneManagementExtension** az IntuneManagementExtension-állapotok az egyes Windows 10 rendszerű eszközökön naponta készülő listája.
Az entitás az utolsó 60 nap adatait őrzi meg. 


|      Tulajdonság       |                         Leírás                         | Példa |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               A dátum egyedi azonosítója.                |   123   |
|      TenantKey      |              A bérlő egyedi azonosítója.               |   456   |
|      DeviceKey      |              Az eszköz egyedi azonosítója.               |   789   |
| ExtensionVersionKey | Az IntuneManagementExtension verziójának egyedi azonosítója. |    1    |
|  ExtensionStateKey  |             Az állapot egyedi azonosítója.              |    2    |


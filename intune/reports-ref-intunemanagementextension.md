---
title: IntuneManagementExtension entitás
titleSuffix: Microsoft Intune
description: Az Intune-adattárház API-ban található entitásgyűjtemények IntuneManagementExtension entitáskategóriájára vonatkozó referencia-témakör.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebece46bac8ebee5cb3c6a573f0b09c4b308abe3
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040990"
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


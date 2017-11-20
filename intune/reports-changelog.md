---
title: "Intune-adattárház – módosítási napló | Microsoft Docs"
description: "Az Intune-adattárház API módosításai."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Az Intune-adattárház API módosítási naplója

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Maradjon naprakész az Intune-adattárház frissítéseivel kapcsolatban.

## <a name="1710"></a>1710
_Kiadás dátuma: 2017. november_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>A felhasználói entitás tartalmazza a legújabb felhasználói adatokat az adattárház adatmodelljében <!-- 1544273 -->

Az Intune-adattárház adatmodelljének első verziója csak a legújabb Intune-előzményadatokat tartalmazta. A jelentéskészítők így nem tudták felmérni a felhasználók aktuális állapotát. Ebben a frissítésben a [**felhasználói entitás**](reports-ref-user.md) a legújabb felhasználói adatokat tartalmazza.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Új entitások az adattárház adatmodelljében <!-- 1479526 --><!-- -->

 - Új entitás: [**UserDeviceAssociation**](reports-ref-user-device.md). A **UserDeviceAssociation** tartalmazza a szervezet felhasználói hozzárendeléseit.
 - Megjelent az [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) entitás. Az **IntuneManagementExtension** mobileszközökhöz készült entitásokat tartalmaz, amelyek többek között a verziószámot és a telepítési állapotot követik nyomon.

## <a name="next-steps"></a>További lépések
 - Heti összesítésben [olvashat az Intune újdonságairól](whats-new.md). Emellett tájékozódhat a jövőbeni változtatásokról, a szolgáltatással kapcsolatos fontos bejelentésekről és a korábbi verziókról is. 
 - Tekintse meg [a Microsoft Intune blogját](http://go.microsoft.com/fwlink/?LinkID=273882).
---
title: Felhasználók és eszközök társítása – Intune-adattárház
titlesuffix: Microsoft Intune
description: A UserDeviceAssociation entitás tartalmazza felhasználói a szervezetben.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.openlocfilehash: 02c579a7371a59a46cfb0017e6aa1a17af92bd03
ms.sourcegitcommit: 1c9ef5cfac2fc024528d2cfc9d590fa68dd58080
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/15/2018
ms.locfileid: "53429559"
---
# <a name="reference-for-user-device-association-entity"></a>Segédlet a Felhasználók és eszközök társítása entitáshoz

A **UserDeviceAssociation** entitás tartalmazza a szervezet felhasználói hozzárendeléseit.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Name (Név)        |                                           Leírás                                            |        Példa         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              A felhasználó egyedi azonosítója az adattárházban. (Helyettes kulcs).               |          123           |
|     DeviceKey      |                      Az eszköz egyedi azonosítója az adattárházban.                      |          123           |
| CreatedDateTimeUTC |           A felhasználói eszköztársítás létrehozásának dátuma és időpontja. UTC formátumban.           | 2016.11.23. 12:00:00 |
|     IsDeleted      | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. |       Igaz/hamis       |
|  EndedDateTimeUTC  |              Az IsDeleted paraméter <strong>True</strong> (Igaz) értékre módosulásának dátuma és időpontja (UTC).               | 2017.06.23. 12:00:00 |

## <a name="next-steps"></a>További lépések

- Tudjon meg többet a [Intune Data Warehouse](reports-nav-create-intune-reports.md).
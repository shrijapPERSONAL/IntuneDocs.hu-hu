---
title: Felhasználók és eszközök társítása – Intune-adattárház
titlesuffix: Microsoft Intune
description: Az Intune-adattárház API módosításai.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0829bbcb661822c5d00ba4ca1e5d31ece301ef02
ms.sourcegitcommit: 445a54dc6826a549d770a9953549ae2191d391c2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727424"
---
# <a name="user-device-association"></a>Felhasználók és eszközök társítása

A **UserDeviceAssociation** entitás tartalmazza a szervezet felhasználói hozzárendeléseit.


|        Név        |                                           Leírás                                            |        Példa         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              A felhasználó egyedi azonosítója az adattárházban. (Helyettes kulcs).               |          123           |
|     DeviceKey      |                      Az eszköz egyedi azonosítója az adattárházban.                      |          123           |
| CreatedDateTimeUTC |           A felhasználói eszköztársítás létrehozásának dátuma és időpontja. UTC formátumban.           | 2016.11.23. 12:00:00 |
|     IsDeleted      | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. |       Igaz/hamis       |
|  EndedDateTimeUTC  |              Az IsDeleted paraméter <strong>True</strong> (Igaz) értékre módosulásának dátuma és időpontja (UTC).               | 2017.06.23. 12:00:00 |


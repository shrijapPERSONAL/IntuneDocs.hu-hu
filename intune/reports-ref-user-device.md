---
title: "Felhasználók és eszközök társítása – Intune-adattárház | Microsoft Docs"
description: "Az Intune-adattárház API módosításai."
keywords: "Intune-adattárház"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 45c3e14631fdfe74cafea4a0965efac51386524a
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/04/2018
---
# <a name="user-device-association"></a>Felhasználók és eszközök társítása

A **UserDeviceAssociation** entitás tartalmazza a szervezet felhasználói hozzárendeléseit.

| Név               | Description                                                                                      | Példa                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | A felhasználó egyedi azonosítója az adattárházban. (Helyettes kulcs).                              | 123                    |
| DeviceKey          | Az eszköz egyedi azonosítója az adattárházban.                                            | 123                    |
| CreatedDateTimeUTC | A felhasználói eszköztársítás létrehozásának dátuma és időpontja. UTC formátumban.                                | 2016.11.23. 12:00:00 |
| IsDeleted          | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. | Igaz/hamis             |
| EndedDateTimeUTC   | Az IsDeleted paraméter **True** (Igaz) értékre módosulásának dátuma és időpontja (UTC).                                              | 2017.06.23. 12:00:00 |

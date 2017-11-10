---
title: "Felhasználók és eszközök társítása – Intune-adattárház | Microsoft Docs"
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
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2017
---
# <a name="user-device-association"></a>Felhasználók és eszközök társítása

A **UserDeviceAssociation** entitás tartalmazza a szervezet felhasználói hozzárendeléseit.

| Név               | Leírás                                                                                      | Példa                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | A felhasználó egyedi azonosítója az adattárházban. (Helyettes kulcs).                              | 123                    |
| DeviceKey          | Az eszköz egyedi azonosítója az adattárházban.                                            | 123                    |
| CreatedDateTimeUTC | A felhasználói eszköztársítás létrehozásának dátuma és időpontja. UTC formátumban.                                | 2016.11.23. 12:00:00 |
| IsDeleted          | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. | Igaz/hamis             |
| EndedDateTimeUTC   | Az IsDeleted paraméter **True** (Igaz) értékre módosulásának dátuma és időpontja (UTC).                                              | 2017.06.23. 12:00:00 |

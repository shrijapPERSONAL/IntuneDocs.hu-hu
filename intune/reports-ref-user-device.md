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
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2018
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

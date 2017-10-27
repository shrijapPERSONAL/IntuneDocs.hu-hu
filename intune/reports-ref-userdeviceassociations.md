---
title: "Felhasználók és eszközök társítása | Microsoft Docs"
description: "Az Intune-adattárház API-ban található entitásgyűjtemények Felhasználók és eszközök társítása kategóriájára vonatkozó referencia-témakör."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Segédlet a Felhasználók és eszközök társítása entitáshoz

A **Felhasználók és eszközök társítása** kategória azt a **Felhasználók és eszközök társítása** entitást tartalmazza, amellyel a szervezeten belüli eszköztársítások vannak definiálva.

**Felhasználók és eszközök társítása**

A **Felhasználók és eszközök társítása** entitás a szervezeten belüli eszköztársítások definiálását reprezentálja.

| Név               | Leírás                                                                                      | Példa                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | A felhasználó egyedi azonosítója az adattárházban – helyettes kulcs.                             | 123                    |
| DeviceKey          | Az eszköz egyedi azonosítója az adattárházban.                                           | 123                    |
| CreatedDateTimeUTC | A felhasználói eszköztársítás létrehozásának dátuma és időpontja (UTC).                               | 2016.11.23. 12:00:00 |
| IsDeleted          | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. | Igaz                   |
| EndedDateTimeUTC   | Az IsDeleted paraméter **True** (Igaz) értékre módosulásának dátuma és időpontja (UTC).                                         | 2017.06.23. 12:00:00 |
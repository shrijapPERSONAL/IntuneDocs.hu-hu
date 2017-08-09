---
title: "Felhasználó | Microsoft Docs"
description: "Az Intune-adattárház API-ban található entitásgyűjtemények felhasználó kategóriájára vonatkozó referencia-témakör."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>Felhasználó típusú entitás referenciája

A **Felhasználó** kategória tartalmazza az adatmodellbeli felhasználó- és ügynöktulajdonságokat meghatározó **Felhasználó** entitást.

**Felhasználó**

A **Felhasználó** entitás a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót kilistázza.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| UserKey |A felhasználó egyedi azonosítója az adattárházban – helyettes kulcs |123 |
| UserId |A felhasználó egyedi azonosítója – a UserKey-hez hasonló, de természetes kulcs |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |A felhasználó e-mail címe |John@constoso.com |
| DisplayName |A felhasználó megjelenítendő neve |István |
| IntuneLicensed |Megadja, hogy a felhasználó rendelkezik-e Intune-licenccel. |Igaz/hamis |
| IsDeleted |Jelzi, hogy frissítve lett-e a felhasználórekord.  True (Igaz) – a felhasználóhoz új, frissített mezőkből álló rekord tartozik a táblában. False (Hamis) – a felhasználó legfrissebb rekordja. |Igaz/hamis |
| StartDateInclusiveUTC |A felhasználó adattárházban történt létrehozásának dátuma és időpontja (UTC) |2016.11.23 12:00:00 |
| EndDateExclusiveUTC |Az IsDeleted paraméter True (Igaz) értékre módosulásának dátuma és időpontja (UTC) |2016.11.23 12:00:00 |
| IsCurrent |Jelzi, hogy a felhasználórekord aktuális-e az adattárházban |Igaz/hamis |
| RowLastModifiedDateTimeUTC |A felhasználó adattárházban történt utolsó módosításának dátuma és időpontja (UTC) |2016.11.23 12:00:00 |


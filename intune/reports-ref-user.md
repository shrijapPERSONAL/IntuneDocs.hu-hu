---
title: Felhasználó – Intune-adattárház
titleSuffix: Microsoft Intune
description: Az Intune-adattárház API-ban található entitásgyűjtemények felhasználó kategóriájára vonatkozó referencia-témakör.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e650f8cb713d76c44d3f3399612ee5fd6d02426
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429144"
---
# <a name="reference-for-user-entity"></a>Felhasználó típusú entitás referenciája

A **Felhasználó** kategória tartalmazza az adatmodellbeli felhasználótulajdonságokat meghatározó **Felhasználó** entitást.

## <a name="user"></a>Felhasználó

A **Felhasználó** entitás a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót kilistázza.

A **Felhasználó** entitásgyűjtemény felhasználói adatokat tartalmaz. A rekordok között akkor is ott vannak az adatgyűjtési időszakon belüli felhasználói állapotok, ha a felhasználót azóta eltávolították. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. Az elmúlt hónap adatai tartalmazzák a felhasználót és állapotát annak ellenére, hogy a felhasználó a jelentés időpontjában nincs jelen. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

|          Tulajdonság          |                                                                                                           Leírás                                                                                                          |                Példa               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | A felhasználó egyedi azonosítója az adattárházban – helyettes kulcs.                                                                                                                                                         | 123                                  |
| UserId                     | A felhasználó egyedi azonosítója – a UserKey-hez hasonló, de természetes kulcs.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | A felhasználó e-mail címe.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | A felhasználó egyszerű felhasználóneve.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | A felhasználó megjelenítendő neve.                                                                                                                                                                                                      | István                                 |
| IntuneLicensed             | Megadja, hogy a felhasználó rendelkezik-e Intune-licenccel.                                                                                                                                                                              | Igaz/hamis                           |
| IsDeleted                  | Azt jelzi, hogy a felhasználó összes engedélye lejárt-e, és a felhasználót emiatt eltávolították-e az Intune-ból. Egyetlen rekord esetén ez a jelölő nem változik. Ehelyett új rekord jön létre egy új felhasználói állapothoz. | Igaz/hamis                           |
| RowLastModifiedDateTimeUTC | A rekord adattárházban történt utolsó módosításának dátuma és időpontja (UTC)                                                                                                                                                 | 2016. 11. 23. 0:00                      |


## <a name="next-steps"></a>További lépések
 - A **Jelenlegi felhasználó** entitásgyűjtemény segítségével a jelenleg aktív felhasználókra korlátozhatja a felhasználói adatokat. További információkért lásd: [Jelenlegi felhasználó típusú entitás referenciája](reports-ref-current-user.md).
 - Annak részletesebb megismeréséhez, hogy az adattárház hogyan követi nyomon egy felhasználó Intune-beli élettartamát, lásd: [A felhasználói élettartam reprezentációja az Intune-adattárházban](reports-ref-user-timeline.md).

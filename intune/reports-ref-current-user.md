---
title: "Felhasználó – Intune-adattárház | Microsoft Docs"
description: "Az Intune-adattárház API-ban található entitásgyűjtemények felhasználó kategóriájára vonatkozó referencia-témakör."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>Aktuális felhasználó típusú entitás referenciája

Az **Aktuális felhasználó** kategória az adatmodellbeli felhasználó- és ügynöktulajdonságokat tartalmazza. Az **Aktuális felhasználó** entitásgyűjtemény a jelenleg aktív felhasználókra korlátozódik. Az entitás tartalmazza az Azure Active Directory összes olyan felhasználóját, akikhez licenc van hozzárendelve. Ez lehet Intune-, Hybrid-, vagy Microsoft Office 365-licenc. Az eltávolított felhasználók nem jelennek meg az adatgyűjtési időszakban. A felhasználói állapotváltozások előzményeit tartalmazó gyűjteményhez lásd: [Felhasználó típusú entitás referenciája](reports-ref-user.md).


## <a name="user"></a>Felhasználói

A **Felhasználó** entitás a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót kilistázza.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| UserKey |A felhasználó egyedi azonosítója az adattárházban – helyettes kulcs. |123 |
| UserId |A felhasználó egyedi azonosítója – a UserKey-hez hasonló, de természetes kulcs. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |A felhasználó e-mail címe. |John@constoso.com |
| UPN | A felhasználó egyszerű felhasználóneve. | John@constoso.com |
| DisplayName |A felhasználó megjelenítendő neve. |István |
| IntuneLicensed |Megadja, hogy a felhasználó rendelkezik-e Intune-licenccel. |Igaz/hamis |
| StartDateInclusiveUTC |A felhasználó adattárházban történt létrehozásának dátuma és időpontja (UTC). |2016.11.23. 12:00:00 |
| RowLastModifiedDateTimeUTC |A felhasználó adattárházban történt utolsó módosításának dátuma és időpontja (UTC). |2016.11.23. 12:00:00 |

## <a name="next-steps"></a>További lépések
 - A **Felhasználók** entitásgyűjtemény segítségével a jelenleg nem aktív felhasználókra is kiterjesztheti a felhasználói adatokat. További információkért lásd: [Felhasználó típusú entitás referenciája](reports-ref-user.md). 
 - Annak részletesebb megismeréséhez, hogy az adattárház miképpen követi nyomon egy felhasználó Intune-beli élettartamát, lásd: [Felhasználói élettartam ábrázolása az Intune adattárházban](reports-ref-user-timeline.md).
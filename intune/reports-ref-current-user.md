---
title: Aktuális felhasználó – Intune-adattárház
titlesuffix: Microsoft Intune
description: Az Intune-adattárház API-ban található entitásgyűjtemények felhasználó kategóriájára vonatkozó referencia-témakör.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da149ea2870880a35352e9d37a91c5c39f7a7438
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602078"
---
# <a name="reference-for-current-user-entity"></a>Aktuális felhasználó típusú entitás referenciája

Az **Aktuális felhasználó** kategória az adatmodellbeli felhasználói tulajdonságokat tartalmazza. Az **Aktuális felhasználó** entitásgyűjtemény a jelenleg aktív felhasználókra korlátozódik. Az entitás tartalmazza az Azure Active Directory összes olyan felhasználóját, akikhez licenc van hozzárendelve. Ez lehet Intune-, Hybrid-, vagy Microsoft Office 365-licenc. Az eltávolított felhasználók nem jelennek meg az Aktuális felhasználó gyűjteményben. A felhasználói állapotváltozások előzményeit tartalmazó gyűjteményhez lásd: [Felhasználó típusú entitás referenciája](reports-ref-user.md).


## <a name="current-user"></a>Aktuális felhasználó

Az **Aktuális felhasználó** entitás a vállalatnál hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználó listáját tartalmazza.

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
 - A **Felhasználók** entitásgyűjteménnyel a jelenleg nem aktív felhasználókra is kiterjesztheti a felhasználói adatokat. További információkért lásd: [Felhasználó típusú entitás referenciája](reports-ref-user.md).
 - Annak részletesebb megismeréséhez, hogy az adattárház miképpen követi nyomon egy felhasználó Intune-beli élettartamát, lásd: [Felhasználói élettartam ábrázolása az Intune adattárházban](reports-ref-user-timeline.md).

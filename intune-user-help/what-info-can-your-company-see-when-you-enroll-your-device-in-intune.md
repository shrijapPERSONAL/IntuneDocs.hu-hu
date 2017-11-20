---
title: "Milyen adatokhoz férhet hozzá a munkahelye, ha regisztrálja eszközét? | Microsoft Docs"
description: "Amit a rendszergazda láthat a felügyelt eszközön, és amit nem."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.openlocfilehash: c03985bd7ca92fe4b4e8ea163b7db421bfae09c2
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2017
---
# <a name="what-information-can-my-company-see-when-i-enroll-my-device"></a>Milyen adatok láthatók a cég számára, ha regisztrálom az eszközömet?

A céges adatok védelme érdekében az eszköznek a felügyeletre való regisztrálásával engedélyezi, hogy a cég hozzáférhessen az eszközön található bizonyos adatokhoz.

**A cég számára soha nem látható adatok**

- Hívási és böngészési előzmények
- E-mailek és SMS-ek
- Névjegyek
- Naptár
-   Jelszavak
- Képek, beleértve a Fényképezőgép alkalmazás vagy a Filmtekercs mappa tartalmát

**A cég számára minden esetben látható adatok**

- Az eszköz modellje, például iPhone 7
- Gyártó, például a Microsoft
- Operációs rendszer, például iOS
- Alkalmazásnevek, például Microsoft Word
- Az eszköz tulajdonosa
- Eszköz neve
- Sorozatszám

**A cég számára esetlegesen látható adatok**

-  Telefonszám: a **céges** eszközök esetében a teljes telefonszám látható. A **személyes** tulajdonú eszközök esetében csak a telefonszám utolsó négy számjegye látható a cég számára. Minden egyes eszköz **Tulajdonjogtípusát** megtekintheti az adott eszköz **Eszköz részletei** lapjának megnyitásával.
-  Tartózkodási hely: a cég számára soha nem látható az eszköz helye, kivéve, ha olyan felügyelt iOS-eszközzel rendelkezik, amely elveszett. [Ezt hogyan lehet megállapítani?](https://go.microsoft.com/fwlink/?linkid=853816)
- Alkalmazásleltár: ha a vállalat a Mobile Threat Defense-t használja, akkor az eszközön elérhető alkalmazásokról további információhoz is hozzáférhetnek. További információk: [Mobile Threat Defense](you-are-prompted-to-install-mtd-ios.md).

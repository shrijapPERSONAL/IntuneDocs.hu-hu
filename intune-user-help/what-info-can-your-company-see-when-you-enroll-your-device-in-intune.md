---
title: Milyen adatokhoz férhet hozzá a munkahelye, ha regisztrálja eszközét?
description: Ismerteti, hogy a rendszergazda mit láthat a felügyelt eszközön, és mit nem.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.openlocfilehash: bdf08ccac21407bc2572f1133b2fe8d45548342f
ms.sourcegitcommit: cac71802b2782700f0d52ea114089d73620cd1ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50679253"
---
# <a name="what-information-can-my-company-see-when-i-enroll-my-device"></a>Milyen adatok láthatók a cég számára, ha regisztrálom az eszközömet?

A vállalata számára nem láthatók az Ön személyes adatai, amikor eszközt regisztrál a Microsoft Intune-ban. Amikor regisztrálja eszközét, Ön engedélyezi a vállalatának bizonyos eszközadatoknak, például az eszköz típusának és sorozatszámának megtekintését. A vállalat ezt az információt az eszközön lévő vállalati adatok védelmére használja fel.

**A vállalat számára soha nem látható adatok:**

- Hívási és böngészési előzmények
- E-mailek és SMS-ek
- Névjegyek
- Naptár
-   Jelszavak
- Képek, beleértve a Fényképezőgép alkalmazás vagy a Filmtekercs mappa tartalmát

**A vállalat számára minden esetben látható adatok:**

- Eszközmodell, például Google Pixel
- Gyártó, például a Microsoft
- Operációs rendszer, például iOS
- Alkalmazásnevek, például Microsoft Word
- Az eszköz tulajdonosa
- Eszköz neve
- Sorozatszám

**A vállalat számára esetlegesen látható adatok:**

-  Telefonszám: a **céges** eszközök esetében a teljes telefonszám látható. A **személyes** tulajdonú eszközök esetében csak a telefonszám utolsó négy számjegye látható a cég számára. Minden egyes eszköz **Tulajdonjogtípusát** megtekintheti az adott eszköz **Eszköz részletei** lapjának megnyitásával.
-  Tartózkodási hely: a cég számára soha nem látható az eszköz helye, kivéve, ha olyan felügyelt iOS-eszközzel rendelkezik, amely elveszett. [Ezt hogyan lehet megállapítani?](https://go.microsoft.com/fwlink/?linkid=853816)
- Alkalmazásleltár: ha a cége a Mobile Threat Defense-t használja, akkor az iOS-eszközön elérhető alkalmazásokról további információhoz is hozzáférhet. További információk: [Mobile Threat Defense](you-are-prompted-to-install-mtd-ios.md).
- Hálózati adatok: az androidos eszközök hálózati kapcsolatairól bizonyos adatok elérhetőek lehetnek a cég informatikai részlege számára. Például, ha a cég egyes eszközeinek egy bizonyos épületen belül kell maradniuk, az eszköz azonosítja a hálózatot, amelyhez csatlakozik. 

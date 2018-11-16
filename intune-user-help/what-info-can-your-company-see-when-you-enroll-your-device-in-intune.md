---
title: Milyen adatokhoz férhet hozzá a munkahelye, ha regisztrálja eszközét?
description: Ismerteti, hogy a rendszergazda mit láthat a felügyelt eszközön, és mit nem.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/06/2018
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
ms.openlocfilehash: 63295d7e05889f5a8beb44e399f36a4fbe27544d
ms.sourcegitcommit: 76c7b315b83eb6cb5b996facf1d250fb3e22f1bc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/08/2018
ms.locfileid: "51276115"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Milyen adatok láthatók a szervezet számára, ha regisztrálom az eszközömet?

A szervezete számára nem láthatók az Ön személyes adatai, amikor eszközt regisztrál a Microsoft Intune-ban. Amikor regisztrálja eszközét, Ön engedélyezi a szervezetének bizonyos eszközadatoknak, például az eszköz típusának és sorozatszámának megtekintését. A szervezet ezt az információt az eszközön lévő vállalati adatok védelmére használja fel.

**A szervezet számára soha nem látható adatok:**

- Hívási és böngészési előzmények
- E-mailek és SMS-ek
- Névjegyek
- Naptár
-   Jelszavak
- Képek, beleértve a Fényképezőgép alkalmazás vagy a Filmtekercs mappa tartalmát
- Fájlok

**A szervezet számára mindig látható adatok:**

- Eszközmodell, például Google Pixel
- Eszköz gyártója, például a Microsoft
- Operációs rendszer és annak verziója, például iOS 12.0.1
- Alkalmazásnevek, például Microsoft Word: A személyes eszközökön a szervezet csak a felügyelt alkalmazásjegyzéket tekintheti meg. A vállalati tulajdonú eszközökön a szervezet a teljes alkalmazásleltárat láthatja.
- Az eszköz tulajdonosa
- Eszköz neve
- Eszköz sorozatszáma
- IMEI

**A szervezet számára esetlegesen látható adatok:**

-  Telefonszám: a **céges** eszközök esetében a teljes telefonszám látható. A **személyes** tulajdonú eszközök esetében csak a telefonszám utolsó négy számjegye látható a szervezet számára. Minden egyes eszköz **Tulajdonjogtípusát** megtekintheti az adott eszköz **Eszköz részletei** lapjának megnyitásával.
- Eszköz tárhelye: Ha nem tud telepíteni egy szükséges alkalmazást, a szervezet ellenőrizheti az eszköz tárhelyét, valamint hogy az elegendő-e.  
-  Tartózkodási hely: a szervezet számára soha nem látható az eszköz helye, kivéve, ha olyan felügyelt iOS-eszközzel rendelkezik, amely elveszett. [Ezt hogyan lehet megállapítani?](https://go.microsoft.com/fwlink/?linkid=853816)
- Alkalmazásleltár: ha a szervezete a Mobile Threat Defense-t használja, akkor az iOS-eszközön elérhető alkalmazásokról további információhoz is hozzáférhet. További információk: [Mobile Threat Defense](you-are-prompted-to-install-mtd-ios.md).
- Hálózati adatok: az androidos eszközök hálózati kapcsolatairól bizonyos adatok elérhetőek lehetnek a szervezet informatikai részlege számára. Például ha a szervezet egyes eszközeinek egy bizonyos épületen belül kell maradniuk, az eszköz azonosítja a hálózatot, amelyhez csatlakozik. 

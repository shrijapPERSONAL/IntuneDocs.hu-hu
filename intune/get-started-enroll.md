---
title: Az iOS-eszközök regisztrációs folyamatának ismertetése
titlesuffix: Microsoft Intune
description: Megismerheti a regisztrációs folyamatot egy iOS-eszköz teljes regisztrációs folyamatának végigkövetésével.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bdd8267701b20600d67e6927c8b55d7f9c11a34f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186766"
---
# <a name="understand-the-users-experience-enrolling-an-ios-device"></a>Az iOS-eszközök felhasználói regisztrációs folyamatának ismertetése

A Microsoft Intune segít a munkatársak mobileszközökkel való ellátásában, miközben gondoskodik a vállalati adatok védelméről. Mivel a végfelhasználók a felügyeleti konzol helyett a saját eszközeiken fognak interakcióba lépni az Intune-nal, részletesen meg kell ismernie a regisztrációs folyamatot. Ezzel a módszerrel kombinálhatja a jól kialakított megfelelőségi házirendeket a regisztrációs folyamattal, és empátiát mutathat felhasználói felé. Ez különösen fontos, mivel a felhasználók pontosan tudni fogják, hogy Ön rendszergazdaként milyen adatokat láthat:

| Amit a rendszergazda nem lát | Amit a rendszergazda lát |
|---|---|
| Hívási és böngészési előzmények | Modell |
| Tartózkodási hely | Sorozatszám |
| Személyes e-mailek | Operációs rendszer verziója |
| SMS-ek | Alkalmazásnevek |
| Névjegyek | Tulajdonos |
| A személyes fiókok jelszavai | Eszköz neve |
| Naptáresemények | Gyártó (nem Apple gyártmányú eszközök esetében) |
| Képek, beleértve a Fényképezőgép alkalmazás vagy a Filmtekercs mappa tartalmát | Telefonszám (céges eszközök esetén teljes telefonszám, személyes eszközök esetén csak az utolsó négy számjegy) |

## <a name="how-do-i-enroll-a-device"></a>Hogyan lehet regisztrálni az eszközt?

Az eszköz regisztrációja az első élmény, amelyben számos végfelhasználó részesül a vállalati erőforrások elérésekor. [Ennek az élménynek a megértése](end-user-educate.md) segíthet egy lehetséges rossz élmény jobbá alakításában.

1. Nyissa meg az **App Store-t**, és keressen rá az **Intune céges portál** kifejezésre.
2. Töltse le a **Microsoft Intune Vállalati portál** alkalmazást.
3. Nyissa meg a **Vállalati portál** alkalmazást, és írja be a tesztfelhasználó e-mail-címét és jelszavát, majd koppintson a **Bejelentkezés** elemre.
4. Frissítse az ideiglenes jelszavát egy újra.
5. A **Vállalati hozzáférés beállítása** lapon koppintson az **Eszközregisztráció** elemre.
6. A **Miért érdemes regisztrálni az eszközt** lapon olvassa el, milyen feladatokat végezhet a felhasználó, ha regisztrálja az eszközét, majd koppintson a **Folytatás** gombra.
7. Tekintse át a regisztrációval a felhasználó számára engedélyezett jogosultságok listáját, majd koppintson a **Folytatás** gombra.
8. Tekintse át mi az, amint a rendszergazdák megtekinthetnek az eszközön, és mi az, amit nem, majd koppintson a **Folytatás** gombra.
9. A **Mi a következő lépés?** lapon olvassa el, mi történik a regisztráció során, majd koppintson a **Regisztráció** elemre.
10. A **Profil telepítése** lapon koppintson a **Telepítés** gombra, majd ha az eszköz kéri, adja meg a jelszavát.
11. Koppintson a **Telepítés** elemre.
12. Újra a **Telepítés** elemre koppintva jelezze, hogy elolvasta a figyelmeztetést.
13. A **Figyelmeztetés** előugró ablakban koppintson a **Megbízható** elemre.
14. Amikor a rendszer a profil telepítésének befejezését jelző képernyőre vált, koppintson a **Kész** elemre.
15. Megjelenik az „Eszköz regisztrációja” üzenet a képernyőn, majd az eszköz sikeres regisztrációjáról szóló üzenet. Megjelenik egy előugró ablak, amely arra kéri, hogy nyissa meg a lapot a Céges portálon. Koppintson a **Megnyitás** gombra.
16. Visszatér a **Vállalati hozzáférés beállítása** képernyőre. Ha nem rendelkezik beállított tesztszabályzatokkal, akkor az eszköznek megfelelőnek kell látszania. Ha rendelkezik bármilyen tesztszabályzattal, akkor az **Eszközmegfelelőség** elemre koppintva megjelenik, hogy milyen dolgokat kell végrehajtani, hogy az eszköz biztonságos legyen.

## <a name="next-steps"></a>További lépések

[Ismerkedés az alkalmazások felvételével](get-started-apps.md) – Alkalmazásokat kereshet és adhat hozzá az eszközökhöz, hogy az alkalmazottak elvégezhessék a munkát.

## <a name="learn-more"></a>További információ

* [Eszközregisztrációs lehetőségek az Intune-hoz](enrollment-options.md)
* [Saját eszközök használatának engedélyezése az Intune-ban](byod-enable.md)
* [A regisztrációs és az eszközkezelési folyamat megismertetése a végfelhasználókkal](end-user-educate.md)

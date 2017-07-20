---
title: "Az eszközök regisztrációjának első lépései"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36e658cebdfd23547e3c376124289046f81acc1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-enrolling-devices"></a>Az eszközök regisztrációjának első lépései

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![A céges portál alkalmazást megjelenítő iOS-eszköz. A regisztrációs folyamatban a felhasználó számára megjelenített első képernyő.](/intune-user-help/media/ios-enroll-1a-comp-access-setup.png)

A Microsoft Intune segít a munkatársak mobileszközökkel való ellátásában, miközben gondoskodik a vállalati adatok védelméről. Mivel a végfelhasználók a felügyeleti konzol helyett a saját eszközeiken fognak interakcióba lépni az Intune-nal, részletesen meg kell ismernie a regisztrációs folyamatot. Ezzel a módszerrel kombinálhatja a jól kialakított megfelelőségi házirendeket a regisztrációs folyamattal, és empátiát mutathat felhasználói felé. Ez különösen fontos, mivel a felhasználók pontosan tudni fogják, hogy Ön rendszergazdaként milyen adatokat láthat:

## <a name="what-it-cannot-see"></a>Amit a rendszergazda nem lát
* Hívási és böngészési előzmények
* Tartózkodási hely
* Személyes e-mailek
* SMS-ek
* Névjegyek
* A személyes fiókok jelszavai
* Naptáresemények
* Képek, beleértve a Fényképezőgép alkalmazás vagy a Filmtekercs mappa tartalmát

## <a name="what-it-can-see"></a>Amit a rendszergazda lát
* Modell
* Sorozatszám
* Operációs rendszer verziója
* Alkalmazásnevek
* Tulajdonos
* Eszköz neve
* Gyártó (nem Apple gyártmányú eszközök esetében)
* Telefonszám (céges eszközök esetén teljes telefonszám, személyes eszközök esetén csak az utolsó négy számjegy)

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
---
title: A Céges portálon történő regisztráció megszakítása az Intune-ban
titlesuffix: Microsoft Intune
description: A Céges portállal történő regisztráció megszakításáról szóló jelentés ismertetése.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: ba1ee5a6811457b8c6e7343de7355261a2fcecdb
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236754"
---
# <a name="company-portal-abandonment-report"></a>Céges portállal történő regisztráció megszakítása – jelentés

Ez a jelentés elmagyarázza, hogy a Céges portálon belül hol szakítják meg a regisztrációs folyamatot a regisztráló felhasználók.

A jelentés megtekintéséhez válassza az **Intune** > **Eszközök beléptetése** > **Céges portállal történő regisztráció megszakítása** lehetőséget.

A megszakítással kapcsolatos információk alapján frissítheti az előkészítési dokumentumokat, hogy segítsen a felhasználóknak a regisztrációs folyamat elvégzésében. Ha például sok felhasználó szakítja meg a folyamatot a Felhasználási feltételeknél, akkor megvizsgálhatja ezt a területet, és intuitívebbé teheti a felhasználók számára.

## <a name="what-is-abandonment"></a>Mit jelent a megszakítás?

Megszakítás az, ha a felhasználó az alábbiak bármelyikét teszi:

-   Explicit módon a regisztrációt leállító műveletet választ
-   Bezárja a Céges portált a regisztráció során
-   Több mint 30 percet tölt el egy regisztrációs szakasszal, mielőtt a következővel folytatná

Ha egy felhasználó úgy dönt, hogy megszakítja a regisztrációt, és többször újraindítja, az több kísérletként és több megszakításként jelenik meg. Ha egy felhasználó több, mint 30 percig várakozik, mielőtt a következő regisztrációs képernyőre lépne, az több megszakításnak számít.

## <a name="what-does-the-report-show"></a>Mi mutat meg a jelentés?

A regisztrációs jelentés iOS- és Android-eszközökre vonatkozó adatokat is magában foglal.

A jelentés az elmúlt két hétre vonatkozó adatokat jelenít meg, de szűrheti a jelentést az elmúlt 30 napban bármely időszak megjelenítésére.

Szűrhet a dátumtartomány, az operációs rendszer és a regisztrációs szakasz alapján a **Szűrő** kiválasztásával.

### <a name="number-and-percentage-tiles"></a>Szám és százalékos arány csempék

A jelentés tetején látható a megszakított jelentések száma és százalékos aránya az összes regisztrációhoz viszonyítva.

-   Kezdeményezett regisztrációk: A regisztrációs próbálkozások száma.
-   Megszakított regisztrációk: A regisztrációs próbálkozások száma, amelyek nem eredményeztek teljes mértékben regisztrált és megfelelő eszközt.
-   Megszakítási arány: A megszakított regisztrációs próbálkozások (megszakított regisztrációk / kezdeményezett regisztrációk) százalékos aránya.

### <a name="line-graph"></a>Vonaldiagram

A vonaldiagram jeleníti meg a megszakítások napi számát mind a négy fontos regisztrációs szakaszhoz:

-   Beállítási ellenőrzőlista
-   Platformképernyők
-   Használati feltételek
-   Megfelelőség/aktiválás

### <a name="user-abandonment-actions"></a>Felhasználói megszakítási műveletek

Az alábbi táblázatokban a megszakításnak minősülő felhasználói műveletek listája látható. Regisztrációs képernyők példáinak megtekintéséhez megnézheti az [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) és az [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) rendszerben történő regisztrációról készült videókat. 


#### <a name="setup-checklist-section"></a>Beállítási ellenőrzőlista szakasz

| Regisztrációmegszakítás neve | Képernyő vagy folyamat | Platform | Művelet |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | A rendszer arra kéri, hogy nyisson meg egy oldalt a Céges portálon. | iOS/Android | **Mégse** |
| EnrollmentWrapUp | Eszközregisztrációs képernyő, ami addig látható, amíg be nem fejeződik a **vállalati erőforrások betöltése** | iOS/Android | Időtartam > 30 perc |
| DeviceCategory | Eszközkategória kiválasztása (ha a rendszergazda beállította), addig látható, amíg rá nem kattint a **Kész** gombra | iOS/Android | Időtartam > 30 perc |
| PreEnrollmentWizard | Hozzáférés-beállítási képernyő, ha megkezdte a regisztrációt, de visszatért a hozzáférés-beállításhoz | iOS/Android| **Elhalasztás** |
| PreEnrollmentWizard | Hozzáférés-beállítási képernyő, amely addig látható, amíg rá nem kattint a **Tovább** gombra a **Következő lépések** képernyőn | iOS/Android | Időtartam > 30 perc |

#### <a name="platform-screens-section"></a>Platformképernyők szakasz

| Regisztrációmegszakítás neve | Képernyő vagy folyamat | Platform | Művelet |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Rákérdezés a konfigurációs profil megjelenítésére | iOS | **Figyelmen kívül hagyás** |
| iOSProfileLaunch | Profilképernyő telepítése | iOS | **Mégse** |
| iOSProfileLaunch | Rákérdezés, hogy megbízik-e a profil forrásában az eszköz regisztrációjához | iOS | **Mégse** |
| iOSProfileLaunch | Profiltelepítési képernyő, amely a profil telepítésének befejeződéséig látható | iOS | Időtartam > 30 perc |
| AndroidPermissions | Eszközadminisztrátor aktiválása képernyő | Android | **Mégse** |
| AndroidPermissions | A hívások kezdeményezésének és kezelésének jóváhagyáskérésétől addig, amíg az eszközrendszergazda végre nem hajtja az **aktiválást** | Android | Időtartam > 30 perc |
| KnoxActivation | KLMS-ügynök aktiválása (csak Samsung) | Android| **Mégse** |
| KnoxActivation | KLMS-ügynök aktiválása a **megerősítésig** | Android | Időtartam > 30 perc|

#### <a name="terms-of-use-section"></a>Használati feltételek szakasz

| Regisztrációmegszakítás neve | Képernyő vagy folyamat | Platform | Művelet |
| ---- |---- |---- |---- |
| TermsofUse | Használati feltételek (ha a rendszergazda konfigurálta) | iOS/Android | **Összes elutasítása** |
| TermsofUse | Használati feltételek megjelenítése az **Összes elfogadása** kiválasztásáig | iOS/Android | Időtartam > 30 perc |

#### <a name="complianceactivation-section"></a>Megfelelőség/aktiválás képernyő

| Regisztrációmegszakítás neve | Képernyő vagy folyamat | Platform | Művelet |
| ---- |---- |---- |---- |
| Megfelelőség | Eszközmegfelelőség (ha a rendszergazda beállította) nem zöldként jelenik meg a regisztráció utáni hozzáférés-beállítás esetén| iOS/Android | **Elhalasztás** |
| Megfelelőség | Az eszközmegfelelőség nem zöldként jelenik meg, amíg nem frissíti zöldként való megjelenítésre | iOS/Android | Időtartam > 30 perc |
| Aktiválás | Regisztrációaktiválás (ha a rendszergazda beállította) nem zöldként jelenik meg a hozzáférés beállításakor | iOS/Android | **Elhalasztás** |
| Megfelelőség | Az eszközaktiválás nem zöldként jelenik meg, amíg nem frissíti zöldként való megjelenítésre | iOS/Android | Időtartam > 30 perc |

## <a name="next-steps"></a>További lépések

A megszakítási arányok ellenőrzése után áttekintheti a [regisztrációs beállításokat](enrollment-options.md), hogy megtekintse, végezhet-e valamilyen módosítást a regisztrációs élmény javításához.
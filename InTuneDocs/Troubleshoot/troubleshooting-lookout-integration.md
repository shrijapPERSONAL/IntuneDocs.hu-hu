---
title: "A Lookout-integráció hibaelhárítása | Microsoft Intune"
description: "Ez a témakör a Lookout-integráció leggyakoribb problémáinak hibaelhárítását ismerteti"
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5acf5c707a93aa0b5e7cefdcb0b160af09b9cf70


---

# A Lookout Intune-nal való integrációjának hibaelhárítása
Ez a témakör ismertet néhány gyakori problémát, amely a Lookout mobilfenyegetések elleni védelem (MTP) beállításával kapcsolatban merülhet fel.
## Bejelentkezési hibák elhárítása
### 403-as hibák
A [Lookout MTP-konzolra](https://aad.lookout.com) való bejelentkezéskor a következő 403-as hibaüzenet jelenhet meg: **Ön nem jogosult hozzáférni a szolgáltatáshoz** Erre abban az esetben kerülhet sor, ha az Ön által megadott felhasználónév nem tagja a Lookout MTP eléréséhez konfigurált Azure Active Directory (Azure AD) csoportnak.

A Lookout MTP beállításai csak konfigurált Azure AD-csoport felhasználói számára engedélyezik a hozzáférést. Ha nem biztos benne, hogy melyik csoporthoz állítottak be Lookout MTP-hozzáférést, forduljon a Lookout támogatási csapatához.

A Lookout támogatási csapatát a következőképpen érheti el:

* E-mail: enterprisesupport@lookout.com
* Jelentkezzen be az [MTP-konzolon](http://aad.lookout.com) és keresse meg a **Támogatás** modult.
* A https://enterprise.support.lookout.com/hc/en-us/requests webhelyen nyújtson be támogatási kérést.

### Ha nem tud bejelentkezni
Előfordulhat, hogy az alábbi hibát látja, ha az Azure AD globális rendszergazdája nem fogadta el a kezdeti Lookout-telepítést.

![képernyőfelvétel, amelyen a Lookout bejelentkezési képernyője bejelentkezési hibát mutat](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

A probléma megoldásához jelentkezzen be a https://aad.lookout.com/les?action=consent oldalon és fogadja el a telepítés indításáról szóló kérést. Ezzel kapcsolatban bővebb információt a [Lookout MTP-előfizetés beállítása](set-up-your-subscription-with-lookout-mtp.md) című témakörben talál

## Az eszköz állapotával kapcsolatos problémák elhárítása

### Az eszköz nem jelenik meg a Lookout MTP-konzol eszközlistáján

Ez az alábbi esetek valamelyikében fordulhat elő:
* Ha az adott eszköz tulajdonosa nem tagja a **Lookout MTP-konzolon** megadott **Beléptetési csoportnak**.  A **Rendszer** modulból nyissa meg az  **Intune-összekötő** lapot, és nézze meg a **Beléptetési felügyelet** beállításait.  Ekkor egy vagy több beléptetésre konfigurált Azure AD-csoportnak kell megjelennie.  Ellenőrizze, hogy az a felhasználó, aki a hiányzó eszköz tulajdonosa, tagja-e a megadott Azure AD-csoportok valamelyikének.  Új felhasználó beléptetési csoporthoz való hozzáadását követően a beállított lekérdezési időköz elteltéig tarthat, amíg a felhasználó megjelenik a Lookout MTP-konzol **Eszközök** moduljában (az alapértelmezett érték 5 perc).

* Ha az eszközt nem támogatja a Lookout MTP.  A nem támogatott eszközök a Lookout MTP-konzolon az összekötő beállításainak **Kezelt eszközök** részében jelennek meg.

### Az eszközt a rendszer továbbra is **függőben lévőként** jelenti

Ha egy eszköz **függőben lévőként** jelenik meg, az azt jelenti, hogy a végfelhasználó még nem nyitotta meg a Lookout for Work alkalmazást, és nem koppintott az **Aktiválás** gombra. Az eszközök Lookout for Work alkalmazással történő aktiválásáról bővebben a következő témakörben talál információt:

[A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### A Lookout MTP-konzolon az eszköz aktívként jelenik meg, de nem rendelkezik eszköz-azonosítóval.  
Ez azt jelenti, hogy az eszköz tulajdonosa nem tagja a Lookout MTP-konzolon megadott beléptetési csoportnak.   Az eszköz abban az esetben kerülhet ebbe az állapotba, ha az eszköz tulajdonosát eltávolították a beléptetési csoportból vagy eltávolították az eszköz tulajdonosának beléptetési csoportját.

A Lookout MTP-konzol **Rendszer** moduljából nyissa meg az  **Intune-összekötő** lapot, és nézze meg a **Beléptetés** beállításait.  Ekkor egy vagy több beléptetésre konfigurált Azure AD-csoportnak kell megjelennie.  Ellenőrizze, hogy az a felhasználó, aki az adott eszköz tulajdonosa, tagja-e a megadott Azure AD-csoportok valamelyikének.  

Amíg az eszköz ebben az állapotban van, a Lookout továbbra is értesíti a felhasználót az észlelt fenyegetésekről, de nem küld fenyegetés-információkat az Intune-hoz.

### Az eszköz leválasztott állapotúként jelenik meg

A leválasztott állapot annyit jelent, hogy az eszköz meghatározott ideje nem kommunikált a Lookout MTP-vel (az időtartam alapértelmezés szerint 30 nap, a minimális megengedett időtartam 7 nap). Ez annyit jelent, hogy a Vállalati portál vagy a Lookout for Work alkalmazást nem telepítették az eszközön, vagy eltávolították róla. A probléma megoldásához újra kell telepíteni ezeket az alkalmazásokat. Amikor a felhasználó megnyitja és aktiválja a Lookout for Work alkalmazást, az eszköz újraszinkronizálja magát a Lookout MTP-vel és az Intune-nal.    

### Újraszinkronizálás kikényszerítése az eszközön
A Lookout MTP-konzol **Eszközök** moduljából a rendszergazda kiválaszthatja és törölheti az eszközt.   Amikor a felhasználó legközelebb megnyitja a Lookout for Work alkalmazást és az **Aktiválás** elemre koppint, az eszköz teljes újraszinkronizálást hajt végre.

### Az eszköz tulajdonosa már nem használja az eszközt
Az eszköz adatain teljes törlést kell végrehajtani, és fel kell szólítani az új felhasználót, hogy regisztráljon.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza ki az eszközt, kattintson a jobb egérgombbal, majd válassza a **Kivonás/Teljes törlés** lehetőséget az eszköz felügyelet alól való kivonásához. Kivonása után törölheti az eszközt.

![képernyőfelvétel az Intune felügyeleti konzolon megjelenő kivonás/teljes törlés lehetőségről](../media/mtp/mtp-retire-device-intune-console.png)

A Lookout MTP-konzol **Eszközök** moduljában is választhatja a **Törlés** lehetőséget.  

Amennyiben az új felhasználó tagja valamelyik, a Lookout MTP-konzolon megadott beléptetési csoportnak, az eszköz megjelenik, miután az Azure AD társítja azt az új felhasználóval.

## Megfelelőség-helyreállítási munkafolyamatok
[A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[A Lookout for Work által az Android-eszközön talált fenyegetést kell elhárítani ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### További információ
[Az előfizetés konfigurálása a Lookout MTP használatához](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Oct16_HO1-->



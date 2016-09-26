---
title: "A Lookout for Work alkalmazás telepítése | Microsoft Intune"
description: "Lookout for Work alkalmazások konfigurálása és telepítése Android operációs rendszeren."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Lookout for Work alkalmazások konfigurálása és telepítése
Ebben a kiadásban az Android 4.1-es és újabb rendszert futtató eszközökön telepített Lookout for Work alkalmazás támogatott.
## Android
A jelen szakasz a Lookout for Work alkalmazás konfigurálását és központi telepítését ismerteti az Intune-ban regisztrált Android-eszközökön.  
* 1. lépés: A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) válassza az **Alkalmazások** majd az **Alkalmazások hozzáadása** elemet.   
* 2. lépés: A közzétevő **Szoftvertelepítés** lapján válassza a **Külső hivatkozás** elemet és adja meg a következő URL-címet: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Ne jelölje ki a kezelt böngészőt előíró jelölőnégyzetet.

* 3. lépés: A **Szoftverleírás** lapon adja meg a következő információkat:
  * **Közzétevő:** Lookout Mobile Security
  * **Név:** Lookout for Work
  * **Leírás:** A Lookout a leghatékonyabb védelmet kínálja a mobil fenyegetésekkel szemben az eszköz biztonsága érdekében. Ha telepíti a Lookout alkalmazást az eszközön, az védelmet nyújt a fenyegetésekkel szemben és riasztja a felhasználót és a vállalati rendszergazdát, ha ilyet talál.
  * **Kategória:** Számítógép-felügyelet
* 4. lépés: A sikeres telepítést követően a következő üzenet jelenik meg: **Az adatok feltöltése a Microsoft Intune-ba sikeresen befejeződött**.

Ha az Intune-konzolon az **Alkalmazások** elemre kattint, a listában megjelenik a Lookout for Work alkalmazás ![az Intune felügyeleti konzol alkalmazások lapjának képernyőképe, amelyen a listában látható a Lookout for Work alkalmazás](../media/mtp/lookout-app-listed-intune-console.png)

5. lépés: Ezen a ponton az Intune már képes a Lookout for Work Android alkalmazás központi telepítésére.   Az alkalmazást úgy telepítheti a felhasználók részére, hogy kijelöli a fenti képernyőképen látható Lookout for Work alkalmazást, és a kiválasztja a **Központi telepítés kezelése** lehetőséget.

Ugyanazokat a felhasználókat kell kiválasztania, akiket hozzáadott a Beléptetés kezelése opcióhoz a Lookout MTP-konzolon.  A felhasználói csoportok Lookout MTP-hez történő hozzáadásáról bővebben lásd [Az előfizetés konfigurálása a Lookout MTP használatához](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) című szakasz 3. lépését.
>[!IMPORTANT]
> Az Intune alkalmazástelepítési varázslója nem érzékeli az Azure AD felhasználói csoportokat; ezek helyett az Intune felhasználói csoportokat használja. Ennek megfelelően a Lookout MTP-konzolon az [ebben a témakörben](plan-your-user-and-device-groups.md) leírtak szerint beléptetett Azure AD felhasználói csoport alapján létre kell hoznia egy Intune felhasználói csoportot.

6. lépés: Válassza a **Kötelező telepítés** opciót, hogy a Lookout alkalmazás telepítését kötelezővé tegye a felhasználók eszközein.

### Eszköz aktiválása
A **Kötelező telepítés** opció kiválasztása esetén a központi telepítéshez az Intune leküldi a Lookout for Work alkalmazást az eszközökre.   

Amikor a felhasználó megnyitja a Lookout for Work alkalmazást az eszközön, a rendszer felszólítja a felhasználót, hogy aktiválja az alkalmazást, majd válassza a Bejelentkezés Azure Active Directoryval opciót. A végfelhasználói folyamat részletes áttekintése a következő témakörökben található:

* [A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [El kell hárítania egy fenyegetést, amit a Lookout for Work talált az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## További lépések
* [Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->



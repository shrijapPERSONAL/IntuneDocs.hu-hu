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
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Lookout for Work alkalmazások konfigurálása és telepítése
Ez a cikk részletes információval szolgál arról, hogyan konfigurálhatja és telepítheti a Lookout for Work alkalmazást a regisztrált és az Android 4.1-es vagy későbbi verzióját futtató eszközökön.

* **1. lépés: **A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza az **Alkalmazások**, majd az **Alkalmazások felvétele** lehetőséget.   
* **2. lépés:** A közzétevő **Szoftver telepítése** lapján válassza a **Külső hivatkozás** elemet, és adja meg a következő URL-címet: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Ne jelölje ki a kezelt böngészőt előíró jelölőnégyzetet.

* **3. lépés:** A **Szoftver leírása** lapon adja meg a következő információkat:
  * **Közzétevő:** Lookout Mobile Security
  * **Név:** Lookout for Work
  * **Leírás:** A Lookout a leghatékonyabb védelmet kínálja a mobil fenyegetésekkel szemben az eszköz biztonsága érdekében. Ha telepíti a Lookout alkalmazást az eszközön, az védelmet nyújt a fenyegetésekkel szemben, és riasztja a felhasználót és a cég rendszergazdáját, ha ilyet talál.
  * **Kategória:** Számítógép-felügyelet
* **4. lépés:** A sikeres telepítést követően a következő üzenet jelenik meg: **Sikeresen befejeződött az adatok feltöltése a Microsoft Intune-ba**.

Ha az Intune felügyeleti konzolján az **Alkalmazások** elemre kattint, a listában megjelenik a Lookout for Work alkalmazás ![az Intune felügyeleti konzolja Alkalmazások lapjának képernyőképe, amelyen a listában látható a Lookout for Work alkalmazás](../media/mtp/lookout-app-listed-intune-console.png)

**Az alkalmazást úgy telepítheti a felhasználók részére**, hogy kijelöli a fenti képernyőképen látható Lookout for Work alkalmazást, és a **Központi telepítés kezelése** lehetőséget választja.

Ugyanazokat a felhasználókat kell kiválasztania, akiket a Lookout MTP-konzolon az Enrollment Management (Regisztráció kezelése) beállítás alatt felvett.  A felhasználói csoportok Lookout MTP-hez történő hozzáadásáról bővebben lásd [Az előfizetés konfigurálása a Lookout MTP használatához](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) című szakasz 3. lépését.
>[!IMPORTANT]
> Az Intune alkalmazástelepítési varázslója nem érzékeli az Azure AD-beli felhasználói csoportokat; ezek helyett az Intune-alapú felhasználói csoportokat használja, így azon az Azure AD-beli felhasználói csoporton alapuló Intune-os felhasználói csoportot kell létrehoznia, amely [ennek](plan-your-user-and-device-groups.md) a témakörnek megfelelően lett regisztrálva a Lookout MTP-konzolon.

Válassza a **Szükséges telepítés** beállítást, hogy a Lookout alkalmazás telepítését kötelezővé tegye a felhasználók eszközein.


A **Kötelező telepítés** opció kiválasztása esetén a központi telepítéshez az Intune leküldi a Lookout for Work alkalmazást az eszközökre.   

Amikor a felhasználó megnyitja a Lookout for Work alkalmazást az eszközön, a rendszer felszólítja a felhasználót, hogy aktiválja az alkalmazást, majd válassza a Bejelentkezés Azure Active Directoryval opciót. A végfelhasználói folyamat részletes áttekintése a következő témakörökben található:

* [A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [El kell hárítania egy fenyegetést, amit a Lookout for Work talált az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## További lépések
* [Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->



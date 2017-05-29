---
title: "Új PIN-kód kérése a Céges portál webhelyén | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 9220eecc32ee27725454a48484608af5f4ea0e83
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Az eszköz jelszavának alaphelyzetbe állítása a Vállalati portál webhelyén

Ha elveszíti egy Intune-ban regisztrált eszköz PIN-kódját vagy jelszavát, a [Céges portál webhelyen](http://portal.manage.microsoft.com) kérhet újat. A Vállalati portál webhelyét az Intune-ban regisztrált számítógépek és eszközök felügyeletére, illetve a Vállalati portál alkalmazásban elvégezhető legtöbb feladat végrehajtására használhatja.

> [!NOTE]
> Előfordulhat, hogy a **Jelszó alaphelyzetbe állítása** gomb nem jelenik meg a Vállalati portál webhelyén. Ebben az esetben forduljon a rendszergazdához támogatásért a Vállalati portál webhelyén.

A jelszó alaphelyzetbe állítása:

1.    A [Céges portál webhelyen](http://portal.manage.microsoft.com) koppintson a __menü__ gombra ![A menügomb képe, három vízszintes vonal párhuzamosan elhelyezve egymás alá.](/Intune/whats-new/media/CP_hamburger_menu.png), majd válassza az __Saját eszközök__ menüpontot.

2. A __Saját eszközök__ oldalon válassza ki annak az eszköznek a nevét, amelyiknek a jelszavát alaphelyzetbe kívánja állítani.

  ![Képernyőkép a Saját eszközök oldalról, amelyen néhány azonosítatlan eszköz látható a nem felsorolt eszközök regisztrálására, illetve az azonosítatlan eszközök azonosítására felszólító szalagcím felett.](./media/macOS_enroll_002_tap_here_banner.png)

3.    Az adott eszköz lehetőségei egy előreugró ablakban nyílnak meg. Válassza a **Jelszó alaphelyzetbe állítása** lehetőséget.

    ![A kiválasztott eszközzel kapcsolatos összes lehetőség a Céges portál webhelyén, többek között az Átnevezés, az Eltávolítás, az Eszköz alaphelyzetbe állítása, a Jelszó alaphelyzetbe állítása és a Távoli zárolás lehetőségei. ](./media/iwp-screen-with-all-options.png)

4.  Egy értesítésszalag jelenik meg, ahol megerősítheti, hogy jelszavát alaphelyzetbe kívánja állítani, és tájékoztatja, hogy az eszköz ezt követően kijelentkezik a szolgáltatásból. Mielőtt ismét bejelentkezne, 5 percet kell várnia.

  ![A jelszó alaphelyzetbe állításának megerősítésére felszólító értesítésszalag az eszköz jelszavának alaphelyzetbe állítására figyelmeztető és a felhasználó kijelentkeztetésével kapcsolatos értesítéssel. A felhasználó a Kijelentkezés és a Mégse gombokat használhatja.](./media/iwp-reset-passcode-popup.png)

5.  Válassza a **Kijelentkezés** lehetőséget. Még egy utolsó értesítést fog látni az eszköz PIN-kódjának eltávolításáról. Ha nincs önnél az eszköz, ne távolítsa el a PIN-kódot, mert akinél az eszköz van, az ezután hozzáférhet a rajta található személyes és céges adatokhoz egyaránt. 

  ![A jelszó alaphelyzetbe állításának megerősítésére felszólító második értesítésszalag az eszköz jelszavának alaphelyzetbe állítására figyelmeztető és a jelszó eszközről történő eltávolításával kapcsolatos értesítéssel. Ezen kívül arról is tájékoztat, hogy miként lehet új jelszót beállítani az eszköz beállításainak segítségével.](./media/iwp-reset-passcode-2nd-popup.png)

  A különböző eszközök eltérő hozzáférési kódokat használnak.

  **Android:** Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre.

  **iOS:** Eltávolítja a meglévő jelszót, és nem hoz létre ideiglenes jelszót. Ha a Touch ID ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához vagy vásárláshoz, azt újra be kell állítania.

  **Windows 10 Mobile:** Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre. Ha a Windows Hello arcfelismerési funkcióját használja a bejelentkezéshez, az továbbra is támogatott lesz.
    
  **Windows Phone 8.1:** Eltávolítja a meglévő jelszót, és egy számokból álló ideiglenes jelszót hoz létre.

  Androidos és windowsos eszközöknél az ideiglenes jelszó az **Eszköz adatai** területen fog megjelenni. 

6.  Oldja fel az eszköz zárolását, és adjon meg egy új jelszót vagy módosítsa az ideiglenes jelszót az eszköz **Beállítások** menüjében.

Ha szeretne egy megerősítő értesítést megjeleníteni arról, hogy a jelszó átállítása sikeresen megtörtént, kattintson a Vállalati portál webhelyének felső sarkában található értesítésjelzőre.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).


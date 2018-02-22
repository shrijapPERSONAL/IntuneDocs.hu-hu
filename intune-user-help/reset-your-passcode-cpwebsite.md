---
title: "Új PIN-kód kérése a Céges portál webhelyén | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 06/23/2017
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
ms.openlocfilehash: 1d9321838cdf7721410a1ba204dd02bd868dcd72
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2018
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Az eszköz jelszavának alaphelyzetbe állítása a Vállalati portál webhelyén

Ha elveszíti egy Intune-ban regisztrált eszköz PIN-kódját vagy jelszavát, a [Céges portál webhelyen](https://portal.manage.microsoft.com#HelpDeskDialog) kérhet újat. A Vállalati portál webhelyét az Intune-ban regisztrált számítógépek és eszközök felügyeletére, illetve a Vállalati portál alkalmazásban elvégezhető legtöbb feladat végrehajtására használhatja.

> [!NOTE]
> Regisztrált céges eszköz használata esetén előfordulhat, hogy a Jelszó alaphelyzetbe állítása gomb nem jelenik meg a Céges portál webhelyén. Ha ezt tapasztalja, kérje meg a cég informatikai támogatási szolgálatát, hogy állítsa alaphelyzetbe a jelszót.

A jelszó alaphelyzetbe állítása:

1.  A [Céges portál webhelyen](https://portal.manage.microsoft.com#HelpDeskDialog) koppintson a __menü__ gombra ![A menügomb képe, három vízszintes vonal párhuzamosan elhelyezve egymás alá.](/intune/media/CP_hamburger_menu.png), majd válassza az __Saját eszközök__ menüpontot.

2. A __Saját eszközök__ oldalon válassza ki annak az eszköznek a nevét, amelyiknek a jelszavát alaphelyzetbe kívánja állítani.

  ![Képernyőkép a Saját eszköz lapról, amelyen különböző azonosítatlan eszközök láthatók a listán nem szereplő eszközök regisztrálását vagy az azonosítatlan eszközök azonosítását felajánló szalagcím felett.](./media/macOS_enroll_002_tap_here_banner.png)

3.  Az adott eszköz lehetőségei egy előreugró ablakban nyílnak meg. Válassza a **Jelszó alaphelyzetbe állítása** lehetőséget.

    ![A kiválasztott eszközzel kapcsolatos összes lehetőség a Céges portál webhelyén, többek között az Átnevezés, az Eltávolítás, az Eszköz alaphelyzetbe állítása, a Jelszó alaphelyzetbe állítása és a Távoli zárolás lehetőségei. ](./media/iwp-screen-with-all-options.png)

4.  Egy értesítésszalag jelenik meg, ahol megerősítheti, hogy jelszavát alaphelyzetbe kívánja állítani, és tájékoztatja, hogy az eszköz ezt követően kijelentkezik a szolgáltatásból. Mielőtt ismét bejelentkezne, 5 percet kell várnia.

  ![A jelszó alaphelyzetbe állításának megerősítésére felszólító értesítésszalag az eszköz jelszavának alaphelyzetbe állítására figyelmeztető és a felhasználó kijelentkeztetésével kapcsolatos értesítéssel. A felhasználó a Kijelentkezés és a Mégse gombokat használhatja.](./media/iwp-reset-passcode-popup.png)

5.  Válassza a **Kijelentkezés** lehetőséget. Még egy utolsó értesítést fog látni az eszköz PIN-kódjának eltávolításáról. Ha nincs önnél az eszköz, ne távolítsa el a PIN-kódot, mert akinél az eszköz van, az ezután hozzáférhet a rajta található személyes és céges adatokhoz egyaránt. 

  ![A jelszó alaphelyzetbe állításának megerősítésére felszólító második értesítésszalag az eszköz jelszavának alaphelyzetbe állítására figyelmeztető és a jelszó eszközről történő eltávolításával kapcsolatos értesítéssel. Ezen kívül arról is tájékoztat, hogy miként lehet új jelszót beállítani az eszköz beállításainak segítségével.](./media/iwp-reset-passcode-2nd-popup.png)

  A különböző eszközök eltérő hozzáférési kódokat használnak.

  **Android:** Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre. 
  
  > [!NOTE]
  > Android 7.0-s és újabb verziók esetén az eszköz jelszava nem állítható alaphelyzetbe. Ha elfelejti a jelszót, ezeket az eszközöket a gyári beállításokra kell visszaállítani.

  **iOS:** Eltávolítja a meglévő jelszót, és nem hoz létre ideiglenes jelszót. Ha a Touch ID ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához vagy vásárláshoz, azt újra be kell állítania.

  **Windows 10 Mobile:** Eltávolítja a meglévő jelszót, és egy betűkből és számokból álló ideiglenes jelszót hoz létre. Ha a Windows Hello arcfelismerési funkcióját használja a bejelentkezéshez, az továbbra is támogatott lesz.
    
  **Windows Phone 8.1:** Eltávolítja a meglévő jelszót, és egy számokból álló ideiglenes jelszót hoz létre.

  Androidos és windowsos eszközöknél az ideiglenes jelszó az **Eszköz adatai** területen fog megjelenni. 

6.  Oldja fel az eszköz zárolását, és adjon meg egy új jelszót vagy módosítsa az ideiglenes jelszót az eszköz **Beállítások** menüjében.

Ha szeretne egy megerősítő értesítést megjeleníteni arról, hogy a jelszó átállítása sikeresen megtörtént, kattintson a Vállalati portál webhelyének felső sarkában található értesítésjelzőre.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).

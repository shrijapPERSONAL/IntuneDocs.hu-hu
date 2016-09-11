---
title: "Diagnosztikai adatokat tartalmazó naplófájlok elküldése e-mailben a rendszergazdának | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08eeb1f330ed8fcea5da41f71ded0ccf124da7c5
ms.openlocfilehash: 9446df0381a2b2a1a6322f8f59523ce78406f25a


---


# Diagnosztikai adatokat tartalmazó naplófájlok elküldése e-mailben a rendszergazdának

Ha hiba lép fel Android-eszközén az iskolai vagy a munkahelyi alkalmazások használata közben, netán a Vállalati portál alkalmazás használata közben, elküldheti a rendszergazdának a diagnosztikai adatokról készült naplófájlokat, hogy ő azonosíthassa, majd elháríthassa a hibát. Amennyiben az összes részletet rögzíteni szeretné a naplófájlokban, hogy a rendszergazda könnyebben kideríthesse, mi is a probléma, kapcsolja be a Részletes naplózás beállítást. További tudnivalók: [Részletes naplózás](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

A részletes naplózás bekapcsolása:

1.  Nyissa meg a Vállalati portál alkalmazást.

2.  Koppintson a **Menü** &gt; **Beállítások** elemre.

    > [!NOTE]
    > A felhasználó androidos eszközének típusától függően a **Menü** elem szoftveres vagy hardveres gomb is lehet.

3.  A **Diagnosztikai adatok** csoportban koppintson az **Adatok elküldése** gombra.

    > [!NOTE]
    > **Ha csak Android 6.0-s vagy újabb eszközöket használ:** Amikor az **Adatok küldése** elemre koppint, a következő üzenetet látja: **Engedélyezi a Vállalati portál számára az eszköz fényképeinek, médiafájljainak és fájljainak elérését?**.

    Ez az üzenet félrevezető, mert a **Microsoft soha nem kéri le az eszközén lévő fényképeket, médiafájlokat vagy fájlokat.** A Google szabályozza az üzenet szövegét, így a Microsoft még akkor sem módosíthatja azt, ha az nem felel meg a valóságnak.  Amikor engedélyezi a hozzáférést, csak azt engedélyezi, hogy az eszköz adatnaplókat írjon az eszköz SD-kártyájára, így USB-kábelen keresztül áthelyezhetők lesznek a naplók.

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb az **Adatok küldése** elemre koppint, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket.  Amennyiben később ismét engedélyezni szeretné a hozzáférést, a **Beállítások** &gt; ** **Alkalmazások&gt; **Munkahelyi portál** &gt; **Engedélyek** &gt; **Tárterület** lapon teheti ezt meg.

4.  Az útmutatást követve válassza ki, hogy melyik levelezőprogrammal küldje el az eszköz a naplófájlokat a rendszergazdának. Az alkalmazás létrehoz egy előre megcímzett e-mailt, és csatolja ahhoz a naplófájlokat.




<!--HONumber=Aug16_HO5-->



---
# required metadata

title: Diagnosztikai adatokat tartalmazó naplófájlok elküldése e-mailben a rendszergazdának | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Diagnosztikai adatokat tartalmazó naplófájlok elküldése e-mailben a rendszergazdának

Ha hiba lép fel Android-eszközén az iskolai vagy a munkahelyi alkalmazások használata közben, netán a Vállalati portál alkalmazás használata közben, elküldheti a rendszergazdának a diagnosztikai adatokról készült naplófájlokat, hogy ő azonosíthassa, majd elháríthassa a hibát. Amennyiben az összes részletet rögzíteni szeretné a naplófájlokban, hogy a rendszergazda könnyebben kideríthesse, mi is a probléma, kapcsolja be a Részletes naplózás beállítást.

A részletes naplózás bekapcsolása:

1.  Nyissa meg a Vállalati portál alkalmazást.

2.  Koppintson a **Menu** (Menü) &gt;  **Settings** (Beállítások) elemre..

    > [!NOTE] 
    > A felhasználó androidos eszközének típusától függően a **Menü** elem szoftveres vagy hardveres gomb is lehet.

3.  A **Diagnostic Data** (Diagnosztikai adatok) csoportban koppintson az **Send Data** (Adatok küldése) gombra..

    > [!NOTE]
    > **Csak Android 6.0 vagy újabb rendszerű eszközök esetében:** Amikor a **Send Data** (Adatok küldése) elemre koppint, a következő üzenetet látja: **Allow Company Portal to access photos, media, and files on your device? (Engedélyezi a Munkahelyi portál alkalmazásnak, hogy hozzáférjen az eszközén tárolt fényképekhez, médiatartalmakhoz és fájlokhoz?)**.. 

    Ez az üzenet félrevezető, mert a **Microsoft soha nem kéri le az eszközén lévő fényképeket, médiafájlokat vagy fájlokat.** A Google szabályozza az üzenet szövegét, így a Microsoft még akkor sem módosíthatja azt, ha az nem felel meg a valóságnak.  Amikor engedélyezi a hozzáférést, csak azt engedélyezi, hogy az eszköz adatnaplókat írjon az eszköz SD-kártyájára, így USB-kábelen keresztül áthelyezhetők lesznek a naplók.

    Ha megtagadja a hozzáférést, az üzenet ismét megjelenik, amikor legközelebb az **Adatok küldése** elemre koppint, de a **Ne kérdezzen rá ismét** jelölőnégyzetre koppintva kikapcsolhatja a további üzeneteket.  Ha később úgy dönt, hogy engedélyezi a hozzáférést, lépjen a **Settings** (Beállítások) &gt; **Apps** (Alkalmazások) &gt; **Company Portal** (Vállalati portál) &gt; **Permissions** (Engedélyek) &gt; **Storage** (Tárhely) menüpontra, majd kapcsolja be az engedélyezést.

4.  Az útmutatást követve válassza ki, hogy melyik levelezőprogrammal küldje el az eszköz a naplófájlokat a rendszergazdának. Az alkalmazás létrehoz egy előre megcímzett e-mailt, és csatolja ahhoz a naplófájlokat.


### További információ
[Android-eszköz használata az Intune-nal](using-your-android-device-with-intune.md)

<!--HONumber=May16_HO1-->



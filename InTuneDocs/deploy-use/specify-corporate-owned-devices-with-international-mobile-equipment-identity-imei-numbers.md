---
title: "Az IMEI-számok megadása | Microsoft Docs"
description: "A Microsoft Intune-nal a rendszergazdák IMEI-számokat importálhatnak a mobileszközplatformokra, így könnyebben azonosíthatják a vállalati tulajdonban lévő mobileszközöket"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 02743ee216ce09c74a9d0ab2455e826b36e8aa4a
ms.lasthandoff: 03/22/2017


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune lehetővé teszi, hogy a rendszergazdák nemzetközi mobilkészülék-azonosító (IMEI-) számokat importáljanak IMEI-számokkal rendelkező mobileszköz-platformok esetén, hogy könnyebben azonosítsák a vállalati tulajdonban lévő mobileszközöket. Az eszközök Intune-ban való regisztrációja után az IMEI-számokat importáló eszközöket itt találja: **Csoportok** > **Áttekintés** > **Összes eszköz**. Az **Eszközcsoport** felsorolja az importált IMEI-számmal rendelkező eszközöket **Vállalati** értékkel látják el a **Tulajdonos** oszlopban.

1. A [Microsoft Intune felügyeleti konzoljában](http://manage.microsoft.com) lépjen a **Csoportok** &gt; **Minden eszköz** &gt; **Előre regisztrált vállalati eszközök** &gt; **IMEI-szám szerint (minden platform)** területre, majd válassza az **Eszközök felvétele** lehetőséget. Két módon adhat hozzá eszközöket:

    -   **Sorozatszámokat tartalmazó .csv-fájl feltöltése** – Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben maximum 5,000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot. A részletek mezőjébe legfeljebb 128 karakter írható.

        |||
        |-|-|
        |&lt;1. IMEI azonosító&gt;|&lt;1. eszköz részletei&gt;|
        |&lt;2. IMEI azonosító&gt;|&lt;2. eszköz részletei&gt;|
        Ez a .csv- fájl egy szövegszerkesztőben megtekintve így jelenik meg:

        ```
        01 234567 890123,device details
        02 234567 890123,device details
        ```

    -   **Eszközadatok kézi megadása** – Adja meg legfeljebb tizenöt eszköz sorozatszámát és adatait.

   A *Részletek* mező adminisztratív célokra szolgál. Olyan részleteket adhat meg, amelyek segítenek azonosítani az eszközt a Céges eszközök hardverazonosító szerinti listájában. Ezek az információk nem kerülnek át az eszközre, csak az Intune konzoljában jelennek meg.

2.   Kattintson a **Tovább** gombra.
3.  Az **Eszközök felülvizsgálata** panelen ellenőrizheti az importált eszköz IMEI-számát. Eldöntheti azt is, hogy felülírja-e az újraimportált IMEI-számok **Részleteit**. A **Felülírás** négyzet jelölését törölve megőrizheti az aktuális részleteket. Válassza a **Befejezés** lehetőséget az IMEI-számok importálásához.
4.  Az importált IMEI-számok és leírások az **IMEI szerint (minden platform)** listába kerülnek.

> [!IMPORTANT]
> Ha Android-eszközökhöz tartozó IMEI-számokat importál, ügyeljen rá, hogy egyes Android-eszközök több IMEI-számmal is rendelkezhetnek. Ha olyan IMEI-számot importál, amely nem egyezik meg az eszköz által az Intune-nak jelentett IMEI-számmal, az eszköz nem vállalati, hanem személyes eszközként lesz besorolva.

Amikor az adott IMEI-számmal rendelkező eszközt regisztrálják az Intune-ban – általában akkor, amikor egy felhasználó telepíti a Vállalati portál alkalmazást, és elvégzi a regisztrációs folyamatot –, az eszköz Vállalati címkével fog rendelkezni, és regisztráltként jelenik meg az **IMEI-eszközök** csoportban.

>[!NOTE]
> Ha a szervezet a közeljövőben az új Azure Portalra lesz migrálva, akkor ennek a funkciónak a működésében változást fognak tapasztalni. Az Intune korábbi felügyeleti konzolján a rendszergazdák feltöltött CSV-fájlból fogadhatják el a társított részleteket, így írhatják felül az egyes hardverazonosítók korábbi részleteit. Az új Azure Portalon automatikusan felül lehet írni az összes hardverazonosító részleteit, vagy figyelmen kívül hagyni a korábbi azonosítók újabb adatait.

Az IMEI-azonosítók részletes specifikációját a [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) lapon találja.


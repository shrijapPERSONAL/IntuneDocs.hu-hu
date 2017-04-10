---
title: "IMEI azonosítók hozzáadása az Intune-hoz"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune –előzetes: Ez a témakör azt ismerteti, hogyan lehet céges azonosítókat (IMEI-számokat) felvenni a Microsoft Intune-ba. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: e0a853c34c6d38e8fae6f4712ba6c2b767e5d0ba
ms.lasthandoff: 03/22/2017

---

# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Rendszergazdaként Ön létrehozhat egy IMEI-számokat felsoroló, vesszővel tagolt (.csv formátumú) fájlt a céges tulajdonban lévő eszközök azonosítása céljából. Az egyes IMEI-számokhoz a listában adminisztrációs célból részleteket is meg lehet adni.

## <a name="create-a-csv-file"></a>CSV-fájl létrehozása
Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A részletek maximális hossza 128 karakter. A .csv-fájlok jelenleg legfeljebb 500 sorosak lehetnek.

**Sorozatszámokat tartalmazó .csv-fájl feltöltése** – Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben maximum 5,000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot.

|||
|-|-|
|&lt;1. IMEI azonosító&gt;|&lt;1. eszköz részletei&gt;|
|&lt;2. IMEI azonosító&gt;|&lt;2. eszköz részletei&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Céges azonosítók .csv-listájának felvétele**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza a **Meglévő azonosítók adatainak felülírása** lehetőséget, így az új adatok felülírják a jelenlegieket.

4. Keresse meg az IMEI-számok CSV-fájlját, és válassza a **Hozzáadás** elemet.

> [!IMPORTANT]
> Bizonyos androidos eszközök több IMEI-számmal rendelkeznek. Az Intune eszközönként egy IMEI-számot vesz leltárba. Ha olyan IMEI-számot importál, amely nem egyezik meg az eszköz az Intune által leltározott IMEI-számával, az eszköz nem vállalati, hanem személyes eszközként lesz besorolva. Ha egy eszközhöz több IMEI-számot importál, a nem leltározott számok **Ismeretlen** regisztrációs állapottal jelennek meg.

Az importálás után ezek az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet **Regisztrálva** vagy **Nem történt kapcsolatfelvétel**. ****Utóbbi állapot azt jelenti, hogy az eszköz még nem lépett kapcsolatba az Intune szolgáltatással.

## <a name="delete-a-csv-list"></a>CSV-lista törlése

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Válassza a **Törlés** elemet.

Az IMEI-azonosítók részletes specifikációját a [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) lapon találja.


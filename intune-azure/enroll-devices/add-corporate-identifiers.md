---
title: "IMEI-azonosítók felvétele az Intune-ba | Azure-beli Intune –előzetes | Microsoft Docs"
description: "Azure-beli Intune –előzetes: Ez a témakör azt ismerteti, hogyan lehet céges azonosítókat (IMEI-számokat) felvenni a Microsoft Intune-ba. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8667f063de65fd5fa86149ac124b236a432eecef

---

# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A céges eszközök azonosítására listát készíthet az IMEI-számokról. Az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet „Regisztrálva” vagy „Nem történt kapcsolatfelvétel”. Utóbbi állapot azt jelenti, hogy az eszköz nem egyeztet adatokat az Intune szolgáltatással.

Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor.

Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

01 234567 890123,eszközadatok</br>
02 234567 890123,eszközadatok

**Céges azonosítók .csv-listájának felvétele**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza a **Meglévő azonosítók adatainak felülírása** lehetőséget, így az új adatok felülírják a jelenlegieket.

4. Keresse meg az IMEI-számok CSV-fájlját, és válassza a **Hozzáadás** elemet.

**Céges azonosítók .csv-listájának törlése**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Válassza a **Törlés** elemet.



<!--HONumber=Feb17_HO3-->



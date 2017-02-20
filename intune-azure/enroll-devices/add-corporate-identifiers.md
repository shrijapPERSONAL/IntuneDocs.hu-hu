---
title: "IMEI-azonosítók felvétele az Intune-ba | Azure-beli Intune –előzetes | Microsoft Docs"
description: "Azure-beli Intune –előzetes: Ez a témakör azt ismerteti, hogyan lehet céges azonosítókat (IMEI-számokat) felvenni a Microsoft Intune-ba. "
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A céges eszközök azonosítására listát készíthet az IMEI-számokról. Az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet „Regisztrálva” vagy „Nem történt kapcsolatfelvétel”. Utóbbi állapot azt jelenti, hogy az eszköz nem egyeztet adatokat az Intune szolgáltatással.

Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor.

Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

01 234567 890123,eszközadatok</br>
02 234567 890123,eszközadatok

**Céges azonosítók .csv-listájának felvétele**

1. Válassza az Azure Portalon a **További szolgáltatások** elemet, írja be az **Intune** nevet a szövegmezőbe, majd válassza az **Egyéb** > **Intune** elemet.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza a **Meglévő azonosítók adatainak felülírása** lehetőséget, így az új adatok felülírják a jelenlegieket.

4. Keresse meg az IMEI-számok CSV-fájlját, és válassza a **Hozzáadás** elemet.

**Céges azonosítók .csv-listájának törlése**

1. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

2. Válassza a **Törlés** elemet.



<!--HONumber=Feb17_HO1-->


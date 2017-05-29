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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 25414cd42159d1c3e09b80d236ccb12f0df5662a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Rendszergazdaként Ön létrehozhat egy IMEI-számokat felsoroló, vesszővel tagolt (.csv formátumú) fájlt a céges tulajdonban lévő eszközök azonosítása céljából. Az egyes IMEI-számokhoz a listában adminisztrációs célból részleteket is meg lehet adni.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele
Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A részletes adatok maximális terjedelme 128 karakter, csak adminisztratív célt szolgálnak, és nem jelennek meg az eszközön. A .csv-fájlok jelenleg legfeljebb 500 sorosak lehetnek.

**Sorozatszámokat tartalmazó .csv-fájl feltöltése** – Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben maximum 5,000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot. 

|||
|-|-|
|&lt;1. IMEI azonosító&gt;|&lt;1. eszköz részletei&gt;|
|&lt;2. IMEI azonosító&gt;|&lt;2. eszköz részletei&gt;|

Ez a .csv- fájl egy szövegszerkesztőben megtekintve így jelenik meg:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Bizonyos androidos eszközök több IMEI-számmal rendelkeznek. Az Intune eszközönként egy IMEI-számot vesz leltárba. Ha olyan IMEI-számot importál, amely nem egyezik meg az eszköz az Intune által leltározott IMEI-számával, az eszköz nem vállalati, hanem személyes eszközként lesz besorolva. Ha egy eszközhöz több IMEI-számot importál, a nem leltározott számok **Ismeretlen** regisztrációs állapottal jelennek meg.

**Céges azonosítók .csv-listájának felvétele**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen jelölje ki az **Eszközregisztráció** > **Regisztrációs korlátozások** elemet, majd válassza a **Céges készülékazonosítók** lehetőséget, és kattintson a **Hozzáadás** elemre.

3. Az **Azonosítók hozzáadása** panelen adja meg az azonosító típusát: **IMEI**. Megadhatja, hogy a korábban importált számok **felülírják-e a meglévő azonosítók adatait**.  

4. Kattintson a mappa ikonra, és adja meg az importálni kívánt lista elérési útját. Keresse meg az IMEI-számok CSV-fájlját, és válassza a **Hozzáadás** elemet.

Az importálás után ezek az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet **Regisztrálva** vagy **Nem történt kapcsolatfelvétel**. ****Utóbbi állapot azt jelenti, hogy az eszköz még nem lépett kapcsolatba az Intune szolgáltatással.

## <a name="delete--corporate-identifiers"></a>Céges azonosítók törlése

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen jelölje ki az **Eszközregisztráció** > **Regisztrációs korlátozások** elemet, válassza a **Céges készülékazonosítók** lehetőséget, és kattintson a **Törlés** elemre.

3. Az **Azonosítók törlése** panelen keresse meg a törölni kívánt eszközazonosítók .csv-fájlját, majd kattintson a **Törlés** elemre.

## <a name="imei-specifications"></a>IMEI-azonosítók specifikációi
Az IMEI-azonosítók részletes specifikációját a [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) lapon találja.


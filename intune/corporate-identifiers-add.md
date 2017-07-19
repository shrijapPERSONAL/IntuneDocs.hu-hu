---
title: "IMEI azonosítók hozzáadása az Intune-hoz"
titleSuffix: Intune on Azure
description: "Ez a témakör azt ismerteti, hogyan lehet céges azonosítókat (IMEI-számokat) felvenni a Microsoft Intune-ba. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57ab3b79ad53a4b195fac426d211a114f054602f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A céges tulajdonú eszközök azonosítása céljából rendszergazdaként létrehozhat és importálhat egy IMEI- (International Mobile Equipment Identifier) számokat vagy sorozatszámokat felsoroló, vesszővel tagolt (.csv) fájlt. Sorozatszámot csak iOS és Android rendszerű eszközhöz adhat meg. Adminisztrációs célból minden IMEI-azonosítóhoz vagy sorozatszámhoz megadhat további adatokat is.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Ismerje meg, hogyan találhatja meg egy Apple-eszköz sorozatszámát](https://support.apple.com/HT204308).
[Ismerje meg, hogyan találhatja meg a saját Apple-eszköz sorozatszámát](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele
Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A bal oldali oszlopban tüntesse fel az IMEI-azonosítót vagy a sorozatszámot, a jobb oldali oszlopban pedig a további adatokat. Egy .csv-fájlból csak egyféle azonosítót (IMEI-azonosítót vagy sorozatszámot) importálhat. A részletes adatok maximális terjedelme 128 karakter, csak adminisztratív célt szolgálnak, és nem jelennek meg az eszközön. A .csv-fájlok jelenleg legfeljebb 500 sorosak lehetnek.

**Sorozatszámokat tartalmazó .csv-fájl feltöltése** – Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben maximum 5,000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot.

|||
|-|-|
|&lt;1. azonosító&gt;|&lt;1. eszköz részletei&gt;|
|&lt;2. azonosító&gt;|&lt;2. eszköz részletei&gt;|

Ez a .csv- fájl egy szövegszerkesztőben megtekintve így jelenik meg:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Bizonyos androidos eszközök több IMEI-számmal rendelkeznek. Az Intune regisztrált eszközönként csak egy IMEI-számot olvas be. Ha olyan IMEI-számot importál, amely nem egyezik meg az eszköz az Intune által leltározott IMEI-számával, az eszköz nem vállalati, hanem személyes eszközként lesz besorolva. Ha egy eszközhöz több IMEI-számot importál, a nem leltározott számok **Ismeretlen** regisztrációs állapottal jelennek meg.

**Céges azonosítók .csv-listájának felvétele**

1. Az Intune-portálon jelölje ki az **Eszközregisztráció** > **Regisztrációs korlátozások** elemet, majd válassza a **Céges készülékazonosítók** lehetőséget, és kattintson a **Hozzáadás** gombra.

 ![Képernyőkép a céges készülékazonosítók munkaterületről a Hozzáadás gomb kiemelésével.](./media/add-corp-id.png)

2. Az **Azonosítók hozzáadása** panelen adja meg az azonosító típusát: **IMEI** vagy **Sorozatszám**. Megadhatja, hogy a korábban importált számok **felülírják-e a meglévő azonosítók adatait**.

3. Kattintson a mappa ikonra, és adja meg az importálni kívánt lista elérési útját. Keresse meg a .csv-fájlt, és kattintson a **Hozzáadás** elemre. A **Frissítés** elemre kattintva megtekintheti az új eszközazonosítókat.

Az importálás után ezek az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet **Regisztrálva** vagy **Nem történt kapcsolatfelvétel**. ****Utóbbi állapot azt jelenti, hogy az eszköz még nem lépett kapcsolatba az Intune szolgáltatással.

## <a name="delete--corporate-identifiers"></a>Céges azonosítók törlése

1. Az Intune-portálon jelölje ki az **Eszközregisztráció** > **Regisztrációs korlátozások** elemet, válassza a **Céges készülékazonosítók** lehetőséget, és kattintson a **Törlés** gombra.

3. Az **Azonosítók törlése** panelen keresse meg a törölni kívánt eszközazonosítók .csv-fájlját, majd kattintson a **Törlés** elemre.

## <a name="imei-specifications"></a>IMEI-azonosítók specifikációi
Az IMEI-azonosítók részletes specifikációját a [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) lapon találja.

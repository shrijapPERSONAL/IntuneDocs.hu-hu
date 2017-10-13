---
title: "Vállalati azonosítók hozzáadása az Intune-hoz"
titlesuffix: Azure portal
description: "Megtudhatja, hogyan adhat hozzá vállalati azonosítókat (regisztrációs módszer, IMEI és sorozatszámok) a Microsoft Intune-hoz. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 82b839943d21cd44c1be457cc8436928f41fe73c
ms.sourcegitcommit: b6a2d55d9c4e3248ff7ef738393f458f1978de44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2017
---
# <a name="identify-devices-as-corporate-owned"></a>Eszközök azonosítása vállalati tulajdonúként

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune-rendszergazdaként vállalati tulajdonúként azonosíthat eszközöket, így finomíthatja a felügyeletet és az azonosítást. Az Intune további felügyeleti feladatokat végezhet, valamint további adatokat gyűjthet, például a vállalati tulajdonú eszközök teljes telefonszámát és az eszközökön található alkalmazások leltárát. Eszközkorlátozásokat is beállíthat a nem vállalati tulajdonú eszközök regisztrációjának megakadályozásához.

Az eszköz vállalati tulajdonúként lesz azonosítva, ha az alábbi feltételek bármelyike fennáll:

- [i](device-enrollment-manager-enroll.md) fiókkal regisztrálták (bármely platformon).
- Az Apple [Készülékregisztrációs programban](device-enrollment-program-enroll-ios.md), az [Apple School Managerrel](apple-school-manager-set-up-ios.md) vagy az [Apple Configuratorral](apple-configurator-enroll-ios.md) regisztrálták (csak iOS esetén).
- [Regisztráció előtt az eszközt céges eszközként azonosították](#identify-corporate-owned-devices-with-imei-or-serial-number) nemzetközi mobilkészülék-azonosító (IMEI-) számmal (minden IMEI-számmal rendelkező platform esetében) vagy sorozatszámmal (csak iOS és Android esetében)
- Az eszköz regisztrálva van az Azure Active Directory vagy a Enterprise Mobility + Security szolgáltatásban Windows 10 Enterprise-eszközként
- Az eszköz tulajdonságai között [az eszköz céges tulajdonként](#change-device-ownership) van feltüntetve

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Céges eszközök azonosítása IMEI- vagy sorozatszám alapján

Intune-rendszergazdaként létrehozhat és importálhat IMEI számokat vagy sorozatszámokat felsoroló, vesszővel tagolt (.csv) fájlt. Az Intune ezeket az azonosítókat használva határozza meg a regisztráció során, hogy egy adott eszköz céges tulajdonú-e. IMEI-számot minden támogatott platformhoz megadhat. Sorozatszámot csak iOS, macOS és Android rendszerű eszközhöz adhat meg. Adminisztrációs célból minden IMEI-azonosítóhoz vagy sorozatszámhoz megadhat további adatokat is.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Ismerje meg, hogyan találhatja meg egy Apple-eszköz sorozatszámát](https://support.apple.com/HT204308).<br>
[Ismerje meg, hogyan találhatja meg a saját Android-eszközének sorozatszámát](https://support.google.com/store/answer/3333000).

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
> Bizonyos androidos eszközök több IMEI-számmal rendelkeznek. Az Intune regisztrált eszközönként csak egy IMEI-számot olvas be. Ha olyan IMEI-számot importál, amely nem egyezik meg az Intune által leltározott IMEI-számmal, az eszközt vállalati helyett magán tulajdonúnak sorolja be a rendszer. Ha egy eszközhöz több IMEI-számot importál, a leltárban nem szereplő számok **Ismeretlen** regisztrációs állapottal jelennek meg.<br>
>Ezenkívül fontos tudnia: nem biztos, hogy az androidos sorozatszámok egyediek vagy elérhetőek lesznek. Egyeztessen az eszköz szállítójával arról, hogy a sorozatszám tekinthető-e megbízható eszközazonosítónak.
>Elképzelhető, hogy az a sorozatszám, amelyet az eszköz az Intune felé jelez, nem egyezik meg az eszköz Android beállítások/Névjegy (Android Settings/About) menüjében megjelenő azonosítóval. Ellenőrizze, hogy az eszköz gyártója milyen típusú sorozatszámot tüntet fel itt.

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Céges azonosítók .csv-listájának felvétele

1. Az Intune-ban az Azure Portálon válassza az **Eszközök beléptetése** > **Céges készülékazonosítók** lehetőséget, majd kattintson a **Hozzáadás** gombra.

 ![Képernyőkép a céges készülékazonosítók munkaterületről a Hozzáadás gomb kiemelésével.](./media/add-corp-id.png)

2. Az **Azonosítók hozzáadása** panelen adja meg az azonosító típusát: **IMEI** vagy **Sorozatszám**. Megadhatja, hogy a korábban importált számok **felülírják-e a meglévő azonosítók adatait**.

3. Kattintson a mappa ikonra, és adja meg az importálni kívánt lista elérési útját. Keresse meg a .csv-fájlt, és kattintson a **Hozzáadás** elemre. A **Frissítés** elemre kattintva megtekintheti az új eszközazonosítókat.

Az importált eszközöket nem mindig regisztrálja a rendszer. Emiatt az eszközök **Regisztrált** vagy **Nincs kapcsolat** állapotúak lehetnek. ****Utóbbi állapot azt jelenti, hogy az eszköz még nem lépett kapcsolatba az Intune szolgáltatással.

### <a name="delete-corporate-identifiers"></a>Céges azonosítók törlése

1. Az Intune-ban az Azure Portálon válassza az **Eszközök beléptetése** > **Céges készülékazonosítók** lehetőséget.
2. Válassza ki a törölni kívánt eszközazonosítókat, majd kattintson a **Törlés** gombra.
3. Hagyja jóvá a törlést.

Ha törli egy regisztrált eszköz céges azonosítóját, azzal nem változtatja meg az eszköz tulajdonosát. Az eszköz tulajdonosának módosításához nyissa meg az **Eszközök** > **Minden eszköz** panelt, válassza ki az eszközt, majd válassza a **Tulajdonságok** lehetőséget, és módosítsa az **Eszköz tulajdonosa** értékét.

### <a name="imei-specifications"></a>IMEI-azonosítók specifikációi
Az IMEI-azonosítók részletes specifikációját a [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) lapon találja.

## <a name="change-device-ownership"></a>Eszköz tulajdonosának módosítása

Az Intune-ban az eszközök tulajdonságai között mindegyik eszközbejegyzésnél szerepel a **Tulajdonos**. Rendszergazdaként megadhatja, hogy az adott eszköz **Személyes** vagy **Céges**.

**Eszköz tulajdonosának módosítása:**
1. Az Intune-ban az Azure Portalon az **Eszközök** > **Minden Eszköz** lehetőségnél válassza ki az adott eszközt.
3. Válassza a **Tulajdonságok** lehetőséget.
4. Adja meg az **Eszköz tulajdonosa** beállításnál, hogy az eszköz **Személyes** vagy **Céges**.

  ![Képernyőkép az eszköz tulajdonságai képernyőről az Eszközkategória és az Eszköz tulajdonosa beállításokkal.](./media/device-properties.png)

---
title: "Apple Configurator-sorozatszámok hozzáadása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk azt ismerteti, hogyan lehet sorozatszámokat hozzáadni a vállalati eszközökhöz az Apple Configurator használatával."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 37c56d0c219c61c345874b24e8ba9ac640f1ef76
ms.openlocfilehash: 4c2ebe535935518127a799ae0518c43a2e53de72
ms.lasthandoff: 02/17/2017


---

# <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-sorozatszámok hozzáadása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kövesse az alábbi lépéseket, ha sorozatszámokat szeretne hozzáadni az Intune-hoz [vállalati iOS-eszközök Apple Configuratorrel és a Beállítási asszisztenssel való regisztrálásakor](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). A sorozatszámokat egyenként is hozzáadhatja, vagy feltölthet egy vesszővel tagolt értékekből álló (CSV-) fájlt, amely a sorozatszámokat tartalmazza. A sorozatszámok feltöltése után profilt rendelhet hozzájuk. A profil olyan felügyeleti beállításokat tartalmaz, amelyeket eszközökre alkalmazhat.

Az iOS-eszközök regisztrálásának további módjairól [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md) című témakörben olvashat.

**Apple Configurator-sorozatszámok hozzáadása az Intune-hoz**

1. Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv-fájlt). A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor. Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

    F7TLWCLBX196,eszköz adatai</br>
    DLXQPCWVGHMJ,eszköz adatai

2. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

3.  Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

4. Az **Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **Apple Configurator-sorozatszámok** lehetőséget.

5. Az **Apple Configurator-sorozatszámok** panelen válassza a **Hozzáadás** elemet.

6. A **Sorozatszámok hozzáadása** panelen válassza ki az importált sorozatszámokhoz hozzáadandó profilt. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza az Adatok felülírása lehetőséget a meglévő azonosítókra, így az új adatok felülírják a jelenlegieket.

7. Keresse meg a sorozatszámokat tartalmazó .csv-fájlt, és válassza a **Hozzáadás** lehetőséget.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Profil hozzárendelése meghatározott sorozatszámokhoz

Az Intune-ban a profilok hozzárendelése az Azure Portal két különféle helyén is elvégezhető. Használhatja az alábbi lépéseket is, vagy elvégezheti a profilok hozzárendelését az Apple Configurator regisztrációs profilok panelen is, ahol a profilok létrehozása is történik (lásd: [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Az alábbi lépéseket csak akkor használhatja profilok hozzárendeléséhez, ha már előzőleg létrehozta a profilt.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

3. Az **Apple Configurator-sorozatszámok** panelen válassza ki azokat a sorozatszámokat, amelyekhez profilt szeretne rendelni, majd válassza a **Profil hozzárendelése** lehetőséget.

4. A **Profil hozzárendelése** panelen válassza ki a hozzárendelendő profilt, majd válassza a **Hozzárendelés** lehetőséget.

## <a name="delete-serial-numbers"></a>Sorozatszámok törlése
A korábban importált sorozatszámokat törölheti is. A sorozatszám csak akkor törölhető, ha az eszköz regisztrációját előzőleg törölték. A sorozatszám törlése után az Apple Configurator csak a sorozatszám újbóli hozzáadása után használható a Beállítási asszisztenssel.

## <a name="view-the-state-of-a-device"></a>Eszköz állapotának megtekintése
Az eszközök sorozatszáma kétféle állapotúak lehetnek:

- Regisztrált – az eszköz regisztrálva van, és csatlakoztatva van az Intune szolgáltatáshoz
- Nincs csatlakoztatva – az eszköz még nem lett csatlakoztatva az Intune szolgáltatáshoz.
- Visszaállítás függőben – az eszköz regisztrálva van, de változtatás történt (például megváltoztak a regisztrálási beállítások vagy az alkalmazott DEP-profil). Ha egy eszköz DEP-profilja megváltozik, a változások csak a készülék regisztrációjának eltávolítása, majd újbóli regisztrálása után lépnek érvénybe.

**Sorozatszám állapotának megtekintéséhez**

Az **Apple Configurator-sorozatszámok** panelen válassza ki azt a sorozatszámot, amelynek meg szeretné nézni az állapotát, amit az **Állapot** lehetőségnél tehet meg.


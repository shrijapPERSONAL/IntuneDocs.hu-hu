---
title: "Regisztrációs korlátozások beállítása az Intune-ban | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: c4fa22fad4df9c0e4699cf258eb9518a1534bb94
ms.lasthandoff: 02/15/2017

---

# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Megadhatja a regisztrálni engedett eszközök típusát és maximális számát. A Regisztrációs korlátozások panelen a következőket adhatja meg:

- A regisztrálni engedett platformokat, illetve hogy letiltja-e a személyes tulajdonban lévő iOS-es és androidos eszközök regisztrálását.

- Az egy felhasználó által regisztrálható eszközök maximális számát.

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök regisztrálása** lehetőséget, majd válassza a **Regisztrációs korlátozások** elemet.

3. Az **Eszköztípus-korlátozások** elemnél válassza az **Alapértelmezett** beállítást.

4. A **Minden felhasználó** panelen válassza a **Platformok** elemet.

5. A regisztrációra engedélyezett platformoknál válassza az **Engedélyezés** lehetőséget. A blokkolni kívánt platformoknál pedig válassza a **Tiltás** lehetőséget. Alapértelmezés szerint az összes platform **Engedélyezés** értékre van állítva. 

    >[!NOTE]
    >Ezek a beállítások nincsenek hatással az Intune-szoftverügyféllel végzett windowsos regisztrációkra, csak a mobileszköz-felügyelettel végzettekre. 

6. Válassza a **Mentés** lehetőséget.

7. Válassza a **Platformkonfigurációk** elemet.

8. Válassza ki, hogy **engedélyezni** vagy **tiltani** kívánja a személyes tulajdonban lévő iOS-es és androidos eszközök regisztrálását.

9. Válassza a **Mentés** lehetőséget.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök regisztrálása** lehetőséget, majd válassza a **Regisztrációs korlátozások** elemet.

3. Az **Eszközszámkorlátok** elemnél válassza az **Alapértelmezett** beállítást.

4. A **Minden felhasználó** panelen válassza az **Eszközszámkorlát** elemet.

5. Válassza ki a felhasználó által regisztrálható eszközök maximális számát, majd válassza a **Mentés** lehetőséget.


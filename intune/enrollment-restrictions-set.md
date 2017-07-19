---
title: "Regisztrációs korlátozások beállítása az Intune-ban"
titleSuffix: Intune on Azure
description: "Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdájaként meghatározhatja, hogy mely eszközöket lehessen regisztrálni az Intune általi felügyelethez. Az Intune-portálon állíthatja be az eszközregisztráció következő korlátozásait:

- Regisztrált eszközök maximális száma
- Regisztrációra alkalmas eszközplatformok:
  - Android
  - iOS
  - macOS
  - Windows
- Személyes tulajdonú eszközök korlátozása (csak iOS és Android)

>[!NOTE]
>A regisztrációs korlátozások nem biztonsági funkciók. A feltört eszközök más tulajdonságokat állíthatnak magukról. Ezek a korlátozások a nem rosszindulatú felhasználók esetén jelentenek észszerű erőfeszítést igénylő akadályt.

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása
Az alapértelmezett regisztrációs korlátozások vonatkoznak minden olyan felhasználóra, akihez nincs magasabb prioritású regisztrációs korlátozás hozzárendelve.  
1. Az Intune-portálon válassza az **Eszközök regisztrálása** lehetőséget, majd a **Regisztrációs korlátozások** elemet.
![Az eszközkorlátozási munkaterület képernyőképe az alapértelmezett eszköztípus-korlátozásokkal és eszközszám-korlátozásokkal.](media/device-restrictions-set-default.png)
2. A **Regisztrációs korlátozások** > **Eszköztípus-korlátozások** alatt válassza az **Alapértelmezett** lehetőséget.
3. A **Minden felhasználó** alatt válassza a **Platformok** lehetőséget. Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást minden platformhoz:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Kattintson a **Mentés**gombra.
4. A **Minden felhasználó** alatt válassza a **Platformkonfigurációk** lehetőséget, és adja meg a következő beállításokat:
  - **Személyes tulajdonú** – Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást az Android- és iOS-eszközökhöz.
  ![Az eszközkorlátozási munkaterület képernyőképe az alapértelmezett eszközplatform-konfigurációval, ahol a személyes tulajdonú eszközök beállításai meg vannak adva.](media/device-restrictions-platform-configurations.png)
  Kattintson a **Mentés**gombra.

>[!NOTE]
>Ha letiltja a személyes tulajdonú Android-eszközök regisztrációját, az Android for Work-eszközöket akkor is lehet regisztrálni.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása
Az alapértelmezett regisztrációs korlátozások vonatkoznak minden olyan felhasználóra, akihez nincs magasabb prioritású regisztrációs korlátozás hozzárendelve.  
1. Az Intune-portálon válassza az **Eszközök regisztrálása** lehetőséget, majd a **Regisztrációs korlátozások** elemet.
2. Válassza a **Regisztrációs korlátozások** > **Eszközszámkorlátok** lehetőséget.
3. A **Minden felhasználó** alatt válassza az **Eszközszámkorlát** lehetőséget. Adja meg a regisztrált eszközök felhasználónkénti maximális számát.  
![Az Eszközszámkorlátok panel képernyőképe az eszközszámkorlátokkal.](./media/device-restrictions-limit.png)

  Kattintson a **Mentés**gombra.

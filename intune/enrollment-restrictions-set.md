---
title: "Regisztrációs korlátozások beállítása az Intune-ban"
titlesuffix: Azure portal
description: "Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0117d3249f7fd2568201762b7dd16af9cc26392c
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdájaként meghatározhatja, hogy mely eszközöket lehessen regisztrálni az Intune általi felügyelethez. Az Azure Portal webhelyen állíthatja be az eszközregisztráció következő korlátozásait:

- Regisztrált eszközök maximális száma
- Regisztrációra alkalmas eszközplatformok:
  - Android
  - iOS
  - macOS
  - Windows
- Az operációs rendszer verziója (csak iOS és Android esetén)
  - Minimális verzió
  - Maximális verzió
- Személyes tulajdonú eszközök korlátozása (csak iOS, Android vagy macOS esetén)

>[!NOTE]
>A regisztrációs korlátozások nem biztonsági funkciók. A feltört eszközök más tulajdonságokat állíthatnak magukról. Ezek a korlátozások a nem rosszindulatú felhasználók esetén jelentenek észszerű erőfeszítést igénylő akadályt.

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása
Az alapértelmezett regisztrációs korlátozások minden felhasználós és felhasználó nélküli regisztrációra vonatkoznak.
1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. A **Regisztrációs korlátozások** > **Eszköztípus-korlátozások** alatt válassza az **Alapértelmezett** lehetőséget.
5. A **Minden felhasználó** alatt válassza a **Platformok** lehetőséget. Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást minden platformhoz:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Kattintson a **Mentés**gombra.
6. A **Minden felhasználó** alatt válassza a **Platformkonfigurációk** lehetőséget, és adja meg a következő beállításokat. Az engedélyezett platformok esetén a következő lehetőségeket konfigurálhatja:
  - **Verzió** – Adja meg az operációs rendszer **Minimális** és **Maximális** verzióját Android- és iOS-eszközökhöz. Az operációs rendszer verziójának korlátozásai nem vonatkoznak a Készülékregisztrációs programmal, az Apple School Manager programmal, vagy az Apple Configurator alkalmazással regisztrált eszközökre.
  - **Személyes tulajdonú** – Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást az Android-, iOS- és macOS-eszközökhöz.
  ![Az eszközkorlátozási munkaterület képernyőképe az alapértelmezett eszközplatform-konfigurációval, ahol a személyes tulajdonú eszközök beállításai meg vannak adva.](media/device-restrictions-platform-configurations.png)
  Kattintson a **Mentés**gombra.

>[!NOTE]
>Ha letiltja a személyes tulajdonú Android-eszközök regisztrációját, a személyes tulajdonú Android for Work-eszközök továbbra is regisztrálhatók.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása
Az alapértelmezett regisztrációs korlátozások minden felhasználóra vonatkoznak.
1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Az Azure Portal webhelyen válassza az **Eszközök regisztrálása**, majd a **Regisztrációs korlátozások** lehetőséget.
5. Válassza a **Regisztrációs korlátozások** > **Eszközszámkorlátok** lehetőséget.
6. A **Minden felhasználó** alatt válassza az **Eszközszámkorlát** lehetőséget. Adja meg a regisztrált eszközök felhasználónkénti maximális számát.  
![Az Eszközszámkorlátok panel képernyőképe az eszközszámkorlátokkal.](./media/device-restrictions-limit.png)

  Kattintson a **Mentés**gombra.

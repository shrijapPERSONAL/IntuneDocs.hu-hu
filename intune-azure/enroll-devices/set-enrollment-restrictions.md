---
title: "Regisztrációs korlátozások beállítása az Intune-ban | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A regisztrálható eszközök típusát a regisztrációra jogosult platformok megadásával korlátozhatja az Intune-ban. Ezenkívül azt is megadhatja, hogy egy felhasználó legfeljebb hány eszközt regisztrálhat.

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása

1. Válassza az Azure Portalon a **További szolgáltatások** elemet, írja be az **Intune** nevet a szövegmezőbe, majd válassza az **Egyéb** > **Intune** elemet.

2. Az Intune panelen válassza az **Eszközök regisztrálása** lehetőséget, majd válassza a **Regisztrációs korlátozások** elemet.

3. Az **Eszköztípus-korlátozások** elemnél válassza az **Alapértelmezett** beállítást.

4. A **Minden felhasználó** panelen válassza a **Platformok** elemet.

5. A regisztrációra engedélyezett platformoknál válassza az **Engedélyezés** lehetőséget. A blokkolni kívánt platformoknál pedig válassza a **Tiltás** lehetőséget.

6. Válassza a **Mentés** lehetőséget.

7. Válassza a **Platformkonfigurációk** elemet.

8. Válassza ki, hogy engedélyezni vagy tiltani kívánja a személyes tulajdonban lévő iOS-eszközök regisztrációját.

9. Válassza a **Mentés** lehetőséget.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása

1. Az Intune panelen válassza az **Eszközök regisztrálása** lehetőséget, majd válassza a **Regisztrációs korlátozások** elemet.

2. Az **Eszközszámkorlátok** elemnél válassza az **Alapértelmezett** beállítást.

3. A **Minden felhasználó** panelen válassza az **Eszközszámkorlát** elemet.

4. Válassza ki a felhasználó által regisztrálható eszközök maximális számát, majd válassza a **Mentés** lehetőséget.



<!--HONumber=Feb17_HO1-->



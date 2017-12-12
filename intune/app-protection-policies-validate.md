---
title: "Az alkalmazásvédelmi szabályzatok ellenőrzése"
titleSuffix: Azure portal
description: "Ez a témakör azt ismerteti, hogyan tesztelheti és ellenőrizheti, hogy az alkalmazásvédelmi szabályzat konfigurációja és működése megfelelő-e.”"
keywords: 
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7914946519bc1977aeabfb474f66d4ced2a8f8ee
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2017
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Ez a témakör azon problémák ellenőrzésével kapcsolatban nyújt tájékoztatást, amelyek az alkalmazásvédelmi szabályzatok konfigurációját követően merülhetnek fel. Az útmutató az Azure Portal webhelyen található alkalmazásvédelmi szabályzatokra vonatkozik.

### <a name="checking-for-symptoms"></a>Hibajelenségek keresése
Mivel az alkalmazásvédelem egy adatvédelmi eszköz, nem valószínű, hogy a felhasználók jeleznek problémákat. Alkalmazásvédelmi konfigurációs problémák esetén a felhasználó ugyanolyan korlátlan hozzáféréssel rendelkezik, mint az alkalmazásvédelem nélkül, így nem veszi észre a problémát. Éppen ezért azt javasoljuk, hogy alkalmazásvédelmi konfigurációját úgy ellenőrizze, hogy az alkalmazásvédelmi szabályzatokat olyan felhasználók kis csoportján teszteli, akik képesek szándékosan tesztelni az alkalmazásvédelmi korlátozásokat.


### <a name="what-to-check"></a>Mit kell ellenőrizni?

Ha a tesztelés azt mutatja, hogy az alkalmazásvédelmi szabályzat nem az elvárt módon működik, akkor javasoljuk, hogy ellenőrizze az alábbiakat:

- A felhasználók rendelkeznek alkalmazásvédelmi licenccel?
- A felhasználók rendelkeznek O365-licenccel?
- Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**.

#### <a name="user-app-protection-status"></a>A felhasználók alkalmazásvédelmi állapota
1. Az Azure-portálon válassza az **Alkalmazások kezelése** > **Figyelés** >  **App protection user status** (Alkalmazásvédelmi felhasználói állapot) > **felhasználók** lehetőséget.

2. A listából válasszon ki egy felhasználót, vagy keressen rá valamelyik felhasználóra, majd válassza a **Felhasználó kiválasztása** lehetőséget. Az **Alkalmazásjelentések** oszlop tetején fog megjelenni, hogy a felhasználó rendelkezik-e alkalmazásvédelmi licenccel. Ez alatt látható, hogy a felhasználó rendelkezik-e O365-licenccel, és itt jelenik meg az alkalmazás állapota a felhasználó összes eszközére vonatkozóan.



### <a name="what-to-do"></a>Mi a teendő
A felhasználói állapotnak megfelelően az alábbi műveleteket hajthatja végre:

- Ha a felhasználó nem rendelkezik alkalmazásvédelmi licenccel, rendeljen Intune-licencet a felhasználóhoz.
- Ha a felhasználó nem rendelkezik O365-licenccel, szerezzen be számára egy licencet.
- Ha a felhasználó alkalmazása **Nincs bejelentkezve** állapottal jelenik meg a listában, ellenőrizze, hogy megfelelően állította-e be az adatvédelmi szabályzatot az adott alkalmazáshoz.
- Győződjön meg róla, hogy ezek a feltételek érvényesek minden olyan felhasználóra, akit be kíván vonni az adatvédelmi szabályzatok hatálya alá.

### <a name="see-also"></a>További információ

[Mi az Intune alkalmazásvédelmi szabályzata?](app-protection-policies.md)

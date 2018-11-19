---
title: Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése
titleSuffix: Microsoft Intune
description: Útmutató annak ellenőrzéséhez, hogy az alkalmazásvédelmi szabályzat be van-e állítva és megfelelően működik-e.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0a207d3e845e3983dfe6ce3abbb70fcbbe65cf
ms.sourcegitcommit: 4d5e811d451aeb6307e0f64818e182e471ae1ed4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51618973"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Annak ellenőrzése, hogy az alkalmazásvédelmi szabályzat megfelelően be van-e állítva és működik-e. Az útmutató az Azure Portal webhelyen található alkalmazásvédelmi szabályzatokra vonatkozik.

### <a name="checking-for-symptoms"></a>Hibajelenségek keresése
Mivel az alkalmazásvédelem egy adatvédelmi eszköz, nem valószínű, hogy a felhasználók jeleznek problémákat. Alkalmazásvédelmi konfigurációs probléma esetén a felhasználó rendelkezik ugyanolyan korlátlan hozzáféréssel, mint az alkalmazásvédelem nélkül, így nem ismert probléma. Ebből kifolyólag javasoljuk, hogy az alkalmazásvédelmi konfiguráció ellenőrzéséhez kiszolgálóinkat az alkalmazásvédelmi szabályzatokat olyan felhasználók, akik képesek szándékosan tesztelni az alkalmazásvédelmi korlátozásokat kis csoportján.


### <a name="what-to-check"></a>Mit kell ellenőrizni?

Ha a tesztelés azt mutatja, hogy az alkalmazások alkalmazásvédelmi szabályzat működését nem a várt módon, tekintse meg ezeket az elemeket:

- A felhasználók rendelkeznek alkalmazásvédelmi licenccel?
- A felhasználók rendelkeznek O365-licenccel?
- Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**.

#### <a name="user-app-protection-status"></a>A felhasználók alkalmazásvédelmi állapota
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza ki **ügyfélalkalmazás** > **figyelő** >  **alkalmazásvédelem állapota**, majd válassza ki a **hozzárendelt felhasználók**csempére. 
4. Az a **alkalmazásjelentések** lapon jelölje be **felhasználó kiválasztása** viszi, megjelenik a felhasználók és csoportok listáját. 
5. Keresse meg, és válasszon ki egy felhasználót a listából, majd válassza a **felhasználó kiválasztása**. Felső részén a **alkalmazásjelentések** ablaktáblán megjelenik-e a felhasználó rendelkezik alkalmazásvédelmi licenccel. Is láthatja, hogy a felhasználó rendelkezik-e egy licencet az Office 365 és az alkalmazás állapota az összes felhasználói eszköz.



### <a name="what-to-do"></a>Mi a teendő
A felhasználói állapotnak megfelelően az alábbi műveleteket hajthatja végre:

- Ha a felhasználó nem rendelkezik alkalmazásvédelmi licenccel, rendeljen hozzá egy Intune licencet a felhasználó.
- Ha a felhasználó nem rendelkezik licenccel, az o365 szolgáltatáshoz, a felhasználó-licenc beszerzéséhez.
- Ha a felhasználó alkalmazása **Nincs bejelentkezve** állapottal jelenik meg a listában, ellenőrizze, hogy megfelelően állította-e be az alkalmazásvédelmi szabályzatot az adott alkalmazáshoz.
- Győződjön meg arról, hogy ezek a feltételek vonatkoznak minden olyan felhasználóra, amelyre alkalmazásvédelmi szabályzatok a alkalmazni szeretné.

### <a name="see-also"></a>Lásd még:

[Mi az Intune alkalmazásvédelmi szabályzata?](app-protection-policies.md)

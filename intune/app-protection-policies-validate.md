---
title: Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése
titleSuffix: Microsoft Intune
description: Útmutató annak ellenőrzéséhez, hogy az alkalmazásvédelmi szabályzat be van-e állítva és megfelelően működik-e.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ea79a2e177b8a4e85454140c7efb9172defe5b6
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Annak ellenőrzése, hogy az alkalmazásvédelmi szabályzat megfelelően be van-e állítva és működik-e. Az útmutató az Azure Portal webhelyen található alkalmazásvédelmi szabályzatokra vonatkozik.

### <a name="checking-for-symptoms"></a>Hibajelenségek keresése
Mivel az alkalmazásvédelem egy adatvédelmi eszköz, nem valószínű, hogy a felhasználók jeleznek problémákat. Alkalmazásvédelmi konfigurációs problémák esetén a felhasználó ugyanolyan korlátlan hozzáféréssel rendelkezik, mint az alkalmazásvédelem nélkül, így nem veszi észre a problémát. Ebből kifolyólag javasolt az alkalmazásvédelmi konfiguráció ellenőrzéséhez az alkalmazásvédelmi szabályzatokat olyan felhasználók kis csoportján tesztelni, akik képesek szándékosan tesztelni az alkalmazásvédelmi korlátozásokat.


### <a name="what-to-check"></a>Mit kell ellenőrizni?

Ha a tesztelés azt mutatja, hogy az alkalmazásvédelmi szabályzat nem az elvárt módon működik, akkor javasolt ellenőrizni az alábbi elemeket:

- A felhasználók rendelkeznek alkalmazásvédelmi licenccel?
- A felhasználók rendelkeznek O365-licenccel?
- Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**.

#### <a name="user-app-protection-status"></a>A felhasználók alkalmazásvédelmi állapota
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
1. Válassza az **Alkalmazásfelügyelet** > **Figyelés** >  **Alkalmazásvédelem állapota** > **Hozzárendelt felhasználók** lehetőséget.

2. A listából válasszon ki egy felhasználót, vagy keressen rá valamelyik felhasználóra, majd válassza a **Felhasználó kiválasztása** lehetőséget. Az **Alkalmazásjelentések** oszlop tetején jelenik meg, hogy a felhasználó rendelkezik-e alkalmazásvédelmi licenccel. Az is látható, hogy a felhasználó rendelkezik-e O365-licenccel, illetve az alkalmazás állapota a felhasználó összes eszközére vonatkozóan.



### <a name="what-to-do"></a>Mi a teendő
A felhasználói állapotnak megfelelően az alábbi műveleteket hajthatja végre:

- Ha a felhasználó nem rendelkezik alkalmazásvédelmi licenccel, rendeljen Intune-licencet a felhasználóhoz.
- Ha a felhasználó nem rendelkezik O365-licenccel, szerezzen be számára egy licencet.
- Ha a felhasználó alkalmazása **Nincs bejelentkezve** állapottal jelenik meg a listában, ellenőrizze, hogy megfelelően állította-e be az alkalmazásvédelmi szabályzatot az adott alkalmazáshoz.
- Győződjön meg róla, hogy ezek a feltételek érvényesek minden olyan felhasználóra, akit be kíván vonni az adatvédelmi szabályzatok hatálya alá.

### <a name="see-also"></a>Lásd még:

[Mi az Intune alkalmazásvédelmi szabályzata?](app-protection-policies.md)

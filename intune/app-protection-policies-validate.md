---
title: Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése
titleSuffix: Microsoft Intune
description: Ismerje meg, hogyan tesztelheti, hogy az alkalmazásvédelmi szabályzat be van-e beállítva, és megfelelően működik-e a Microsoft Intune-ban.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 760ff85bc31cf66e66a3bf98f7da22d5ce48eee0
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292234"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>A Microsoft Intune-ban az alkalmazás alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Annak ellenőrzése, hogy az alkalmazásvédelmi szabályzat megfelelően be van-e állítva és működik-e. Az útmutató az Azure Portal webhelyen található alkalmazásvédelmi szabályzatokra vonatkozik.

## <a name="checking-for-symptoms"></a>Hibajelenségek keresése
Mivel az alkalmazásvédelem egy adatvédelmi eszköz, nem valószínű, hogy a felhasználók jeleznek problémákat. Alkalmazásvédelmi konfigurációs probléma esetén a felhasználó fog rendelkezik ugyanolyan korlátlan hozzáféréssel, mint azok lenne az alkalmazásvédelem nélkül, és nem tudják, hogy probléma van. Ebből kifolyólag javasoljuk, hogy az alkalmazásvédelmi konfiguráció ellenőrzéséhez kiszolgálóinkat az alkalmazásvédelmi szabályzatokat olyan felhasználók, akik képesek szándékosan tesztelni az alkalmazásvédelmi korlátozásokat kis csoportján.

## <a name="what-to-check"></a>Mit kell ellenőrizni?

Ha a tesztelés azt mutatja, hogy az alkalmazások alkalmazásvédelmi szabályzat működését nem a várt módon működik, tekintse meg ezeket az elemeket:

- A felhasználók rendelkeznek alkalmazásvédelmi licenccel?
- A felhasználók rendelkeznek O365-licenccel?
- Állapota, az egyes alkalmazások a felhasználók alkalmazásvédelmi alkalmazásainak elvárt módon. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**.

### <a name="user-app-protection-status"></a>A felhasználók alkalmazásvédelmi állapota
1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza ki **ügyfélalkalmazások** >  **alkalmazásvédelmi állapot**, majd válassza ki a **hozzárendelt felhasználók** csempére. 
4. Az a **alkalmazásjelentések** lapon jelölje be **felhasználó kiválasztása** viszi, megjelenik a felhasználók és csoportok listáját. 
5. Keresse meg, és válasszon ki egy felhasználót a listából, majd válassza a **felhasználó kiválasztása**. Felső részén a **alkalmazásjelentések** ablaktáblán megjelenik-e a felhasználó rendelkezik alkalmazásvédelmi licenccel. Is láthatja, hogy a felhasználó rendelkezik-e egy licencet az Office 365 és az alkalmazás állapota az összes felhasználói eszköz.

## <a name="what-to-do"></a>Mi a teendő
A felhasználói állapotnak megfelelően az alábbi műveleteket hajthatja végre:

- Ha a felhasználó nem rendelkezik alkalmazásvédelmi licenccel, rendeljen egy [Intune-licencet](licenses.md) a felhasználó számára.
- Ha a felhasználó nem rendelkezik licenccel, az o365 szolgáltatáshoz, egy [licenc](licenses.md) a felhasználó számára.
- Ha a felhasználó alkalmazása **nincs bejelentkezve**, ellenőrizze, hogy hogy megfelelően állította-e be egy [alkalmazásvédelmi szabályzat](app-protection-policies-validate.md) az adott alkalmazáshoz.
- Győződjön meg arról, hogy ezek a feltételek vonatkoznak minden olyan felhasználóra, akit be kíván [alkalmazásvédelmi szabályzatok](app-protection-policies-monitor.md) a alkalmazni.

## <a name="see-also"></a>Lásd még:

- [Mi az Intune alkalmazásvédelmi szabályzata?](app-protection-policies.md)
- [Az Intune-t tartalmazó licencek](licenses.md)
- [Licencek hozzárendelése a felhasználókhoz, hogy regisztrálhassák az eszközöket az Intune-ban](licenses-assign.md)
- [Az alkalmazásvédelmi szabályzatok konfigurációjának ellenőrzése](app-protection-policies-validate.md)
- [Az alkalmazásvédelmi szabályzatok figyelése](app-protection-policies-monitor.md)


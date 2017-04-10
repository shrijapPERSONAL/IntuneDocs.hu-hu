---
title: "A MAM-telepítés ellenőrzése | Microsoft Docs"
description: "Ez a témakör ismerteti, hogyan tesztelheti és ellenőrizheti, hogy a MAM-szabályzat beállítása és működése megfelelő-e."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 080d8f4fd4b6e1b53df860f4319b1c199d504c06


---

# <a name="validating-your-mobile-application-management-setup"></a>A mobilalkalmazás-kezelés beállításának ellenőrzése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör azokkal a problémákkal kapcsolatban nyújt tájékoztatást, amelyek a mobilalkalmazás-kezelés (MAM) beállítását követően merülhetnek fel. Az útmutató az Azure-portálon található MAM-szabályzatokra vonatkozik.

### <a name="checking-for-symptoms"></a>Hibajelenségek keresése
Mivel a MAM egy adatvédelmi eszköz, nem valószínű, hogy a felhasználók jeleznek problémákat. MAM-konfigurációs probléma esetén a felhasználó ugyanolyan korlátlan hozzáféréssel rendelkezik, mint a MAM nélkül, így nem veszi észre a problémát. Éppen ezért azt javasoljuk, hogy MAM-konfigurációját úgy ellenőrizze, hogy a MAM-szabályzatokat olyan felhasználók kis csoportján teszteli, akik képesek szándékosan tesztelni a MAM-korlátozásokat.


### <a name="what-to-check"></a>Mit kell ellenőrizni?

Ha a tesztelés azt mutatja, hogy a MAM-szabályzat nem az elvárt módon működik, akkor javasoljuk, hogy ellenőrizze az alábbiakat:

- A felhasználók rendelkeznek MAM-licenccel?
- A felhasználók rendelkeznek O365-licenccel?
- Az egyes felhasználók MAM-alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**.

#### <a name="user-mam-status"></a>A felhasználó MAM-állapota
1. Az Azure-portálon válassza az **Intune mobilalkalmazás-kezelés** > **beállítások** > **alkalmazás-felügyelet** > **Összes beállítás** > **Felhasználói alkalmazásjelentések** > **felhasználók** lehetőséget.

2. A listából válasszon ki egy felhasználót, vagy keressen rá valamelyik felhasználóra, majd válassza a **Felhasználó kiválasztása** lehetőséget. Az **Alkalmazásjelentések** oszlop tetején fog megjelenni, hogy a felhasználó rendelkezik-e MAM-licenccel. Ez alatt látható, hogy a felhasználó rendelkezik-e O365-licenccel, és itt jelenik meg az alkalmazás állapota a felhasználó összes eszközére vonatkozóan.

![Alkalmazás állapota a MAM-ban](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Mi a teendő
A felhasználói állapotnak megfelelően az alábbi műveleteket hajthatja végre:

- Ha a felhasználó nem rendelkezik MAM-licenccel, rendeljen hozzá egy Intune-licencet az [Intune-licencek kezelése](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md) című részben leírtaknak megfelelően.
- Ha a felhasználó nem rendelkezik O365-licenccel, szerezzen be számára egy licencet.
- Ha a felhasználó alkalmazása **Nincs bejelentkezve** állapottal jelenik meg a listában, ellenőrizze, hogy megfelelően állította-e be a MAM-szabályzatot az adott alkalmazáshoz.
- Győződjön meg róla, hogy ezek a feltételek vonatkoznak minden olyan felhasználóra, akit be kíván vonni a MAM-szabályzatok hatálya alá.

### <a name="see-also"></a>További információ
[Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására a Microsoft Intune-ban](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Alkalmazásadatok védelme mobilalkalmazás-kezelési szabályzatokkal a Microsoft Intune segítségével](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->



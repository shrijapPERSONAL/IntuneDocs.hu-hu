---
title: "Riasztások által biztosított értesítések | Microsoft Docs"
description: "Tudja meg, hogyan követheti nyomon riasztásokkal, mi történik a Microsoft Intune-ban."
keywords: 
author: nathbarn
ms.author: angrobe
manager: angrobe
ms.date: 8/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft intune
ms.technology: 
ms.assetid: 396ea714 0433 4bd5 a934 8d0b477f28e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune classic
ms.openlocfilehash: 287e8f3736082e427481d7a8a363947d4c42cdd6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
#  <a name="use-alerts-to-get-notified-by-microsoft-intune"></a>Riasztások használata Microsoft Intune-értesítésekhez

[!INCLUDE[classic portal](../includes/classic-portal.md)]

A riasztásokkal nyomon követheti, mi történik a Microsoft Intune-ban. A riasztások többek között a következő eseményekről kaphat értesítést:
- Az Exchange Connectorral kapcsolatos problémákról, amelyek a mobileszköz-felügyeletet is érintik
- Arról, ha a rendszer kártevőt talál egy számítógépen
- Arról, ha a rendszer ütközést észlel két Intune-házirend között
- Az Intune-szoftverügyfél üzembe helyezése sikertelen

## <a name="how-alerts-work"></a>A riasztások működése

A riasztások generálása a **riasztástípusok** alapján (az Intune beépített, előre konfigurált szabályai alapján) történik. Például **A felhőbeli szabad tárkapacitás 10% vagy kevesebb** típusú riasztás akkor figyelmeztet, ha hamarosan elfogy az alkalmazások tárolására szolgáló terület a felhőben. Az egyes riasztástípusok engedélyezhetők, letilthatók, és konfigurálhatók a hozzájuk kapcsolódó tulajdonságok. A fenti riasztástípusnál például a következőket konfigurálhatja:

- **Állapot:** megadja, hogy a riasztástípus engedélyezve van-e, vagy le van tiltva.
- **Súlyosság:** megadja, hogy mennyire súlyos a riasztás.

|Severity|Részletek|
|--|---|
|**Kritikus riasztás**|Olyan súlyos problémát jelöl, amelyet mielőbb ki kell vizsgálni – például ha a rendszer kártevőt észlel valamelyik számítógépen.|
|**Figyelmeztető riasztás**|Olyan problémát jelöl, amely egyelőre még nem súlyos, de súlyossá válhat, ha nem foglalkozik vele – ilyenek például a telepítésre váró biztonsági frissítések.|
|**Információs riasztás**|Olyan információt jelez, amely az üzemeltetés szempontjából nem kritikus – ilyen például, ha elérhető válik az Exchange Connector újabb verziója.|

Más riasztástípusok ettől eltérő konfigurációs elemeket is tartalmazhatnak, például hogy az eszközök hány százalékát kell érintenie a problémának ahhoz, hogy a riasztás létrejöjjön.

**Ha egy riasztástípus megadott feltétele teljesül, a rendszer létrehozza és megjeleníti a riasztást az Intune felügyeleti konzolon.**

Emellett az is beállítható, hogy az Intune e-mailben értesítse arról, ha riasztás jön létre.

## <a name="set-up-alerts"></a>Riasztások beállítása

A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Felügyelet** &gt; **Riasztások és értesítések** elemet, majd válasszon a következő feladatok közül:

|Feladat|Leírás|
|---|------|
|**Riasztástípusok**|Válassza ki a konfigurálni kívánt riasztástípust, majd tegye a következők valamelyikét:<br /><br />Válassza a **Konfigurálás** elemet. A **Riasztástípus beállítása** párbeszédpanelen adja meg a kívánt beállításokat, majd kattintson az **OK** gombra.<br /><br />**Engedélyezze** vagy **tiltsa le** a riasztást.<br /><br />Bontsa ki a **Riasztástípusok** csomópontot, majd válassza ki azt a kategóriát, amelynek a riasztástípusait meg szeretné tekinteni.|
|**Címzettek**|Kattintson a **Hozzáadás** gombra, majd adja meg az új e-mail-címet, amelyen e-mail értesítéseket szeretne fogadni.<br /><br />A meglévő címzetteket **szerkesztheti** és **törölheti** is.<br /><br />Ha értesítést szeretne kapni, a kívánt e-mail címet az **Értesítési szabályok** területen is fel kell vennie címzettként.|
|**Értesítési szabályok**|Az e-mail riasztások címzettjeit meghatározó szabályok konfigurálására szolgál. A következő lehetőségek közül választhat:<br /><br />**Meglévő szabály választása** Válasszon egy szabályt, majd kattintson a **Címzettek kiválasztása** elemre. Ezután kiválaszthatja az összes címzettet, aki e-mailt kap, ha létrejön egy riasztás, amely megfelel ennek a szabálynak.<br /><br />**Új szabály létrehozása** Adja meg a szabály nevét, válassza ki a szabályokra érvényes riasztási kategóriákat és riasztási súlyosságot, válassza ki azon eszközcsoportokat, amelyekre a szabály érvényes, és válassza ki azokat a felhasználókat, akik e-mailt kapnak riasztás esetén.<br /><br />A meglévő szabályokat **engedélyezheti**, **letilthatja**, **szerkesztheti**és **törölheti** is.|

## <a name="working-with-alerts"></a>A riasztások kezelése

Ha riasztásokat szeretne megtekinteni a [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com), válassza a **Riasztások** elemet, majd válassza ki a megnézni kívánt riasztástípust.

A következő beállításokkal kezelheti a riasztásokat az Intune felügyeleti konzolról.

|Beállítás|Leírás|
|-----|----|
|**Aktív riasztások megtekintése**|Válasszon a következő lehetőségek közül:<br /><br />**A riasztás összefoglalásának megtekintése** Az **Irányítópult** munkaterületen a legfontosabb hibák a Riasztások panelen jelennek meg. További részletes információk megjelenítéséhez kattintson az ablaktáblára.<br /><br />Emellett az egyes riasztások összefoglalását a **Riasztások** munkaterület **Áttekintés** lapján tekintheti meg.<br /><br />**Az összes riasztás megtekintése** A **Riasztások** munkaterületen válassza a **Minden riasztás** elemet.|
|**Megjegyzések megtekintése**|Válasszon a következő lehetőségek közül:<br /><br />Az **Irányítópult** munkaterületen kattintson a **Megjegyzések** elemre.<br /><br />A **Riasztások** munkaterületen válassza a **Minden riasztás** &gt; **Értesítések** elemet.|
|**Riasztás bezárása**|A riasztások listájában válassza ki a bezárni kívánt riasztást, majd kattintson a **Riasztás bezárása** elemre.<br /><br />A bezárt riasztások 90 nap után véglegesen törlődnek.|
|**Bezárt riasztás újraaktiválása**|A riasztáslistában válassza a **Szűrők** legördülő lista **Bezárt** elemét.<br /><br />A bezárt riasztások listájában jelölje ki az újraaktiválni kívánt riasztást, majd kattintson a **Riasztás újraaktiválása** elemre.|

Az Intune riasztásai aktív állapotúak maradnak 30 napig, vagy az alábbiak egyikének bekövetkeztéig:

- A riasztást kiváltó probléma megoldódik.
- A riasztást valaki manuálisan lezárja.

A lezárt riasztások újraaktiválhatóak a lezárást követő 30 napra. A 30 nap leteltével a lezárt és az inaktív riasztások törlődnek az Intune-ból.

> [!TIP]
> Ha ugyanazt a riasztást különböző operációs rendszerű eszközök is kiváltják, elképzelhető, hogy több verzió jelenik meg ugyanabból a riasztásból a riasztáslistában.

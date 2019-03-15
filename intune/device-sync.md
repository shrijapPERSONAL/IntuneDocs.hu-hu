---
title: Eszközök szinkronizálása a Microsoft Intune nal – Azure | Micrososft Docs
description: A Microsoft Intune-ban regisztrált vagy az általa kezelt eszközök szinkronizálásával az eszközök beolvashatják a legfrissebb szabályzatokat és műveleteket. Az Azure Portallal való szinkronizálás lépései és az újrapróbálható hibakódok.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f13e00abad5b48dcd7996cf9df1cc5756f250d3
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57388110"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Az eszközök szinkronizálása az Intune-nal a legfrissebb szabályzatok és műveletek beolvasásához


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A **Szinkronizálás** eszközművelet kikényszeríti a választott eszköz azonnali bejelentkezését az Intune-nál. Bejelentkezéskor az eszköz azonnal fogadja az hozzárendelt összes függőben lévő műveletet vagy szabályzatot. Ez a funkció segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Eszköz szinkronizálása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet. 
3. Az **Intune**-ban válassza az **Eszközök** > **Minden eszköz** lehetőséget.
4. A kezelt eszközök listájában válasszon ki egy eszközt, válassza a **További** lehetőséget, majd a **Szinkronizálás** elemet.
5. Válassza az **Igen** lehetőséget a megerősítéshez.

A szinkronizálási művelet állapotának megtekintéséhez válassza az **Eszközök** > **Eszközműveletek** lehetőséget.

Standard Intune házirend bejelentkezési frekvenciája annak a [frissítési ciklus alkalommal](device-profiles.md).

## <a name="retryable-error-codes"></a>Újrapróbálható hibakódok

Ha a rendszergazda a **Szinkronizálás** eszközműveletet futtatja, a sikertelen iOS- és Android-alkalmazásokhoz használható újrapróbálható hibakód továbbra is elérhető. Ha azonban az alkalmazás nem újrapróbálható hibakódot generált, akkor az hét napig nem lesz elérhető az eszköz számára.


| Hibakód  | Javasolt leírás | Újrapróbálható |
|---|---|---|
| 2016330898 | Ismeretlen hiba történt. | Nem |
| 2016330897 | Intune-kapcsolata túllépte az időkorlátot. Kapcsolat alaphelyzetbe állítása. | Igen |
| 2016330896 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása. | Igen |
| 2016330895 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása. | Igen |
| 2016330894 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása. | Igen |
| 2016330893 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása. | Igen|
| 2016330892 | A nemzetközi roaming le van tiltva. | Nem|
| 2016330891 | Hívás közben az eszköz mobilhálózati adatkapcsolata nem érhető el. Várjon a hívás befejezéséig. | Igen|
| 2016330890 | Az eszköz mobilhálózata. Ezeket az eszközöket jelenleg nem lehetett használni. | Nem|
| 2016330889 | A biztonságos kapcsolat sikertelen. Kapcsolat alaphelyzetbe állítása. | Igen|
| 2016330888 | A kiszolgáló megbízhatósági értékelése sikertelen. | Nem|

## <a name="next-steps"></a>További lépések

[Megtekintheti az eszköz részleteit](device-inventory.md).
 

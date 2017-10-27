---
title: "Eszközök szinkronizálása az Intune-nal"
titlesuffix: Azure portal
description: "Ismerje meg, hogyan szinkronizálhat eszközöket az Intune-nal, hogy beolvassák a legfrissebb szabályzatokat és műveleteket.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dadcd33f39827365fc3f22c46d4332f3ea3cbf09
ms.sourcegitcommit: a1c751959c9b3d5678bd9d67007e762df30eab59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Az eszközök szinkronizálása az Intune-nal a legfrissebb szabályzatok és műveletek beolvasásához


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Szinkronizálás** eszközművelet kikényszeríti a választott eszköz azonnali bejelentkezését az Intune-nál. Bejelentkezéskor az eszköz azonnal fogadja az hozzárendelt összes függőben lévő műveletet vagy szabályzatot.  Ez a művelet segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Eszköz szinkronizálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy eszközt, majd válassza a **Szinkronizálás** távoli műveletet.
7. A művelet megerősítéséhez válassza az **Igen** lehetőséget.


## <a name="retriable-error-codes"></a>Újrapróbálható hibakódok

Ha a rendszergazda a **Szinkronizálás** eszközműveletet futtatja, a sikertelen iOS- és Android-alkalmazásokhoz használható újrapróbálható hibakód lesz elérhető. Ha azonban az alkalmazás nem újrapróbálható hibakódot generált, akkor az hét napig nem lesz elérhető az eszköz számára.


| Hibakód  | Javasolt leírás                                                                                                                  | Újrapróbálható |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Ismeretlen hiba történt.                                                                                                             | Nem        |
| 2016330897 | Intune-kapcsolata túllépte az időkorlátot. Kapcsolat alaphelyzetbe állítása                                                                             | Igen       |
| 2016330896 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása.                                                                            | Igen       |
| 2016330895 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása.                                                                            | Igen       |
| 2016330894 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása.                                                                            | Igen       |
| 2016330893 | Megszakadt az internetkapcsolat. Kapcsolat alaphelyzetbe állítása.                                                                            | Igen       |
| 2016330892 | A nemzetközi roaming le van tiltva.                                                                                                     | Nem        |
| 2016330891 | Hívás közben az eszköz mobilhálózati adatkapcsolata nem érhető el. Várjon a hívás befejezéséig. | Igen       |
| 2016330890 | Az eszköz mobilhálózata. Ezeket az eszközöket jelenleg nem lehetett használni.                                                   | Nem        |
| 2016330889 | A biztonságos kapcsolat sikertelen. Kapcsolat alaphelyzetbe állítása.                                                                                   | Igen       |
| 2016330888 | A kiszolgáló megbízhatósági értékelése sikertelen.                                                                                                | Nem        |

## <a name="next-steps"></a>További lépések

Válassza az **Eszközműveletek** lehetőséget a szinkronizálási művelet állapotának megtekintéséhez. 

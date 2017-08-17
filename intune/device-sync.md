---
title: "Eszközök szinkronizálása az Intune-nal"
titleSuffix: Intune on Azure
description: "Ismerje meg, hogyan szinkronizálhat eszközöket az Intune-nal, hogy beolvassák a legfrissebb szabályzatokat és műveleteket.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 870eb3bf255cda92952a908596485d7b53259fb4
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Az eszközök szinkronizálása az Intune-nal a legfrissebb szabályzatok és műveletek beolvasásához


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Szinkronizálás** eszközművelet kikényszeríti a választott eszköz azonnali bejelentkezését az Intune-nál. Bejelentkezéskor az eszköz azonnal fogadja az hozzárendelt összes függőben lévő műveletet vagy szabályzatot.  Ez a művelet segíthet a vonatkozó szabályzatok azonnali ellenőrzésében és a hibák elhárításában anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – támogatott
- Windows Phone – támogatott
- iOS – támogatott
- macOS – támogatott
- Android – támogatott

## <a name="how-to-sync-a-device"></a>Eszköz szinkronizálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy eszközt, majd válassza a **Szinkronizálás** távoli műveletet.
7. A művelet megerősítéséhez válassza az **Igen** lehetőséget.

## <a name="next-steps"></a>További lépések

Válassza az **Eszközműveletek** lehetőséget a szinkronizálási művelet állapotának megtekintéséhez. 

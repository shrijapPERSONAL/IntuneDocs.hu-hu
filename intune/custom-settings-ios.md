---
title: Egyéni Microsoft Intune-beállítások iOS rendszerű eszközökhöz
titleSuffix: ''
description: A Microsoft Intune egyéni iOS-profiljához tartozó beállítások ismertetése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0ae4e757264465043ee6992033710c5a81d7157
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831300"
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Egyéni Microsoft Intune-eszközbeállítások iOS rendszerű eszközökhöz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune egyéni iOS-profilja használatával az [Apple Configurator eszközzel](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) létrehozott beállítások iOS-alapú eszközökhöz rendelhetők hozzá. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később egyéni iOS-profilokba importálhatja, és a beállításokat érvénybe léptetheti munkahelye felhasználói és eszközei esetében.

Ezzel a funkcióval olyan iOS-beállításokat rendelhet hozzá a felhasználókhoz és eszközökhöz, amelyek nem konfigurálhatók az Intune másféle konfigurációs típusaival.


1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. Az **Egyéni konfigurációs profil** panelen konfigurálja az összes alábbi beállítást:

- **Egyéni konfigurációs profil neve** – Adja meg, hogy a szabályzat milyen néven jelenjen meg az eszközön és az Intune-állapotban.
- **Konfigurációs profil fájlja** – Keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt.
Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök iOS-verziójával, amelyekhez az egyéni iOS-szabályzatot kívánja hozzárendelni. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatókban talál.

Az importált fájl a panel **Fájl tartalma** területén jelenik meg.

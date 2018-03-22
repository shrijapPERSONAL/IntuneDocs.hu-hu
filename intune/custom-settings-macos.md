---
title: Egyéni Microsoft Intune-beállítások macOS rendszerű eszközökhöz
titleSuffix: ''
description: A Microsoft Intune egyéni macOS-profiljához tartozó beállítások ismertetése.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8dc2042d7f88cf626d7420d4760255e1e9a3469
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Egyéni Microsoft Intune-eszközbeállítások macOS rendszerű eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune egyéni macOS-profil használatával az [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) eszközzel létrehozott beállítások macOS-alapú eszközökhöz rendelhetők. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később egyéni macOS-profilokba importálhatja, és a beállításokat érvénybe léptetheti munkahelye felhasználói és eszközei esetében.

Ezzel a funkcióval olyan macOS-beállításokat rendelhet hozzá, amelyek nem konfigurálhatók az Intune másféle konfigurációs típusaival.


1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. Az **Egyéni konfigurációs profil** panelen konfigurálja az összes alábbi beállítást:

- **Egyéni konfigurációs profil neve** – Adja meg, hogy a szabályzat milyen néven jelenjen meg az eszközön és az Intune-állapotban.
- **Konfigurációs profil fájlja** – Keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt.
Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök macOS-verziójával, amelyekhez az egyéni macOS-szabályzatot hozzárendeli. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatókban talál.

Az importált fájl a panel **Fájl tartalma** területén jelenik meg.

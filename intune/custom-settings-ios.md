---
title: "Egyéni Intune-beállítások iOS-eszközökhöz"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune-előzetes: egyéni iOS-profil beállításainak ismertetése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3d1ccae3c36e13b4074c442b48943077041a8b52
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Egyéni Microsoft Intune-beállítások iOS-eszközökhöz

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A Microsoft Intune egyéni iOS-profilja használatával az [Apple Configurator eszközzel](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) létrehozott beállítások iOS-alapú eszközökhöz rendelhetők hozzá. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később egyéni iOS-profilokba importálhatja, és a beállításokat érvénybe léptetheti munkahelye felhasználói és eszközei esetében.

Ezzel a funkcióval olyan iOS-beállításokat rendelhet hozzá a felhasználókhoz és eszközökhöz, amelyek nem konfigurálhatók az Intune másféle konfigurációs típusaival.


1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. A **Profil létrehozása** panelen adja meg a következőket:

- **Egyéni konfigurációs profil neve** – Adja meg, hogy a szabályzat milyen néven jelenjen meg az eszközön és az Intune-állapotban.
- **Konfigurációs profil fájlja** – Keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt.
Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök iOS-verziójával, amelyekhez az egyéni iOS-szabályzatot kívánja hozzárendelni. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatókban talál.

Az importált fájl a panel **Fájl tartalma** területén jelenik meg.


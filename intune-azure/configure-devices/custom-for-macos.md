---
title: "Egyéni beállítások az Intune-ban macOS-eszközök esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Egyéni macOS-profil beállításainak ismertetése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 84902bb0e7ea67b388debd8bd7992d396d981a7b
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>macOS-eszközökre vonatkozó egyéni beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune egyéni macOS-profil használatával az [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) eszközzel létrehozott beállítások macOS-alapú eszközökre telepíthetők. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később egyéni macOS-profilokba importálhatja, és a beállításokat érvénybe léptetheti munkahelye felhasználói és eszközei esetében.

Ezzel a funkcióval olyan macOS-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune másféle konfigurációs típusaival.


1. Az első lépésekhez használja az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](how-to-configure-custom-settings.md) című témakört.
2. A **Profil létrehozása** panelen adja meg a következőket:

- **Egyéni konfigurációs profil neve** – Adja meg, hogy a szabályzat milyen néven jelenjen meg az eszközön és az Intune-állapotban.
- **Konfigurációs profil fájlja** – Keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt.
Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök macOS-verziójával, amelyekre az egyéni macOS-házirendet telepíti. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatókban talál.

Az importált fájl a panel **Fájl tartalma** területén jelenik meg.


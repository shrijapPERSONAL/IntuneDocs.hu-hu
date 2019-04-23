---
title: Egyéni eszközbeállítások az Azure-beli Intune-ban | Microsoft Docs
description: Profilok hozzáadása és létrehozása egyéni beállítások használatához Windows Phone, Windows 8.1, Windows 10 vagy újabb rendszereken, valamint Android, Android Enterprise, macOS és iOS rendszerű eszközökön a Microsoft Intune használatával
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 923570324dba89efdc9e314f18307ea7310bb252
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508106"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Egyéni beállításokkal rendelkező profil létrehozása az Intune-ban

## <a name="what-are-custom-profiles"></a>Mik azok az egyéni profilok?

A Microsoft Intune számos beépített beállítást tartalmaz az eszközök különböző funkcióinak vezérléséhez. Emellett egyéni profilokat is létrehozhat. Az egyéni profilok akkor hasznosak, ha olyan eszközbeállításokat és funkciókat kíván használni, amelyek nem érhetők el beépítetten az Intune-ban. Ezen profilok a szervezet eszközeinek módosítható funkcióit és beállításait tartalmazzák. Létrehozhat például egy olyan egyéni profilt, amely minden iOS rendszerű eszközre ugyanazt a beállítást alkalmazza.

További információt a konfigurációs profilokról a [Microsoft Intune-eszközprofilokat bemutató](device-profiles.md) cikkben találhat. 

Ez a cikk Android-, Android Enterprise-, iOS-, macOS-, valamint Windows-eszközökön használható egyéni profilok létrehozásához tartalmaz hivatkozásokat.

## <a name="available-platforms"></a>Elérhető platformok

Az egyéni beállításokat minden platformra külön-külön kell konfigurálni. Az Android és Windows rendszerű eszközök funkcióinak vezérléséhez például Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket adhat meg. Apple-eszközök esetében importálhat egy, az [Apple Configuratorrel](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) vagy az [Apple Profile Managerrel](https://support.apple.com/profile-manager) létrehozott fájlt.

Az egyéni profilok a beépített profilokhoz hasonlóan hozhatók létre, és a következő platformokon érhetőek el:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>További lépések

A kezdéshez válassza ki a platformot:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

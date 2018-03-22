---
title: macOS-eszköz adatainak törlése
titleSuffix: Microsoft Intune
description: A cikk azt ismerteti, hogyan törölhető macOS rendszerű eszközről minden adat, beleértve az operációs rendszert is.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6ae04abda7f026bcbc02e325274712a386147b8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="erase-all-data-from-a-macos-device"></a>Minden adat törlése macOS rendszerű eszközről

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Lehetőség van arra, hogy a macOS-eszközről minden adatot, többek között az operációs rendszert is törölje. Ezzel együtt az eszköz maga is törölve lesz az Intune-felügyeletből. A végfelhasználók erről nem kapnak figyelmeztető értesítést.

1. Az [Intune-ban az Azure Portalon](https://aka.ms/intuneportal) az **Eszközök** > **Minden Eszköz** lehetőségnél válassza ki azt az eszközt, amelyet törölni szeretne.
![Képernyőkép](./media/device-erase/choosedevice.png)
2. Kattintson a **Továbbiak** > **Törlés** lehetőségre, majd **Helyreállítási PIN-kódként** adjon meg egy 6 jegyű számot. Ezt a PIN-kódot kell megadnia a felhasználónak, hogy az operációs rendszert újra tudja telepíteni az eszközön. A PIN-kódot jegyezze fel, mert a törlés végeztével már nem lesz látható.
![Képernyőkép](./media/device-erase/providepin.png)
3. Az eszköz törléséhez kattintson az **OK** gombra.

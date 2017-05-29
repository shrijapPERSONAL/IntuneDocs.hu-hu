---
title: "Android-felhasználói alkalmazások letöltése | Microsoft Docs"
description: "Módszerek az Android-alkalmazások elérhetővé tételére végfelhasználók számára"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e76e17adac581efd64a54d90b23ad52a12417593
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---


# <a name="how-your-android-users-get-their-apps"></a>Android-felhasználói alkalmazások letöltése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör ismerteti, hogy az androidos végfelhasználók hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz. Az ebben foglalt információk a különböző típusú eszközök (androidos natív vagy Samsung Knox Standard-eszközök) esetén eltérőek lehetnek.

## <a name="native-non-samsung-knox-standard-android-devices"></a>Natív (Samsung Knox Standard) androidos eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Megjelenik egy értesítés, amelyre koppintva a felhasználók elindítják a telepítést. A telepítés befejezését követően megjelenik az értesítés. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintva elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

## <a name="samsung-knox-standard-android-devices"></a>Androidos Samsung Knox Standard-eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Az alkalmazás további felhasználói beavatkozás nélkül telepítve lesz. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | Az alkalmazás felhasználói beavatkozás nélkül telepítve lesz.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

Az alkalmazások az alább leírtak szerint kezelhetők vagy nem kezelhetők. Az alkalmazások kezeltként való beállítása minden típusú androidos eszközön azonos.

**Felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal felügyelhetők. Ezek az Intune által becsomagolt vagy az Intune Mobile Application Management (MAM) SDK-val készített alkalmazások. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal nem felügyelhetők. Ezeket az alkalmazásokat nem az Intune csomagolta be, vagy nem tartalmazzák az Intune MAM SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

### <a name="see-also"></a>További információ
[Alkalmazások hozzáadása a Microsoft Intune-nal](/intune-classic/deploy-use/add-apps)

[iOS-felhasználói alkalmazások letöltése](how-your-ios-users-get-their-apps.md)

[Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)


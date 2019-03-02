---
title: Android-felhasználói alkalmazások letöltése
description: Módszerek az Android-alkalmazások elérhetővé tételére végfelhasználók számára
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/21/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: df2e426120740c13673d053a430181040e19ac78
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238744"
---
# <a name="how-your-android-users-get-their-apps"></a>Android-felhasználói alkalmazások letöltése

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ez a témakör ismerteti, hogy az androidos végfelhasználók hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz. Az ebben foglalt információk a különböző típusú eszközök (androidos natív vagy Samsung Knox Standard-eszközök) esetén eltérőek lehetnek.

## <a name="native-non-samsung-knox-standard-android-devices"></a>Natív (Samsung Knox Standard) androidos eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Megjelenik egy értesítés, amelyre koppintva a felhasználók elindítják a telepítést. A telepítés befejezését követően megjelenik az értesítés. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintva elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

A végfelhasználóknak az [üzletági alkalmazások](lob-apps-android.md) telepítéséhez engedélyezniük kell az ismeretlen forrásból való telepítést. Ezek a beállítások általában két különböző helyen találhatók:

* **Android 7.1.2-es és régebbi**: **Beállítások** > **biztonsági** > **ismeretlen források**
* **Android 8.0 és újabb**: **Beállítások** > **alkalmazások és értesítések** > **speciális alkalmazás-hozzáférés** > **ismeretlen alkalmazások telepítése**  >  **Céges portál** > **engedélyezés ebből a forrásból**

Ebben az esetben a Céges portál értesíti a felhasználót, és közvetlenül végigvezeti a megfelelő beállítás megadásán. 


## <a name="samsung-knox-standard-android-devices"></a>Androidos Samsung Knox Standard-eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Az alkalmazás további felhasználói beavatkozás nélkül telepítve lesz. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | Az alkalmazás felhasználói beavatkozás nélkül telepítve lesz.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

Az alkalmazások az alább leírtak szerint kezelhetők vagy nem kezelhetők. Az alkalmazások kezeltként való beállítása minden típusú androidos eszközön azonos.

**Felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal felügyelhetők. Ezeket az Intune „csomagolta be”, vagy az Intune App SDK-val állították össze. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal nem felügyelhetők. Ezeket az alkalmazásokat nem az Intune csomagolta be, vagy nem tartalmazzák az Intune App SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

### <a name="see-also"></a>Lásd még:
[Alkalmazások hozzáadása a Microsoft Intune-nal](apps-add.md)

[iOS-felhasználói alkalmazások letöltése](end-user-apps-ios.md)

[Windows-felhasználói alkalmazások letöltése](end-user-apps-windows.md)

---
title: "Android-felhasználói alkalmazások letöltése | Microsoft Intune"
description: "Módszerek az Android-alkalmazások elérhetővé tételére végfelhasználók számára"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 627914b2ac877c1b5ff5bc95f7f2098ab8988250
ms.openlocfilehash: 98e712fb852c89c1d092b87482f30ada33010a33


---


# Android-felhasználói alkalmazások letöltése
Ez a témakör ismerteti, hogy az androidos végfelhasználók hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz. Az ebben foglalt információk a különböző típusú eszközök (androidos natív vagy Samsung Knox-eszközök) esetén eltérők lehetnek.

## Androidos natív (nem Samsung Knox-) eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Megjelenik egy értesítés, amelyre koppintva a felhasználók elindítják a telepítést. A telepítés befejezését követően megjelenik az értesítés. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintva elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

## Androidos Samsung Knox-eszközök

| Alkalmazás típusa | Üzletági (LOB) alkalmazások | Play Áruház-alkalmazások  |
| ------------- |-------------| -----|
| Nem kötelező alkalmazások      | A felhasználók a **telepítés** elemre koppintanak a Vállalati portálon. Az alkalmazás további felhasználói beavatkozás nélkül telepítve lesz. | A felhasználók az alkalmazásra koppintanak a Vállalati portálon, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést.|
| Required apps      | Az alkalmazás felhasználói beavatkozás nélkül telepítve lesz.    | A felhasználóknak megjelenik egy értesítés, amelyet nem tudnak bezárni. Az értesítés azt jelzi, hogy szükség van egy alkalmazás telepítésére. A felhasználók az értesítésre koppintanak, és egy megnyíló Play Áruház-oldalra kerülnek, ahonnan elindíthatják a telepítést. A telepítés befejezését követően megjelenik az értesítés. |

Az alkalmazások az alább leírtak szerint kezelhetők vagy nem kezelhetők. Az alkalmazások kezeltként való beállítása minden típusú androidos eszközön azonos.

**Felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal felügyelhetők. Ezek az Intune által becsomagolt vagy az Intune Mobile Application Management (MAM) SDK-val készített alkalmazások. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Ezek az alkalmazások szabályzatokkal nem felügyelhetők. Ezeket az alkalmazásokat nem az Intune csomagolta be, vagy nem tartalmazzák az Intune MAM SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

### További információ
[Alkalmazások hozzáadása a Microsoft Intune-nal](/intune/deploy-use/add-apps)

[iOS-felhasználói alkalmazások letöltése](how-your-ios-users-get-their-apps.md)

[Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->



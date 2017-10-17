---
title: "Eszköznaplók gyűjtése"
description: "Ismerje meg, hogyan gyűjthet naplókat felügyelt eszközeiről."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f54e0d40e0a8f723e04d4c2b936dee37bc611858
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="device-logs"></a>Eszköznaplók

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A hibaelhárítás támogatása érdekében érdemes lehet eszköznaplókat gyűjteni a felhasználók által használt eszközökről. A naplók gyűjtésére vonatkozó utasítások ebben a témakörben találhatók. A naplók gyűjtéséhez általában szükség van az eszköz elérésére, vagy megkérheti a felhasználót, hogy gyűjtse össze ő a naplókat, majd küldje el azokat Önnek.

### <a name="android-logs"></a>Naplók Android-eszközökön
A naplók az Android-eszközökön a következő helyen találhatók: *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

A fájlok olykor nem jelennek meg, főként az újabb Android-eszközökön. Ha ez történik, a felhasználóinak meg kell nyitnia a Céges portál alkalmazást Androidhoz. Itt válasszák a **Beállítások**>**Naplófájlok másolása** elemet, majd indítsák újra az eszközt.

Az alábbi cikkben további információt talál arról, felhasználói hogyan küldhetnek önnek adatnaplókat:

- [Az eszközproblémák rendszergazdai megoldásának támogatása részletes naplózással](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) – Ebben részletes információt talál a részletes naplózás bekapcsolásáról, amely a felhasználók összes adatnaplóját automatikusan elküldi önnek. Alapértelmezés szerint a részletes naplózás be van kapcsolva.

- [Android diagnosztikai adatok naplófájljainak elküldése e-mailben a rendszergazdának](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Diagnosztikai adatok naplófájljainak elküldése USB-kábelen keresztül a rendszergazdának](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>iOS-naplók

A felhasználó a regisztrációval kapcsolatos hibákat a következő cikkben leírtak szerint küldheti el Önnek: [Az iOS regisztrálási hibáinak elküldése a rendszergazdának](/intune-user-help/send-errors-to-your-it-admin-ios).

A felhasználó a következő cikkben leírtak szerint küldheti el az eszköznaplókat: [iOS-eszköznaplók küldése](/intune-user-help/send-logs-to-microsoft-ios).

### <a name="mac-os-x-logs"></a>Mac OS X naplófájlok

1. Nyissa meg a **Konzol** alkalmazást.
2. A **Fájlok** menüben válassza a következőt: **system.log**.
3. A felső menüsávban válassza a **Fájl** > **Másolat mentése másként** lehetőséget. Ezt követően mentse a fájlt.

### <a name="windows-phone"></a>Windows Phone

Előbb, a menü eléréséhez válassza a Windows Phone céges portál alkalmazásban a három pontot (**...**), majd a **Naplók elküldése** elemet. Ez a funkció a vállalati portál alkalmazásba való bejelentkezés előtt és után egyaránt elérhető.

### <a name="windows"></a>Windows

A windowsos Vállalati portál alkalmazásban a naplók helye a következő: *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.

---
title: "Eszköznaplók gyűjtése | Microsoft Intune"
description: "Ismerje meg, hogyan gyűjthet naplókat felügyelt eszközeiről."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19b0b502d2c8c261947c461f27a0e8153df5b186
ms.openlocfilehash: 1e65c1fa25e273ba03218f79ebeff611138e8013


---

# <a name="device-logs"></a>Eszköznaplók

A hibaelhárítás támogatása érdekében érdemes lehet eszköznaplókat gyűjteni a felhasználók által használt eszközökről. A naplók gyűjtésére vonatkozó utasítások ebben a témakörben találhatók. A naplók gyűjtéséhez általában szükség van az eszköz elérésére, vagy megkérheti a felhasználót, hogy gyűjtse össze ő a naplókat, majd küldje el azokat Önnek.

### <a name="android-logs"></a>Naplók Android-eszközökön
A naplók az Android-eszközökön a következő helyen találhatók: *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

A fájlok olykor nem jelennek meg, főként az újabb Android-eszközökön. Ha ez történik, a végfelhasználóknak meg kell nyitniuk a Vállalati portál alkalmazás Android-verziójában a **Beállítások** elemet, majd a **Naplók másolása** lehetőséget választani, és újra kell indítaniuk az eszközt. 

Az alábbi cikkben további információt talál arról, felhasználói hogyan küldhetnek önnek adatnaplókat:

- [Az eszközproblémák rendszergazdai megoldásának támogatása részletes naplózással](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) – Ebben részletes információt talál a részletes naplózás bekapcsolásáról, amely a felhasználók összes adatnaplóját automatikusan elküldi önnek. Alapértelmezés szerint a részletes naplózás be van kapcsolva.

- [Android diagnosztikai adatok naplófájljainak elküldése e-mailben a rendszergazdának](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Diagnosztikai adatok naplófájljainak elküldése USB-kábelen keresztül a rendszergazdának](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>iOS-naplók

A felhasználó a regisztrációval kapcsolatos hibákat a következő cikkben leírtak szerint küldheti el Önnek: [Az iOS regisztrálási hibáinak elküldése a rendszergazdának](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Mac OS X naplófájlok

1. Nyissa meg a **Konzol** alkalmazást.
2. A **Fájlok** menüben válassza a következőt: **system.log**.
3. A felső menüsávban válassza a **Fájl** > **Másolat mentése másként** lehetőséget. Ezt követően mentse a fájlt.

### <a name="windows-phone"></a>Windows Phone

A Windows Phone vállalati portál alkalmazásban a felhasználó a **…** választja, hogy A megnyíló menüben válassza a **Naplók küldése** lehetőséget. Ez a funkció a vállalati portál alkalmazásba való bejelentkezés előtt és után egyaránt elérhető.

### <a name="windows"></a>Windows

A windowsos Vállalati portál alkalmazásban a naplók helye a következő: *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO2-->



---
title: "Eszköznaplók gyűjtése | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3233346702cf6de968abb251e885dc208d7720c
ms.openlocfilehash: 183888119325568c857240a038740898a630a696


---

# Eszköznaplók

A hibaelhárítás támogatása érdekében érdemes lehet eszköznaplókat gyűjteni a felhasználók által használt eszközökről. A naplók gyűjtésére vonatkozó utasítások ebben a témakörben találhatók. A naplók gyűjtéséhez általában szükség van az eszköz elérésére, vagy megkérheti a felhasználót, hogy gyűjtse össze ő a naplókat, majd küldje el azokat Önnek.

### A naplók helye Android-eszközökön
A naplók az Android-eszközökön a következő helyen találhatók: *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. A felhasználó e-mailben is elküldheti Önnek a naplófájlokat, ennek menetéről további információ[Az Android diagnosztikai adatait tartalmazó naplófájlok elküldése e-mailben a rendszergazdának](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) című cikkben találhat.

### iOS-naplók

A felhasználó a regisztrációval kapcsolatos hibákat a következő cikkben leírtak szerint küldheti el Önnek: [Az iOS regisztrálási hibáinak elküldése a rendszergazdának](/intune/enduser/send-errors-to-your-it-admin-ios)

### Mac OS X-eszközök

1. Nyissa meg a **Konzol** alkalmazást.
2. A **Fájlok** menüben válassza a következőt: **system.log**.
3. A felső menüsávban válassza a **Fájl** > **Másolat mentése másként** lehetőséget. Ezt követően mentse a fájlt.

### Windows Phone

A felhasználó kattintson a **Windows Phone Vállalati portál** alkalmazás **…** ikonjára. A megnyíló menüben válassza a **Naplók küldése** lehetőséget. Ez a funkció a portálra való bejelentkezés előtt és után egyaránt elérhető.

### Windows

A windowsos Vállalati portál alkalmazásban a naplók helye a következő: *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Sep16_HO2-->



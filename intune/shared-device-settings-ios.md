---
title: "Megosztott eszközök Intune-beli konfigurációs beállításai iOS-re"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Ismertető az iOS-eszköz zárolási képernyőjén információ megjelenítéséhez használható beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a2aba8b2f062a3e06d517a572992b84fd977514
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Közös használatú eszköz konfigurációs beállításai üzenetek megjelenítéséhez az iOS-eszköz zárolási képernyőjén

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A megosztott eszköz konfigurációs beállításaival a rendszergazdák a bejelentkezési ablakban és a zárolási képernyőn megjelenő opcionális szöveget adhatnak meg (például „ha megtalálja, itt adja le” szöveget vagy eszközcímke-információt). 

>[!IMPORTANT]
> Ez a funkció az iOS 9.3-as vagy újabb verzióját futtató felügyelt eszközökön támogatott.

1. Az **Eszközfunkciók** panelen válassza a **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** lehetőséget.
2. A **Megosztott eszköz konfigurációja (csak felügyelt eszközökön)** panelen konfigurálja a következőket:
    - **Eszközcímke-információ** – Adjon meg információkat az eszköz eszközcímkéjéről. Például: **A Contoso vállalat tulajdona**. A megadott információ minden eszközön megjelenik, amelyhez ezt a profilt hozzárendeli.
    - **Lábjegyzet a zárolási képernyőn** – Adjon meg egy szöveget, amely elősegíti, hogy az elvesztett vagy ellopott eszközt visszahozzák. Például: **Ha megtalálta, kérjük, hívja ezt a számot: <telefonszám>**.
3. Ha végzett, válassza az **OK** lehetőséget annyiszor, amíg vissza nem tér a **Profil létrehozása** panelhez, majd válassza a **Létrehozás** elemet. 


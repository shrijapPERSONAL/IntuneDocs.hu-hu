---
title: "Alkalmazások frissítése | Microsoft Intune"
description: "Ez a témakör azt ismerteti, hogy miként frissítheti az alkalmazásokat, ha új verzióra van szükség."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: bb077902e33d6ab18dea33a6ab2d1ff9a70ce937


---

# Alkalmazások frissítése a Microsoft Intune-nal
A Microsoft Intune lehetővé teszi az alkalmazásfrissítések kezelését. Ez a témakör azt ismerteti, hogy miként frissítheti az alkalmazásokat, ha új verzióra van szükség.

## Alkalmazások frissítése
Amikor megjelenik egy telepített alkalmazás egy új verziója, az Intune lehetővé teszi, hogy frissítse és telepítse az alkalmazás újabb verzióját. Egy központi telepítést csak ugyanazon alkalmazás egy újabb verziójára cserélhet le (ugyanazzal az azonosítóval). Az alkalmazásfrissítéseket nem használhatja egy központi telepítés egy másik alkalmazáscsomaggal való frissítésére.

### Alkalmazásazonosítók
Az alkalmazásazonosító egy olyan tulajdonság, amely egyedi módon azonosítja az alkalmazást. Nem telepíthet több alkalmazáspéldányt azonos azonosítóval. Példa:

- **iOS** – Csomagazonosító (példa: com.microsoft.excel)
- **Android** – Csomagazonosító (példa: com.microsoft.excel)
- **Windows Phone** – (xap-telepítő) a Termékazonosítót (GUID) használja
- **Windows** – (appx/appxbundle) a Csomag teljes nevét használja



> [!IMPORTANT]
> Ha egy alkalmazást a **Szükséges telepítés** központi telepítési művelettel telepít, majd később a központi telepítési műveletet az **Elérhető telepítés**lehetőségre módosítja, az alkalmazás frissítései nem lesznek automatikusan telepítve azokon az eszközökön, melyeken a központi telepítési módosítás előtt települt az alkalmazás. A probléma megoldásához tegye a következőket:
> 
> -   Kérje meg az eszköz felhasználóját, hogy nyissa meg a vállalati portált, válassza ki a telepített alkalmazást, majd kattintson a **Telepítés** lehetőségre.
> -   Módosítsa a központi telepítési műveletet az **Eltávolítás**lehetőségre, és az alkalmazás eltávolítása után telepítse újra az alkalmazást az **Elérhető telepítés**központi telepítési művelettel.

### Alkalmazás frissítésére

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) válassza az **Alkalmazások** &gt; **Alkalmazások** elemet.

2.  Válassza ki a frissíteni kívánt alkalmazást az **Alkalmazások** listáról, majd kattintson a **Szerkesztés** lehetőségre.

3.  A **Szoftver szerkesztése** varázslóban adja meg az alkalmazáscsomag minden új adatát.

4.  Ha elkészült, válassza a **Frissítés** elemet.

Amikor az eszközök legközelebb keresnek elérhető alkalmazásokat, az alkalmazás automatikusan a legújabb verzióra fog frissülni.
Az alkalmazáscsomagokból telepített alkalmazások (üzletági alkalmazások) esetében az alkalmazás mind a szükséges, mind az elérhető üzembe helyezésekhez frissül addig, amíg változatlan azonosítóval rendelkezik.
Az áruházi hivatkozásként üzembe helyezett alkalmazások frissítéseit az alkalmazás eredeti áruháza kezeli.






<!--HONumber=Jul16_HO3-->



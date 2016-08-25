---
title: "Alkalmazások frissítése | Microsoft Intune"
description: "Ebből a témakörből megtudhatja, hogyan frissítheti az alkalmazásokat, ha új verzióra van szükség."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ffc9a753f2f5ff2aa98a589b752936d67a0888b5
ms.openlocfilehash: cefe90cdb0cda5ada259576af7cf477642860446


---

# Alkalmazások frissítése a Microsoft Intune-nal
A Microsoft Intune lehetővé teszi az alkalmazásfrissítések kezelését. Ebből a témakörből megtudhatja, hogyan frissítheti az alkalmazásokat, ha új verzióra van szükség.

## Alkalmazások frissítése
Amikor megjelenik egy telepített alkalmazás egy új verziója, az Intune lehetővé teszi, hogy frissítse és telepítse az alkalmazás újabb verzióját. Egy telepítést csak ugyanazon alkalmazás egy újabb verziójára cserélhet le (amely ugyanazzal az azonosítóval rendelkezik). Az alkalmazásfrissítéseket nem használhatja egy központi telepítés egy másik alkalmazáscsomaggal való frissítésére.

### Alkalmazásazonosítók
Az alkalmazásazonosító egy olyan tulajdonság, amely egyedi módon azonosítja az alkalmazást. Nem telepíthet több alkalmazáspéldányt azonos azonosítóval. Az alábbiakban bemutatunk néhány példát az alkalmazásazonosítókra:

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

1.  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza az **Alkalmazások** &gt; **Alkalmazások** elemet.

2.  Válassza ki a frissíteni kívánt alkalmazást az **Alkalmazások** listáról, majd kattintson a **Szerkesztés** lehetőségre.

3.  A **Szoftver szerkesztése** varázslóban adja meg az alkalmazáscsomag minden új adatát.

4.  Ha elkészült, válassza a **Frissítés** elemet.

Amikor az eszközök legközelebb keresnek elérhető alkalmazásokat, az alkalmazás automatikusan a legújabb verzióra fog frissülni.
Az alkalmazáscsomagokból telepített alkalmazások (üzletági alkalmazások) esetében az alkalmazás mind a szükséges, mind az elérhető telepítésekhez frissül mindaddig, amíg változatlan azonosítóval rendelkezik.

Az áruházi hivatkozásként üzembe helyezett alkalmazások frissítéseit az alkalmazás eredeti áruháza kezeli.



<!--HONumber=Aug16_HO3-->



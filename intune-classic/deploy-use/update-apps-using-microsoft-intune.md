---
title: "Alkalmazások frissítése"
description: "Ebből a témakörből megtudhatja, hogyan frissítheti az alkalmazásokat, ha új verzióra van szükség."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 14117098235decb55350dc6d1f1ba9c7475f40b8
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="update-apps-using-microsoft-intune"></a>Alkalmazások frissítése a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune lehetővé teszi az alkalmazásfrissítések kezelését. Ebből a témakörből megtudhatja, hogyan frissítheti az alkalmazásokat, ha új verzióra van szükség.

## <a name="how-to-update-apps"></a>Alkalmazások frissítése
Amikor megjelenik egy telepített alkalmazás egy új verziója, az Intune lehetővé teszi, hogy frissítse és telepítse az alkalmazás újabb verzióját. Egy telepítést csak ugyanazon alkalmazás egy újabb verziójára cserélhet le (amely ugyanazzal az azonosítóval rendelkezik). Az alkalmazásfrissítéseket nem használhatja egy központi telepítés egy másik alkalmazáscsomaggal való frissítésére.

### <a name="app-identifiers"></a>Alkalmazásazonosítók
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

### <a name="to-update-an-app"></a>Alkalmazás frissítésére

1.  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza az **Alkalmazások** &gt; **Alkalmazások** elemet.

2.  Válassza ki a frissíteni kívánt alkalmazást az **Alkalmazások** listáról, majd kattintson a **Szerkesztés** lehetőségre.

3.  A **Szoftver szerkesztése** varázslóban adja meg az alkalmazáscsomag minden új adatát.

4.  Ha elkészült, válassza a **Frissítés** elemet.

Amikor az eszközök legközelebb keresnek elérhető alkalmazásokat, az alkalmazás automatikusan a legújabb verzióra fog frissülni.
Az alkalmazáscsomagokból telepített alkalmazások (üzletági alkalmazások) esetében az alkalmazás mind a szükséges, mind az elérhető telepítésekhez frissül mindaddig, amíg változatlan azonosítóval rendelkezik.

Az áruházi hivatkozásként üzembe helyezett alkalmazások frissítéseit az alkalmazás eredeti áruháza kezeli.

---
title: "Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows-eszköz Intune-beli regisztrálásakor? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4881d765a6a79d380ab6d3facdb55d9f0c81bf97
ms.openlocfilehash: ac4fdc73122fb5dc82771f174d9bd783c186bf9d


---


# Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows-eszköz Intune-beli regisztrálásakor?

Amikor a Munkahelyi portál alkalmazást telepíti, majd egy Windows- vagy Windows Phone-eszközt regisztrál vele, azzal lehetővé teszi, hogy a rendszergazda felügyelje az eszközt, és így biztonságban tartsa a cég vagy az intézmény adatait, a Windows 10-nél korábbi rendszerű eszközök esetében az alábbiakban ismertetett módon. A Windows 10 rendszerű eszközökkel kapcsolatos információkat [ezen az oldalon](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md) találja.

## Mi történik minden Windows-eszközzel a regisztrálás után?
Ha Windows- vagy Windows Phone-eszközét regisztrálja az Intune-ban, a következőkre nyílik lehetősége:

-   Elérheti a vállalat hálózatát, a saját levelezését és a munkájához szükséges fájlokat

-   Letöltheti a vállalati alkalmazásokat a Vállalati portál webhelyről (Windows 7 és Vista rendszer esetében a vállalati alkalmazásokat kizárólag a Vállalati portál webhelyről lehet letölteni)

-   Automatikusan konfigurálhatja vállalati vagy iskolai e-mail-fiókját

-   Ha elveszíti a telefonját, visszaállíthatja a gyári beállításait

Egy eszköz regisztrálásával jogosultságot ad a rendszergazdának a következő műveletek elvégzésére:

-   Az eszköz visszaállítása az alapértelmezett gyári beállításokra. Az eszköz elvesztésekor vagy ellopásakor bizonyulhat hasznosnak.

-   Csak a munkahelyi fájlok és munkahelyi alkalmazások eltávolítása. **A saját adatok és beállítások nem törlődnek.**

-   Az IT-rendszergazda leltárt készíthet az eszközre telepített szoftverekről, ideértve az Ön által telepített szoftvereket is.

-   Követelményeket határozhat meg az eszközön, például a jelszó vagy PIN-kód használatát a vállalati adatok védelme érdekében. Az IT-rendszergazda korlátozhatja, hogy hányszor lehet helytelen jelszót megadni, és kizárhatja a felhasználót az eszközről, ha túl sokszor próbálkozott.

-   Megkövetelheti az eszközön tárolt adatok titkosítását a céges adatok védelme érdekében az eszköz elvesztése vagy ellopása esetén. 

-   Ehhez el kell fogadnia a használati feltételeket.

-   Megakadályozhatja, hogy felvételt készíthessen a vállalattal kapcsolatos adatokról.

## Mi történik minden Windows rendszerű számítógéppel a regisztrálás után?

-  Olyan szoftverek települnek a számítógépre, amelyek lehetővé teszik a rendszergazda számára a számítógép felügyeletét, Önnek pedig a különböző vállalati erőforrások, például alkalmazások és támogatási információk elérését. A rendszergazda automatikusan frissítheti ezeket a szoftvereket.

-  Lehetséges, hogy az Intune Endpoint Protection is települ a számítógépre. Ez egy vírusok és kártevő szoftverek elleni védelmi alkalmazás.

-  A IT rendszergazda adatokat gyűjthet a számítógép merevlemezéről, illetve adatokat törölhet róla.

-  Az IT rendszergazda alkalmazásokat és frissítéseket telepíthet a számítógépre.

## Mi történik az eszköz regisztrálása után nyolcóránként?
A regisztrált eszközök megközelítőleg nyolcóránként elvégzik a következőket:

-   Az IT rendszergazda által elérhetővé tett házirendek és alkalmazásfrissítések letöltése.

-   A hardverleltár változásainak elküldése.

-   A vállalati alkalmazások leltárában bekövetkezett változások elküldése.

Ha kérdése van, lépjen kapcsolatba a rendszergazdával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).




<!--HONumber=Sep16_HO4-->



---
title: "Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows-eszköz Intune-beli regisztrálásakor? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: 840d985fd2c4771831f722cdff214026a383f606


---


# Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows-eszköz Intune-beli regisztrálásakor?

Amikor a Vállalati portál alkalmazást telepíti, majd egy Windows- vagy Windows Phone-eszközt regisztrál vele, azzal lehetővé teszi, hogy a rendszergazda felügyelje az eszközt, és ezáltal biztonságban tartsa a vállalati vagy iskolai adatokat, a Windows 10-nél korábbi rendszerű eszközök esetében az alábbiakban ismertetett módon. Windows 10-eszközökkel kapcsolatos információkért nyissa meg [ezt az oldalt](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Mi történik minden Windows-eszközzel a regisztrálás után?
Ha Windows- vagy Windows Phone-eszközét regisztrálja az Intune-ban, a következőkre nyílik lehetősége:

-   Elérheti a vállalat hálózatát, a saját levelezését és a munkájához szükséges fájlokat

-   Letöltheti a vállalati alkalmazásokat a Vállalati portál webhelyről (Windows 7 és Vista rendszer esetében a vállalati alkalmazásokat kizárólag a Vállalati portál webhelyről lehet letölteni)

-   Automatikusan konfigurálhatja vállalati vagy iskolai e-mail-fiókját

-   Ha elveszíti a telefonját, visszaállíthatja a gyári beállításait

Egy eszköz regisztrálásával jogosultságot ad a rendszergazdának a következő műveletek elvégzésére:

-   Az eszköz visszaállítása az alapértelmezett gyári beállításokra. Az eszköz elvesztésekor vagy ellopásakor bizonyulhat hasznosnak.

-   Az összes céges adat és telepített munkahelyi alkalmazás eltávolítása. A saját adatok és beállítások nem törlődnek.

-   Az IT rendszergazda leltárt készíthet a számítógépre telepített szoftverekről, ideértve az Ön által személyes használatra telepített szoftvereket is.

-   Jelszó vagy PIN-kód megadásának kényszerítése az eszközön, így túl sok helytelen jelszó megadásakor a rendszer kizárhatja az eszközről, vagy visszaállíthatja az eszközön a gyári alapbeállításokat, amely az adatok törlését is magával vonhatja.

-   Az eszközön tárolt adatok titkosításának kényszerítése segít az adatok védelmében az eszköz elvesztésekor vagy ellopásakor.

-   Ehhez el kell fogadnia a használati feltételeket.

-   Az IT rendszergazda házirendeket léptethet életbe a számítógépen. Lehetséges például, hogy jelszót vagy PIN-kódot kell beállítania a számítógépen; ebből fakadóan kizárhatja magát a számítógépről, vagy letörölheti az összes adatot a számítógép merevlemezéről, ha túlságosan sokszor adja meg hibásan a jelszót.

-   Az SD-kártya letiltása.

## Mi történik minden Windows rendszerű számítógéppel a regisztrálás után?

-  Olyan szoftverek települnek a számítógépre, amelyek lehetővé teszik a rendszergazda számára a számítógép felügyeletét, Önnek pedig a különböző vállalati erőforrások, például alkalmazások és támogatási információk elérését. A rendszergazda automatikusan frissítheti ezeket a szoftvereket.

-  Lehetséges, hogy az Intune Endpoint Protection is települ a számítógépre. Ez egy vírusok és kártevő szoftverek elleni védelmi alkalmazás.

-  Az IT rendszergazda leltárt készíthet a számítógépre telepített szoftverekről, ideértve az Ön által személyes használatra telepített szoftvereket is.

-  Elképzelhető, hogy el kell fogadnia a vonatkozó használati feltételeket.

-  A IT rendszergazda adatokat gyűjthet a számítógép merevlemezéről, illetve adatokat törölhet róla. A rendszergazda akár a merevlemez teljes tartalmát is törölheti.

-  Az IT rendszergazda alkalmazásokat és frissítéseket telepíthet a számítógépre.

-  Az IT rendszergazda házirendeket léptethet életbe a számítógépen. Lehetséges például, hogy jelszót vagy PIN-kódot kell beállítania a számítógépen; ebből fakadóan kizárhatja magát a számítógépről, vagy letörölheti az összes adatot a számítógép merevlemezéről, ha túlságosan sokszor adja meg hibásan a jelszót.


## Mi történik az eszköz regisztrálása után nyolcóránként?
A regisztrált eszközök megközelítőleg nyolcóránként elvégzik a következőket:

-   Az IT rendszergazda által elérhetővé tett házirendek és alkalmazásfrissítések letöltése.

-   A hardverleltár változásainak elküldése.

-   A vállalati alkalmazások leltárában bekövetkezett változások elküldése.

A regisztrálás lépéseit lásd: [Windows-eszköz regisztrálása az Intune-ban](enroll-your-device-in-intune-windows.md). A [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet az Intune-ban?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) című szakaszból megtudhatja, hogy a rendszergazda mit láthat az eszközén.

Ha kérdése van, lépjen kapcsolatba a rendszergazdával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).

### További információ
[Windows-eszköz használata az Intune-nal](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO4-->



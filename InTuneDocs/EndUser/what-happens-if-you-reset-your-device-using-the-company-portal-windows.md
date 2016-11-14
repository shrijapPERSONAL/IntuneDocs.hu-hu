---
title: "Mi történik, ha alaphelyzetbe állít egy saját Windows-eszközt a Vállalati portálon? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bdb221d9c52231d31511b29cbdc69985bc0da5b2
ms.openlocfilehash: 1cc7e4ad5abee16a0e06780b37c23903d196a018


---


# Mi történik, ha alaphelyzetbe állít egy saját Windows-eszközt a Vállalati portálon?

Ha a Vállalati portál alkalmazást vagy a [Vállalati portál webhelyet](reset-your-device-cpwebsite.md) használja a Windows-eszköz alaphelyzetbe állításához, a művelet visszaállítja az eszközt annak gyári állapotába, és törli az összes alkalmazást, beállítást és adatot, a személyes adatokat is beleértve. Az, hogy az adott eszközön mi történik, az eszköz típusától és használati módjától függ (erről részletes információk az alábbi táblázatban láthatók). Az elveszett vagy ellopott eszköz alaphelyzetbe állításával kapcsolatos útmutatásokért lásd: [Elveszett vagy ellopott eszköz alaphelyzetbe állítása (tartalmának végleges törlése)](reset-erase-your-lost-or-stolen-device-windows.md).

|Eszközök konfigurálása és felügyelete|Eszköz típusa|
|---------------------------------------|---------------|
|A rendszergazda felügyeli a mobileszközt|**Windows 10 és Windows Phone 8.1**</br>Az eszköz nem jelenik meg többé a Vállalati portálon, és a Vállalati portál megpróbálja visszaállítani az eszközt a gyári alapértékekre. A rendszer eltávolítja a személyes adatait, alkalmazásait és beállításait. <br /><br />**Windows 10 mobil verzió**</br>Az eszköz regisztrációjának törlése kizárólag alaphelyzetbe állítással lehetséges.|
|Az eszköz csak a vállalati e-mailekhez férhet hozzá.|**Windows Phone 8.1**<br />Az eszköz nem jelenik meg többé a Vállalati portálon, és a rendszer törli a vállalati e-mail-fiókját és a nem mentett e-maileket.<br /><br />**Windows 7 vagy Windows Vista**<br />Kizárólag e-mailek elérésére használt, Windows 7 vagy korábbi operációs rendszert futtató számítógép nem állítható alaphelyzetbe.<br /><br />**Windows 8.1 és Windows 8**<br />Az eszköz nem jelenik meg többé a Vállalati portálon, és a rendszer törli a vállalati e-mail-fiókját és a nem mentett e-maileket.|
|Számítógépek és laptopok|**Windows 8.1 és Windows 8**<br />Windows 8 vagy Windows 8.1 rendszert futtató számítógép nem állítható alaphelyzetbe, kivéve, ha kizárólag e-mailek elérésére használják.<br /><br />**Windows 7 vagy Windows Vista**<br />Windows 7 vagy korábbi operációs rendszert futtató számítógép nem állítható alaphelyzetbe.|

Ha kérdése van, lépjen kapcsolatba a rendszergazdával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->



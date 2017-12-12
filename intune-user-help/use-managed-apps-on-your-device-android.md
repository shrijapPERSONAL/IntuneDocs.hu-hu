---
title: "Felügyelt alkalmazások használata Android-eszközön | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed10a62c-b026-4ad3-ac41-641933522df2
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 5099e7e476477258267b2ae6c94f48693a6f0253
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="use-managed-apps-on-your-android-device"></a>Felügyelt alkalmazások használata Android-eszközön

A felügyelt alkalmazások olyan alkalmazások, amelyeket a cég informatikai támogatási szolgálata beállíthat a rajtuk keresztül elérhető vállalati adatok védelme érdekében. Amikor androidos eszközön felügyelt alkalmazásban fér hozzá vállalati adatokhoz, észreveheti, hogy az alkalmazás a várttól kissé eltérően működik. Előfordulhat például, hogy nem tudja másolni és beilleszteni a védett vállalati adatokat, vagy nem tudja menteni az adatokat bizonyos helyekre.

A különböző felügyelt alkalmazások együtt is működhetnek az eszközön annak érdekében, hogy el tudja végezni mindennapos feladatait, miközben a vállalati adatok védelméről is gondoskodnak. Ha például megnyit egy vállalati fájlt egy felügyelt alkalmazásban, és egy másik alkalmazásra van szükség a fájl megtekintéséhez, a szükséges alkalmazás automatikusan megnyílik. Ha egy szükséges alkalmazás nem érhető el, akkor előfordulhat, hogy bizonyos műveletek, például a dokumentumok vagy a felügyelt dokumentumokban található webes hivatkozások megnyitása nem végezhetők el.

Amikor felügyelt alkalmazásban fér hozzá vállalati adatokhoz, az alábbihoz hasonló üzenet jelenik meg, amely tudatja, hogy egy felügyelt alkalmazást nyitott meg.

![open-managed-apps-message](./media/managed-apps-message.png)

## <a name="how-do-i-get-managed-apps"></a>Hogyan szerezhetők be a felügyelt alkalmazások?
Különböző módokon szerezhet be felügyelt alkalmazásokat:

-   Ha az eszköze regisztrálva van a Microsoft Intune-nal, akkor telepítheti az alkalmazást a Céges portál alkalmazásból vagy a Céges portál webhelyről, illetve a cég informatikai támogatási szolgálata is telepítheti azt az eszközére. A regisztrációval kapcsolatos információkért lásd: [Eszköz regisztrálása az Intune-ban](enroll-your-device-in-Intune-android.md).

-   Alkalmazást telepíthet a Play Áruházból is, majd bejelentkezhet az Intune által felügyelt vállalati felhasználói fiókjával.

## <a name="what-can-my-company-support-manage-in-an-app"></a>Mit felügyelhet a cég informatikai támogatási szolgálata az alkalmazásokban?
Itt talál néhány példát arra, hogy melyek lehetnek azok a cég informatikai támogatási szolgálata által az alkalmazásokban felügyelt elemek, amelyek hatással lehetnek a vállalati adatok használatára az eszközön:

-   Adott webhelyek hozzáférése

-   Adatátvitel alkalmazások között

-   Fájlok mentése

-   Másolási és beillesztési műveletek

-   PIN-hozzáférési követelmények

-   Vállalati hitelesítő adatokkal végzett bejelentkezés

-   Biztonsági mentés létrehozásának lehetősége a felhőben

-   Képernyőfelvételek készítésének lehetősége

-   Adattitkosítási követelmények

A következők olyan általános alkalmazások, amelyeket az informatikai részlege felügyelhet:

-   Intune Managed Browser

-   Intune Image Viewer

-   Intune PDF Viewer

-   Intune AV Viewer

-   Microsoft Word, Excel és PowerPoint

Az eszközén lévő felügyelt alkalmazásokról további információért lépjen kapcsolatba a cég informatikai támogatási szolgálatával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).

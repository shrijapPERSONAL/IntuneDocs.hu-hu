---
title: Felügyelt alkalmazások használata iOS-eszközön | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35d77c9aa739096f36f4dbf4b75a4186e55a3381
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501603"
---
# <a name="use-managed-apps-on-your-ios-device"></a>Felügyelt alkalmazások használata iOS-eszközön

A felügyelt alkalmazások olyan alkalmazások, amelyeket a cég informatikai támogatási szolgálata beállíthat a rajtuk keresztül elérhető vállalati adatok védelme érdekében. Amikor iOS-es eszközön felügyelt alkalmazásban fér hozzá vállalati adatokhoz, észreveheti, hogy az alkalmazás a várttól kissé eltérően működik. Előfordulhat például, hogy nem tudja másolni és beilleszteni a védett vállalati adatokat, vagy nem tudja menteni az adatokat bizonyos helyekre.

A különböző felügyelt alkalmazások együtt is működhetnek az eszközön annak érdekében, hogy el tudja végezni mindennapos feladatait, miközben a vállalati adatok védelméről is gondoskodnak. Ha például megnyit egy vállalati fájlt egy felügyelt alkalmazásban, és egy másik alkalmazásra van szükség a fájl megtekintéséhez, a szükséges alkalmazás automatikusan megnyílik. Ha egy szükséges alkalmazás nem érhető el, akkor előfordulhat, hogy bizonyos műveletek, például a dokumentumok vagy a felügyelt dokumentumokban található webes hivatkozások megnyitása nem végezhetők el.

Amikor felügyelt alkalmazásban fér hozzá vállalati adatokhoz, az alábbihoz hasonló üzenet jelenik meg, amely tudatja, hogy egy felügyelt alkalmazást nyitott meg.

![managed-apps-message-ios](./media/managed-apps-message.png)

## <a name="how-do-i-get-managed-apps"></a>Hogyan szerezhetők be a felügyelt alkalmazások?  
Különböző módokon szerezhet be felügyelt alkalmazásokat:

-   Ha az eszköze regisztrálva van a Microsoft Intune-nal, akkor telepítheti az alkalmazást a Céges portál alkalmazásból vagy a Céges portál webhelyről, illetve a cég informatikai támogatási szolgálata is telepítheti azt az eszközére. A regisztrálással kapcsolatban lásd: [iOS-eszköz regisztrálása az Intune-ban](enroll-your-device-in-intune-ios.md), illetve [MacOS-eszköz regisztrálása az Intune-ban](enroll-your-device-in-intune-macos.md).

-   Alkalmazást telepíthet az App Store-ból is, majd bejelentkezhet az Intune által felügyelt vállalati felhasználói fiókjával.

Egyes esetekben előfordulhat, hogy a cég informatikai támogatási szolgálata egy telepített alkalmazáshoz több licencet is vásárol. Ha egy olyan üzenet jelenik meg, amely arra kéri, hogy fogadja el az Apple Volume Purchase Program szerződését, ez teljesen normális, és elfogadhatja. Ha nem fogadja el, nem fogja tudni telepíteni az alkalmazást.

## <a name="available-apps"></a>Nem kötelező alkalmazások   
 A szervezet választja ki a megfelelő és alkalmazások hasznos az Ön számára a munkahelyi vagy iskolai rendszerhez. Ezeket az alkalmazásokat csak azok a céges portálon megtalálhatja.   

 Alkalmazások is elérhető lesz az eszköz típusa alapján. Például ha az iOS-hez készült céges portál alkalmazás használ, hozzáférhet az iOS-alkalmazások, de nem Android-alkalmazások.   

## <a name="request-an-app-for-work-or-school"></a>A kérelem egy alkalmazást a munkahelyi vagy iskolai fiók   
 Ha szükséges, de nem látható a vállalati portál alkalmazás, kérheti. Keresse meg a kapcsolattartási adatait a **segélyszolgálat** a vállalati portál alkalmazás **támogatási** fülre. Ugyanazokat az adatokat a látni fogja a [céges portál webhelyen](https://go.microsoft.com/fwlink/?linkid=2010980).   
 

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

Az eszközén lévő felügyelt alkalmazásokról további információért lépjen kapcsolatba a cég informatikai támogatási szolgálatával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).

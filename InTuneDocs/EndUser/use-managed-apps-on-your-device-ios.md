---
# required metadata

title: Felügyelt alkalmazások használata az eszközön | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e

# optional metadata

ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Felügyelt alkalmazások használata az eszközön

A felügyelt alkalmazások olyan alkalmazások, amelyeket a rendszergazda konfigurálhat a rajtuk keresztül elérhető vállalati adatok védelme érdekében. Amikor iOS-es eszközön felügyelt alkalmazásban fér hozzá vállalati adatokhoz, észreveheti, hogy az alkalmazás a várttól kissé eltérően működik. Előfordulhat például, hogy nem tudja másolni és beilleszteni a védett vállalati adatokat, vagy nem tudja menteni az adatokat bizonyos helyekre.

A különböző felügyelt alkalmazások együtt is működhetnek az eszközön annak érdekében, hogy el tudja végezni mindennapos feladatait, miközben a vállalati adatok védelméről is gondoskodnak. Ha például megnyit egy vállalati fájlt egy felügyelt alkalmazásban, és egy másik alkalmazásra van szükség a fájl megtekintéséhez, a szükséges alkalmazás automatikusan megnyílik. Ha egy szükséges alkalmazás nem érhető el, akkor előfordulhat, hogy bizonyos műveletek, például a dokumentumok vagy a felügyelt dokumentumokban található webes hivatkozások megnyitása nem végezhetők el.

Amikor felügyelt alkalmazásban fér hozzá vállalati adatokhoz, az alábbihoz hasonló üzenet jelenik meg, amely tudatja, hogy egy felügyelt alkalmazást nyitott meg.

![managed-apps-message-ios](./media/managed-apps-message.png)

### Hogyan szerezhetők be a felügyelt alkalmazások?
Különböző módokon szerezhet be felügyelt alkalmazásokat:

-   Ha az eszköze regisztrálva van a Microsoft Intune-nal, akkor telepítheti az alkalmazást a Vállalati portál alkalmazásból vagy a Vállalati portál webhelyről, illetve a rendszergazda is telepítheti azt az eszközére. A regisztrálással kapcsolatban lásd: [iOS-eszköz regisztrálása az Intune-ban](enroll-your-device-in-intune-ios.md), illetve [Max OS X-eszköz regisztrálása az Intune-ban](enroll-your-device-in-intune-mac-os-x.md).

-   Alkalmazást telepíthet az App Store-ból is, majd bejelentkezhet az Intune által felügyelt vállalati felhasználói fiókjával.

### Mit felügyelhet a rendszergazda az alkalmazásokban?
Itt talál néhány példát arra, hogy melyek lehetnek azok a rendszergazda által az alkalmazásokban felügyelt elemek, amelyek hatással lehetnek a vállalati adatok használatára az eszközön:

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

-   Felügyelt webböngésző

-   Felügyelt képmegtekintő

-   Felügyelt PDF-megtekintő

-   Felügyelt AV-lejátszó

-   Microsoft Word, Excel, PowerPoint

Az eszközén lévő felügyelt alkalmazásokról további információért lépjen kapcsolatba az informatikai rendszergazdájával.

### További információ
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=May16_HO2-->



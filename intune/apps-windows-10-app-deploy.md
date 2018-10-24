---
title: Windows 10-es alkalmazások telepítése a Microsoft Intune-nal
titlesuffix: ''
description: A Microsoft Intune-nal elérhető Windows 10-es alkalmazási helyzetek ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61e2ec9def6ecba265521cf801322d592dd4dac9
ms.sourcegitcommit: ca132d509e3c978d18e50eac89e1a1ed7ddb25c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48866354"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Windows 10-es alkalmazások telepítése a Microsoft Intune-nal 

A Microsoft Intune jelenleg többféle alkalmazástípust és telepítési helyzetet támogat Windows 10 rendszerű eszközökön. Miután hozzáadott egy alkalmazást az Intune-hoz, azt felhasználókhoz és eszközökhöz rendelheti hozzá. A következő információ a támogatott Windows 10-es alkalmazási helyzetekkel kapcsolatos további részleteket mutat be. Ezenfelül alkalmazásoknak a Windowsban történő telepítésekor figyelembe veendő fontos tudnivalókat is tartalmaz. 

A Windows 10-es eszközökön támogatott alkalmazástípusok az üzleti alkalmazások és a Vállalati Microsoft Áruházbeli alkalmazások. A windowsos alkalmazások fájlnévkiterjesztései közé tartozik az **.msi**, az **.appx**, az **.appxbundle**, az **.msix** és az **.msixbundle** is.  

> [!Note]
> Az alkalmazások eszközkörnyezetben történő telepítéséhez szükséges minimális Windows 10 frissítés a [2018. május 23-ai – KB4100403 (OS Build 17134.81)](https://support.microsoft.com/en-us/help/4100403/windows-10-update-kb4100403).

## <a name="windows-10-line-of-business-apps"></a>Windows 10-es üzletági alkalmazások

A Windows 10-es üzletági alkalmazások alá vannak írva és fel vannak töltve az Intune felügyeleti konzoljára. Lehetnek olyan modern alkalmazások, mint az Univerzális Windows-platform (UWP) alkalmazások és a Windows-alkalmazáscsomagok (AppX), de Win 32-alkalmazások is, amilyenek az egyszerű Microsoft Installer telepítőcsomag-fájlok (MSI). Az üzletági alkalmazások frissítéseit minden alkalommal a rendszergazdának kell feltöltenie és üzembe helyeznie. Az üzembe helyezett frissítések felhasználói beavatkozás nélkül, automatikusan telepítve lesznek azoknak a végfelhasználóknak az eszközein, akik telepítették az alkalmazást. A felhasználó nem avatkozhat be a frissítésekbe. 

## <a name="microsoft-store-for-business-apps"></a>Vállalati Microsoft Áruházbeli alkalmazások

A Vállalati Microsoft Áruház felügyeleti portálján megvásárolt modern Vállalati Microsoft Áruházbeli alkalmazások a felügyelethez a Microsoft Intune-ra lesznek szinkronizálva. Az alkalmazások lehetnek **online licencelésűek** vagy **offline licencelésűek**. A Vállalati Microsoft Áruházbeli alkalmazások frissítéseit közvetlenül a Microsoft Áruház felügyeli, és nem kívánnak további rendszergazdai beavatkozást. A rendszergazda meg is akadályozhatja bizonyos alkalmazások frissítését egyéni egységes erőforrás-azonosító (Uniform Resource Identifier, URI) használatával. További információ: [Vállalati alkalmazásfelügyelet – Alkalmazás automatikus frissítésének megakadályozása](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Az eszközön a végfelhasználó is letilthatja az eszközön lévő összes Vállalati Microsoft Áruházbeli alkalmazás frissítéseit. 

## <a name="installing-apps-on-windows-10-devices"></a>Alkalmazások telepítése Windows 10-es eszközökön
Az alkalmazás típusától függően az alkalmazás két módszer egyikével telepíthető Windows 10-es eszközre:

- **Felhasználói környezet**: Ha az alkalmazás felhasználói környezetben van üzembe helyezve, a felügyelt alkalmazás akkor lesz telepítve a felhasználó számára az eszközön, amikor a felhasználó bejelentkezik az eszközre. Lényeges, hogy az alkalmazás telepítése csak akkor lesz sikeres, ha a felhasználó bejelentkezik az eszközre. 
    - A modern üzletági és Microsoft Áruházbeli alkalmazások (online vagy offline) telepíthetők felhasználói környezetben, és az Elérhető és Szükséges hozzárendelés-típust is támogatják.
- **Eszközkörnyezet**: Ha az alkalmazás eszközkörnyezetben van üzembe helyezve, akkor a felügyelt alkalmazást az Intune telepíti közvetlenül az eszközre.
    - Eszközkörnyezetben csak modern üzleti alkalmazások és online licencelésű Vállalati Microsoft Áruházbeli alkalmazások helyezhetők üzembe, és csak a Szükséges hozzárendelés-típust támogatják.

Ha egy alkalmazás eszközkörnyezetben van üzembe helyezve, a telepítés csak akkor lesz sikeres, ha célja az eszközkörnyezetet támogató eszköz. Az eszközkörnyezetben történő üzembe helyezés ezen felül a következő feltételeknek tesz eleget:
- Ha egy alkalmazás eszközkörnyezetben van üzembe helyezve, célja pedig egy felhasználó, akkor a telepítés sikertelen lesz és a következő állapot- és hibaüzenet jelenik meg a felügyeleti konzolon:
    - Állapot: Sikertelen.
    - Hiba: Eszközkörnyezetben történő telepítés célja nem lehet felhasználó.
- Ha egy alkalmazás eszközkörnyezetben van üzembe helyezve, célja azonban egy olyan eszköz, amely nem támogatja az eszközkörnyezetet, akkor a telepítés sikertelen lesz, és a következő állapot- és hibaüzenet jelenik meg a felügyeleti konzolon:
    - Állapot: Sikertelen.
    - Hiba: A platform nem támogatja az eszközkörnyezetben történő telepítést. 

> [!Note]
> Ha egy adott üzembe helyezés alkalmazás-hozzárendelése már ki van mentve, ennek a hozzárendelésnek a környezete többé nem módosítható, csak a modern alkalmazások esetén. Modern alkalmazások esetén a környezet felhasználóiról eszközkörnyezetre módosítható. 

Ha egy felhasználó/eszköz esetében a szabályzatok ellentmondanak, az érvényre jutó szabályzat a következő prioritások alapján lesz meghatározva:
- Az eszközkörnyezetek szabályzatai magasabb prioritásúak a felhasználói környezetekéinél. 
- A telepítési szabályzatok magasabb prioritásúak az eltávolításiaknál.

Alkalmazásoknak a Microsoft Intune használatával való hozzárendeléséről az [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md) és az [Alkalmazás-hozzárendelések belefoglalása vagy kizárása a Microsoft Intune-ban](apps-inc-exl-assignments.md) című cikkek tartalmaznak további információt. Az Intune-beli alkalmazástípusokat az [Alkalmazások hozzáadása a Microsoft Intune-hoz](apps-add.md) című cikk ismerteti.

## <a name="next-steps"></a>További lépések

- További információ az alkalmazások csoportokhoz rendeléséről: [Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md).
- Alkalmazás-hozzárendelések figyelésével kapcsolatos további tudnivalókért lásd: [Alkalmazások figyelése](apps-monitor.md).

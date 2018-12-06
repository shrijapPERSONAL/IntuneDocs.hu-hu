---
title: Windows 10-es alkalmazások telepítése a Microsoft Intune-nal
titlesuffix: ''
description: A Microsoft Intune-nal elérhető Windows 10-es alkalmazási helyzetek ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 00e8b0e35514fe583027d15fdcc810295aa9fa9e
ms.sourcegitcommit: 88f760abcea7348a0c6d00b533b54a6ff68d3985
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977286"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Windows 10-es alkalmazások telepítése a Microsoft Intune-nal 

A Microsoft Intune jelenleg többféle alkalmazástípust és telepítési helyzetet támogat Windows 10 rendszerű eszközökön. Miután hozzáadott egy alkalmazást az Intune-hoz, azt felhasználókhoz és eszközökhöz rendelheti hozzá. A következő információ a támogatott Windows 10-es alkalmazási helyzetekkel kapcsolatos további részleteket mutat be. Ezenfelül alkalmazásoknak a Windowsban történő telepítésekor figyelembe veendő fontos tudnivalókat is tartalmaz. 

A Windows 10-es eszközökön támogatott alkalmazástípusok az üzleti alkalmazások és a Vállalati Microsoft Áruházbeli alkalmazások. A windowsos alkalmazások fájlnévkiterjesztései közé tartozik az **.msi**, az **.appx** és az **.appxbundle** is.  

> [!Note]
> A modern alkalmazások telepítéséhez minimálisan szükséges Windows 10-frissítések a következők:
> - A Windows 10 1803-as verziójához: [2018. május 23. – KB4100403 (operációs rendszer: 17134.81-es build)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - A Windows 10 1709-es verziójához: [2018. június 21. – KB4284822 (operációs rendszer: 16299.522-es build)](https://support.microsoft.com/help/4284822).

## <a name="windows-10-line-of-business-apps"></a>Windows 10-es üzletági alkalmazások

A Windows 10-es üzletági alkalmazások alá vannak írva és fel vannak töltve az Intune felügyeleti konzoljára. Lehetnek olyan modern alkalmazások, mint az Univerzális Windows-platform (UWP) alkalmazások és a Windows-alkalmazáscsomagok (AppX), de Win 32-alkalmazások is, amilyenek az egyszerű Microsoft Installer telepítőcsomag-fájlok (MSI). Az üzletági alkalmazások frissítéseit minden alkalommal a rendszergazdának kell feltöltenie és üzembe helyeznie. Az üzembe helyezett frissítések felhasználói beavatkozás nélkül, automatikusan telepítve lesznek azoknak a végfelhasználóknak az eszközein, akik telepítették az alkalmazást. A felhasználó nem avatkozhat be a frissítésekbe. 

## <a name="microsoft-store-for-business-apps"></a>Vállalati Microsoft Áruházbeli alkalmazások

A Vállalati Microsoft Áruház felügyeleti portálján megvásárolt modern Vállalati Microsoft Áruházbeli alkalmazások a felügyelethez a Microsoft Intune-ra lesznek szinkronizálva. Az alkalmazások lehetnek **online licencelésűek** vagy **offline licencelésűek**. A Vállalati Microsoft Áruházbeli alkalmazások frissítéseit közvetlenül a Microsoft Áruház felügyeli, és nem kívánnak további rendszergazdai beavatkozást. A rendszergazda meg is akadályozhatja bizonyos alkalmazások frissítését egyéni egységes erőforrás-azonosító (Uniform Resource Identifier, URI) használatával. További információ: [Vállalati alkalmazásfelügyelet – Alkalmazás automatikus frissítésének megakadályozása](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Az eszközön a végfelhasználó is letilthatja az eszközön lévő összes Vállalati Microsoft Áruházbeli alkalmazás frissítéseit. 

## <a name="installing-apps-on-windows-10-devices"></a>Alkalmazások telepítése Windows 10-es eszközökön
Az alkalmazás típusától függően az alkalmazás két módszer egyikével telepíthető Windows 10-es eszközre:

- **Felhasználói környezet**: Ha az alkalmazás felhasználói környezetben van üzembe helyezve, a felügyelt alkalmazás akkor lesz telepítve a felhasználó számára az eszközön, amikor a felhasználó bejelentkezik az eszközre. Lényeges, hogy az alkalmazás telepítése csak akkor lesz sikeres, ha a felhasználó bejelentkezik az eszközre. 
    - A modern üzletági és Microsoft Áruházbeli alkalmazások (online vagy offline) telepíthetők felhasználói környezetben, és az Elérhető és Szükséges hozzárendelés-típust is támogatják.
    - A **felhasználói módban** vagy **kettős módban** készült Win32-alkalmazások felhasználói környezetben helyezhetők üzembe, és egyaránt támogatják a **Kötelező** és az **Elérhető** szándékmegjelölésű telepítést. 
- **Eszközkörnyezet**: Ha az alkalmazás eszközkörnyezetben van üzembe helyezve, akkor a felügyelt alkalmazást az Intune telepíti közvetlenül az eszközre.
    - Csak a modern üzleti alkalmazások és az üzleti alkalmazások offline licenccel rendelkező Microsoft Store eszköz környezetben is telepíthető, és csak a kötelező szándékot támogatni fogja.
    - A **Számítógép módban** vagy **kettős módban** készült Win32-alkalmazások felhasználói környezetben helyezhetők üzembe, és csak a **Kötelező** szándékmegjelölésű telepítést támogatják.

> [!NOTE]
> A **kettős módban** készült Win32-alkalmazások esetén Önnek (a rendszergazdának) kell kiválasztania, hogy az alkalmazás **felhasználói módban** vagy **Számítógép módban** fog-e működni az adott példányhoz kapcsolódó összes hozzárendelés esetében. Az üzembe helyezési környezet hozzárendelésenként változtatható.  

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

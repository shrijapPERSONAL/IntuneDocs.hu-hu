---
title: "Az iOS-mobilalkalmazások konfigurációs szabályzatainak használata | Microsoft Intune"
description: "Az Intune mobilalkalmazás-konfigurációs szabályzataival automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók iOS-alkalmazásokat futtatnak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 360865bcd97230e264ee3439407e8dd3017d0055
ms.openlocfilehash: 1f239270c26a70b161e52c24e94ca5c2cae9ca3a


---

# iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban
A Microsoft Intune mobilalkalmazás-konfigurációs szabályzataival automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók iOS-alkalmazásokat futtatnak. Egy alkalmazás kérheti a felhasználótól például a következők megadását:

-   Egyéni portszám.

-   Nyelvi beállítások.

-   Biztonsági beállítások.

-   Márkajelzési beállítások, például a vállalat logója.

Ha ezeket a beállításokat a felhasználó helytelenül adja meg, az növelheti az segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

A mobilalkalmazás-konfigurációs házirendek segítséget nyújthatnak ezeknek a problémáknak a megoldásában azáltal, hogy lehetővé teszik ezeknek a beállításoknak a telepítését a felhasználók számára a házirendben még az alkalmazás futtatása előtt. A beállítások megadása ezek után automatikusan történik, és nincs szükség felhasználói beavatkozásra.

Nem kell telepítenie ezeket a házirendeket közvetlenül a felhasználók és eszközök számára. Ehelyett a szabályzatot társítani kell egy alkalmazáshoz, majd telepíteni kell az alkalmazást. A házirend-beállítások akkor lesznek felhasználva, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

> [!TIP]
> Ez a szabályzattípus jelenleg csak az iOS 8.0-ás vagy újabb verzióit futtató eszközökön érhető el. A szabályzat az alábbi alkalmazástelepítési módszereket támogatja:
>
> -   **Felügyelt iOS-alkalmazás az App Store-ból**
> -   **Alkalmazáscsomag az iOS számára**
>
> Az alkalmazástelepítés-típusokról bővebben a következő témakörben olvashat: [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps.md).

## Mobilalkalmazás-konfigurációs házirend konfigurálása

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** &gt; **Áttekintés** &gt; **Házirend hozzáadása** elemet.

2.  A szabályzatok listájában bontsa ki az **iOS** csomópontot, válassza a **Mobilalkalmazás konfigurálása** lehetőséget, majd a **Házirend létrehozása** elemet.

    > [!TIP]
    > Ehhez a szabályzattípushoz csak egyéni beállításokat lehet megadni. Ajánlott beállítások nem állnak rendelkezésre.

3.  A **Házirend létrehozása** lap **Általános** részében adja meg a mobilalkalmazás-konfigurációs szabályzat nevét és, ha szeretné, a leírását.

4.  Az oldal **Mobilalkalmazás-konfigurációs házirend** részében írja vagy illessze be a mezőbe a kívánt alkalmazáskonfigurációs beállításokat tartalmazó XML-tulajdonságlistát. Az XML-tulajdonságlista formátuma a konfigurálni kívánt alkalmazás függvényében eltérő. A használandó formátummal kapcsolatban forduljon az alkalmazás szállítójához.

    > [!TIP]
    > Az XML-tulajdonságlistákkal kapcsolatos további információért tekintse meg az iOS Developer Library [Understanding XML Property Lists ](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Az XML-tulajdonságlisták ismertetése) című témakörét.

5.  A megadott XML-tulajdonságlista formátumának érvényességét az **Ellenőrzés** lehetőségre kattintva ellenőrizheti.

    > [!IMPORTANT]
    > Amikor az **Ellenőrzés**lehetőségre kattint, az Intune ellenőrzi, hogy érvényes-e a megadott XML formátuma. Azt azonban nem ellenőrzi, hogy az XML-tulajdonságlista működni fog-e az alkalmazással, amelyhez társítva van.

6.  Amikor elkészült, kattintson a **Házirend mentése**gombra.

Az új szabályzat megjelenik a **Konfigurációs szabályzatok** csomópontban.

## Információ az XML-fájlformátummal kapcsolatban

Az Intune a következő adattípusokat támogatja a tulajdonságlistákban:
    
- &lt;integer&gt;
- &lt;real&gt;
- &lt;karakterlánc&gt;
- &lt;tömb&gt;
- &lt;dict&gt;
- &lt;true /&gt; vagy &lt;false /&gt;
     
Az adattípusokkal kapcsolatban további információt az iOS Developer Library [About Property List](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) (Tulajdonságlisták) című témakörében talál.

Ezenkívül az Intune a következő tokentípusokat támogatja a tulajdonságlistában:
- \{\{userprincipalname\}\} – (Példa: **John@contoso.com**)
- \{\{mail\}\} – (Példa: **John@contoso.com**)
- \{\{partialupn\}\} – (Példa: **John**)
- \{\{accountid\}\} – (Példa: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Példa: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Példa: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Példa: **John Doe**)
- \{\{serialnumber\}\} – (Példa: **F4KN99ZUG5V2**) iOS eszközök esetében
- \{\{serialnumberlast4digits\}\} – (Példa: **G5V2**) iOS-eszközök esetében
    
A \{\{ és \}\} karaktereket csak a tokentípusok használják, ezek más célokra nem használhatók.

## Mobilalkalmazás-konfigurációs házirend társítása egy alkalmazáshoz
A mobilalkalmazás-konfigurációs házirendet a létrehozást követően társítani kell ahhoz az iOS-alkalmazáshoz, amelyre a konfigurációs házirend beállításait alkalmazni kívánja.

Ehhez kövesse az alkalmazástelepítés létrehozásának lépéseit, amelyeket a következő témakörök ismertetnek: [Alkalmazások hozzáadása Microsoft Intune-beli mobileszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md), illetve [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md). Amikor eléri a varázsló **Mobilalkalmazás konfigurálása** lapját, az **Alkalmazáskonfigurálási szabályzat** legördülő listából válassza ki az alkalmazáshoz társítani kívánt szabályzatot.

Ezután a megszokott módon haladjon tovább az alkalmazás telepítésével és a telepítés nyomon követésével.

Amikor a telepített alkalmazást futtatják egy eszközön, akkor az a mobilalkalmazás-konfigurációs szabályzatban megadott beállításokkal fog futni.

> [!TIP]
> Ha egy vagy több mobilalkalmazás-konfigurációs szabályzat ütközik egymással, egyik sem lesz alkalmazva, az ütközésről pedig jelentés készül az Intune felügyeleti konzoljának **irányítópultján**.

## Mobilalkalmazás-konfigurációs XML-fájl példaformátuma

Mobilalkalmazás-konfigurációs fájl létrehozásakor a következő értékek közül egyet vagy többet adhat meg ebben a formátumban:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```



<!--HONumber=Sep16_HO3-->



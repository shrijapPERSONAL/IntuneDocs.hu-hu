---
title: "A Microsoft Intune alkalmazáskonfigurációs szabályzatainak használata | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: ez a témakör azt ismerteti, hogyan lehet alkalmazáskonfigurációs szabályzatokkal konfigurációs adatokat szolgáltatni a futtatott iOS-alkalmazásoknak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 847ddf08fdd7308475895af36f43c5391c9556fa
ms.contentlocale: hu-hu
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-use-microsoft-intune-app-configuration-policies"></a>A Microsoft Intune alkalmazáskonfigurációs szabályzatainak használata

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune alkalmazáskonfigurációs szabályzataival automatikusan megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor a felhasználók alkalmazásokat futtatnak. Az alkalmazás kérheti például a felhasználótól a következők megadását:

-   Egyéni portszám.

-   Nyelvi beállítások.

-   Biztonsági beállítások.

-   Márkajelzési beállítások, például a vállalat logója.

Ha ezeket a beállításokat a felhasználó helytelenül adja meg, az növelheti az segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

Az alkalmazáskonfigurációs szabályzatok segítséget nyújthatnak e problémák megoldásában, mivel még az alkalmazás futtatása előtt hozzá tudják rendelni a beállításokat a szabályzat által érintett felhasználókhoz. A beállítások megadása ezek után automatikusan történik, és nincs szükség felhasználói beavatkozásra.

A házirendeket nem kell közvetlenül felhasználókhoz vagy eszközökhöz rendelni. Ehelyett a szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A házirend-beállítások akkor lesznek felhasználva, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

> [!TIP]
> Ez a szabályzattípus jelenleg csak az iOS 8.0-ás vagy újabb verzióit futtató eszközökön érhető el. A szabályzat az alábbi alkalmazástelepítési módszereket támogatja:
>
> -   **Felügyelt iOS-alkalmazás az App Store-ból**
> -   **Alkalmazáscsomag az iOS számára**
>
> Az alkalmazástelepítés-típusokról bővebben a következő témakörben olvashat: [Alkalmazás felvétele a Microsoft Intune-ba](add-apps.md).

## <a name="create-an-app-configuration-policy"></a>Alkalmazáskonfigurációs szabályzat konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1.  A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazáskonfigurációs szabályzatok** lehetőséget.

2.  A szabályzatok panelének listájából válassza a **Hozzáadás** elemet.

3.  A **Konfigurációs szabályzat hozzáadása** panelen adja meg a szabályzat nevét és leírását (ez utóbbi nem kötelező).
4.  Válassza a **Társított alkalmazás** elemet, majd a **Társított alkalmazás** panelen jelölje ki azt a felügyelt alkalmazást, amelyre a konfigurációt alkalmazni szeretné.
5.  A **Konfigurációs szabályzat hozzáadása** panelen válassza a **Konfigurációs beállítások** lehetőséget, majd a Konfigurációs beállítások panelen válassza ki, hogyan szeretné megadni a profilt alkotó XML-értékeket:
    - **XML-adatok megadása** – ezzel a lehetőséggel beírhat vagy beilleszthet egy XML-tulajdonságlistát, amelyben a kívánt alkalmazáskonfigurációs beállítások szerepelnek. Az XML-tulajdonságlista formátuma a konfigurálni kívánt alkalmazás függvényében eltérő. A használandó formátummal kapcsolatban forduljon az alkalmazás szállítójához.
    Az Intune ellenőrzi a megadott XML formátumának helyességét, azt azonban nem, hogy az XML-tulajdonságlista működni fog-e az alkalmazással, amelyhez társítva van.
    Az XML-tulajdonságlistákkal kapcsolatos további információért tekintse meg az iOS Developer Library [Understanding XML Property Lists ](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Az XML-tulajdonságlisták ismertetése) című témakörét.
    - **Konfigurációtervező használata** – ezzel a lehetőséggel közvetlenül a portálon adhat meg XML-kulcs–érték párokat.
8. Ha elkészült, lépjen vissza a **Konfigurációs szabályzat hozzáadása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a szabályzat, és megjelenik a szabályzatok listáját tartalmazó panelen.

Ezt követően a szokott módon [oszthatja ki](deploy-apps.md) és [monitorozhatja](monitor-apps.md) az alkalmazást.

Amikor a kiosztott alkalmazást futtatják egy eszközön, az alkalmazáskonfigurációs szabályzatban megadott beállításokkal fog futni.

> [!TIP]
> Ha az alkalmazáskonfigurációs szabályzatok ütköznek egymással, egyik sem lép életbe.

## <a name="information-about-the-xml-file-format"></a>Információ az XML-fájlformátummal kapcsolatban

Az Intune a következő adattípusokat támogatja a tulajdonságlistákban:

- &lt;integer&gt; (egész szám)
- &lt;real&gt; (valós szám)
- &lt;string&gt; (karakterlánc)
- &lt;array&gt; (tömb)
- &lt;dict&gt; (szótár)
- &lt;true /&gt; (igaz) vagy &lt;false /&gt; (hamis)

Az adattípusokkal kapcsolatban további információt az iOS Developer Library [About Property List](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) (Tulajdonságlisták) című témakörében talál.

Ezenkívül az Intune a következő tokentípusokat támogatja a tulajdonságlistában:
- \{\{userprincipalname\}\} – (példa: **John@contoso.com**)
- \{\{mail\}\} – (példa: **John@contoso.com**)
- \{\{partialupn\}\} – (Példa: **János**)
- \{\{accountid\}\} – (Példa: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Példa: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Példa: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Példa: **Kovács János**)
- \{\{serialnumber\}\} – (Példa: **F4KN99ZUG5V2**) iOS-eszközök esetében
- \{\{serialnumberlast4digits\}\} – (Példa: **G5V2**) iOS-eszközök esetében

A \{\{ és \}\} karaktereket csak a tokentípusok használják, ezek más célokra nem használhatók.





## <a name="example-format-for-an-app-configuration-xml-file"></a>Alkalmazáskonfigurációs XML-fájl példaformátuma

Alkalmazáskonfigurációs fájl létrehozásakor a következő értékeket adhatja meg ebben a formátumban:

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


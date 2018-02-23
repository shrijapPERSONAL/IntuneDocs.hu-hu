---
title: "Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt iOS-eszközökhöz | Microsoft Docs"
titlesuffix: Azure portal
description: "Ez a témakör azt ismerteti, hogyan lehet alkalmazáskonfigurációs szabályzatokkal konfigurációs adatokat szolgáltatni a futó iOS-alkalmazásoknak."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b64d8b60a4c577acc2f6ef161f6de37ac529e7ac
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt iOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazáskonfigurációs szabályzataival beállításokat adhat meg a felhasználók által futtatott iOS-alkalmazásokhoz. A házirendeket nem kell közvetlenül felhasználókhoz vagy eszközökhöz rendelni. Ehelyett a szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A szabályzatbeállítások akkor használatosak, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

Alkalmazáskonfigurálási szabályzatot rendelhet a felhasználók és eszközök egy csoportjához belefoglalási és kizárási hozzárendelések kombinációjával. Miután hozzáadta az alkalmazáskonfigurálási szabályzatot, beállíthatja az alkalmazáskonfigurálási szabályzat hozzárendeléseit. A szabályzat hozzárendeléseinek beállításakor felvehet vagy kizárhat a szabályzat hatálya alá eső felhasználói csoportokat. Amikor felvesz egy vagy több csoportot, kiválaszthat bizonyos csoportokat, vagy választhat beépített csoportokat. Beépített csoportok a következők: **Minden felhasználó**, **Minden eszköz**, és **Minden felhasználó és minden eszköz**. 

>[!NOTE]
>Az Intune biztosítja az előre létrehozott **Minden felhasználó** és **Minden eszköz** csoportok beépített optimalizálását a felhasználók kényelme érdekében a konzolon. Mindenképpen ajánlott ezeket a csoportokat használni az összes felhasználó és az összes eszköz megcélzására az Ön által létrehozott „Minden felhasználó” vagy „Minden eszköz” csoport helyett.

Miután kiválasztotta a belefoglalt csoportokat az alkalmazáskonfigurálási szabályzathoz, kiválaszthatja az adott kizárni kívánt csoportokat is.

> [!TIP]
> Ez a szabályzattípus jelenleg csak az iOS 8.0-ás vagy újabb verzióit futtató eszközökön érhető el. A szabályzat az alábbi alkalmazástelepítési módszereket támogatja:
>
> -   **Felügyelt iOS-alkalmazás az App Store-ból**
> -   **Alkalmazáscsomag az iOS számára**
>
> Az alkalmazástelepítés-típusokról bővebben a következő témakörben olvashat: [Alkalmazás felvétele a Microsoft Intune-ba](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Alkalmazáskonfigurációs szabályzat konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. Válassza a **Mobilalkalmazások** panelt.
4. Válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget a **Felügyelet** csoportban, majd a **Hozzáadás** lehetőséget.
5. Adja meg a következő adatokat:
    - **Név**<br>
      Az Azure Portalon megjelenő profilnév.
    - **Leírás**<br>
      Az Azure Portalon megjelenő profilleírás.
    - **Eszközbeléptetés típusa**<br>
      Válasza a **Felügyelt eszközök** lehetőséget.
6. A **Platform** beállításban válassza az **iOS** lehetőséget.
7.  Válassza a **Társított alkalmazás** lehetőséget. A **Társított alkalmazás** panelen jelölje ki azt a felügyelt alkalmazást, amelyre a konfigurációt alkalmazni szeretné.
8.  A **Konfigurációs szabályzat hozzáadása** panelen válassza a **Konfigurációs beállítások** lehetőséget.
9. Válassza a **Konfigurációs beállítások formátuma** lehetőséget. Válasszon az alábbi lehetőségek közül:
    - **[Konfigurációtervező használata](#use-configuration-designer)**
    - **[XML-adatok megadása](#enter-xml-data)**
10. XML-adatainak hozzáadását követően használja az **OK**, majd a **Hozzáadás** gombot a konfigurációs szabályzat hozzáadásához. Ekkor megjelenik a konfigurációs szabályzat áttekintő panelje.
11. Válassza a **Hozzárendelések** lehetőséget a belefoglalási és kizárási beállítások megjelenítéséhez. 

    ![Szabályzat-hozzárendelések](./media/app-config-policy01.png)
12. Válassza a **Minden felhasználó** lehetőséget a **Belefoglalás** lapon.

    ![Szabályzat-hozzárendelések – Minden felhasználó](./media/app-config-policy02.png)
13. Válassza a **Kizárás** lapot. 
14. Kattintson a **Válassza ki a kizárandó csoportokat** lehetőségre a kapcsolódó panel megjelenítéséhez.

    ![Szabályzat-hozzárendelések – Válassza ki a kizárandó csoportokat](./media/app-config-policy03.png)
15. Válassza ki azokat a csoportokat, amelyeket ki szeretne zárni, majd kattintson a **Kijelölés** lehetőségre.

    >[!NOTE]
    >Csoportok hozzáadásakor, ha bármely más csoport már bele lett foglalva egy adott hozzárendelés-típus esetében, az előre ki lesz jelölve és nem módosítható más belefoglalási hozzárendelés-típusok esetében. Ezért az adott csoport használatba lett véve, és így nem használható kizárt csoportként.
16. Kattintson a **Mentés**gombra.

## <a name="use-configuration-designer"></a>A configuration designer használata

A konfigurációtervezőt olyan eszközökön található alkalmazásokhoz használhatja, amelyek regisztrálva vannak vagy nincsenek regisztrálva az Intune-ban. A tervezővel konkrét konfigurációs kulcsokat és értékeket konfigurálhat. Az értékekhez az adattípust is meg kell adnia. A beállítások megadása ezen alkalmazások számára azok telepítésekor automatikusan történik.

### <a name="add-a-setting"></a>Beállítás hozzáadása

1. A konfiguráció minden kulcsához és értékéhez állítsa be az alábbiakat:
   - **Konfigurációs kulcs**<br>
     Az adott beállításkonfigurációhoz egyedi azonosítóként szolgáló kulcs.
   - **Érték típusa**<br>
     A konfigurációs érték adattípusa. A típus az alábbiak egyike: egész szám, valós szám, karakterlánc vagy logikai.
   - **Konfigurációs érték**<br>
     A konfiguráció értéke.
2. A konfigurációs beállítások megadásához válassza az **OK** gombot.

### <a name="delete-a-setting"></a>Beállítás törlése

1. Válassza a beállítás melletti három pontot (**...**).
2. Válassza a **Törlés** elemet.

A \{\{ és \}\} karaktereket csak a tokentípusok használják, ezek más célokra nem használhatók.

## <a name="enter-xml-data"></a>XML-adatok megadása

Beírhat vagy beilleszthet egy XML-tulajdonságlistát, amelyben a kívánt alkalmazáskonfigurációs beállítások szerepelnek (Intune-ban regisztrált eszközök esetén adható meg). Az XML-tulajdonságlista formátuma a konfigurálni kívánt alkalmazás függvényében eltérő. A használandó formátummal kapcsolatban forduljon az alkalmazás szállítójához.

Az Intune ellenőrzi az XML-formátumot, azt azonban nem, hogy az XML-tulajdonságlista (PList) működni fog-e a célalkalmazással.

További információ az XML-tulajdonságlistákról:

  -  [iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Tekintse meg az [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Az XML-tulajdonságlisták ismertetése) című témakört az iOS Developer Libraryben.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Alkalmazáskonfigurációs XML-fájl példaformátuma

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
### <a name="supported-xml-plist-data-types"></a>Támogatott XML PList-adattípusok

Az Intune a következő adattípusokat támogatja a tulajdonságlistákban:

- &lt;integer&gt; (egész szám)
- &lt;real&gt; (valós szám)
- &lt;string&gt; (karakterlánc)
- &lt;array&gt; (tömb)
- &lt;dict&gt; (szótár)
- &lt;true /&gt; (igaz) vagy &lt;false /&gt; (hamis)

### <a name="tokens-used-in-the-property-list"></a>A tulajdonságlistában használt tokenek

Ezenkívül az Intune a következő tokentípusokat támogatja a tulajdonságlistában:
- \{\{userprincipalname\}\} — például **John@contoso.com**
- \{\{mail\}\} — például **John@contoso.com**
- \{\{partialupn\}\} — például **János**
- \{\{accountid\}\} — például **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\} — például **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\} — például **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} — például **Szabó János**
- \{\{serialnumber\}\} — például **F4KN99ZUG5V2** (iOS-eszközök esetén)
- \{\{serialnumberlast4digits\}\} — például **G5V2** (iOS-eszközök esetén)

## <a name="next-steps"></a>További lépések

Ezt követően a szokott módon gondoskodhat az alkalmazás valamely csoporthoz történő [hozzárendeléséről](apps-deploy.md) és [figyeléséről](apps-monitor.md).
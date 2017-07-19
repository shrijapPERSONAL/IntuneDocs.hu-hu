---
title: "Az Intune iOS rendszerhez készült alkalmazáskonfigurációs szabályzatainak használata"
titleSuffix: Intune on Azure
description: "Ez a témakör azt ismerteti, hogyan lehet alkalmazáskonfigurációs szabályzatokkal konfigurációs adatokat szolgáltatni a futtatott iOS-alkalmazásoknak.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>A Microsoft Intune iOS rendszerhez készült alkalmazáskonfigurációs szabályzatainak használata

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazáskonfigurációs szabályzataival automatikusan megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor a felhasználók iOS-alkalmazásokat futtatnak. Egy alkalmazás kérheti a felhasználótól például a következők megadását:

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
> Az alkalmazástelepítés-típusokról bővebben a következő témakörben olvashat: [Alkalmazás felvétele a Microsoft Intune-ba](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Alkalmazáskonfigurációs szabályzat konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
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

Ezt követően a szokott módon [oszthatja ki](apps-deploy.md) és [monitorozhatja](apps-monitor.md) az alkalmazást.

Amikor a kiosztott alkalmazást futtatják egy eszközön, az alkalmazáskonfigurációs szabályzatban megadott beállításokkal fog futni.

> [!TIP]
> Ha az alkalmazáskonfigurációs szabályzatok ütköznek egymással, egyik sem lép életbe.

## <a name="create-a-mam-targeted-configuration-policy"></a>Célzott MAM-konfigurációs szabályzat létrehozása
A célzott MAM-konfiguráció lehetővé teszi, hogy az alkalmazások konfigurációs adatokat fogadjanak az Intune App SDK-ból. Ezeknek az adatoknak a formátumát és változatait az alkalmazás tulajdonosának/fejlesztőjének kell meghatároznia és kommunikálnia az Intune-ügyfelek felé. Az Intune-rendszergazdák az Intune Azure-konzolról célozhatják és telepíthetik a konfigurációs adatokat. A célzott MAM-konfigurációs adatok az MAM szolgáltatásával biztosíthatók az MAM-WE-vel való együttműködésre képes alkalmazások számára. Az [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) például rendelkezik engedélyezett/letiltott URL-ek listájával. Az alkalmazáskonfigurációs adatokat az MDM-csatorna helyett az MAM szolgáltatásán keresztül közvetlenül az alkalmazásba küldi a rendszer. A [Mobileszköz-kezelési alkalmazás-konfigurációs házirendek](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) az MDM-en keresztül elérhető natív megoldást jelentik. A célzott MAM-konfigurációnál a fő különbség az, hogy az eszköz, amelyen az alkalmazás fut, nem szükséges, hogy az MDM által regisztrált legyen. A célzott MAM-konfiguráció iOS és Android rendszeren érhető el. Az iOS-hez az alkalmazásnak magában kell foglalnia az Intune App SDK iOS rendszerhez 7.0.1 verzióját, és részt kell vennie az alkalmazáskonfigurációs beállításokban. A célzott MAM-konfigurációs szabályzat létrehozásának lépései a következők: 

1. Jelentkezzen be az **Azure Portal** webhelyre.

2. Válassza az **Intune > Mobilalkalmazások - Alkalmazáskonfigurációs szabályzatok** lehetőséget.

3. Az **Alkalmazáskonfiguráció** panelen válassza a **Hozzáadás** lehetőséget.

4. Az alkalmazáskonfigurációs beállításokhoz írja be a **Nevet** és a **Leírást** (ez utóbbi nem kötelező), majd válassza az **Intune-ban nem regisztrált** lehetőséget.

5. Válassza a **Kötelező alkalmazások kiválasztása** lehetőséget, majd a **Célzott** az alkalmazások panelen válassza ki az alkalmazásokat a kívánt platformokhoz. <br>
**Megjegyzés:** Üzleti alkalmazások esetén válassza a **További alkalmazások** elemet. Adja meg az alkalmazás csomagazonosítóját.

6. Az **OK** kiválasztásával visszatérhet az **Alkalmazáskonfiguráció hozzáadása** panelre.

7. Válassza a **Konfiguráció definiálása** lehetőséget. A **Konfigurálás** panelen kulcs-érték párok definiálásával adhatja meg a konfigurációkat.

8. Ha elkészült, válassza az **OK** elemet.

9. Az **Alkalmazáskonfiguráció hozzáadása** panelen válassza a **Létrehozás** elemet.

Ezzel létrejön az új konfiguráció, és megjelenik az Alkalmazáskonfiguráció panelen.

Ezt követően a szokott módon [oszthatja ki](apps-deploy.md) és [monitorozhatja](apps-monitor.md) az alkalmazást.

Amikor a kiosztott alkalmazást (amelyik integrálva van az Intune App SDK-va) futtatják egy eszközön, a célzott MAM-konfigurációs szabályzatban megadott beállításokkal fog futni. A hozzárendelt alkalmazás integrálva kell, hogy legyen az Intune APP SDK támogatott verziójával. A célzott MAM-konfigurációs szabályzatok használatának alkalmazásfejlesztési követelményeivel kapcsolatos további információkért lásd [Az iOS rendszerű Intune APP SDK integrációs útmutatóját](https://docs.microsoft.com/intune/app-sdk-ios).

A Graph API a célzott MAM-konfigurációs értékekre vonatkozó képességeivel kapcsolatos további információk: [Graph API-referencia – célzott MAM-konfiguráció](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

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

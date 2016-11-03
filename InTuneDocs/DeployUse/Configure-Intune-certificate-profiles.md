---
title: "Tanúsítványprofilok konfigurálása | Microsoft Intune"
description: "Tudnivalók az Intune-tanúsítványprofilok létrehozásáról."
keywords: 
author: nbigman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: c51c5ae199ca2950dc0371b400727af534a70f09


---

# Intune-tanúsítványprofilok konfigurálása
Miután a [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md) vagy a [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md) részben leírtaknak megfelelően konfigurálta az infrastruktúrát és a tanúsítványokat, hozzáfoghat a tanúsítványprofilok létrehozásához. Ennek folyamata a következő:

- **1. feladat**: Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása
- **2. feladat**: Megbízható tanúsítványprofilok létrehozása
- **3. feladat**: A két tanúsítványtípus egyikének létrehozása:
  - SCEP-tanúsítványprofilok
  - .PFX-tanúsítványprofilok

## **1. feladat**: Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása
Exportálja a megbízható legfelső szintű hitelesítésszolgáltató (CA) tanúsítványát **.cer** kiterjesztésű fájlként a kibocsátó hitelesítésszolgáltatóról vagy a vállalati hitelesítésszolgáltatóban megbízó bármelyik eszközről. A titkos kulcsot ne exportálja.

Ezt a tanúsítványt a megbízható tanúsítványprofil konfigurálásakor kell importálnia.

## **2. feladat**: Megbízható tanúsítványprofilok létrehozása
Létre kell hoznia egy Megbízható hitelesítésszolgáltatói tanúsítványprofilt, mielőtt Egyszerű tanúsítványigénylési protokoll (SCEP) vagy PKCS #12 (.PFX) szerinti tanúsítványprofilt hozna létre. Minden mobileszközplatformhoz külön megbízható tanúsítványprofillal és SCEP- vagy .PFX-profillal kell rendelkeznie.

### Megbízható tanúsítványprofil létrehozása

1.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet.
2.  Adja hozzá a következő házirend-típusok valamelyikét:
    - **Android &gt; Megbízható tanúsítványprofil (Android 4 és újabb)**
    - **iOS &gt; Megbízható tanúsítványprofil (iOS 8.0 és újabb)**
    - **Mac OS X &gt; Megbízható tanúsítványprofil (Mac OS X 10.9 és újabb)**
    - **Windows &gt; Megbízható tanúsítványprofil (Windows 8.1 és újabb)**
    - **Windows &gt; Megbízható tanúsítványprofil (Windows Phone 8.1 és újabb)**

    További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Konfigurálja a megbízható tanúsítványprofil beállításait Android, iOS, Mac OS X, Windows 8.1 vagy Windows Phone 8.1 rendszerhez a rendszer által kért információk megadásával. 
4.  A **Tanúsítványfájl** beállításnál importálja a kiállító hitelesítésszolgáltatótól exportált megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt (.cer fájl). A **Céltár** beállítás kizárólag olyan Windows 8.1-es vagy újabb rendszerrel futó eszközökre vonatkozik, amelyeken egynél több tanúsítványtár érhető el.
    
4.  Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

## **3. feladat**: SCEP- vagy .PFX-tanúsítványprofilok létrehozása
Miután létrehozott egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, létre kell hoznia a használni kívánt platformok SCEP- vagy .PFX-tanúsítványprofilját is. Egy SCEP-tanúsítványprofil létrehozásakor meg kell adnia egy ugyanarra a platformra vonatkozó megbízható tanúsítványprofilt. Ez a művelet összeköti a két tanúsítványprofilt, de az egyes profilok központi telepítését külön-külön kell elvégeznie.

### SCEP-tanúsítványprofil létrehozása

1.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet.
2.  Adja hozzá a következő házirend-típusok valamelyikét:
    - **Android &gt; SCEP-tanúsítványprofil (Android 4 és újabb)**
    - **iOS &gt; SCEP-tanúsítványprofil (iOS 8.0 és újabb)**
    - **Mac OS X &gt; SCEP-tanúsítványprofil (Mac OS X 10.9 és újabb)**
    - **Windows &gt; SCEP-tanúsítványprofil (Windows 8.1 és újabb)**
    - **Windows &gt; SCEP-tanúsítványprofil (Windows Phone 8.1 és újabb)**

    További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  A profilkonfigurációs oldalon szereplő utasításokat követve végezze el az SCEP-tanúsítványprofil beállítását.
    > [!NOTE]
    >
    > Egyéni tulajdonosnév megadásához a **Tulajdonos nevének formátuma** legördülő listából válassza az **Egyéni** lehetőséget (csak iOS-profilok esetén érhető el).
    >
    > Az egyéni formátum jelenleg két változót támogat: `Common Name (CN)` és `Email (E)`. A változók és a statikus karakterláncok együttes használatával a következőhöz hasonló egyéni tulajdonosnév-formátumot hozhat létre:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > A példában a rendszergazda egy olyan tulajdonosnév-formátumot hozott létre, amely a `CN` és az `E` változó mellett a Szervezeti Egység, a Szervezet, a Hely, az Állam és az Ország értékek karakterláncait is alkalmazza. A [CertStrToName függvény](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) sorolja fel a támogatott karakterláncokat.

4.  Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

### .PFX-tanúsítványprofil létrehozásához

1.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet.
2.  Adja hozzá a következő házirend-típusok valamelyikét:
  - **Android &gt; .PFX-tanúsítványprofil (Android 4 és újabb verziók)**
  - **Windows &gt; PKCS #12 (.PFX) tanúsítványprofil (Windows 10 és újabb verziók)**
  - **Windows &gt; PKCS #12 (.PFX) tanúsítványprofil (Windows Phone 10 és újabb verziók)**
  - **iOS > PKCS #12 (.PFX) tanúsítványprofil (iOS 8.0 és újabb)**    
    További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Adja meg a házirendűrlapon kért adatokat.
4.  Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

## Tanúsítványprofilok központi telepítése
A tanúsítványprofilok központi telepítésekor a megbízható hitelesítésszolgáltatói tanúsítványprofilból származó tanúsítványprofil települ az eszközön. Az eszköz az SCEP- vagy a .PFX-tanúsítványprofilt használja tanúsítványkérelem létrehozására.

A tanúsítványprofilok csak a profil létrehozásakor használt platformot futtató eszközökön települnek.

-   Tanúsítványprofilokat telepíthet felhasználógyűjteményekre és eszközgyűjteményekre is.

    > [!TIP]
    > Ahhoz, hogy a tanúsítványok gyorsan megjelenjenek az eszközökön azok regisztrálását követően, a tanúsítványprofilt felhasználócsoportra és ne eszközcsoportra telepítse. Ha eszközcsoportra telepít, akkor teljes eszközregisztráció szükséges, mielőtt az eszköz megkaphatná a házirendeket.

-   Jóllehet az egyes profilokat külön-külön telepíti, a legfelső szintű hitelesítésszolgáltató és az SCEP- vagy .PFX-profil telepítésére is szükség van. Ellenkező esetben az SCEP- vagy .PFX-tanúsítványházirend hibát fog jelezni.

A tanúsítványprofilok központi telepítése ugyanúgy zajlik, mint az Intune egyéb házirendjeinek telepítése:

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése** elemre.
2.  A **Telepítések kezelése** párbeszédpanelen:
    -   **A szabályzat telepítéséhez** válasszon ki egy vagy több olyan csoportot, amelyhez telepíteni szeretné a szabályzatot, majd válassza a **Hozzáadás**&gt;**OK** lehetőséget.
    -   **A párbeszédpanel telepítés nélkül történő bezárásához** kattintson a **Mégse** gombra.

Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat a telepítésről.

### További lépések

Ezt követően megtudhatja, hogy a tanúsítványok segítségével hogyan teheti biztonságossá az e-mail, Wi-Fi és VPN-profilokat.

-  [Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md)
-  [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->



---
title: Tanúsítványprofilok konfigurálása
description: Tudnivalók az Intune-tanúsítványprofilok létrehozásáról.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 51da197b9b805fbac22b6a46453617b7703a37e8
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="configure-intune-certificate-profiles"></a>Intune-tanúsítványprofilok konfigurálása

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Miután a [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md) vagy a [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md) részben leírtaknak megfelelően konfigurálta az infrastruktúrát és a tanúsítványokat, hozzáfoghat a tanúsítványprofilok létrehozásához. Ennek folyamata a következő:

- **1. feladat**: Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása
- **2. feladat**: Megbízható tanúsítványprofilok létrehozása
- **3. feladat**: A két tanúsítványtípus egyikének létrehozása:
  - SCEP-tanúsítványprofilok
  - .PFX-tanúsítványprofilok

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>**1. feladat**: Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása
Exportálja a megbízható legfelső szintű hitelesítésszolgáltató (CA) tanúsítványát **.cer** kiterjesztésű fájlként a kibocsátó hitelesítésszolgáltatóról vagy a vállalati hitelesítésszolgáltatóban megbízó bármelyik eszközről. A titkos kulcsot ne exportálja.

Ezt a tanúsítványt a megbízható tanúsítványprofil konfigurálásakor kell importálnia.

## <a name="task-2-create-trusted-certificate-profiles"></a>**2. feladat**: Megbízható tanúsítványprofilok létrehozása
Létre kell hoznia egy Megbízható hitelesítésszolgáltatói tanúsítványprofilt, mielőtt Egyszerű tanúsítványigénylési protokoll (SCEP) vagy PKCS #12 (.PFX) szerinti tanúsítványprofilt hozna létre. Minden mobileszközplatformhoz külön megbízható tanúsítványprofillal és SCEP- vagy .PFX-profillal kell rendelkeznie.

### <a name="to-create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

1.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet, majd válasszon ki egy eszközplatformot. Megbízható tanúsítványprofilt hozhat létre az alábbi eszközökhöz:

-  Android 4 és újabb verziók

-  Android for Work

-  iOS 7.1-es és újabb verziók

-  Mac OS X 10.9 és újabb verziók

-  Windows 8.1 és újabb

-  Windows Phone 8.1 és újabb verziók

2.  **Megbízható tanúsítványprofil**-házirend hozzáadása.

    További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Konfigurálja a megbízható tanúsítványprofil beállításait Android, iOS, Mac OS X, Windows 8.1 vagy Windows Phone 8.1 rendszerhez a rendszer által kért információk megadásával.
4.  A **Tanúsítványfájl** beállításnál importálja a kiállító hitelesítésszolgáltatótól exportált megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt (.cer fájl). A **Céltár** beállítás kizárólag olyan Windows 8.1-es vagy újabb rendszerrel futó eszközökre vonatkozik, amelyeken egynél több tanúsítványtár érhető el.

4.  Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

> [!NOTE]
>
> Az Android- és Android for Work-eszközök megjelenítenek egy üzenetet arról, hogy harmadik fél megbízható tanúsítványt telepített.


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a>**3. feladat**: SCEP- vagy .PFX-tanúsítványprofilok létrehozása
Miután létrehozott egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, létre kell hoznia a használni kívánt platformok SCEP- vagy .PFX-tanúsítványprofilját is. Egy SCEP-tanúsítványprofil létrehozásakor meg kell adnia egy ugyanarra a platformra vonatkozó megbízható tanúsítványprofilt. Ez a művelet összeköti a két tanúsítványprofilt, de az egyes profilok központi telepítését külön-külön kell elvégeznie.

### <a name="to-create-an-scep-certificate-profile"></a>SCEP-tanúsítványprofil létrehozása

1.  Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet, majd válasszon ki egy eszközplatformot.  SCEP-tanúsítványprofilt hozhat létre az alábbi eszközökhöz:

-  Android 4 és újabb verziók

-  Android for Work

-  iOS 7.1-es és újabb verziók

-  Mac OS X 10.9 és újabb verziók

-  Windows 8.1 és újabb

-  Windows Phone 8.1 és újabb verziók

2. **SCEP-tanúsítványprofil** házirend hozzáadása

   További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3. A profilkonfigurációs oldalon szereplő utasításokat követve végezze el az SCEP-tanúsítványprofil beállítását.
   > [!NOTE]
   > 
   > Egyéni tulajdonosnév megadásához a **Tulajdonos nevének formátuma** legördülő listából válassza az **Egyéni** lehetőséget (csak iOS-profilok esetén érhető el).
   > 
   > Az egyéni formátum jelenleg két változót támogat: `Common Name (CN)` és `Email (E)`. A változók és a statikus karakterláncok együttes használatával a következőhöz hasonló egyéni tulajdonosnév-formátumot hozhat létre:
   > 
   >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US
   > 
   > A példában a rendszergazda egy olyan tulajdonosnév-formátumot hozott létre, amely a `CN` és az `E` változó mellett a Szervezeti Egység, a Szervezet, a Hely, az Állam és az Ország értékek karakterláncait is alkalmazza. A [CertStrToName függvény](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) sorolja fel a támogatott karakterláncokat.

4. Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

### <a name="to-create-a-pfx-certificate-profile"></a>.PFX-tanúsítványprofil létrehozásához

1. Az [Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet, majd válasszon ki egy eszközplatformot. A .PFX-tanúsítványokat támogatják:
   - Android 4 és újabb verziók
   - Android for Work
   - Windows 10 és újabb
   - Windows Phone 10 és újabb verziók
   - iOS 8.0 és újabb verziók    


2. **.PFX-tanúsítványprofil** házirend hozzáadása.
     További információ: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3. Adja meg a házirendűrlapon kért adatokat.
4. Válassza a **Házirend mentése** elemet.

Az új házirend a **Házirend** munkaterületen jelenik meg. Ekkor telepítheti.

## <a name="deploy-certificate-profiles"></a>Tanúsítványprofilok központi telepítése
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

### <a name="next-steps"></a>További lépések

Ezt követően megtudhatja, hogy a tanúsítványok segítségével hogyan teheti biztonságossá az e-mail, Wi-Fi és VPN-profilokat.

-  [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md)
-  [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md)

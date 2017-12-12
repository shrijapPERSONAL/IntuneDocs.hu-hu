---
title: "Tanúsítványok konfigurálása az Intune-nal"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt olyan tanúsítványok Intune-beli létrehozásáról és hozzárendeléséről, amelyek segítenek a Wi-Fi-, VPN- és egyéb kapcsolatok védelmében."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9c74ee1daf6602a4958d9955c3955b465495e013
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Tanúsítványok konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Amikor a felhasználóknak engedélyezi a vállalati erőforrások VPN-, Wi-Fi- vagy e-mail-profilokon keresztüli elérését, ezeket a kapcsolatokat tanúsítványokkal hitelesítheti. Tanúsítványok használatakor nem kell megadnia a felhasználóneveket és a jelszavakat a kapcsolatok hitelesítéséhez.

Az Intune-nal hozzárendelheti ezeket a tanúsítványokat a felügyelt eszközökhöz. Az Intune a következő tanúsítványtípusok eszközökhöz rendelését és felügyeletét támogatja:

- SCEP protokoll
- PKCS#12 (vagy PFX)

Ezen tanúsítványtípusok mindegyikének megvannak a maga előfeltételei és infrastrukturális követelményei.

## <a name="general-workflow"></a>Általános munkafolyamat

1. Ha még nem működik a megfelelő tanúsítványinfrastruktúra, helyezze üzembe. [SCEP-tanúsítványokat](certificates-scep-configure.md) és [PKCS-tanúsítványokat](certficates-pfx-configure.md) használhat.
2. Telepítsen egy főtanúsítványt vagy köztes hitelesítésszolgáltatói tanúsítványt minden eszközön, hogy az eszköz felismerje a hitelesítésszolgáltató (CA) érvényességét. Ehhez hozzon létre és rendeljen hozzá egy **megbízható tanúsítványprofilt**. A profil hozzárendelésekor az Intune-nal felügyelt eszközök lekérik és megkapják a főtanúsítványt. Mindegyik platformhoz különálló profilt kell létrehoznia. A megbízható tanúsítványprofilok a következő platformokhoz érhetők el:
    - iOS 8.0 és újabb verziók
    - macOS 10.9 és újabb verziók
    - Android 4.0 és újabb verziók
    - Android for Work
    - Windows 8.1 és újabb
    - Windows Phone 8.1 és újabb verziók
    - Windows 10 és újabb
3. Hozza létre a VPN-, Wi-Fi- és e-mail-hozzáférés hitelesítésére szolgáló tanúsítványprofilokat.

   A következő platformú eszközök számára **PKCS-** vagy **SCEP**-tanúsítványprofilt oszthat ki:

   - iOS 8.0 és újabb verziók
   - Android 4.0 és újabb verziók
   - Android for Work
   - Windows 10 (asztali és mobilverzió), illetve újabb

   A következő platformot futtató eszközök esetében csak **SCEP-tanúsítványprofil** használható:

   - macOS 10.9 és újabb verziók
   - Windows Phone 8.1 és újabb verziók

Mindegyik eszközplatformhoz külön profilt kell létrehoznia. Létrehozásakor társítsa a profilt a már létrehozott megbízható főtanúsítvány-profilhoz.

### <a name="further-considerations"></a>További szempontok

- Ha nem rendelkezik vállalati hitelesítésszolgáltatóval, létre kell hoznia egyet.
- SCEP-profilok használatakor konfigurálnia kell egy NDES-kiszolgálót is.
- Mind az SCEP-, mind a PKCS-profilok használatához le kell töltenie és konfigurálnia kell a Microsoft Intune Tanúsítvány-összekötőt.


## <a name="step-1-configure-your-certificate-infrastructure"></a>1. lépés: a tanúsítványinfrastruktúra konfigurálása

Az alábbi témakörök nyújtanak segítséget az egyes tanúsítványprofil-típusok infrastruktúrájának konfigurálásához:

- [SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal](certificates-scep-configure.md)
- [PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>2. lépés: a megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása

Exportálja a megbízható legfelső szintű hitelesítésszolgáltató (CA) tanúsítványát **.cer** kiterjesztésű fájlként a kibocsátó hitelesítésszolgáltatóról vagy a vállalati hitelesítésszolgáltatóban megbízó bármelyik eszközről. A titkos kulcsot ne exportálja.

Ezt a tanúsítványt a megbízható tanúsítványprofil konfigurálásakor kell importálnia.

## <a name="step-3-create-trusted-certificate-profiles"></a>3. lépés: megbízható tanúsítványprofilok létrehozása
Ahhoz, hogy SCEP- vagy PKCS-tanúsítványprofilt hozhasson létre, először létre kell hoznia egy megbízható tanúsítványprofilt. Minden mobileszközplatformhoz külön megbízható tanúsítványprofil, illetve és SCEP- vagy PKCS-profil szükséges. A megbízható tanúsítványok létrehozása az összes eszközplatformon hasonlóan zajlik.

### <a name="to-create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozásához

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az megbízható tanúsítványprofil nevét és leírását a **Név** és a **Leírás** mezőben.
5. Válassza ki a megbízható tanúsítvány eszközplatformját a **Platform** legördülő listából. Jelenleg az alábbi platformokra vonatkozóan lehet tanúsítványbeállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **Megbízható tanúsítvány** lehetőséget.
7. Tallózással keresse meg az 1. feladatban mentett tanúsítványt, majd kattintson az **OK** gombra.
8. Válassza ki – csak a Windows 8.1- és Windows 10-eszközök esetében – a megbízható tanúsítvány céltárolóját a **Céltároló** mezőben, a következő lehetőségek közül:
    - **Számítógép tanúsítványtárolója – fő**
    - **Számítógép tanúsítványtárolója – köztes**
    - **Felhasználói tanúsítványtároló – köztes**
8. Ha elkészült, válassza az **OK** gombot, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** gombot.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.


> [!Note]
> Az androidos eszközök megjelenítenek egy üzenetet arról, hogy egy harmadik fél megbízható tanúsítványt telepített.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>4. lépés: SCEP- vagy PKCS-tanúsítványprofilok létrehozása

Az alábbi témakörök nyújtanak segítséget az egyes tanúsítványprofil-típusok konfigurálásához és eszközökhöz rendeléséhez:

- [SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal](certificates-scep-configure.md)
- [PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal](certficates-pfx-configure.md)

Miután létrehozott egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, létre kell hoznia a használni kívánt platformok SCEP- vagy PKCS-tanúsítványprofilját is. Az SCEP-tanúsítványprofil létrehozásakor meg kell adnia egy ugyanarra a platformra vonatkozó megbízható tanúsítványprofilt. Ez a művelet összeköti a két tanúsítványprofilt, de az egyes profilok hozzárendelését külön-külön kell elvégeznie.


## <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendeléséről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt általános tájékoztatást.

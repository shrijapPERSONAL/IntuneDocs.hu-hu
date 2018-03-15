---
title: "Tanúsítványprofil létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs"
description: "Az eszközökhöz SCEP- vagy PKCS-tanúsítványkörnyezet konfigurálásával, a nyilvános tanúsítvány exportálásával, a profil az Azure Portalon való létrehozásával, majd a SCEP vagy PKCS a tanúsítványprofilhoz való hozzárendelésével adhat hozzá tanúsítványprofilokat a Microsoft Intune-ban, az Azure Portalon"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b9d181c4a6e490018c88214a2ed91c90327f2526
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Eszközök tanúsítványprofiljainak konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Amikor a felhasználóknak engedélyezi a vállalati erőforrások VPN-, Wi-Fi- vagy e-mail-profilokon keresztüli elérését, ezeket a kapcsolatokat tanúsítványokkal hitelesítheti. Tanúsítványok használatakor nem kell megadnia a felhasználóneveket és a jelszavakat a kapcsolatok hitelesítéséhez 

Az Intune-nal hozzárendelheti ezeket a tanúsítványokat a felügyelt eszközökhöz. Az Intune a következő tanúsítványtípusok eszközökhöz rendelését és felügyeletét támogatja:

- SCEP protokoll
- PKCS#12 (vagy PFX)

Ezen tanúsítványtípusok mindegyikének megvannak a maga előfeltételei és infrastrukturális követelményei.

## <a name="overview"></a>Áttekintés

1. Ha még nem működik a megfelelő tanúsítványinfrastruktúra, helyezze üzembe. [SCEP-tanúsítványokat](certificates-scep-configure.md) és [PKCS-tanúsítványokat](certficates-pfx-configure.md) használhat.

2. Telepítsen egy főtanúsítványt vagy köztes hitelesítésszolgáltatói tanúsítványt minden eszközön, hogy az eszköz felismerje a hitelesítésszolgáltató (CA) érvényességét. Ehhez hozzon létre és rendeljen hozzá egy **megbízható tanúsítványprofilt**. A profil hozzárendelésekor az Intune-nal felügyelt eszközök lekérik és megkapják a főtanúsítványt. Mindegyik platformhoz különálló profilt kell létrehoznia. A megbízható tanúsítványprofilok a következő platformokhoz érhetők el:

    - iOS 8.0 és újabb verziók
    - macOS 10.9 és újabb verziók
    - Android 4.0 és újabb verziók
    - Android for Work
    - Windows 8.1 és újabb
    - Windows Phone 8.1 és újabb verziók
    - Windows 10 és újabb

3. Hozza létre a VPN-, Wi-Fi- és e-mail-hozzáférés hitelesítésére szolgáló tanúsítványprofilokat. A következő platformú eszközök számára **PKCS-** vagy **SCEP**-tanúsítványprofilt oszthat ki:

   - iOS 8.0 és újabb verziók
   - Android 4.0 és újabb verziók
   - Android for Work
   - Windows 10 (asztali és mobilverzió), illetve újabb

   A következő platformot futtató eszközök esetében csak **SCEP-tanúsítványprofil** használható:

   - macOS 10.9 és újabb verziók
   - Windows Phone 8.1 és újabb verziók

Mindegyik eszközplatformhoz külön profilt kell létrehoznia. Létrehozásakor társítsa a profilt a már létrehozott megbízható főtanúsítvány-profilhoz.

### <a name="further-considerations"></a>További szempontok

- Ha nem rendelkezik vállalati hitelesítésszolgáltatóval, létre kell hoznia egyet
- SCEP-profilok használatakor konfigurálnia kell egy NDES-kiszolgálót is
- Mind az SCEP-, mind a PKCS-profilok használatához le kell töltenie és konfigurálnia kell a Microsoft Intune Tanúsítvány-összekötőt


## <a name="step-1-configure-your-certificate-infrastructure"></a>1. lépés: a tanúsítványinfrastruktúra konfigurálása

Az alábbi témakörök nyújtanak segítséget az egyes tanúsítványprofil-típusok infrastruktúrájának konfigurálásához:

- [SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal](certificates-scep-configure.md)
- [PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>2. lépés: a megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása

Exportálja a megbízható legfelső szintű hitelesítésszolgáltató (CA) tanúsítványát nyilvános, (.cer) kiterjesztésű fájlként a kibocsátó hitelesítésszolgáltatóról vagy a vállalati hitelesítésszolgáltatóban megbízó bármelyik eszközről. A titkos kulcsot (.pfx) ne exportálja.

Ezt a tanúsítványt a megbízható tanúsítványprofil konfigurálásakor kell importálnia.

## <a name="step-3-create-trusted-certificate-profiles"></a>3. lépés: megbízható tanúsítványprofilok létrehozása
Ahhoz, hogy SCEP- vagy PKCS-tanúsítványprofilt hozhasson létre, először létre kell hoznia egy megbízható tanúsítványprofilt. Minden mobileszközplatformhoz külön megbízható tanúsítványprofil, illetve és SCEP- vagy PKCS-profil szükséges. A megbízható tanúsítványok létrehozása az összes eszközplatformon hasonlóan zajlik.

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, majd keresse meg a **Microsoft Intune** elemet.
2. A **Microsoft Intune** területen válassza az **Eszközkonfiguráció** lehetőséget, majd a **Profilok** elemet. Ezt követően válassza a **Profil létrehozása** lehetőséget.
3. Adja meg a megbízható tanúsítványprofil **nevét** és **leírását**.
4. Adja meg a megbízható tanúsítvány eszközplatformját a **Platform** területen: 

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**

5. A **Profil típusa** beállításban válassza a **Megbízható tanúsítvány** lehetőséget. Keresse meg a 2. lépésben elmentett tanúsítványt (*TanúsítványNév*.cer).

    Válassza ki – csak a Windows 8.1- és Windows 10-eszközök esetében – a megbízható tanúsítvány céltárolóját a **Céltároló** mezőben, a következő lehetőségek közül:  

    - **Számítógép tanúsítványtárolója – fő**
    - **Számítógép tanúsítványtárolója – köztes**
    - **Felhasználói tanúsítványtároló – köztes**

6. A módosítások mentéséhez kattintson az **OK** gombra, majd válasza a **Létrehozás** lehetőséget az új profil mentéséhez.

Ekkor létrejön a profil, és megjelenik a listán. Ha csoportokhoz szeretné hozzárendelni a profilt, tekintse meg az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikket.

Az Android-eszközök megjeleníthetnek egy üzenetet arról, hogy egy harmadik fél megbízható tanúsítványt telepített.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>4. lépés: SCEP- vagy PKCS-tanúsítványprofilok létrehozása

Az alábbi témakörök nyújtanak segítséget az egyes tanúsítványprofil-típusok konfigurálásához és eszközökhöz rendeléséhez:

- [SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal](certificates-scep-configure.md)
- [PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal](certficates-pfx-configure.md)

Miután létrehozott egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, létre kell hoznia a használni kívánt platformok SCEP- vagy PKCS-tanúsítványprofilját is. SCEP-tanúsítványprofil létrehozásakor adjon meg egy ugyanarra a platformra vonatkozó megbízható tanúsítványprofilt. Ez a művelet összeköti a két tanúsítványprofilt, de az egyes profilok hozzárendelését külön-külön kell elvégeznie.

## <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendeléséről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt általános tájékoztatást.
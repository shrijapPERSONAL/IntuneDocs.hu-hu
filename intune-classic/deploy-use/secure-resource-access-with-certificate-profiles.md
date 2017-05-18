---
title: "Tanúsítványprofilok az erőforrások eléréséhez | Microsoft Docs"
description: "Biztonságos VPN-, Wi-Fi- és e-mailes hozzáférés az egyes eszközökre telepített tanúsítványok segítségével."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9cf53cb240ba14317fbb680ad4f4c40c8320506d
ms.lasthandoff: 12/10/2016


---

# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Amikor a felhasználóknak engedélyezi a vállalati erőforrások VPN-, Wi-Fi- vagy e-mail-profilokon keresztüli elérését, a hozzáférés biztonságosságáról az egyes felhasználói eszközökön telepített tanúsítványokkal gondoskodhat. Működési elv:

1. Győződjön meg arról, hogy már működik a megfelelő tanúsítványinfrastruktúra a [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md) és a [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md) című témakörben foglaltak szerint.

2. Telepítsen egy főtanúsítványt vagy köztes hitelesítésszolgáltatói tanúsítványt minden eszközön, hogy az eszköz felismerje a hitelesítésszolgáltató (CA) érvényességét. Ehhez hozzon létre és telepítsen egy **megbízható tanúsítványprofilt**. A profil telepítésekor az Intune-nal felügyelt eszközök lekérik és megkapják a főtanúsítványt. Mindegyik platformhoz különálló profilt kell létrehoznia. A **megbízható tanúsítványprofil** a következő platformokhoz érhető el:
 -  iOS 8.0 és újabb verziók
 -  Mac OS X 10.9 és újabb verziók
 -  Android 4.0 és újabb verziók
 -  Android for Work
 -  Windows 8.1 és újabb
 -  Windows Phone 8.1 és újabb verziók

3. Az [Intune-tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md) című részben leírtak szerint hozza létre a VPN-, Wi-Fi- és e-mail-hozzáférés hitelesítésére szolgáló tanúsítványprofilokat. A következő platformokon működő eszközökre **PKCS #12 (.PFX) formátumú tanúsítványprofilt** *vagy* **SCEP-tanúsítványprofilt** telepíthet:

  -  iOS 8.0 és újabb verziók
  -  Android 4.0 és újabb verziók
  -  Android for Work
  -  Windows 10 (asztali és mobilverzió), illetve újabb

  A következő platformon működő eszközök esetében használjon **SCEP-tanúsítványprofilt**:
    -   Mac OS X 10.9 és újabb verziók
    -   Windows Phone 8.1

Mindegyik platformhoz különálló profilt kell létrehoznia. A profil létrehozásakor társítsa azt a már létrehozott **megbízható főtanúsítvány-profillal**.

> [!NOTE]           
> - Ha nem rendelkezik vállalati hitelesítésszolgáltatóval, létre kell hoznia egyet.
>- Ha az eszközplatformjai alapján úgy dönt, hogy SCEP-profilt használ, egy NDES-kiszolgálót is konfigurálnia kell.
>-  Mind az SCEP-, mind a .PFX-profilok használatához le kell töltenie és konfigurálnia kell a Microsoft Intune tanúsítvány-összekötőjét.
>-  Ezek konfigurálását az [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md) és a [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md) című témakör ismerteti.

### <a name="next-steps"></a>További lépések
- [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md)
- [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md)
- [Intune-tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md)


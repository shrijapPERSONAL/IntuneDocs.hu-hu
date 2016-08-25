---
title: "Tanúsítványprofilok az erőforrások eléréséhez | Microsoft Intune"
description: "Biztonságos VPN-, Wi-Fi- és e-mailes hozzáférés az egyes eszközökre telepített tanúsítványok segítségével."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c8158b6a54347f6bec1008142eed44daca8946d0


---

# Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével
Amikor engedélyezi a vállalati erőforrások VPN-en, Wi-Fi-n vagy e-mailes profilokon keresztüli hozzáférését, biztonságossá teheti ezt a hozzáférést az egyes felhasználói eszközökre telepített tanúsítvánnyal. Működési elv:

1. Győződjön meg arról, hogy már működik a megfelelő tanúsítványinfrastruktúra a [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) (SCEP-tanúsítványinfrastruktúra konfigurálása) vagy a [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md) (PFX-tanúsítványinfrastruktúra konfigurálása) című témakörben foglaltak szerint.

2. Telepítsen egy főtanúsítványt (vagy köztes hitelesítésszolgáltatói tanúsítványt) minden eszközön, hogy az eszköz felismerje a hitelesítésszolgáltató érvényességét. Ezt egy **megbízhatótanúsítvány-profil** létrehozásával és telepítésével teheti meg. A profil telepítésekor az Intune-nal felügyelt eszközök lekérik és megkapják a főtanúsítványt. Mindegyik platformhoz különálló profilt kell létrehoznia. A **megbízható tanúsítványprofil** a következő platformokhoz érhető el:
 -  iOS 7.1-es és újabb verziók
 -  Mac OS X 10.9 és újabb verziók
 -  Android 4.0 és újabb verziók
 -  Windows 8.1 és újabb
 -  Windows Phone 8.1 és újabb verziók

3. Állítsa be a következő témakörnek megfelelően, hogy mindegyik eszköz tanúsítványt kérjen az e-mailes, VPN- és Wi-Fi-hozzáférés hitelesítéséhez: [Intune-tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md). **PKCS #12 (.PFX) tanúsítványt** vagy **SCEP-tanúsítványt** telepíthet a következő platformot használó eszközökre:

-  Android 4.0 és újabb verziók
-  iOS 7.1-es és újabb verziók
-  Windows 10 (asztali és mobilverzió), illetve újabb

Használja az **SCEP-tanúsítványprofilt** a következőkhöz:
-   Mac OS X 10.9 és újabb verziók
-   Windows Phone 8.1 és újabb verziók

Mindegyik platformhoz különálló profilt kell létrehoznia. A profil létrehozásakor a már létrehozott **megbízható főtanúsítvány-profillal** társítja azt.

> [!NOTE]           
> -    Ha nem rendelkezik vállalati hitelesítésszolgáltatóval, létre kell hoznia egyet.
>- Ha az eszközplatformjai alapján úgy dönt, hogy SCEP-profilt használ, egy NDES-kiszolgálót is konfigurálnia kell.
>-  SCEP- vagy .PFX-profilok használatához le kell töltenie és konfigurálnia kell a Microsoft Intune tanúsítvány-összekötőjét.
> Ezek konfigurálása az [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md) és a [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md) című témakörben lett ismertetve.

### További lépések
- [SCEP-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-scep.md)
- [PFX-tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure-for-pfx.md)
- [Intune-tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO3-->



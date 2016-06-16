---
# required metadata

title: Vállalati erőforrások elérésének lehetővé tétele tanúsítványprofilokkal | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével
Amikor engedélyezi a vállalati erőforrások VPN-en, Wi-Fi-n vagy e-mailes profilokon keresztüli hozzáférését, biztonságossá teheti ezt a hozzáférést az egyes felhasználói eszközökre telepített tanúsítvánnyal. Működési elv:

1. Győződjön meg arról, hogy már működik a megfelelő tanúsítványinfrastruktúra a [Tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure.md) című témakörben foglaltak szerint.

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
> Mindegyik említett eset konfigurálását a következő témakör ismerteti: [Tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure.md).

### További lépések
- [Tanúsítványinfrastruktúra konfigurálása](configure-certificate-infrastructure.md)
- [Intune-tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md)



<!--HONumber=Jun16_HO1-->



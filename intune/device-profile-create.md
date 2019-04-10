---
title: Eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Adjon hozzá vagy eszközkonfigurációs profil konfigurálása a Microsoft Intune-ban. Válassza ki a platform típusát, adja meg a beállításokat, és a egy hatókörcímkét hozzá.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423529"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Eszközprofil létrehozása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Eszközök profilok hozzáadása és konfigurálása a beállítások lehetővé teszik, és juttathatja el ezeket a beállításokat a szervezetnél található eszközökön. [Az eszközprofilok segítségével eszközök szolgáltatásainak és beállításainak alkalmazása](device-profiles.md) részletesebb leírását – például, hogy miket tehet lépnek.

Ez a cikk:

- Profil létrehozásának lépéseit ismerteti.
- Bemutatja, hogyan hatókörcímke "szűréséhez" a profil hozzáadásához.
- A bejelentkezési frissítési ciklusok idejét, amikor eszköz megkapja-e a profilokat, az összes profil együtt sorolja fel.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.

2. Válassza az **Eszközök konfigurálása** lehetőséget. A következő lehetőségek állnak rendelkezésére:

    - **Áttekintés**: Listázza a profilok állapotát, és ez a témakör további részleteket a felhasználókhoz és eszközökhöz rendelt profilokról.
    - **Kezelése**: Eszközprofilok létrehozása, és töltse fel az egyéni [PowerShell-parancsfájlok](intune-management-extension.md) a profilon belül futtatandó, és eszközöket vehet fel adatforgalmi [esim-kártya](esim-device-configuration.md).
    - **A figyelő**: Ellenőrizze a profil sikeres vagy sikertelen állapotát, és naplók megtekintése a profilok.
    - **A telepítő**: SCEP- vagy PFX hitelesítésszolgáltató, vagy engedélyezze a [Távközlésiköltség-kezelőben](telecom-expenses-monitor.md) a profilban.

3. Válassza ki **profilok** > **profil létrehozása**. Adja meg a következő tulajdonságokat:

   - **Név**: Adjon meg egy leíró nevet a profilhoz. Adjon nevet a profilokat, így könnyen azonosíthatja azokat később. Például a helyes profil neve van **WP e-mail-profil teljes vállalati**.
   - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza ki a platform az eszközök. A választható lehetőségek:  

       - **Android**
       - **Vállalati Android**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 és újabb**
       - **Windows 10 és újabb**

   - **Profil típusa**: Válassza ki a létrehozni kívánt beállításokat. A megjelenő listában függ a **platform** választja.
   - **Beállítások**: Az alábbi cikkek ismertetik az egyes profiltípusok beállításait:

       - [Felügyeleti sablonok](administrative-templates-windows.md)
       - [Egyéni](custom-settings-configure.md)
       - [Kézbesítésoptimalizálás](delivery-optimization-windows.md)
       - [Eszközfunkciók](device-features-configure.md)
       - [Eszközkorlátozások](device-restrictions-configure.md)
       - [Kiadás frissítési és mód kapcsoló](edition-upgrade-configure-windows-10.md)
       - [Oktatás](education-settings-configure.md)
       - [E-mail](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Identity protection](identity-protection-configure.md)  
       - [Kioszkmód](kiosk-settings.md)
       - [PKCS-tanúsítvány](certficates-pfx-configure.md)
       - [SCEP-tanúsítvány](certificates-scep-configure.md)
       - [Megbízható tanúsítvány](certificates-configure.md)
       - [Frissítési szabályzatok](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [A Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Információvédelem](windows-information-protection-configure.md)

     Például, ha kiválasztja **iOS** a platform típusát a profilbeállítások hasonlóan néz ki: ehhez a profilhoz:

     ![IOS-profil létrehozása az Intune-ban](./media/create-device-profile.png)

4. Amikor végzett, válassza ki a **OK** > **létrehozás** a módosítások mentéséhez. A profil létrehozásáról, és látható a listában.

## <a name="scope-tags"></a>Hatókörcímkék

Miután hozzáadta a beállításokat, a profil még egy hatókörcímkét is hozzáadhat. Hatókörcímkék hozzárendelni, és meghatározott csoportokra, például a HR vagy minden Egyesült Államokbeli a Hálózatvezérlő által alkalmazott szabályzatok szűrő.

Hatókörcímkék, és mit tehet kapcsolatos további információkért lásd: [RBAC használata és a hatókörcímkék elosztott informatikai](scope-tags.md).

### <a name="add-a-scope-tag"></a>Hatókörcímke hozzáadása

1. Válassza ki **hatókör (címkék)**.
2. Válassza ki **Hozzáadás** hatókör új címke létrehozásához. Vagy válasszon ki egy meglévő hatókörcímke a listából.
3. Válassza ki **OK** a módosítások mentéséhez.

## <a name="refresh-cycle-times"></a>Frissítse a ciklusok idejét

Az Intune a következő adatfrissítési ciklusok konfigurációs profilokat a frissítések kereséséhez használja:

| Platform | A frissítés|
| --- | --- |
| iOS | 6 óránként |
| macOS | 6 óránként |
| Android | 8 óránként |
| Eszközként regisztrált Windows 10 számítógépek | 8 óránként |
| Windows Phone | 8 óránként |
| Windows 8.1 | 8 óránként |

Ha az eszköz nemrég lett regisztrálva, a bejelentkezés gyakrabban fusson:

| Platform | Gyakoriság |
| --- | --- |
| iOS | 6 órán át 15 perceként, majd 6 óránként |  
| macOS | 6 órán át 15 perceként, majd 6 óránként | 
| Android | 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Eszközként regisztrált Windows 10 számítógépek | 30 percen át 3 percenként, majd 8 óránként | 
| Windows Phone | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Windows 8.1 | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 

Bármikor a felhasználók nyissa meg a céges portál alkalmazást, és az eszköz szinkronizálása érdekében az profil frissítések azonnali ellenőrzésére.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

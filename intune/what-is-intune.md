---
title: "Az Azure Portalbeli Intune bemutatása"
titlesuffix: Azure portal
description: "Az Azure Portalbeli Intune alapjainak ismertetése, és hogy miként segíthet az eszközök felügyeletében.”"
keywords: 
author: arob98
ms.author: angrobe
nmanager: dougeby
ms.date: 10/30/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 19b5d98165be67b32afa86ba942c42fc4a3048b3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Az Azure Portalbeli Microsoft Intune bemutatása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune az Azure Portal webhelyre kerül át, ami azt jelenti, hogy a megszokott munkafolyamatok és funkciók megváltoztak.
Az új portál új és frissített funkciókat kínál az Azure Portalon, ahol felügyelheti munkahelye mobileszközeit, számítógépeit és alkalmazásait.

* A [Hová kerültek a szolgáltatások az Azure-ban?](ui-changes.md) hivatkozással megjelenítheti az adott, az Azure-ra való átálláskor módosított munkafolyamatokat és felhasználóifelület-elemeket.
* A [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md) ismerteti a csoportok kezelésében az Azure Active Directory biztonsági csoportokra való áttérés hatásait.




Ebben a könyvtárban találja az új termék folyamatosan frissülő dokumentációját. Ha javaslatai vannak, küldjön visszajelzést a témakör megjegyzéseiben. Szívesen meghallgatnánk a véleményét.

Az új felhasználói felület főbb újdonságai a következők:

- Integrált konzol az Enterprise Mobility + Security (EMS) összes biztonsági összetevőjéhez
- Webes szabványokra épülő HTML-alapú konzol
- Microsoft Graph API-támogatás számos művelet automatizálásához
- Azure Active Directory- (AD-)csoportok az Azure-os alkalmazások közötti kompatibilitás érdekében
- A legtöbb modern böngésző támogatása

## <a name="before-you-start"></a>Előkészületek

Az Azure Portalon az Intune használatához Intune-os rendszergazdai és bérlői fiókkal kell rendelkeznie. Ha még nincs fiókja, [regisztráljon](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Támogatott webböngészők az Azure portálon

Az Azure Portal működik a legtöbb modern PC-n, Mac-en és táblagépen. Mobiltelefonok használata nem támogatott.
Jelenleg a következő böngészők támogatottak:

- Microsoft Edge (legújabb verzió)
- Microsoft Internet Explorer 11
- Safari (csak Mac, legújabb verzió)
- Chrome (legújabb verzió)
- Firefox (legújabb verzió)

A támogatott böngészőkről az [Azure Portalon](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) találja a legfrissebb információt.

## <a name="whats-in-this-library"></a>Mit tartalmaz ez a könyvtár?

A dokumentáció a szükséges információk könnyebb megtalálhatósága érdekében az Azure Portal elrendezését tükrözi.

![Az Azure Portal munkafolyamatai](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Bevezetés és az első lépések
Ez a szakasz [bevezető jellegű információt](introduction-intune.md) tartalmaz, amely az Intune használatának megkezdéséhez nyújt segítséget.
### <a name="plan-and-design"></a>Tervezés és kialakítás
Hasznos tudnivalók az Intune-környezet [tervezéséhez és kialakításához](/intune-classic/plan-design/introduction).
### <a name="device-enrollment"></a>Eszközök beléptetése
[Útmutató az eszközök Intune általi felügyeletéhez.](device-enrollment.md)
### <a name="device-compliance"></a>Eszközmegfelelőség
[Definiálhatja az eszközök megfelelőségi szintjét, majd jelentést készíthet a nem megfelelő eszközökről](device-compliance.md).
### <a name="device-configuration"></a>Eszközök konfigurálása
[A felügyelt eszközök beállításainak és szolgáltatásainak konfigurálására szolgáló profilok ismertetése.](device-profiles.md)
### <a name="devices"></a>Eszközök
[A leltár és a jelentések segítségével megismerkedhet a felügyelt eszközökkel.](device-management.md)
### <a name="mobile-apps"></a>Mobilalkalmazásokban
[Útmutató az alkalmazások közzétételéhez, felügyeletéhez, konfigurálásához és védelméhez.](app-management.md)
### <a name="conditional-access"></a>Feltételes hozzáférés
[A megadott feltételek alapján korlátozhatja az Exchange-szolgáltatásokhoz való hozzáférést.](conditional-access.md)
### <a name="on-premises-access"></a>Helyszíni hozzáférés
[Az Exchange ActiveSynchez és a helyszíni Exchange-hez való hozzáférés konfigurálása](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Ismerje meg a felügyelt eszközfelhasználókat, és rendezze csoportba az erőforrásokat](users-add.md).
### <a name="groups"></a>Csoportok
[Ismerje meg, hogyan használhatja az Azure Active Directory-csoportokat az Intune-nal](groups-get-started.md)
### <a name="intune-roles"></a>Intune-szerepkörök
[Szabályozhatja, hogy kik hajthatnak végre különböző műveleteket az Intune-ban, és kikre vonatkozzanak ezen műveletek.](role-based-access-control.md) A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.
### <a name="software-updates"></a>Szoftverfrissítések
[Ismerje meg, hogyan konfigurálhatja a szoftverfrissítéseket Windows 10-es eszközök esetén](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Újdonságok

[Ismerje meg az Intune újdonságait](whats-new.md).

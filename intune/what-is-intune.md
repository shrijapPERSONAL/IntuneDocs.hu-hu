---
title: "Az Azure-beli Intune előzetes verziójának bemutatása"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Ismerje meg az Azure Portal előzetes verziójának alapjait, és hogy miként lehet segítségére az eszközök felügyeletében."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d7ff50eb821e0927c3c6ea21f3cdb1257762a0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>A Microsoft Intune bemutatása az Azure Portal előzetes verziójában


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A Microsoft Intune az Azure Portalra kerül át, ami azt jelenti, hogy a megszokott munkafolyamatok és funkciók változnak.
Az új portál betekintést nyújt az új és frissített Azure Portal-funkciókba, amelyekkel felügyelheti munkahelye mobileszközeit, számítógépeit és alkalmazásait.
Végül minden Intune-funkció átkerül majd az Azure-ba, de számos Intune-feladatot már most is elvégezhet az Azure Portalon. Mivel az új felület előnézet, bizonyos funkciók még nem szerepelnek a portálon. A részletekért lásd az [Újdonságok](#whats-new) ismertetését.

> [!IMPORTANT]
> **Nem jelenik még meg az új portál?**<br>
> A Microsoft bizonyos kiválasztott bérlők számára már elkezdte az előzetes bevezetését. A meglévő bérlők migrálása az új felhasználói felületre a 2017-es év elejétől kezdődik. Az Office-üzenetközpontban a bérlő migrálása előtt értesítést fog kapni.
>
> A 2017 januárja előtt létrehozott Intune-fiókok esetében az Apple-regisztrációs munkafolyamatok egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.


Ebben a könyvtárban találja az új termék dokumentációját, amely folyamatosan frissül az előzetes során. Ha javaslatai vannak, küldjön visszajelzést a témakör megjegyzéseiben. Szívesen meghallgatnánk a véleményét.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Az új felhasználói felület főbb újdonságai a következők:

- Integrált konzol az Enterprise Mobility + Security (EMS) összes biztonsági összetevőjéhez
- Webes szabványokra épülő HTML-alapú konzol
- Microsoft Graph API-támogatás számos művelet automatizálásához
- Azure Active Directory- (AD-)csoportok az Azure-os alkalmazások közötti kompatibilitás érdekében
- A legtöbb modern böngésző támogatása

A klasszikus Intune-konzolhoz az [Intune dokumentációs könyvtárában](https://docs.microsoft.com/intune-classic/) találhat dokumentációt.

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

A dokumentáció a szükséges információk könnyebb megtalálhatósága érdekében az Intune-portál elrendezését tükrözi.

![Az Azure Portal munkafolyamatai](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Bevezetés és az első lépések
Ez a szakasz tájékoztatást nyújt az [újdonságokról](whats-new.md), az [ismert problémákról](known-issues.md), a [támogatás kéréséről](get-support.md) és az Intune [ingyenes próbaverziójáról](free-trial-sign-up.md).
### <a name="plan-and-design"></a>Tervezés és kialakítás
Hasznos tudnivalók az Intune-környezet [tervezéséhez és kialakításához](/intune-classic/plan-and-design/introduction).
### <a name="device-enrollment"></a>Eszközök beléptetése
[Útmutató az eszközök Intune általi felügyeletéhez.](device-enrollment.md)
### <a name="device-compliance"></a>Eszközmegfelelőség
[Definiálhatja az eszközök megfelelőségi szintjét, majd jelentést készíthet a nem megfelelő eszközökről.](device-compliance.md)
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
[Ismerje meg a felügyelt eszközfelhasználókat, és rendezze csoportba az erőforrásokat](user-management.md).
### <a name="groups"></a>Csoportok
[Ismerje meg, hogyan használhatja az Azure Active Directory-csoportokat az Intune-nal](groups-get-started.md)
### <a name="intune-roles"></a>Intune-szerepkörök
[Szabályozhatja, hogy kik hajthatnak végre különböző műveleteket az Intune-ban, és kikre vonatkozzanak ezen műveletek.](role-based-access-control.md) A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.
### <a name="software-updates"></a>Szoftverfrissítések
[Ismerje meg, hogyan konfigurálhatja a szoftverfrissítéseket Windows 10-es eszközök esetén](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Újdonságok

[Az előzetes kiadás újdonságainak ismertetése](whats-new.md).


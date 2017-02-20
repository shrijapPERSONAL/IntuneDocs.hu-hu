---
title: "Bevezetés – Intune az Azure Portalon – Előzetes verzió | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Ismerje meg az Azure Portal előzetes verziójának alapjait, és hogy miként lehet segítségére az eszközök felügyeletében."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>A Microsoft Intune bemutatása az Azure Portal előzetes verziójában


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune az Azure Portalra kerül át, ami azt jelenti, hogy a megszokott munkafolyamatok és funkciók változnak.
Az új portál az új és frissített Azure Portal-funkciók előzetes verzióját kínálja, amelyben felügyelheti munkahelye mobileszközeit, számítógépeit és alkalmazásait.
Minden Intune-funkció végül az Azure-ba kerül majd át, de bizonyos Intune-feladatokat már most elvégezhet az Azure Portalon. Mivel az új felület előnézet, bizonyos funkciók még nem szerepelnek a portálon. A részletekért lásd [az előzetes újdonságainak](#what's-new-in-the-preview) ismertetését.

> [!IMPORTANT]
> **Nem jelenik még meg az új portál?**<br>
> A Microsoft bizonyos kiválasztott bérlők számára már elkezdte az előzetes bevezetését. A meglévő bérlők migrálása az új felhasználói felületre a 2017-es év elejétől kezdődik. Az Office-üzenetközpontban a bérlő migrálása előtt értesítést fog kapni. Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


Ebben a könyvtárban találja az új termék dokumentációját, amely folyamatosan frissül az előzetes során. Ha javaslatai vannak, küldjön visszajelzést a témakör megjegyzéseiben. Szívesen meghallgatnánk a véleményét.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Az új felhasználói felület főbb újdonságai a következők:

- Integrált konzol az Enterprise Mobility + Security (EMS) összes biztonsági összetevőjéhez
- Webes szabványokra épülő HTML-alapú konzol
- Microsoft Graph API-támogatás számos művelet automatizálásához
- Azure AD-csoportok az Azure-os alkalmazások közötti kompatibilitás érdekében
- A legtöbb modern böngésző támogatása

A klasszikus Intune-konzolhoz az [Intune dokumentációs könyvtárában](https://docs.microsoft.com/en-us/intune/) találhat dokumentációt.

## <a name="before-you-start"></a>Előkészületek

Az Azure Portalon az Intune használatához Intune-os rendszergazdai és bérlői fiókkal kell rendelkeznie. [Itt](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) igényelhet fiókot.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Támogatott webböngészők az Azure portálon

Az Azure Portal működik a legtöbb modern PC-n, Mac-en és táblagépen. Mobiltelefonok használata nem támogatott.
Jelenleg a következő böngészők támogatottak:

- Microsoft Edge (legújabb verzió)
- Microsoft Internet Explorer 11
- Safari (csak Mac, legújabb verzió)
- Chrome (legújabb verzió)
- Firefox (legújabb verzió)

A támogatott böngészőkről a legfrissebb információt [itt](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) találja.

## <a name="whats-in-this-library"></a>Mit tartalmaz ez a könyvtár?

A dokumentáció a szükséges információk könnyebb megtalálhatósága érdekében az Intune-portál elrendezését tükrözi.

![Az Azure Portal munkafolyamatai](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Eszközök regisztrálása
Útmutató az eszközök Intune általi felügyeletéhez.
[További információ](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>Eszközök és csoportok
A leltár és a jelentések segítségével megismerkedhet a felügyelt eszközökkel.
[További információ](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>Felhasználók kezelése
Áttekintheti a felügyelt eszközök felhasználóit.
[További információ](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>Alkalmazások kezelése
Az alkalmazások közzétételével, felügyeletével, konfigurálásával és védelmével kapcsolatos információt tartalmazza.
[További információ](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>Eszközök konfigurálása
Azon profilokkal kapcsolatos információt tartalmazza, amelyek segítségével konfigurálhatja a beállításokat és a szolgáltatásokat a felügyelt eszközökön.
[További információ](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>Eszközmegfelelőség beállítása
Definiálhatja az eszközök megfelelőségi szintjét, majd jelentést készíthet a nem megfelelő eszközökről [További információ](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>Feltételes hozzáférés
Korlátozhatja az Exchange-szolgáltatásokhoz való hozzáférést az Ön által megadott feltételektől függően.
[További információ](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>Hozzáférés-vezérlés
Szabályozhatja, hogy kik hajthatnak végre különböző műveleteket az Intune-ban, és kikre vonatkozzanak ezen műveletek. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.
[További információ](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>Újdonságok

[Az előzetes kiadás újdonságainak ismertetése](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


---
title: "Az Azure Portalbeli Intune bemutatása"
titlesuffix: Azure portal
description: "Az Azure Portalbeli Intune alapjainak ismertetése, és hogy miként segíthet az eszközök felügyeletében.”"
keywords: 
author: arob98
ms.author: angrobe
nmanager: dougeby
ms.date: 02/14/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 6e2528c243938e81a6f730a950ee3949ca44047c
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2018
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Az Azure Portalbeli Microsoft Intune bemutatása


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune a többi Azure-szolgáltatáshoz hasonlóan az Azure Portalon érhető el. Az Azure Portalon az **Intune** lehetőség kiválasztásával kezelheti a cége mobileszközeit, PC-it és alkalmazásait.

>[!NOTE] 
> Ha a Microsoft Intune egy korábbi verzióját már használta, akkor az alábbi információt hasznosnak fogja találni:
    * A [Hová kerültek a szolgáltatások az Azure-ban?](ui-changes.md) hivatkozással megjelenítheti az adott, az Azure-ra való átálláskor módosított munkafolyamatokat és felhasználóifelület-elemeket.
    * A [Klasszikus Intune-csoportok az Azure Portalon](groups-get-started.md) ismerteti a csoportok kezelésében az Azure Active Directory biztonsági csoportokra való áttérés hatásait.

A Microsoft Intune Azure Portalbeli használatának néhány fontos pontja:

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

## <a name="microsoft-intune-in-the-azure-portal"></a>A Microsoft Intune az Azure Portalon

A Microsoft Intune szolgáltatást az [Azure Portalon](https://portal.azure.com) találhatja meg. Az Azure számos szolgáltatást tartalmaz, amelyek közül sokat valószínűleg nem használ napi szinten. A [Bevezetés az Intune használatába az Azure Portalon](get-started-azure.md) című cikkben segítséget kaphat a portál használatának beállításához.

## <a name="the-microsoft-intune-documentation"></a>A Microsoft Intune dokumentációja

Ezt a témát a Microsoft Intune teljes dokumentációjához hasonlóan folyamatosan frissítjük. Ha javaslatai vannak, küldjön visszajelzést a témakör megjegyzéseiben. Szívesen meghallgatnánk a véleményét.

A dokumentáció a szükséges információk könnyebb megtalálhatósága érdekében a Microsoft Intune (alább látható) Azure Portalbeli elrendezését tükrözi.

![Az Azure Portal munkafolyamatai](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Útmutató a dokumentációhoz

Az alábbi táblázatban gyorsan megtalálhatja a Microsoft Intune használatához szükséges főbb információkat.

| Szakasz                                                      | Description                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Bevezetés és az első lépések](introduction-intune.md)       | Az Intune alapjai, többek között:<br /> – Gyakran használt megoldások<br /> – Hogyan működik a Microsoft Intune<br /> – Eszközkezelés az Intune-ban<br /> – Alkalmazáskezelés az Intune-ban<br /> – Nagyvállalati mobilitási felügyelet (EMM) eszközregisztrálással és anélkül                                                         |
| [Tervezés és kialakítás](planning-guide.md)                         | Útmutató a Microsoft Intune-környezet megtervezéséhez és kialakításához.                                                                                                                                                                                                             |
| [Eszközök regisztrálása](device-enrollment.md)                    | Azt ismerteti, hogyan segít a Microsoft Intune a munkahelyi eszközök felügyeletében az eszközök Intune-ban való regisztrálásával. A dolgozók eszközeit többféleképpen is lehet regisztrálni.                                                                                                         |
| [Eszközmegfelelőség](device-compliance.md)                    | Az eszközöknek az Intune eszközmegfelelőségi szabályzatai által meghatározott szabályok és beállítások szerint kell működnie, hogy a Microsoft Intune megfelelőnek tekintse azokat. Megfelelőségre példa lehet többek között az, ha az eszközhöz való hozzáféréshez jelszót követel meg, ha titkosítja az eszközt, vagy ha az operációs rendszer egy adott minimális verziószámát írja elő. |
| [Eszközök konfigurálása](device-profiles.md)                   | A Microsoft Intune-nal eszközprofilok létrehozásával konfigurálhatja az összes felügyelt eszközre vonatkozó beállításokat és funkciókat. Beállíthatja például az értesítéseket, az adatmegosztást, az e-mailes támogatást, a Wi-Fi-kapcsolatot, a tanúsítványokat vagy a végpontok védelmét.              |
| [Eszközök](device-management.md)                              | Biztosítani szükséges, hogy a felügyelt eszközök rendelkezzenek minden olyan erőforrással, amelyekre a felhasználóknak a munkavégzéshez szükségük lehet, miközben a céges adatokat is védeni kell a kockázatoktól. Az eszközöket a munkahelyi eszközleltár ellenőrzésével felügyelheti, és távoli eszközműveleteket is végrehajthat.                                                      |
| [Mobilalkalmazások](app-management.md)                             | Információ az alkalmazások hozzáadásáról, üzembe helyezéséről, figyeléséről, konfigurálásáról és védelméről.                                                                                                                                                                                                                             |
| [Feltételes hozzáférés](conditional-access.md)                  | A céges adatok védelmét szolgáló eszközalapú és alkalmazásalapú feltételeket határozhat meg.                                                                                                                                                                                                            |
| [Felhasználók](users-add.md)                                        | Információ arról, hogyan adhat hozzá felhasználókat a felügyelt eszközökhöz és alkalmazásokhoz.                                                                                                                                                                                                                                           |
| [Csoportok](groups-get-started.md)                              | Információ arról, hogyan hozhatók létre és hogyan kezelhetők csoportok az Intune-ban. A csoportok használatával gyorsan hozzárendelhet eszköz- és alkalmazáskonfigurációs védelmi szabályzatokat.                                                                                                                                             |
| [Intune-szerepkörök](role-based-access-control.md)                 | Szabályozhatja, hogy kik hajthatnak végre különböző műveleteket az Intune-ban, és hogyan lesznek alkalmazva ezek a műveletek. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.                                                                                 |
| [Szoftverfrissítések](windows-update-for-business-configure.md) | Információ arról, hogyan konfigurálhatja a szoftverfrissítéseket Windows 10-es eszközök esetén.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Újdonságok

A Microsoft Intune legújabb funkcióiról az [Újdonságok](whats-new.md) témakörben olvashat.

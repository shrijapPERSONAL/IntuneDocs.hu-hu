---
title: "Eszközök távoli felügyelete a Microsoft Intune-ban – Azure | Microsoft Docs"
description: "Áttekintés a TeamViewer használatához szükséges szerepkörökről, és a TeamViewer-összekötő telepítéséről, valamint lépésenkénti útmutató eszközök távoli felügyeletéhez a Microsoft Intune használatával az Azure Portalon"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 64f6dd6bf787a6f590655f03ac8f04312836e0b5
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>A TeamViewer használata Intune-eszközök távoli felügyeletéhez

Az Intune által kezelt eszközök a [TeamViewer](https://www.teamviewer.com) használatával felügyelhetők távolról. A TeamViewer külső szállítótól származó, külön megvásárolható program. Ez a témakör bemutatja, hogyan konfigurálható a TeamViewer az Intune-ban, és hogyan felügyelhető távolról egy eszköz. 

## <a name="prerequisites"></a>Előfeltételek

- Használjon támogatott eszközt. Az Intune-nal felügyelt Android- és Windows-eszközök támogatják a távfelügyeletet. A TeamViewer nem feltétlenül támogatja a Windows Holographic (HoloLens), Windows Team (Surface Hub), vagy Windows 10 S rendszerű eszközöket. A támogatással kapcsolatban tekintse át a [TeamViewer](https://www.teamviewer.com) frissítéseit.

- Az Azure Portal-beli Intune rendszergazdának a következő [Intune-szerepkörökkel](role-based-access-control.md) kell rendelkeznie:  

    - **Távoli segítségnyújtás frissítése**: Lehetővé teszi, hogy a rendszergazda módosítsa a TeamViewer-összekötő beállításait.
    - **Távoli segítségnyújtás kérése**: Lehetővé teszi, hogy a rendszergazda új távsegítség munkamenetet indítson bármely felhasználó számára. Az ezzel a szerepkörrel rendelkező felhasználókat nem korlátozzák a hatókörön belüli Intune-szerepkörök. A hatókörön belüli Intune-szerepkörhöz rendelt felhasználói vagy eszközcsoportok szintén kérhetnek távsegítséget. 

- [TeamViewer](https://www.teamviewer.com)-fiók a bejelentkezéshez szükséges hitelesítő adatokkal

A TeamViewer használatával engedélyezi a TeamViewer for Intune összekötőjének TeamViewer-munkamenetek létrehozását, Active Directory-adatok olvasását és a TeamViewer-fiók hozzáférési jogkivonatának mentéset.

## <a name="configure-the-teamviewer-connector"></a>A TeamViewer-összekötő konfigurálása

Ahhoz, hogy távsegítséget nyújthasson eszközökre, az alábbi lépéseket követve konfigurálja az Intune TeamViewer-összekötőt:

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, majd keresse meg a **Microsoft Intune** elemet.
2. A **Microsoft Intune** alatt válassza az **Eszközök**, majd a **TeamViewer-összekötő** elemet.
3. Válassza a **Kapcsolódás** lehetőséget, és fogadja el a licencszerződést.
4. Válassza **Az engedélyezéshez jelentkezzen be a TeamViewer szolgáltatásba** lehetőséget.
5. Ekkor megnyílik a TeamViewer webhelyének egyik oldala. A TeamViewer-licenc hitelesítő adatainak megadását követően válassza a **Bejelentkezés** lehetőséget.

## <a name="remotely-administer-a-device"></a>Eszközök távoli felügyelete

Az összekötő konfigurálása után megkezdheti egy eszköz távoli felügyeletét. Hajtsa végre a következő lépéseket: 

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, majd keresse meg a **Microsoft Intune** elemet.
2. A **Microsoft Intune** alatt válassza az **Eszközök**, majd a **Minden eszköz** elemet.
3. Jelölje ki a listában a távolról felügyelni kívánt eszközt. Az eszköz tulajdonságainál válassza az **Új távsegítség munkamenet** lehetőséget.
4. Miután az Intune kapcsolódott a TeamViewer szolgáltatáshoz, látni fog némi információt az eszközről. A **Kapcsolódás** lehetőséggel indítsa el a távoli munkamenetet.

![Androidos eszköz távoli felügyelet a TeamViewer használatával – példa](./media/android-teamviewer.png)

Távoli munkamenet indításakor a végfelhasználó egy értesítésjelzőt lát az eszközén található céges portál alkalmazás ikonján. Egy értesítés is megjelenik az alkalmazás megnyitásakor. A felhasználó ekkor elfogadhatja a kezdeményezett távsegítséget.

A TeamViewerben sokféle művelet, például az eszköz felügyeletének átvétele is végrehajtható az eszközön. Az elvégezhető tevékenységek teljes körű ismertetését a [TeamViewer útmutató](https://www.teamviewer.com/support/documents/) tartalmazza.

Ha végzett, zárja be a TeamViewer ablakot.
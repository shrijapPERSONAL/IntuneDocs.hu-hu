---
title: macOS eszközfunkció-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a macOS-eszközök konfigurálása a Microsoft Intune AirPrint a beállításokat. A lépéseket a a hálózaton az IP-cím, elérési útja és portbeállítások az AirPrint-kiszolgáló is megtekintheti. Az eszközkonfigurációs profil ezek a beállítások segítségével konfigurálhatja a macOS-eszközök a hálózaton lévő AirPrint-kiszolgálók használatára.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0707226412d314ac1d44ba339b4c9151b394919
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233899"
---
# <a name="macos-device-feature-settings-in-intune"></a>macOS eszközfunkció-beállítások az Intune-ban

Az Intune tartalmaz néhány beépített beállítások macOS-felhasználók számára a hálózaton lévő AirPrint nyomtatókra való nyomtatás engedélyezése. Ez a cikk ezeket a beállításokat, és ismerteti az egyes beállítások funkciója. Azt is megjeleníti a lépéseket a az IP-cím, elérési útja és a terminál alkalmazással (emulátor) port az AirPrint-nyomtatókhoz.

## <a name="before-you-begin"></a>Előkészületek

[A macOS-eszközkonfigurációs profil létrehozása](device-features-configure.md).

## <a name="airprint-settings"></a>AirPrint-beállítások

1. A **beállítások**válassza **AirPrint**. Adja meg a következő tulajdonságokat az AirPrint-kiszolgáló:

    - **IP-cím**: Adja meg a nyomtató IPv4 vagy IPv6-címét. Ha állomásnevek nyomtatók azonosítására használ, a nyomtató a terminál alkalmazásban történő megpingelésével beszerezheti az IP-címet. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
    - **Elérési út**: Adja meg a nyomtató elérési útját. Az elérési út általában `ipp/print` nyomtatók a hálózaton. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
    - **Port**: Adja meg az AirPrint-célhely figyelőportja. Ha üresen hagyja ezt a tulajdonságot, az AirPrint az alapértelmezett portot használ. Az iOS 11.0-s vagy újabb érhető el.
    - **TLS**: Válasszon **engedélyezése** AirPrint-kapcsolatok a Transport Layer Security (TLS) biztonságos. Az iOS 11.0-s vagy újabb érhető el.

2. Válassza a **Hozzáadás** lehetőséget. Az AirPrint-kiszolgáló hozzáadásakor a listához. Számos AirPrint-kiszolgálókat is hozzáadhat.

    Emellett **importálás** egy vesszővel tagolt fájlt (.csv), amely tartalmazza az AirPrint-nyomtatókra listáját. Miután hozzáadta az AirPrint-nyomtatókra az Intune-ban, azt is megtehetjük, **exportálása** ebben a listában.

3. Amikor végzett, válassza ki a **OK** mentheti a listát.

## <a name="get-the-ip-address-and-path"></a>Az IP-cím és az elérési út

Az IP-címét a nyomtatót, az erőforrás elérési útja és a portot kell AirPrinter-kiszolgálók hozzáadásához. A következő lépések bemutatják, hogyan beolvasni ezeket az információkat.

1. Az azonos helyi hálózatra (alhálózatra), az AirPrint-nyomtatókra csatlakoztatott Mac számítógépen nyissa meg a **terminálon** (a **/Applications/Utilities**).
2. A Terminálszolgáltatások alkalmazásban írjon be `ippfind`, és válassza ki, adja meg.

    Megjegyzés: a nyomtató-információkat. Például előfordulhat, hogy vissza valami hasonló `ipp://myprinter.local.:631/ipp/port1`. Az első része a nyomtató neve. A második (`ipp/port1`) az erőforrás elérési útja.

3. A Terminalba írja be a `ping myprinter.local`, és válassza ki, adja meg.

   Megjegyzés: az IP-címet. Például előfordulhat, hogy vissza valami hasonló `PING myprinter.local (10.50.25.21)`.

4. IP-cím és az erőforrás elérési útja értéket használja. Ebben a példában az IP-cím van `10.50.25.21`, és az erőforrás-elérési út `/ipp/port1`.

## <a name="next-steps"></a>További lépések

- A megadott beállítások megjelenítéséhez [iOS](ios-device-features-settings.md) eszközök.
- Ez a profil hozzárendelése a csoportokhoz; Lásd: [eszközprofilok hozzárendelése](device-profile-assign.md).

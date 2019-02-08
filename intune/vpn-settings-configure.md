---
title: VPN-eszközprofil létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Tekintse meg az iOS-eszközökhöz használható VPN-kapcsolati típusokat, hozzon létre VPN-eszközprofilt az Azure Portalon, és tudja meg, hogyan tudja megvédeni a VPN-profilt tanúsítványokkal vagy felhasználónévvel és jelszóval a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2d0bde56c6622648d47fe47458bdac62d7843ca
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838461"
---
# <a name="create-vpn-profiles-in-intune"></a>VPN-profilok létrehozása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. A Microsoft Intune **VPN-profiljainak** használatával a VPN-beállításokat a szervezet felhasználóihoz és eszközeihez rendelheti hozzá, így könnyen és biztonságosan kapcsolódhatnak a hálózathoz.

Tegyük fel például, hogy minden iOS-eszközön alkalmazni szeretné azokat a beállításokat, amelyek a vállalati hálózaton lévő egyik fájlmegosztáshoz való csatlakozáshoz szükségesek. Létrehoz egy VPN-profilt, mely tartalmazza a vállalati hálózathoz való csatlakozáshoz szükséges beállításokat. Ezután hozzárendeli ezt a profilt az iOS-eszközzel rendelkező összes felhasználóhoz. A felhasználók látni fogják a VPN-kapcsolatot a rendelkezésre álló hálózatok listájában, és könnyen csatlakozhatnak.

Egyéni Intune-konfigurációs szabályzatokkal VPN-profilok hozhatók létre a következő platformokon:

* Android 4 és újabb verziók
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* Windows Phone 8.1 és újabb verziók
* A Windows 10 asztali verzióját futtató regisztrált eszközök
* Windows 10 mobil verzió
* Windows Holographic for Business

## <a name="vpn-connection-types"></a>VPN-kapcsolat típusai

A következő kapcsolattípusokkal hozhat létre VPN-profilt:

|Kapcsolat típusa|Android<br>Androidos munkahelyi profilok|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Automatikus|Nem|Nem|Nem|Nem|Nem|Igen|
|Check Point Capsule VPN|Igen|Igen|Igen|Igen|Igen|Igen|
|Cisco AnyConnect|Igen|Igen|Igen|Nem|Nem|Nem|
|SonicWall Mobile Connect|Igen|Igen|Igen|Igen|Igen|Igen|
|F5 Edge Client|Igen|Igen|Igen|Igen|Igen|Igen|
|Palo Alto Hálózatok GlobalProtect|Nem|Igen|Nem|Nem|Nem|Igen|
|Pulse Secure|Igen|Igen|Igen|Igen|Igen|Igen|
|Cisco (IPSec)|Nem|Igen|Nem|Nem|Nem|Nem|
|Citrix|Igen (csak Android esetén)|Igen|Nem|Nem|Nem|Igen|
|IKEv2|Nem|Nem|Nem|Nem|Nem|Igen|
|L2TP|Nem|Nem|Nem|Nem|Nem|Igen|
|PPTP|Nem|Nem|Nem|Nem|Nem|Igen|
|Zscaler|Nem|Igen|Nem|Nem|Nem|Nem|
|Egyéni VPN|Nem|Igen|Igen|Nem|Nem|Nem|

> [!IMPORTANT]
> Az eszközökre alkalmazott VPN-profilok használatához telepíteni kell a megfelelő VPN-alkalmazást a profilhoz. Az alkalmazás Intune-nal történő hozzárendeléséhez [A Microsoft Intune-alkalmazásfelügyelet ismertetése](app-management.md) című témakörben talál segítséget.  

Az [Egyéni beállításokkal rendelkező profil létrehozása](custom-settings-configure.md) című témakörből tájékozódhat arról, hogy hogyan hozhat létre egyéni VPN-profilokat URI-beállításokkal.

## <a name="create-a-device-profile-containing-vpn-settings"></a>A VPN-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
4. Adja meg a VPN-profil nevét és leírását a **Név** és a **Leírás** mezőben.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a VPN-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet VPN-eszközbeállításokat megadni:
   - **Android**
   - **Vállalati Android**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 és újabb**
   - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **VPN** lehetőséget.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
   - [Androidos és androidos munkahelyi profil beállításai](vpn-settings-android.md)
   - [iOS-beállítások](vpn-settings-ios.md)
   - [macOS-beállítások](vpn-settings-macos.md)
   - [Windows Phone 8.1-beállítások](vpn-settings-windows-phone-8-1.md)
   - [Windows 8.1-beállítások](vpn-settings-windows-8-1.md)
   - [Windows 10-beállítások](vpn-settings-windows-10.md) (beleértve a Windows Holographic for Businesst is)
8. Ha végzett, hozza létre a profilt a **Létrehozás** lehetőség választásával.

Ekkor létrejön a profil, és megjelenik a profilok listájában. Ha csoportokhoz szeretné hozzárendelni a profilt, tekintse meg az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikket.

## <a name="methods-of-securing-vpn-profiles"></a>A VPN-profilok védelmének biztosítása

A VPN-profilok számos különböző kapcsolattípust és különféle gyártóktól származó protokollt használhatnak. Az ilyen kapcsolatok védelmét általában az alábbi két módszer egyikével biztosítják.

### <a name="certificates"></a>Tanúsítványok

A VPN-profil létrehozásakor ki kell választania egy SCEP-vagy PKCS-tanúsítványprofilt, amelyet korábban az Intune-ban hozott létre. Ez a profil identitástanúsítványként is ismert. Ennek segítségével hajtja végre a rendszer a hitelesítést egy olyan megbízható tanúsítványprofillal (vagy *főtanúsítvánnyal*), amelyet Ön a felhasználói eszköz csatlakozásának engedélyezéséhez hozott létre. A megbízható tanúsítványt a rendszer a VPN-kapcsolatot hitelesítő számítógépre alkalmazza, amely általában a VPN-kiszolgáló.

A tanúsítványprofiloknak az Intune-ban történő létrehozásáról és használatáról a következő dokumentumban olvashat bővebben: [Tanúsítványok konfigurálása a Microsoft Intune-nal](certificates-configure.md).

### <a name="user-name-and-password"></a>Felhasználónév és jelszó

A felhasználó a VPN-kiszolgálón felhasználónév és jelszó megadásával végzi el a hitelesítést.

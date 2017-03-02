---
title: "Az Intune VPN-beállításainak konfigurálása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Ez a témakör azt ismerteti, hogyan lehet az Intune-nal VPN-kapcsolatokat konfigurálni a felügyelt eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: ff05d9ed7bae2742de8dbbe908f2c92d2459a7f4
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>A VPN-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. A Microsoft Intune **VPN-profiljainak** beállításával a szervezet felhasználóira és eszközeire alkalmazhatja a VPN-beállításokat, így könnyedén és biztonságosan kapcsolódhatnak a hálózathoz.

Tegyük fel például, hogy minden iOS-eszközön alkalmazni szeretné azokat a beállításokat, amelyek a vállalati hálózaton lévő egyik fájlmegosztáshoz való csatlakozáshoz szükségesek. Ehhez létre kell hoznia egy, a vállalati hálózathoz való csatlakozáshoz szükséges beállításokat tartalmazó VPN-profilt, majd ezt a profilt minden iOS-eszközt használó felhasználónak ki kell osztania. A felhasználók látni fogják a VPN-kapcsolatot a rendelkezésre álló hálózatok listájában, és könnyen csatlakozhatnak.

## <a name="vpn-connection-types"></a>VPN-kapcsolat típusai

A következő kapcsolattípusokkal hozhat létre VPN-profilt:

|||
|-|-|
|Kapcsolat típusa|Android|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|Pulse Secure|Igen|Igen|Igen|Igen|Igen|Igen|
|Cisco (IPSec)|Nem|Igen|Nem|Nem|Nem|Nem|
|Citrix|Igen|Igen|Nem|Nem|Nem|Nem|
|F5 Edge Client|Igen|Igen|Igen|Igen|Igen|Igen|
|Dell SonicWALL Mobile Connect|Igen|Igen|Igen|Igen|Igen|Igen|
|Check Point Capsule VPN|Igen|Igen|Igen|Igen|Igen|Igen|
|Cisco AnyConnect|Igen|Igen|Igen|Nem|Nem|Nem|
|Automatikus|Nem|Nem|Nem|Nem|Nem|Igen|
|IKEv2|Nem|Nem|Nem|Nem|Nem|Igen|
|L2TP|Nem|Nem|Nem|Nem|Nem|Igen|
|PPTP|Nem|Nem|Nem|Nem|Nem|Igen|
|Egyéni|Nem|Igen|Igen|Nem|Nem|Nem|


> [!IMPORTANT]
> Az eszközökre alkalmazott VPN-profilok használatához telepítenie kell a megfelelő VPN-alkalmazást a profilhoz. Az alkalmazás Intune-os telepítéséhez a következő dokumentumban talál segítséget: [Alkalmazásfelügyelet a Microsoft Intune-ban](/intune-azure/manage-apps/what-is-app-management).  

Az [Egyéni VPN-profilok létrehozása](create-custom-vpn-profiles.md) című témakörből tájékozódhat arról, hogy hogyan hozhat létre egyéni VPN-profilokat URI-beállításokkal.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>A VPN-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen töltse ki az egyéni VPN-profil **Név** és **Leírás** mezőjét.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a VPN-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet VPN-eszközbeállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **VPN** lehetőséget.
7. A választott platformtól függően a konfigurálható beállítások eltérőek lehetnek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](vpn-for-android.md)
    - [iOS-beállítások](vpn-for-ios.md)
    - [macOS-beállítások](vpn-for-macos.md)
    - [Windows Phone 8.1-beállítások](vpn-for-windows-phone-8-1.md)
    - [Windows 8.1-beállítások](vpn-for-windows-8-1.md)
    - [Windows 10-beállítások](vpn-for-windows-10.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha a profilt csoportokhoz szeretné hozzárendelni, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.


## <a name="methods-of-securing-vpn-profiles"></a>A VPN-profilok védelmének biztosítása

A VPN-profilok számos különböző kapcsolattípust és különféle gyártóktól származó protokollt használhatnak. Az ilyen kapcsolatok védelmét általában az alábbi két módszer egyikével biztosítják.

### <a name="certificates"></a>Tanúsítványok

A VPN-profil létrehozásakor ki kell választania egy SCEP-vagy PKCS-tanúsítványprofilt, amelyet korábban az Intune-ban hozott létre. Ez identitástanúsítványként is ismert, és ennek segítségével hajtja végre a rendszer a hitelesítést egy olyan megbízható tanúsítványprofillal (vagy *főtanúsítvánnyal*), amelyet Ön a felhasználó eszközének a csatlakoztatásához hozott létre. A megbízható tanúsítványt a rendszer a VPN-kapcsolatot hitelesítő számítógépre alkalmazza, amely általában a VPN-kiszolgáló.

A tanúsítványprofiloknak az Intune-ban történő létrehozásáról és használatáról a következő dokumentumban olvashat bővebben: [Tanúsítványok konfigurálása a Microsoft Intune-nal](how-to-configure-certificates.md).

### <a name="user-name-and-password"></a>Felhasználónév és jelszó

A felhasználó a VPN-kiszolgálón felhasználónév és jelszó megadásával végzi el a hitelesítést.


---
title: "Alkalmazásonkénti VPN-profil az Android Pulse Secure használatával"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Útmutató az alkalmazásonkénti VPN-profilok létrehozásához az Intune által felügyelt Android-eszközök számára."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 2c79f5f796152e930c4a952388541383ab50e595
ms.lasthandoff: 03/17/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Alkalmazásonkénti VPN-profil létrehozása androidos eszközökhöz egyéni Microsoft Intune-profillal

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune által felügyelt Android 5.0-s és újabb rendszerű eszközökhöz alkalmazásonkénti VPN-profilt hozhat létre. Először hozzon létre egy olyan profit, amely a Pulse Secure kapcsolattípust használja. Ezután hozzon létre egy olyan egyéni szabályzatot, amely a VPN-profilt meghatározott alkalmazásokkal társítja.

Miután telepíti a házirendet az Android rendszerű eszközön vagy felhasználói csoportokon, a felhasználóknak el kell indítaniuk a PulseSecure VPN-t. A PulseSecure ezután csak a megadott alkalmazások adatforgalma számára engedélyezi a nyitott VPN-kapcsolat használatát.

> [!NOTE]
>
> Ez a profil csak a Pulse Secure kapcsolattípust támogatja.


## <a name="step-1-create-a-vpn-profile"></a>1. lépés: VPN-profil létrehozása


1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
2. A profilok listáját mutató panelen válassza a **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen írja be a VPN-profilra vonatkozó **Név** és **Leírás** (nem kötelező) szövegét.
4. A **Platform** legördülő listájában válassza az **Android** lehetőséget.
5. A **Profil típusa** legördülő listában válassza a **VPN** lehetőséget.
3. Válassza a **Beállítások** > **Konfigurálás** lehetőséget, majd konfigurálja a VPN-profilt a [VPN-beállítások konfigurálása](how-to-configure-vpn-settings.md) és az [Intune VPN-beállítások androidos eszközökhöz](vpn-for-android.md) részekben ismertetett beállítások alapján.

Jegyezze fel a VPN-profil nevét a következő lépéshez. Például: **AlkVpnProfil**.

## <a name="step-2-create-a-custom-configuration-policy"></a>2. lépés: Egyéni konfigurációs szabályzat létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok panelen katttintson a **Profil létrehozása** lehetőségre.
4. A **Profil létrehozása** panelen írja be az egyéni profilra vonatkozó **Név** és **Leírás** szövegét.
5. A **Platform** legördülő listájában válassza az **Android** lehetőséget.
6. A **Profil típusa** legördülő listában válassza az **Egyéni** lehetőséget.
7. Válassza a **Beállítások** > **Konfigurálás** lehetőséget.
3. Az **Egyéni OMA-URI beállítások** panelen válassza a **Hozzáadás** lehetőséget.
    - Adja meg a beállítás nevét.
    - Az **Adattípus** mezőben válassza a **Karakterlánc** lehetőséget.
    - Az **OMA-URI** mezőbe írja be a következő karakterláncot: **./Vendor/MSFT/VPN/Profile/*Név*/PackageList**, ahol a*Név* az 1. lépésben feljegyzett VPN-profil neve. A jelen példában a karakterlánc a következő lenne: **./Vendor/MSFT/VPN/Profile/AlkVpnProfil/PackageList**.
    - Az **Érték** területen adja meg azoknak a csomagoknak a pontosvesszővel tagolt listáját, amelyeket a profilhoz társít. Ha például azt szeretné, hogy az Excel és a Google Chrome böngésző VPN-kapcsolatot használjon, írja be a következőt: **com.microsoft.office.excel;com.android.chrome**.

![Példa Android rendszerű, alkalmazásonkénti VPN-hez létrehozott egyéni szabályzatra](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Az alkalmazáslista Blacklist (Letiltott) vagy Whitelist (Engedélyezett) értékre állítása (nem kötelező)
  A **BLACKLIST** (LETILTOTT) érték kiválasztásával megadhatja azoknak az alkalmazásoknak a listáját, amelyek *nem* használhatják a VPN-kapcsolatot. Minden más alkalmazás VPN-kapcsolaton keresztül fog csatlakozni az internethez.
Másik megoldásként használhatja a **WHITELIST** (ENGEDÉLYEZETT) értéket, és megadhatja azon alkalmazások listáját, amelyek *használhatják* a VPN-kapcsolatot. A listán nem szereplő alkalmazások nem csatlakozhatnak az internethez a VPN-kapcsolaton keresztül.
  1.    Az **Egyéni OMA-URI beállítások** panelen válassza a **Hozzáadás** lehetőséget.
  2.    Adja meg a beállítás nevét.
  3.    Az **Adattípus** mezőben válassza a **Karakterlánc** lehetőséget.
  4.    Az **OMA-URI** mezőbe írja be a következő karakterláncot: **./Vendor/MSFT/VPN/Profile/*Név*/Mode**, ahol a*Név* az 1. lépésben feljegyzett VPN-profil neve. A fenti példában a karakterlánc a következő lenne: **./Vendor/MSFT/VPN/Profile/AlkVpnProfil/Mode**.
  5.    Az **Érték** mezőbe írja be a **BLACKLIST** (LETILTOTT) vagy a **WHITELIST** (ENGEDÉLYEZETT) értéket.



## <a name="step-3-assign-both-policies"></a>3. lépés: Mindkét szabályzat hozzárendelése

Használja a következő témakör utasításait mindkét profil hozzárendelésére a szükséges felhasználókhoz vagy eszközökhöz: [Eszközprofilok hozzárendelése](how-to-assign-device-profiles.md).


---
title: Wi-Fi-beállítások konfigurálása az Intune-ban
titleSuffix: Microsoft Intune
description: Útmutató arról, hogyan konfigurálhatóak a Wi-Fi-kapcsolatok felügyelt eszközökön a Microsoft Intune-nal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: df2e2f81008c6dedf5660a8a9eff4bf2cfe2ec6b
ms.sourcegitcommit: 77540295381a59918eb638ce9c1870209cf8af02
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46505733"
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>A Wi-Fi-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune Wi-Fi-profiljaival a vezeték nélküli hálózati beállításokat a szervezet felhasználóihoz és eszközeihez rendelheti hozzá. Wi-Fi-profil hozzárendelése esetén a felhasználók anélkül csatlakozhatnak a vállalati Wi-Fi hálózathoz, hogy azt maguknak kellene konfigurálniuk.

Tegyük fel például, hogy egy új, Contoso Wi-Fi nevű vezeték nélküli hálózatot helyezett üzembe, és szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1. Hozza létre a Contoso Wi-Fi vezeték nélküli hálózathoz való csatlakozás beállításait tartalmazó Wi-Fi profilt.
2. Rendelje hozzá a profilt az iOS-eszközök összes felhasználóját tartalmazó csoporthoz.
3. A felhasználók eszközeiken megtalálják az új Contoso Wi-Fi hálózatot a vezeték nélküli hálózatok között, és könnyedén csatlakozhatnak hozzá.

## <a name="supported-device-platforms"></a>Támogatott eszközplatformok

A Wi-Fi-profilok a következő eszközplatformokat támogatják:

- Android 4 és újabb verziók
- Androidos munkahelyi profilok
- iOS 8.0 és újabb verziók
- macOS (a Mac OS X 10.11-es vagy újabb verziója)

Windows 8.1, Windows 10, Windows 10 Mobile és Windows Holographic for Business rendszerű eszközök esetén importálhatja egy másik eszköz korábban exportált Wi-Fi-konfigurációját.

A témakörben található információk alapján megismerheti a Wi-Fi-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>A Wi-Fi-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panel **Kezelés** területén válassza a **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni Wi-Fi-profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a Wi-Fi-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet Wi-Fi-beállításokat megadni:
    - **Android**
    - **Vállalati Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**


6. Apple vagy Android rendszerű eszközök esetén a **Wi-Fi típusa** legördülő listában válassza az **Alapszintű** vagy **Vállalati** lehetőséget. Ha alapvető jellemzőket, például a hálózat nevét és SSID azonosítóját szeretné megadni, használhatja az **Alapszintű** lehetőséget. A **Vállalati** lehetőséggel több speciális adatot adhat meg, mint például az EAP protokoll használatát, ha a Wi-Fi-hálózata ezt a protokollt használja. 

   A **Wi-Fi-importálás** profil (Windows 8.1 és újabb esetén) lehetővé teszi, hogy egy másik eszközön XML-fájlba exportált Wi-Fi-beállításokat importálhasson.
1. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Androidos és androidos munkahelyi profil beállításai](wi-fi-settings-android.md)
    - [iOS-beállítások](wi-fi-settings-ios.md)
    - [macOS-beállítások](wi-fi-settings-macos.md)
    - [Windows 8.1 és újabb beállításai](wi-fi-settings-import-windows-8-1.md) (beleértve a Windows Holographic for Businesst is)
1. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="next-steps"></a>További lépések

Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.

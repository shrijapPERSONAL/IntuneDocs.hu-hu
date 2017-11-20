---
title: "Wi-Fi-beállítások konfigurálása az Intune-ban"
titleSuffix: Azure portal
description: "Útmutató arról, hogyan konfigurálhatóak a Wi-Fi-kapcsolatok felügyelt eszközökön az Intune-nal.”"
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3333a5addfd0c4ab757121e22e19ac66c0b3e1d
ms.sourcegitcommit: ec8561b8c63515e0b5f21a858984108dc5dbd5d3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>A Wi-Fi-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune Wi-Fi-profiljaival a vezeték nélküli hálózati beállításokat a szervezet felhasználóihoz és eszközeihez rendelheti hozzá. Wi-Fi-profil hozzárendelése esetén a felhasználók anélkül csatlakozhatnak a vállalati Wi-Fi hálózathoz, hogy azt maguknak kellene konfigurálniuk.

Tegyük fel például, hogy egy új, Contoso Wi-Fi nevű vezeték nélküli hálózatot helyezett üzembe, és szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1. Hozza létre a Contoso Wi-Fi vezeték nélküli hálózathoz való csatlakozás beállításait tartalmazó Wi-Fi profilt.
2. Rendelje hozzá a profilt az iOS-eszközök összes felhasználóját tartalmazó csoporthoz.
3. A felhasználók eszközeiken megtalálják az új Contoso Wi-Fi hálózatot a vezeték nélküli hálózatok között, és könnyedén csatlakozhatnak hozzá.

A Wi-Fi-profilok a következő eszközplatformokat támogatják:

- Android 4 és újabb verziók
- Android for Work
- iOS 8.0 és újabb verziók
- macOS (a Mac OS X 10.9-es vagy újabb verziója)

Windows 8.1, Windows 10 és Windows 10 Mobile rendszerű eszközök esetén importálhatja egy másik eszköz korábban exportált Wi-Fi-konfigurációját.

A témakörben található információk alapján megismerheti a Wi-Fi-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>A Wi-Fi-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok panelen válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni Wi-Fi-profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a Wi-Fi-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet Wi-Fi-beállításokat megadni:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows 8.1 és újabb (profil importálása)**
6. A **Profil típusa** legördülő listában válassza az **Alap Wi-Fi** vagy a **Vállalati Wi-Fi** lehetőséget.
    >[!TIP]
    >Ha alapvető jellemzőket, például a hálózat nevét és SSID azonosítóját szeretné megadni, használja az **Alap Wi-Fi** lehetőséget. A **Vállalati Wi-Fi** lehetőséggel több speciális adatot adhat meg, mint például az EAP protokoll használatát, ha a Wi-Fi-hálózata ezt használja. A **Wi-Fi-importálás** (Windows 8.1 és Windows 10 esetén) lehetővé teszi, hogy egy másik eszközön XML-fájlba exportált Wi-Fi-beállításokat importálhasson.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Az Android és az Android for Work beállításai](wi-fi-settings-android.md)
    - [iOS-beállítások](wi-fi-settings-ios.md)
    - [macOS-beállítások](wi-fi-settings-macos.md)
    - [Windows Phone 8.1-beállítások](wi-fi-settings-import-windows-8-1.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha szeretné a profil csoportokhoz való hozzárendelésével folytatni, erről a [How to assign device profiles](device-profile-assign.md) (Eszközprofilok hozzárendelése) című témakörben olvashat.

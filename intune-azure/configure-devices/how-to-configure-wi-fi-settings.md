---
title: "Az Intune Wi-Fi-beállításainak konfigurálása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: További információ arról, hogyan használható az Intune a Wi-Fi-kapcsolatoknak a felügyelt eszközökön való konfigurálásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: f91d919a72b7d14353250d2de532ab083a62c210


---

# <a name="how-to-configure-wi-fi-settings"></a>A Wi-Fi-beállítások konfigurálása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune Wi-Fi profiljaival vezeték nélküli hálózati beállításokat adhat meg a szervezet felhasználói és eszközei számára. Wi-Fi profil központi telepítése esetén a felhasználók anélkül csatlakozhatnak a vállalati Wi-Fi hálózathoz, hogy azt maguknak kellene konfigurálniuk.

Tegyük fel például, hogy egy új, Contoso Wi-Fi nevű vezeték nélküli hálózatot helyezett üzembe, és szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1. Hozza létre a Contoso Wi-Fi vezeték nélküli hálózathoz való csatlakozás beállításait tartalmazó Wi-Fi profilt.
2. Rendelje hozzá a profilt az iOS-eszközök összes felhasználóját tartalmazó csoporthoz.
3. A felhasználók eszközeiken megtalálják az új Contoso Wi-Fi hálózatot a vezeték nélküli hálózatok között, és könnyedén csatlakozhatnak hozzá.

A Wi-Fi-profilok a következő eszközplatformokat támogatják:

- Android 4 és újabb verziók
- iOS 8.0 és újabb verziók
- macOS (a Mac OS X 10.9-es vagy újabb verziója)

Windows 8.1, Windows 10 és Windows 10 Mobile rendszerű eszközök esetén importálhatja egy másik eszköz korábban exportált Wi-Fi-konfigurációját.

A témakörben található információk alapján megismerheti a Wi-Fi-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>A Wi-Fi-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok panelen válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni Wi-Fi-profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné a Wi-Fi-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet Wi-Fi-beállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows 8.1 és újabb (profil importálása)**
6. A **Profil típusa** legördülő listában válassza az **Alap Wi-Fi** vagy a **Vállalati Wi-Fi** lehetőséget.
    >[!TIP]
    >Ha alapvető jellemzőket, például a hálózat nevét és SSID azonosítóját szeretné megadni, használja az **Alap Wi-Fi** lehetőséget. A **Vállalati Wi-Fi** lehetőséggel több speciális adatot adhat meg, mint például az EAP protokoll használatát, ha a Wi-Fi-hálózata ezt használja. A **Wi-Fi-importálás** (Windows 8.1 és Windows 10 esetén) lehetővé teszi, hogy egy másik eszközön XML-fájlba exportált beállításokat importálhasson.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](wi-fi-for-android.md)
    - [iOS-beállítások](wi-fi-for-ios.md)
    - [macOS-beállítások](wi-fi-for-macos.md)
    - [Windows Phone 8.1-beállítások](wi-fi-import-for-windows-8-1.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.




<!--HONumber=Feb17_HO1-->


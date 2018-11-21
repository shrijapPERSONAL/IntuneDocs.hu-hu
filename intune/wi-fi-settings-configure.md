---
title: Wi-Fi-profil létrehozása az eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Itt láthatja a Wi-Fi eszközkonfigurációs profilok Microsoft Intune-ban való létrehozásának lépéseit. Az Android, Android Enterprise, Android kioszk, iOS, macOS, Windows 10 vagy újabb, és a Windows Holographic for Business rendszerekhez hoz létre profilokat. Ezekkel a profilokkal Wi-Fi-kapcsolatot hozhat létre tanúsítványok használatához, EAP-típus és hitelesítési módszer kiválasztásához, proxy engedélyezéséhez és egyebekhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a338cce6249cc7c5214a9d69a897cad3eaa09e93
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188398"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Wi-Fi-beállítások hozzáadása és használata az eszközökön a Microsoft Intune-ban

A Microsoft Intune Wi-Fi-profiljaival a vezeték nélküli hálózati beállításokat a szervezet felhasználóihoz és eszközeihez rendelheti hozzá. Wi-Fi-profil hozzárendelésekor a felhasználók konfigurálás nélkül férhetnek hozzá a vállalat Wi-Fi-hálózatához.

Tegyük fel például, hogy egy új, Contoso Wi-Fi nevű vezeték nélküli hálózatot helyez üzembe. Ekkor szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1. Hozza létre a Contoso Wi-Fi vezeték nélküli hálózathoz való csatlakozás beállításait tartalmazó Wi-Fi-profilt.
2. Rendelje hozzá a profilt az iOS-eszközök összes felhasználóját tartalmazó csoporthoz.
3. A felhasználók az eszközükön a vezeték nélküli hálózatok listájában találják az új Contoso Wi-Fi-hálózatot. Ezután az Ön által kiválasztott hitelesítési módszerrel csatlakozhatnak a hálózathoz.

A cikkben szereplő lépésekkel hozzon létre egy Wi-Fi-profilt. Ezután tekintse át a platformspecifikus beállításokat és a részleteket tartalmazó témaköröket.

## <a name="supported-device-platforms"></a>Támogatott eszközplatformok

A Wi-Fi-profilok a következő eszközplatformokat támogatják:

- Android 4 és újabb verziók
- Android Enterprise és kioszk
- iOS 8.0 és újabb verziók
- macOS (a Mac OS X 10.11-es vagy újabb verziója)
- Windows 10 vagy újabb, Windows 10 Mobile és Windows Holographic for Business

> [!NOTE]
> A Windows 8.1-et futtató eszközökön importálhatja egy másik eszköz korábban exportált Wi-Fi-konfigurációját.

## <a name="create-a-wi-fi-device-profile"></a>Wi-Fi-eszközprofil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** elemre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet. 
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a Wi-Fi profil **nevét** és **leírását**.
4. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni fogja a Wi-Fi-beállításokat. A választható lehetőségek:

    - **Android**
    - **Vállalati Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**

5. A **Profil típusa** területen válassza a **Wi-Fi** lehetőséget.

    - A kioszk üzemmódban futó **Android Enterprise** eszközökön a **Csak az eszköz tulajdonosa** > **Wi-Fi** lehetőséget választhatja.
    - A **Windows 8.1 és újabb** rendszereken a **Wi-Fi-importálás** lehetőséget választhatja. Ez lehetővé teszi, hogy XML-fájlként importálhasson egy másik eszközről korábban exportált Wi-Fi-beállításokat.

6. Egyes Wi-Fi-beállítások minden platformon eltérnek. Az adott platformhoz tartozó beállítások megtekintéséhez válasszon az alábbiak közül:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise és kioszk](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 és újabb](wi-fi-settings-windows.md)
    - [Windows 8.1 és újabb](wi-fi-settings-import-windows-8-1.md) (beleértve a Windows Holographic for Businesst is)

    A legtöbb platformhoz **alapszintű** és **vállalati** beállítások is tartoznak. Az **alapszintű** beállítások olyan jellemzőket takarnak, mint a hálózat neve és az SSID. A **vállalati** beállításokkal speciális információkat adhat meg, például az EAP-protokollt (Extensible Authentication Protocol).

7. Miután végzett a Wi-Fi-beállítások hozzáadásával, válassza a **Profil létrehozása** > **Létrehozás** elemet a konfigurációs profil hozzáadásához. Ekkor létrejön a profil, és megjelenik a profilok listájában (**Eszközkonfiguráció** > **Profilok**).

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

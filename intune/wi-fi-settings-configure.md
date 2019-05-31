---
title: Wi-Fi-profil létrehozása az eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Itt láthatja a Wi-Fi eszközkonfigurációs profilok Microsoft Intune-ban való létrehozásának lépéseit. Az Android, Android Enterprise, Androidos teljes képernyős, iOS, macOS, Windows 10 és újabb és Windows Holographic for Business profiljainak létrehozásához. Ezekkel a profilokkal Wi-Fi-kapcsolatot hozhat létre tanúsítványok használatához, EAP-típus és hitelesítési módszer kiválasztásához, proxy engedélyezéséhez és egyebekhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dc28a614514bf9b1a4987976cb057529b75a5fc
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412002"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Wi-Fi-beállítások hozzáadása és használata az eszközökön a Microsoft Intune-ban

Wi-Fi hálózat eléréséhez több mobileszközt által használt vezeték nélküli hálózat legyen. A Microsoft Intune tartalmazza a beépített Wi-Fi-beállítások, a szervezet felhasználóira és eszközeire is telepíthető. Ez a csoport beállításait "profilnak" nevezik, és más felhasználókhoz és csoportokhoz rendelhető. Kiosztás után a a felhasználók anélkül is hozzáférhetnek a vállalati Wi-Fi hálózaton konfigurálása magukat.

Tegyük fel például, hogy egy új, Contoso Wi-Fi nevű vezeték nélküli hálózatot helyez üzembe. Ekkor szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1. Hozzon létre egy Wi-Fi profilt, amely tartalmazza azokat a beállításokat, amelyek a Contoso Wi-Fi vezeték nélküli hálózathoz csatlakoznak.
2. Rendelje hozzá a profilt egy csoporthoz, amely tartalmazza az összes felhasználó az iOS-eszközök.
3. A felhasználók az eszközükön a vezeték nélküli hálózatok listájában találják az új Contoso Wi-Fi-hálózatot. Ezután az Ön által kiválasztott hitelesítési módszerrel csatlakozhatnak a hálózathoz.

Ez a cikk felsorolja a Wi-Fi-profil létrehozásához szükséges lépéseket. Is tartalmaz, amelyek ismertetik a különböző beállításokat az egyes platformokra vonatkozó hivatkozásokat.

## <a name="supported-device-platforms"></a>Támogatott eszközplatformok

A Wi-Fi-profilok a következő eszközplatformokat támogatják:

- Android 4 és újabb verziók
- Android Enterprise és kioszk
- iOS 8.0 és újabb verziók
- macOS (a Mac OS X 10.11-es vagy újabb verziója)
- Windows 10 vagy újabb, Windows 10 Mobile és Windows Holographic for Business

> [!NOTE]
> A Windows 8.1-et futtató eszközökön importálhatja egy másik eszköz korábban exportált Wi-Fi-konfigurációját.

## <a name="create-a-device-profile"></a>Eszközprofil létrehozása

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a Wi-Fi profil **nevét** és **leírását**.
4. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni fogja a Wi-Fi-beállításokat. A választható lehetőségek:

    - **Android**
    - **Vállalati Android**
    - **iOS**
    - **macOS**
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

A profil létrejön, de egyelőre nem csinál semmit. Ezután [hozzárendeli ezt a profilt](device-profile-assign.md) és [monitorozhatja az alkalmazás állapotát.](device-profile-monitor.md).

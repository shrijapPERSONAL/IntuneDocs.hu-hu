---
title: Wi-Fi-beállítások importálása Windows 8.1 és későbbi verziók esetén
titleSuffix: Microsoft Intune
description: Útmutató Wi-Fi-beállítások importálásához Windows rendszerből Intune-os Wi-Fi-profilba.
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
ms.openlocfilehash: 157416738e4607d5022f1c3c7ed8251a8e32fe3e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-beállítások importálása Windows 8.1 és újabb rendszerű eszközökhöz a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Windows 8.1, a Windows 10 operációs rendszer asztali vagy mobil verzióját vagy a Windows Holographic for Business verziót futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi beállítások exportálása windowsos eszközről

A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi profilt. A kulcsot egyszerű szöveges formátumban kell exportálnia a profil sikeres használatához.

A szükséges Wi-Fi-profillal már rendelkező Windows-számítógépen kövesse az alábbi lépéseket:

1. Hozzon létre egy helyi mappát az exportált W-Fi-profilokhoz, például a **c:\WiFi** mappát.
2. Nyisson meg egy parancssort rendszergazdaként.
3. Futtassa a `netsh wlan show profiles` parancsot, és jegyezze fel az exportálni kívánt profil nevét. Ebben a példában a profil neve: **WiFiName**.
4. Futtassa a `netsh wlan export profile name="ProfileName" folder=c:\Wifi` parancsot. Ezzel létrehozza a **Wi-Fi-WiFiName.xml** nevű Wi-Fi-profilfájlt a célmappában.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi-beállítások importálása az Intune-ba

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
4. Adja meg az eszközkorlátozási profil nevét és leírását a **Név** és a **Leírás** mezőben.

    > [!IMPORTANT]
    > - A névnek **meg kell egyeznie** a Wi-Fi-profil XML-fájljában található névattribútummal. Ellenkező esetben sikertelen lesz a művelet.
    > - Ha előmegosztott kulcsot tartalmazó Wi-Fi-profilt exportál, akkor **mindenképp** hozzá kell adnia a `key=clear` kapcsolót a parancshoz. Például írja be a következőt: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`.
    > - Az előmegosztott kulcsok Windows 10 rendszerben való használata szervizelési hiba megjelenéséhez vezet az Intune-ban. E hiba megjelenésekor a Wi-Fi-profilt a rendszer megfelelően hozzárendeli az eszközhöz, és a profil a várt módon fog működni.
    > - Az előmegosztott kulcsot tartalmazó Wi-Fi-profilok exportálásakor gondoskodjon a fájlok védelméről. A kulcs egyszerű szövegként szerepel, ezért az Ön felelőssége a kulcs védelme.

5. A **Platform** beállításnál válassza a **Windows 8.1 és újabb** lehetőséget.
6. A **Profil típusa** beállításnál válassza a **Wi-Fi importálás** lehetőséget.
7. Adja meg a következő beállításokat:
  - **Kapcsolat neve**: Adja meg a Wi-Fi-kapcsolat nevét. Ez a név jelenik meg a végfelhasználók számára elérhető Wi-Fi-hálózatok böngészése közben.
  - **Profil XML-fájlja**: Válassza a tallózás gombot, majd válassza ki azt az XML-fájlt, amely az Intune-ba importálni kívánt Wi-Fi profilbeállításokat tartalmazza.
  - **Fájl tartalma**: Megjeleníti a kiválasztott konfigurációs profil XML-kódját.
8. Amikor elkészült, válassza az **OK**, majd a **Létrehozás** gombot a profil létrehozásához.

Ekkor létrejön a profil, és megjelenik a profilok listájában.

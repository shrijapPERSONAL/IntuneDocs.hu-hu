---
title: "Wi-Fi-beállítások importálása Windows 8.1 és későbbi verziók esetén"
titleSuffix: Microsoft Intune
description: "Útmutató Wi-Fi-beállítások importálásához Windows rendszerből Intune-os Wi-Fi-profilba."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0113703cbdc58172edc9552146c7634aa1058e3b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-beállítások importálása Windows 8.1 és újabb rendszerű eszközökhöz a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Windows 8.1, a Windows 10 operációs rendszer asztali vagy mobil verzióját vagy a Windows Holographic for Business verziót futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi beállítások exportálása windowsos eszközről

A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi profilt. A szükséges Wi-Fi profillal már rendelkező Windows-számítógépen kövesse az alábbi eljárást.
1. Hozzon létre egy helyi mappát az exportált W-Fi-profilokhoz, például a **c:\WiFi** mappát.
1. Nyisson meg egy parancssort rendszergazdaként.
1. Futtassa a **netsh wlan show profiles** parancsot, és jegyezze fel az exportálni kívánt profil nevét. Ebben a példában a profil neve: **WiFiName**.
1. Futtassa a következő parancsot: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Ez a parancs egy **Wi-Fi-WiFiName.xml** nevű Wi-Fi-profilt hoz létre a célmappában.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi-beállítások importálása az Intune-ba

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** lapon válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok lapon kattintson a **Profil létrehozása** lehetőségre.
4. A **Profil létrehozása** lapon adjon meg egy **Nevet** és **Leírást** az eszközkorlátozási profilra vonatkozóan.

   > [!WARNING]
   > A névnek meg **kell** egyeznie a Wi-Fi-profil xml-fájlban az attribútumban található névvel, ellenkező esetben sikertelen lesz a művelet.

5. A **Platform** legördülő listájában válassza a **Windows 8.1 vagy újabb** lehetőséget.
6. A **Profil típusa** legördülő listában válassza a **Wi-Fi importálás** lehetőséget.
7. Az **Alap Wi-Fi** lapon adja meg a következő beállításokat:
    - **Kapcsolat neve** – adja meg a Wi-Fi-kapcsolat nevét. Ez a név jelenik meg a végfelhasználók számára elérhető Wi-Fi-hálózatok böngészése közben.
    - **Profil XML-fájlja** – A tallózás gombra kattintva válassza ki azt az XML-fájlt, amely az Intune-ba importálni kívánt Wi-Fi profilbeállításokat tartalmazza.
    - **Fájl tartalma** – Megjeleníti a kiválasztott konfigurációs profil XML-kódját.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** lapra, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó lapon.

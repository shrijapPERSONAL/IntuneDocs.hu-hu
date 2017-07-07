---
title: "Wi-Fi-beállítások importálása Windows 8.1 és későbbi verziók esetén"
titleSuffix: Intune on Azure
description: "Útmutató Wi-Fi-beállítások importálásához Windows rendszerből Intune-os Wi-Fi-profilba.”"
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4ef9bf6ed3f731afada55d2af71d56367f4638d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-beállítások importálása Windows 8.1 és újabb rendszerű eszközökhöz a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Windows 8.1, vagy a Windows 10 asztali vagy mobilverzióját futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi beállítások exportálása windowsos eszközről

A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi profilt. A szükséges Wi-Fi profillal már rendelkező Windows-számítógépen kövesse az alábbi eljárást.
1. Hozzon létre egy helyi mappát az exportált W-Fi-profilokhoz, például a **c:\WiFi** mappát.
1. Nyisson meg egy parancssort rendszergazdaként.
1. Futtassa a **netsh wlan show profiles** parancsot, és jegyezze fel az exportálni kívánt profil nevét. Ebben a példában a profil neve: **WiFiName**.
1. Futtassa a következő parancsot: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Ez a parancs egy **Wi-Fi-WiFiName.xml** nevű Wi-Fi-profilt hoz létre a célmappában.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi-beállítások importálása az Intune-ba

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok panelen katttintson a **Profil létrehozása** lehetőségre.
4. A **Profil létrehozása** panelen adjon meg egy **Nevet** és **Leírást** az eszközkorlátozási profilra vonatkozóan.
5. A **Platform** legördülő listájában válassza a **Windows 8.1 vagy újabb** lehetőséget.
6. A **Profil típusa** legördülő listában válassza a **Wi-Fi importálás** lehetőséget.
7. Az **Alap Wi-Fi** panelen adja meg a következőket:
    - **Kapcsolat neve** – adja meg a Wi-Fi-kapcsolat nevét. Ez a név fog megjelenni a végfelhasználók számára elérhető Wi-Fi-hálózatok böngészése közben.
    - **Profil XML-fájlja** – A tallózás gombra kattintva válassza ki azt az XML-fájlt, amely az Intune-ba importálni kívánt Wi-Fi profilbeállításokat tartalmazza.
    - **Fájl tartalma** – Megjeleníti a kiválasztott konfigurációs profil XML-kódját.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

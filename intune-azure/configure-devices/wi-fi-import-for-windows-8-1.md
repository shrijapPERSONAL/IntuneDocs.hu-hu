---
title: "Wi-Fi-beállítások importálása Windows 8.1 és későbbi verziók esetén"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Wi-Fi beállítások importálása Windows rendszerből Intune-os Wi-Fi-profilba."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b0157f1021ae7c98392dc3c96481a4514758b059
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-beállítások importálása Windows 8.1 és újabb rendszerű eszközökhöz a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Windows 8.1, vagy a Windows 10 asztali vagy mobilverzióját futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi beállítások exportálása windowsos eszközről

A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi profilt. A szükséges Wi-Fi profillal már rendelkező Windows-számítógépen kövesse az alábbi eljárást.
1. Hozzon létre egy helyi mappát az exportált W-Fi-profilokhoz, például a **c:\WiFi** mappát.
1. Nyisson meg egy parancssort rendszergazdaként.
1. Futtassa a **netsh wlan show profiles** parancsot, és jegyezze fel az exportálni kívánt profil nevét. Ebben a példában a profil neve: **WiFiName**.
1. Futtassa a következő parancsot: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Ez a parancs egy **Wi-Fi-WiFiName.xml** nevű Wi-Fi-profilt hoz létre a célmappában.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi-beállítások importálása az Intune-ba

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
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


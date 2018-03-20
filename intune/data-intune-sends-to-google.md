---
title: "Az Intune által a Google-nek küldött adatok"
titleSuffix: Microsoft Intune
description: "Az Intune által az Google-nek küldött adatok listája."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63f1b07d13daad7512dff8e53f9acbafa7bffdd3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/17/2018
---
# <a name="data-intune-sends-to-google"></a>Az Intune által a Google-nek küldött adatok

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ha az Android eszközkezelése engedélyezve van egy eszközön, a Microsoft Intune kapcsolatot létesít az Google-lel, és felhasználói és eszközadatokat oszt meg vele. Ahhoz, hogy a Microsoft Intune létrehozhassa a kapcsolatot, Önnek létre kell hoznia egy Google-fiókot.

Az alábbi táblázat felsorolja az adatokat, amelyeket az eszközkezelés engedélyezése esetén a Microsoft Intune küld a Google-nek:


| A Google-nek küldött adat | Részletek | Felhasználási mód | Példa |
|:---:|:---:|:---:|:---:|
| EnterpriseId | A Google adja meg a Gmail-fiók és az Intune összekapcsolásakor. | Az Intune és a Google közötti kommunikáció során használt elsődleges azonosító.  Ehhez a kommunikációhoz tartozik a szabályzatok beállítása, az eszközök kezelése és az Android Enterprise és az Intune közötti kapcsolat létrehozása és bontása. | Egyedi azonosító. Példa a formátumra: LC04eik8a6 |
| Szabályzattörzs | Az Intune adja meg új alkalmazás- vagy konfigurációs szabályzat mentésekor. | Szabályzatok alkalmazása az eszközökre. | Ez az egy alkalmazás- vagy konfigurációs szabályzathoz konfigurált összes beállítás gyűjteménye. Ha azok egy szabályzatban meg vannak adva, akkor tartalmazhat olyan ügyféladatokat is, mint a hálózati nevek, alkalmazásnevek és alkalmazás-specifikus beállítások. |
| Eszközadatok | Az eszközök munkahelyi profillal való alkalmazása az Intune-ban történő regisztrációval kezdődik. A felügyelt eszközök alkalmazásának első lépése a Google-ben történő regisztráció. | Az Intune és a Google többféle tevékenység során cserélhet eszközadatokat. Ilyen például a szabályzatok alkalmazása, az eszköz kezelése és az általános jelentéskészítés. | **Az eszköz neveként használt egyedi azonosító.** Példa: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**A felhasználó neveként használt egyedi azonosító.** Példa: enterprises/LC04ebru7b/users/116838519924207449711<br>**Eszköz állapota** Példák: Active (aktív), Disabled (letiltva), Provisioning (kiépítés folyamatban).<br>**Megfelelőségi állapotok.** Példák: Setting not supported (a beállítás nem támogatott), missing required apps (kötelező alkalmazások hiányoznak)<br>**Szoftveradatok.** Példák: szoftverfrissítések & verzió javítási szintje.<br>**Hálózati adatok.** Példák: IMEI, MEID, WifiMacAddress<br>**Device Settings.** Példák: Információ a titkosítási szintekről, és hogy az eszközön futhatnak-e ismeretlen alkalmazások.<br> A lap alján egy JSON-üzenetminta is található. |
| newPassword | Az Intune adja meg. | Az eszköz PIN-kódjának alaphelyzetbe állítása. | Az új jelszóként használt karakterlánc. |
| Google User | Google | Munkahelyi profil kezelése munkahelyi profil (BYOD) alapú helyzetekben. | Egyedi azonosító a kapcsolt Gmail-fiókhoz. Példa: 114223373813435875042 |
| Alkalmazásadatok | Az Intune adja meg alkalmazásszabályzat mentésekor. |  | Alkalmazásnév karakterlánc. Példa: app:com.microsoft.windowsintune.companyportal |
| Vállalati szolgáltatásfiók | A Google adja meg az Intune kérelmére válaszolva. | Az adott ügyfelet érintő Intune és Google közötti tranzakciók során használt hitelesítő adat. | Több részből áll:<br> **EnterpriseId**: lásd fent.<br>**UPN**: az ügyfél részéről történő hitelesítéshez generált UPN.<br>Példa: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Kulcs**: Hitelesítési kérelmekben használt Base64-kódolású blob. A szolgáltatásban titkosítva van tárolva, de a blob tartalma a következő:<br> A felhasználó kulcsaként használt egyedi azonosító<br>Példa: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Példa eszközadatokra**

Az alábbi példa egy Google-től származó JSON-eszközüzenetet mutat be:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Ha nem szeretné használni az Android eszközkezelést az Intune-nal, és törölni szeretné az adatokat, le kell tiltania a Microsoft Intune androidos eszközkezelést és törölnie kell a Google-fiókját. A fiókkezelésről a Google-fiókban tudhat meg többet.



---
title: "Az Intune AirPlay-beállításai iOS-eszközökhöz"
titleSuffix: Intune on Azure
description: "Ismerje meg, hogyan segítheti az Intune az iOS-es eszközök automatikus csatlakoztatását AirPlay-kompatibilis eszközökhöz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7e44c1d438fc5782d696cba0b39c3c4d65492096
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/05/2017
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Az Intune AirPlay-beállításai iOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ezekkel a beállításokkal segítheti a felügyelt iOS-es eszközök a hálózatán lévő AirPlay-kompatibilis eszközökhöz (például AppleTV-khez) való csatlakoztatását.
A képesség a következőket teszi lehetővé:

- **Eszköz- és jelszólista konfigurálása** – A felhasználók automatikusan kapcsolódhatnak a hatókörön belüli AirPlay-eszközökhöz. Az AirPlay-eszközök nevével és jelszavával hozza létre, hogy kapcsolódáskor ne kelljen megadni.
- **Engedélyezett célhelyek konfigurálása** – Összeállíthatja az engedélyezett AirPlay-eszközök listáját (az eszközazonosítók alapján). A végfelhasználók (a felügyelt eszközökön) csak a felsorolt eszközöket látják és érik el.

## <a name="get-started"></a>Első lépések

1. Az **Eszközfunkciók** panelen válassza az **AirPlay** elemet.
2. Az **AirPlay** panelen tegye a következők egyikét vagy mindkettőt:

## <a name="configure-a-device-and-password-list"></a>Eszköz- és jelszólista konfigurálása

1. A **Jelszavak** panelen töltse ki az AirPlay-eszközhöz (pl. **Contoso Apple TV**) tartozó **Eszköznév** és **Jelszó** mezőt.
2. Az összes eszközadat megadása után kattintson a **Hozzáadás** elemre. Az eszköz megjelenik az **Eszköznév** listában.
3. Folytassa az eszközök hozzáadását. Ha elkészült, válassza az **OK** elemet.


## <a name="configure-allowed-destinations"></a>Engedélyezett célhelyek konfigurálása

1. Az **Allowed destinations (supervised only)** (Engedélyezett célhelyek (csak felügyelt eszközökhöz)) panelen adja meg az AirPlay-eszköz **Device ID** (Eszközazonosító) értékét, például: 52:46:CD:51:83:4C.
2. Az eszközazonosító megadása után kattintson a **Hozzáadás** elemre. Az azonosító megjelenik a **Device ID** (Eszközazonosító) listában.
3. Folytassa az eszközök hozzáadását. Ha elkészült, válassza az **OK** elemet.

Az eszközöket és jelszavakat, illetve az engedélyezett célhelyeket vesszővel tagolt szövegfájlból (csv-ből) is importálhatja.


## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).


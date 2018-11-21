---
title: Az Intune AirPlay-beállításai iOS-eszközökhöz
titlesuffix: Microsoft Intune
description: A cikk azt mutatja be, hogyan segítheti a Microsoft Intune az iOS-es eszközök automatikus csatlakoztatását AirPlay-kompatibilis eszközökhöz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: efeb7895bcd83883e7fcaaca93c3d19d19a0bb5c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184131"
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Az Intune AirPlay-beállításai iOS-eszközökhöz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ezekkel a beállításokkal segítheti a felügyelt iOS-es eszközök a hálózatán lévő AirPlay-kompatibilis eszközökhöz (például AppleTV-khez) való csatlakoztatását.
A képesség a következőket teszi lehetővé:

- **Eszköz- és jelszólista konfigurálása** – A felhasználók automatikusan kapcsolódhatnak a hatókörön belüli AirPlay-eszközökhöz. Az AirPlay-eszközök nevével és jelszavával hozza létre, hogy kapcsolódáskor ne kelljen megadni.
- **Engedélyezett célhelyek konfigurálása** – Összeállíthatja az engedélyezett AirPlay-eszközök listáját (az eszközazonosítók alapján). A végfelhasználók (a felügyelt eszközökön) csak a felsorolt eszközöket látják és érik el.

## <a name="get-started"></a>Első lépések

1. Az [Intune az Azure Portalon](https://portal.azure.com) felületről lépjen az eszközkonfigurációs terület [**Eszközfunkciók** részére](device-features-configure.md). 
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


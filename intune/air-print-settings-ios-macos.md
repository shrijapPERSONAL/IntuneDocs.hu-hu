---
title: "Az Intune AirPrint-beállításai iOS- és macOS-eszközökhöz"
titlesuffix: Azure portal
description: "Ismerje meg, hogyan segítheti az Intune az iOS-es és macOS-es eszközök automatikus csatlakoztatását AirPrint-kompatibilis nyomtatókhoz."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f55d05dd39fca02e72535cbbff9afb8d575ed9f
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>AirPrint-beállítások iOS- és macOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ezekkel a beállításokkal a hálózaton lévő AirPrint-kompatibilis nyomtatókhoz való automatikus csatlakozásra konfigurálhatja az iOS-es és macOS-es eszközöket. Ehhez a nyomtatók IP-címére és erőforrás-elérési útjára is szükség van.

## <a name="find-airprint-printer-information"></a>AirPrint-nyomtatóadatok keresése

Ezzel az eljárással vehet fel AirPrint-információkat az AirPrint-adattartalomba, amely alapján az iOS-es eszközök felhasználói nyomtathatnak az ismert AirPrint-nyomtatókra.

1. Egy, az AirPrint-nyomtatókkal azonos helyi hálózatra (alhálózatra) csatlakoztatott Mac gépen nyissa meg a Terminal programot (az **/Applications/Utilities** alatt)
2. A Terminalba írja be az **ippfind** parancsot, majd nyomja le az Entert.
3. Jegyezze fel a parancs által visszaadott nyomtatóadatokat – például **ipp://myprinter.local.:631/ipp/port1**. Az információ első fele a nyomtató neve, a második az erőforrás elérési útja.
4. A Terminalba írja be a **ping myprinter.local** parancsot, majd nyomja le az Entert.
5. Jegyezze fel a parancs által visszaadott nyomtatóadatokat – például **PING myprinter.local (10.50.25.21)**.
6. Végül adja meg az IP-címet és az erőforrás elérési útját az AirPrint adattartalom beállításainál. Példánkban az IP-cím **10.50.25.21**, az erőforrás elérési útja pedig **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>AirPrint-profil konfigurálása

1. Az **Eszközfunkciók** panelen válassza az **AirPrint** elemet.
2. Az **AirPrint** panelen az **IP-cím** és az **Erőforrás elérési útja** megadásával és a **Hozzáadás** gombra kattintva vegye fel az AirPrint-célhelyet.
3. Folytassa, amíg fel nem vette az összes kívánt célhelyet. Ha elkészült, válassza az **OK** elemet.

A nyomtatók listáját vesszővel tagolt formátumú (.csv) fájlból is importálhatja, vagy exportálhatja ilyenbe.


## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).
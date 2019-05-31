---
title: A - beli Microsoft Intune szoftverfrissítéseinek hibaelhárítása |} A Microsoft Docs
description: A Microsoft Intune szoftverfrissítéseivel kapcsolatban felmerülő problémák megoldása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee5ed6339efff4b3e32a9c10ac756d7f8bec6260
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402625"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>A Microsoft Intune szoftverfrissítéseinek hibaelhárítása

Segítségével a Microsoft Intune software update kapcsolatos problémák megoldásához. A hibakódok és leírások listájának megtekintéséhez, keresse fel a [szoftverek frissítési ügynök hibakódjait Microsoft Intune-ban](software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Windows 7-eszközök Intune-ban a jelentéskészítés sok felülírt frissítések leállítása

A Microsoft Intune-ügyfelek akkor fordulhatnak elő, az alábbi jelenségek közül legalább egyet:

- Eszközök nem hirtelen küldenek jelentéseket az Intune-hoz.  
- Eszközök ügyfeleken magas fokú Processzorhasználatot tapasztalható.
- Alkalmazások telepítése lassan az Intune-nal való telepítésekor.
- A Microsoft Intune Center a következő hibaüzenetet jeleníti meg: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- Az Intune felügyeleti konzol > csoportok > minden eszköz > állapotát jeleníti meg: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

A probléma akkor fordulhat elő, ha a felülírt frissítések (frissítések helyébe egy másik frissítés) még nem lett utasítva, hosszabb ideig. Bizonyos folyamatok, például az alkalmazások telepítése során a Windows ellenőrzi az összes felülírt frissítést, így a frissítéseket és leképezhesse megfelelően vannak leképezve. Ha a felülírt frissítések listája túl nagy, az ellenőrzési feladat magas CPU-kihasználtság okozhat a feldolgozási terhelés és a szükséges idő miatt. Ezt a hibát elsősorban észleli a Windows 7-eszközökön a felülírt frissítések a Windows 7 rendszerhez elérhető nagy száma miatt. Az újabb operációs rendszerek nem lehet például sok felülírt frissítés, és nem lehet a probléma ki van téve.

**Felbontás**

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza ki **szoftverfrissítések**.
3. Elutasítja a alkalmazni előfordulhat, hogy a Windows 7 összes felülírt frissítést, vagy az alkalmazások, például a Microsoft Office, az érintett ügyfelek, amelyek lettek telepítve.
4. Indítsa újra az érintett ügyfeleket.

Ha a Windows 7 rendszert használ, győződjön meg a következő frissítés telepítve van:[3050265 Windows Update Client for Windows 7: 2015 június](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>További lépések

Első [segítséget a Microsoft támogatási](get-support.md), vagy használja a [közösségi fórumokat is talál](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
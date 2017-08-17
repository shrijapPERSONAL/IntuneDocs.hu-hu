---
title: "Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása"
titleSuffix: Intune on Azure
description: "A cikk azt ismerteti, hogyan használható az Újrakezdés az Intune-t futtató Windows 10 rendszerű számítógépek alaphelyzetbe állításához.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44633f244536a0033dd51fc06e1dba09c0490500
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása az Újrakezdéssel


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Újrakezdés** eszközművelet eltávolít minden alkalmazást az alkotói frissítéssel rendelkező Windows 10-es számítógépről, majd automatikusan a Windows legújabb verziójára frissíti az eszközt.
Így egyszerűbben eltávolíthatók az új gépeken gyakran előtelepítve megtalálható számítógépgyártói (OEM) alkalmazások. A konfigurációval meg lehet adni, hogy a művelet a felhasználói adatokat is eltávolítsa-e. Ebben az esetben az alkalmazások és a beállítások el lesznek távolítva, de a felhasználó kezdőmappájának tartalma megmarad.

## <a name="how-to-use-fresh-start"></a>Az Újrakezdés használata

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki a Windows 10-es asztali eszközt, majd válassza a távoli **Újrakezdés** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.


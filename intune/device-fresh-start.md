---
title: "Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása"
titlesuffix: Azure portal
description: "A cikk azt ismerteti, hogyan használható az Újrakezdés az Intune-t futtató Windows 10 rendszerű számítógépek alaphelyzetbe állításához.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása az Újrakezdéssel


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az **Újrakezdés** eszközművelet eltávolít minden alkalmazást az alkotói frissítéssel rendelkező Windows 10-es számítógépről, majd automatikusan a Windows legújabb verziójára frissíti az eszközt.
Ezzel a művelettel egyszerűbben eltávolíthatók az új gépeken gyakran előtelepítve megtalálható számítógépgyártói (OEM) alkalmazások. A konfigurációval meg lehet adni, hogy a művelet a felhasználói adatokat is eltávolítsa-e. Ebben az esetben az alkalmazások és a beállítások el lesznek távolítva, de a felhasználó kezdőmappájának tartalma megmarad.

## <a name="how-to-use-fresh-start"></a>Az Újrakezdés használata

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válassza ki a Windows 10-es asztali eszközt, majd válassza a távoli **Újrakezdés** eszközműveletet.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.


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
ms.openlocfilehash: dce888c1985ff4761100d15d898b654d77318b65
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
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


---
title: Windows 10 rendszerű eszközök visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A Microsoft Intune Újrakezdés funkciójával eltávolíthat alkalmazásokat Windows 10 rendszerű számítógépekről.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5658bf2e1ee250ef9fd405b3f7ec1772b166f338
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása az Újrakezdéssel


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Újrakezdés** eszközművelet eltávolít minden olyan alkalmazást, amely az alkotói frissítéssel rendelkező Windows 10 rendszerű számítógépeken fut. Ezután automatikusan frissíti a Windowst a legújabb verzióra.

Ezzel a művelettel eltávolíthat olyan előre telepített (OEM-ektől származó) alkalmazásokat, amelyek általában telepítve vannak egy új számítógépen. Ha meg szeretné tartani a felhasználó kezdőmappájának tartalmát, és csak az alkalmazásokat és a beállításokat szeretné törölni, használja a(z) `if user data is retained` beállítást.

> [!IMPORTANT]
> Az Újrakezdés törli az eszköz Intune-regisztrációját, azonban az Azure Active Directory-kapcsolata megmarad.

## <a name="use-fresh-start"></a>Az Újrakezdés használata

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson a **Minden szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza a **Microsoft Intune** elemet.
3. Kattintson az **Eszközök**, majd a **Minden eszköz** elemre.
4. A felügyelt eszközök listájából válassza ki a Windows 10-es asztali eszközt, majd válassza az **Újrakezdés** lehetőséget.

## <a name="next-steps"></a>További lépések

Az ikon állapotának megtekintéséhez válassza az **Eszközműveletek** (**Microsoft Intune** > **Eszközök**) lehetőséget.
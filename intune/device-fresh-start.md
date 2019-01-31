---
title: Windows 10 rendszerű eszközök visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A Microsoft Intune Újrakezdés funkciójával eltávolíthat alkalmazásokat Windows 10 rendszerű számítógépekről.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1eb1e671cc16196974cb15cdc785ba7d99fa8f46
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303412"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Intune-t futtató Windows 10 rendszerű eszközök alaphelyzetbe állítása az Újrakezdéssel


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az **Újratelepítés** eszközművelet eltávolít minden alkalmazást, amely telepítve van egy Windows 10 rendszerű (1703-as vagy újabb verzió) számítógépen. Ezzel a művelettel eltávolíthatja az olyan előre telepített (OEM) alkalmazásokat, amelyek általában telepítve vannak egy új számítógépen.  

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com), majd lépjen a **Microsoft Intune** > **Eszközök** > **Minden eszköz** elemre.
2. A felügyelt eszközök listájából válasszon ki egy Windows 10-es asztali eszközt.
3. Kattintson az **Újratelepítés** lehetőségre. 
4. **Az eszközön található felhasználói adatok megőrzése** beállításnál válassza ki a következőket:
   * Az eszköz Azure AD-csatlakozásának megtartása
    * -Eszközt léptetnek be mobileszköz-kezelés ismét mikor engedélyezésekor egy Azure Active Directory felhasználó jelentkezik be az eszközre.
    * Az eszköz felhasználójához tartozó kezdőmappa tartalmának megtartása, az alkalmazások és beállítások eltávolítása  
  > [!IMPORTANT]
 > Ha nem tartja meg a felhasználói adatokat, az eszköz a gyári állapotára fog visszaállni. BYOD-eszközök megszűnik az Azure AD és a mobileszköz-kezelés.
 > Az Azure AD-csatlakoztatott eszközök lesz regisztrálva mobileszköz-felügyelet alá újra engedélyezésekor egy Azure Active Directory felhasználó jelentkezik be az eszközre.
 
5. Kattintson az **OK**gombra.   
6. A művelet állapotának megtekintéséhez lépjen vissza az **Eszközök** szintjére, majd kattintson az **Eszközműveletek** elemre.  

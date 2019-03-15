---
title: Windows 10 rendszerű eszközök visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A Microsoft Intune Újrakezdés funkciójával eltávolíthat alkalmazásokat Windows 10 rendszerű számítógépekről.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 230c328c14f0da39db34c8b91ac30fe05f9b05ca
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57388192"
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
 
5. Kattintson az **OK** gombra.   
6. A művelet állapotának megtekintéséhez lépjen vissza az **Eszközök** szintjére, majd kattintson az **Eszközműveletek** elemre.  

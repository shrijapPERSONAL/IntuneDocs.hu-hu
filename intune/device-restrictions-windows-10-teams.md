---
title: "Eszközkorlátozások az Intune-ban Windows 10 Team esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt a Windows 10 Team-eszközökre vonatkozó eszközkorlátozásokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a5c3eaf3d2b1fc4383282473352124c793b666f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>A Windows 10 Team eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- **Képernyő felébresztése, ha valaki a helyiségben tartózkodik** – Lehetővé teszi az eszköz automatikus felébresztését, ha az érzékelők valakit észlelnek a helyiségben.
- **Vezeték nélküli kivetítéshez szükséges PIN-kód** – Meghatározza, hogy meg kell-e adni a PIN-kódot az eszköz vezeték nélküli vetítési képességeinek használata előtt.
- **Miracast vezeték nélküli vetítés** – A beállítás engedélyezésével lehetővé teheti a Windows 10 Team-eszköz számára a Miracast-kompatibilis eszközök használatát a vetítéshez.
- **Üdvözlőképernyőn megjelenített értekezletadatok** – Ha engedélyezi ezt a lehetőséget, kiválaszthatja az üdvözlőképernyő Értekezletek csempéjén megjelenő adatokat. A következőket teheti:
    - **Csak szervező és időpont megjelenítése**
    - **Szervező, időpont és tárgy megjelenítése (zártkörű értekezletek esetén a tárgy rejtett)**
- **Üdvözlőképernyő háttérképének URL-címe** – A beállítás engedélyezésével egy egyéni hátteret jeleníthet meg a Windows 10 Team-eszközök **üdvözlőképernyőjén** a megadott URL-címről.<br>A képnek PNG formátumban kell lennie, és az URL-címnek a **https://** karakterlánccal kell kezdődnie.
- **Frissítésre szolgáló karbantartási időszak** – Meghatározza, hogy mely időszakban kerülhet sor frissítésekre az eszközön. Beállíthatja a kezdési időt és az időtartamot (1-5 óra) is.
- **Azure Operational Insights** – A Microsoft Operations Manager csomag részét képező Azure Operational Insights összegyűjti, tárolja és elemzi a Windows 10 Team-eszközök naplófájladatait.<br>Az Azure-os Operational Insights szolgáltatáshoz végzett csatlakozáshoz meg kell adnia egy **munkaterület-azonosítót** és egy **munkaterületkulcsot**.

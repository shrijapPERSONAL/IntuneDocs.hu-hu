---
title: "Eszközkorlátozások az Intune-ban Windows 10 Team esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: További információ a Windows 10 Team-eszközökre vonatkozó korlátozásokról."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: afbbe6b7649e1ffc3f84ada64396d9033a2db200
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>A Windows 10 Team eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

- **Képernyő felébresztése, ha valaki a helyiségben tartózkodik** – Lehetővé teszi az eszköz automatikus felébresztését, ha az érzékelők valakit észlelnek a helyiségben.
- **Vezeték nélküli kivetítéshez szükséges PIN-kód** – Meghatározza, hogy meg kell-e adni a PIN-kódot az eszköz vezeték nélküli vetítési képességeinek használata előtt.
- **Miracast vezeték nélküli vetítés** – A beállítás engedélyezésével lehetővé teheti a Windows 10 Team-eszköz számára a Miracast-kompatibilis eszközök használatát a vetítéshez.
- **Üdvözlőképernyőn megjelenített értekezletadatok** – Ha engedélyezi ezt a lehetőséget, kiválaszthatja az üdvözlőképernyő Értekezletek csempéjén megjelenő adatokat. A következőket teheti:
    - **Csak szervező és időpont megjelenítése**
    - **Szervező, időpont és tárgy megjelenítése (zártkörű értekezletek esetén a tárgy rejtett)**
- **Üdvözlőképernyő háttérképének URL-címe** – A beállítás engedélyezésével egy egyéni hátteret jeleníthet meg a Windows 10 Team-eszközök **üdvözlőképernyőjén** a megadott URL-címről.<br>A képnek PNG formátumban kell lennie, és az URL-címnek a **https://** karakterlánccal kell kezdődnie.
- **Frissítésre szolgáló karbantartási időszak** – Meghatározza, hogy mely időszakban kerülhet sor frissítésekre az eszközön. Beállíthatja a kezdési időt és az időtartamot (1-5 óra) is.
- **Azure Operational Insights** – A Microsoft Operations Manager csomag részét képező Azure Operational Insights összegyűjti, tárolja és elemzi a Windows 10 Team-eszközök naplófájladatait.<br>Az Azure-os Operational Insights szolgáltatáshoz végzett csatlakozáshoz meg kell adnia egy **munkaterület-azonosítót** és egy **munkaterületkulcsot**.


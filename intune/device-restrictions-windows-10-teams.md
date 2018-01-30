---
title: "Eszközkorlátozások az Intune-ban Windows 10 Team esetén"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt a Windows 10 Team-eszközökre vonatkozó eszközkorlátozásokról."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3648f8b273f666d1898226f3da8580e55a6bc6f8
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>A Windows 10 Team eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="apps-and-experience"></a>Alkalmazások és felhasználói élmény

- **Képernyő felébresztése, ha valaki a helyiségben tartózkodik** – Lehetővé teszi az eszköz automatikus felébresztését, ha az érzékelők valakit észlelnek a helyiségben.
- **Üdvözlőképernyőn megjelenített értekezletadatok** – Ha engedélyezi ezt a lehetőséget, kiválaszthatja az üdvözlőképernyő Értekezletek csempéjén megjelenő adatokat. A következőket teheti:
    - **Csak szervező és időpont megjelenítése**
    - **Szervező, időpont és tárgy megjelenítése (zártkörű értekezletek esetén a tárgy rejtett)**
- **Üdvözlőképernyő háttérképének URL-címe** – A beállítás engedélyezésével egy egyéni hátteret jeleníthet meg a Windows 10 Team-eszközök **üdvözlőképernyőjén** a megadott URL-címről.<br>A képnek PNG formátumban kell lennie, és az URL-címnek a **https://** karakterlánccal kell kezdődnie.

## <a name="azure-operational-insights"></a>Azure Operational Insights

- **Azure Operational Insights** – A Microsoft Operations Manager csomag részét képező Azure Operational Insights összegyűjti, tárolja és elemzi a Windows 10 Team-eszközök naplófájladatait.
Az Azure-os Operational Insights szolgáltatáshoz végzett csatlakozáshoz meg kell adnia egy **munkaterület-azonosítót** és egy **munkaterületkulcsot**.

## <a name="maintenance"></a>Karbantartás

- **Frissítésre szolgáló karbantartási időszak** – Meghatározza, hogy mely időszakban kerülhet sor frissítésekre az eszközön. Konfigurálhatja az időszak **Kezdési időpontját** és **Időtartamát (óra)** (1 és 5 óra között).

## <a name="wireless-projection"></a>Vezeték nélküli kivetítés

- **Vezeték nélküli kivetítéshez szükséges PIN-kód** – Meghatározza, hogy meg kell-e adni a PIN-kódot az eszköz vezeték nélküli vetítési képességeinek használata előtt.
- **Miracast vezeték nélküli vetítés** – A beállítás engedélyezésével lehetővé teheti a Windows 10 Team-eszköz számára a Miracast-kompatibilis eszközök használatát a vetítéshez.
- **Miracast vezeték nélküli kivetítési csatorna** – Válassza ki a kapcsolat létrehozásához használt Miracast-csatornát.


## <a name="next-steps"></a>További lépések

Olvassa el az [Eszközkorlátozási profilok konfigurálása](device-restrictions-configure.md) szakaszt a profil mentéséhez, majd hozzárendeléséhez a felhasználók és eszközök számára.

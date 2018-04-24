---
title: Konfigurációs szabályzat Windows Team-alapú eszközökhöz – Beállítások
description: Regisztrált Windows 10 Team eszközök, például a Microsoft Surface Hub beállításainak konfigurálására használhatja a **Windows 10 Team eszközökhöz készült általános konfigurációs házirendjét**.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>A Windows Team konfigurációs házirendjének beállításai a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Regisztrált Windows 10 Team eszközök, például a Microsoft Surface Hub beállításainak konfigurálására használhatja a **Windows 10 Team eszközökhöz készült általános konfigurációs házirendjét**.


|                                  Beállítás neve                                   |                                                                                                                                                                Részletek                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Képernyő felébresztésének engedélyezése, ha valaki van a helyiségben</strong>   |                                                                                                                         Lehetővé teszi az eszköz automatikus felébresztését, ha az érzékelők valakit észlelnek a helyiségben.                                                                                                                          |
|              <strong>PIN-kód kérése vezeték nélküli vetítéshez</strong>               |                                                                                                             Meghatározza, hogy meg kell-e adni a PIN-kódot az eszköz vezeték nélküli vetítési funkcióinak használata előtt.                                                                                                             |
|          <strong>Karbantartási időszak megadása az eszközfrissítésekhez</strong>           |                                                                                          Meghatározza, hogy mely időszakban kerül sor az eszköz frissítéseire. Beállíthatja a kezdési időt és az időtartamot (1-5 óra) is.                                                                                           |
|               <strong>Az Azure-os Operational Insights engedélyezése</strong>                |                  A Microsoft Operations Manager csomag részét képező Azure-os Operational Insights naplófájladatokat gyűjt, tárol és elemez a from Windows 10 Team-eszközökről.<br /><br />Az Azure-os Operational Insights szolgáltatáshoz végzett csatlakozáshoz meg kell adnia egy <strong>munkaterület-azonosítót</strong> és egy <strong>munkaterületkulcsot</strong>.                   |
|              <strong>Miracast vezeték nélküli vetítés engedélyezése</strong>               |                                          Engedélyezze ezt a lehetőséget, hogy a Windows 10 Team-eszköz Miracast technológiát használó eszközökkel vetíthessen.<br /><br />Ha engedélyezi ezt a lehetőséget, a <strong>Válasszon Miracast-csatornát</strong> területen válassza ki a tartalom vetítéséhez használni kívánt Miracast-csatornát.                                           |
| <strong>Az üdvözlőképernyőn megjelenő értekezletadatok kiválasztása</strong> | Ha engedélyezi ezt a lehetőséget, kiválaszthatja az <strong>Üdvözöljük</strong> képernyő <strong>Értekezletek</strong> csempéjén megjelenő adatokat. A következőket teheti:<br /><br />-   <strong>Csak szervező és időpont megjelenítése</strong><br />-   <strong>Szervező, időpont és tárgy megjelenítése (zártkörű értekezletek esetén a tárgy rejtett)</strong> |
|                <strong>Zárolási képernyő háttérképének URL-címe</strong>                 |                                           Engedélyezze ezt a beállítást, ha az Ön által megadott URL-címről egy egyéni hátteret szeretne megjeleníteni a Windows 10 Team-eszközök <strong>Üdvözöljük</strong> képernyőjén.<br /><br />A képnek PNG formátumban kell lennie, és az URL-címnek a <strong>https://</strong> karakterlánccal kell kezdődnie.                                            |

### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


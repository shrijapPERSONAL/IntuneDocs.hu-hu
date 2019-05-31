---
title: Teljes képernyős beállítások a Windows és holografikus eszközök Microsoft Intune - Azure-ban |} A Microsoft Docs
description: Konfigurálja a Windows 10 (vagy újabb) és a Windows Holographic for Business Egyalkalmazásos és többalkalmazásos kioszk eszközöket, a start menü testreszabásához, alkalmazások hozzáadása, megjelenítése a tálcán és egy webes böngésző konfigurálása a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19641a36cf429773a8c0e06a90ee279d2baa06f7
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412237"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Windows 10 és Windows Holographic for Business eszközbeállítások futtatása egy dedikált futtasson teljes képernyőn az Intune-nal

A Windows 10-eszközökön az Intune használatával eszközöket futtató egy teljes képernyős, más néven egy dedikált eszközök. Egy eszköz teljes képernyős módban futtathat egy alkalmazást, vagy számos alkalmazás futtatásához. Megjelenítése és a start menü testreszabásához, adja hozzá a különböző alkalmazásokat, beleértve a Win32-alkalmazások, adjon hozzá egy adott kezdőlap az egy webböngészőt, és egyéb. 

Ez a funkció az operációs rendszert futtató eszközökre vonatkozik:

- Windows 10 és újabb
- Windows Holographic for Business

Az Intune eszközönként egy kioszkprofilt támogat. Ha egy adott eszközön több kioszkprofilra van szüksége, használhat egy [egyéni OMA-URI](custom-settings-windows-10.md)-t.

Az Intune használja a "profilok" hozhat létre, és ezeket a beállításokat a szervezet igényeinek megfelelően. Ezeket a funkciókat egy profilt ad hozzá, miután leküldéses vagy telepítheti ezeket a beállításokat a szervezet csoportjaihoz.

Ez a cikk bemutatja, hogyan hozhat létre eszközkonfigurációs profil. Az összes beállítás listáját, és mit tesznek, lásd: [Windows 10-es teljes képernyős beállítások](kiosk-settings-windows.md) és [kioszkmód Windows Holographic for Business](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>A profil létrehozása

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza ki **Windows 10 és újabb verziók**
   - **Profil típusa**: Válassza ki **kioszk**

4. A **beállítások**, jelölje be a **teljes képernyős mód**. A **Kioszkmód** azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

    - **Nincs konfigurálva** (alapértelmezett): A szabályzat nem teszi lehetővé a teljes képernyős mód.
    - **Önálló alkalmazás, a teljes képernyős**: Az eszköz fut, egyetlen felhasználói fiókkal, és lezárja az egyetlen Store alkalmazás. Ezért, amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
    - **Többalkalmazásos kioszk**: Az eszköz a több Store apps, a Win32-alkalmazások vagy a Beérkezett fájlok Windows-alkalmazások az alkalmazás felhasználói modellben használt azonosítója (AUMID) használatával futtatja. Az eszközön csak a hozzáadott alkalmazások lesznek elérhetők.

        A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználóknak, amelyben csak a szükséges alkalmazások érhetőek el. A szükségtelen alkalmazásokat pedig elrejti.

    Az összes beállítások listáját, és mit tesznek lásd:
      - [Windows 10-es teljes képernyős beállítások](kiosk-settings-windows.md)
      - [A kioszkmód Windows Holographic for Business](kiosk-settings-holographic.md)

5. Ha elkészült, a módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. 

A profil létrehozásáról, és a profilok listájában jelenik meg. Ezután [hozzárendelése](device-profile-assign.md) a profilt.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

A következő platformokat futtató eszközök esetében a teljes képernyős profilokat hozhat létre:
- [Android](device-restrictions-android.md#kiosk)
- [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)
- [Windows 10 és újabb](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)

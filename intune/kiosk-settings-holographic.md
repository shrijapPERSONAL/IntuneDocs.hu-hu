---
title: Teljes képernyős beállítások a Microsoft Intune - Azure-ban Windows Holographic for Business |} A Microsoft Docs
description: Egyalkalmazásos és többalkalmazásos kioszk a Windows Holographic for Business-eszközök konfigurálása, a start menü testreszabásához, alkalmazások hozzáadása, megjelenítése a tálcán és egy webes böngésző konfigurálása a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f38803d3be05182639ac8eca2578e9ce121f7c2f
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514038"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows Holographic for Business, az Intune-ban a teljes képernyős futtató eszköz beállításai

Windows Holographic for Business rendszerű eszközök egyalkalmazásos vagy többalkalmazásos kioszkmódban való használatra is konfigurálhatók. Bizonyos funkciókat a Windows Holographic for Business nem támogat.

Ez a cikk és szabályozhatja a különböző beállításokat ismerteti a Windows Holographic for Business-eszközök. A mobileszköz-felügyelet (MDM) megoldás részeként ezek a beállítások segítségével konfigurálhatja a Windows Holographic for Business-eszközök kioszk módban futtatni.

Intune rendszergazdaként létrehozhat és rendelje hozzá ezeket a beállításokat az eszközökön.

Az Intune-ban, a Windows teljes képernyős szolgáltatással kapcsolatos további tudnivalókért lásd: [a kioszkmód konfigurálása](kiosk-settings.md).

## <a name="before-you-begin"></a>Előkészületek

[A profil létrehozásához](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Egyetlen teljes képernyős alkalmazásos kioszkok

Egyalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **Felhasználói bejelentkezési típus**: Válassza ki **helyi felhasználói fiók** , írja be a helyi (eszközön létező) felhasználói fiókot, vagy egy a teljes képernyős alkalmazáshoz társított Microsoft-fiók (MSA) fiók. Az **Automatikus bejelentkezésű** felhasználói fiókokat a Windows Holographic for Business nem támogatja.

- **Az alkalmazástípus**: Válassza ki **Store alkalmazás**.

- **Alkalmazás teljes képernyős módban való futásra**: Válasszon **áruházbeli alkalmazás hozzáadása**, és válasszon ki egy alkalmazást a listából.

    Nincsenek alkalmazások a listában? Adjon hozzá néhányat az [Ügyfélalkalmazások](apps-add.md) rész lépéseinek használatával.

    Válassza ki **OK** a módosítások mentéséhez.

## <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

Az ebben az üzemmódban lévő alkalmazások elérhetők a Start menüben. A felhasználó kizárólag ezeket az alkalmazásokat tudja megnyitni. Többalkalmazásos kioszk mód választásakor adja meg a következő beállításokat:

- **A Windows 10 S mód eszközökön célzott**: Válasszon **nem**. S mód nem támogatott a Windows Holographic for Business.

- **Felhasználói bejelentkezési típus**: Adjon hozzá egy vagy több felhasználói fiókok, amelyek használhatják a hozzáadott alkalmazások. A választható lehetőségek: 

  - **Automatikus bejelentkezés**: Nem támogatott a Windows Holographic for Business.
  - **A helyi felhasználói fiókok**: **Adjon hozzá** a helyi (eszközön létező) felhasználói fiók. A megadott fiókkal történik a bejelentkezés a kioszkba.
  - **Azure AD-felhasználó vagy csoport (Windows 10 1803-es és újabb verziók)**: Felhasználói hitelesítő adatokkal jelentkezzen be az eszköz szükséges. Válassza a **Hozzáadás** lehetőséget Azure AD-felhasználók vagy -csoportok kiválasztására a listából. Több felhasználót és csoportot is kiválaszthat. A módosítások mentéséhez válassza az **Választ** gombot.
  - **HoloLens-látogató**: A látogatói egy a Vendég fiók felhasználói hitelesítő adatokat vagy hitelesítést nem igénylő leírtak szerint [megosztott PC mód fogalmak](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Alkalmazások**: Adja hozzá az alkalmazások futtatását a teljes képernyős eszközön. Ne feledje, hogy több alkalmazást is hozzáadhat.

  - **Adja hozzá a Store apps**: Válasszon ki egy meglévő alkalmazást segítségével hozzáadott [ügyfélalkalmazás](apps-add.md). Ha nem találhatók alkalmazások a listában, akkor beszerezheti az alkalmazásokat, és [hozzáadhatja őket az Intune-hoz](store-apps-windows.md).
  - **Win32-alkalmazás hozzáadása**: Nem támogatott a Windows Holographic for Business.
  - **Hozzáadása AUMID alapján**: Ez a beállítás használatával Beérkezett üzenetek Windows-alkalmazások hozzáadása. Adja meg a következő tulajdonságokat: 

    - **Alkalmazásnév**: Kötelező. Adjon nevet az alkalmazásnak.
    - **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)**: Kötelező. Adja meg a Windows-alkalmazás alkalmazásfelhasználói modellben használt azonosítóját. Az azonosító a [Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) című témakörben leírtak alapján kereshető meg.
    - **Csempe méretének**: Kötelező. Válassza a Kicsi, Közepes, Széles és Nagy alkalmazáscsempe-méretek egyikét.

- **Teljes képernyős böngésző beállításait**: Nem támogatott a Windows Holographic for Business.

- **Használat alternatív Start elrendezésének**: Válasszon **Igen** , adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a start menüben, beleértve az alkalmazások sorrendjét. Használja ezt a beállítást, ha több testreszabási lehetőségre van szüksége a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) című cikk nyújt némi útmutatást, és tartalmaz egy kimondottan Windows Holographic for Business rendszerű eszközökhöz készült XML-fájlt.

- **Windows-tálcán**: Nem támogatott a Windows Holographic for Business.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Teljes képernyős profilok is létrehozhat [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), és [Windows 10 és újabb](kiosk-settings-windows.md) eszközök.

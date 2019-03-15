---
title: A Windows Holographic üzleti megosztott eszközbeállítások - beli Microsoft Intune - |} A Microsoft Docs
description: Adja hozzá, és Windows Holographic for Business segítségével konfigurálhatja az eszközöket, amelyek megosztott, vagy a Microsoft Intune-ban több felhasználó használja. A fiók beállításait, és mit tesznek az eszközökön, beleértve a Microsoft HoloLens listájának megtekintéséhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 151ceaa40f2993d3160b9de34eee92e53c35925d
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565859"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Windows Holographic for Business beállításainak kezeléséhez, megosztott eszközök Intune-nal

Windows Holographic for Business-eszközök, például a Microsoft HoloLens használható több felhasználó által. Több felhasználóval rendelkező eszközök megosztott eszközök nevezik, és részei a mobileszköz-felügyelet (MDM) megoldások.

A Microsoft Intune-nal, felhasználók jelentkezhetnek be a megosztott eszközökre Vendég fiókkal. Mint az eszközön, azok csak a get funkciókat engedélyezi a hozzáférést.

Ez a cikk és a rendelkezésre álló beállításokat a Windows Holographic for Business az eszközkonfigurációs profil ismerteti. A profil létrehozásakor az Intune-ban, majd üzembe helyezése, vagy rendelje hozzá a profilt az eszközcsoportok a szervezetben. A vegyes eszköz típusa és operációsrendszer-verziók egy eszközcsoport számára is rendelhet ehhez a profilhoz.

Ez a funkció az Intune-ban a további információkért lásd: [szabályozhatja a hozzáférést, a partnerek és a megosztott PC vagy több felhasználó-eszköz funkcióinak power](shared-user-device-settings.md). A Windows CSP további információkért lásd: [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>A Kezdés előtt

[A profil létrehozásához](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Közös használatú eszköz több felhasználó beállításai

> [!NOTE]
> Csak a, a Microsoft HoloLens, beleértve a Windows Holographic for Business rendszerű eszközök támogatják a **fiókkezelés** beállításait. Ha konfigurálja az Intune-ban látható a többi beállítás bármelyikét, beleértve a **megosztott PC mód**, ez nem befolyásolja ezeket az eszközöket.

- **Fiókkezelés**: Állítsa be **engedélyezése** automatikusan törli a vendégek által létrehozott helyi fiókoknak és az AD és az Azure ad-ben. A felhasználók bejelentkezésekor ki az eszközt, vagy Rendszerkarbantartás futtatásakor, a rendszer törli ezeket a fiókokat. Ha engedélyezve van, is állítsa be:
  - **Fiók törlése**: Válassza ki a fiókok törlésekor: **A storage tárterületre vonatkozó küszöbértéket**, **storage tárterületre vonatkozó küszöbértéket és inaktív küszöbérték**, vagy **jelentkezzen ki után azonnal**. Ezt is adja meg:
    - **Kezdő törlése threshold(%)**: Adja meg a lemezterület százalékában (0 – 100). Ha a teljes lemez-és tárterület a beírt érték alá csökken, a rendszer törli a gyorsítótárazott fiókokat. Folyamatosan törli a fiókok lemezterületet felszabadítása érdekében. A legrégebb inaktív fiókok először törlődnek.
    - **Állítsa le a delete threshold(%)**: Adja meg a lemezterület százalékában (0 – 100). A teljes lemez/tárhely megfelel-e a beírt érték, ha leállítja a törlése.

  Állítsa be **letiltása** , hogy a helyi AD-ben és a vendégek által létrehozott Azure AD-fiókokat.

  > [!NOTE]
  > Csak a Microsoft HoloLens-eszközök támogatják a **fiókkezelés** beállításait.

## <a name="next-steps"></a>További lépések

- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
- Tekintse meg a beállításokat a [Windows 10 és újabb](shared-user-device-settings-windows.md).

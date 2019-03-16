---
title: iOS- és macOS-eszközprofilok létrehozása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Adjon hozzá vagy iOS- vagy macOS-profil létrehozása, és konfigurálhatja az AirPrint, elrendezését a kezdőképernyő, értesítések, közös használatú eszköz, egyszeri bejelentkezési és a webtartalomszűrő-beállításai a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ae03a4155fa2d170648548bb9a08b570f49c673
ms.sourcegitcommit: c4258bb5824daf3f7e0ac3bb8afc539bde4d95da
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/16/2019
ms.locfileid: "57991049"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>iOS-es vagy macOS-es eszközfunkció-beállítások megadása az Intune-ban

Az Intune számos szolgáltatást tartalmaz, és a beállítások, amelyek segítségével a rendszergazdák szabályozhatja az iOS és macOS-eszközökhöz. A rendszergazdák például a következőket teheti:

- A hálózaton lévő AirPrint-nyomtatókra való hozzáférés engedélyezése a felhasználóknak
- Alkalmazások és mappák hozzáadása a kezdőképernyőn, beleértve az új oldal hozzáadása
- Válassza ki, és ha igen, értesítések jelennek meg
- A zárolási képernyőn megjelenítendő üzenet vagy az eszköz eszközcímkéjéről, különösen a megosztott eszközök konfigurálása
- Engedélyezheti a felhasználók biztonságos egyszeri bejelentkezés használatát hitelesítő adatok alkalmazások közötti megosztását.
- Webhelyek, felnőtteknek szóló nyelv és engedélyezése vagy letiltása adott webhelyek szűrése

Ezek a funkciók érhetők el az Intune-ban, és a rendszergazda által konfigurálható. Az Intune használja a "profilok" hozhat létre, és ezeket a beállításokat a szervezet igényeinek megfelelően. Miután ezek a funkciók egy profilt ad hozzá, amit leküldéses, vagy a profilt a szervezetében üzembe helyezi az iOS és macOS-eszközök.

Ez a cikk bemutatja, hogyan hozhat létre eszközkonfigurációs profil. Emellett megtekintheti az összes rendelkezésre álló beállítások [iOS](ios-device-features-settings.md) és [macOS](macos-device-features-settings.md) eszközök.

## <a name="create-a-device-profile"></a>Eszközprofil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki a platformot:
        - **iOS**
        - **macOS**
    - **Profil típusa**: Válassza ki **eszközfunkciók**.
    - **Beállítások**: Adja meg a konfigurálni kívánt beállításokat. Az összes beállítások listáját, és mit tesznek lásd:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. Ha elkészült, a változások mentéséhez válassza az **OK** gombot, majd a **Létrehozás** elemet.

A profil létrehozásáról és jelennek meg a listában. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

## <a name="next-steps"></a>További lépések

A profil létrehozását követően készen áll hozzá kell rendelni. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

Megtekintheti az összes az eszközfunkció-beállításai [iOS](ios-device-features-settings.md) és [macOS](macos-device-features-settings.md) eszközök.

---
title: Adjon hozzá vagy oktatási beállításainak konfigurálása a Microsoft Intune – Azure |} A Microsoft Docs
description: Használja a végezze el a vizsga alkalmazás a Windows 10 és újabb rendszerű eszközökhöz a Microsoft Intune eszközkonfigurációs profil. Az oktatási settiings használó konfigurációs profil létrehozása és a egy teszt alkalmazás URL-CÍMÉT adja meg, hogyan felhasználókat jelentkezzen be, figyelheti a képernyő a teszt során, és lehetővé vagy szövegjavaslatokat megakadályozása a teszt során.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 27f573ca028c64a5aae64bc6feef707d42ad7f06
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841606"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>A végezze el a vizsga alkalmazás használata a Windows 10 rendszerű eszközökön a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Oktatási profilok az Intune-ban egy teszt vagy a vizsgára érvénybe az eszközökön a tanulók számára tervezték. Ez a funkció tartalmazza a **vizsga** alkalmazás és a egy tesztcélú URL-cím hozzáadása beállítások válassza ki, hogyan végfelhasználók jelentkezzen be a teszt és egyéb. Ez a funkció a következő platformot támogatja:

- Windows 10 és újabb

Ha a felhasználó bejelentkezik, a végezze el a vizsga alkalmazás automatikusan megnyílik a megadott tesztet. Más alkalmazás nem futtatható az eszközön, amíg a vizsgálat folyamatban van. [Tesztek is a Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) további információt talál a hajtsa végre a megfelelő alkalmazás.

Ez a cikk a Microsoft Intune eszközkonfigurációs profil létrehozásának lépéseit sorolja fel. Olvassa el, és a Windows 10 rendszerű eszközökhöz elérhető oktatási beállítások ismertetése információkat is tartalmaz.

## <a name="create-a-device-profile"></a>Eszközprofil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **a Microsoft Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válasszon **Windows 10 és újabb**.
    - **Profil**: Válasszon **oktatási profil**.

4. Adja meg a konfigurálni kívánt beállításokat:

    - [Windows 10 és újabb](education-settings-windows.md)

5. A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A beállítások megadása és a profil létrehozása után a profil megjelenik a profilok listájában. A következő lépés a [profil hozzárendelése egyes csoportokhoz](device-profile-assign.md).

## <a name="next-steps"></a>További lépések

Listájának megtekintéséhez a [Windows 10-es oktatási beállítások](education-settings-windows.md) és azok leírásait.

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

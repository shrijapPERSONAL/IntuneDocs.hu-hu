---
title: Megosztott vagy több felhasználó-eszköz beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Adjon hozzá, és használja a Windows 10 és Windows Holographic for Business eszközök megosztott eszközök vagy a Microsoft Intune-ban több felhasználó használja. Tekintse meg az összes beállítás listáját, és mit tesznek az eszközökön, beleértve a Microsoft HoloLens. A Vendég fiók szabályozhatja, fiókok kezelése, és törli az inaktív fiókok, engedélyezése vagy letiltása helyi tárolójára történő mentése, állítsa be a power és beállítások alvó állapotba, válassza ki, amikor frissítések telepítve vannak, és eszközök használata az eszközkonfigurációs profil oktatási környezetben.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c2cf06508cc21682a580c09e8207343b09e39eb
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392987"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Hozzáférés-vezérlése, a fiókok és a power funkcióinak megosztott PC vagy több felhasználói eszközök Intune-nal

Több felhasználóval rendelkező eszközök megosztott eszközök nevezik, és a mobileszköz-felügyelet (MDM) megoldások gyakori részét képezik. A Microsoft Intune-nal, testre szabhatja a következő platformot futtató megosztott eszközök:

- A Windows 10 Professional és újabb
- Windows 10 Enterprise és újabb
- A Windows Holographic for Business, például a HoloLens

Például iskolák rendelkezik eszközöket, amelyek általában sok tanulói is használják. Ezzel a beállítással az iskolája Intune-rendszergazda bekapcsolhatja a megosztott PC-funkció, hogy egy felhasználó egyszerre. Nem lehet átállítani a diákok között különböző bejelentkezett fiókok az eszközön. A tanulói kijelentkezésekor, meg eltávolítani az összes felhasználó-specifikus beállításokat.

A végfelhasználók ezek megosztott eszközökhöz, a Vendég fiók bejelentkezhet. Miután a felhasználók bejelentkeznek, a hitelesítő adatok lettek gyorsítótárazva. Mint az eszközön, végfelhasználók csak a get funkciókat engedélyezi a hozzáférést. Ha például úgy dönt, amikor az eszköz alvó állapotba mód, ha a felhasználók tekintse meg és fájlok helyi mentése, engedélyezheti vagy letilthatja az energiagazdálkodási beállításokat, és több. Azt is szabályozhatja, ha törli a Vendég fiók, ha a felhasználó jelentkezik ki, vagy az inaktív fiókok törlése a küszöbérték elérésekor.

Ez a cikk bemutatja, hogyan hozhat létre egy profilt, és a hozzájuk tartozó leírások az elérhető beállításokra mutató hivatkozásokat tartalmaz.

A profil létrehozásakor az Intune-ban üzembe helyezése, vagy rendelje hozzá a profilt az eszközcsoportok a szervezetben. Ez a profil eszközcsoportokra a vegyes eszköztípusok és az operációs rendszer (OS) verziói is hozzárendelhetők.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: Válassza ki **Windows 10 és újabb**.
   - **Profil típusa**: Válassza ki **megosztott több felhasználó-eszköz**.

4. Adja meg a beállításokat a [Windows 10 és újabb](shared-user-device-settings-windows.md) vagy [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A profil létrehozásáról és jelennek meg a listában, de azt nem csinál semmit még. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md) eszközcsoportokra a szervezetben.

## <a name="next-steps"></a>További lépések

- Tekintse meg az összes beállítását [Windows 10 és újabb](shared-user-device-settings-windows.md) és [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

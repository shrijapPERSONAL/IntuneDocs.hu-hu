---
title: A PIN-kód segítségével jelentkezzen be a-beli Microsoft Intune Windows 10-eszközökön |} A Microsoft Docs
description: Segítségével Windows Hello for Business engedélyezése a felhasználók számára, hogy jelentkezzen be a PIN-kód, az ujjlenyomattal és egyéb eszközöket. Az identity protection konfigurációs profil létrehozása az Intune-ban Windows 10-es eszközökhöz, ezekkel a beállításokkal, és rendelje hozzá a profilt felhasználói csoportokat és eszközcsoportokat.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d52c140a8cf408955d8a8d4cbce6038349b5b66b
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395797"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Használjon Windows Hello for Business Windows 10 rendszerű eszközökön a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows Hello for Business a módszer azáltal, hogy a jelszavak, intelligens kártyák és a virtuális intelligens kártyák a Windows-eszközökön való bejelentkezéshez. Az Intune beépített beállítást tartalmaz, így a rendszergazdák konfigurálhatja és használhatja a Windows Hello for Business. Például használhatja ki ezeket a beállításokat:

- Windows vállalati Hello engedélyezése a vállalati eszközök és felhasználók számára
- Eszköz PIN-kód követelményeket, ideértve a minimális vagy maximális hosszúságú PIN-kód beállítása
- Lehetővé teszi a kézmozdulatok, például egy ujjlenyomat, amely a felhasználók (vagy nem használható), jelentkezzen be a eszközök

Ez a funkció a következő rendszerű eszközökre vonatkozik:

- Windows 10 és újabb
- Windows 10 mobil verzió
- Windows Holographic for Business

Az Intune használja a "profilok" hozhat létre, és ezeket a beállításokat a szervezet igényeinek megfelelően. Miután hozzáadta ezeket a funkciókat az egy profilt, leküldéses, vagy telepítheti ezeket a beállításokat a felhasználói és eszközcsoportokra a szervezetben.

Ez a cikk bemutatja, hogyan hozhat létre eszközkonfigurációs profil. Az összes beállítás listáját, és mit tesznek, lásd: [eszközbeállítások Windows 10-es Windows Hello for Business engedélyezése](identity-protection-windows-settings.md).

## <a name="create-the-device-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **a Microsoft Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki **Windows 10 és újabb**. A Vállalati Windows Hello csak a Windows 10 vagy újabb rendszerű eszközökön támogatott.
    - **Profil típusa**: Válassza ki **Identity protection**.
    - **A vállalati Windows Hello konfigurálása**: Válassza ki, hogyan szeretné konfigurálni Windows Hello for Business. A választható lehetőségek:

        - **Nincs konfigurálva**: [Windows Hello for Business kiosztja](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) az eszközön. Ha csak felhasználókhoz rendel hozzá identitásvédelmi profilokat, az eszközkörnyezet alapértelmezett beállítása a **Nem konfigurált** lesz.
        - **Letiltott**: Ha nem szeretné használni Windows Hello for Business, akkor válassza ezt a lehetőséget. Ez a beállítás letiltja a Windows Hello for Business az összes felhasználó számára.
        - **Engedélyezett**: Válassza ezt a beállítást, [kiépítése]((https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning)), és a Windows Hello for Business beállításainak konfigurálása az Intune-ban. Adja meg a konfigurálni kívánt beállításokat. Az összes beállítások listáját, és mit tesznek lásd:

            - [Windows 10-es eszközbeállítások Windows Hello for Business engedélyezése](identity-protection-windows-settings.md)

4. Ha elkészült, a módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A profil jön létre, és megjelenik a profilok listájában. Ezután [hozzárendelése](device-profile-assign.md) ezt a profilt a felhasználói és eszközcsoportok az igényeinek.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>További lépések

- Tekintse meg az összes [a beállításokat, és mit tesznek](identity-protection-windows-settings.md).
- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

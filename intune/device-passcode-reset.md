---
title: Eszközök PIN-kódjának visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A PIN-kód eltávolítása művelettel eltávolíthatja vagy visszaállíthatja a PIN-kódot az Intune-nal kezelt vagy figyelt eszközökön.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a233c62b76901d9bad00aa6d8b2a8a4dd45dea96
ms.sourcegitcommit: 024cce10a99b12a13f32d3995b69c290743cafb8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/14/2018
ms.locfileid: "39039301"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ha új PIN-kódot szeretne létrehozni egy eszközhöz, használja a  **PIN-kód eltávolítása** műveletet. Ez a művelet csak a munkahelyi profilnál kéri a PIN-kód alaphelyzetbe állítását. Az androidos munkahelyi profilok esetében az eszköz PIN-kódjának alaphelyzetbe állítása nem támogatott.

## <a name="work-profile-pin-reset-supported-platforms"></a>A munkahelyi profil PIN-kódjának alaphelyzetbe állítása szempontjából támogatott platformok

- Munkahelyi profillal regisztrált, 8.0-ás vagy újabb verziójú Android-eszközök 
- 6.0-ás vagy régebbi verziójú Android-eszközök
- Vállalati androidos kioszkeszközök
- iOS 
     
## <a name="unsupported-platforms"></a>Nem támogatott platformok

- Munkahelyi profillal regisztrált, 7.0-ás vagy régebbi verziójú Android-eszközök
- 7.0-ás vagy újabb verziójú Android-eszközök
- macOS
- Windows

## <a name="reset-a-passcode"></a>Új PIN-kód kérése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. Az Ön által kezel eszközök listájáról válasszon ki egy eszközt, majd válassza a **...További** lehetőséget. Majd válassza a **PIN-kód eltávolítása** távoli eszközműveletet.

## <a name="resetting-android-work-profile-passcodes"></a>Androidos munkahelyi profilok PIN-kódjainak alaphelyzetbe állítása

A támogatott, androidos munkahelyi profilt használó eszközök végfelhasználói új feloldó jelszót vagy biztonsági kérdést kapnak a felügyelt profilhoz. 

Az Android 8.0-s munkahelyi profilos eszközökön a végfelhasználók a regisztráció befejeződése után azonnal értesítést kapnak, hogy aktiválják alaphelyzetbe állítási PIN-kódjukat. Az értesítés akkor jelenik meg, ha egy munkahelyi profil jelszavát kell beállítani. A PIN-kód megadása után az értesítés eltűnik.

## <a name="resetting-ios-passcodes"></a>iOS PIN-kódok alaphelyzetbe állítása

A PIN-kódok törlődnek az iOS-eszközökről. Ha PIN-kódokra vonatkozó megfelelőségi szabályzat van érvényben, az eszköz megkéri a felhasználót, hogy állítson be egy új jelszót a Beállítások területen. 

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

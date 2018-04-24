---
title: Eszközök PIN-kódjának visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A PIN-kód eltávolítása művelettel eltávolíthatja vagy visszaállíthatja a PIN-kódot az Intune-nal kezelt vagy figyelt eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19b30315fa26dd53b5e383bc9e4bef5c65b89962
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ha új PIN-kódot szeretne létrehozni egy eszközhöz, használja a  **PIN-kód eltávolítása** műveletet.

## <a name="supported-platforms"></a>Támogatott platformok

- Munkahelyi profillal regisztrált, 7.0-ás vagy újabb verziójú Android-eszközök
- 6.0-ás vagy régebbi verziójú Android-eszközök
- iOS 
     
## <a name="unsupported-platforms"></a>Nem támogatott platformok

- Munkahelyi profillal regisztrált, 6.0-ás vagy régebbi verziójú Android-eszközök
- 7.0-ás vagy újabb verziójú Android-eszközök
- macOS
- Windows

## <a name="reset-a-passcode"></a>Új PIN-kód kérése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. Az Ön által kezel eszközök listájáról válasszon ki egy eszközt, majd válassza a **...További** lehetőséget. Majd válassza a **PIN-kód eltávolítása** távoli eszközműveletet.

## <a name="resetting-android-for-work-passcodes"></a>Android for Work PIN-kódok alaphelyzetbe állítása

A támogatott Android for Work-eszközök végfelhasználói új eszközfeloldó jelszót vagy kezelt profilra vonatkozó kérdést kapnak. A 7.0-ás vagy újabb Android-verziójú munkahelyi profilok esetében a végfelhasználók egy jelszóvisszaállítási értesítést kapnak közvetlenül a regisztráció után. Az értesítés akkor jelenik meg, ha egy munkahelyi profil jelszavát kell beállítani. A PIN-kód megadása után az értesítés eltűnik.

## <a name="resetting-ios-passcodes"></a>iOS PIN-kódok alaphelyzetbe állítása

A PIN-kódok törlődnek az iOS-eszközökről. Ha PIN-kódokra vonatkozó megfelelőségi szabályzat van érvényben, az eszköz megkéri a felhasználót, hogy állítson be egy új jelszót a Beállítások területen. 

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

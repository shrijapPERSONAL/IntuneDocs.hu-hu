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
ms.openlocfilehash: 81330083830eb2e3e1fe3e36217d403a77094a65
ms.sourcegitcommit: 8be5f29107d882c3ecf3dc0ce718a2423f91ce9a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/27/2018
ms.locfileid: "36964725"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ha új PIN-kódot szeretne létrehozni egy eszközhöz, használja a  **PIN-kód eltávolítása** műveletet.

## <a name="supported-platforms"></a>Támogatott platformok

- Munkahelyi profillal regisztrált, 8.0-ás vagy újabb verziójú Android-eszközök
- 6.0-ás vagy régebbi verziójú Android-eszközök
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

## <a name="resetting-android-for-work-passcodes"></a>Android for Work PIN-kódok alaphelyzetbe állítása

A támogatott Android for Work-eszközök végfelhasználói új feloldó jelszót vagy biztonsági kérdést kapnak a felügyelt profilhoz. A 8.0-ás vagy újabb Android-verziójú munkahelyi profilok esetében a végfelhasználók egy jelszó-visszaállítási értesítést kapnak közvetlenül a regisztráció után. Az értesítés akkor jelenik meg, ha egy munkahelyi profil jelszavát kell beállítani. A PIN-kód megadása után az értesítés eltűnik.

## <a name="resetting-ios-passcodes"></a>iOS PIN-kódok alaphelyzetbe állítása

A PIN-kódok törlődnek az iOS-eszközökről. Ha PIN-kódokra vonatkozó megfelelőségi szabályzat van érvényben, az eszköz megkéri a felhasználót, hogy állítson be egy új jelszót a Beállítások területen. 

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

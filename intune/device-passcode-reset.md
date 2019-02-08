---
title: Eszközök PIN-kódjának visszaállítása a Microsoft Intune-nal – Azure | Microsoft Docs
description: A PIN-kód eltávolítása művelettel eltávolíthatja vagy visszaállíthatja a PIN-kódot az Intune-nal kezelt vagy figyelt eszközökön.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aecc509a0a98f277de0fc550317151d71b4ecb2d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839662"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Eszközök PIN-kódjának visszaállítása vagy eltávolítása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a dokumentum a PIN-kód eszközszintű alaphelyzetbe állítását és a munkahelyi profil PIN-kódjának alaphelyzetbe állítását ismerteti vállalati Android (korábbi nevén Android for Work, vagy AfW) rendszerű eszközökön. Ezt a megkülönböztetést fontos szem előtt tartani, hiszen a követelmények eltérőek lehetnek. Az eszközszintű PIN-kód alaphelyzetbe állítása az egész eszközön átállítja a PIN-kódot. A munkahelyi profil PIN-kódjának alaphelyzetbe állítása csak a felhasználó munkahelyi profiljára vonatkozó PIN-kódot állítja át a vállalati Android rendszerű eszközökön.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Az eszközszintű PIN-kód alaphelyzetbe állításának támogatott platformjai

| Platform | Támogatott? |
| ---- | ---- |
| 6.x vagy régebbi verziójú Android-eszközök | Igen |
| Vállalati Android rendszerű eszközök kioszkmódban | Igen |
| iOS-eszközök | Igen |
| Munkahelyi profillal regisztrált, 7.0-s vagy régebbi verziójú Android-eszközök | Nem |
| 7.0-ás vagy újabb verziójú Android-eszközök | Nem |
| macOS | Nem |
| Windows | Nem |

Az Android-eszközök esetében ez tulajdonképpen annyit jelent, hogy az eszközszintű PIN-kód alaphelyzetbe állítása csak 6.x vagy korábbi verziójú, illetve kioszkmódban futó vállalati Android rendszerű eszközökön támogatott. Ennek az az oka, hogy a Google többé nem támogatja az Android 7 rendszerű eszközökön a PIN-kód/jelszó alaphelyzetbe állítását eszközrendszergazda által jóváhagyott alkalmazásokból, minden MDM-szállítóra vonatkozóan.

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Azok a platformok, amelyeken alaphelyzetbe állítható a vállalati Android munkahelyi profil PIN-kódja

| Platform | Támogatott? |
| ---- | ---- |
| Munkahelyi profillal regisztrált, 8.0-s vagy újabb verziójú vállalati Android-eszközök | Igen |
| Munkahelyi profillal regisztrált, 7.x vagy korábbi verziójú vállalati Android-eszközök | Nem |
| 7.x vagy korábbi verziójú Android-eszközök | Nem |
| iOS | Nem |
| macOS | Nem |

A munkahelyi profilokhoz a PIN-kód alaphelyzetbe állítása művelettel hozhat létre új PIN-kódot. Ez a művelet elindítja a PIN-kód alaphelyzetbe állítását, és új, ideiglenes PIN-kódot hoz létre, kizárólag a munkahelyi profilhoz. 

## <a name="reset-a-passcode"></a>Új PIN-kód kérése


1. Jelentkezzen be a [az Azure portal](https://portal.azure.com) azokkal a következő szerepkörök: Az Azure Active Directory globális rendszergazdája, az Azure Active Directory Intune Szolgáltatásadminisztrátor, ügyfélszolgálati operátor vagy szerepkörű rendszergazda. Szerepkörök és engedélyek teljes listáját lásd: a [Intune RBAC-táblázat](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).
2. Válassza a **Minden szolgáltatás** lehetőséget, szűrjön az **Intune**-ra, és válassza a **Microsoft Intune** elemet.
3. Válassza az **Eszközök**, majd a **Minden eszköz** lehetőséget.
4. Az Ön által kezel eszközök listájáról válasszon ki egy eszközt, majd válassza a **...További** lehetőséget. Majd válassza a **PIN-kód eltávolítása** távoli eszközműveletet.

## <a name="reset-android-work-profile-passcodes"></a>Androidos munkahelyi profilok PIN-kódjának alaphelyzetbe állítása

A támogatott, androidos munkahelyi profillal regisztrált vállalati eszközök végfelhasználói új feloldó jelszót vagy biztonsági kérdést kapnak a felügyelt profilhoz.

A 8.x vagy újabb verziójú, munkahelyi profillal regisztrált vállalati Android-eszközök végfelhasználói a regisztráció befejezése után azonnal értesítést kapnak arról, hogy aktiválniuk kell az új PIN-kódot. Az értesítés akkor jelenik meg, ha a munkahelyi profilban kötelező jelszót megadni, és be is van állítva jelszó. A PIN-kód megadása után az értesítés eltűnik.


## <a name="remove-ios-passcodes"></a>iOS-beli PIN-kódok eltávolítása

A PIN-kódok alaphelyzetbe állítás helyett törlődnek az iOS-eszközökről. Ha PIN-kódokra vonatkozó megfelelőségi szabályzat van érvényben, az eszköz megkéri a felhasználót, hogy állítson be egy új jelszót a Beállítások területen.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök** panel **Eszközműveletek** szakaszában tekintheti meg.

---
title: Rövid útmutató – Kötelező jelszóhossz beállítása Android-eszközökhöz
titlesuffix: Microsoft Intune
description: Ebben a rövid útmutatóban a Microsoft Intune-t használjuk az Android-eszközöktől elkért jelszavak hosszának beállításához.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395284"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Rövid útmutató: Kötelező jelszóhossz beállítása Android-eszközökhöz

Ebben a rövid útmutatóban a Microsoft Intune-t használjuk annak beállítására, hogy a rendszer az Android-eszközöket használó munkatársaktól adott hosszúságú jelszót kérjen el, mielőtt engedélyezné az eszközökön található információkhoz való hozzáférést. 

> [!IMPORTANT]
> Az alkalmazottak tartalmainak védelme érdekében a jelszóbeállítások mellett egyéb rendszerbiztonsági beállításokat használatát is érdemes fontolóra venni. További információkért tekintse meg a [rendszerbiztonsági beállításokat](compliance-policy-create-android-for-work.md#system-security-settings) ismertető cikket.

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Bejelentkezés az Intune-ba

Jelentkezzen be az [Intune-ba](https://aka.ms/intuneportal) globális rendszergazdaként vagy Intune-szolgáltatásadminisztrátorként. Az Intune-t az Azure Portalon a **Minden szolgáltatás** > **Intune** útvonalon érheti el. Az Intune a **Figyelés + felügyelet** szakaszban található.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása
1. A **Microsoft Intune** panel megnyitása után válassza az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** lehetőséget.
2. A **Név** mezőben adja meg az **Android compliance** (Android-megfelelőség) nevet. Egy **leírást** is adjon meg.
3. A **Platform** beállításban válassza az **Android** lehetőséget. 
4. Kattintson a **Beállítások** > **Rendszerbiztonság** elemre az Android **Rendszerbiztonság** paneljének megjelenítéséhez.
5. A **Jelszó** szakaszban kattintson a **Jelszó szükséges a mobileszközök feloldásához** lehetőség mellett található **Kötelező** gombra.
6. A **Jelszó minimális hossza** legyen **6**.  

    ![Képernyőkép egy csoport létrehozásáról a Microsoft Intune-ban](./media/quickstart-set-password-length-android-01.png)

7. Ha elkészült, az **OK** gombra kattintva zárja be a **Rendszerbiztonság** panelt. 
8. Az **Android-megfelelőségi szabályzat** bezárásához kattintson az **OK** gombra. 
9. A szabályzat létrehozásához kattintson a **Létrehozás** elemre.

Ha sikeresen létrehozta a szabályzatot, az megjelenik az **Eszközmegfelelőség – Szabályzatok** listájában. 

## <a name="next-steps"></a>További lépések

Ebben a rövid útmutatóban az Intune használatával létrehozott egy megfelelőségi szabályzatot az alkalmazottak Android-eszközeihez, hogy legalább hat karakter hosszúságú jelszót kelljen hozzájuk megadni.

> [!div class="nextstepaction"]
> [Automatikus regisztráció beállítása](quickstart-setup-auto-enrollment.md)
